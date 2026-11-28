---
author: AI Engineer
date: '2026-11-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1S4hx3wgvBE
speaker: AI Engineer
tags:
  - software-factory
  - brownfield-development
  - demand-factory
  - ai-agents
  - product-management
title: 建立软件工厂与需求工厂：基于棕地开发的策略
summary: Justin McCarthy 分享了在 Diffusion 构建“软件工厂”的经验，强调在已有产品（棕地）中通过循环和承诺来维持系统稳定性。他提出应区分产品市场契合度探索与现有系统维护，并倡导建立“需求工厂”来匹配生产系统速率，通过 AI 代理协助识别市场需求并扩展品牌边界。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Diffusion
products_models:
  - Claude 4
  - GPT-5
  - Codex
  - Bun
  - Cloud Code
media_books: []
status: evergreen
---
## 开场与软件工厂的起源

>> 大家好，我叫 Justin McCarthy，是 Diffusion 的创始人兼首席执行官，我们致力于将模型的能力扩散到全球经济中。外面的世界很大，有 100 万亿美元的经济体量，有 80 亿人口，所以有很多事要做。这就是我们正在做的事情。我们实现这一目标的方式之一，就是建造软件工厂。其实这场演讲，虽然名字里带了“工厂”这个词，但不会太偏技术。最后会有一个二维码，里面有一些技术资料供大家参考，所以我鼓励大家自己去拿，或者让你们的 agent 去获取。我最近经常发送双通道信息，在上面讲给人类听的内容，然后在下面附带一些给 agent 的东西。这场演讲也差不多是这样。我会给你们讲人类听的内容，然后你们的 agent 会在最后获取 agent 通道的内容。

<details><summary>Original English</summary>
[music]
>> All right, my name is Justin McCarthy. I'm the founder and CEO at Diffusion, and we are diffusing the capabilities of the model into the global economy. Uh it's a big place out there. There's $100 trillion of it. There's 8 billion of us, so there's a lot to do. Um uh and that's that's what we're doing. And one way we're doing it is by building software factories. Um this talk actually, you know, uh I don't I I guess it's got the factory thing in the name. Um uh this it's not going to be super technical. There's a QR code at the end that is going to have some technical stuff for you, so I would encourage you to pick up or have your agents pick things up. Uh I'm sending a lot of dual channel messages these days where I say the human stuff up here, and then I attach something for the agent down there. So that's kind of this presentation. I'm going to say human things to you, and then your agents are going to pick up the agent channel stuff at the end.
</details>

对我来说，这一切始于去年 7 月。当时我们在使用 Claude 4 系列模型，我有幸能够非常深入地研究，并真正去探究当你开始让这些东西循环运行起来时会发生什么。这就是我与团队一起建造的软件工厂的开端故事。我要说的是，即使在 4 系列模型上，甚至在我们还在等待 GPT-5 和最初的 Codex harness 的时候，即便在那个时候，我们也能看到这东西将会奏效的微光，但代价是巨大的 token 消耗，而且只有在真正像 Rube Goldberg 装置那样复杂拼凑的情况下才能实现。也就是说，只有当这些循环被非常粗糙地拼凑在一起、非常手工地打造出来时，你才能看到这些微光——某种能够稳定输入的输出，从而带来我们最终想要的那种可靠性。

<details><summary>Original English</summary>
Um okay. So uh so this started for me uh in July of last year. Uh we were on the Claude 4 series of models, and um you know, I had the privilege of being able to dive very, very deep um uh and really ask what happens uh when you begin looping these things. Um so that uh was the story of the beginning of the software factory that I built um together with uh the team. And I'll say that, you know, even on the 4 series of models, uh even as we were awaiting GPT-5 and the initial Codex harness, um you know, even then we could see glimmers that this thing was going to work, but at tremendous token expense and only in the presence of a real Rube Goldberg contraption. Okay? So only when the loops were very duct taped together um and and very sort of um hand crafted uh would you be able to see these glimmers of some kind of an output that would stabilize the input that would lead to the kinds of reliability um that we would ultimately okay?
</details>

所以我想说的是，这种感觉——如果你从本次大会上关于软件工厂的演讲数量来判断——我想这种感觉就是我们现在所知的“软件工厂”，而且时代精神中某种程度上已经接受了这样一个事实：至少其中一部分现在就这么自然发生了，实现它所需的我们的创造力和投入也大大减少了。

