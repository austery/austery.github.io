---
author: Latent Space
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=abYcV5LHMG4
speaker: Latent Space
tags:
  - formal-verification
  - mathematical-reasoning
  - ai-collaboration
  - lean-language
  - super-intelligence
title: 超越非正式AI：Carina Hong谈Axiom Math的形式化验证与数学发现
summary: Axiom Math 创始人兼CEO Carina Hong 探讨了公司如何通过形式化验证和Lean语言在数学领域取得突破，并获得2亿美元A轮融资。她强调验证AI旨在扩展智能而非纠正错误，并介绍了Axiom Prover在解决数学难题上的卓越表现。访谈还深入讨论了数学发现工具的开源、形式化验证在软件和硬件领域的应用前景，以及AI在编码和规范化中的作用，最终展望了通过形式化方法实现超级智能的愿景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Carina Hong
  - Brandon Anderson
  - R.J. Haneki
  - Ramanujan
  - Terence Tao
  - Kevin Buzzard
  - Shou
  - Lawrence Tribe
  - Julie Draw
  - Donald Knuth
companies_orgs:
  - Axiom Math
  - Atomic AI
  - Mirror Omix
  - Anthropic
  - OpenAI
  - Meta
  - Google DeepMind
  - European Space Agency
  - Boeing
  - Airbus
  - AWS
  - Mass Arena
  - MIT
  - UCL Gatsby Institute
  - Stanford
  - Facebook
  - SpaceX
products_models:
  - Axiom Prover
  - AlphaProof
  - Lean
  - Arian spacecraft
  - GPT
  - DeepSeek
  - Copra
  - DeepSea Prover
  - GoTo Prover
  - Axel (AXL)
  - Claude
media_books:
  - The Man Who Knew Infinity
status: evergreen
---
### 验证AI的愿景

**Carina Hong**: 但我认为，现在是**验证AI**首次开启合作的时刻，无论是人机协作，还是在蓝图规划之前的人人协作。**Lean**是一种基础，是一种验证形式语言，然后是像我们现在看到的人机协作，以及未来AI代理之间的协作。我认为**验证AI**是为了开放性，而不是为了满足封闭行业的需求。我认为验证不应该仅仅是为了解决幻觉问题。对我来说，验证是为了扩展才华，复合才华。这就像回到协作的观点，它让**拉马努金**成为一个更强大的数学家。他本身已经很强了，但验证帮助他扩展了才华，既能向上扩展，也能向外扩展。

<details>
<summary>Original English</summary>

**Carina Hong**: But it's for the first time now, I think, verified AI is to open up collaboration, either it's human-AI collaboration, well before blueprinting, that's human-human collaboration, and **Lean** was a grounding, was a verification formal language, and then human-AI collaboration like we're seeing now, future AI agent-agent-agent like collaboration. Like I think **verified AI** is for openness, it's not for meeting the requirements of closed industries. And I think just like I think verification should not be about, oh, I remember like, you know, there's this article like chatbots, it's mixed up of is math solution to hallucination. Verification to me is not about lousiness. Verification to me is about scaling brilliance, compounding brilliance. It's like just kind of going back to the collaboration point. It's about **Ramanujan** being a much stronger mathematician. He was already a really strong one, but verification helps him extend the brilliance, like both kind of like scale up and scale out.

</details>

**Brandon Anderson**: 欢迎收听Leen Space AR for Science播客。我是**Brandon Anderson**，我在**Atomic AI**公司开发RNA疗法。今天与我一同主持的是**Mirror Omix**的CTO **R.J. Haneki**，他致力于空间转录组学研究。我们非常荣幸邀请到**Axiom Math**的CEO兼创始人**Carina Hong**。**Axiom**在多个领域引起了轰动。首先，他们去年12月在**Putinome**考试中获得了满分。我认为他们还声称是第一个使用形式化验证来证明研究猜想的AI。非常令人兴奋的是，他们昨天刚刚宣布完成了一笔相当大的A轮融资。欢迎来到节目，谢谢你来。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Welcome to the Leen Space AR for science podcast. I'm **Brandon Anderson**. I build RNA therapeutics at **Atomic AI** and I'm joined by **R.J. Haneki**, the CTO of **Mirror Omix**, working on spatial transcrytoics. It's a pleasure to have **Carina Hong** from CEO and founder of **Axiom Math**. **Axiom** has made a splash in several different areas. First, they were they got a perfect score in the **Putinome** last December. I think they also had the claim of the first AI to prove research conjectures using formal verification and very exciting they just yesterday announced quite a large Series A. Yeah, welcome to the show. Thank you for having me.

</details>

**Brandon Anderson**: 你们刚刚筹集了2亿美元，正如你的一位同事所说，这基本上相当于美国每年数学研究的全部预算。

<details>
<summary>Original English</summary>

**Brandon Anderson**: You just raised $200 million, which as one of your colleagues said, this is like basically the entire like US math budget for math research each year.

</details>

**Carina Hong**: 真的吗？

<details>
<summary>Original English</summary>

**Carina Hong**: Is that true? Actually,

</details>

**Brandon Anderson**: 根据他的LinkedIn帖子，是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: according to his LinkedIn post, yeah.

</details>

**Carina Hong**: 哇。

<details>
<summary>Original English</summary>

**Carina Hong**: Wow.

</details>

**Brandon Anderson**: 2.5亿美元显然是每年的数学预算。

<details>
<summary>Original English</summary>

**Brandon Anderson**: 250 million is our apparently the annual math budget.

</details>

**Carina Hong**: 我们应该在数学研究上投入更多资金。

<details>
<summary>Original English</summary>

**Carina Hong**: We should spend more on math research.

</details>

**Brandon Anderson**: 是有点悲哀。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah, it's kind of sad, but

</details>

**Carina Hong**: 是啊，我知道。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I know.

</details>

**Brandon Anderson**: 但无论如何，作为一个热爱数学的书呆子，这真的很酷。我的意思是，当我听到你们筹集了2亿美元，估值达到16亿美元时，我简直惊呆了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: But anyway, like, you know, as a, you know, as a nerd who loves math, that's like really cool. But I mean, I'm just like that kind of blew my mind like what I heard that like, okay, so like, yeah, how is it 200, 200 million, I guess 1.6 billion valuation. Yeah, I don't know.

</details>

**Carina Hong**: 是的。非常非常高兴能来到这里。另外，我认为这是一次A轮融资，所以这次播客的时机非常有趣。我们是一家成立七八个月的公司，所以这笔融资对我们意义重大。这是一个非常酷的里程碑。我们目前大约有30名员工。所以，我认为这笔资金将为我们提供所需的动力，以加速我们迄今为止强大的执行势头。我认为人们看待我们有很多种方式。有人把我们看作一家数学初创公司。所以，数学初创公司，**Lean**初创公司，我们做的其他事情显然是形式化验证。我们认为验证是数学领域一个非常好的首选市场。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Um, well, super, super excited to be here. Um, also I think like, you know, this is a Series A, so it's very, very interesting, timely, timely podcast. Uh, we are like a seven, eight months old company, so it definitely means a lot to us. It's a really cool milestone. Um, we're currently about like 30 people now. So kind of going into, I think this amount of funding will like give us a fuel that we it needs to to to accelerate um, the strong execution momentum that we have so far. Um, I think like people think of us like there are many kind of ways to think about people think of as us as a math startup. So math startup, **Lean** startup, the other obviously things that we do um, that are formal verification. We think verification is a really good best first market for math.

</details>

**Brandon Anderson**: 所以我认为这次融资将让我们能够探索一些应用领域，正如我的同事CTO **Shou**在A轮融资的小型发布视频中说的，它让我们“拓宽我们的梦想”。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And so I think this fundraise is going to like let us explore some of the applied domains, uh, as my colleague CTO **Shou** said in the the little launch video um of the Series A we had is it it lets us broaden our dreams. So yeah.

</details>

**Brandon Anderson**: 但仍然是2亿美元和16亿美元的估值。这有市场吗？我的意思是，我当时想，显然你们不仅仅是为了证明事情的乐趣而做这些，尽管我相信其中有很多乐趣。

<details>
<summary>Original English</summary>

**Brandon Anderson**: But still like $200 million and I guess a 1.6 billion valuation. How is there a market for that? I mean, I was like, obviously you're not doing this just for the fun of proving things, although I'm sure there's a lot of that, but

</details>

### 形式化验证的市场潜力

**Carina Hong**: 让我们回到2024年，当时**01**等模型刚刚发布。**Anthropic**当时秘密在做什么？是编码。每个人都知道他们在做编码，像**OpenAI**、**Meta**、**Ax**，每个人都完全知道**Anthropic**在做编码，但他们都忽视了它。他们认为“哦，他们是B2B公司，他们只想要一个垂直领域。”人们认为编码是一个垂直领域，但现在看看我们今天在哪里。编码实现了从编码到推理的强大迁移学习，基本上垄断了推理的未来。我认为这真的非常令人震惊。那些当时从事编码工作的人，我认为他们相信我们现在对数学和**Lean**的信念，那就是如果你有更结构化和形式化的数据，它将比我们正在解决的特定垂直领域更具横向性。所以，如果你今天我们以非正式的方式做数学，比如标准的思维链数据，根据人类偏好训练一个数学模型，那么我可能会说我们只是一个数学初创公司。但是，当我们追求数学时，我们也在做一些对其他领域具有迁移学习作用的事情。所以，我认为这更广泛的图景是，虽然公司的DNA仍然是数学，我们所有人都是数学迷，这是一个非常强烈的文化宣言。每个人都有一个伟大的使命，让AI成为一个超人数学家，就像我们在**Pudnam**上看到的一批研究猜想一样。事实上，我们还有另一批正在进行中。我们还认为这将是**验证推理**的基础，我们稍后会谈论**验证AI**，因为我认为你还有其他问题。

<details>
<summary>Original English</summary>

**Carina Hong**: So let's let's bring us back to 2024, so when, you know, **01** recently models like just came out. What is what was **Anthropic** kind of like secretly working on back then? It was coding. And everyone knows they're working on coding like **OpenAI**, **Meta**, **Ax**, everyone has full knowledge that **Anthropic** was working on coding and they just like overlooked it. They thought, oh, there are at B2B place, they just want one vertical. People think of coding as one vertical and now look at where we are today. Coding kind of like strong transfer learning from coding to reasoning to basically, you know, a monopoly in the in the future of reasoning and I think that's that's really, really shocking. The people who are working on coding, I think back then believe in something that we believe, you know, similarly with math and **Lean** now, which is that if you have more structured and formal data, it's going to be a lot more horizontal than the specific vertical we are tackling. So, you know, if today we are doing, you know, math informal way, like the standard train of thought data, train a math model based on human preference, then I would say, well, perhaps we are just a math startup, right? But, you know, while we are pursuing math, we are also doing things that do have transfer learning to other to other domains. Um, so I think that's kind of like the broader broader picture is that while the DNA of the company remains math and all of us are math nerds and this is a very strong culture statement. Everyone has a great mission of having AI be a superhuman mathematician like we are seeing on **Pudnam** on a batch of research conjectures. In fact, we have another batch coming. Um, we're also thinking that this is going to be fundamental to **verified reasoning** and we kind of talk a little bit about **verified AI**. I want to talk a little bit about **verified AI** next because I think you have another

</details>

**Brandon Anderson**: 是的，是的，我有很多想问的。所以，我想听听关于**验证AI**的。我确实想深入了解一下。那么，我们知道**Anthropic**和**OpenAI**以及其他公司，他们没有进行形式化验证并将其用于他们的发布和任何其他事情吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. Yeah. I have several things I want like, uh, so I want to hear about the **verified AI**. I do want to dig in a little bit. So, do we know that, you know, **Anthropic** and **OpenAI** and everyone they're not doing formal verification and using that for their rollouts and whatever?

</details>

**Carina Hong**: 我有很多小道消息，可能不应该公开。研究人员之间会交流，他们会玩纸牌游戏。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I have a lot of like rumor mill that I probably shouldn't like put it on the record like I think, you know, like researchers talk, they play card games. Yeah.

</details>

**Carina Hong**: 但他们是否这样做，背后有非常有趣的原因。我认为这就是我的主要观点，如果你在一个前沿实验室，方向确实会因为许多你无法控制的原因而发生很大变化。

<details>
<summary>Original English</summary>

**Carina Hong**: But there there really interesting reasons if they are or not doing it. I think that's like kind of the takeaway I have which is that if you're like at a frontier lab and the direction actually does change a lot for a lot of reasons beyond your control.

</details>

**Carina Hong**: 所以我想把我们带回到**AlphaProof**的时刻，对吧？**AlphaProof**是如此令人惊叹，2024年42题中28题的表现对我来说是**IMO**时刻。它不是2025年的金牌，因为在2024年和2025年，AI模型可以解决所有非组合学问题。唯一的区别是，如果你解决了所有非组合学问题，你在2024年得到28分，在2025年得到35分，因为2025年只有一个组合学问题。在**AlphaProof**之后，我们没有看到**Google DeepMind**在形式化数学方面取得很多成果或进展，这实际上是因为一些不一定是技术性的原因。但是，如果你在一个初创公司，并且你非常专注于形式化数学和**验证AI**，那么你就可以长时间地研究真正酷的问题，并且你更有可能在进展和突破方面达到你想要的目标。

<details>
<summary>Original English</summary>

**Carina Hong**: So I want to kind of like bring us back to the **AlphaProof** moment, right? Like **AlphaProof** was such an amazing that really the 2024 um 28 out of 42 performance was the **IMO** moment for me. It was not gold in 2025 because across 2024 and 2025 AI models could solve all the problem that are not combinatorics. The only difference is that, you know, if you get all the problems that are not combinotaurics, you get 28 in 2024 and 35 in 2025 because there's only one combinatorics question in 2025. Um, after **AlphaProof** kind of like we didn't see a lot of the formal math uh, you know, results or kind of progress from **Google DeepMind** and that's actually because of reasons that are not necessarily technical, but if you're at a startup and you have very singular focus that is formal math and **verified AI**, then um, you know, you get to work on really cool problem for a long time and you have like a lot a lot higher likelihood to get to where you want to be in terms of like progress and breakthrough unlock.

</details>

**Brandon Anderson**: 是的，请为我们定义一下。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So yeah, just define that for us.

</details>

**Carina Hong**: 是的，很多人认为**形式化验证**是一个古老的话题。它存在的时间比深度学习早得多，它存在于基于规则的计算机科学时代。自1980年代以来，对形式化验证一直有非常强烈的推动。有一些非常有趣的历史轶事，例如，我认为巴黎工会要求地铁系统的自动切换必须经过形式化验证以确保安全。所以，这是一个非常有趣的关于技术的工会。在**挑战者号**事故前后，**欧洲航天局**一直在使用形式化验证来验证**阿丽亚娜飞船**。**波音**和**空客**也进行了验证。近年来，我认为**AWS**有很多关于自动化推理的推动，因为他们有很多企业客户，这些客户确实要求事情必须100%经过验证，不能遗漏任何边缘情况，而一般的测试无法满足需求。所以很多人认为验证是一件令人烦恼的事情，因为它就像税收和合规性一样，只是为了确保我们符合要求，对吧？但这真的不是。我们谈论验证，我认为我们的竞争对手在发布时谈论形式化验证，他们是在幻觉的背景下谈论的。也许对他们来说，形式化验证是为了解决幻觉，解决错误。但对我们来说，不，对我们来说，**验证AI**是为了才华。它是为了扩展和复合超级智能。这是一个相当深刻的观点，有时需要一些解释。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, like a lot of people think about **formal verification** as an ancient, you know, subject. Um, it it existed like as long as, you know, way before like like deep learning and it existed in the time of rule-based computer science. Uh, there's this really strong push of like **formal verification** around like since ever since 1980s, uh, really interesting historic anecdotes such as, uh, I think the Paris trade union demanded that the automatic switching of the subway system needs to be formally verified for safety purpose. So quite interesting trade union for for technology, um, and like I think around the time of **Challenger** both before and after **European Space Agency** was using **formal verification** for the **Arian spacecraft**. Uh, it's also interesting **Boeing**, **Airbus** for verification and then more recent years, right? Like I think like there's a lot of push about automated reasoning at **AWS** because they have a lot of enterprise customers that really requires things to be to be 100% you know, verified and there's no edge cases mi uh, like missed and like just general like testing doesn't satisfy the need. So a lot of people think about verification as something that's like annoying because it's like tax and compliance like it's making sure that we are good to go right and like that's really not the and and so we we talked about like verification, I think our competitor when they launched they talk about um **formal verification** pre-reasoning they talked about it uh in the time of hallucination and and maybe for them like **formal verification** is about the lousiness the the hallucination for us. No, like for us **verified AI** is about the brilliance. It's about scaling and compounding super intelligence. So this is quite a deep point and sometimes it takes a little bit of explanation.

</details>

**Carina Hong**: 所以，如果你想想才华的地位，例如**拉马努金**，他是一位杰出的数学家，他能够在不知道如何证明的情况下，仅凭直觉发现许多有趣的公式。他去了剑桥，与**哈代**和**利特尔伍德**合作。在著名的电影《**知无涯者**》中，有一条故事情节讲述了**哈代**强迫他不再依赖直觉，而是进行证明是多么困难。在他学会证明写作后，他成为了一位更强大的数学家，他的直觉成果变成了定理，后代数学家在此基础上继续发展。所以，这是一种扩展和复合我们已经拥有的智能的方式。

<details>
<summary>Original English</summary>

**Carina Hong**: So if you think about like, you know, the the place of brilliance, for example, **Ramanujan** like he's a brilliant mathematician, he was able to find a lot of like interesting formulas just by intuition before he know how to do proofs. So he went to Cambridge um, you know, work with **Hardy** and **Littlewood** and, you know, in the famous movie **The Man Who Knew Infinity**, there's this like storyline of how hard it was for **Hardy** to force him to no longer rely on intuitions and do proofs. After he learned proof writing, he came out as a much more powerful mathematician whose results um like intuitions turn into theorems and future generations of mathematicians build on that those theorems. So it is a way to kind of scale and compound uh the intelligence that we already have.

</details>

**Carina Hong**: 另一个例子是，数学家们几千年来一直用英语或他们各自国家的自然语言编写“代码”。我为什么称之为编写代码？因为有一种社区标准，即严格的逻辑推导。每一步都必须正确无误。否则，你就会被你的数学社区排斥。

<details>
<summary>Original English</summary>

**Carina Hong**: Another example, mathematicians kind of have been writing code in English or their respective countries natural language for thousands of years. And why do I call it writing code? Um, because there's this sort of community standard of rigorous logical deduction. Everything has to be step by step correct. Um, otherwise you will get outcasted by your mass community. Uh, like

</details>

**Brandon Anderson**: 社区的规则。

<details>
<summary>Original English</summary>

**Brandon Anderson**: the law well rules in the community.

</details>

**Carina Hong**: 所以，这很有趣，对吧？因为那是由人类数学家强制执行的，对吧？所以，这是一个同行评审过程。一篇论文的同行评审目前需要两年时间。

<details>
<summary>Original English</summary>

**Carina Hong**: So, so it's interesting, right? Because that is kind of human mathematician enforced, right? And so, uh, it's a peer-review process, peer review of a paper currently takes two years.

</details>

**Brandon Anderson**: 好的，但是证明助手和形式化证明跟踪器，比如**Lean**，仍然找到了自己的位置，对吧？为什么呢？如果我是一个数学家，我的工作可以由其他人同行评审，那我们为什么还需要**Lean**呢？为什么数学家们还要玩**Lean**呢？为什么我们还要谈论基于**Lean**的辅助定理证明呢？这是因为**Lean**可以处理低层次的问题。例如，我们甚至不谈论AI，我们谈论的是**Lean**中的**grind**策略，它目前可以在非常低的层次上处理大量的数学证明。这非常令人震惊，因为我见过另一家在同一领域工作的公司，他们的一些演示，我看了演示，它实际上可以完全由**Lean**中的**grind**策略处理。你能向非专业人士解释一下**Lean**是什么吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay, so but proof assistant and, you know, formal proof trackers like **Lean** still found its place, right? And why? Like if you if I'm a mathematician and, you know, any like my work can be peer reviewed by other humans, like why do we even why do mathematicians even play with **Lean** right? And why do we even like talk about kind of like, you know, **Lean** based um assisted like ser improving it's it's because like it handles a low level, for example, we're not even talking about AI, we're talking about for example, the **grind** tactic in **Lean** it can currently handle a lot of mass proofs like at a very low level and and this is pretty shocking because I have seen, you know, actually another uh company working in the same space like, you know, some of their demo and I look at the demo like it can actually completely be handled by **grind** uh which is a tactic in **Lean**. Can you explain what **Lean** is to non experts?

