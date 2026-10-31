---
author: a16z
date: '2026-10-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iRMmPjunm3Q
speaker: a16z
tags:
  - legal-ai
  - ai-agent
  - plaintiff-law
  - business-model
title: AI 法律助理 Eve 如何通过端到端代理重塑原告律所商业模式
summary: Andreessen Horowitz 合伙人 Alex Rampel 与法律 AI 初创公司 Eve 联合创始人兼 CEO Jay 探讨了法律 AI 在原告律所中的应用。对话阐述了原告律所受制于人力瓶颈的现状，以及 Eve 如何通过端到端长周期代理处理案件、提高办案效率，推动法律服务从按小时计费向结果导向演变。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Alex Rampel
  - Jay
companies_orgs:
  - Eve
  - Andreessen Horowitz
products_models:
  - Auditor
media_books: []
status: evergreen
---
### 原告律所的供给瓶颈与 AI 赋能

**>>**: 从历史上看，原告法其实只需要一部手机和一个电子邮件地址。差不多就这样了。没有任何软件真正解决过他们的核心问题，也就是劳动力瓶颈。大多数人想到 AI 时，会觉得“哦，你们要把所有人都开除然后削减成本。”但事实并非如此，如果我使用 Eve，实际上能为我的律所赚到更多的钱。人们不可能随随便便开出一张空白支票，按每小时 500 到 600 美元来支付不管案件要打多久的费用。Eve 致力于做到的，其实就是端到端地处理整个流程。洛杉矶的一家律所从每位律师管理约 100 名客户，跃升到了管理 500 名客户。
<details><summary>Original English</summary>

Historically, plaintiff law really didn't need more than a cell phone email address. That was kind of it. No software really solved their core problem, which is labor constraint. Most people think of AI is like, "Oh, you're going to fire everybody and cut costs." And it's like, "No, actually, like, if I use Eve, I make a lot more money for my firm. People can't pay $500, $600 an hour on a blank check for however long the case might take." What Eve has aimed to do is really handle that whole thing end to end. One firm in LA went from managing about 100 clients per attorney to 500.
</details>

**>>**: 哇。
<details><summary>Original English</summary>

>> Wow.
</details>

**>>**: 这确实是可能做到的事情。
<details><summary>Original English</summary>

>> That is a type of thing that is possible.
</details>

**>>**: 为什么 Eve 会比单纯的原生通用智能更好呢？
<details><summary>Original English</summary>

>> Why is Eve better than just kind of like raw intelligence?
</details>

**>>**: 如果你今天把阿尔伯特·爱因斯坦放到一家律所里，他在相当长一段时间内都不会有任何产出。这正是 Eve 正在解决的通用问题。为什么这个人会没有产出？嗯，这归因于很多因素。其中之一是……
<details><summary>Original English</summary>

>> If you drop Albert Einstein into a law firm today, he will not be productive for quite some time. That is a general problem that Eve is solving. And why won't that person be productive? Well, it's due to a number of things. One is
</details>

### 原告法与风险代理制度的本质

**>>**: 大家好。我是 Alex Rampel，Andreessen Horowitz 的合伙人，今天我非常高兴能与 Eve 的联合创始人兼 CEO Jay 在这里交流。大家都知道律师，也懂法律。但我认为大多数人，尤其是在硅谷，当他们听到“法律”和“法务”时，通常会联想到公司法，比如那种真正大型的、名牌的“白鞋”律所，你在哈佛法学院毕业后进入那里，开出每小时 2,000 美元的账单。但法律还有另外一面，实际上规模更大、分布更广，我想我们可以称之为原告法。每次你开车走 101 高速公路时，都会看到所有这些广告牌。或许你可以先讲讲，Eve 究竟是什么？你们专注于哪种形式的法律和法律 AI？顺便谈谈整个行业的大致情况，因为我觉得大多数美国人都熟悉它，但并不一定真正理解它。尤其是对于硅谷的人来说，他们听说过 Wilson Sonsini，但没听说过 Morgan & Morgan，对吧？而 Morgan & Morgan 可能比 Wilson Sonsini 赚得更多。那么，什么是原告法？能否也用你自己的话解释一下 Eve？
<details><summary>Original English</summary>

Hi everyone. I'm Alex Rampel, partner at Andreen Horwitz, and I'm very happy to be here with Jay from Eve, uh, co-founder and CEO. Um, and everybody knows a lawyer, right? Everybody knows law. But most people, I think, especially in Silicon Valley, when they hear law and legal, they kind of think about corporate law, like really big, you know, supposedly white white shoe, I guess, is the term law firms where you go to Harvard Law School and you build $2,000 an hour. But there's like another side of law which actually is bigger, more distributed, and I guess we would call that plaintiff law. Um, so like every time you drive on 101, you see all these billboards. Um, and maybe kind of talk about like what is maybe start off like what is Eve? Um, what form of law and legal AI do you focus on? and maybe a little bit about the industry in general because I feel like most Americans are familiar with it but they don't necessarily realize especially for people I think here in Silicon Valley they've heard of Wilson Cinci but they haven't heard of Morgan and Morgan right and Morgan and Morgan is probably a lot more profitable than Wilson Cinci but like what what is plaintiff law and also kind of maybe explain Eve in your own words
</details>

**>>**: 当然。首先，感谢你邀请我来这里，Alex，聊 Eve 总是很让人兴奋。Eve 是为真实普通人服务的法律 AI，对吧？像你我这样的人，不是机构，不是企业法务，不是那些已经拥有所有资源的人，而是我们如何真正为那些原本负担不起的人提供法律服务？这就是原告法律行业真正兴起的原因。因为最终发生的情况是，你提到 Wilson Sonsini 可能每小时收费 2,000 美元，那确实是他们的商业模式。律师的时间很昂贵，而且你试图把律师引导到越来越昂贵的时间上去。大多数律师也是如此。他们有很多账单要付，今天需要做法律工作。你在背后投入的工作越多，就能更好地陈述事实，就能取得更好的结果。这就是我们今天所处的世界。考虑到这一点，律师明白人们不可能按每小时 500 或 600 美元开出一张空白支票，支付无论案件持续多久的费用。因此，原告行业是建立在风险代理法之上的。这意味着他们只有在为客户打赢官司时才能拿到报酬。这就是让他们在普通人对抗机构时拥有公平竞争平台的原因。而 Eve 的目标是真正端到端地处理整个流程，即如何代表客户，从最初的第一通电话一直到为他们争取到和解金。如何纯粹依靠 AI 完成这整套端到端的工作，并将其提供给律师，从而放大他们实际能够带来的结果。这就是 Eve 正在做的事情。我们真正的做法，就像是给大卫一把击倒歌利亚的弹弓。这就是我们在做的事。
<details><summary>Original English</summary>

>> absolutely one thank you for having me here Alex always fun to talk about Eve um what Eve is is is legal AI for real people, right? Like people like you, me, not institutions, not in-house legal, not the people that already have all the resources, but how do we actually provide legal services to people um that otherwise can't afford it? And this is how the plaintiff law industry really came about because what ended up happening was you talked about how Wilson Cini might charge $2,000 an hour and that's that's really the business model. Lawyers times are expensive and you're trying to point lawyers towards more and more expensive time. The same is true for most lawyers. They they have a lot of bills to pay and they need today legal work. The more work you put behind it, you can represent your facts better. You can get a better outcome. That is the state of world we live in today. To account for this, lawyers understand people can't pay $500, $600 an hour on a blank check for however long the case might take. So, the plaintiff industry came about on working on contingency law. So, what this means is they only get paid when they win the case for the client. And this is what's allowed them to even have any sort of leveling playing field with people versus institutions. And what Eve is aiming to do is really handle that whole thing end to end and of how do you represent a client all the way from the very first call to getting them a settlement. How do you do that end to end thing purely with AI and give that to the lawyers to then amplify the outcomes they can actually provide. And that's what Eve is doing. And we're really arming, you know, think about giving David a slingshot to take down Goliath. That's what we're doing.
</details>

### 法律市场的供需失衡与市场失灵

**>>**: 我觉得这很吸引人的一点是，我常常联想到基础经济学，供给曲线是向右上倾斜的，这意味着什么？记住这里有价格和数量。这是数量，这是价格。随着价格上涨，供给量就会增加。
<details><summary>Original English</summary>

So what I find fascinating about this is uh you really I I kind of think about econ 101 where you have a supply curve that goes up into the right and what does that mean? Um because remember there's price and quantity. So here's here's quantity and here here's price. So as the price goes up right then the quantity supplied goes up
</details>

**>>**: 没错。如果我做某件事能赚 10 万美元，哇，那我完全愿意加入。但需求曲线是相反的方向。
<details><summary>Original English</summary>

>> right. So if I can make $100,000 by doing something wow I'm totally in. But the demand curve is the opposite direction.
</details>

**>>**: 没错。价格和数量是朝这个方向变化的。因此，需求，也就是我想要的单位数量……实际上我应该这样画，这是数量，这里是价格。价格下降，需求量就会大幅上升。如果我把这个应用到法律领域，比如如果我遇到了 1,000 美元的损失，对吧？即使是风险代理，我也可以给律师打电话，对吧？他们可能不想接我的案子，因为如果他们拿走结果的三分之一，他们会想要更大的案子，而且这需要一定量的工作。AI 在某种程度上真正解放了这些市场失灵，因为你刚才提到了给大卫一把更大的弹弓，很多时候大卫只是……首先，如果我有 1,000 美元的损失，我肯定付不起每小时 1,200 美元的律师费，所以我就出局了。于是风险代理法出现了。问题在于赔偿金可能不够大。所以律师可能想为我服务，但他或她有必须支付工资的律师助理等等。但如果软件能把这些工作做了，现在的市场机会就会大得多，对吧？你实际上可以为很多人伸张正义，否则他们并不是因为风险代理收费而被挤出市场，因为风险代理你怎么会被价格挤出呢？但接这种案子并不符合律师的利益。他们想服务接到的 1,000 个客户，但他们做不到。他们必须专注于最大的那些客户，从而损害了较小客户的利益，因为这又处于均衡点的右侧。我不知道你是否同意这点，或者你怎么看？
<details><summary>Original English</summary>

>> That's right. So you know price and quantity go this direction. So the demand the number of of units that I I want. Um actually I should say this this is quantity this is price here. So you know price goes down quantity demanded goes up considerably. And if I think about applying this to law like what if I have $1,000 of damages right? Um I can call a lawyer even for contingency right? um they might not want to take my case because if they take a third of the outcome, it's like they want a bigger case and it's going to require a certain amount of work and AI really it it kind of liberates these market failures to a certain extent because um you mentioned kind of giving David a bigger slingshot like a lot of times like David just well number one if I have $1,000 of damages I certainly can't pay $1,200 an hour for a lawyer so like I'm out for that. We'll enter contingency law. The problem is that like the settlement might not be big enough. So like the lawyer might want to serve me but like he or she has parallegals that they have to pay and so on and so forth. But if the software can do the work now the market opportunity is so much bigger, right? You can actually deliver justice for a lot of people that otherwise they weren't priced out of it because how do you how are you priced out of contingency? But like it's not really in the interest of a lawyer. they they want to serve, you know, a thousand customers that they get, but they can't. They have to focus on the biggest ones to the detriment of the smaller ones because again, it's kind of to the right of that equilibrium point. Um, I don't know if you agree with that or how you think about that.
</details>