<details><summary>Original English</summary>
So I'll just say that feeling um if you judge from the number of software factory talks that have been present here um at the conference, that feeling um I think is what we know now as software factories and it's sort of accepted in the zeitgeist that at least some part of this um just kind of happens now and it requires substantially less of our creativity and input to achieve.
</details>

## 区分绿地与棕地：何时该建造工厂

所以，这当然也是我该说“请停止建造软件工厂”的时候了，对吧？我在这里显然带有一点调侃的意味，但同时也是认真的。我认为你们真的应该停止把你们的想法、抱负和目标都交给工厂流程去处理，因为大多数时候我们并不知道自己想要什么，或者至少在很多时候，当我们创造新事物时，我们还不知道自己想要什么。如果我们试图把一件连自己都不知道想要什么的事情工业化，我们肯定得不到正确的东西，或者会花太长时间，或者会花太多钱，结果会在很多方面都很糟糕。

<details><summary>Original English</summary>
So that's of course the time for me to say please stop building software factories, right? Um so uh so I and I and I'm I'm you know obviously you know a little bit tongue in cheek here but um but also serious uh uh I think you really should stop uh subjecting your ideas and your ambitions and your goals uh to a factory process um you know because most of the time we don't know what we want or at least a lot of the time we're creating something new we don't yet know what we want. And if we're trying to industrialize something where we don't know what we want um uh we're certainly we're not going to get the right thing or we're going to take too long or we're going to spend too much um we're going to have all it's going to be sad in multiple ways, okay?
</details>

所以我想说的是，让我们开始运用一些辨别力，判断我们是在探索产品市场契合度（product market fit）、开辟新天地、征服新领域，还是在做一件已经有先例并且已经在运转的事情。这种关于我们处于哪种工作模式的辨别力，我觉得非常有用，因为棕地（brownfield）工厂的绝妙之处在于，它是我们已经能从中获得报酬的东西。客户正在用他们的美元和他们的使用量说：“对，这对我有用，我喜欢它，我想要更多。”它是那些维持运转、支付账单、让客户满意的现有事物，你不需要去探索关于它的任何东西，因为为了循环维持该系统稳定性而需要知道的一切，都已经内置在运行时（runtime）中了。所以正在发生的一切、客户使用它的所有方式、他们对它的所有评价，甚至可能包括客服工单，都在强化你在那片棕地中所拥有的一切的完整性、生命力和实用性。

<details><summary>Original English</summary>
Um so what I would say is uh let's begin to use some discernment about whether we're discovering product market fit, we're breaking new ground, we're conquering new territory, or whether we are doing something that you know already has a precedent and is already working, okay? Um and that discernment about sort of what way what mode we're working in um uh you know I I find it really helpful um because uh the great thing about a brownfield factory is it's something that we're already being paid for. It's something where customers are saying with their dollars and their uh and their utilization like yeah this works for me I like it I want more of this, okay? Um it's the existing things that keeping the lights on paying the bills keeping keeping customers happy um and you don't need to discover anything about it because everything you need to know to loop the stability of that system is is just built into the runtime, okay? So everything that's happening all the ways your customers are using it everything they're saying about it, maybe even the support tickets, those are reinforcing um the integrity and the vitality and the utility of whatever you've got in that brownfield, okay?
</details>

当然我们接下来也会谈到这一点，但另一个令人兴奋的事情是，正如我们从其他许多演讲者那里听到的——Jared 刚才全都在讲重写 Bun 和 Cloud Code——你当然可以重写很多这样的棕地代码。于是，所有那些技术债务，所有那些历史上拖慢我们速度的沉重包袱，所有那些长得离谱的待办事项列表（backlog），我们现在可以看到它们正在逐渐消退，而且我们不需要花太多精力去问客户想要什么，因为客户每天都会来，他们就在用行动说：“我正在用的就是我想要的。”

<details><summary>Original English</summary>
And then of course we're going to talk about this, but um uh the another exciting thing as we heard from many of our other speakers um uh you know Jared just uh talked all about rewriting uh Bun um and and Cloud Code. Um you can rewrite a lot of that brownfield of course, okay? So this becomes all of that technical debt, all those sort of boat anchors that are slowing us down historically, um uh all that you know impossibly long backlog um we can see those drying up now um and we don't have to spend uh much energy asking what the customer wants because the customer is arriving every day and they're saying what I'm using is what I want.
</details>