</details>

### Lean语言及其功能

**Carina Hong**: 好的，是的，我认为我们的顺序有点不对。是的，所以**Lean**是一个计算机程序，有点像用于数学证明。它是一种形式语言，就像它的近亲**Isabelle Coq**或**Rock**，以及其他更远的亲戚，如**Daphne Agda**，这些形式语言构成了整个领域。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. Yeah. I think our order is like a little little wrong. Yeah. So **Lean** is a computer program, uh, a bit like for mass proofs. It is a formal language, um, just like its cousin **Isabelle Coq** or **Rock** um, and um, some other further cousins like **Daphne Agda** like these formal languages whole sector. Yeah.

</details>

**Brandon Anderson**: 它有什么作用？

<details>
<summary>Original English</summary>

**Brandon Anderson**: And what what does it do? It it

</details>

**Carina Hong**: 它基本上是这样的：如果你有一个用**Lean**程序编写的证明，并且假设没有发生任何奇怪的事情，比如你使用了`sorry`（这是一种让你暂时接受某些事情为真的策略），假设一切都是安全的，那么人们就有像`comparator safe verify`和**Axiom**最近推出的`verify proof`这样的工具，它比`comparator`快100倍。然后，一旦你执行了那个程序，它编译后告诉你它是正确的，那么这个证明就是实际正确的。

<details>
<summary>Original English</summary>

**Carina Hong**: It basically if you have a proof written in the program in **Lean** and then uh assuming there's not no any like weird things happening like, you know, like, you know, use of sorry which is a tactic that let you take things for granted assuming everything is is safe um hence P people have tools like comparator safe verify and **Axiom** recently rolled out verify proof that's like 100 times faster than comparator um then, you know, once you kind of execute that program, it like once it compiles and it tells you that is correct, then it is the proof is actually correct.

</details>

**Brandon Anderson**: 所以就像一个类型检查器。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So just like a type checker.

</details>

**Carina Hong**: 是的，它是基于一个叫做**Curry-Howard对应**的结果，它将证明转化为程序。所以，我想谈谈**Lean**的魔力。我认为它是一个非常好的编程语言，原因在于，一方面，如果你根本不关心形式部分，如果你不关心逻辑部分，你只是想用**Lean**编写代码，你可以做到。我们有候选人，实际上，目前在**Lean**基金会工作的人，他在我们的面试过程中用**Lean**编写了自动求导。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, that is based on this result called **Curry-Howard correspondence** which turns proofs into programs. So, so I want to talk about the magic of **Lean**. Why I think it's a really good programming language is because on one hand, if you don't care about the formal part at all, if you don't care about the logic part, you just want to use **Lean** to write code, you can like we have had candidates actually currently um, you know, the person is working at the **Lean** fro um, he wrote autograd in **Lean** in our interview process.

</details>

**Brandon Anderson**: 所以它是一种图灵完备语言。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So it's a it's a a turning complete language.

</details>

**Carina Hong**: 没错。所以你可以用**Lean**做很多事情，它是一种函数式编程语言，对吧？然后你可以用它来做编码，也可以用它来做数学，二合一。

<details>
<summary>Original English</summary>

**Carina Hong**: That's right. So um, you can write you can do a lot of things with **Lean** you can it's a it's a functional programming language right and then you can you can also use it to so you use it to do coding you can use it to do math two in one.

</details>

**Brandon Anderson**: 好的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay.

</details>

**Carina Hong**: 回到我之前想说的，如果数学家们已经强制要求大多数证明都是正确的，比如说，也许不是所有数学家，而是象牙塔里和学术界的人，所有的证明都是正确的，那我们为什么还需要**Lean**这个模型跟踪器呢？这是因为**Lean**有策略可以帮助他们处理低层次的计算或证明或推导，而不是计算。然后，他们就能够在高层次的直觉空间中进行导航。所以我的观点是，对我们来说，形式化验证或**验证AI**不仅仅是为了处理或剔除错误、幻觉和失误。它是为了扩展才华。它是关于超级智能的。事实上，**陶哲轩**也有一个很棒的视频，讲述了如何使用**Lean**作为一种协作方式，因为你可以，没错，这是我想说的另一点。很多人都在思考我们的市场是什么，它必须是某个非常小众的工业社会领域，具有任务关键性、安全关键性，不，那不是总目标市场（TAM）。总目标市场是所有代码。

<details>
<summary>Original English</summary>

**Carina Hong**: And kind of going back to what I was kind of getting at if mathematicians are already enforcing that most proofs, you know, say say maybe not all mathematicians but by but the ivory tower and people in academia all proofs are correct, why do we even need **Lean** the model tracker? It's because **Lean** has tactics that help them handle the low-level calculation or proof or deduction, not calculation. Um, then for them to be able to navigate in a high level intuition space. So this is my point that it is not about like **formal verification** or **verified AI** to us, it's not just about handling or like kicking out the lousiness, the hallucinations, the mistakes. It's about scaling brilliance. It's about super intelligence. I actually **Terrence Tao** has a great video also about using **Lean** to as a way you can collaborate because you can you exactly that's another point I want to I want to talk about right a lot of people think about, you know, what is our what is our market it has to be some like really niche industrial societies area that is mission critical, safety critical, no, that's not the TAM, the TAM is all code.

</details>

**Brandon Anderson**: 总目标市场是对所有AI生成代码的优先拒绝权。

<details>
<summary>Original English</summary>

**Brandon Anderson**: The TAM is a is a right of first refusal on all AI generated a code like for right the first refusal meaning, you know, you get to choose whether you want to verify it.

</details>

**Carina Hong**: 所以这是我想强调的重要一点，那就是人们谈论形式化验证时，几乎觉得它很痛苦，因为它有所有这些严格的要求。

<details>
<summary>Original English</summary>

**Carina Hong**: So this is the important part I want to kind of come across which is that people talk about **formal verification** as almost like painful because it has all these like stringent requirements.

</details>

**Brandon Anderson**: 到目前为止确实如此。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Up until now it has been.

</details>

**Carina Hong**: 是的，对我们来说，**验证生成**实际上意味着性能提升，意味着更高的样本效率，意味着像我们这样的初创公司，尽管我们筹集了一些资金，但计算预算和数据预算都比前沿实验室少，却能够匹配甚至超越超人任务的性能。事实上，在2025年12月我们实时参加的**Pudnam**考试中，这是一个评估许多大型语言模型（LLM）的组织，他们发现最好的LLM **DeepSeek**在120分的考试中得了103分。最好的学生，我们现在知道是来自**MIT**或**芝加哥**的学生，我们不知道是哪一个，因为他们不公布前五名的分数，得了110分，而我们得了120分。所以，这是第一次，我记得当我们开始做这个的时候，人们都在问，一个形式化数学系统，数据量少了几个数量级，是否有可能匹配或击败一个非形式化的LLM？而**Pudnam**是它第一次击败。所以我们不只是考虑它的痛苦和挑战，我们正在考虑**验证生成**带来的性能提升，改进，以及你可以，就像你期望**RL4Lean**一样，因为看到了我们自己编码的证据而有所改进。所以这是我想说的第二点，关于如何看待验证，**验证AI**。

<details>
<summary>Original English</summary>

**Carina Hong**: Yes, and and to us it's actually **verified generation** means performance gain, it means higher sample efficiency, it means a startup like us with like, you know, still we we raise some money but lesser compute budget, lesser data budget than Frontier Lab will be able to match even exceed, you know, performance on superhuman tasks. In fact, for the **Pudnam exam** that we just competed December 2025, which we did in real time **Mass Arena**, which is this organization that evaluates a lot of LLMs, found the best LLM **DeepSeek** got 103 points out of a 120 point exam. The best human obviously we now know is a student from either **MIT** or **Chicago**. We don't know which one um because they don't announce the top five winner score got 110 and we got 120. So it's the first time actually I remember when we were starting this people were like is it even possible that a formal mass, you know, system with so much orders of magnitude last data can can match or beat a a for an informal LLM and **Pudnam** is the first time it beat right and and so we're not thinking about it just about the painfulness, the challenges it pose, we are thinking about the **verified generation** performance gain, the improvement, the the fact that you can, you know, just like you would expect **RL4Lean** seem to to have improvement because of seeing evidence of our own coding. So this is the second point I want to make about like how to think about verification, **verified AI**.

</details>

### Axiom Math与前沿实验室的区别

**Brandon Anderson**: 那么，也许我们可以谈谈为什么。你能描述一下你们所做的与前沿实验室在构建标准RL增强型LLM时所做的有什么不同吗？你们所做的有什么不同？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So maybe we can talk a little bit about why. Can you describe what what is different about what you do versus what the frontier labs, you know, at least when they're building their standard RL enhanced uh LLMs. What what's different about what you do?

</details>

**Carina Hong**: 是的。我们非常依赖一种叫做**Lean**数据的数据。我们谈论过**Lean**，它是我们拥有的所有**Lean**证明数据。你知道它是正确的，所以你知道它是否正确，这非常重要。所以，我们有一个模型系统，这些模型经过后训练，并使用强化学习（RL）或监督微调（SFT）。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So we heavily rely on a kind of data called **Lean** data and we kind of talked about **Lean** is all the all the data um that we have that's **Lean** proofs, you know, it's correct so you you know it's correct or not and that's quite quite important so you know, we have a system of models these models are post-trained and um using RL or SFT.

</details>

**Brandon Anderson**: 所以大型语言模型（LLM）找到了一些基础模型，你直接拿来用，然后进行后训练或持续训练。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So LLM found like some sort of foundation model that you get off the shelf and you post-train it or or continuous.

</details>

**Carina Hong**: 是的。显然，我们倾向于使用开源的基础模型。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. And there's obviously an inclination for open source, you know, base models.

</details>

**Brandon Anderson**: 所以，它会说英语，可能知道如何编码，但你也会对其进行微调或持续训练。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So, it does speak English, probably knows how to code, but it also you fine-tune it or or continue.

</details>

**Carina Hong**: 而且基础模型可能与其他人说的也相似，对吧？如果他们没有预训练他们的模型，对吧？

<details>
<summary>Original English</summary>

**Carina Hong**: And the base model might be similar to what everyone else saying as well, right? Um, if they're not kind of pre-training their model, right?

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 然后我们基本上做这种形式化数学的强化学习（RL）。我认为有一个标准的流程或者说人们使用的“行业诀窍”。我们尽力在此基础上进行创新。我认为我们发现，扩展推理几乎没有障碍，递归地将一个证明目标分解成许多子目标，然后学习回溯。

<details>
<summary>Original English</summary>

**Carina Hong**: And then we basically do this, you know, RL for formal math kind of there's I think a standard pipeline or like, you know, tricks of the trade that people use. We try to innovate really uh on top of it as much as we can. I think that we found um scaling inference to have almost no wall um recursively decomposing uh, you know, a proof goal into many sub goals and then learning to backtrack as well.

</details>

**Brandon Anderson**: 是否存在这样的风险：你从你所知道的特定领域数据集开始，然后你开始在一个空间中递归地展开，但现在你所有的训练数据都局限于某个领域，它仍然只是，比如说，在一个大空间中从你最初的训练数据对数级增长。所以你可能会陷入困境，也就是说，你可能在这方面做得很好，但你只是创造了一个巨大的锯齿状前沿，而其他一些领域则远离它们。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Is there a risk that like you start out with this, you know, what you know and a certain domain of data sets and so on and then you start rolling out, you know, recursively in a space, but now all of your training data is localized in some domain that you it still is only so like maybe logarithmically um in some large space growing from your initial training data. So you could get trapped essentially in that, you know, you could be really good at this, but you just created a big jagged frontier where some other domains are just far from them.

</details>

**Carina Hong**: 我们谈论的是**分布偏移**。所以，是的，这是一个悬而未决的问题，一个在数论方面做得很好的系统是否能在另一个数学领域也做得很好。是的，没错。实际上，我认为我们看待这个问题的方式是，这取决于拓扑学是否有很多现有的定义，几乎就像数学基础设施一样。

<details>
<summary>Original English</summary>

**Carina Hong**: **Distribution shift** we're talking about. So yes, so so, you know, it is an open question whether a uh a system that can do really well in number theory can do well in uh give me, you know, another another field of math. Yeah, exactly. Well, actually, I think this the way we think about it is it depends. It depends on whether topology has a lot of the um existing definitions as almost like, you know, the the math infrastructure.

</details>

**Carina Hong**: 现有。因为人们过去发现，当人们在构建**Mathlib**代数时，他们可以直接。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, existing because what people have found in the past is when people were building out **Mathlib** algebra um, you know, book work um, like they they can just.

</details>

**Brandon Anderson**: 所以**Mathlib**是**Lean**的本科图书馆之类的东西。所以它就像你在本科数学中学到的所有证明，它们都以某种方式存在。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So **Mathlib** being the **Lean** like undergraduate library kind of stuff. So it's like all the proofs that you learn in undergraduate math and they're all sort of in.

</details>

**Carina Hong**: 是的。例如，我的一些朋友，他们现在在**Axiom**工作。这真是一个疯狂的轮回时刻。**Kenny**，我们认识五六年了，他是第一个告诉我**Lean**的人。他当时和**Kevin Buzzard**一起构建**Mathlib**。在**Mathlib**中，代数的编码比分析学容易得多。所以这很有趣，因为对于分析学来说，围绕收敛、极限等许多定义变得很棘手。所以我认为今天的**Mathlib**中没有很多拓扑学，就微分拓扑学、微分几何学之类的而言。所以，我们的系统可能在这些领域表现不佳，因为它甚至没有可以作为基础的定义。但在那些定义已经存在的领域，我们在分布多样性方面做得相当不错。我们有很好的表现，解决了数论、交换代数、代数几何、一些离散数学和概率论中的开放研究问题。

<details>
<summary>Original English</summary>

**Carina Hong**: Vain. Yeah. So for example, some of my friends um who currently are **Axiom**. It's, you know, crazy like full circle back moment. Um **Kenny** um, we're like friends for like, you know, five, six years and he was the first one to tell me about **Lean**. He was working with **Kevin Buzzard** to build out **Mathlib**. It's a lot easier to codify algebra in **Mathlib** than than for for analysis. M uh, so so that's that's interesting because for analysis a lot of the definitions around convergence, limits is sector becomes tricky and so I don't think there's a lot of like topology in **Mathlib** today um in terms of like differential topology, differential geometry kind of stuff so, you know, our system likely will not do very well on those on those domains because it doesn't even have definitions to build off on top of for the places where the um definitions are are in, we actually are doing quite okay in terms of distribution ution diver diversity, we have good performance, you know, so having solved open research questions and um number theory, commutative algebra, algebraic geometry, some discrete math that comes and probability.

</details>

**Brandon Anderson**: 所以你之前说过，在**Pudnam**考试中，2024年版本中，所有**AlphaProof**没有答对的问题。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So earlier you said that like with the **Pudnam exam** you the the 2024 version when all of the questions were that were not that **AlphaProof** did not get right.

</details>

**Carina Hong**: **IMO**国际。

<details>
<summary>Original English</summary>

**Carina Hong**: The **IMO** international.

</details>

**Brandon Anderson**: 是的，对于**IMO**，我所有答错的问题都在组合学中。这个特定领域是否存在弱点？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes, for the **IMO** all of the ones I got wrong were in cominatorics is there is Is there like a weakness there in that specific domain?

</details>

**Carina Hong**: 我会说，对于数学奥林匹克竞赛，人们认为组合学有点棘手。

<details>
<summary>Original English</summary>

**Carina Hong**: I would say so for for Olympia in math people are seeing commonars being a little bit more um tricky.

</details>

**Carina Hong**: 似乎步骤非常富有创造性。所以，我作为一个人类，当我有朋友非常擅长组合学时，我从来不认为自己是组合学的顶尖高手。我更擅长数论，但我认识一些人，他们是**IMO**金牌得主，满分**Pudnam**研究员，一路走来，当他们做组合学中的技巧时，我就会想：

<details>
<summary>Original English</summary>

**Carina Hong**: Uh seems like the steps are quite creative. So I for I'm a human and, you know, when I have friends who are really good at commentaryics, which I never consider myself really the the top of comarics. I'm kind of better at number theory, but I know some people who are just they're **IMO** gold perfect score put them fellow perfect score and like all the way and then when they do like tricks and comarics, I'm like,

</details>

**Carina Hong**: 我不知道你是怎么想到的，但是，你知道，在你给我那个构造之后，它实际上变得更容易追踪了。我认为一个基于**Lean**的系统在那些非常有创造性的地方会遇到困难，这就是为什么我们**Axiom**实际上也投资于一种叫做**数学发现**的东西。它还没有被使用，我们将在未来几周内发布一些重大新闻，基本上是开源整个**数学发现**的代码库。

<details>
<summary>Original English</summary>

**Carina Hong**: I don't know how you thought of that and but, you know, after you give me that construction actually becomes a lot more trackable. I think a **Lean** based system will struggle in those very creative um places, which is why we at **Axiom** actually also invest on something called **mathematical discovery**. It's not used and we have some major news in the coming weeks basically open sourcing entire code bases of **mathematical discovery** coming up.

</details>

**Brandon Anderson**: 你想告诉我们一些吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: You want to tell us a little bit?

</details>

### 数学发现工具的开源

**Carina Hong**: 是的，当然。所以，我们目前正在开源两个代码库。目标是，如果你是一名数学家或理论物理学家，并且你有一个想要解决的问题。例如，你想要找到一个非常复杂的图构造，那么我们会建议你遵循我们编写的非常详细的手册，该手册旨在供数学家运行我们的代码。它是一个帮助数学家进行**数学发现**的工具。**数学发现**的理念是，证明对于数学来说是不够的。事实上，在你开始证明某事之前，你不知道从哪里开始。所以你会尝试构造一些有趣的例子。这些通常可以是序列，对吧？如果你想理解一个序列的性质，你会写出前几项。这也可以是图。所以，如果你想弄清楚你正在寻找的图是否应该具有某种性质，那么你会从做一些更简单的图版本开始。现在，构造不能由**Lean**完成。所以我们相信AI可以用于**数学发现**，我们有该领域的OG之一，**Chart**，他是**Axiom**的技术人员，他之前曾做过**Pattern Boost**，并端到端地解决了30年前的猜想，通过找到一个反例来证明其不成立，还找到了130年前问题的解决方案，即**全局李雅普诺夫函数**，这是一种出现在**三体问题**中的数学对象。所以我们认为，**数学发现**工具应该向数学社区开放。所以我们正在为此开源整个代码库。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah, sure. U so, uh, we are currently uh having two code bases um being open sourced. So the goal is for if you're a mathematician or you're a theoretical physicist and you have a problem that you would like to solve. For example, you want to uh find a construction that is a very complicated graph construction, then we would suggest you follow the very detailed manual supposed intended for mathematicians to run the code that we write. Uh, it's a it's a tool for for mathematicians to make **mathematical discoveries**. **Mathematical discoveries** is this idea that, you know, proof is not enough for math. Uh, in fact, before you kind of start proving something, you don't know where you want to start. So you will try to construct some interesting examples. These can be usually say sequences right if you want to understand the property of a sequence you will write out a few of the first terms. This can also be graphs. So if you want to, you know, figure out what the graph that you're looking for um should I have say a certain property uh, then you will start by doing some simpler version of the graph. Now constructions cannot be done by **Lean**. So we believe in having AI for mass discovery and we have, you know, one of the OGs in that field **Chart** um member of technical staff at at **Axiom** and he previously have done **Pattern Boost** and end to end, you know, settle disproof a 30-year-old conjecture by finding a counter example um found the solution to 130 year old problem the **global Lyapunov function** that is a kind of mathematical object showing up in the **three body problem**. So we we are we are thinking that, you know, it's **mathematical discovery** tools should be open to the mass community. So we are open sourcing entire code bases for that.