**>>**: 完全正确。我认为这正是我们今天面临的实际市场问题。如果回到第一性原理，如果你是一个人，你理应拥有一名优秀的律师来代表你的案件。通常只有在走投无路时才需要律师，对吧？在这个时候，我们人性中最好的一面、最坏的一面都会暴露出来，而我们自己没有代表自己的专业技能。这就是整个职业存在的原因。这就是为什么司法系统大约占据了我们政府的三分之一。正是出于这个原因。
<details><summary>Original English</summary>

That is exactly right. I think that is the actual market problem we have today, which is, you know, if if you go back to first principles, if if you're a person, you deserve a great lawyer to represent your case. And usually only need a lawyer when your back is against the wall, right? The best of us, the worst of us comes out this time and we don't have the skill sets to represent ourselves. That's why this whole profession exists. That's why the legal system is about third of our our government. It's for this reason. Yeah.
</details>

**>>**: 今天正在发生的事情是，因为律师仍然需要拿到报酬，瓶颈依然存在于法律工作上。在今天，如果一个案件不能让律师赚到至少 5,000 美元的费用，他们就不会接。
<details><summary>Original English</summary>

>> Um and today what's happening is because lawyers still need to get paid. It's still bottlenecked on legal work. Today, if a lawyer doesn't make at least 5,000 fees of a case, they do not take it on.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah,
</details>

**>>**: 这就是当今的市场动态。即使能赚 5,000 美元，他们在很多案件上也是亏钱的。他们实际上押注的是少数案件能拿到巨额赔偿。
<details><summary>Original English</summary>

>> that is the market dynamics today. And even at 5,000, they're losing money on a lot of cases. They're really banking on few cases paying out very large.
</details>

**>>**: 他们甚至完全不能保证会赢。所以他们已经承担了这种风险，这就是风险代理的本质。
<details><summary>Original English</summary>

>> They're not even guaranteed to win period. So, they already take that that's the contingency aspect. That's exactly
</details>

**>>**: 但这有点像“即使我赢了，我也是输的”，因为承办这个案件的成本会高于实际的潜在收益，即便最终打赢了也是如此。
<details><summary>Original English</summary>

>> But it's kind of like even if I win, I lose because my costs of carrying the case are going to be higher than the actual potential outcome even if I win.
</details>

**>>**: 完全正确。想想看，这里的大多数人都经历过车祸，某种轻微碰撞。如果金额低于免赔额，全美国没有律师会接这个案子，对吧？在经济上根本不划算。哪怕免赔额对个人来说是 3,000 或 4,000 美元，那也是失去一张薪水支票与否的差距，对吧？而他们根本得不到任何法律代理。
<details><summary>Original English</summary>

>> That's exactly right. I mean, think about like most people here have been in an car accident, fender bender of some sort. If it's below the deductible, no lawyer in America will touch that case, right? It's just not economically worth it. Even if the deductible's $3,000, $4,000 to an individual, that is a difference between a paycheck being gone versus not, right? And there's no representation they can get for that,
</details>

**>>**: 对吧？同样的事情……原因实际上也必须站在律师的角度来理解，对吧？假设你在工作中一直受到骚扰，而你的雇主本来可以制止它，比如在酒店餐饮服务行业，雇主本可以告诉顾客“不要骚扰我的员工”，并改变流程来实现这一点。今天这并不会发生，因为当那个人打电话时，另一端的律师必须接听电话，处理那个电话，这大约需要 30 到 45 分钟的时间。然后在此之后，还要去做法律研究。因为在美国的雇佣关系中，几乎所有事情都是任意雇佣（at-will），你必须把问题与某种受保护的条款联系起来，这被称为诉讼请求由头（causes of action）。所以你必须把它与一个诉因联系起来，这项工作需要他们花上 10 个小时……
<details><summary>Original English</summary>

>> right? And the the same thing and and the reason is actually from their side we have to understand from their side too right so let let's say you've been getting harassed at work and your employer could stop it like in hospitality industry let's say you could you know tell your customers hey don't harass my employees and change processes to make that happen today that doesn't happen because when that person gets calls the lawyer on the other side has to pick up a call feel that call that's about 30 to 45 minutes of And then after that, go do legal research because in employment in America, pretty much everything's at will and you have to tie a problem to uh you know like a protected protected clause of some kind and it's called causes of action. So you have to tie it to a cause of action and that work requires them to go spend 10 hours
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: ……去研究判例法，研究事实，来来回回询问更多后续问题，看看他们是否符合条件。当他们花完了所有这些时间，他们可能仍然会意识到：嘿，这个案子甚至赚不到 5,000 美元。
<details><summary>Original English</summary>

>> to go research your case law, research the facts, go back and forth and ask them more followup questions, see if they qualify. And while they spent all that time, they might still realize, hey, this doesn't even make me $5,000,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>

>> right?
</details>

**>>**: 这就是为什么在劳动和雇佣领域，例如 96% 的案件会被拒绝受理。
<details><summary>Original English</summary>

>> So that is why 96% of cases on the labor unemployment side, for example, gets rejected,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>

>> right?
</details>

**>>**: 所以你根本找不到任何人来代理，除非你自己掏腰包。而在很多情况下，人们根本没有钱自费请律师。所以……
<details><summary>Original English</summary>

>> So you can never find anybody of represent unless you come out of pocket. In many cases, people don't have money to come out of pocket. So
</details>

### 用 AI 释放劳动力约束：从 10 小时到即时响应

**>>**: 完全正确。完全正确。所以除非发生极其恶劣的事情，否则你只能忍气吞声。这就是目前的现状，瓶颈全都在法律劳动力上。而这正是 Eve 想要解决的：如何把原本需要 10 个小时的过程，通过 Eve 变成即时完成？一通电话打进来，Eve 实际上会接听电话，并自动运用律所的见解来判断这是否是律师应该承接的案件，然后直接生成索赔函（demand letter）或完成初步工作。对吧？这彻底改变了这类案件的经济模型。我们仍处于非常早期的阶段，Eve 在处理端到端长期限结果方面的能力正变得越来越强。这些案件需要 6 个月甚至一年时间来推进，期间可能会发生上千次来回往复的行动。随着 Eve 的准确性越来越高……
<details><summary>Original English</summary>

>> that's exactly right. That's exactly right. So you just kind of take it unless something really egregious happens. Um, and that is the current state and it's all bottlenecked on legal labor. And this is what Eve is meant to do is to how do you now take that 10 hours is now immediate with Eve. A call comes in, Eve actually answers the call and automatically uses his insights on the law firm to know whether or not this is a case the lawyer has to take on or not and then hit the ground running with a demand or the initial preliminary work done. Right? And that completely changes the economics of that type of case. And we're still at the very beginning stages, you know, like what's what's happening is Eve is getting more and more capable of handling outcomes end to end over a very long horizon. These cases take 6 months a year to take to launch and through them probably a thousand actions back and forths that are happening. And as accuracy of Eve is getting higher and higher,
</details>

**>>**: 这种长期限的闭环就变得可行了。越是可行，越复杂的案件工作就被平摊成一个恒定的常数。现在，所有这些没有代理的人都能获得法律代理了。
<details><summary>Original English</summary>

>> this long horizon becomes possible. So the more this becomes possible, even more complicated work gets more ties down to a constant case. So now all these people without representation get representation.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 如果你真正问问自己，在你的一生中有多少次，如果寻求法律援助没有阻力，你会去寻求帮助？这个数字远比我们想象的要高得多。是的。这是一个有趣的故事，这是一个真实的故事。大概九个月前，我在洛斯阿尔托斯一家叫 Blue Bottle 的小咖啡馆里，当时正在向别人解释 Eve。我解释说，大多数人认为 AI 就是“哦，你要解雇所有人并削减成本”，一切都关乎节省成本；而实际情况是，“不，如果我使用 Eve，我能为我的律所赚更多的钱。并不是因为我削减了成本，而是因为我可以接更多的案子。这实际上是收入扩张。”我作为一个外部投资人在解释这些，可能没有你说得那么好。在谈话快结束时，我们聊了很多话题，但提到了 Eve。这时一个人朝我走来，看起来有点生气。他牵着一只大狗，我其实有点怕大狗。他问：“你刚才聊的那家公司叫什么？”我心想：“糟糕，他要生气了吗？”他说：“我是一名出庭辩护律师。我想试试这款产品。”我说：太棒了。
<details><summary>Original English</summary>

>> Um and if you really ask yourself like how many times in your life if asking for legal help wasn't a friction point? Would you have asked it? That number is way higher than we think. Yeah. So it's a funny story. This is a true story. I was in Blue Bottle, a little coffee shop in Los Altos, and I was explaining Eve to somebody probably nine months ago, and I was explaining it because most people think of AI as like, oh, you're going to fire everybody and cut costs, and it's all about cost savings, and it's like, no, actually, like, if I use Eve, I make a lot more money for my firm. And it's not because I'm cutting costs. It's like I can take on more cases. It's actually revenue expansion. So, I'm explaining this um as as an outsider investor can, so not as well as you probably would. And at the end of this, I mean, we were talking about many topics, but Eve came up and this guy comes up to me, he looks a little angry. He has a big dog, and I'm kind of afraid of big dogs. And he was like, "What was that company you were talking about?" I was like, "Uhoh, is he going to get mad?" He's like, "I'm a trial attorney. I want to try it." Oh, great.
</details>

**>>**: 所以我给你们拉来了一个新客户。谢谢。
<details><summary>Original English</summary>

>> So, I got you a new customer there. Thank you.
</details>

**>>**: 但核心在于你们扩大了增收机会。或许可以剖析一下其中的动态机制。因为大家都开过 101 高速或 95 号州际公路。I-95 是一条从佛罗里达一直延伸到缅因州的交通走廊，贯穿整个东海岸。我几乎开过整条路线。感觉有一半的广告牌都是出庭律师、原告律所打的。显然他们在那里做广告是因为希望能接到电话，比如“嘿，我遇到了事故或问题”。但是经济账是怎样的呢？我花了这么多钱投放广告，这也是为什么我认为 Eve 如此引人入胜的原因，因为我必须拒绝掉 90% 打进来的销售线索，我猜是这样吧？具体数字是怎样的？我在广告牌上花钱，收到了大量进线。其中有多少能转化为案件？这些案件中又有多少能转化为实际收入？或许可以对比一下使用前后的情况，因为你们对律师来说不是缩减成本的工具，而是为他们拓展收入的工具。那是从法律层面上看，但对于一家律所来说，其经济账是怎样的呢？
<details><summary>Original English</summary>

>> But the whole point is that you expand the revenue opportunity, but maybe kind of walk through like what do the dynamics because everybody has driven on 101 or I 95. I95 is the corridor that goes from Florida all the way up to to Maine or something, you know, up and down the eastern seabboard. And it's like I've driven almost all of that. And it's like I feel like half of the ads are for trial attorneys, uh, plaintiff law. Um, so they're obviously advertising there because you want they want to get called. It's like, hey, I I I have this accident or I have this issue. Um, but what do the economics look like? So like I I spend all this is why again I think Eve is so fascinating because I have to turn down 90% of the leads that I'm getting. I assume, right? Or like what what do the numbers look like? I spend money on a billboard. I get lots of inbound. How many of those turn into cases? How many of those cases turn into revenue? Maybe kind of like a before and after because you are you're not a cost savings play for lawyers. You're a revenue expansion play for them. That's that's from the legal side. But what what what do the economics look like for a law firm?
</details>