## 棕地工厂的核心属性：承诺、循环与持续性

好，所以我们知道要建造什么。我们建造现有的东西。关于如何思考与你的棕地打交道、清理它并让它自我维持，有几点笔记。在 Diffusion，我们使用“承诺（promise）”这个词来代表产品中我们所珍视的某种保证、某个方面、某个优先级和某个维度。功能是一个承诺，某样东西的成本和价格是一个承诺，某样东西的安全性是一个承诺。而且你很少会想要在自己的承诺上倒退和退化。因此，如果你能开始讨论我们对现有产品有哪些期望，你就可以开始把这些期望编码到循环中。而一个循环，就像我们一直在讨论的任何工厂方案一样，无论是用 YAML 文件、Python 还是图（graph）来表示，循环的特点在于它以某种方式接收一个输入和一个输出，然后以某种方式将其反馈回去。正如你们许多人所知，这就是放大器的理想化框图，如果你切断了那条反馈支路，你只会放大噪声。我想我们现在都有这种感觉了，因为我们一直在使用软件工厂和循环。必须有某种方法将那种保真度反馈到系统的输入中，但如果你这样做了并且调校得当，它就能奏效。所以这就是我们应该努力追求的，尤其是在棕地中。我们正在获得所需的所有信号，来修复、稳定和改进这些循环。

<details><summary>Original English</summary>
Okay, so um so we know what to build. We build the we build the existing thing. Uh and a couple of uh a couple of notes about just ways of thinking about working with your brownfield and you know cleaning it up and making it self-sustaining. Um uh at Diffusion we use the word promise um to represent you know some guarantee, some aspect, some priority, and some dimension within the product that we value, okay? Feature is a promise, um you know the cost and price of a thing is a promise, um the security of a thing is a promise. Um and it's rare that you want to revert and regress on your promises, okay? Um uh so if you can start talking about the ways that we have expectations that are against an existing product um you can begin to encode those in loops, okay? And a loop just like any of the factory schemes we've been discussing, whether represented in a YAML file or some Python or graph um you know a loop has the characteristic of somehow uh taking an input ha and an output and then somehow feeding it back, okay? As many of you know this is the sort of idealized uh block diagram of an amplifier, and if you cut that feedback leg, you're just going to amplify noise, okay? And um I think we all have this feeling now that we've been working with software factories and working with loops. Um there has to be some way of feeding back that fidelity into the input of the system, but if you do it and you tune it right, it can work, right? Um so uh so this is what we should strive for, especially in a brown field. We're getting all the signal we need to cure, stabilize, and improve those loops.
</details>

棕地工厂的下一个属性是，它真的应该是持续的（continuous）。如果你回顾过去提交（commits）到达的历史，那些提交是有某种季节性规律的。会有每日和每小时的季节性规律，会有每周的周期，你会看到这些提交每隔一段时间出现一次。现在它可以持续不断地发生了。当你的循环由工厂里的 agent 维护时，我不知道，它可能看起来像一条直线——就是一连串 24/7 全天候持续进行的活动，因为总有值得担心的事情。它是不是有点慢？它是不是有点不安全？它是不是有点这样那样的问题？所有这些担忧都是全天候存在的，如果你以正确的方式建造你的棕地工厂，它应该兼容持续智能（continuous intelligence），兼容对这个问题的持续应用，而且它就应该这样一直运行下去。所以你有一个现有的代码状态，你有一套现有的承诺，只需让它持续运行、让它循环、让它信守这些承诺。换句话说，我的棕地工厂基于一套现有的承诺，它就应该是持续的、在后台运行的，并且为我信守这些承诺。因此，我强烈主张建造这样一个系统，它将为你提供自由和创造力，让你开始思考在绿地（greenfield）中应该做什么——在绿地中，可能不需要同样程度的循环严谨性，而是需要更多真正用于探索产品市场契合度的精力。