</details>

**Brandon Anderson**: 所以发现意味着它提出了新的猜想，还是它？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So discovery meaning it gives it makes new conjectures or it.

</details>

**Carina Hong**: 是的，那是一个预猜想的步骤。哦，我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: That's a yeah, it's a preconuring step actually. Oh I see.

</details>

**Carina Hong**: 是的。所以你开始形成直觉，对吧？如果你是一个数学家，你的目标是解决一个非常困难的猜想，**Axiom Prover**不能直接为你解决。你可能想尝试提出一些引理或猜想，然后将其交给**Axiom Prover**。如果你是一个人类数学家，你会想从提出这个猜想开始。你不知道该去哪里。你想找到构造。现在，我们将开源的代码将帮助你，希望能显著帮助你。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So you you start to form intuitions right. If you're a mathematician and your goal is to solve a really hard hard conjecture x improver can't just solve it for you. Um, you might want to try to formulate some sort of lemas conjectures that you want to say then give to **Axiom Prover**. Um, if you're a human mathematician, you will start by wanting to formulate that conjecture. You don't know where to go. You want to find constructions. Now, uh, the code is that we're going to open source going to help you uh hopefully significantly.

</details>

### 形式化验证与理论局限

**Carina Hong**: 所以，可能有很多计算机科学家在听，其中一件事会立即浮现，尤其是在谈论形式化验证时，那就是**莱斯定理**、可判定性问题和不完备定理，以及关于计算复杂性和大型语言模型的一些论点。

<details>
<summary>Original English</summary>

**Carina Hong**: So, one thing that maybe there's a lot of computer scientists listening and one of the things that will immediately kind of come up in especially when you're talking about **formal verification** and so forth is **Rice's theorem** and decidability and incompleteness theorem and and maybe um some arguments about computational complexity and LLMs. So I I'm curious to hear.

</details>

**Brandon Anderson**: **莱斯定理**说你不能证明所有程序的非平凡属性，对吧？那么你们是如何在这个空间中导航的呢？显然形式化验证能够做一些事情。

<details>
<summary>Original English</summary>

**Brandon Anderson**: **Rice's theorem** says you cannot prove non-trivial things about programs for all programs, right? So how are you navigating this space? Obviously **formal verification**, you know, does is able to do some things.

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah.

</details>

**Carina Hong**: 是的，我认为很清楚，就像有理论结果告诉你，你不能形式化验证所有程序，对吧？但是我认为形式化验证大多数有用的程序是很好的，对吧？所以，我记得**MIT**有一个小纪录片，或者说不是纪录片，而是一个给被录取学生的广告，**MIT**的吉祥物**Tim**说了一句名言：“理论给了你什么？”这有点像它并没有阻止我们尽可能地推动它。所以我们未来的目标是，假设你正在进行编码，你想要验证一个非常复杂的任务的代码。所以，现在是前端网站，但未来我们可能想要验证更复杂的东西，整个分布式系统，即使那样，我们也希望能够说将其分解。可能有一个高层次的草图计划，这个我们可以做，其他人也可以做，但比如说，你让**Claude**帮你把它分解成10个部分，在某个时候它会决定调用**Axiom**，**Axiom**会给你一个你知道是经过形式化验证的计算机程序，或者它会说这对于我们来说仍然太难了。

<details>
<summary>Original English</summary>

**Carina Hong**: So yeah, I think like it's it's very clear that you just like there's theoretical result telling you you cannot formally verify all programs, right? But you you I think it it's good to formally verify majority of the useful programs, right? So, you know, like I remember uh there's this **MIT** uh like little like documentary or not a documentary like an advertisement for, you know, uh people who are admitted students and then there's this famous line by **Tim** the the beaver the mascot of **MIT** saying that what aory give you which is which is kind of like it doesn't stop us from trying to push it as much as possible. So the goal that we have for the future is suppose you are, you know, doing doing the the coding you want to v code a really complex task. So, you know, currently it's front end websites, but in the future we might want to vibe code much more complicated things whole distributed systems, even then we want to be able to say decompose it, there's maybe a highle kind of like sketch plan this we can make other people can make but say, you know, you have **Claude** give you like, you know, kind of break it down into 10 things and at one point it will decide to call **Axiom** and **Axiom** will give you a computer program that you know is formally verified or it will say this is still too hard for us.

</details>

**Brandon Anderson**: 所以你编写程序，把它交给**Axiom**，它可能会对它进行修改。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you you write the program, you give it to **Axiom**, it makes changes to it maybe.

</details>

**Carina Hong**: 所以我们谈论的是两种阶段。

<details>
<summary>Original English</summary>

**Carina Hong**: So so we're talking about kind of two um sort of phases.

</details>

**Carina Hong**: 我们有可能是验证伙伴。所以你已经有了一个计算机程序，你希望我们来验证它。事实上，**GPT**发现了一个未解决的**埃尔德什问题**的证明，我们的竞争对手**Harmonic**的**Aristotle**验证了它。但我们想做的是**验证生成**，对吧？我们可能想说，嘿，我们生成并提供给你的这个小组件，所有这些都是经过形式化验证的。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, it is possible that we are the verification partner. So you already have a computer program and you want us to verify it. In fact, like, you know, **GPT** found a proof to an unsolved **Erdos problem** and our competitor **Harmonic**, you know, **Aristotle** um, you know, verified it. But we we can do we want to do **verify generation**, right? We might want to say, hey, you know, this little component everything that we generate and provide for you um is is formally verified.

</details>

**Brandon Anderson**: 我明白了。所以，想法是你们同时生成，共同生成，这样我就可以想象这会融入到承诺或，抱歉，抱歉，然后一个，抱歉。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see. So, so the idea would be you you generate you co generate bo both and so that and I can imagine this fitting into um, you know, the idea of a promise or a sorry sorry and then a sorry.

</details>

**Carina Hong**: **Lean**的`sorry`。

<details>
<summary>Original English</summary>

**Carina Hong**: **Lean** sorry.

</details>

**Brandon Anderson**: 一个**Lean**的`sorry`，意思是它是一个未被证明的引理，但你暂时将其视为给定，直到你有时间去证明它，对吧？这是理解`sorry`的好方法吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: A **Lean** sorry meaning it's a lema that is unproven, but you're just taking it as given until you can take have the time to prove it right is that a good way to think about a sorry.

</details>

**Carina Hong**: 这是一个理解`sorry`的好方法，但不一定是在编码语境中。

<details>
<summary>Original English</summary>

**Carina Hong**: That is a good way to think about a sorry, but not necessarily in the coding context.

</details>

**Brandon Anderson**: 所以我可以想象你可以说，假设这个模块经过验证，那么这个模块就是正确的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: It's So I can imagine you're you can say assuming that this module is verified then this module is correct.

</details>

**Carina Hong**: 这样你就可以把问题分解得足够小，以便进行验证。

<details>
<summary>Original English</summary>

**Carina Hong**: And and so that that you can decompose a problem small enough that you can verify is this kind of.

</details>

**Carina Hong**: 所以假设我们想用代码控制流程。

<details>
<summary>Original English</summary>

**Carina Hong**: So so let's say we want to, you know, like web code control flows.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 对吧？那相当困难。你很可能会把它分解成多个步骤。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. That's quite hard. You will likely, you know, break that down into multiple steps.

</details>

**Brandon Anderson**: 然后它会继续将这些步骤分解成更细粒度的步骤。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And then it will continue to break down these steps into more fine grain steps.

</details>

**Carina Hong**: 在某个时候，你想要绝对正确的东西。

<details>
<summary>Original English</summary>

**Carina Hong**: And at one point you want something that is absolutely correct. Y

</details>

**Carina Hong**: 然后这也很可能在可及范围内。然后我们想要生成，我们想要生成一段计算机程序，其基础是一个保证，即也生成了证明，它告诉你你指定的这个程序员可以为你解决问题。所以，我们的愿景是，任何可以被定义的东西都可以被执行，任何可以被指定的东西都可以被证明。所以我的想法是，如果你有一个程序，一个程序乘以一个语句或问题，它映射到可验证性条件乘以一个证明。所以，当程序验证社区为你提供了可验证性条件时，我们正在努力招募一个非常强大的团队来帮助我们做到这一点。**Axiom Prover**将为你提供证明。

<details>
<summary>Original English</summary>

**Carina Hong**: And then this is also something that is likely within reach. Then we want to generate, you know, both uh, we want to generate a piece of computer program and underlying is a guarantee that there is also the uh proof that has been generated which tells you that the thing that you specify this, you know, programmer can solve for you. So, so, so the vision we have is anything that can be which anything is, you know, and it's a little bit marketing because because as you said theoretical bound but but mostly um, well almost surely hopefully um, anything that can be defined can be executed, anything that can be specified can be proven. So the way I think about it is if you have a uh program um times a a, you know, a program times a times a statement or problem, it maps to verifiability conditions times a proof. So while the programming ver program verification community has given you say the verifiability conditions and we're trying to kind of recruit a really strong team to help us do that. **Axiom Prover** is gonna give you the proof.

</details>

**Brandon Anderson**: 所以请帮我把程序映射到证明，因为我可以说，你知道，这个两行的**Lean**程序验证了，你知道，我声称它解决了的任何问题。我怎么知道它真的验证了我认为它验证的东西？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So just help me map from the program to the proof because like I could say, you know, this two-line **Lean** program verifies, you know, sort of like whatever whatever I claim it solves. How do I know that it actually verifies the thing that I think it.

</details>

**Carina Hong**: 验证了？是的。所以，例如，目前有一个叫做**CodeArena**的基准测试。它是一个代码验证基准测试，旨在对**Lean**友好。所以，每个问题都是一个编码问题，目标是生成代码和证明，这是两个不同的计算机程序。是的。然后目标是生成带有证明的代码。所以，你知道，这个代码应该解决这个问题，然后证明这个程序确实解决了这个问题。

<details>
<summary>Original English</summary>

**Carina Hong**: Verifies? Yeah. So so for example, there's this currently there's this benchmark called **CodeArena**. It's a uh code verification benchmark um that's supposed to be **Lean** friendly and so, you know, every problem is a coding problem and the goal is to generate there's a code part and there's a proof part two two different computer programs. Yeah. And then the goal is to generate code with proof. So, you know, the code that supposedly solves this problem and then the proof that this program indeed does solve the problem.

</details>

**Brandon Anderson**: 我明白了。那么人们在这个基准测试上的表现如何？我想稍微谈谈这个，因为它很有趣。它是由**伯克利**和**Meta**的研究人员在2025年推出的，他们发现他们评估的任何版本的**GPT**，一次通过率约为3.6%，迭代后约为22%。现在，形式化数学系统模型表现如何？**Copra**是一个系统，因为在一个系统中，你进行迭代和定义，所以一次通过率不太适用，但他们仍然评估了该系统的一次通过率，大约是11-12%。然后还有**DeepSea Prover**和**GoTo Prover**模型，也是11-12%。我认为我们的竞争对手去年发布了仅证明部分的96%。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see. Now now how do people do on this benchmark? I kind of want to like talk about this a little bit because it's interesting. It was um rolled out I think by um **Berkeley** and **Meta** researchers in 2025 and they found I think whatever version of **GPT** they evaluated does like pass one like 3.6% iterative something like 22%. Now, you know how does the formal mass systems models do um **Copra** which is a a system because in a system you iterate and define so pass one doesn't quite work but still they evaluated pass one of the system about like I think 11 12%. And then also **DeepSea Prover** and **GoTo Prover** model 11 12%. And I think our competitor has released last year on the only proof part 96%.

</details>

**Carina Hong**: 而我们最近，在没有修改**Pudnam**系统的情况下，我们看到了99%的成绩，在189个问题中我们解决了187个，只错了两个，是带有证明的代码。所以，如果你想训练一个能做带有证明的代码的东西，并且你想做强化学习，那实际上是相当烦人的，因为你看，如果你的证明是非形式化数学，那它就是混合的，非常烦人，因为那就像是混合目标函数。你的代码是**Python**之类的，你的证明是自然语言的数学证明，那么你的强化学习性能就不会很强。但是，如果你的证明是**Lean**，并且你有代码，你可以选择**Rust**，这是一种强类型语言。它更具转换性。所以你会获得更好的性能。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, and we actually recently with no modification to the **Pudnam** system, we saw a 99% out of the 189 problems, we solved 187, we missed only two um code with proof. So if you if you want to train something to do code with proof and you want to do reinforcement learning, it's actually quite annoying because look, it's it's mix if you want proof to be informal math, it's it's very annoying because then that's like just mix objective function um your code is something like **Python** your proof is say natural language mass proof um, you will not have very strong RL kind of performance right but if you have proof as **Lean** and you have, you know, code you can choose **Rust** which is a strongly typed language. It's more it's more conversion. So you're going to have much better performance.

</details>

**Brandon Anderson**: 我无法理解如何将它们联系起来。比如，我可以说这个证明解决了**费马定理**，但我不知道，比如，它只有两行**Lean**代码，显然它没有解决。那我怎么知道我写的程序与我生成的证明相匹配呢？

<details>
<summary>Original English</summary>

**Brandon Anderson**: I can't wrap my head around how do I tie so like I can say that this proof solves for ma theorem right but I don't know that like but it's two lines in **Lean** obviously it doesn't so how do I know that the program that I wrote matches the proof that I generated.

</details>

**Carina Hong**: 你基本上会查看编码问题，然后查看程序，然后你会尝试查看它是否满足可验证性条件。

<details>
<summary>Original English</summary>

**Carina Hong**: You will basically look at the coding problem and you look at the the program and then you um like try to see if it satisfies the verifiability conditions.

</details>

**Brandon Anderson**: 但我怎么知道呢，对吧？如果我读它。

<details>
<summary>Original English</summary>

**Brandon Anderson**: But like how do I know, right? Like if I read it,

</details>

**Brandon Anderson**: 对吧？

<details>
<summary>Original English</summary>

**Brandon Anderson**: right?

</details>

**Carina Hong**: 你知道，我可以直接目测，然后说，传统上数学家们就是这样做的，他们拿到论文，阅读它，然后说我同意这个证明解决了这个问题，然后另一个人说不，等等，它没有，你看这里，然后人们争论，最终达成共识，认为这个证明解决了这个问题。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, you know, like I can I can just like eyeball it and I can say and then like traditionally how mathematicians have done this is they they, you know, they take the paper and they read it and they say I agree that this proof solves the problem and then this other person says no wait it doesn't for, you know, like look at this and then people disagree and eventually there's consensus that that like this proof solves this problem. So like how do how are you.

</details>

**Brandon Anderson**: 但你一步一步地检查它，对吧？

<details>
<summary>Original English</summary>

**Brandon Anderson**: But you check it step by step. Right.

</details>

**Carina Hong**: 是的。没错。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Right. Right.

</details>

**Carina Hong**: 是的。是的。所以你基本上会查看可验证性条件，看看它是否真的满足。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. So you basically will look at the verifiability conditions and see if it does actually satisfy that.

</details>

**Brandon Anderson**: 所以假设我们正在看一段计算机程序。是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So so suppose suppose like we're looking at like, you know, a piece of computer program. Yeah.

</details>

**Carina Hong**: 对吧？然后它是否真的解决了编码问题。你对此会有一个判断。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. And then whether it does actually solve the coding problem. You will have a judgment about that. Right. Yeah.

</details>

**Brandon Anderson**: 所以你不会仅仅依赖测试，尽管那是一种方式。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you will not solely rely on testing even though that is a way. That's what.

</details>

**Brandon Anderson**: 所以有人会看证明，然后说：“是的，那确实解决了我们认为它应该解决的问题。”

<details>
<summary>Original English</summary>

**Brandon Anderson**: So somebody looks at the proof and says, "Yeah, that actually solves the problem that we think it's supposed to some."

</details>

**Carina Hong**: 但现在你基本上是在生成一个满足可验证性条件的形式化验证程序。

<details>
<summary>Original English</summary>

**Carina Hong**: But then but then now you're you're basically producing a, you know, formal verification program that satisfy the verifiability conditions.

</details>

**Brandon Anderson**: 关于这个。

<details>
<summary>Original English</summary>

**Brandon Anderson**: about this.

</details>

**Carina Hong**: 程序和这个语句。所以函数再次将你从程序和语句带到可验证性条件和证明。

<details>
<summary>Original English</summary>

**Carina Hong**: Program and this statement. So again the function is taking you from the program and the statement to verifiability conditions and proof.

</details>

**Brandon Anderson**: 好的。所以我明白了这在基准测试中是如何运作的。那么，如果我有一个飞行控制系统，它非常。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay. So I can see how this works in a benchmark. Then if I have let's say I have a a flight control system that is like very.

</details>

**Carina Hong**: 那么问题就变得非常令人恼火，你知道，这个规范。

<details>
<summary>Original English</summary>

**Carina Hong**: Then the the problem becomes very annoyingly uh, you know, this the like specification.

</details>

**Carina Hong**: 我认为这个词是，你知道，即使我们说成功，我们也会遇到规范问题。

<details>
<summary>Original English</summary>

**Carina Hong**: I think the word is going to, you know, even if we say successful like like anything that, you know, that we will have a specification problem.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 所以，就像银行会说，请给我一个真正安全的财务审计？抱歉。请为我证明财务审计，对吧？

<details>
<summary>Original English</summary>

**Carina Hong**: So like here comes a bank saying that like please do I have a really safe financial audit? Sorry. Like prove the financial audit for me, right?

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 就像。

<details>
<summary>Original English</summary>

**Carina Hong**: Like.

</details>

**Brandon Anderson**: 那是什么意思？我们无法指定。人类不擅长指定我们想要的一切。

<details>
<summary>Original English</summary>

**Brandon Anderson**: What does that mean? Like we we can't specify. Humans are bad at specifying everything that we want.

</details>

**Carina Hong**: 总是会有一些。

<details>
<summary>Original English</summary>

**Carina Hong**: There's always like some sort of.

</details>

**Brandon Anderson**: 说我们没有指定，如果未指定，就无法证明。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Saying that we are not specified and if it's not specified, it's not proven.

</details>

**Brandon Anderson**: 好的。那你们怎么解决这个问题？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay. So what do you do about that?

</details>

**Carina Hong**: 是的。所以我们还没有达到那个阶段。目前，我们的愿景是，任何可以被指定的东西都可以被证明。现在，显然有些人在这方面做得非常好，那也许就是非形式化推理者发挥作用的地方。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So we're not there yet. Okay. Currently uh, you know, like again the the the vision as of currently is anything that can be specified can be proven. Okay. Now obviously there are people have been really good at, you know, that's where maybe where that's informal kind of reasoner come in.

</details>

**Brandon Anderson**: 对，非形式化推理者可以，我想引用测试的文献。测试很棒，因为测试就像“嘿，你考虑过那个吗？”对吧？我想强调**Facebook**广告研究总监**Shou**关于基于突变的LLM单元测试生成的工作。你的想法是AI会说“嘿，你考虑过这个、这个、这个情况吗？”所以这有点像猜想。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Right the informal reasoner can and this is I want to kind of, you know, call the literature of testing like testing are great because testing is like, hey, have you thought about that right like like I want to highlight the work mutation based, you know, LM unit test generation by accident CTO **Shou** and he was a director of **Facebook** ad research like the way you kind of think about it is like the AI will be like, hey, have you thought about have you thought about this this this case like and so this is a little bit like conjecture.

</details>

**Brandon Anderson**: 所以猜想将有助于规范。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So the conjecture is going to help with the specification.

</details>

**Brandon Anderson**: 我明白了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see.

</details>

**Brandon Anderson**: 然后证明者进行证明。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And then the prover does the proof.

</details>

**Brandon Anderson**: 所以这是一个互动过程，也许是那个人，这样我们就能给出好的具体。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And so this is an interactive process maybe that the person so that when we're actually giving good specific.

</details>

**Carina Hong**: 我认为这是编码的未来，是的。我认为这是编码的未来，我认为这就是，你知道，即使我们假设一切都可以形式化验证，研究自动任务生成仍然很有趣，因为它基本上为你提供了规范建议。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: I think this is the future of coding, yes, I think this is the future of coding and I think this is where, you know, this is where I think even if we are suppose like given the assumption that everything can be formally verified, you know, like studying sort of like, you know, automatic task generation is still interesting because it it is basically giving you the specification proposal. Yeah.