### 律所的内部流程瓶颈与软件重塑

**>>**: 完全正确。当大多数人开车经过时，他们只看到了广告牌上的头像，却忽略了背后的人，以及处理每一通电话实际需要付出的工作量。这就是现在的现状，也是 Eve 要协助解决的。对律所来说，这笔账其实很简单：通常来说，你代理的人越多，赚的钱就越多。但由于你可以接纳更多客户，而你目前确实因为承办成本过高而拒绝并放弃了很多案件，所以从他们的角度来看，需求其实不是制约因素，真正的瓶颈在于劳动力供给。比如“我内部是否有足够的人手来真正处理这个问题？”而且更复杂的是，不同的律所面临着不同层面的问题，瓶颈在不断转移，对吧？比如一家小型律所可能只有一名律师，配有一名案件经理或某种办公室主管来接听最初的电话，记录下来，然后律师在空闲时间回复。他们基本上处于一种混乱忙碌的状态。然后是下一个层级，他们找到了一种系统化的方法，比如拥有一个位于某地的呼叫中心式的案源接收（intake）团队来进行接收，而这又成了新的瓶颈。因此，当你增加营销支出时——假设你在那个广告牌上看起来特别有吸引力，大量的人打电话进来——突然间那个团队就不堪重负了，你再次受限于你能代理的人数上限，对吧？
<details><summary>Original English</summary>

That that's exactly right. When most people drive by, they see the face and they forget about the people behind them and the amount of work every single call actually takes. That's that's what happens today. That's what Eve is there to help with. And the math on the law firm side is very simple. The more people you represent, typically speaking, the more money you make. But because you can take on more people and you honestly are denying and not taking on many cases because they're too expensive to take on, the demand from their perspective is not really constraint. It's really the supply of labor. Like do I have enough people uh inside to actually service that problem and to make things more complicated different firms here are in different realms of problems where the bottleneck keeps shifting, right? So like a small firm might just have one attorney that is has a case manager or some sort of uh office manager that feels initial call and just notes it down and then the lawyer then responds back in their free time, right? They're kind of running chaotically running around and then there's a next level which is they find a way to systematize it. You know, they have a an intake team of call like a call center somewhere that intakes it and now that becomes a new bottleneck. So now when you increase your marketing spend, let's say you looked particularly attractive in that billboard and a lot of people are calling in. Uh suddenly now that team is overwhelmed and you're limited again by how many people you can represent,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>

>> right?
</details>

**>>**: 这就是这些小微企业每天要应对的挑战。它们是小微企业，不是庞大的巨头。他们想要代表个人，而这里的每个人上的都是法学院，而不是商学院。他们希望为大众服务。因此，我们基本上将所有这些整合到 Eve 平台中，使律师仅在真正需要时才被介入，比如发挥他们的法律专业洞察力，关于如何拿下这个案件的独特判断。Eve 在不断抬高底线。我该如何在这个底线之上更进一步？我认为这才是所有律师真正应该花时间的地方——与他们的客户沟通，帮助客户取得结果。
<details><summary>Original English</summary>

>> And this is the daily challenge these small businesses are dealing with. It's they're small businesses. They're not massive enterprises. Uh they want to represent individuals and everyone here went to law school, not business school. They want to be there for the people. Um, so we're basically consolidating all of that into the EVE platform such that they are getting pulled in only for what they need to, right? Like their lawyer insights, their particular insights on how do they take this case? Eve keeps raising the floor. How do I take it from this floor to the next level? And that is where I believe really all lawyers should spend time talking to their people and helping get client outcomes.
</details>

**>>**: 这在某种程度上就是市场失灵的关键点：如果我能以每小时 12 美分雇用一名律师助理，或者付出相应的模型 token 成本，我就可以服务打进来的全部 5,000 个线索。但我做不到。
<details><summary>Original English</summary>

Well, and this is kind of the the market failure point to a certain extent, which is I could serve all 5,000 leads that came in if only I could hire a parallegal for 12 cents per hour, right? Or whatever the token cost of it, but it's like I can't.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>

>> Mhm.
</details>

**>>**: 没有任何劳动力市场能以这种方式运作，但现在有了 AI，我可以了。你有没有关于使用前后的具体案例？就像男士生发俱乐部广告那样，“这是使用前的我，这是使用后的我，我拥有一头浓密的头发。”对你们合作的最佳客户来说，具体情况是怎样的？我猜收入上的转变是相当显著的。
<details><summary>Original English</summary>

>> So, I would just there's no labor market that could actually function, but with AI now, I can. Um, I mean, do do you have anecdotes of just like kind of before and after? It's just like, you know, like the hair club for men. It's like, you know, here I am before, here after. I have a nice head of hair. But like, what what's that for kind of your best customers that you work with? I imagine the revenue transformation is pretty significant.
</details>

**>>**: 是的。洛杉矶的一家律所从每位律师管理约 100 名客户，跃升到了管理 500 名客户。
<details><summary>Original English</summary>

Yeah. One one firm in LA went from managing about 100 clients per attorney to 500.
</details>

**>>**: 哇。
<details><summary>Original English</summary>

>> Wow.
</details>

**>>**: 没错。这确实是可能做到的事情。而且值得赞赏的是，他们为了实现这一目标非常努力。他们把 Eve 用到了极致：从案源接收、接听电话、自动进行资质筛选，消除了在不同律师和案件经理之间传递信息的所有交接中继问题，所有这些现在都在 Eve 的智能体中处理；一直到最终和解，在他们去参加调解人谈判之前自动生成摘要简报，明确告诉你需要关注什么、根据我们处理过的类似案件和解金额应该大致是多少，以及你以前使用过哪些策略帮助你走到了这一步。
<details><summary>Original English</summary>

Right. And that is that is a type of thing that is possible. And they went to to their credit, they worked really hard to achieve this. They utilized Eve up to the max of all the way from intake take fielding the call doing qualification automatically removing all the relay problem that they have of passing things from one attorney to another to a case manager all that is now handled within agents in Eve and all the way to settlement where it's actually briefs before they go to a mediator discussion that actually tells you here's what you need to focus on here's what the settlement outcome should look like for cases like this that we worked on and here are the tactics you used before that got you here.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 这就是未来的样貌。它真正地持续推进案件，而你在协助它，让它比单打独斗做得更好。我认为这就是法律的未来，对吧？作为律师，你将看起来更像一名数据科学家和工程师，通过工程化手段让系统变得越来越好。这是使用 Eve 的顶级律所在思想观念上所经历的一种转变。
<details><summary>Original English</summary>

>> And that is what the future looks like. It's truly moving the case forward continuously and you're helping making it do a better job than it could do by itself. That is I think the future of law, right? Where you as a lawyer are really going to look more like a almost a data scientist and engineer engineering something to be better and better. And that is a shift the top law firms on eve mentally kind of go through.
</details>

### 原告法律软件的“影子劳动力”市场

**>>**: 是的。如果看看一般的普通律所，他们对 AI 并不真正了解。其实这可以说是对整个 AI 赋能应用领域一个很有趣的视角。在以前，法律领域的软件技术栈是什么？如果你是像 Wilson Sonsini 这样的大型律所，可能最重要的工具是工时追踪软件，对吧？因为你是按小时计费的。如果你从事风险代理法，时间虽然重要，但你并不以此向客户开账单。你可能需要记录每个案件花了我多少钱。但我猜你们的主要工具其实是 Microsoft Word。以前没有其他软件，这也是风险投资人过去会看错这个行业的原因：他们会觉得“原告法领域的软件市场很小，他们都买微软 Office。微软 Office 虽然有点贵，但整个软件支出每年可能也就几百亿美元之类”，看似微不足道。等一下，他们交付的案由结果每年高达数千亿美元。他们无法交付更多成果，是因为真正受到了劳动力的制约。而且他们不可能以每小时 12 美分的价格雇用劳动力，因为这种劳动力根本不存在。事实证明，软件市场实际上就像是一个“影子劳动力市场”，它的规模远比任何人预期的都要庞大得多。你不能因为你是一家法律软件公司就说软件市场很小。人们知道 Harvey，或者知道公司法软件，或者存在已久的电子证据开示（e-discovery）工具。但我很好奇，在 Eve 出现之前，主要的技术栈是什么？难道就只有 Microsoft Word 吗？或者如果我从法学院毕业想创业、想进入这个细分领域，我的软件栈是什么？
<details><summary>Original English</summary>

>> Yeah. Well, I kind of think of if you if you look at uh your average law firm where they don't really know AI and and actually like this is kind of an interesting kind of take on on the world of of AI enabled applications in general. Like what was the software stack for law before? Well, if you're a big firm like Wilson Cinci, probably the most important thing is like your your time tracker, right? Because you're billing by the hour. If you're in contingency law, it's like, well, your time matters, but you're not billing your customers on that. You probably need to have like a, you know, each case, here's how much money I'm spending on the case. But like, I imagine your primary tool was Microsoft Word. And there wasn't, and this is how like VCs would have like gotten this industry wrong before, which is like, oh well, the software market for plaintiff law is small. They all buy Microsoft Office. Yeah, Microsoft Office is kind of expensive. So therefore, like the software spend is like in the tens of billions of dollars a year or something, you know, seemingly comically small. But wait a minute, the outcomes that they deliver is in the hundreds of billions of dollars a year. um they can't deliver more outcomes because they're really constrained on labor. Um and they can't hire labor for 12 cents an hour because it doesn't exist. So it turns out the software market is kind of like this shadow labor market and it's like massively bigger than anybody would have expected. Um, and and like it's always just a weird thing because it's like you can't say the software market is small because you're a you're a legal software company,
</details>

**>>**: 这正是原告法律与机构之间令人遗憾的地方：从历史上看，原告法其实只需要一部手机和一个电子邮件地址。说实话，即使是微软 Word，有些个体从业律师出于成本原因也不会购买。
<details><summary>Original English</summary>

>> but people know Harvey or they know like corporate laws or like you know eiscocovery tools that have been around. But I imagine like what was the main software stack before Eve entered? What was it just Microsoft Word or like what what what was in order for me to go into business? I graduated from law school. I want to be in this particular you know subsector of the field. What was my software stack? You know, this is the unfortunate thing about plaintiff law and institutions is historically plaintiff law really didn't need more than a cell phone email address. Honestly, even Microsoft Word, some people on the solos would not buy it for cost reasons.
</details>

**>>**: 不会买，因为仔细想想，你其实不需要做太多的文本修订划线（redlining）。
<details><summary>Original English</summary>

>> No, it's it's because if you think about it, you actually don't do that much redlinining.
</details>

**>>**: 这是一种信任边界的情况，对吧？你的一方和另一方在某种程度上是对立的，所以你们并不是在……
<details><summary>Original English</summary>

>> It's a trust boundary situation, right? So you're you're one side is kind of opposition to the other side. So you're not
</details>

**>>**: 并不是真正的协作。
<details><summary>Original English</summary>

>> really collaborating.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yes.
</details>

**>>**: 不像在做合同审查或类似事情时那样。
<details><summary>Original English</summary>

>> In the same way that you are when you're doing contract review or or something along those lines.
</details>