<details><summary>Original English</summary>
The next attribute of a brown field factory is, you know, it really should be continuous. If you look at uh the history in the before times of when commits would arrive, there was some seasonality to those commits. There would be a daily and hourly seasonality. There'd be a weekly cycle, and you would see those commits come in at intervals. It can happen continuously now. When your loops are being maintained by your agents in a factory, I don't know, like it might look like a straight line. Uh just uh just a solid list of activity that's happening 24/7 because there's always something to worry about. Um is it a little bit slow? Is it a little bit insecure? Is it a little bit whatever? Um all of those worries apply around the clock, and if you're building your brown brown brown field factory the right way, um it should be it should be compatible with continuous intelligence, continuous application of this question, um and and it should just run, okay? So you've got an existing code state, you've got an existing set of promises, um just make it continuous, make it loop, and make it keep those promises, okay? So so another way to summarize that is, you know, my brown field factory on an existing set of promises, it should just be continuous, it should be background, and should be keeping those promises for me. Okay? So uh so I'm a strong advocate of building a system like this, um and it's going to give you the freedom and the creativity to begin asking what you should be doing in the greenfield, you know, probably not with the same level of looping rigor, probably with more true product market fit and discovery sort of energy, okay?
</details>

## 随时间简化与“相同但更快”

还有一个非常迷人的特性。这绝对是我在过去一年里亲身经历过的。我早些时候提到过，一年前，它能工作，但需要大量的组件。让它运转起来在很大程度上仍然是一项工程挑战。正如我们从 Zach 和 Potato 等人那里听到的，这些系统正在变得稍微容易一些，这很大程度上要归功于模型本身以及 harnesses。但你可以从你的工厂中期待的一件事是，它会随着时间的推移而简化。这是我们在自己的 skills 中已经看到的现象。当然，skills 正在变得越来越短。harnesses 正在变得越来越通用。而这在很大程度上同样归功于模型本身。

<details><summary>Original English</summary>
All right. One other really fascinating property. Um, this is certainly something that I've experienced uh over the last year. I mentioned earlier, you know, a year ago, um it would work, but there was a lot of componentry. Okay, getting it getting it to work was still very much engineering. Um, as we heard from some others from Zach and from Potato, um these systems are they're getting a little bit easier and a lot of credit goes to the model itself, um as well as the harnesses. But one thing you can expect from your factory um is that it is going to simplify over time. Okay? Um, this is something that we've seen in our skills. The skills are getting shorter, of course. The harnesses are getting more general, of course. Um, and a lot of this again is credit um uh to the models themselves.
</details>

我想指出，有一家著名的 AI 公司也制造这些小玩意儿。这算是一个挺著名的演进过程。那家 AI 公司的 Raptor 1 发动机非常繁琐精密，但它能用。它看起来就是这样，有很多管子，但它确实推动了火箭。在同样大小的封装里——大致相同的外部尺寸下——第二个版本拥有更高的性能和更少的活动部件。这一个和这一个之间的差异，是智慧的巨大投入——字面意义上的火箭科学家和工程师们专注于“我们怎样才能把这个东西做得更简单”。要知道，这很难。很难找到那些人，也很难让他们把精力集中在一个难题上。当然，我们在这种简化过程中拥有强大的盟友，因为我们有 Astra、Fable 和 Carbon，对吧？他们正试图把我们的工厂从第 1 版带到第 2 版再到第 3 版，这样等到我们周一回来开始工作的时候，也许我们的工厂就已经比刚开始时简单得多了，对吧？或者我们再等一个模型版本，我们的工厂就会拥有更少的活动部件，却有两倍的性能。所以这是当下这个时代一个非常有趣的特征，以前从未存在过。因此，如果你现在勉强能让这东西运转起来，你可以期待很快就能看到更顺畅的层流、更高的性能，而这期间不需要你投入太多创造性的贡献。

<details><summary>Original English</summary>
Um, I'll note that uh there's a uh there's a famous AI company um that also makes these widgets. Um, and this is kind of a famous uh progression. So the Raptor 1 engine from that AI company um uh was really fiddly, but it worked. Okay? Uh it looked like this. There were a lot of tubes, but it definitely propelled the rocket. Okay? In that same package, right, that same approximate external dimension, the second version had higher performance and fewer moving parts. Okay? The delta between this one and this one was a tremendous application of intelligence, okay? Like literal rocket scientists and engineers focusing on how can we make this thing simpler. Okay? Um, you know, that's hard. It's hard to get those people and it's hard to concentrate them on a difficult problem. Um, we have tremendous allies in this simplification, of course, because we have Astra and Fable and Carbon, right? And so they are trying to take our factory from version 1 to 2 to 3 so that by the time, you know, we come back we come back and, you know, start our jobs on Monday or whatever, um maybe we have a much simpler factory than when we started, right? Or we wait one more uh model version and our factory is has fewer moving parts yet twice the performance. Okay? So this is a really interesting feature of this moment that hasn't existed before. So if you can just barely get the thing to work, you can expect uh uh a smoother laminar flow, higher performance, you know, soon, okay? Without much of your creative contribution in between.
</details>