</details>

**Brandon Anderson**: 没错。然后另一件事是，让我们谈谈所有的形式化，也就是定义它的能力。它有点像将一些更非形式化的东西转化为更形式化的东西，或者说是形式化。所以假设我有一个为**ICPC**编写的编码问题，这个问题是用英语写的，比如Alice和Bob等等。现在我想把它转化为一个形式化的语句，一个形式化的规范。我现在如何进行自动形式化步骤？这将是为什么呢？因为我还没有解决问题。所以我没有任何信号。我没有任何基础。测试用例的输入输出对将作为我的基础。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Right. And then another thing is let's talk about all the formalization, right, which is the ability to to define it. It is kind of conver uh converting something that is more more informal uh into a into something that is more formal or the formalization. Um, so suppose I have a coding problem that is written for **ICPC** and this problem is written in English like Alice and Bob blah blah blah. Okay. Now I want to convert that into a formal statement like a formal spec. How do I do the auto formalization step right now? This is going to be how because I have not solved the problem yet. So I don't have any signal. I don't have any grounding. The test cases input output pair is going to ground my formost.

</details>

**Brandon Anderson**: 所以我知道我必须知道我将给出这个输入。我将给出这个输出。它必须具有这些特征。所以，我编写测试用例，我编写一个，那么在**Lean**中是否有等价物呢？在那里，规范，你只是知道你期望的结果，这样，你知道，结果的陈述，但证明是完全未知的，这很烦人，因为很多时候它是证明。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So I know I have to know I'm going to give this input. I'm going to give this output. It has to have these characteristics. And so and so I write test cases and I write a so is there equivalent in **Lean** of this right where the specification where you just know the sort of like outcomes that you are expecting so that like you the statement of the the result and then the but the proof is completely un quite annoying because it's like a lot of the times it's proof.

</details>

**Brandon Anderson**: 所以你实际上没有数字答案来作为基础。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you don't actually have the numerical answers to ground it.

</details>

**Carina Hong**: 好的。所以自动形式化是一件相当困难的事情。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. So autoformmization is a quite quite a hard thing to do.

</details>

**Carina Hong**: 因为你知道通常发生的情况是，你无法，你只是很难将一个语句的自动形式化作为基础。你显然可以将一个证明的自动形式化作为基础。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, because you know what's generally happened is um, you can't you just it's hard to ground the auto formalization of a statement. You can obviously ground the automization of a proof.

</details>

**Brandon Anderson**: 但因为你那时可以直接运行它。

<details>
<summary>Original English</summary>

**Brandon Anderson**: But because you can then just run it.

</details>

**Carina Hong**: 但你需要人类来目测它。

<details>
<summary>Original English</summary>

**Carina Hong**: But you need human to eyeball it.

</details>

**Brandon Anderson**: 一个形式化的、你知道的、相当规模的程序的**Lean**证明有多大？我的意思是，它们是随着程序的大小而增长，还是超线性增长？是的，目前实际上，你知道，每写一行代码，可能就有20行证明。

<details>
<summary>Original English</summary>

**Brandon Anderson**: How big is a **Lean** proof of like a formalized, you know, of a formalized program of significant size? I mean, do they grow with the size of the program or do they grow super linearly? Yeah, currently actually, you know, for each line of code written there could be like 20 lines of proof.

</details>

**Brandon Anderson**: 好的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay,

</details>

**Carina Hong**: 看起来不太好。

<details>
<summary>Original English</summary>

**Carina Hong**: It's not looking that great.

</details>

**Brandon Anderson**: 但那是一种线性关系吗？还是随着程序的复杂性增加，它也会以某种方式增长？

<details>
<summary>Original English</summary>

**Brandon Anderson**: But but is that like a linear relationship or is it as the complexity of the program gets greater then it like it, you know, sort of also grows so that it's.

</details>

**Carina Hong**: 我对这个扩展定律没有很好的答案。

<details>
<summary>Original English</summary>

**Carina Hong**: A good I don't have a good answer to the scaling law of that.

</details>

**Brandon Anderson**: 好的。是的。因为我知道那在形式化验证中是一个问题，对吧？你需要有这些非常非常长的证明，即使是简单的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay. Yeah. Because I know that that's a problem in **formal verification**, right? Where you have these huge pro like you have to have these very very long proofs for even simple.

</details>

**Carina Hong**: 是的。那么，当你们开始处理更大的问题时，你们会遇到大型语言模型能力的局限性吗？

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So then then do are you going to run into sort of like limitations in in the capabilities of LLMs when you start to get to large larger um.

</details>

**Carina Hong**: 我们从根本上相信我们正在构建一个推理引擎。

<details>
<summary>Original English</summary>

**Carina Hong**: What what we believe fundamentally is we are building a reasoning engine.

</details>

**Brandon Anderson**: 嗯。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Mhm.

</details>

**Carina Hong**: 我们已经看到一个证明器处理了非常大的证明树。

<details>
<summary>Original English</summary>

**Carina Hong**: And we have seen a prover deal with really huge trees that are like, you know, tree of a proof.

</details>

**Carina Hong**: 好的。我们已经看到它从40个节点扩展到4000个节点。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. Uh, we have seen it scale from 40 notes to 4,000 notes.

</details>

**Brandon Anderson**: 等等，抱歉。**Axiom Prover**是大型语言模型吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So wait, sorry. Actually **Axiom Prover** is the is the LLM.

</details>

**Carina Hong**: **Axiom Prover**是一个由我们进行后训练的多个模型组成的集成系统。

<details>
<summary>Original English</summary>

**Carina Hong**: **Axiom Prover** is a ensemble system of multiple models that we do post training.

</details>

**Brandon Anderson**: 我明白了。好的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see. Okay.

</details>

**Carina Hong**: 而且它显然也包括我们已经开源的**Axel**工具。抱歉。

<details>
<summary>Original English</summary>

**Carina Hong**: And also it also includes obviously the tools that **Axel** that we have um open released. Sorry.

</details>

**Brandon Anderson**: 是的。换句话说，是的。所以我们已经看到它能够处理越来越复杂的任务。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. In other words, yeah. So so we have seen it being able to deal with more and more complex task.

</details>

**Brandon Anderson**: 我明白了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see.

</details>

**Carina Hong**: 我们不认为它有部分限制。你可以问，它在预训练的基础模型上是否会在某个点受到限制？

<details>
<summary>Original English</summary>

**Carina Hong**: We don't think it's partially bound. You could ask, you know, is it bounded at one point on the pre-trained base model?

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah,

</details>

**Carina Hong**: 我认为这是一个好问题。我认为，你知道，中期训练可能非常有趣，因为它确实，你知道，很多能力提升确实来自那个部分，对吧？如果你可以争辩说，即使你尝试强化学习一些不太有才华的人，那个人表现可能远不如一个未经后训练的**拉马努金**。你可以争辩说，这是非常非常悲哀的现实，但我们可能会在某个时候考虑这样做。

<details>
<summary>Original English</summary>

**Carina Hong**: I think that's a good question. I think, you know, mid-training could be very interesting because it does actually, you know, a lot of the sort of capability gain does come from that part, right? If you could argue that even if you uh try to reinforcement learn some uh person who is not very talented uh that person might behave you be be perform a lot less well than an un unpost trained **Raman** you can you can you can argue that very very sad reality of things but um so at one point we might consider doing doing that.

</details>

**Carina Hong**: 但我们认为还有很多可以推动的地方。

<details>
<summary>Original English</summary>

**Carina Hong**: But we think there's so much to push.

</details>

**Brandon Anderson**: 所以你只是觉得现在有太多的开销，或者说有太多的空间可以发展，以至于你目前还没有遇到理论上的限制。我只是想知道，因为你知道，最近有一些关于大型语言模型能够从根本上解决的问题的计算复杂性的研究结果，我认为它们并不是一个问题。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you just feel like there's so much overhead right now or so so much um space taste to glow that that you're not running into theoretical constraints at this point. I I just wonder because, you know, there's been recent results in the computational complexity of the problems that LLMs can solve fundamentally and I don't think that they're really a concern for.

</details>

**Brandon Anderson**: 你知道，当我用**Claude Code**编写代码时，但我可以想象在这种系统中，问题变得足够大，以至于你有数以亿计行的**Lean**代码，你无法将它们全部放入上下文窗口，所以你必须对此保持聪明，然后你必须进行总结，然后你不断总结，很快就会有点迷失方向，而且看起来，对于一个非常大的系统，你可能会遇到这个问题。

<details>
<summary>Original English</summary>

**Brandon Anderson**: You know, when I'm writing code with **Claude Code**, but I can imagine problems becoming big enough in a system like this where you have a gazillion lines of **Lean** you can't get them get them into the context window so you have to like be smart about that and then you have to summarize and then you're summarizing and summarizing and pretty soon are like kind of losing track of what's going on and it just seems like with a large very large system like that you might run into.

</details>

**Carina Hong**: 是的，我认为这很有趣。这总是一个丰富的问题。所以很简单，你只要继续。**数学发现**的复兴已经到来，**Axiom Prover**确实尝试证明一切，你最终会得到数万行的**Lean**证明。所以首先，自动非形式化比自动形式化容易得多，减去没有基础的问题，对吧？你知道，每个模型都见过大量的文本和大量的**Lean**。所以，你总是可以，你知道，将**Lean**转换回非形式化，然后就出现了问题，你如何知道你是否正确？你可以依赖循环一致性。所以，你再次形式化，然后证明程序等价之类的。所以，这就是。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think this is this is interesting. It's always a problem of abundance. So simple you just like keep really the the **mathematical discovery** renaissance has come **Axiom Prover** does try to prove everything, you end up with like tens of thousand lines of **Lean** proof. So first of all, it's auto informalization is a lot easier than auto formalization minus a problem of no grounding right. You know, every every model has seen a lot of text and a lot of **Lean**. So, you can always, you know, convert that **Lean** back into back into informal and then there's the problem of well, how do you know if you're correct or not? You can rely on cyclic like consistency. So, you then formalize again and like prove like program equivalent something like that. So, that's.

</details>

**Brandon Anderson**: 哦，所以你先非形式化，然后形式化，你可以用它来确保你仍然使用。是的。是的。虽然非形式化，你知道，显然不是一个很难的问题，所以你总是可以这样做。所以对于我们输出的很多**Lean**代码，我们可以有一个非形式化的摘要器，对于大块的**Lean**代码，它实际上做得很好。所以，你知道，那是一回事。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Oh, so you you like informalize and then formalize you can use it to make sure that you still use Yeah. Yeah. like and although informalization is, you know, obviously less hard a problem so you can always do that. So for a lot of the, you know, the the **Lean** code that we output, we can have an informal summarizer of of like big chunks of **Lean** is actually doing okay so, you know, that's that's a that's a thing.

</details>

### 人类理解与AI生成证明

**Carina Hong**: 还有一个问题，我认为这很有趣，我认为去年在温哥华**ICML**的AI for Math研讨会上有一个小组讨论，有**Leo Deora**、**Java Jere**、**Jeremy Aigod**和CTO **Shoubo**在场，他们讨论的是，人类或数学家在某个时候是否会停止尝试理解正在发生的事情？因为。

<details>
<summary>Original English</summary>

**Carina Hong**: And there's have another question of like which I think is very interesting is I think there's a panel at um **ICML** Vancouver last year um at AI for mass workshop there's like **Leo Deora** and **Java Jere** **Jeremy Aigod** and um **Shoubo** and CTO was there and they were talking about like will will humans or mathematicians at some point stop trying to understand what's going on there right because like.

</details>

**Carina Hong**: 假设你是一个非常有抱负的数学家，你想要证明你的假设，然后砰，这里有一个**Lean**证明，它实际上是正确的，它就是，你知道，一百万行的问题。是的，这难道不是对社区的一个巨大负面影响吗？因为我的意思是，通常当有人提出了一个大的证明时，它通常是一个过程，我正要说到那里，对吧？就像，那个负面结果会发生吗？这是小组讨论的问题，它完全是假设性的，没有人，没有人的模型系统可以证明我的假设，对吧？所以免责声明，请不要剪掉那部分，只是单独的。但是，你知道，人们仍然会尝试理解正在发生的事情，我认为答案通常总是肯定的。我认为好奇心和理解正在发生的事情的愿望，无论是数学上还是其他领域。这是一种基本的人类需求，我认为这就像，我认为在**验证超级智能**时代的一剂乐观主义是，即使所有的输出都将以更快、指数级增长的量产生，与人类可能消耗的量相比，他们仍然会尝试消耗它，他们仍然会尝试消耗他们认为重要的那些。所以，基本上，注意力是瓶颈，如果注意力是瓶颈，那么真正重要的是直觉和品味，你知道，哪个陈述可能值得人类消耗，也可能在有限的计算机资源中值得消耗，值得计算资源的投入，那就是人类数学家的品味将永远引导我们，我认为这非常美妙。

<details>
<summary>Original English</summary>

**Carina Hong**: Suppose you're a really ambitious mathematician, you're like I want to proof read my hypothesis and bang here's a **Lean** proof and like it's actually correct and it's just like, you know, problem 1 million lines. Um, yeah, isn't that like a big negative for the community because I mean usually when someone comes up with a big proof of something um often times it process I was about to get there right it's like, well, will will that negative outcome happen was a question the panel was discussing it's completely hypothetical no one's no one's like, you know, model system can can prove my hypothesis right so the disclaimer please please don't cut that part just stand alone um, but like, you know, um, well people still trying to try to understand what's going on and I I think the answer is usually is is always yes. I think curiosity and the the desire to understand what is going on, you know, um mathematically or in other domains as well. It's a basic human need and I think that is like, I think a dose of optimism in an era of I think **verified super intelligence** suppose we get there is that even even if all the outputs are going to be produced and at a much, you know, faster pace and much more exponential volume compared to what humans could possibly consume, they're still going to try to consume it and they're still going to try to consume the ones that they deem important. So then basically attention is the bottleneck and if attention is a bottleneck then really intuition and taste uh, you know, of which statement is probably worth worth the consumption of human and also maybe in a finite computer resource worth worth the consumption worth the the sort of spending of compute resources that's where human mathematicians taste will always guide us and I think that's incredibly beautiful.

</details>

**Brandon Anderson**: 内部获取结果是否值得？所以你可以用一种方式证明，然后尝试让你的系统通过许多不同的路径来获得，或者说概念上正交的证明，这样你就能得到一组多样化的、关于同一事物的不同推理方式，因为你知道，我认为如果你给它一个问题，它说“哦，好吧，这是一种蛮力自然的做法，也许有些人会这样做。”然后，有一种更短、更优雅的做法。所以你们有没有想过训练你们的模型在某些方面变得优雅？是的，在某个时候我们会达到那里，因为你知道，我认为这个猜想可能取决于我们所说的品味。优雅对我来说感觉像是一个对齐问题，你知道，谁来决定什么是优雅的？人类来决定什么是优雅的，对吧？这就是人类的特点。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Is it worth like internally taking like results? So you can prove one way and then trying to send your system at many different routes to get like or like orthogonal conceptually orthogonal proofs and so you kind of get a diverse set of different ways of you reasoning about the same thing because, you know, I think it could be very valuable if you give it a problem to say, oh, well, like here's kind of the brute force natural way that like maybe some humans would do it. Um, and then the uh there's like a really much shorter elegant way of doing it. So have you essentially thought about training your models to be elegant in some ways? Yeah, at one point we're going to get to there because, you know, I think the conjecture uh will probably depend on what what, you know, will probably depend on what we mean by taste elegance feels like an alignment problem to me, you know, like, you know, who who gets to say what is elegant? Humans get to say what is elegant, right? That's what makes human right.

</details>

**Brandon Anderson**: 有些事情是关于努力工作的，对吧？你努力工作的东西就是你擅长的东西。

<details>
<summary>Original English</summary>

**Brandon Anderson**: There's something about hard work right that what what you work on hard is what you're going to be good at.

</details>

**Carina Hong**: 是的，是的，我们将会遇到这个问题，我认为在很多领域都会如此，对吧？不仅仅是数学。比如，你如何成为一个拥有真正良好高层次理解的资深程序员？嗯，我猜是全栈理解，高层次和低层次。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, yeah, and we're going to have a problem about that, I think like pretty much in a lot of the domains as well, right? Not just math. Like how do you be that senior um programmer with, you know, really good high level understanding? Well, I guess full stack understanding high level and low level.

</details>

**Brandon Anderson**: 如果你没有经过一年的训练。

<details>
<summary>Original English</summary>

**Brandon Anderson**: If you haven't spent the year of training.

</details>

**Carina Hong**: 我的意思是，我会争辩说你不需要，这很哲学，但你知道，我不需要擅长汇编语言编程，对吧？没有多少人擅长那个。少数人擅长是因为这对他们的工作很重要。

<details>
<summary>Original English</summary>

**Carina Hong**: I mean, I would argue that you don't this is very philosophical, but like, you know, I I don't need to be good at assembly language programming right like no not many people are good at that. A few people are because it's important for their job.

</details>

**Brandon Anderson**: 这不是经验，而是好奇心。

<details>
<summary>Original English</summary>

**Brandon Anderson**: It's not experience but curiosity.

</details>

**Carina Hong**: 是的。所以，但这对我来说感觉有点不同，因为不擅长证明事情，例如，对吧？那似乎是一个根本性的差距，也许如果我不这样做，我的思维方式就不会以同样的方式发展。而如果我只是不擅长汇编语言编程，但我擅长更高级别的编程。所以也许那不重要。我认为那可能是因为教育系统、流程运作方式，如果你没有表现出早期的才华迹象，你有时就不会经历预训练的过程。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So, but but it feels to me a little different because not being good at like proving things for example, right? That seems like a fundamental gap in like that maybe my mind doesn't develop in the same way if I am not doing that. Whereas if I'm just not good at assembly language program well, but I'm good at like higher level programming. So maybe that doesn't matter. I think that's probably because how the maybe how the education system the pipeline works which is that if you do not show early signs of brilliance, you don't sometimes go through the process of pre-training.

</details>

**Brandon Anderson**: 在数学中。

<details>
<summary>Original English</summary>

**Brandon Anderson**: in math.

</details>

**Carina Hong**: 是的。是的。对吧？所以你也许可以争辩说，你不需要，你知道，学习所有东西来培养品味，但你需要达到一个门槛。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. Right. Like so so that maybe you can argue that you don't need to say, you know, learn everything to develop a sense of taste but there's like a threshold you kind of need to meet.

</details>

**Carina Hong**: 是的。所以，例如，你可能需要能够编码，即使你不需要理解汇编语言，那件事可能会转移我的直觉，或者，你知道，我的直觉可能会从我试图追求的奥林匹克竞赛中转移，而漫画的转移更直接。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So for example, you probably need to be able to code even if you don't need to understand assembly language and that thing might transfer my intuition or, you know, my my intuition might transfer from the Olymp I tried to pursue and comics transfer is more direct.

</details>

**Carina Hong**: 嗯，它非常相似，数论可能更进一步，但仍然可以。然后当它变得与奥林匹克数学的转移非常不同时，转移是否那么强？但有点像，你知道，你需要勤奋，就像你说的，对吧？你需要勤奋地经历一定量的训练。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, it's very similar and number theory could be further but still okay and then when it gets to like something that's a lot more different than Olympian mass transfer is that strong but kind of like, you know, you need to diligent as you said right like you need to diligently go through some amount of training.

</details>

**Carina Hong**: 如果人们过度依赖强大的AI，那就不会发生。

<details>
<summary>Original English</summary>

**Carina Hong**: And if people over rely on strong AI and that doesn't happen.

</details>

### Axiom Math的商业愿景

**Brandon Anderson**: 我想换个话题。你提到了软件验证。你们将在哪些领域赚钱，如何赚到足够的钱来证明这个估值是合理的？顺便恭喜你们。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I want to switch gears you mentioned uh software verification what are the domains how are you going to make uh enough money to justify the valuation that like and congratulations by the way.

</details>

**Carina Hong**: 谢谢。