**>>**: 所以差不多就是那样。没有任何软件真正解决过他们的核心问题，也就是你刚才提到的劳动力限制。这是他们开展任何业务的核心。因为他们拥有劳动力，并且善于管理人力，所以对他们来说，所有问题看起来都可以通过劳动力来解决。他们就是这样成长起来的。结果就是，大量的软件研发资源都流向了被告辩护机构，因为那是预算所在的地方，比如 Harvey。说实话，今天的任何法律软件公司，绝大多数都在做被告辩护业务，因为那里的预算充裕，对吧？
<details><summary>Original English</summary>

>> So that was kind of it. And no software really solved their core problem which is exactly what you mentioned their labor constraint. That is the core of how they do anything at all. And because they have labor and they're good at managing their labor, they found a way to solve all every problem to them looked like solve with labor. And that's how they've they've grown up. And as a result of that, what ended up happening was a lot of resources on software went towards defense institutions because that's where the budgets were for Harvey. You know, really any company honestly, legal software company today, vast majority of them are on the defense side because that's where the budgets are. Right.
</details>

**>>**: 没错。为他们开发软件容易，从他们那里收钱也容易。而在原告这一边，这些都是每个月精打细算的小微企业，对吧？如果你不能从第一天起就为他们带来结果，你就被淘汰了，根本拿不到续费。他们会骂你，会想尽办法找你麻烦，对吧？这就是事情如此困难的原因。但我们意识到的是：我们清楚他们的核心诉求与动机。他们想要代表更多的人，他们想要赢。而我们现在可以做到这一点。今天软件的奇妙之处在于，一旦你手动完成了一项任务——甚至是包括处理新数据并转换数据的任务，而这正是 AI 非常擅长的——你现在就可以把它编码为一个流程。这是一个前所未有的根本性转变。他们过去曾试图通过人员运营来实现这一点，但从未奏效，因为每个案件的差异都足够大，无法机械套用，最终还是受限于能否招到足够聪明的人来处理。而现在，一个聪明的人实际上可以像我们讨论的那样，同时处理 500 个事实迥异、情况大不相同的案件。要怎么把所有这些细节记在大脑里？这很难，对吧？但现在你不再需要强行靠大脑记了。
<details><summary>Original English</summary>

>> Right. And that's what's easy to build for, easy to get money for. And on the on the plaintiff side, these are small business that are watching their pocketbooks every month, right? If you're not driving outcomes for them from day one, you're out. You're not getting renewed. They're they're going to curse you out. You know, like any anything they can do, they're going to come after you, right? And that's what's made things so difficult. But what we realized is, well, their core problem is we know what their incentives are. They want to represent more people. They want to win. And we can do that now. You know, there's once the beauty of software today is once you do a task manually, even tasks that include crunching new piece of data and transforming it, that's kind of what AI is really good at, you can now encoded as a process. That is a fundamentally new shift that has never happened before. That's what they were trying to do with people operations, but never worked because every single case is still different enough that you can't do it. it's still bottlenecked on hiring smart enough people to be able to handle it. And now one smart person can actually handle like we talked about 500 different cases of very different facts, very different situations. Um, and how do you even keep that in your brain? Like it's hard, right? But now you don't have to.
</details>

### 非公开数据与本地化智能壁垒

**>>**: 我猜目前很多在应用层创业的创始人都在思考：“哎呀，也许我们会成为大公司的垫脚石”，比如开发底层基础大模型的实验室，也许他们下一步就会涉足这个领域，我们就完了。防御这种情况的方法有很多，但单说“防御”其实低估了潜力，因为如果你拥有网络效应，或者拥有别人都没有的数据，你就能交付更好的结果。所以，谁在乎大家是不是都在后台或者私下使用 ChatGPT 或 Claude 呢？不过，能否谈谈你肯定深思熟虑过的问题：为什么 Eve 比单纯的原生智能更好？随着使用该产品的从业人员越来越多，它是如何变得越来越强大的？
<details><summary>Original English</summary>

And I guess one of the things that a lot of founders are thinking about right now at the application layer is like, uhoh, maybe I'm roadkill from the big guys, right? like the labs that produce the intelligence, maybe they're going to go tackle MySpace next and I'm I'm toast. And there are many ways of defending against that, but defending kind of sells it short because if you're able like if you have a network effect or if you have data that actually nobody else has, you can deliver better outcomes. So, you know, who cares if everybody uses chat GBT or or clawed behind the scenes or on their own? But maybe talk about like I'm sure you've thought about this a lot, you know, why is Eve better than just kind of like raw intelligence and how does it get better because it does uh the more practitioners that use the product?
</details>

**>>**: 是的，我们押注于这些模型会变得越来越优秀。而我们的价值正是在于此。如果你有一千个阿尔伯特·爱因斯坦可以用来做诉讼，或者有史以来最好的律师来做每一项具体任务，我们当然乐意采用。但问题是，如果你今天把阿尔伯特·爱因斯坦放到一家律所里，他在相当长一段时间内都无法产生生产力。而这正是 Eve 正在解决的普遍问题。为什么那个人会没有产出？我认为这源于几个方面。首先，在原告法律中，绝大部分数据实际上是无法从网络上抓取爬取的。只有不到百分之一的案件真正达成了和解并形成了判例意见，对吧？
<details><summary>Original English</summary>

Yeah, we're we're betting on we're betting on these models getting better and better. Um and our value is exactly that. you know, if you have thousand Albert Einsteins to work with to do litigation or or you know, the best attorney ever to to do every single task, we would take it. The problem is if you drop Albert Einstein into a law firm today, he will not be productive for quite some time. Um, and that is a general problem that Eve is solving, right? And why won't that person be productive? Well, it's due to a number of things, I think. One is in plaintiff law, the vast majority of data is actually non-scrapable. about less than a percent of cases actually settle and get turned into case opinions,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>

>> right?
</details>

**>>**: 绝大多数案件在发出索赔函之前或在进入诉讼程序之前就和解了，有些甚至在更早阶段就解决了，对吧？这实际上只是一场谈判：“看，这就是我受到的伤害，请给予补偿。”举个具体例子：我遭遇了车祸，我没有过错。对方的保险公司会说：“哦，你伤得没那么重，我们赔你一美元。”对吧？他们总是试图推卸否认。保险公司的第一条规则是推诿拒赔，第二条规则还是推诿拒赔。规则一直如此，这些都是保险公司的标准做法。
<details><summary>Original English</summary>

>> Vast majority settle pre-demand or pre-litigation and some even before that, right? Where it's actually just a negotiation of, hey, this is how I was wronged. Please fix it. And to make that concrete, it's like I'm in a car accident. I'm not at fault. Um, you know, the adversary, if you will, like the other side's insurance companies like, oh, you weren't that hurt. We'll give you a dollar. Right? They always try to like deny, deny, deny. like rule number one if an insurance carrier is denied. Rule number two is denied. You know, it just goes on. Those are all the rules of insurance carriers.
</details>

**>>**: 于是我现在聘请了一名律师，去真正拿回应得的赔偿，因为我确实受伤了，我的车确实彻底报废了，而他们就是不想付钱。你最终拿到了和解，没有立案成诉，没有真正走上法庭审理。但你知道：Geico 最终确实赔付了 29,000 美元。
<details><summary>Original English</summary>

>> So now I hire a lawyer um and to actually get what I'm owed because I actually am injured and my car is actually totaled and they just don't want to pay me. Um you get a settlement doesn't go to case. It doesn't go to actual trial, but you know, that's right. That Geico actually did pay $29,000.
</details>

**>>**: 我猜这是非常非常有价值的信息。
<details><summary>Original English</summary>

And that's very, very useful information, I assume.
</details>

**>>**: 没错。保险公司面对的是成千上万起不同的诉讼。
<details><summary>Original English</summary>

>> That's right. insurance is the one that's dealing with 100,000 different law.
</details>

**>>**: 他们拥有共享的共同体，了解所有的案情，但因为这些案件分散在各个不同的本地律所中，律所并不知道 Geico 的一举一动。
<details><summary>Original English</summary>

>> They have the shared community, they know all the cases, but because it's charted across all the different local firms. They don't know exactly Geico's every single move.
</details>

**>>**: 完全正确。他们甚至使用名称听起来令人畏惧的软件，比如 Colossus，用来追踪并试图断定：一根拇指骨折，他们认为就值这个金额。客观地说，给伤害定价本身就是一件难事。但他们不仅这样做，还会计算用多低的赔偿金就能打发掉对方，完全不考虑当事人的实际需求和具体处境。这正是法律体系旨在纠正的问题，也是法律存在的意义。现在的情况是——这也是有趣且具有挑战性的部分——如果你去 Google 搜索“如何针对 State Farm 就软组织损伤案件写出一封出色的索赔函”，这种内容在网上任何地方都找不到。即使是对新加入原告律所的律师助理来说，这也是他们必须现学的东西。最重要的是，情况还会变得更加复杂，因为在地方司法管辖区内，当地的法庭环境、对方辩护律师的行为模式都会略有不同，这些背景语境也同样重要。因此，Eve 所做的，就是将这些在历史上极难利用的多属性、多维度信息——本质上是在特定的时刻我能做出的最佳行动是什么以改善案件结果——进行转化。
<details><summary>Original English</summary>

>> That's exactly right. And, you know, they even have ominous sounding software like Colossus, which tracks, you know, they they're they try to basically say a broken thumb. This is how much we think it's worth. Which is a hard thing to do in their defense. Like it's a hard thing to do, but they are doing that. but also saying this is how much we can get away with giving them away for and irrespective of that individual's actual need uh of of their particular situations. And that's what the legal system is meant to fix. That's that's what it's there for. Um and what now is happening is and this is this is the interesting bit and the challenge is if you go and Google how do you write an amazing demand letter for again state farm for soft tissue injury cases like that today exists nowhere even for a new parallegal that is joining a plaintiff firm this is something they have to learn and on top of that it gets more complicated because when you're in local jurisdiction the local environment like the court systems uh you're opposing council, they all behave a little differently and that context matters too. So what EVA is doing is it's turning this historically incredibly difficult to utilize multi-attribute multi-dimensional information that is basically what is the best thing I can do at this particular moment to improve the outcome of the case.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 在一个案件的处理过程中，同一个问题会重复出现成千上万次。人类的大脑根本无法在脑海中记住所有这些。但 AI 可以，这正是我们帮助律所构建的数据类型，他们立即从中看到了价值。他们看到价值的第一个环节当然就是案源接收：我到底应该接谁的案子？我擅长代理谁？或许可以从那里开始，然后不断精进，对吧？
<details><summary>Original English</summary>

>> And that same question is repeated thousands of times during the case. And a human brain is just not capable of kind of keeping all of that in mind. Um and but AI is right and and that is the type of data we help build for law firms and they're seeing the immediate value from it. And the first place where they see value is of course intake. Who do I even take on? Who am I good at representing and maybe start there and keep getting better,
</details>

### 数据隔离、知识共享与审查产品 Auditor

**>>**: 我设想，因为这些都不是大律所，对吧？如果我是新泽西州一家拥有 4 名律师的律所，而那边在亚利桑那州有另一位拥有 7 名律师的律所，他们的对手往往都是 State Farm、Geico 等等。在一定限度内共享信息其实是没问题的。你是怎么考虑数据问题的？因为这在创业初期对公司来说往往是个难关，大家会觉得“不行，这是我的数据”。但我猜这其中有一种互惠交换。这就像我和一家牙科 AI 公司合作，爱荷华州的牙医不能为佛罗里达州的患者看病，但他们希望从彼此的集体行动经验中学习。你怎么看数据隔离这类问题？这曾经成为过阻碍吗？或者你们是如何考虑使用这些数据的？
<details><summary>Original English</summary>