好。那么我们来建造一个棕地工厂吧。给这个工厂一个绝佳的指令是：“相同，但更快”。我很少参加过有人争论是否要提高系统性能的会议，对吧？只要你处于某种帕累托均衡（Pareto equilibrium）中——你没有用更便宜去换更快，或者用更快去换更安全——那么这就绝对是好事。所以它应该更快、更便宜、更安全。注意，有时我们会把“更好”也加进这个组合里，而在棕地工厂中，“更好”可能很难实现。“更好”可能涉及更多你的意图，“更好”可能涉及更多你的判断力和品味。所以也许在那个地方，你需要进入探索阶段并使用不同的技术。但是天哪，更快、更便宜、更安全——尤其是在 vold apocalypse 的另一边……抱歉，不是另一边，我们仍处于 vold apocalypse 的开端。我们绝对需要这些东西自主地变得更安全，对吧？所以你应该拥有它。

<details><summary>Original English</summary>
Okay. So uh let's make a brownfield factory. Um uh a great instruction to give that factory is the same but faster. Um I've been in very few meetings where someone debated uh you know increasing the performance of a system, right? Um as long as you are at some sort of a Pareto equilibrium where you're not trading faster for cheaper or trading safer for faster, okay? Then this is just good. Okay? So uh so it should be faster, it should be cheaper, it should be safer. Um note that sometimes we include better in this mix and better may be difficult to achieve in a brown in a brownfield factory. Better may involve more of your intent, better may involve more of your judgment and taste. Um so maybe that's where you go into discovery and use different techniques. But gosh, faster, cheaper, safer, um especially on the other side of the vold apocalypse. Sorry, other side, still at the beginning of the vold apocalypse. Like we we definitely need these things to just autonomously get safer, right? Okay. So you should have that.
</details>

所以我认为每个人都应该拥有棕地工厂。你应该用它来履行你现有的承诺。你应该拥有它，而且随着时间的推移，它应该变得更好、更快、更便宜。我发现这大概需要一周时间。所以如果你还没有花这一周时间，现在就去做吧。就像你回家后，去花上一周时间，就说你下周休假，然后把你的棕地工厂围绕你所有的现有承诺搭建起来。如果你没有办法做到这一点，或者你觉得需要帮助，随时可以联系我，我们随时待命提供帮助。

<details><summary>Original English</summary>
Okay. So um so I think everyone should have the brownfield factory. You should have it for your existing commitments. You should have it. It should become better, faster, and cheaper over time. Um I find that this takes like a week. So if you haven't spent that week yet, just do it. Just like whenever you get home, like go go spend a week, uh say you're on vacation next week and just stand up your brownfield factory on all all your existing commitments. Um if you don't have a way to do that or you feel like you need help, you can always reach out to me and uh we're standing by to help.
</details>

## 提升野心：建造需求工厂

所以棕地工厂，你们应该去做，但它也太容易了。拜托，太容易了。你们还需要提升自己的野心。在剩下的几分钟里，我们要谈谈如何提升我们的野心。

<details><summary>Original English</summary>
Um so brownfield factories, you should do them, but also too easy. Okay? Like, come on, too easy. Okay? Um, uh, you need you need to elevate your ambition as well. Okay? So in my remaining couple minutes here, um, we're going to talk about how to elevate our ambition.
</details>

我认为我们大家此刻都在挣扎的一件事是：天哪，现在产出的代码太多了。更糟的是，它还能正常运行。产出太多了，也许太多过头了。我们可能面临着产出过剩。而且很可能是，我们的客户并不想要所有这些软件。他们实际上并没有要求软件。他们要求的是更高的毛利率，他们要求的是更多的客户，他们要求的是更多的品牌差异化。而仅仅给他们交付更多可点击的窗口和按钮，这已经不能满足他们了。而这正是我们所有人开始看到自己新工作出现的地方。我们能够很好地与模型沟通，这就是你们坐在这里的原因，对吧？你们公司里还有其他人并不那么擅长与这些东西沟通。这意味着我们现在有了一项新工作。我们必须弄清楚如何建造一个“需求工厂（demand factory）”，因为我们的棕地工厂无法建立护城河。它所能做的只是让我们现有的承诺顺利运行。这很棒，因为它让我们能够把注意力集中到公司外部，面向市场，展望未来。但天哪，我们需要开始着手打造需求工厂了。