<details>
<summary>Original English</summary>

**Carina Hong**: Thank you.

</details>

**Brandon Anderson**: 那么，你们向投资者展示的愿景是什么？为什么这真的能赚大钱？

<details>
<summary>Original English</summary>

**Brandon Anderson**: How so what what's the give us the the high level summary of like what is the what is the vision that you show you put in front of investors about why does this actually make a lot of money?

</details>

**Carina Hong**: 是的。首先，这一轮融资有点先发制人。所以，我认为很多投资者对**Axiom**非常感兴趣。就我们所相信的而言，我们相信编码的未来将受到验证能力的某种限制。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So um, first of all, this round is kind of preemptive. So it's uh, I think a lot of the investors have pretty high interest about about **Axiom**. Um, in terms of kind of what we believe in, we believe the future of coding is going to be somewhat constrained by verification capability.

</details>

**Carina Hong**: 我们相信解决形式化数学是一个非常自然的起点，然后通过扩展，你可以提高硬件和软件的验证能力。例如，对于硬件来说，那将是革命性的。我的意思是，据我们所知，对于一个大部分经过验证的GPU，没有部分功劳。

<details>
<summary>Original English</summary>

**Carina Hong**: And we believe in solving formal mass is a very natural starting point and then by extension you can increase the verification capability across hardware and software and for hardware for example, that's quite revolutionary. I mean that is there is no as we know there's no partial credit for a mostly verified GPU.

</details>

**Brandon Anderson**: 不。

<details>
<summary>Original English</summary>

**Brandon Anderson**: No.

</details>

**Carina Hong**: 它是全有或全无。

<details>
<summary>Original English</summary>

**Carina Hong**: Uh it's all or nothing.

</details>

**Brandon Anderson**: 它是全有或全无。

<details>
<summary>Original English</summary>

**Brandon Hong**: It is all or nothing.

</details>

**Carina Hong**: 而且你确实需要一个完美的证明器。我想强调这一点，假设我是一个喜欢解决数学问题的人。我认为有很多**Twitter**用户喜欢像**Pokemon**一样狩猎**埃尔德什问题**，然后我只是尝试，你知道，使用一个非确定性的OM，比如**GPT**，来尝试获得完整的证明。

<details>
<summary>Original English</summary>

**Carina Hong**: It is all or nothing and you do and you do need a perfect prover like I want to stretch that which stress this point which is that suppose I am a, you know, I am someone who loves solving maths. I think there are a lot of **Twitter** users who enjoy **Pokemon** like hunting um **Erdos problems** and then I just try to um, you know, use a non-deterministic OM uh like **GBT** say to try to get the full proof for that.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 现在我可以做很多次，我可能会成功，也可能不会，我可能不会在意我是否真的成功。这对于硬件验证来说绝对行不通。所以对于那些我称之为需要**硬核验证**的领域，这是一个痛点。这是一个当前的痛点，有数百名人类和数千个许可证被专门用于解决一个局部网格问题验证。

<details>
<summary>Original English</summary>

**Carina Hong**: Now I can do that many many times and I might succeed and I might not and I might not have a problem with whether I actually succeed or not. This absolutely does not work for hardware verification. So for those kind of domains which I call like **hardcore verification** needed, it is a painpoint. It is a current painpoint there there there are hundreds of humans and thousands of licenses being dedicated to solve one local grid problem verification.

</details>

**Brandon Anderson**: 顺便说一句，我的理解是，在ASIC项目中，从设计到验证的行业标准是1比3，1比。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Just as an aside, the my understanding is that the industry standard for design to verification in a asich as project is like 1 to three, 1 to.

</details>

**Carina Hong**: 4比3到4。没错。无论是团队规模还是持续时间。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Four to three to four. Correct. Both in say Tim size and then duration. Yeah.

</details>

**Brandon Anderson**: 没错。所以如果你乘以那个，是的，平方，然后我想，所以那是一个，我会说，你知道，它是一个必须覆盖的领域。现在对于软件验证，它很有趣，对吧？因为，你知道，正如我们可能都意识到的，我的侄子用代码编写了一个可爱的网站，绝对没有必要形式化验证那段代码，你为什么要这样做呢？现在我听到了**Kats**讲的一个故事，他是《**纽约时报**》的记者，他告诉我的故事是这样的：

<details>
<summary>Original English</summary>

**Brandon Anderson**: Right. So if you multiply that uh yeah square and then I think so so that's that's a I would say like, you know, it's a it's a must cover. And now for software verification, it is it is interesting, right? Because, you know, as probably we all realize like my nephew vibe codes a lovable website, there is absolutely no need to formally verify that piece of code like why would you now I heard of a story from **Kats** actually that **New York Times** reporter who um told me the story which is like.

</details>

**Carina Hong**: 然而，如果你想想代理时代，我的**Open Claude**可能会做各种各样的事情，也可能会做一些坏事。比如，我的**Open Claude**可能会决定给我的教授打上一些不好的标签，对吧？你可以说，那也许是形式化验证的问题吗？可能仍然不是，对吧？你可以改变行动空间的一些东西，使其更受限制。所以你不需要依赖形式化验证。所以你可能有很多案例，但你可以想想，也许一个处理大量监管事务的企业，使用代理，他们可能想做一些事情，那是他们的选择，但我会争辩说，验证能力的提高，无论是延迟还是准确性，所有这些东西，整体性能将决定人们是否依赖形式化验证。

<details>
<summary>Original English</summary>

**Carina Hong**: However, if you think about like, you know, in the time of agents like my **Open Claude** can probably do all sorts of things and probably can do some bad things. Uh, like my **Open Claude** can decide to like tag something bad to my professor, right? Like and and and you can say that perhaps is that a problem of **formal verification**? Probably still not, right? You can change something about the action space and make it more limited. So you don't you don't need to rely on for verification. So you can have a lot of cases, but you can think about, you know, maybe an enterprise that is dealing with a lot of regulatory kind of stuff using agents, they might want to do something like it it's their choice, but I will argue that the improvement of verification capability both in latency, you know, and in accuracy, all these stuff the performance holistically is going to determine whether people rely on **formal verification** or not.

</details>

**Brandon Anderson**: 当然。所以从某种意义上说，我们希望把它做得如此出色，以至于我们基本上可以把它变成一个选择。那么，投资者为什么认为你们能做到这一点呢？因为我的意思是，人们在验证方面已经工作了很长时间，我认为每个人都同意这是一个重要问题，而且我认为，如果我能为我编写的每个程序都提供一个验证证明，比如“嘿，**Claude**，也给我证明”，然后它就生成了，哦，是的，我觉得很好。我绝对会这样做。那么，在你们看来，投资者看到了什么，说服他们“好吧，就是现在，我要投入2亿美元”之类的？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Sure. So in a way we want to make it so good that basically we can make that a choice. So, so why did the investors think that you could do this, right? Because I mean people have been working on verification for so long and I think everyone agrees it's an important problem and it and I think certainly if I can just have a verification proof for every program that I write like, hey **Claude** like give me the proof also and then it just produces it and oh yep looks good to me. I would absolutely do that. But so why is it what was it that the investors saw in your opinion that persuaded them that okay this is the moment I'm gonna put in my 200 million or whatever?

</details>

**Carina Hong**: 我认为，当谈到信念时，你要么拥有它，要么没有。所以你要么和我们一起梦想，要么不梦想，这没关系，因为当我们实现梦想时，公司将价值100亿美元。

<details>
<summary>Original English</summary>

**Carina Hong**: I think um when it comes to faith, you either have it or you don't. So you either dream the dream with us or you don't and that's okay because when we realize the dream, the company is going to be worth 10 billion.

</details>

**Carina Hong**: 是的。所以，我认为这就是我的感受，我们相信验证是**超级智能**的关键部分。我们版本的**超级智能**是绝对经过验证的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So I think that's kind of the the feeling that I have which is that we believe verification is the critical critical part to super intelligence. Our version of super intelligence is absolutely verified.

</details>

**Carina Hong**: 我们不认为有任何其他可能的未来。我们不相信。

<details>
<summary>Original English</summary>

**Carina Hong**: We don't think there's any other possible future. We do not believe that.

</details>

**Carina Hong**: 我要郑重声明，我们不相信一个非形式化的数学系统会是数学通用人工智能（AGI）的解决方案。

<details>
<summary>Original English</summary>

**Carina Hong**: I'm going to say on the record we do not believe that an informal mass system is going to be the mass AGI solution.

</details>

**Brandon Anderson**: 为什么不呢？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Why not?

</details>

**Carina Hong**: 我们就是不相信。

<details>
<summary>Original English</summary>

**Carina Hong**: We just don't believe that.

</details>

**Brandon Anderson**: 我的意思是，反驳的论点是，哦，你知道，我们只是做了很多好的强化学习，而且，你知道，我们已经看到**GPT**解决了，你知道，一些问题等等。那么你为什么认为它会耗尽能量呢？

<details>
<summary>Original English</summary>

**Brandon Anderson**: I mean, the counterargument is, oh, you know, like we just do a lot of good RL and, you know, we've seen uh **GPT**, you know, solving, you know, I think some problem and like whatever. So why do you think that that runs out of gas?

</details>

**Carina Hong**: 是的。所以你可以说，如果你是一个前沿数学家，你拥有无限资源，那么从定义上讲就没有耗尽能量的问题，对吧？如果你认为无限意味着没有耗尽能量，我认为它不会扩展到**超级智能**。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So you can say that if you are a frontier math and you have like so sorry frontier lab and you have like infinite resources, why does there is by definition no running out of gas right if you think like infinite means like there's no running out of gas I don't think it's going to scale to super intelligence.

</details>

**Brandon Anderson**: 所以你认为你会耗尽，基本上是耗尽资金，或者耗尽电力。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you think that you run out like you run out of money basically or run out of power.

</details>

**Carina Hong**: 当然，作为一家初创公司，我们首先不能那样做。作为一家初创公司，我们首先不能那样做。

<details>
<summary>Original English</summary>

**Carina Hong**: Sure so we as a startup first of all cannot do that we first of all as a startup cannot do that.

</details>

**Carina Hong**: 但我们普遍认为，形式化数学，然后通过将数学证明转化为程序，转化为代码，会给我们带来更好的性能。所以，这只是你的样本效率论点等等，你只是，也许你只是无法，你无法充分弯曲曲线，如果你不使用形式化。问题是，非形式化的东西对我们来说也是可用的，如果你真的喜欢，你可以同时拥有非形式化和形式化系统，那将会非常强大。

<details>
<summary>Original English</summary>

**Carina Hong**: But we generally think that formal mass then by sort of converting mass proofs to programs to code give us much better performance. So, so it's just it's your sample efficiency argument and so forth that you just and maybe you just can't that that you can't bend the curb enough if you don't use formal. The thing is the the thing is the informal stuff is also available to us in a way if you really like you can have a both informal and formal system and that is going to be.

</details>

**Brandon Anderson**: 我明白了，我明白了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see I see.

</details>

**Carina Hong**: 非常强大。我有点怀疑，你知道，我们是否能仅仅通过非形式化方法扩展到数学通用人工智能（AGI），因为你将不断拥有大型语言模型（LLM）判断解决方案，或者你有人类专家评分。而人类专家无法很好地扩展。然后，如果你真的争辩无限，那么当然，你也有无限的资金，你可以支付无限。真的有无限数量的人能够理解和证明，比如说，**朗兰兹纲领**中的一个非平凡结果吗？我认为，你知道，祝你好运找到那些人。事实上，我认为前沿数学之所以能够走到一起，是因为他们无法通过他们的专家池组建一个基准测试，所以他们不得不与**Epoch**合作来完成，对吧？我认为这就是我担心人类部分的原因。所以他们有LLM裁判，然后现在是随机裁判。问题是，有些事情是无法实现的，而有些事情是极其昂贵的，而且极其昂贵地实现它们最终会混淆在一起。

<details>
<summary>Original English</summary>

**Carina Hong**: Very strong the thing that I kind of like I think my my suspicion about like, you know, whether we can scale to mass AGI just by the informal approach is you're going to keep having, you know, the LLMs judges solution or you have human experts who grade And it's just human experts like doesn't scale that well. And then if you really argue infinite infinity then sure then you also have infinite money and you can pay infinite there there's so many is there really infinite number of people who can understand and prove at say like about like, you know, a result a nonual result in **Langland's program** I think, you know, good luck finding those people and in fact, I think how frontier maths came to came came together is because they couldn't assemble a a a benchmark by their expert pool so they have to, you know, collaborate with **Epoch** to do it right and and I think that's kind of what what I worry about about qu having the human part. So they have LLMs judges and then now stocastic judging. The problem is like whether something is impossible to achieve versus something is incredibly expensive and like really incredibly expensive and incredibly expensive to achieve get kind of like mixed in the end.

</details>

**Brandon Anderson**: 然后当然，投资者总是想知道为什么是你们，对吧？所以我读了一些关于你们背景的资料，我认为如果我们不听听你们的个人故事，那将是对听众的不敬。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And then of course investors always want to know why you, right? So I've read a little bit about your background and I think it we would do a disservice to the audience if we didn't hear a little bit just about your personal story.

</details>

**Carina Hong**: 我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: I see.

</details>

**Brandon Anderson**: 你想谈谈你做过的一些非常有趣的事情吗？所以我想听听你和你的团队。是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Do you want to talk just a little bit about like you've you've done some really interesting stuff. So I I'd love to hear like you and then your team. Yeah.

</details>

**Brandon Anderson**: 是什么让**Axiom**如此特别？

<details>
<summary>Original English</summary>

**Brandon Anderson**: What what what makes **Axiom** special?

</details>

### Axiom Math的团队与背景

**Carina Hong**: 是的，我认为**Axiom**非常特别，因为他们是真正的专家数学家。基本上，他们是我们正在开发的系统的用户，而且迭代循环非常快。它非常非常快。你有一些最强大的数学家，无论是在研究还是奥林匹克竞赛中，你还有一些**Mathlib**的贡献者、维护者、开发者，真正的**Lean**专家，并将他们与来自应用机器学习（ML）领域的人结合起来，他们来自像**Metafare**和**Golden Age**这样非常强大的组织，以及拥有代码生成专业知识的人，他们与编译器合作，比如**Colonel Jan**。我认为这种跨学科的思维方式非常有帮助。我们认为AI for Math传统上就是跨学科的。人们甚至从AI for Science中借鉴技术，纯技术，从代码生成文献中借鉴技术，人们显然也从更广泛的前沿应用ML中借鉴技术，试图将其应用于AI for Math这个小众问题。所以我们也认为拥有这样一支非常特别的团队是一个差异化因素。我们还认为，正如你所说，没有永久的护城河。我们生成的专有数据，以及我们看到的一些飞轮效应，是一种时间护城河。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think **Axiom** is like very special because they're really expert mathematicians. Basically, they are users of the system we are developing and that iteration loop is very fast. It is extremely it is extremely fast. You have like some of the strongest, you know, mathematicians and both in research and Olympia contest and you also have people who are um, you know, **Mathlib** contributors, maintainers, developers um **Lean** gurus really and u combine them with people who come from like applied ML um really strong organizations like **Metafare** um and **Golden Age** um as well as people who have codegen expertise who work with like compiler like **Colonel Jan** um have kind of these backgrounds of people together. I think that sort of interdisciplinary way of thinking about things quite quite helpful. We think AI for math has traditionally been quite interdisciplinary. People are borrowing techniques from even AI for science. Pure tech um borrowing tech techniques from from the code gen literature and people are borrowing techniques from obviously the broader like, you know, frontier like applied ML um to try to apply on the niche problem AI for math. So we also think having this sort of very special special team is a is a differentiation. Uh, we also think that, you know, as you say there's no no permanent mode. Um, the proprietary data that we generate um and a little bit of a flywheel we are seeing is a time mode.

</details>

**Carina Hong**: 就我个人而言，我热爱数学。我认为，你知道，我从小就开始学习数学，当你要解决的问题有点超出能力范围时，数学有时会变得非常困难，有时会有点令人沮丧，有时我会想，如果我能有一个AI帮助我就好了。是的，我认为为什么不构建这样一个东西呢？

<details>
<summary>Original English</summary>

**Carina Hong**: Well me personally, uh, I I love math. I think, you know, I I kind of have been doing math since I was very young and like math sometimes gets really hard when when the problem you are solving are are just a little bit out of reach and it gets a bit depressing and times to times I wonder if I can just have an AI help me. Uh, and uh, and yeah, I think why I figure why not build such a thing?

</details>

**Brandon Anderson**: 你在**牛津大学**攻读了神经科学硕士学位。

<details>
<summary>Original English</summary>

**Brandon Anderson**: You did a master's at **Oxford** in neuroscience.

</details>

**Brandon Anderson**: 那对你的思考有影响吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Has that informed your thinking here?

</details>

**Carina Hong**: 这是一个很好的问题。我认为我的神经科学经验是，你很好地学习了什么很难？什么是不可能的？

<details>
<summary>Original English</summary>

**Carina Hong**: That's a great question. I think like my my my, you know, experience with neuroscience is you you learn very well but what's hard? What's impossible?

</details>

**Carina Hong**: 我的意思是，这很有趣。我认为在神经科学的那一年，我感受到了一些关于什么很难的感觉，但几乎没有感受到什么可能奏效的感觉。但是，我认为我当时是在神经科学的幌子下，在**UCL Gatsby Institute**闲逛，并有幸与一些非常酷的教员一起进行AI研究。所以，我认为那是非常富有成效的一年AI学习。

<details>
<summary>Original English</summary>

**Carina Hong**: I mean it's very interesting. I think that year of neuroscience like give me some feelings about what's hard and almost no feeling about what might work. So, but I think I was kind of under the pretense of neuroscience like hanging out at the **UCL Gatsby Institute** and was fortunate to do AI research with some really cool faculties and so I think that was a very productive year of AI study.

</details>

**Brandon Anderson**: 非神经研究。你。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Non- neural study. You.

</details>

**Brandon Anderson**: 所以你主要是为了学习AI。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you're it was mostly for you studying AI.

</details>

**Carina Hong**: 没错。没错。我认为在英国，如果你在20世纪，如果你称某物为AI，你不会得到捐款，但如果你称某物为脑科学，你可能会有机会。所以，**UCL Gatsby**是一个顶级的AI中心，很多人从那里去了**DeepMind**，包括**Deise**本人。这是一个非常棒的研究环境。我记得那些茶歇时间的讲座非常精彩，人们基本上只是在做AI。它被称为**Gatsby计算神经科学研究所**。

<details>
<summary>Original English</summary>

**Carina Hong**: That's right. That's right. I think in the UK if you um back back in the, you know, um 20th century if you call something AI, you would not get the donation, but if you call something brain science, you might have a chance. So, so the **UCL Gatsby** which is a premier AI hub where a lot of people actually go um, you know, from their to **DeepMind** including **Deise** himself, uh, it's a very wonderful research environment. Uh, I remember those kind of like tea time talks were very amazing and and people were basically just doing AI. Uh, it's called the **Gatsby computational neuroscience institute**.

</details>

**Carina Hong**: 是的。我认为那件事之所以发生，是因为我当时在神经科学硕士项目，然后很快意识到你需要杀死老鼠，我有点不想做那个，而计算神经科学听起来更有吸引力。当你看到项目，看到**Transformer**时，你会觉得你绝对想做那个。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. I think how how that kind of, you know, happened was because so I was I was in the master of neuroscience program and then um quickly realized that you need to like kill rats and um kind of don't want to do that and computational neuroscience sounds more appealing and and when you look at the project and you see like **Transformer** you're like you absolutely want to do that.

</details>

**Brandon Anderson**: 是的，我们都对此感到兴奋。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah, we're we're all excited about that.

</details>

**Brandon Anderson**: 所以在**Gatsby**之后，你在**斯坦福大学**开始了数学博士项目。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So so after the **Gatsby** uh, you started a math PhD program at **Stanford**.

</details>

**Carina Hong**: 我实际上在法学院全职学习了一年。哦。

<details>
<summary>Original English</summary>

**Carina Hong**: I started actually one year full full-time at the law school. Oh.

</details>