>> right? And I imagine um because these aren't giant firms, right? Like if I'm a lawyer in New Jersey with a four person, four attorney practice and uh over there there's another lawyer in Arizona with a seven attorney practice, but their counterparties tend to be State Farm and Geico and and and whatnot uh at the limit. It's actually fine to share information. I guess how do you think about data because I imagine this is always a this is always you know hard for companies when you're getting off the ground. It's like no this is my data. Um but there's also there's a give to get I assume. It's kind of like you know I I work with a a dental AI company and it's like well the dentist in Iowa can't serve patients in Florida but they want to learn from the collective actions of each other. Um but I guess how do you think about you know just data se sequestration and whatnot? um does that ever become an issue or how do you think about using it?
</details>

**>>**: 我们基本上遵循了该行业已有的既定规则，但用软件放大了它。这就是我们的立场。规则是：针对他们自己的具体案件，他们希望高度保密，这在法律上非常重要，属于律师-委托人特免权保护范围（attorney-client privilege），我们绝不会在这些数据上进行模型训练。
<details><summary>Original English</summary>

>> We we've largely followed the rules of engagement that already exists in this industry but we've amplified it with software. That's kind of our stance, right? So the rules rules of engagement is for their own cases uh they want to be very private like that is important by law. It's attorney client privilege and we don't train on that data ever. Yeah.
</details>

**>>**: 明白。
<details><summary>Original English</summary>

>> Right.
</details>

**>>**: 然而，律师们为了分享这种知识，实际上也会出差、参加继续法律教育（CLE）讲座，相互分享针对 State Farm 某种具体辩护策略的应对技巧，因为 State Farm 在全美各地都在重复使用同样的策略。这里并不是针对 State Farm，任何机构在这里都是平等的博弈对象，但这确实是他们一直在做的事情。因此，我们聘请了自己的律师，并在平台上追踪案件的胜诉率。我们希望帮助你：如果你使用 Eve，你应该获得更高的胜诉率，这就是我们所追踪的指标。我们有一款名为 Auditor 的产品，它会在夜间逐页分析每一个案件，寻找优秀律师每次都能发现的问题。不幸的是，在所有律所中，绝大多数案件——几乎每一个案件——都有被遗漏的信息。而现在，这不再是个问题了。
<details><summary>Original English</summary>

Uh however, what attorneys also do is to share this knowledge they actually travel. They attend CLE and they share tactics each other on how they went up against State Farm's X and Y defense um because State Farm repeats that defense across the board, right? And uh not picking on State Farm, anyone is fair game here, but that is that is what they're already doing. So, we hire our own attorneys and track success rates of cases for our platform. And we want to help if you're using Eve, you should have more success. That's what we track. Um and we have this product called Auditor, which actually analyzes every single case through every single page overnight and looks for uh situations that a perfect attorney would catch every time. And across the board, unfortunately, vast majority of cases have almost every single case has missed information, right? And now that's no longer a thing.
</details>

### 对抗性博弈与长周期代理的演进

**>>**: 是的，或许可以谈谈未来的走向。因为一方面，我可以预见 Geico 迟早也会变得更聪明一点，他们可能……因为他们那套“推诿、拒赔”的方案正是他们变聪明的方式，因为他们意识到这是一个对抗性系统。比如我在火灾中失去了房子，我声称里面有一幅毕加索的名画，而他们会觉得我是在虚报有一幅毕加索，于是他们就会直接拒赔。各方都在相互博弈，但他们也会获得超级工具。在各类消费级 Agent 身上已经能看到一点这种苗头：我想在这家极难订座的餐厅预订位置，而他们是由人工接听电话，现在由于我每个小时只需要付一美分之类的成本，我就可以对他们发起类似 DDoS 的呼叫冲击。最终他们会意识到自己被 DDoS 了，并加以防范。所以一方面，你如何看待你的对手们——不是你自己的对手，而是你客户的对手？他们如何适应这样一个世界：过去对于 Geico 来说很舒服，他们可以说“你有 2,000 美元的损失”，消费者可能会觉得“虽然我有 2,500 美元的损失，但由于涉及金额不大，以前从未真正需要担心这个问题”。而现在，对他们来说很不幸，但对世界上的“大卫们”——那些真正受到侵害的受害者来说很幸运，现在他们可以反击了。而你们正在为此提供支持。这是一方面。但你也提到了长周期代理（long-horizon agents）。当很多事情实际上都可以由 AI 完成时，法律实践会变成什么样？你之前将其形容为未来的律师几乎就像是数据科学家。但对抗性的博弈过程会变成怎样？由于你的介入，State Farm 和 Geico 可能会使用什么工具？更宏观地看，鉴于你在操纵文字、挖掘事实并完成所有这些工作，而人类在其中的重要性下降，法律行业将如何演变？人类显然在护送案件走向最终结案方面扮演着重要角色，但 AI 会做什么，不做什么？
<details><summary>Original English</summary>

Yeah. and maybe talk about the future of where where things go because um on the one hand I can imagine a world where it's like one of these days Geico is going to get a little bit smarter um and they're probably going to like because they're deny deny deny plan that's how they got smart before right because they realize it is an adversarial system like you know I lost my house in a fire and I'm going to claim I had a Picasso in there and then they're going to think that I'm claiming that I have a Picasso they're just going to deny the claim deny deny Like so each party is kind of fighting each other, but they're going to get superpowers. I mean, you see this playing out a little bit with Muse and all the consumer agents where I want a reservation at this restaurant that's impossible to get and they have a human answering the phone. I can dodo them now that I have to pay one penny per hour or something. And then eventually they're going to realize that they're getting DDoS and they're going to prevent that. So, you know, I guess on the one hand, like how do you think about, you know, your your adversaries here? not not your adversaries, but like your client's adversaries. How are they adapting to a world where it's like, you know, it was great for Geico where they could say, "Hey, you have $2,000 of damages." The consumer is like, "Yeah, I did have maybe $2,500 of damages, but it's like they never really had to worry about that before because of the quantum." And now, unfortunately for them, but fortunately for the Davids of the world, like people that are actually agrieved and and have been victims, now they can fight back. And you're powering that. So that's kind of one thing, but also you mentioned long horizon agents. Um because you know what does the practice of law look like when a lot of the stuff can actually be done by AI? You have I think you you framed it as like the uh the attorneys are almost like the data scientists of the future. But you know maybe talk about like what does the adversary or the adversarial process look like? you know, what what what are the the skate farms and Geico using uh potentially as a result of you entering the scene, but also like how big big question, but how does law evolve and emerge just given that you know you're kind of manipulating words and finding facts and doing all this kind of stuff or like the humans are not as important. Um they obviously have an important role of shephering the case to completion, but like what does the AI do versus not do?
</details>

**>>**: 我的思考框架是：最终当涉及到个人时，他们总是需要法律代理。至于代表工作由谁来做，你可以假设 99% 甚至 99.9% 是由 AI 完成的，但总会保留那一点点人类的温度，对吧？我们坚信人类将对案件的结果产生积极影响。
<details><summary>Original English</summary>

Yeah, I mean ultimately my my framework for thinking about this is ultimately when you have an individual they're going to need representation whether that representation like who does the work on the representation you can assume it's 99% AI maybe 99.9% AI there's always going to be that little bit that is the human touch right and we do believe that people are going to make a positive difference to the outcomes of the of the
</details>

**>>**: 被告方或机构方一直以来的优势在于：他们拥有更多资源，拥有更多资金。他们还拥有更多的时间，当个人负债累累急于支付账单时，拖延时间其实是机构掌握的另一项非常强大的武器。这是他们依仗的优势，他们试图依赖中心化和标准化。而在原告这边，你有一位为你抗辩案件并推动进入诉讼程序的律师，我认为这正是将要发生的事情。我认为会有更多的案件具备实质威慑力，而所有的常规来回沟通，我认为都将通过智能体对智能体的方式进行。虽然这听起来像是一个疯狂的未来世界，但我认为我们正在走向那里。而决定胜负的关键在于：律师对该客户、对该组事实，以及对他们在当地辩护律所面对的对手了解多少，他们利用这些见解为客户争取到不同的结果。我不认为这会消失。事实上我们已经看到，Eve 上的许多客户实际上选择将更多时间花在庭审辩护工作上。
<details><summary>Original English</summary>

And that is exactly what you have, right? So like what you have on the on the defense side or really institution side is what's always happened which is they have more resources, they have more money. Uh they have more time which is actually another weapon they have which is quite powerful when individuals are in in debt to pay their fees. Um and that is a very powerful tool they have and uh that is that is a strength they're working with and they're trying to rely on you know centralization and standardization. On the defense side you have a attorney that is fighting your case and pushing them to get to litigation and I think that is going to be what's happens. I think a lot more cases are going to have teeth and all the routine back and forths I think is going to happen through agents talking to agents. I think that's, you know, it's crazy future world, but I think that's where we're headed to. And the difference maker is what does the attorney understand about that client, that set of facts, um, and their local environment of who they're going up against locally in that law in in that defense firm, and they're using that insight to make a difference for their client. And I don't think that ever goes away. Um it's it's in fact something we're seeing already where many customers on Eve are actually choosing to spend more time on their trial work.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 因为软件让这成为可能。在以前，出庭审判会拖垮你整家律所。
<details><summary>Original English</summary>

>> Because it actually enables that. Previously going to trial took down your entire firm.
</details>

**>>**: 突然之间，你所有的精力都耗费在庭审准备和陪审团面试上。
<details><summary>Original English</summary>

>> Suddenly you're just spending all your time doing trial trial prep, interviewing juries.
</details>

**>>**: 你只希望案子能和解。
<details><summary>Original English</summary>

>> You want things to settle.
</details>

**>>**: 没错。
<details><summary>Original English</summary>

>> Exactly.
</details>

**>>**: 过去更偏向于追求和解的动议。
<details><summary>Original English</summary>

>> It's more of a settlement motion.
</details>

**>>**: 完全正确。而现在，我认为事情正转向真正的实质权益倡导。我该如何把我们的观点传达出去？我的当事人身处绝境，对方做错了事，我该如何在真正对他们重要的事情上代表他们？
<details><summary>Original English</summary>

>> That's exactly right. And instead, I think things are going more into real advocacy. How do I actually make our point known? How do I, you know, my client is against back of the wall. They're doing bad things are doing good things. How do I represent them in what actually matters for them?
</details>

### 数据驱动诉讼与纠纷解决的未来

**>>**: 但我设想，这也是你们正在做的数据科学的一面：拥有这个庞大的、以前可能从未被积累过的数据集。因为正如你所提到的，所有这些都非常个性化定制，过去没有任何关于所有和解金额的公共数据库。我在诉讼金融（litigation finance）领域稍微见过类似的情景：如果我是一名出庭律师，而你作为我的客户并不按小时付我报酬，我该如何支付我自己、我的员工、办公室租金以及所有开销？会有诉讼投资机构出现说：“我来资助这个案件。”我资助这个案件是因为我指望你能赢。他们会使用各种聪明的方法，比如分析法官是谁等等，他们是在使用数据。但除此以外，从历史上看，这些数据从未真正存在于任何地方。而现在有了这些数据，你作为律师就能做出更明智的决定：我是该把它诉诸法庭审理，还是接受和解，或者继续反驳交涉？Geico 开出了 12,000 美元，我应该争取 15,000 美元吗？我应该把它推向法庭，争取赢下 10 万美元吗？我该如何做出这些决定？
<details><summary>Original English</summary>