<details><summary>Original English</summary>
Okay. So one of the things that I think is we are all struggling with at this moment is, gosh, there's a lot of code coming out. Even worse, it's working. Um, uh, that's a lot of stuff. Uh, it's maybe too much stuff. Um, uh, we maybe have a glut of stuff. And uh, it could be the case that our customers uh, didn't want all this software. They actually they actually weren't asking for software. They were asking for more gross margin. They were asking for more customers. They were asking for more brand differentiation. Okay? Uh, and just shipping them more Windows uh, to click on and buttons to click on, um, that's not doing it for them anymore. Okay? Um, and this is where all of us um, are beginning to see the emergence of our new job. Okay? We can communicate with the models quite well. That's why you're here. Right? Um, there are other people in your firms who are not as fluent in communicating with these things. Okay? Um, so that means like we have a new job now. Um, we have to figure out how to build a demand factory because our brownfield factory can't build the moat. Right? All it can do is keep our existing promises running well. Um, that's great because it allows us to focus on sort of outside the building and look toward the market and look toward the future. Um, but gosh, we we need to start working on the demand factory.
</details>

我其实并不知道需求工厂具体是什么，但它大概是这样的：它大概就是我们需要的那种东西，好让我们在后端提升软件工厂的性能时，不至于把软件洒得满地都是。我们要让需求系统与我们的生产系统在速率上相匹配。但需求工厂需要大量的探索。这是一个新想法，但我认为你们绝对是可以开始推动你们的组织去问这些问题的人。不要等销售和市场部门来找你们问这个问题。你可以看到，在你们品牌的边界之内，还有更多东西可以交付。但你们需要向世界解释这一点，而且需要用新的词汇、新的意象和新的产品线等等去解释它。

<details><summary>Original English</summary>
Okay? Um, I don't really know what a demand factory is, but it it probably um, uh, looks something like this. It probably looks like the thing that we need so that when we boost performance in the back end here in the software factory, we don't end up spilling software all over the floor. And we rate match the demand systems to our production systems. Okay? But there's a lot of discovery that needs to go into the demand factory. This is a this is a new idea, okay? But I think you are absolutely the ones who can begin pushing your organizations to ask these questions. Like don't wait for sales and marketing to come to you on this question. Like you can see that within the uh envelope of your brand, there's something more you can ship. Um but you're going to need to explain that to the world and you're going to need to explain it using new words and new imagery and new product lines and so forth.
</details>

我认为你们的需求工厂能帮助你们向市场提出更好的问题，因为 agent 可以帮助确定接下来该问什么的优先级。我认为它能帮助实现更好的倾听，因为 agent 可以综合你们从这些问题中得到的答案，并且可以帮你们连夜重新排序，还可以把它们与你们听到的其他所有信息进行比较。因此，我认为它们可以安排更好的实验。我们如何获得这一特定产品的需求价格弹性？你们的实验带宽是有限的。如何分配它？模型将会帮你们解决这个问题。我认为这可能会带来更低延迟的响应，让我们能更快地答应客户，而客户也会开始不再自我设限，开始提出更多要求。那将会非常棒。

<details><summary>Original English</summary>
I think your demand factory helps you ask better questions of your market because the agents can help prioritize what to ask next. I think it can help with better listening because the agents can synthesize the answers you get back from those questions and can help you re-rank and they can help you re-rank overnight and they can compare it to everything else you've heard, okay? And therefore, I think they can schedule better experiments. How do we get the price elasticity of demand on this particular offering? You have a finite amount of experimental bandwidth. How do you allocate it? The models are going to help you with that. I think this could lead to lower latency responses where we are saying yes faster, okay? And customers begin uncensoring themselves and they start asking for more. That would be great.
</details>

## 品牌边界与需求信号