**Carina Hong**: 因为JD/PhD项目结构是，你必须全职住校一年。所以那也是非常有趣的一年，学习一些非常迷人的东西，比如刑法，研究凶杀案。令人兴奋。不。

<details>
<summary>Original English</summary>

**Carina Hong**: Because the JD PhD program structured in a way where you have to spend full one full residency year. So that was also a very fun year um of learning things that like are just quite fascinating like criminal law looking at homicide cases. Exciting. No. Um.

</details>

**Brandon Anderson**: 你有没有觉得法律系统在某种程度上被过度或不足地指定了，以至于你可能可以访问并改进它？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Do you ever feel like the legal system is under or oversp specified in some way that maybe you could um you could access and improve?

</details>

**Carina Hong**: 这是一个很好的问题。我认为对于很多事情来说，它绝对是指定不足的。对于其他一些事情，我实际上对将数学推理迁移学习到那些特定领域感到非常兴奋。我认为上诉诉讼，你看到一些真正优秀的上诉学者和律师，他们就是来自数学训练。不多，但像**Lawrence Tribe**就是一个例子，你知道，**哈佛大学**法学教授，左翼民主党最强大的上诉诉讼和最高法院简报的大脑之一。我认为还有很多其他领域，比如反垄断，它非常流程化；合同法有时也流程化；破产法、税法，更多是公司方面的。我只是喜欢诉讼方面。

<details>
<summary>Original English</summary>

**Carina Hong**: That's a that's a great question. I think for a lot of things it's definitely underspecified. Um, for some other things I was actually quite excited about sort of transfer learning from mathematical reasoning to those specific fields. I think appella litigation the legal gymnastics you see some really good appellet scholars and lawyers that just come from mass training. Not many but like **Lawrence Tribe** for one, you know, **Harvard** law professor um one of the, you know, strongest like um, you know, appallet litigation and SCOD's briefs like brains on on the left uh Democratic party um and uh uh and I think there's a lot of other domains such as antitrust that's incredibly flowcharty, contract law sometimes also flowarty, bankruptcy, tax u more on the corporate side I I I just love litigation side.

</details>

**Brandon Anderson**: 是的，所以实际上，我确实，只是因为我们正在谈论诉讼，这不是同一件事，但有一个**埃尔德什问题**，**Axiom**看到了，我不知道是**Axiom Prover**还是什么，对吧？对此存在争议，因为它声称已经解决了这个问题，而实际上证明已经被它发现了，然后只是形式化了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah so actually I do just just because we're talking about litigation, it's not the same thing, but there was a there was a **Erdos problem** that that **Axiom** saw I don't know if it was **Axiom Prover** or whatever is that right there was a controversy about it because it had represented that it had solved the problem when in fact the proof had been it had discovered the proof and then just formalized it.

</details>

### 埃尔德什问题与文献检索的挑战

**Carina Hong**: 是的。所以实际上发生的是，我们的竞争对手**Harmonic**决定公开宣称他们解决了未解决的**埃尔德什问题**124和481。然后我们相信了他们的文献综述，认为这些问题确实是未解决的，我们当时是一家非常年轻的公司。我们想测试我们的系统是否能尝试解决我们的竞争对手能解决的问题。我们完全没有想到它真的解决了它们，但事实证明我们都错了，因为这个问题实际上之前就已经解决了。我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So actually what happened was our competitor **Harmonic** decided to publicize that they have solved uh unsolved problems um **Erdog number** uh 124 and 481 and then we trusted their literature review believing that these problems are really truly unsolved and we were really young company at the time. We wanted to test if our system can attempt to try the problems that our competitor can. We fully did not expect that actually solved them, but um turns out that we were both wrong that in fact the problem has been solved before. I see.

</details>

**Carina Hong**: 所以这不是我们唯一一次依赖别人的文献搜索，我们应该承担责任。另一次是这篇名为《**无平方游走中的死胡同**》的论文。**Miller教授**提出了这个问题，结果发现它实际上已经解决了。但是，我们，我的意思是，我们真的应该做好自己的工作。

<details>
<summary>Original English</summary>

**Carina Hong**: So then it's not the only time that we relied on others literature uh uh literature search and, you know, we we should own it. Um, the other time was this paper called **dead ends in squaref free walks**. Um, you know, professor um uh uh **Professor Miller** um have this problem that actually turns out to have been solved. But um, we we I mean, we really should have done our part. That is that is, you know.

</details>

**Brandon Anderson**: 我试图引出的观点是，不是说你们做错了什么，而是。

<details>
<summary>Original English</summary>

**Brandon Anderson**: The point I'm trying to maybe elicit is um not not like you guys did something wrong, but rather.

</details>

**Carina Hong**: 你知道，有一个日本的广告，整个公司，成千上万的人在广告中道歉，说“对不起，我们把价格提高了5美分”，那就是我想做的广告。这太尴尬了。

<details>
<summary>Original English</summary>

**Carina Hong**: You know, there's this like Japanese like um advertisement of like a whole company like hundreds and thousands of people like apologizing in the in the advertisement and it's like, you know, sorry we raised our price by like 5 cents and that's the advertisement I was like thinking that maybe I should just do that. It's so it's so embarrassing.

</details>

**Brandon Anderson**: 不，但我认为信息来源的问题，以及你如何，它又回到了我之前问的问题，我如何将答案与问题联系起来？

<details>
<summary>Original English</summary>

**Brandon Anderson**: No, but I think that the question of providence of information and sort of like how do you it goes back to the question I was asking before about like how do I how am I connecting the answer to the question.

</details>

**Carina Hong**: 是的，这是一个很好的问题。我认为在**埃尔德什**事件之后，我们变得非常小心。所以我们有点，你知道，我们没有真正看其他的**埃尔德什问题**。我相信**Harmonic**仍然声称他们解决了**埃尔德什问题**，可能解决了，也可能没有，我不知道。你知道，我认为**陶哲轩**和许多其他人有一个所有**埃尔德什问题**及其状态的数据库。我认为，你知道，顺便说一句，这是一个非常容易犯的错误，因为有很多**埃尔德什问题**实际上已经解决了，对吧？我认为那确实是，我认为，你知道，搜索和检索是一个难题，你不知道那个论点或它的等价版本是否已经解决了。事实上，我认为整个数据库中最有趣的部分是，有很多问题不是直接解决的，但可以仅仅是另一个已解决结果的非常微不足道的扩展，或者有时甚至没有解决。有时我认为在这个“**无平方游走中的死胡同**”案例中，这与**Harmonic**完全无关，我们实际上没有意识到，然后**Conander教授**实际上向我们和**Miller教授**指出，它实际上来自**Stack Math Overflow**或**Stack Overflow**上的一个帖子。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, this is a great question. I think after **Erdos** we're like extremely careful and so we kind of like, you know, we didn't really look at the other **Erdos problems** I believe that **Harmonic** still continue to claim they have solved **Erdos problem** that might might not I don't know uh it's, you know, there's a I think **Terrence Tao** and a lot of other people have a database all the **Erdos problems** and the status I think, you know, like it is really by the way like it's a really easy mistake to make because there are so many **Erdos problems** that actually have been solved right and I think that that's kind of indeed I think like, you know, search and retrieval is a is a is a hard problem like you don't know if that argument or an equivalent version of that in fact, I think the most interesting part about that entire database is um there are a lot of problems that are not directly solve solved but can be just an very is the extension almost a trivial extension of another result that has been solved or not sometimes not even resolved sometimes I think in this um **dead end square free walks** case which is nothing to do **Harmonic** complet um that we actually didn't realize and then **Professor Conander** actually pointed to us and to **Professor Miller** is that it was actually from a **Stack Math Overflow** or **Stack Overflow** post.

</details>

**Carina Hong**: 嗯，一个用户指出有一个1936年的结果。这很有趣。我认为很难找出为什么搜索是一个难题。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, like a user pointed out that there's a 1936 six results. It's fascinating. I think it's hard to hard to find out why search is a hard problem.

</details>

**Brandon Anderson**: 我猜这意味着你们的猜想引擎或类似的东西是否使用搜索作为其过程的一部分？还是那是你们人类做的事情，然后输入给它？

<details>
<summary>Original English</summary>

**Brandon Anderson**: I guess that means that you do does the the conjecture engine or whatever does that does that use search as part of its process or is that something that you kind of you you the human does and then feeds?

</details>

**Carina Hong**: 我认为知识图谱或知识库是任何公司都非常重要的组成部分。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I think knowledge graph or knowledge base is a very, you know, important component of any any company.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 而且我认为它没有被充分讨论。

<details>
<summary>Original English</summary>

**Carina Hong**: Uh, and I think I don't think it's talked about enough.

</details>

**Brandon Anderson**: 所以你们，听起来你们不想给我们太多细节，但你们有一个知识图谱。我的意思是，这还引出了我读到过的地方，你们有一个非常庞大的**Lean**证明数据库，是你们生成的。所以从某种意义上说是合成数据，但这可能对你们来说是一个竞争优势。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And so and and you guys with that it sounds like you don't want to give us too many details, but like so you guys have a knowledge graph. I mean that brings up also I I read somewhere that you guys have a really massive database of **Lean** proofs that you've generated. So synthetic data in in some sense, but that the and this may maybe is a competitive advantage for you.

</details>

**Carina Hong**: 我认为每个人都在努力积累数据，这不是一种护城河，它只是时间和时间护城河。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I think everyone is trying to accumulate like a data which is not a mode it's just time and time mode.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Carina Hong**: 是的。这完全取决于你是否能足够快地执行，以确保你有一个缓冲，比如说，因为你的数据集积累，但这只是一个缓冲。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. It's all it's all it's all about like, you know, whether you can execute fast enough um to make sure that you have like a certain buffer um because of say your data set, you know, accumulation but that is only just a buffer.

</details>

**Brandon Anderson**: 你有没有想过做一些像数学领域的**AlphaZero**一样的事情，从零开始，让它自己创造公理，看看会发生什么？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Have you ever thought about doing something like an **AlphaZero** for math where you start from nothing and let it just make up axioms and see what happens?

</details>

**Carina Hong**: 啊，这是一个很棒的问题。我认为这是一个非常有趣的方法。是的，我认为我们相信一件事，那就是，你知道，假设**Axiom Prover**可以成为一个非常强大的数学家，那么它每天证明的东西应该希望能帮助它改进，对吧？我认为这种自我改进的设计非常有价值。

<details>
<summary>Original English</summary>

**Carina Hong**: Ah, this is a wonderful question. I think that's a very interesting approach actually. Yeah, I think we we believe in something which is that like, you know, suppose um **Axiom Prover** can be a really strong mathematician and then really the the thing that it is proving every day should hopefully help it improve right I think this sort of self-improvement design is extremely valuable.

</details>

**Carina Hong**: 嗯，我认为AI for Math社区中还有其他人，我认为**Gabriel Pesra教授**的工作非常有趣。我认为有一些更具猜想性质的探索。假设我们只是改变，你知道，有很多特定的事情你可以以某些方式做，可以尝试看看你的系统是否能学会猜想和构建理论。我认为这个话题非常有趣和重要，因为它确实，你声称。

<details>
<summary>Original English</summary>

**Carina Hong**: Um, and I think there are um other people in the AI for mass community I think uh **Professor Gabriel Pesra's** work is very interesting um I think there are some of the um kind of more conjecturing type of exploration Um suppose we just kind of change um, you know, a lot of the there are specific things you can do in in certain in certain ways that that can try to see if your system can learn to contracture and build theories. I think that the the topic is really interesting and important because it really you're claiming that the.

</details>

**Carina Hong**: 达到**超级智能**。

<details>
<summary>Original English</summary>

**Carina Hong**: To get to super intelligence.

</details>

**Brandon Anderson**: 有点像。

<details>
<summary>Original English</summary>

**Brandon Anderson**: There's sort of this like.

</details>

**Brandon Anderson**: 这根本不可能。也许如果你有无限的资源，你可以只用强化学习，它就能奏效。但现实是，你无法足够样本高效地做到这一点。所以你需要在推理过程中有一个验证器，而不是因为你在训练过程中确实有验证器，但你在推理过程中没有。

<details>
<summary>Original English</summary>

**Brandon Anderson**: It's just not going to be possible. Maybe if you had infinite resources, you could just RL and it would work maybe. But the reality is is that you just can't be sample efficient enough or whatever it is to do that. So that you need some sort of verifier in the loop with the inference process rather than because you do have verifiers and like sort of during the training process and you just don't have them during the inference process.

</details>

**Carina Hong**: 是的，我认为他们中的很多人只是秘密地试图用这个来作为他们推理的基础。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think a lot of them are just secretly like trying to use this to ground their reasoning.

</details>

**Brandon Anderson**: 是的。我也是。我的意思是，我很惊讶，当**01**即将到来，但还没有发布时，每个人都知道**01**要来了。我确信他们会宣布他们正在使用**Lean**进行形式化验证和证明，并实际生成证明，然后验证它们，这样它们就能为推理提供基础。我的意思是，那是我的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes. As well. I mean, I would I was surprised that that like when when **01** was, you know, everyone knew **01** was coming, but it did hadn't come out. I was sure they're going to announce that they're using **Lean** to to do like **formal verification** of proofs and actually generate proofs and then verify them so that they're grounding and reasoning. I mean, that was my.

</details>

**Carina Hong**: 当我在那里的时候，有**3PF**，那是一项很棒的工作。还有**MiniF2F**。这些都是**OpenAI**的形式化数学工作。好的。所以大概那些人正在做一些事情。

<details>
<summary>Original English</summary>

**Carina Hong**: When I was there, there was **3PF** that was a great piece of work. There's also **MiniF2F**. These are all formal mass work at **OpenAI**. Okay. So presumably those guys are doing something.

</details>

**Brandon Anderson**: 不，不，他们都离开了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: No, no, they all left.

</details>

**Brandon Anderson**: 哦，他们都离开了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Oh, they all left.

</details>

**Carina Hong**: 所以这就是我的观点，如果你是一个实习生，我猜你不能永远是实习生。所以假设你是一个初级技术人员，你想在一个问题上工作，只要需要多长时间来解决它。奇怪的是，人们认为初创公司是那种你的跑道可能会耗尽，然后一切都会崩溃的东西。你可能更有机会在像**Axiom**或其他新实验室这样的初创公司中，长时间专注于同一个问题。

<details>
<summary>Original English</summary>

**Carina Hong**: So that's my point which is that if you're like, you know, an intern, I guess you can't be an intern forever. So let's say you're like a junior, you know, like member technical staff and you want to work on something for like as long as it takes to solve it. Weirdly, people think about startup as this sort of your runway can just run out and it can just like all fall apart thing. You might have a better chance of staying focused on the same problem for as long as it takes at say a startup like **Axiom** or one of the other new labs.

</details>

**Brandon Anderson**: 是的。如果你与大公司的使命保持一致，而不是像有人决定你正在做的事情不再。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. If you're aligned to the mission of the big company rather than like somebody decided that what you're doing is no longer.

</details>

**Carina Hong**: 是的。是的。可能是你的副总裁输掉了一些政治斗争，所以，是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. It can be your VP lost some political fight and so Yeah.

</details>

**Brandon Anderson**: 是的。绝对如此。所以。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. Absolutely. So.

</details>

**Carina Hong**: 不，显然如果我们成功了，他们都会，你知道，再次开始做那件事。

<details>
<summary>Original English</summary>

**Carina Hong**: No obviously if we succeed then they're all going to, you know, start doing that again.

</details>

**Brandon Anderson**: 是的。然后，我猜作为人才，也会有更多潜在的选择。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes. And then like I guess as a talent then there are more like, you know, potential places to choose from as well.

</details>

**Brandon Anderson**: 是的。所以你们的工作就是快速前进。所以他们正在挣扎。实际上，你们，我们还没有谈到，但你们实际上也刚刚发布了一个用于**Lean**验证的API。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. So then your job is to go fast. So they they they're they're struggling. So actually you um we haven't talked about it but you actually also just released an um an API for doing **Lean** verification.

</details>

**Brandon Anderson**: 而且我实际上用**Claude Code**试了一下，因为它比设置自己的**Lean**工具链更容易。是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And um I actually tried it with **Claude Code** um because it's easier than setting up uh, you know, your own **Lean** um tool chain. Yeah.

</details>

**Brandon Anderson**: 嗯，你知道，尝试让**Lean**证明一些东西。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Um, and the infrastructure is is maybe non-trivial especially at scale. So you want to talk a little bit?

</details>

### Axel：Axiom的Lean引擎

**Carina Hong**: 是的。是的。所以我们刚刚发布了**Axel**，AXL代表**Axiom Lean Engine**，它实际上是一套用于**Lean**的证明验证和操作工具，用**Lean**语言构建。所以，它是一堆元编程工具。现在，元编程人才非常，我认为非常难找，我们非常感谢拥有一个真正优秀的团队来做这项工作，我们想把它免费发布给社区使用，因为我们认为可能还有其他人也在进行大规模的**Lean**操作，这些工具将使他们的工作更加健壮、更快，并能大规模进行。**Axel**目前我认为有14个这样的工具，从`verify proof`开始，它是一种确保没有奇怪事情发生的工具，比如没有**Lean**代码作弊，你没有假设奇怪的事情。如果你问n加n等于n，你可以证明2加2等于2，你知道那肯定不是正确答案。嗯，还有很多其他类型的生成工具。例如，你可以尝试不同的修复尝试。所以，你知道，损坏的**Lean**输入，然后好的**Lean**输出。而且，你知道，目前还有其他大型语言模型（LLM）的修复方法。所以希望我们提供的这个能更便宜，更直接，而且，你知道，我认为强大而优秀的工程可以让你走得很远。很多**Lean**社区的人一直在使用**Axel**，即使它才发布一周，来做各种各样有趣的事情。我们看到区块链社区的人用它来做有趣的事情，我们还听说很多人说**Claude**加**Axel**是他们目前的首选设置。我们认为这些是非常有趣的工具。我认为著名的，我认为今天有一位数学家说他形式化了**Donald Knuth**的，你知道，用**Claude**来证明一个结果，我认为是一个**Ramsey**结果，然后形式化了**Lean**证明，然后那个也使用了**Axel**工具。所以我们很高兴看到人们已经在使用它。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. So we just released **Axel**, AXL stands for **Axiom Lean Engine** and uh it's really a set of kind of proof validation and manipulation tools that are built for **Lean** in the language of **Lean**. So uh it's a bunch of meta programming tools. Now meta programming talents are are extremely I think like, you know, hard to find and we're so grateful to have like a really crack team working on that and we want to kind of like release it to the community for um to use for free because we think that there are probably other people doing also like large scale **Lean** operations and these tools going to make their stuff go a lot more robust and faster and do so at scale. Um and **Axel** is currently I think 14 uh like such tools starting from `verify proof` which is the sort of to make sure that there's not nothing weird um, you know, going on like no no sort of cheating by by **Lean** code you don't aim something out, you know, we don't you don't assume weird things if you ask n plus n equals n you can pro to prove 2 plus 2 equals 2 which you're you know, for sure not that's not the right answer. Um, there are also like, you know, a lot of other kind of generation tools. Um, for example, you can try like different repair attempts. So, you know, broken **Lean** in and then good **Lean** out. Uh, and you know, there are like currently, you know, other repair methods by LLM. So hopefully this what we provide can be just a lot cheaper and uh more kind of, you know, straightforward and it's just, you know, I think strong strong and better engineering can can get you to to a place that's quite far. A lot of the people from the **Lean** community has been using **Axel** even if it's just been a week to do all sorts of different interesting things. We have seen uh people from the kind of blockchain community use it to to do interesting things as actor and we have seen also we have heard from a lot of the people that **Claude** plus **Axel** is kind of their go-to setup um for for now. Um, we think that these are really interesting tools. I think famously I think um today there's this mathematician who said he formalized the **Donald Knuth**, you know, using **Claude** to prove I think a result um a **Ramsey** **Ramsey result** and then to formalize the the the **Lean** proof and then um that is also using **Axel** tool so we are really glad to see people kind of already using it.

</details>