But I imagine this is kind of the data science side of what you're doing as well with this giant data set that's probably never been accumulated before because as you mentioned all these, it's so bespoke. There's no like communal repository for like all of the settlement amounts. But like I've seen this with litigation finance a little bit where if I'm a lawyer, uh if I'm a trial attorney, and I'm not getting paid by the hour by you, my client, well, where do I pay myself and my staff and my office rent and everything else? Well, there are companies that will show up and say, "I will fund this case." That's right. Right. And I'm funding this case because I'm counting on you winning it. And like they'll do all sorts of clever things like here's the judge and here's this. Like they're using data. So outside of I I think those guys have been very data science forward. But historically like this data just like never really lived anywhere. And now that it does, you can make smarter decisions as an attorney. I'm like, do I take it to trial or do I accept the settlement or do I push back? Oh, Geico offered me $12,000. Should I push back and fight for 15? Should I, you know, take it to trial and try to win a h 100red? Like how do I make those decisions?
</details>

**>>**: 完全正确。这就是为什么我们能帮助他们在每一个案件中做出最佳决策，并知晓何时达到了最优结果。
<details><summary>Original English</summary>

That's exactly right. That's which is why we can help them make the best decision in every single case. and know when an optimal outcome has been achieved.
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 而且我认为进一步推进案件依然是律师的职责所在，对吧？这就是我所说的类似数据科学的工作。
<details><summary>Original English</summary>

>> And it's still I would say it's still the attorney's responsibility to push it even further, right? And I think that is what I meant by data science like work because
</details>

**>>**: 你是在利用软件的力量去完成你以前甚至从未想过要做的分析工作，从而改善案件的结果。
<details><summary>Original English</summary>

>> you're using the power of software to do work you never even thought to do to improve the outcome.
</details>

**>>**: 这当然是一个非常宽泛的问题，但你认为整个法律体系将走向何方？我之前在富国银行遇到了一些麻烦，我想：我都试着处理了四个小时了，干脆起诉他们算了。于是我打开了基于 ChatGPT 的代码工具，我说：起诉富国银行。四个小时后，它起草完成了起诉书，还实际找到了一名法律文书送达员。我收到了立案通知，我们要对簿公堂了，但开庭日期排到了二月。在专利法领域也发生着类似的事情：过去申请专利需要耗费大量工作，现在申请的工作量减少了，但美国专利商标局（USPTO）依然是瓶颈所在。如果你来预测一下，随着 AI 成为标配，整个法律行业将走向何方？你显然是在为原告法领域提供这种能力，但如果考虑整个法律执业，如果快进 5 年，它会变成什么样？哪些会保持相似，哪些会发生改变？
<details><summary>Original English</summary>

And I mean where do you think this is a very broad question of course but like where does the legal system go? I was having some some trouble with Wells Fargo and I'm like you know what I've tried like for four hours to do this. I'm just going to sue them. So, I went to CodeEx, you know, Chad GBD. I was like, sue Wells Fargo. Four hours later, it had sued Wells Fargo. It actually found a process server. Um, I got the notice of SE like we're going to court, but you know, the date is in February. Like another kind of similar vein is happening with patent law where before it's so much work to go file a patent. Now, it's less work to file a patent, but you still have the USPTO, which is the bottleneck. So I guess I mean if you were to prognosticate like where does the legal industry go now that AI is becoming table stakes and you're delivering you're you're part of that table obviously for plaintiff law but if you think about the entire practice of law in general like how does it change if you were to fast forward 5 years what does it look like what's similar what's different
</details>

**>>**: 很大概率上，我认为不可避免地需要建立一套不让所有纠纷都涌入法院系统的机制。在法律领域这本身就已经是成熟的框架，比如退伍军人事物的某些案件会通过专门的委员会处理；在劳动和雇佣领域，很多案件在进入法院之前要先经过平等就业机会委员会（EEOC）；雇主们也探索出了各种调解和仲裁方式，不一定非要走法院程序，对吧？这是一个自然演化的框架，我认为这种情况会越来越多。我认为将发生的微调在于，对于其中的某些细分领域，我们可能会采用某种自动化争议解决机制（ADR），由具备 AI 能力的调解员或对双方持中立态度的中立机构利用 AI 大大加速形成裁决的过程。我不认为最终的裁判会被取代，但他们将获得一组客观事实，展示历史上这类事件是如何发生和处理的。而消除可能存在的偏见则取决于他们。我认为我们会把越来越多的时间花在这类纠纷解决上。
<details><summary>Original English</summary>

most likely I think it's inevitable that you're going to have to create systems where not everything goes to the court system and this already is a framework that is used in law, right? Like I mean for some types of uh veterans affair cases that goes through a different committee for even labor and employment that goes through EEOC in a lot of cases before it goes through uh and you know employers have figured out different ways to mediate and have arbitration that doesn't necessarily go through the court system, right? And this is this is the framework that actually naturally evolves. And I expect that to happen more and more. And I think the tweak that's going to happen is that for some pockets of it, we're probably going to go through some version of like ADR, automated dispute resolution where AI enabled mediators or central parties that have a neutral view of both sides are going to use AI to really speed up how they come up with judgment. And I don't think the judgment will really be replaced, but what they will get is a set of facts that shows historically here's how this happened. Here's how this happened. And it's up to them to remove the biases that might exist. And I think we're just going to spend more and more time on that side of things.
</details>

### 律所规模分化：专业化深耕与并购整合

**>>**: 你认为小型律协会变大吗？因为这是另一种可能：如果我每位律师过去只能处理 100 起案件，现在能处理 500 起，未来可能处理 5,000 起。那我为什么还要把办公室局限在新泽西州一个非常非常小的地点？也许我应该扩张得更广。未来会不会出现大型的、类似企业实体的律所？最大的出庭诉讼律所好像是 Morgan & Morgan，对吧？他们的年收入达到数十亿美元，但普通律所规模相当小。但可以想象，在 Eve 和这些变革的赋能下，小律所实际上也可以发展成数十亿美元营收的企业。这有点像风投期待的结果与所谓的“生活方式型企业”（lifestyle business）之间的对比。你曾经做过风险投资人，所以你知道这个词，这是一个稍微带点贬义的词，用来指代能产生利润的小生意。但你认为这是一种合理的预测吗？这些本地的夫妻店式律所有可能成长为非常庞大的机构吗？
<details><summary>Original English</summary>

And do you think the small law firms get bigger? Because that would be the other thing. It's like if I could only handle a 100 cases per attorney, now I can handle 500, but in the future maybe 5,000. you know, why do I limit my office to like a very very small New Jersey location? You know, may maybe I should go more broad. Um, and you're going to have kind of larger almost like corporate like law entities and like I I think the biggest trial attorney firm is Morgan and Morgan. Is that right? Um, and they have billions of dollars in revenue, but your average firm is is quite small, but you could imagine powered by Eve and with all the changes that we're talking about, it's like the small firm could actually become a billiond dollar revenue business. Um, it's kind of like venture outcomes versus kind of like what what you would call lifestyle business. You were a VC once upon how you know that term. Uh, some somewhat porative term for like you make profits. Um, but [laughter] how do you think like is is that a reasonable take that like some of these small guys can actually I mean obviously you can't go public as a as a law firm for now uh maybe in Arizona or something you can but um uh how do you think there's a chance for some of these local mom and pop uh stores if you will to become very very large institutions?
</details>

**>>**: 我认为将要发生的转变是，许多这类律所会变得更像软件公司。我认为他们终于要参与到过去 30 年他们一直被排除在外的软件革命中来了，对吧？如果深入剖析，你就会理解其中的原因：假设你拿到了一笔 25,000 美元的和解金，律师通常能拿到大约三分之一，为了计算简便就算是 8,000 美元吧。在这 8,000 美元中，大约一半用于人力支出，30% 用于市场营销，剩下的可能就是利润。这就是目前行业的商业模式。由于这种商业结构，你极难将资金重新投资于更好地为下一位客户提供服务中，对吧？过去你能做到这一点的唯一途径就是雇佣更优秀的律师，对吧？
<details><summary>Original English</summary>

I think the transformation that's going to happen is a lot of these law firms are going to look more like software companies. I think they're going to finally participate in the software revolution that's been happening for the last 30 years they've been left out of, right? Um, and if you if you kind of deep dive, you'll understand why. Let's say you have a $25,000 settlement. The attorney gets maybe a third of that. Uh, let's call it 8,000 for simplicity. Uh, and you know, like of that 8,000 about half of it goes towards labor spend, 30% goes to marketing, and the rest maybe is profit, right? like that. That's kind of the business as it exists today. Because of that business, it is so difficult to reinvest back into servicing your next client better,
</details>

**>>**: 对。
<details><summary>Original English</summary>

>> right? Like the only way you can really do that is by hiring a better attorney today,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>

>> right?
</details>

**>>**: 改变在于，现在他们实际上可以积累一套属于他们自己的独特数据库和数据集，使其在某个法律细分领域取得优于竞争对手的结果。这是一种专业化。历史上这个行业已经经历过类似的过程：大约 30 年前，有社区律师负责处理所有事务，从劳动用工到知识产权等等。
<details><summary>Original English</summary>

>> What changes is now they can actually acrewue a database and data set that is unique to them that gets them results that is better than their competitors for a subset of law, right? And this is kind of specialization and historically this industry already went through that you know like 30 years ago there was a uh you know your neighborhood lawyer that handled everything you know from from employment cases to IP to what have you. Yes.
</details>

**>>**: 是的，没错。
<details><summary>Original English</summary>

>> Exactly.
</details>

**>>**: 后来出现了执业领域的细分。有人特别擅长知识产权，有人特别擅长雇佣劳动。而现在分工正在变得更加精细，比如有人专精于护理出生缺陷案件或类似的方向。我可以预见到这会再深入一个层次：有人可以在涉及特定 X 和 Y 事实模式的软组织损伤案件上变得极其专业，针对这些具体案件做广告可能比像 Morgan & Morgan 这样的大律所把广告牌铺得到处都是要划算得多。
<details><summary>Original English</summary>

Exactly. And and now what we have are specializations of practice areas. You have someone that's really good at IP, someone that's good at employment. And now it's getting even more specific, right? like someone that's good at let's say nursering birth defects or or something along those lines and I can anticipate that to go even another level where now someone could get really good at soft tissue injury cases that involve X and Y fact patterns and it advertising for those cases might be a lot more cost effective than some other larger firm like Morgan Morgan
</details>

**>>**: 先在本地精通某一领域，然后向全国扩张，因为你在该细分领域拥有极高的专业胜任力。
<details><summary>Original English</summary>

>> just showing their billboard everywhere. So get good at something locally and then expand just across the entire country because you have such high competence around that one field.
</details>