我觉得很奇妙的是，尽管我们的竞争对手拥有同样的模型，但似乎存在某种新的均衡版本，我们都在进行博弈论最优的竞争，然而如果我们先起步，仍然会有一定的优势。所以现在就开始吧。然后弄清楚我能向市场承诺的最大范围是什么，那就是我的品牌边界（brand envelope），让我们把它填满。稍微离题快速讲一下品牌边界——假设我们是 Spindrift，我们在卖一些很棒的带有一点果汁的气泡水。我提议：“嘿，你们知道吗？我们在里面加点咖啡因吧。”也许委员会会通过这个提议，也许我们就推出了这款产品。然后下一周我进来又说：“再加上机油吧。”你们知道，那肯定会被否决。但能量饮料，那是对我们品牌边界的一次很好的扩展。对于你们每家公司来说，都有同样的道理。也许你们不能卖机油，但也许你们可以卖能量饮料。所以找出你们的能量饮料是什么，现在就开始卖吧。

<details><summary>Original English</summary>
Um I think like weirdly, you know, even though our competitors have uh the same models, there's some version of some new equilibrium where we're all doing game theory optimal compe- competition and yet still if we start first, there'll be some edge, okay? So get started now. And then figure out what is the maximum extent of what I can possibly promise to the market and that's my brand envelope and let's fill it up. And just quick digression on brand envelope uh um let's say we're spindrift. Uh uh we we're selling some awesome sparkling water with a little fruit juice. Um I propose, hey, you know what? Let's throw some caffeine in there. Like maybe that gets by the committee. Like maybe we ship that. Um and then the next week I come in and I say like and motor oil. Okay? Um you know, that's going to get shot down. But uh energy drink, that's a good expansion of our brand envelope. For every one of your companies, you have the same thing. Maybe you can 't sell motor oil, but maybe you can sell an energy drink. So figure out what your energy drink and start selling it now.
</details>

所以让我们建造你们的需求工厂吧。它将会有大量来自客户、来自市场、来自任何你能衡量需求的地方的高质量信号流入。而且它将会有很大的流量。但为了让这种流量不至于压垮变更管理和欲望，它不能超出客户的需求。因此，你们需要有更多的客户。事实上，你们需要拥有更多的所有东西，但你们需要在这些客户中占据更多的钱包份额（wallet）。为了在这些客户中获得更多的钱包份额，你们就必须销售更多的 skews。除了更多的 skews，你们还必须把它们组织成连贯的产品线。所以你们将会有更多的产品线。而一旦你们把所有这些都做到极致，你们就需要直接去收购你们的竞争对手。如果你们现在就开始，你们就会成为那个去收购别人的一方。

<details><summary>Original English</summary>
Okay? So let's build your demand factory. Um it's going to have a high volume of high quality signal coming in from customers, coming in from the market, coming in from any place where you can measure demand. Um and it's going to be uh it's going to have a high volume of flow. Okay? Um but in order for that flow to not overwhelm change management, desire, um it can't blow out the needs of your customer. So therefore you need to have more customers. Okay? You in fact need to have more of everything, but you need to have more wallet within those customers. Okay? To get more share of wallet within those customers, you're going to have to sell more skews. Okay? Uh in addition to more skews, you're going to have to organize them into coherent product lines. So you're going to have more product lines. Okay? And once you've maxed out all of that, you're going to need to just acquire your competitor. Okay? And if you get started now, you're going to be the one doing the acquiring.
</details>

好，这就是全部内容了，这就是棕地工厂。我认为你们可以建造自己的棕地工厂。我认为你们绝对可以从现在开始建造自己的需求工厂。我显然也认为你们可以重启自己的产品管理，并且可以唤醒你们的高管团队。我们在 Diffusion 随时待命。我们在那里确实附上了一些我非常喜欢的棕地技术的技术资源。是的，我期待与你们中的许多人建立联系。好，保重，谢谢大家。

<details><summary>Original English</summary>
Okay. So uh so this is it. This is Brownfield Factories. I think you can build your Brownfield factory. I think you can absolutely build your demand factory beginning now. Uh I also obviously think you can reboot your product management and reboot and you can wake up your executive team. Um and we are standing by at Diffusion. So uh we do have some technical resources attached there on some Brownfield techniques that I really like. Um and uh yeah uh I look forward to uh connecting with many of you. Okay. Take care. Thanks.
</details>