**Brandon Anderson**: 我的意思是，我觉得这是**陶哲轩**所说的协作的绝佳机会，一旦人们能够使用通用工具，并且变得容易操作，我的意思是，即使你有一个直觉，即使不是像我这样强大的数学家，你也可能能够参与到证明一个更大定理的努力中。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I mean, I feel like this is a great opportunity for the collaborations that **Terrence Tao** was talking about as well where once people have access to the common tools and it becomes easy to do and I mean like if if you have a intuition even uh not a strong ma mathematician like myself, you might be able to participate in the, you know, sort of like an effort to prove a larger theorem or something like that.

</details>

**Carina Hong**: 是的，我认为这很有趣，这种观点是，如果你想想数学，它不像软件工程那样具有协作性。你没有成千上万的人一起工作。我认为**Polymath**就是一个例子，当时发生了这样的事情，那太棒了。所以如果你有很多真正好的设置，确实，像商品化的访问，人们都可以参与进来。事实上，我认为一些大型形式化项目就是这样完成的，事情被分成子任务，但**陶哲轩**和**Alex Kondonderage**的蓝图编写过程，将任务分配给不同的人，以及事情如何组合在一起，那个蓝图编写部分极其重要。我认为已经有关于球体堆积的结果，我认为是另一家公司做的，而A维度的蓝图部分仍然很大程度上建立在球体堆积社区，**Lean**社区，人类蓝图的基础上，与其他一些结果也类似，蓝图部分仍然是人类生成的，我认为自动生成的蓝图将成为一个技术瓶颈，许多人正在同时尝试解决。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think that's that's very interesting like view which is that like if you think about like mathematics has been not like as collaborative as software engineering. You don't have like hundreds and thousands of people working on something together. I think **Polymath** was an instance when when that happened that was fantastic. So if you have a lot of really good sort of setup indeed like commoditized kind of access and people can all participate in in fact that's how I think some of the large formalization projects have been done uh things are divided into subtask but really the blueprint writing process by say **Terren Tao** and **Alex Kondonderage** of assigning the task to different people and how things kind of fit together that blueprint writing part is extremely important and there has been I think result about sphere packing I think by um one of the other companies out there and the blueprint part for um the A dimension is still pretty much built on what the sphere packing uh community the **Lean** community the humans blueprint and similar with some of their other results as well the blueprint part has still been human generated and I think autogenerated blueprint is going to be a technical bottleneck that many people are trying to solve around the same time.

</details>

**Brandon Anderson**: 那么，我作为一个，你知道，**Claude Code**用户，尝试解决一些小的引理或类似的东西是否有价值？即使我对数学没有很好的理解，也许我有一个高层次的理解。

<details>
<summary>Original English</summary>

**Brandon Anderson**: So is there value in me as a, you know, **Claude Code** user trying to attempt part like some small lema or whatever um where I don't have a great understanding of the math maybe I have a high level understanding.

</details>

**Carina Hong**: 这取决于你是想形式化还是想证明。

<details>
<summary>Original English</summary>

**Carina Hong**: Depends are you trying to formalize or are you trying to prove.

</details>

**Brandon Anderson**: 嗯，证明新的东西。这是一个很好的观点，是的。所以也许形式化，你显然可能会从形式化开始，对吧？你知道证明，但你就是无法让任何人正确地形式化。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Uh to prove new things that's a good point yeah so maybe form you would obviously probably start with formalization right you know the proof and you just can't get nobody has been able to get the formalization correct.

</details>

**Carina Hong**: 我确实见过人们使用**Lean**和形式化，他们尝试手动完成，你知道，而不是使用AI作为学习数学的方式。不，你知道，它是自动形式化。你没有那个过程。嗯，这很有趣，因为我认为我的很多朋友之所以开始研究**Lean**和**Mathlib**，是因为他们正在攻读博士学位，而且这个问题非常困难。我们总是卡住，我们想回顾一些本科课程，那时我们仍然理解数学是什么，我们通过做**Lean**来做到这一点，我认为这非常美妙。

<details>
<summary>Original English</summary>

**Carina Hong**: I do actually have seen people use **Lean** and formalization and they try to do it by hand, you know, not using and AI as a way to learn mathematics. No, it's, you know, it's auto formalization. You don't have that process. Well, it's interesting because I think a lot of the uh my friends who started, you know, working on **Lean** and **Mathlib** was because they are in PhD and this problem's really hard. We get stuck all the time and we want to kind of review some of the undergrad classes a time where we still understand what the math was about and we do so by, you know, doing **Lean** and I think that's that's very beautiful.

</details>

**Brandon Anderson**: 材料。

<details>
<summary>Original English</summary>

**Brandon Anderson**: the material.

</details>

**Carina Hong**: 是的，但如果你有，例如，访问**Axiom Prover**，它也可以形式化所有形式化的东西，你就失去了学习过程的那个部分。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, but if you have for example like, you know, um access to **Axiom Prover** that also can formalize all the formalized things and you don't have you lose that part of the learning process.

</details>

**Carina Hong**: 是的，但我确实认为，你知道，对于你和我，我们可以设置**Axel**并尝试看看我们可能能够证明什么结果。我认为这很有趣。感谢**Axel**大大加快了速度。你不需要等很长时间。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, but I do think that, you know, like for for for, you know, you and I we can set up like **Axel** and try to like see, you know, what what results we might be able to prove. And I think that's quite interesting. And thanks to **Axel** sort of making the speed a lot faster. You don't have to wait very long.

</details>

**Carina Hong**: 我记得**Pudnam**考试那天。我们都在作战室里。那是星期六。我们都非常兴奋，我们刚刚从官方组织，**Pudnam**考试的监考人那里拿到了试卷。我们只是在看**Axel**的工作量有多大。没有它，我们不可能在时间限制内解决那八个问题，绝对不可能在时间限制内。我认为这些工具的一点是，它非常有趣，因为你也可以有有趣的强化学习奖励。

<details>
<summary>Original English</summary>

**Carina Hong**: I remember the **Pudnam exam** day. We were all like in the war room. It was a Saturday. We're all really excited and we just got the exam paper from the official um like organization, the proctor of the **Pudnam exam**. We just like were looking at like how like how much workout **Axel** is like getting. And without it we couldn't have solved it with um I think the eight problems within the time limit that definitely not not within the time limit. And I think one thing about these tools is like it's very interesting in that potentially you can have interesting reward for RL as well.

</details>

**Brandon Anderson**: 你这话是什么意思？

<details>
<summary>Original English</summary>

**Brandon Anderson**: What do you mean by that?

</details>

**Carina Hong**: 所以，例如，`verify proof`可以作为奖励，因为它基本上是一个完全正确且经过验证的证明。我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: So for example `verify proof` can be a a reward for just basically a proof is completely correct and validated. I see.

</details>

**Carina Hong**: 我认为形式化验证工具可以成为强化学习的一个有趣方向。

<details>
<summary>Original English</summary>

**Carina Hong**: I think **formal verification** tooling can be interesting direction to pursue with RL.

</details>

**Brandon Anderson**: 是的。所以你的意思是，例如，你形式化，自动形式化非形式化证明，然后验证什么，然后用那个作为奖励，还是你的意思是？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. So you mean um for example you formalize auto formalize the informal proof and then verify what and then use that as a reward or do you mean?

</details>

**Carina Hong**: 不，我的意思是，你将**Lean**程序传递给这些形式化工具，对吧？然后你会得到某种分数。

<details>
<summary>Original English</summary>

**Carina Hong**: No, as in like you pass like **Lean** programs in these formal tools, right? like and you will have some sort of score.

</details>

**Brandon Anderson**: 好的。是的。我认为如果我要构建**01**之类的东西，我心里会使用我刚刚描述的东西。但你是在说只是为了学习如何做**Lean**。所以，前沿实验室的价值主张很有趣，那就是假设你是一个TOC企业，那么当然，你完全可以不做我们正在做的事情。例如，我们看到**DeepSeek**最初有一个形式化团队，然后后来因为战略方向改变而解散了那个团队，这都是完全合理的。现在假设你专注于编码，并且你有人才想做我们正在做的事情。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay. Yeah. I think if I were to build **01** or something, I would have in my mind I would have use what I just described. But you're saying just to learn how to do **Lean**. So, so the value proposition which is interesting about frontier lab is that suppose you are a toc business then sure you you can just not do what we are doing and we have since for example **DeepSeek** like originally having a formal team and then later dissolve that team because of strategic direction change that's all completely reasonable now suppose you are focused on coding right and you have talent who want to work on what we're doing,

</details>

**Carina Hong**: 那么你做代码生成，进一步发展你的优势和模式，会更有意义。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: It makes a lot more sense for you to do code generation, further your strength and mode. Yeah,

</details>

**Carina Hong**: 你可以与**Axiom**合作。就像例如，前沿实验室与从事搜索的初创公司合作，比如**Excel**和**Parallel**，对吧？只需调用**Excel**的搜索API，潜在地，你知道，如果你是前沿实验室，我认为你应该调用**Axiom**的验证API。

<details>
<summary>Original English</summary>

**Carina Hong**: You can partner with **Axiom**. Um just like how for example, Frontier Labs um partner with uh startups that work on search such as **Excel** and **Parallel**, right? Just call **Excel** API for search and potentially, you know, if you're Frontier Lab, I think you should call **Axiom** API for verification.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes.

</details>

**Carina Hong**: 嗯，更好的介词，但是。

<details>
<summary>Original English</summary>

**Carina Hong**: Um better preposition, but.

</details>

**Brandon Anderson**: 建立自己的不合理。我的意思是，你知道，潜在地，我认为人才，**Lean**的挑剔性，数据代码的种类，你知道，没有理由这样做。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Spitting up your own. It doesn't make sense. I mean, it just, you know, potentially, um, I think the talent, the the finicky of **Lean**, um, the sort of data code, like like, you know, there's there's no reason to.

</details>

**Carina Hong**: 是的。我的意思是，我花了五分钟就设置好了。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. I mean, it took me five minutes to set up.

</details>

**Brandon Anderson**: 你为什么决定开始一个。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Why did you decide to start a.

</details>

**Carina Hong**: 对。我为什么决定？你当时是**斯坦福大学**的数学研究生。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. Why did I decide? You were a grad student at **Stanford** and, you know, in math.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah.

</details>

**Brandon Anderson**: 那么，是什么让你决定？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So, what made you decide to.

</details>

**Carina Hong**: 我根本没有学数学很长一段时间。我，我，我认为我几乎一读博士就立即开始筹款了。所以那不是。

<details>
<summary>Original English</summary>

**Carina Hong**: I wasn't in math for a while at all. I was I was uh I think like almost as soon as I started the PhD, I just started fundraising. So it wasn't like.

</details>

**Brandon Anderson**: 哦，真的吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Oh, really?

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah.

</details>

**Brandon Anderson**: 那是计划吗？还是你一开始就在那里，然后几乎立刻意识到这是。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Was that the plan or did you did you start there and you're like almost immediately realized that this is.

</details>

**Carina Hong**: 对。对。所以法学院的那一年，对吧，它在智力层面上对我来说非常非常有趣。但那也是我生活中第一次完全没有科学、技术、数学的一年。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. Right. So So the year of law school, right, it was very very interesting to me like on an intellectual level. But it's also this the first year where I had no science, technology, math whatsoever in my life.

</details>

**Carina Hong**: 这是一个奇怪的一年，对吧？我读了很多书。我练习。嗯，我正在学习如何写作。我正在学习如何阅读。

<details>
<summary>Original English</summary>

**Carina Hong**: It's a weird year, right? Like I'm I'm reading a lot. I'm I'm practicing. Well, I'm learning how to write. I'm learning how to read like.

</details>

**Carina Hong**: 但我只是，我只是想沉迷于技术方面的东西。那也是那一年发生的事情。所以，是的，法学院的那一年，对吧？它对我来说非常非常有趣，因为就像，好吧，我需要沉迷于技术方面的东西，否则我就会，我不想说我无聊，因为我真的很喜欢法律的一切。我真的非常喜欢它。那是一件非常有趣的研究。但是，我只是，我的意思是，我基本上一直对推理的进展非常兴奋。我看了很多后训练的论文。我只是自己学习所有这些。然后，在某个时候，我达到了一个地步，我觉得这肯定会发生。

<details>
<summary>Original English</summary>

**Carina Hong**: And but like I'm I'm just kind of I want to like be obsessed about something in technology. Like that was also what's going on that year. So yeah, the year of law school, right? And and it was very very interesting to me because it's like okay like I just I need to be obsessed with like a technical thing cuz otherwise I get to I don't think I'm bored because I really love like everything about about law. I really really loved it. It was it was something that's incredibly interesting to study. Um, but I just I I mean I've been basically like, you know, very excited about like the progress of reasoning. I was looking at a lot of the post-training kind of papers. I was I was learning all of these like just by myself. Um, and then at one point it got to a point where I'm like I think this is for sure happening.

</details>

**Carina Hong**: 而且，我认为和**Shou**在Ver的每个周末交谈，也没有帮助平息这个想法。所以我变得越来越沉迷。

<details>
<summary>Original English</summary>

**Carina Hong**: And like I think talking to **Shou** right at at Ver like every weekend also like it didn't help like soothing this thought. So I got more and more obsessed.

</details>

**Carina Hong**: 在某个时候，我心想，好吧，如果我每分钟都在做这件事，而且我无法思考其他事情，那么，你知道，我需要做点什么。我的意思是，就像你一样，我疯狂地爱上了AI将做数学的想法，然后，好吧，我现在要做数学吗？这真的非常疯狂，我记得当时这种痴迷非常强烈，我就是无法摆脱它。然后我去了**Nihennessy**活动。

<details>
<summary>Original English</summary>

**Carina Hong**: And at a point I'm like, okay, if I'm doing this like literally every minute and I can't think about something else like, you know, I need to do something about it. I mean it's like you I fall madly in love with the idea that AI is going to do math and like, okay, now do I do I do math? like I it's really really crazy like at a time where I remember the obsession was quite I just couldn't get out of it and then um I went to this **Nihennessy** event.

</details>

**Carina Hong**: 学者餐厅会举办各种免费午餐活动，那些活动很棒，因为你可以得到免费食物，并且可以接触到有趣的知识。我记得**Julie Draw**，她当时是**Facebook**的第一位产品经理，她来演讲，然后演讲结束后我基本上就走上前去问她，如果你想创业，但你又真的很想做学术，因为你喜欢数学，你会怎么做？然后她说，嗯，你知道，你花在这两件事上的时间是多少？我说，100%和0%。然后她说，嗯，你必须追随你的能量。

<details>
<summary>Original English</summary>

**Carina Hong**: Scholar dining house like host all sorts of like free lunch events and those are great because you get free food and you get interesting intellectual exposure to things and I remember **Julie Draw** who was I think a **Facebook** um first **Facebook** PM came to speak and then after that I just like basically walked up to her and I said like, uh, like what do you do if you want to do a startup and you really wanted to do academia because you you kind of love math. And then she's like, well, you know, what's your time spent on these two different things? And I'm like, 100% 0%. And then she's like, well, you kind of have to follow your energy.

</details>

**Brandon Anderson**: 是的。我的意思是，如果你完全沉迷于它。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. I mean, if you're if you are completely obsessed with it.

</details>

**Carina Hong**: 是的。我完全沉迷于它，但我认为它会变得很大。而且我认为它必须是一家营利性初创公司，因为它比取得数学突破的范围要广得多。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. I was completely obsessed with it, but I thought it's going to be big. And I thought like it it just it just has to be a for-profit startup because like it's so much broader than making mathematical breakthroughs.

</details>

**Carina Hong**: 如果你考虑递归自我改进，以及更高级别的概念，比如你真的想拥有这个AI科学家，那么数学推理将是其中非常重要的一部分。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: If you think about like recursive self-improvement and like really the the kind of more high level like concept of like you really want to have this AI AI scientist like the mass reason is going to be is going to be a pretty big part of it. Yeah.

</details>

**Carina Hong**: 现在尝试，我认为**Cursor**和**Claude**以及其他人相信的是，就像数学可以迁移到编码一样，编码也可以迁移到数学。我认为这是真的。只是，你知道，为什么不直接推动它呢？我不明白。你需要直接推动它。

<details>
<summary>Original English</summary>

**Carina Hong**: And now trying like I think the the sort of belief by by **Cursor** and **Claude** and other folks is like okay like just like mass transfer to coding coding transfer to mass as well. I think that's true. It's just that like, you know, why why not push it directly. I don't I don't get it. You need to push that directly.

</details>

**Carina Hong**: 然后还有另一个想法，也许回到协作点。验证传统上被认为是，好吧，有些行业有很多防护措施。所以如果你在国防、军事领域工作，好吧，你需要基本上满足很多进入壁垒，以满足那些严格的要求。所以验证是针对封闭行业的，但现在我认为**验证AI**首次开启了协作，无论是人机协作，还是在蓝图规划之前的人人协作，**Lean**是一种基础，是一种验证形式语言，然后是像我们现在看到的人机协作，以及未来AI代理之间的协作。

<details>
<summary>Original English</summary>

**Carina Hong**: And then there's this other like, you know, thought which is that and maybe kind of going back to the collaboration point right. Um verification has traditionally been thought of as okay well there are some industry where there's a lot of guard rails. So if you're working in defense, military use, okay, you need to like basically satisfy a lot of barriers to entry to meet those stringent like requirements. So it's it's something that's verification is for the industries that are closed but it's for the first time now I think **verified AI** is to open up collaboration either it's human-AI collaboration well before blueprinting that's human-human collaboration and **Lean** was a grounding was a verification formal language and then human-AI collaboration like we're seeing now future AI agent-agent-agent like collaboration.

</details>

**Carina Hong**: 所以我认为**验证AI**是为了开放性，而不是为了满足封闭行业的需求。我认为验证不应该仅仅是为了，哦，我记得，你知道，有一篇文章说聊天机器人搞混了，AI是幻觉的解决方案吗？抱歉，是数学是幻觉的解决方案吗？对我来说，验证不是为了错误。对我来说，验证是为了扩展才华，复合才华。这就像回到协作点。它是关于**拉马努金**成为一个更强大的数学家。他本身已经很强了，但验证帮助他扩展了才华，既能向上扩展，也能向外扩展。所以验证。

<details>
<summary>Original English</summary>

**Carina Hong**: So like I think **verified AI** is for openness, it's not for meeting the requirements of closed industries. And I think just like I think verification should not be about, oh, I remember like, you know, there's article like chatbots mixed stuff up is AI the solution to sorry it's math solution to hallucination. Verification to me is not about lousiness. Verification to me is about scaling brilliance compounding brilliance. It's like just kind of going back to the collaboration point. It's about **Ramanujan** being a much stronger mathematician. He was already a really strong one but verification helps him extend the brilliance like both kind of like scale up and scale out. So verification.

</details>

**Brandon Anderson**: 严谨的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: rigorous.

</details>

**Carina Hong**: 对我来说，验证不是为了，你知道，消除错误，消除缺陷，而是为了扩展才华。第三点是，对我来说，验证不是为了，你知道，仅仅谈论严谨，它实际上是为了性能提升，对吧？它不仅仅是为了严格的要求，你必须克服的障碍，它实际上是**验证生成**将使其变得更好。我认为这三点，我认为最后一点是，很多人认为你从事验证是因为你不信任技术。这在公众中卖得很好，包括我的父母，他们会问“哦，我们为什么要进行验证？因为，你知道，技术会犯错误。”不，我们不认为验证是基于对技术的不信任。它是因为，你知道，预期的快速指数级扩展，以及技术的部署和创造，以及技术进步，是它所推动和要求的。这是一个非常数学的视角，对吧？因为你是在说证明是证明驱动数学，对吧？很多数学是基于证明的。是的。数学驱动着世界上的许多科学和创新，数学的创新驱动着世界的创新。所以。

<details>
<summary>Original English</summary>

**Carina Hong**: Verification to me is not about, you know, like erasing the mistakes the lousiness about scaling brilliance and and the third point is that like verification to me is um not about like the sort of, you know, just talking about rigor it's actually about performance gain right it's not just about the stringent requirements the hurdles that you need to overcome it is about like actual **verified generation** is going to make it so much better and I think like kind of these three points I think the last point is that a lot of the people think that you work on verification because of your distrust for technology. Like it sells really well to I think the general p public including like my parents like, oh, why we're doing verification because like, you know, technology make mistakes it's no we don't think verification is based on is because of the distrust for technology. It's because that's what like um expected rapid exponential scale up and and um the deployment and the creation of technology and technological progress is what that compels and demands. It's a very mathematical perspective, right? Because you're saying proofs are proofs are drive math, right? A lot of math is based is is about proofs. Yeah. And math drives a lot of science and innovation in the world and the innovations in math drive innovation in the world. So that.