**>>**: 完全正确。所以我认为我们会看到那种专业化分工，同时也会看到相反的趋势：一些大型律所正在整合，我们也在与达到 Morgan & Morgan 规模的客户合作。那些已经做大的律所正在到处收购其他律所，因为他们意识到借助 Eve，他们可以非常迅速地整合过去极其痛苦的并购重组流程。现在整合可以完全围绕客户的需求展开——客户要的是法律结果，而 Eve 正是为此而生。
<details><summary>Original English</summary>

>> That's exactly right. And we're so I think we're going to see that type of specialization and I think we're also going to see the opposite where some of the large we're also working with some on the scale of Morgan Morgan like some of them actually are coming together. So those ones that got us big are actually going around buying other law firms because they realized with Eve they can very quickly consolidate what used to be very painful reintegration process now it can be done on exactly what the client wants which is hey the client wants a legal outcome and EV is made just for that.
</details>

**>>**: 是的，通过这种方式，他们很大程度上摆脱了大量的组织变革管理、人员编制变动和运营调整，因为 Eve 替他们处理了其中的大部分工作，从而加速让收购产生回报。
<details><summary>Original English</summary>

>> Yeah. So by doing that they get to largely work away from a lot of the change management uh workforce changes operation changes because Eve handles a lot of that for them. They can speed up their time to making that acquisition worth it.
</details>

### 从按席位付费到结果导向定价

**>>**: 有趣的是，目前正在掀起一股转向结果导向定价的浪潮。过去的 SaaS 软件通常是按每人每月计费。我过去常开玩笑说，这就像软件销售中的“中杯、大杯、超大杯”星巴克模式。你去任何一家 SaaS 公司的网站，这也是为什么 Claude 可以轻易克隆它们的原因，因为它们看起来都一样：每月 79 美元、每月 99 美元、每月 129 美元，中杯、大杯、超大杯。以前都是按人头席位收费。再看看像 Zendesk 这样的公司，在最后一次作为上市公司时拥有 20 亿美元的 ARR，后来被私募机构 Permira 和 Hellman & Friedman 私有化了。现在大家会问：你究竟需要多少个席位？也许是零个，我们需要的是交付结果。所以软件界的所有人、很多 AI 公司都宣称“我们交付结果，我们按结果收费”。有趣的是，你们所聚焦的原告法律形式从一开始就一直是结果导向的。但也有其他非结果导向的法律类型，我敢保证所有客户都会更希望它是基于结果收费的。当然有时这很微妙，比如我在 McDermott Will & Emery 有一位信托与遗产律师，她非常优秀，但收费极其昂贵。我这边的最终结果是我去世，所以我不知道我是不是真的想要那个结果。但你肯定更希望固定收费。为律师辩护一句，按小时收费的原因并不全是为了敲诈客户，而是因为我脑海中的想法与我的表达方式之间存在数据不对称，项目的范围可能会随着时间而改变。但我认为其他形式的法律可能也应该更像原告法，也应该采取结果导向的定价，对吧？或者像移民法也应该结果导向，一切都应该转向结果导向定价。但这很难，因为在“我将如何代表被告赢得这场官司”方面存在数据不足。你怎么看法律在更大范围内的变化？我觉得原告法领先于我们现在看到的一切：每个人都想要结果，没有人愿意为原料或投入买单。这可能是唯一一个从一开始就始终坚持结果导向的商业领域，其他法律领域不也应该这样运作吗？
<details><summary>Original English</summary>

>> Well the funny thing is that there's this movement underway to outcome oriented pricing. So like software SAS used to be per seat per month. Um and I used to joke it was like the tall grande venty model of software selling. It's like you go to like any SAS company's website. This is why, you know, Claude can clone them all so readily. They all look the same. It's like $79 a month, $99 a month, $129 a month, you know, tall ground venty. Um, and it was per seat. And like look at a company like Zenesk, which had $2 billion of ARR when they were last a public company. They were taken private by Premier and Helman and Freriedman. And now they're like, uhoh, how many seats do you need? Like maybe zero. We we need to deliver outcomes. So everybody in the software world uh is kind of like in a lot of AI companies like we deliver outcomes. we charge for outcomes. The interesting thing is that the form of law that you focused on was always outcome oriented from the very beginning. Um, but you have other types of law that are not outcome oriented where I guarantee all the clients would much much much prefer that it was outcome based, right? I mean, sometimes it's tricky like I have a trust in estate attorney at McDermott Will and Emory. She's very very good. She's like so expensive. Like I guess my outcome the outcome is my death. So I don't know if I want that. But, you know, you would prefer to just say like there's a fixed cost, but there's often this data uh, you know, in in their defense, the reason to charge by the hour is not so much to rip off the client, but there's data asymmetry between what I want in my head and how I articulate it. Maybe the the the scope of the project is changing over time, but you know, other forms of law, I would argue they probably should look more like plaintiff's law. They should have outcome oriented pricing as well, right? or like immigration law that should be outcome oriented like everything should be outcome oriented pricing but it's hard because there's a data deficiency if you will in terms of like how will I win this case on behalf of the defendant but I guess like how do you think other forms of like you could probably expand well beyond plaintiff law um I don't know if you agree with me but like how do you think about just like law in general changing because I kind of feel like plaintiff's law was like ahead of everything that we're seeing right now it's like everybody wants outcomes nobody wants to pay for the ingredients or the inputs. Um this was the only kind of field probably of business where it's like it was always outcome oriented but kind of shouldn't other parts of law work that way?
</details>

**>>**: 这也正是我们的信念。困难之处在于：当你在被告方甚至原告方处理一个新案子时，你不知道它是需要 10 个小时还是 100 个小时的工作量，很多时候接手之前你真的无法预料。对于原告法律，这就是为什么我们必须如此深入地扎根到每个执业领域去实现成果。去年我们就在做现在被称为“长周期代理”的事情，那是为了取得成果所必需的。为了实现法律的普及民主化，最终需要达到的状态是：根据一组既定事实，你能推算出需要多少算力资源才能得出结果。这需要通过聚合和更好地使用数据，以及更有效地运行算力来实现。所以我们两方面都在做。我们高度聚焦于结果。这种“大卫战歌利亚”的局面在各地都在发生。不仅仅是在大律所或企业内部法务，那些只是预算充足的地方，他们可以开出间歇性的空白支票，而“这到底值多少实际结果”的倒逼机制并不明确。就像你去融资时可能会收到一张 10 万美元的法律账单，这笔钱对应的确切产出是什么很难衡量，但这是他们今天唯一定价的方式，因为他们不知道自己工作的实际预期价值是多少。
<details><summary>Original English</summary>

That is our exact belief as well. Right. So like the the hard part has been it is hard. You know when when you're on the defense side or even the plaintiff's side the question around a new case is it 10 hours of work, 100 hours of work. In many cases you really don't know until you take it on. Um and for plaintiffs that is why we had to go so deep into each practice area into achieving outcomes and you know we were doing what is now coined long horizon agents like last year that's just what was needed to drive results and now it's getting better and better to actually drive legal outcomes and ultimately I think what is needed for democratizing of law is from a set of facts you need to know how much compute resources you need to arrive at a outcome. And that happens through both aggregation of and better usage of data and better usage of actually running the compute to achieve set outcome. And so we're doing both right. So like that is why we're laser focused on outcomes and we want to drive outcomes. And eventually this David versus Goliath uh thing is happening everywhere. You know it's not just in in uh you know big law or in-house legal. Those are just where the budgets are. So they actually can write basically a blank check for intermittent period of time and the the forcing function around how much is this actually worth in outcomes to me is not known right like I mean you know this like when you go fund raise you might get hit with like a 100k check what is the exact outcome of that uh you know like it's very hard to know what the value is but that is the only way they can price today right um and that's because they don't know what the expected value of their work actually is.
</details>

**>>**: 这也是不对称性所在。比如你需要为 C 轮融资聘请律师，这可能非常简单，也可能非常复杂，因此很难给出固定费率。
<details><summary>Original English</summary>

>> Well, that's the asymmetry as well. It's like I don't know. It's like, okay, you need to hire a lawyer for your series C. And what does that mean? Well, it could be like very very simple. It could be very complicated. So, it's very hard to have a flat rate.
</details>

**>>**: 没错。
<details><summary>Original English</summary>

That's right.
</details>

**>>**: 因为律所可能会亏损。如果收费偏低他们不会亏，比如收你 25,000 美元而只花了一个小时；但如果需要耗费 4,000 个小时的律师时间，他们就会亏钱。正如你所知，在公司法中，这些往往是亏本引流产品（loss leader），然后再通过后续的并购或 IPO 赚回来。但这与原告法有些不同。你们是如何收费的？你们的收费模式是如何演变的？刚创业第一天你们肯定不知道该向哪类客户收多少费用，你们的思考肯定也经历过演进。
<details><summary>Original English</summary>

Um because they could get burned in Well, they can't get burned in the low direction. Right. It's like I charge you $25,000. I spent an hour on this, but they could get burned if it's like I have to now spend 4,000 hours of attorney time. I could lose money on this. which of course every single firm they oh well actually like as you know in corporate law these are loss leader products and then you try to make it up on the M&A or IPO or something but obviously a little bit different than plaintiff law. How do you guys charge? How did you because I imagine you had a it's not like on day one when you started the business you knew exactly what you were going to charge for like what type of customer. I imagine your thinking has evolved on this as well.
</details>

**>>**: 当然。其实说来也奇怪，从第一天起……
<details><summary>Original English</summary>

>> Absolutely. Okay. So, I mean from actually, weirdly enough, from day one,
</details>

**>>**: 你们一开始大概也是那种“中杯、大杯”模式吧。
<details><summary>Original English</summary>

>> we started probably with the with the uh you know, uh what was it? Tall grande.
</details>

**>>**: 星巴克中杯、大杯、超大杯模式，是的。
<details><summary>Original English</summary>

>> Tall Grande Venty. Yes,
</details>

**>>**: 超大杯模式。我们一开始确实是那样做的，因为当时我们也不懂别的模式，对吧？然后随着我们不断深入，我们意识到他们真正在意的是结果，在意的是如何服务更多客户。这促使我们在非常早期——大约一年半以前——就转向了基于结果的模式。在今天的 AI 时间里，一年半可以说是很久了。
<details><summary>Original English</summary>

>> Vente model. Uh that's that's what we started with because we didn't know any better, right? And then as we dug into it, we realized like what they care about is outcomes. What they care about is how do I serve more clients? So, that actually forced us to be outcome based from very early days. uh you know we're talking like a year and a half ago which is pretty funny that's early uh in today's world
</details>

**>>**: 相当于狗年的 100 倍。
<details><summary>Original English</summary>

>> AI time like [laughter] dog years times 100 yes
</details>

**>>**: 没错。但那就是我们的发展历程。这里有巨大的增长空间：我们谈到了那个价值分配图，三分之一给律师，其中一半是人力开销，而这原本需要花费的一半成本现在不需要再支出了。如何把它转化为更有用的东西？最有效的方法，就是奇妙地把它花在更多的 token 以及 Eve 可以完成的工作上，以此为律所赚取更多的钱，对吧？这就是我们今天所处的循环。推动我们的市场动态也正是如此：按可计费工时收费的模式虽然不会完全消亡，但会走上按席位定价的老路；对于某些细分法律领域，按工时收费可能是最好的方式，因为可能要过很多年才能知道最终结果的价值，但对于许多法律领域来说已经不再是这样了。在很多领域你其实知道结果是什么，你应该能够把工作分摊平减为一个折旧常数并予以交付。这就是我们所押注的。正因如此，我们从第一天起就专注于端到端地交付法律成果，并且让这一切变得足够简单：律师只需要说“这是我刚接的客户，交给 Eve”，Eve 会在需要时拉你介入，其余的就可以放心交接。
<details><summary>Original English</summary>

>> exactly um but that that is that is kind of um what happened to us right and there's so much room to grow where now that you know we we talked about that that value diagram of a third goes to attorneys half of that is labor that is half they don't have to spend anymore right so how do you actually turn that into something more useful and that way the best way to get more useful work is actually to spend it weirdly on more tokens and more more work that Eve can do to make more money for your firm, right? And that is kind of the cycle we're in today. And a lot of the market dynamics that is helping us is exactly this. Like we actually believe the uh billable auto model, I don't think it's going to die completely, but I think it's going to be on the way of the seatbased pricing model. uh where for some subset of law that is probably the best way you can charge for the work cuz it's very difficult to know value until an outcome many many years later. But for a lot of it that's not true anymore. You know for for a lot of it you actually know what the outcomes are. Um and you should be able to take your work down to an amortized amount and deliver that back right. uh and that is what we are betting on right and this is why we focused on delivering legal outcomes from day one end to end and doing that in such a way that it is as simple as a lawyer saying here's this client I got in give it to Eve Eve will pull you in when you're needed and you're good to go
</details>

### 端到端案件闭环与工程挑战

**>>**: 原告律师受到的是供给制约而非需求制约，他们有着源源不断但由于成本与获客价值测算不划算而无法服务的客户。对于你们自身而言，制约因素是什么？是什么阻碍了你们以更快的速度增长？你们显然增长得极快，你们的限速指标是什么？作为输出，你们需要什么样的投入才能跑得更快？
<details><summary>Original English</summary>

where like see we we've talked about how uh plaintiff attorneys like they are they are supply constraint not demand constraint or many of them are because they have this infinite influx of of clients that they can't serve because the math doesn't really work in terms of, you know, cost versus, you know, CAC versus LTV. It's the the old fashioned thing for any business applies to them as well. You know, where where are your constraints? Like what what kind of holds you back from growing faster? I mean, you're obviously growing incredibly fast. What are your rate limiters? Um what what do you need as inputs to grow faster as an output?
</details>

**>>**: 很多法律测试基准——包括 Anthropic 和 OpenAI（我们与他们中的许多人保持着非常紧密的合作）公开分享的基准——往往非常关注单一结果，比如给出一项任务，看它完成得是否大致过关。而世界现在正在转向代理型任务。对我们来说，唯一重要的始终是代理型结果。目前的科技和流程阶段，每个案件仍然需要相当数量的人工介入，但随着工作深入，我们每个月都在大幅减少这种人工介入。在我们的行业中，我们需要针对每种案件类型都做到这一点。对于每一种案件类型，我们都像做科学研究一样去钻研：如何真正解决这类案件？如何构建一个能够将所有这些数据点处理至结案、全流程推进、并调用包括 Claude 等在内的所有可用工具达成结果的“微型律师大脑”？这是一个非常困难的问题。所以目前我们在很大程度上受限于工程研发人员。我们有无数的事情可以去做来向前推进。另一个令人兴奋的地方是需求端：一旦我们能够端到端解决机动车交通事故案件，为全世界释放的价值就达数千亿美元，而这仅仅是一个细分类型。
<details><summary>Original English</summary>

You know it's it's really fascinating because a lot of the legal benchmarks like even benchmarks that you share publicly that anthropic openai many of whom we're working very closely with are working on care a lot about like almost single outcome right like here's a task did it kind of do mostly okay and the world is now moving into agentic work for us the only thing that ever mattered was the agentic outcomes right so like now all that is getting more and more the end outcome here is Today we're still at the point with technology and and processes where there's still a decent amount of human touches needed per case, but by doing more and more work, we've been drastically reducing that month over month. And in our industry, we need to do that per case type, right? So like for every single case, we're learning that like a science. Like how do you actually resolve this case and how do you build a mini attorney brain that is capable of crunching all these data points to that resolution and driving it across the board and working with all the tools they have access to including cloud and whatnot to drive that outcome. And that is a really hard problem. Right? So we're largely limited by engineers at this point. like we have a limitless number of things to do to drive this forward and the other fun part is we have demand the moment we are able to deliver on let's say moving vehicle accident cases end to end the amount of value that gets unlocked for the world from that is in the hundreds of billions of dollars and that's just one subtype
</details>

**>>**: 这是一个很好的问题：你们是否已经实现过完全自主的端到端案件闭环？比如接听电话、导入客户、从 Geico 拿到赔偿支票，全流程端到端跑通？还是说……
<details><summary>Original English</summary>

>> actually that's a great question have you had a fully autonomous endto-end case it's like answer phone onboard client you know get out get check from Geico, you know, like has that happened end to end or like
</details>

**>>**: 目前还没有，但已经很接近了。这也是为什么我们需要工程师。举个例子，一个案件中大约会发生 10,000 次来回交互。大概有 10,000 次，因为你想想看：一个客户进来了，假设是一个人身伤害（PI）案件，会涉及到医疗记录，于是你必须主动打电话给保险公司和医疗机构，调取客户既有的医疗记录。这项工作今天通常需要两周时间。而有了 Eve 的外呼代理，我们拥有可以通过语音 AI 进行呼叫的外呼智能体。有趣的是，在这个领域我们已经看到智能体与其他智能体互相通话，并学习如何突破彼此的阻拦，这很有意思。这只是所需的一步，然后你必须生成文件，并与对方进行实质沟通。所有这些都是我们正在端到端完成的任务。目前仍然需要少量人工介入来优化结果或提供更完善的协助，但我们目前正在构建的核心正是如何完全端到端地推进这整套流程。
<details><summary>Original English</summary>

>> not not yet, but we're close. Uh that is what that is why we need the engineers, right? So like to put things in perspective, a single case has probably 10,000 back and forths. 10,000 something like that because wow, here's how you think about it, right? A client comes in, let's say it's a PI case. Now you have medical records. So now you have to actually outbound call insurance companies and healthcare companies to get hold of the records that the the clients already had, right? So like that is actually that takes two weeks today. And with Eve outbound agents where we actually have voice AI that can do the outbound call and funnily enough that's an area where we're already seeing agents talking to other agents and learning how to get past each other which is hilarious. Um and that is like one step that's needed, right? Right? And then from there you have to then create a document and actually have a conversation with the other side. So all of this are tasks we are completing end to end. So today there's a little bit of touch required where someone makes an outcome better or um does something a little better but exactly what we're building right now is how do you actually drive this whole thing end to end. Yeah.
</details>

### 对抗策略的反制与规模愿景

**>>**: 我们已经看到了早期迹象，它已经在部分客户那里实际运行了。回到被告方以及他们庞大的信息系统，你是否看到他们整体的反应有所改变？比如对方可能会意识到“糟糕，这些人带着这种材料联系了我，我必须尽快和解”，因为他们通常有着非常固定的规则，不会随心所欲凭空编造，毕竟他们每年要处理成千上万起甚至更多的案件。如果我是 Geico，面对提出的诉求，我的初次尝试通常是压在这个价位和解；但如果原告的成本下降了，这种动态是否会改变？你是否观察到你客户的对手方在反应上有什么变化？
<details><summary>Original English</summary>

>> And we we seeing early signs of that where it's actually live in some customers. And have you seen going back to the defense side and their colossus of of information, have you seen their reaction just in general change? So, as an example of that, it's like, uhoh, these guys contacted me with this. I always need to settle because they probably have like pretty firm rules about this. They don't just like randomly make it up as you go, I would assume, because they're dealing with this tens of thousands of times, if not more, per year. So, if I'm Geico, it's like, oh, you demanded this much. Well, my first attempt is going to settle here, but like if their costs go down, maybe that changes, right? So, have you seen any change in reaction of your, you know, not your counterparty per se, but of your client's counterparties?
</details>

**>>**: 我会说在很大程度上，被告方目前仍然非常依赖按小时计费的商业模式，因此他们还没有完全跟上我们律师的发展步伐，这里存在着很大的定价不对称性。在我们合作的一家律所中，被告方过去的惯用伎俩是：特意将证据开示（discovery）请求的截止日期推迟到感恩节或重大节假日前一天发出。
<details><summary>Original English</summary>

I would say largely still, uh, the defense side very much still works on an hourly business model. So, they haven't quite caught up to the same pace as our attorney. So, like there's a lot of, I guess, pricing asymmetry here. What defense used to do for this one one law firm that we're working with is they would wait they would push out discovery request dates until a day before Thanksgiving or a major holiday, right?
</details>

**>>**: 然后选在那个时间点发送开示请求，因为他们知道对方律师要去度假，在假期中会被沉重的工作量压得脱不开身，要么做不好，要么仓促应付。
<details><summary>Original English</summary>

>> And then send discovery there because they would know the person would go on vacation and be stuck with all this workload over that vacation and they wouldn't do a good job at it or would rush it.
</details>

**>>**: 因为这是对方屡试不爽的招数，这家律所于是在 Eve 上创建了一个智能体，在当天就能做出答复。当下一次这种请求再次寄达时，智能体立即做出了回应，被告方顿时感到震惊：这里到底发生了什么？
<details><summary>Original English</summary>

And now what they used they because it was such a repeated tactic by them they created an agent on Eve to respond the same day. So next time this came through like they responded immediately with the responses and the defense were like what is going on here? [laughter]
</details>

**>>**: 是的。
<details><summary>Original English</summary>

>> Yeah.
</details>

**>>**: 这种策略失效了。
<details><summary>Original English</summary>

>> The tactics don't
</details>

**>>**: 我们看到很多类似的变体正在发生，这促使被告方开始意识到：“等等，当另一方也拥有充裕资源时，就会发生这种局面吗？天哪。”看到这种变化真的很有趣。
<details><summary>Original English</summary>

>> and and like we're seeing there's so many variants of that that is happening now which is causing um defense to realize wait is this is what happens when the other side has resources. Right. Oh crap. Right. and and that's that's what's fun to see.
</details>

**>>**: Jay，这是一次非常精彩的对话，我学到了很多。之前我没意识到每一个案件需要经历 10,000 次沟通交互。非常引人入胜，我也非常荣幸能成为你们的合伙人，期待把 Eve 带给接下来的 10,000 家律所。
<details><summary>Original English</summary>

>> Well, Jay, this is a fantastic conversation. I learned a lot. Um didn't realize there were 10,000 touches every time you went through a case, but uh really fascinating and delighted to be your partner. Um and bring Eve to the next uh the next 10,000 firms.
</details>

**>>**: 谢谢你。我们还有很长的路要走。今天我们可能已经帮助了几十万名客户，未来还有数以亿计的人需要我们去触达，我希望每天都能为他们的生活带来改变。如果大家对此感兴趣，欢迎加入 Eve。
<details><summary>Original English</summary>

Thank you. I mean, we're we still have so much more to go. Uh we've probably helped a couple hundred thousand clients today and we have hundreds of millions to touch and I would love to be making a difference in their life every day. So if that's of interest, please come join Eve.
</details>

**>>**: 太棒了，谢谢你。
<details><summary>Original English</summary>

>> Awesome. Thank you.
</details>