</details>

**Carina Hong**: 但它甚至不需要通过，你知道，解决所有问题。我的观点是，迁移学习不是，迁移学习是关于推动数学推理。所以，这里有几种叙事。对于一些人来说，就像你解决了数学问题，然后数学是科学的基础，所以这实际上是从AI for Math中提取的激进的AI for Science层。我们实际上相信普遍的迁移学习。我认为**Axiom**处于基础设施堆栈中。

<details>
<summary>Original English</summary>

**Carina Hong**: But it doesn't need to even go through like in terms of, you know, the solve everything like obviously stands like my point is like transfer learning doesn't like transfer learning is about like pushing math math reasoning. Just so so there are kind of I guess like there a couple narratives here like for some people it's like you you solve math and then maths are the, you know, fundamentals of sciences so that's actually the from AI for math like take this radical layer of AI for science is that narrative we actually believe in just like general transfer learning like I think **Axiom** is **Axiom** is on the infrastructure stack.

</details>

**Brandon Anderson**: 你认为这只是第一步，基本上可以解锁科学和法律等许多领域的能力。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And you think that this is just a first step to you know, basically unlocking capabilities in many domains in science and law for example.

</details>

**Carina Hong**: 是的。我，我，我认为这是，所以，再次，有很多种信念。一种信念是，有数学，有，你知道，形式化验证的力量。假设我们真的，你知道，解决了数学问题，并且有一个非常强大的非形式化数学推理引擎。我们不期望那个术语像通过形式化方式解决数学问题那样大。

<details>
<summary>Original English</summary>

**Carina Hong**: Yes. I I think it's so so again there are like, you know, multiple multiple kind of like beliefs. One belief is that there's math and there is like, you know, formal the power **formal verification**. Suppose we actually, you know, solve math and have a really strong informal math reasoning engine. We do not expect that term to be as large as solving math through the formal way.

</details>

**Brandon Anderson**: 为什么？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Why?

</details>

**Carina Hong**: 我的意思是，代码作为一种语言，它确实更具结构性。

<details>
<summary>Original English</summary>

**Carina Hong**: I mean code as as it is language but it is indeed on the more structured end.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes.

</details>

**Carina Hong**: 它连接了非形式化和形式化。

<details>
<summary>Original English</summary>

**Carina Hong**: It bridges informal and formal.

</details>

**Brandon Anderson**: 是的。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yes.

</details>

**Carina Hong**: 我们正在做的是，它不是非形式化与形式化，对吧？我们没有采取那种完全形式化的证明方法，它是在非形式化和形式化之间架起桥梁。它是在高层次和低层次之间架起桥梁。它是一种通过推理直接改进，通过迁移学习，它也是间接的，因为，好吧，数学将解锁一点科学，当然，那就是我们真正看到的。

<details>
<summary>Original English</summary>

**Carina Hong**: What we are doing is it's not informal versus formal right. We're not taking the sort of like completely formal of a proof approach like it's in it's bridging between informal and formal. It is bridging between high level and low level. It is a direct sort of like a direct improvement through reasoning um through trans like transfer learning and it's also indirect in that like okay well like math is going to unlock little science and sure um and that is really what we're seeing.

</details>

**Brandon Anderson**: 所以你认为它能够实现迁移学习？

<details>
<summary>Original English</summary>

**Brandon Anderson**: So you think that it enables transfer learning?

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah,

</details>

**Brandon Anderson**: 我明白了。

<details>
<summary>Original English</summary>

**Brandon Anderson**: I see.

</details>

**Carina Hong**: 我认为那是一个共识。

<details>
<summary>Original English</summary>

**Carina Hong**: I think that is that is pretty much a consensus.

</details>

**Carina Hong**: 我认为这是一个共识，这是一个被其他人忽视的赌注，因为数学听起来很纯粹，听起来没有商业价值。

<details>
<summary>Original English</summary>

**Carina Hong**: I think it is a consensus and this is a bet that has been pretty much kind of overlooked by others because math sounds pure and it doesn't sound like there's any commercial value. Mhm.

</details>

**Carina Hong**: 嗯，我当然理解机会成本，如果你是一个前沿实验室，解决这个问题会有机会成本，但我绝对认为这是一个问题，如果你是一个资源充足的初创公司，你应该做。

<details>
<summary>Original English</summary>

**Carina Hong**: Well, I do obviously understand the opportunity like the opportunity cost if you're like a really like a frontier lab of of solving this problem, but I definitely think this is a problem that if you're like a well resource startup, you should be doing.

</details>

**Brandon Anderson**: 这是一个有趣的视角。你把所有想说的都说完了吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: That's an interesting Yeah. perspective. Did you get everything out that you wanted?

</details>

**Carina Hong**: 是的，我认为，你知道，问题是数学还是验证？公司的DNA是数学。我们认为验证是最好的首选市场。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think I think it's um like, you know, like the question of like is math or is verification? The DNA of the company is math. We think best like verification is the best first market.

</details>

**Carina Hong**: 是的。我们认为解决数学问题，特别是形式化数学，将帮助我们应对**验证AI**的真正雄心勃勃的追求。现在当我们完成这项工作后，我们可能会有其他第二市场，包括我们刚刚谈到的AI for Science，但那是在理论层面，对吧？我认为现实世界的测试很重要，而且我们潜在地可以留在数字世界和软件领域，而其他事情则需要获得奖励，比如物理世界的信号。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. And we think that sort of like solving math and especially like formal math um is going to like help us like tackle the really ambitious quest of **verified AI**. Now when we are done with that we might have other that second markets including a for science we just talked about but but on the theoretical layer right like I think real world testing is important and potentially we can stay in the digital world and soft software stuff and for other things to be to be to be getting reward like physical word signals.

</details>

**Brandon Anderson**: 但你认为那种进行真正强大推理的能力。

<details>
<summary>Original English</summary>

**Brandon Anderson**: But do you think that that that the sort of the capability of doing really powerful reasoning.

</details>

**Brandon Anderson**: 一旦你拥有了那个强大的**验证推理引擎**，那就是“好吧，现在我们已经为软件验证和硬件或其他任何东西解锁了它，但现在生物学呢？化学呢？”

<details>
<summary>Original English</summary>

**Brandon Anderson**: Once you have that powerful **verified reasoning engine** that that's the moment when okay now we've unlocked that for, you know, software verification and hardware or whatever but okay so now what about biology what about chemistry.

</details>

**Carina Hong**: 所以那可能是一个，然后另一个是，你离递归自我改进还有多远？

<details>
<summary>Original English</summary>

**Carina Hong**: So that could be one then the other one is then like really how far are you to recursive self-improvement.

</details>

**Brandon Anderson**: 好的，所以就是通用人工智能（AGI）。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Okay, so just AGI.

</details>

**Carina Hong**: 是的，我认为有这样一个问题，不同的人因为他们可能不同的背景有不同的，这真的取决于你的能量和你的热情引导你去哪里。例如，对于一些人来说，我确实听过这个，你知道，我的朋友们，他们想研究通用人工智能（AGI），因为他们相信解决AGI就能解决死亡。还有一些人来自医学背景，他们真的相信他们可以解决死亡，他们不解决AGI，然后解决死亡。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think there is this sort of question and different people because of their probably different backgrounds have different um it's it's really where your energy and your passion leads you like for some people actually I have heard this actually, you know, with my friends they want to work on AGI because they believe solve AGI solve death there are other people who come from a more like medicine background they really believe they can solve death and they don't solve AGI and then solve death.

</details>

**Brandon Anderson**: 他们只是解决AI for Science。

<details>
<summary>Original English</summary>

**Brandon Anderson**: They just solve like AI for science.

</details>

**Carina Hong**: 现在哪种方式是正确的？我不知道。

<details>
<summary>Original English</summary>

**Carina Hong**: Now which way is correct I don't know.

</details>

**Brandon Anderson**: 所以递归自我改进的角度，听起来你是在说，验证加上那种非形式化的语言，正是这种组合能够实现真正良好的递归。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And so the recursive self-improvement angle it sounds to me like you're saying that the combination of verification plus the sort of like language which is informal. It's that combination that enables really good recursive.

</details>

**Carina Hong**: 我认为递归自我改进无论如何都会发生。我们正在努力让形式化验证占据一席之地。所以我们，我们，再次，形式化验证能否被接受、部署并成为共识，取决于我们执行得有多好。我认为当你把这个问题归结为一个执行问题时，你就应该去做。

<details>
<summary>Original English</summary>

**Carina Hong**: I think recursive self-improvement is going to happen anyways. We're trying to have like **formal verification** earnest place. So we we like again the whether um **formal verification** can be welcomed and deployed and become a consensus depends on how well we execute and I think when you boil down that problem into an execution problem, you should just go for it.

</details>

### AI for Math领域的瓶颈

**Brandon Anderson**: 展望未来，你认为该领域，无论是**Axiom**还是整个领域，最大的瓶颈是什么？

<details>
<summary>Original English</summary>

**Brandon Anderson**: What looking forward what's the biggest bottleneck that you see in the field for both atom and maybe just the field abroad in terms of.

</details>

**Carina Hong**: 嗯，碎片化。所以，我认为我们正处于一个市场，人们喜欢开始，你知道，一千个人，他们不联合起来，他们开始一千件事。我认为这实际上是最大的泡沫指标。我认为有分类泡沫，还有其他类别，那里有登月计划，那不是泡沫，它只是看起来有点泡沫。如果那些真正有合法背景的人决定联合起来，为一个使命而不是为了自我，为了新实验室创始人的地位而工作，我认为这些类别我非常看好，反之亦然。所以我认为瓶颈实际上是关于潜在的，我认为这很烦人，因为如果，如果你相信我们正处于一个研究时代，如果你相信深度技术是值得追求的有趣方向，那么市场条件目前有好有坏。好的一面是它使得这些长期、长远押注能够获得资金，坏的一面是市场噪音太多，还有一些非理性玩家。嗯，你知道，我们努力与真正令人难以置信的风险投资公司合作，他们是我们的合作伙伴。他们是我们的知识合作伙伴，有很多共识，我们真的会长时间地互相交流非常酷的技术和非技术想法，而且，你知道，我们花了很多下班时间和周末一起，真正投入地建设公司。还有一些人只是想把资金停泊在某个地方，你知道，虽然我们不与他们合作，但这些市场条件鼓励碎片化，当事情变得碎片化时，没有人能达到目标。我认为每个类别，无论其想法多么正确，都处于一种赢得生存权的阶段。如果情况是这样，那么，例如，伟大的深度技术公司**SpaceX**，人们确实联合起来为那个梦想工作，在这种情况下，可能还有一个非常有魅力的创始人。我认为对我个人来说，一个真正令人担忧的事情是，对于其他一些我个人非常看好的类别，他们的行动，以及普遍看待事物，碎片化是一个问题。比如，我们看到停止从大学拉教授来做一些事情，这确实是一个非常有趣的局面。

<details>
<summary>Original English</summary>

**Carina Hong**: Uh fragmentation so um I think we're in a market where people like to start like, you know, a thousand people they don't join force they start a thousand things I think that's actually the biggest like kind of bubble indicator I think there are categorical bubble and there are like other categories where there are moonshots it's not bubble it just looks a little bubbly in the field if people who are like really like of really legit, you know, backgrounds decides to join force and work in a team for the mission rather than for ego for kind of the status new lab founder. I think that categories I'm I'm really bullish other and vice versa. So I think the bottleneck actually is about potentially I think I think it's it's it's annoying because it's like we are in a if if you believe we are in a in an age of um research if you believe in like deep tax are the interesting directions to go after um the market sort of conditions currently is good and bad and that good it enables these sort of long-term long horizon bets to be funded bad because there's too much noise in the market and some other like irrational players. Um, you know, we we try to work with really incredible venture firms like they are the partners. They are our intellectual partners and there's a lot of alignment and we really bounce like very uh cool ideas technical and non-technical each other like for long long hours and and, you know, we spend like a lot of time off work and weekend together to really intensely build the company. There are also other people who just want to like park like capital somewhere and, you know, while we don't work with them these encourage these are market conditions that encourage fragmentation and when things get fragmented like no one gets there like I think every category regardless of how how right the idea is it's pretty much in a sort of earning the right to exist stage and if that is the case then um and for example great DTAC company **SpaceX** and people do actually join force to work on that dream and potentially in that case also a very charismatic founder. I think a really kind of concerning thing for me personally is that for other probably some categories that I'm personally quite bullish about their action about and just like looking at things generally fragmentation is a problem like the sort of, you know, we see stop pulling professors from university to um work on something when it really it really is a really interesting kind of situation.

</details>

**Brandon Anderson**: 也许这是一个天真的问题，但就像现在，当你谈论AI for Math领域的参与者时，比如你们**Harmonic**，然后是那些大实验室，我有没有遗漏什么人？它真的碎片化了吗？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Maybe this is a naive naive question, but like right now when you were talking about players in let's say AI for math where, you know, you **Harmonic** yeah and then, you know, the big labs right am I missing someone is like is that actually fragmented really?

</details>

**Carina Hong**: 我猜碎片化是整个AI领域的瓶颈。

<details>
<summary>Original English</summary>

**Carina Hong**: I guess fragmentation I think is a bottleneck for the entire like AI landscape.

</details>

**Brandon Anderson**: 好的。是的。我认为AI for Math是一个实际上不是泡沫的类别，因为它没有碎片化，因为那些真正有才华的人确实喜欢联合起来。所以，例如，能够让**K. Can Uno**和**Fr Charton**在一个团队中，这太棒了。你有一个核心贡献者，前沿数学的第四层，一个非常棒的基准测试制定者**Francis**，他在AI for Math Discovery方面有证明和发现，他们一起工作，那么你突然就成为了一个既有证明能力又有构建能力的玩家，这太棒了。我相信，你知道，就像你说的，**Harmonic**可能也有一些真正优秀的人才联合起来。我认为AI for Math是一个很好的类别，因为它没有碎片化，但即使从我们的角度来看，例如，强化学习，我不知道那是否算是一个类别，但你知道，强化学习人才目前很难吸引和留住，对于每个人来说都是如此，而且有很多公司成立后三个月就被出售了，每个月你本可以专注于一个技术问题，却在忙于交易，那是一个被浪费的月份，我这么说也是带着一些痛苦和煎熬，因为经历了两次融资。是的。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. Yeah. I think AI for math is a category that is actually not a bubble because it is not fragmented because people who are really amazing talents do like to join force. So for example the fact to get **K. Can Uno** and **Fr Charton** on one team like this is fantastic like you have someone who's a core contributor Frontier math tier 4 really great benchmark setter **Francis** who's on the AI for mass discovery have proving and discovery they work together then you are suddenly a player with both proven capability and construction capability and that's fantastic and I believe, you know, as you said like **Harmonic** probably also have some really great talents like joining force together I think afro mass is a is a good category because of the absence of fragmentation but even, you know, from from our perspective the sort of for example um, you know, RL right being I don't I don't think that's like a category per se but, you know, RL talents currently um it's quite hard to to attract and retain right for for literally everyone and there are a lot of um companies being started then sold like three months later and and just the the each month where you could have worked on a technical problem and you're instead working on deals It's a month that is wasted and I say that like, you know, also with some amount of pain and suffering because of having having gone through two fundraises. Yes. Yes.

</details>

**Brandon Anderson**: 是的。所以，AI for Math最大的瓶颈是什么？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. So so what's the biggest bottleneck in AI for math.

</details>

**Brandon Anderson**: 不是**Axiom**，而是整个社区。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Not **Axiom** but just the community.

</details>

**Carina Hong**: AI for Math社区。

<details>
<summary>Original English</summary>

**Carina Hong**: The community of AI for math.

</details>

**Brandon Anderson**: 是的。它走向何方？每个人都真正想打破的是什么？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah. Where is it going? What is the thing that everyone just really wants to break?

</details>

**Carina Hong**: 我预计随着**Axiom**和**Harmonic**确立类别领导地位，碎片化将开始发生。

<details>
<summary>Original English</summary>

**Carina Hong**: I expect fragmentation to start to happen as **Axiom** and **Harmonic** establish category leadership.

</details>

**Brandon Anderson**: 嗯。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Mhm.

</details>

**Carina Hong**: 所以我预计人们会，你知道，那是一回事，但我也认为另一个瓶颈可能是短期与长期的压力。我认为我们正在以非常快速的方式做事。但这并不意味着我们总是可以，或者说总是正确地以最快的方式做事。比如，我们以快速的方式做事，因为我们是在国际数学奥林匹克竞赛那天成立的，所以我们无论如何都无法参加那次比赛。下一次数学奥林匹克竞赛是**Pudnam**，我们非常兴奋，因为我的意思是，那是本科生考试，今年的**IMO25** **IMO**在MOHS量表上很容易，而**Pudnam**可能很难，事实上它比**IMO**更难，如果你看AI在MOHS量表上平均和最大保留了多少分数，以及问题的难度。**Pudnam**在两个轴上都更难。所以我们想尝试，所以只有四个月的差距，但这并不意味着我总是会设定四个月的目标。如果我只设定四个月的目标来建立一家公司，我可能会建立一家非常短视的公司。所以，我认为有更长远的问题。例如，市场力量可能会迫使其他玩家进行三方验证。嗯，有可能联合验证是圣杯。有可能如果你解决了那个问题，那么你也会自然地解决三方验证，带有一些分布偏移的epsilon警告，但我坚信，瓶颈可能是压力，但我认为**Axiom**很幸运，我们足够早，我们是一个由非常高能动性的人组成的团队，我们的执行力通常超出预期，但我认为，我认为AI for Math整个领域的瓶颈可能是，试图证明商业价值会显著分散核心能力提升的注意力。

<details>
<summary>Original English</summary>

**Carina Hong**: So I expect people kind of, you know, that that's one thing, but I also think that another bottleneck could be the pressure of short-term versus long-term. I think that we are doing things in a very sort of fastpaced manner. But that does not mean we can always or it does not mean it is always correct to do things in the most fast-paced manner. Like we did things in a fast-paced manner because well we were founded on the day of international mass olympia so we couldn't have competed in that anyway the next mass Olympia is **Pudnam** and we're quite excited because it's I mean it's undergraduate exam and this year's **IMO25** **IMO** was easy on the MOHS scale and **Pudnam** could be hard and in fact it was harder than the **IMO** and the MOHS scale if you look at the AI um, you know, how much how many scores the AI uh has has retained on average and on the max you difficulty of the problem. **Pudnam** is harder in both both axis. Um, so we want want to try and so there's only a gap of four months but it doesn't it doesn't mean I'm always going to set four months goals. If I build a company only setting four months goals I I might build a really short-sighted company. So there are like I think longer horizon problem. I think for example market forces could force other players into trip verification. Well it is possible that co-verification is a holy grail. It's possible that if you solve that then you also naturally solve trip verification with some amount of like epsilon caveat of like distribution shift but I strongly believe that like a bottleneck like could be the pressure but I think that **Axiom** is fortunate that when we are early enough to we are like a team of just incredibly like um high agency people that our execution generally surpasses expectation but I think like what I think could be a bottleneck for the entire aformat field is that potentially trying to prove commercial value is going to distract significantly from the core capability improvement.

</details>

**Brandon Anderson**: 是的，这很有道理。酷。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah, that makes sense. Cool.

</details>

**Brandon Anderson**: 谢谢你开车过来见我们。我知道交通很糟糕。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Thank you for driving up and coming to see us. I know the traffic was was horrible.

</details>

**Carina Hong**: 是的，谢谢你。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, thank you.

</details>

**Brandon Anderson**: 而且，嗯，很高兴和你交谈，我们期待看到事情如何发展。

<details>
<summary>Original English</summary>

**Brandon Anderson**: And and um it's been really a pleasure speaking with you and um we look forward to to seeing how things develop.

</details>

**Carina Hong**: 是的。非常感谢。谢谢你。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Thank you so much. Thank you. Yeah.

</details>