---
author: Norges Bank Investment Management
date: '2026-10-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=URbbqirdIT0
speaker: Norges Bank Investment Management
tags:
  - recommendation-system
  - dating-algorithm
  - generative-ai
  - corporate-turnaround
  - gen-z-culture
title: 专访Match Group CEO斯宾塞·拉斯考夫：揭秘Tinder算法逻辑、Z世代约会变革与企业文化逆转
summary: Match Group首席执行官斯宾塞·拉斯考夫深入拆解了Tinder背后的Rex Algo推荐机制、实时重排升级与情境化点赞；剖析了Z世代约会心理与全社会孤独流行病，阐述AI在安全与档案润色中的赋能；并分享了他清空产品线、重塑创新容错文化的管理哲学以及给年轻人的奋斗箴言。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Match Group
  - Tinder
products_models:
  - Rex Algo
  - Hinge
media_books: []
status: evergreen
---
### 序言与约会哲学：每个人都有属于自己的另一半

**尼古拉·坦根**: 你总不想和一个**输家**约会，对吧？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: You don't want to date a loser, right?

</details>

**斯宾塞·拉斯考夫**: 嗯，我们坚信**每个人都能找到适合自己的人**，所以我从不做评判。世界上根本没有所谓的输家。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Well, there's, you know, we believe there's someone for everyone, so I don't pass judgment. There's no such thing as a loser.

</details>

**尼古拉·坦根**: 这算是你们的商业模式吧。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's kind of your business model.

</details>

**斯宾塞·拉斯考夫**: 世上真的没有输家。他们只是还没有遇到那个对的人而已。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: There's no such thing as a loser. They're just somebody that hasn't met their their right person yet.

</details>

**尼古拉·坦根**: 听起来……听起来非常棒。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's that sounds that sounds really good.

</details>

**尼古拉·坦根**: 大家好，我是**挪威主权财富基金**（Norwegian Sovereign Wealth Fund）首席执行官**尼古拉·坦根**（Nicolai Tangen）。今天与我同行的嘉宾非常特别，他是**Match Group**的首席执行官**斯宾塞·拉斯考夫**（Spencer Rascoff）。Match Group正是**Tinder**、**Hinge**以及十余款其他约会应用背后的母公司。

大家不妨思考一下：当今年轻情侣中，有**40%**是在网上相识的，既不是通过朋友介绍，也不是在工作场所认识。可以说，这是人类有史以来目睹的**最大人类行为转变**之一。而斯宾塞正身处这场巨变的中心。作为一名略带局外人视角的行业新领导者，他在一年半前接掌Match Group之前，曾亲手缔造了房产巨头**Zillow**。我们挪威主权财富基金持有Match Group 1%的股份。因此，斯宾塞，我们一直在为你加油鼓劲！

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Hi everyone, I'm Nicola Tangan, the CEO of the Norwegian Soan Wealth Fund. Today I'm joined by somebody really special, Spencer Roskov, the CEO of Match Group. That's the company behind Tinder, Hinge, and around a dozen of other dating apps. Now, think about it for a second here. 40% of couples today meet online, not through friends, not at work. So, this is one of the biggest shifts in human behavior that we have ever seen. And Spencer, he sits in the middle of it. a bit of an outsider. He built the property giant Zillow before taking over match a year and a half ago and we in the Norwegian southern wealth fund own 1% of match. So we are cheering you on Spencer.

</details>

**斯宾塞·拉斯考夫**: 非常感谢。得知你们的支持我感到十分高兴，非常感谢你们的信任，也谢谢你邀请我来参加节目。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Thank you. I am glad that you are. I appreciate it and thank you for having me.

</details>

### 推荐算法底层演进：卡牌重排与实时推荐系统

**尼古拉·坦根**: 那么，在底层技术上，匹配究竟是如何生成的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Now how are matches actually made?

</details>

**斯宾塞·拉斯考夫**: 我们拥有一套**推荐算法**（Rex Algo），它负责计算应该把谁展示给谁。我最喜欢的比喻方式是：桌子上摆着一叠叠扑克牌。想象一下桌子上有10叠牌，每叠各有52张牌。每一叠牌的展示顺序，其实已经由我们根据与不同用户类型关联的特定规则预先确定好了。

例如，可能会有一叠牌专门为了按特定顺序展示人选而优化，本质上是为了留存付费用户、维持他们的商业变现；也可能会有另一叠牌专门面向首次使用的新用户，旨在基于新用户行为来拉动互动留存；此外还有针对各种不同目标设定的牌叠。

我们最近所做的一项重大变革，称之为**队列统一化**（Q Unification，Queue Unification）——我们将所有这些分散的牌叠合并为一整套，然后重新对卡牌进行智能排序。这一改进极大地提升了推荐的质量，直接反映在匹配数、聊天量以及互动火花（Sparks）的显著增长上。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: We have a recommendation algorithm the Rex Algo which tries to figure out who to show to whom. The way I like to think about it is um there are decks of cards kind of on the table. Imagine 10 decks of cards on this table with 52 cards each. The order of each deck has already been determined by us based on certain rules associated with each user type. Like there might be a deck that is optimized to show people in a particular order um to um uh keep to to keep them as a payer essentially to retain their you know their monetization. There might be another deck for firsttime user to drive engagement based on first-time users. There might be all these different goals. What we've recently done was we've done what we call Q unification where we've combined all of these decks into one and then res resorted the cards and that's radically improved the quality of recommendations as measured by matches and chats and sparks.

</details>

**尼古拉·坦根**: 那么这里面具体发生了什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And so what exact So what exactly has has happened there?

</details>

**斯宾塞·拉斯考夫**: 从本质上讲，我们根据对你的了解，并对比过去表现出类似行为的其他用户数据，对一个庞大得多的候选池顺序进行了深度**定制化与个性化重排**。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, we've basically customized and personalized the order of a much larger stack based on what we know about you as compared with other people who have exhibited similar behavior to you in the past.

</details>

**尼古拉·坦根**: 这是基于我喜欢谁而计算的吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And is that based on who I like?

</details>

**斯宾塞·拉斯考夫**: 是的，完全正确，正是如此。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Yes, exactly. Exactly.

</details>

**尼古拉·坦根**: 所以如果某个人喜欢红头发的人，系统就会展示给他很多红头发的人？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So if I So if somebody likes people with red hair, they see a lot of red hair.

</details>

**斯宾塞·拉斯考夫**: 确实会这样展示，但此前一个巨大的局限在于：他们往往要等几个小时甚至一天之后，才能看到更多红发用户。因为过去我们并没有对这叠牌进行**实时重排**，而是每天结束时或每隔几个小时进行一次**批处理**（batch）重新排序。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: They will, but one of the big limitations is they'll only see people with more red hair a couple hours later or a day later because we previously had not resorted the deck in real time. We had resorted it in batch at the end of the day or every few hours.

</details>

**尼古拉·坦根**: 什么时候能实现完全实时化？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: When will it be real time?

</details>

**斯宾塞·拉斯考夫**: 到今年年底就能实现，这正是其他先进推荐算法的运作方式。比如你在**TikTok**上，系统会根据你刚刚滑过或停留的行为，毫秒级即时重新索引展示内容。这一直是我们过去一年中最重大的技术飞跃之一，即**实时推荐系统**（Real-time Rex）。目前我们还没有完全实现全量实时化，但大约已有半数卡牌队列实现了实时重排。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: by the end of the year, which is the way other recommendation algorithms work. If you're on TikTok, you know, they re-index what you should be shown instantaneously based on what you just did. And that's been one of the big advances over the last year is real-time rex. We're not fully there yet, but we're about half of the decks are resorted in real time.

</details>

**尼古拉·坦根**: 除了长相外貌等等，你们还会根据哪些其他维度进行排序？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: in addition to um looks and so on. What are the other things you sort according to?

</details>

**斯宾塞·拉斯考夫**: 主要是他们的**个人资料信息**（Profile Information）。在过去一年半里，我们付出了巨大努力让用户档案变得更加丰富，增加了更多维度的内容。现在你还可以留下所谓的**情境化点赞**（Contextual Like）。

在过去的老版Tinder中，你只能机械地向右滑动，这基本只表达了“我对这个人感兴趣”。而在新版Tinder中，个人资料包含大量多元信息：比如他们从事什么工作、他们与朋友的关系如何、他们周末喜欢做什么。当你针对某项具体内容作出回应时，比如你说：“是的，我喜欢他们也热爱徒步旅行”，此时你不仅是在告诉对方你喜欢他们热爱徒步这一特质，更是在向我们的算法系统明确输入：你喜欢那些热爱徒步的人群。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um their profile information. So, we've made a lot of effort over the last year and a half to make profiles more rich. So, additional content and now you can leave what's called a contextual like. So, old Tinder, you would just swipe right, which basically says, "I'm interested in this person." New Tinder, the profile has lots of different information, like what do they do for work and what's their relationship with their friends like, and you know, what do they like to do on weekends? And when you respond, you're now indicating that you're interested in that particular item that you, you know, you're saying, "Yes, I like that they like to go for hikes." And so now you've not only told the use that that recipient that that that you like that they like to go on hikes, but you told us that you like people that like to go on hikes.

</details>

**尼古拉·坦根**: 你们目前掌握的数据量到底有多庞大？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's when you you how much data do you have?

</details>

**斯宾塞·拉斯考夫**: 几乎是海量无限的，我们沉淀了数十亿次配对数据。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um near infinite. I mean billions of matches.

</details>

**尼古拉·坦根**: 你们有多少人在深入钻研这项技术？有多少位数据科学家？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How many people do you have drilling down in this? How many scientists?

</details>

**斯宾塞·拉斯考夫**: 我们专门负责推荐算法、日夜扑在这个课题上的核心团队大约有**40人**。这包括数据科学家、算法工程师、产品经理等，他们一直在持续不断地测试、微调并优化算法模型。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: We have uh this recommendations algorithm team that just eats and sleeps this topic is probably 40 people. Data scientists, engineers, product managers, etc. who are constantly testing and tweaking and optimizing algorithms.

</details>

**尼古拉·坦根**: 你在其中看到的最令人惊讶的发现是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's the most surprising finding you have seen?

</details>

**斯宾塞·拉斯考夫**: 我最惊讶的发现是：在这些产品诞生15年之后，竟然还蕴藏着如此巨大的优化潜力！刚加入公司时，我原本以为这些应用已经存在了15到20年，产品肯定早已被彻底优化透了，他们肯定早就掌握了人与人之间最优的推荐匹配逻辑。然而令我震惊的是，其中依然存在着巨大的改进空间。随着我们在过去六个月里落地这些算法改进，我们看到了匹配成功率以及用户满意度的显著飙升。因此，最让我意想不到的，恰恰是这里面未被挖掘的巨大提升空间。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: My most surprising finding was how much potential there still is 15 years later. I mean, I when I joined the company, I assumed that, okay, these apps have been around for 15, 20 years. Surely the product is optimized. Surely they've figured out how to recommend people to one another. And what I've been shocked by is how much room for improvement there is. And as we've made these improvements, you know, in the last six months, we've seen huge increases in match rates and and customer satisfaction. So, that's been the most surprising thing is how much room for improvement there is.

</details>

### 完美档案的密码：男女吸引力法则与AI辅助

**尼古拉·坦根**: 在约会软件上，什么样的男性才能称得上“完美的男人”？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's what's a perfect guy?

</details>

**斯宾塞·拉斯考夫**: 你是说在Tinder上表现最好的男性形象吗？那是一个拥有**完整个人资料**、并且展现出愿意投入时间和精力的人。这与我们平台上泛滥成灾的糟糕现象截然相反——那些只放一张在健身房脱掉上衣对镜自拍的男性。男人往往以为那样对女性很有吸引力，其实根本不然！

女性真正看重的是：拥有7张或更多高质量照片、丰富详实的内容、走心的文字表达，而不仅仅是一堆照片。能够认真回答个人提问提示（Prompts），从根本上展现出你的用心与投入，这才是女性真正寻找的特质。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: A perfect guy uh like like who performs the best on Tinder is that um somebody with a complete profile that has demonstrated the time, put in the time and effort. It's the opposite of what we have far too much of, which is the one photo gym selfie with his shirt off. Like guys think that's appealing to women. It's not. What's appealing to women is seven or more photos, rich profiles, content, words, not just photos. Um, answering the prompts, basically demonstrating effort. That's what women are looking for.

</details>

**尼古拉·坦根**: 资料里是不是还必须得有一只狗，或者说放宠物狗有帮助吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Do you have to have a dog in there as well or

</details>

**斯宾塞·拉斯考夫**: 放狗确实极有帮助！每个人都喜欢狗。至于猫……我的个人资料里也是这么写的，猫的提分效果就没那么明显了。不得不对爱猫人士说声抱歉，猫的加分力度确实不如狗，狗狗几乎受到全方位的喜爱。

顺便提一句，我虽然已婚，但我依然在Tinder以及我们旗下的所有应用上注册了账号。我的个人主页写明了我已婚、我是公司CEO、我来这里纯粹是为了产品调研。而在我的资料里，就放着我和我的爱犬的合影，同时我也放了一张我和我太太的合影。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: dogs help? Yes. Everyone loves dogs. Yes. Cats. My profile. Uh, cats don't help as much. So, my profile, I'm married, but I'm on Tinder. I'm on all of our apps. And my profile says I'm married. I'm the CEO. I'm here for research. But my profile has pictures of me with my dog. I also have a picture of me with my wife on my profile.

</details>

**尼古拉·坦根**: 那你在软件上受欢迎吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Are you like a popular?

</details>

**斯宾塞·拉斯考夫**: 我还算可以吧，表现尚可。但当然了，这完全是为了做业务研究，我绝不会越界。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I do. Okay. I do. Okay. But, of course, this is just for research and I I don't, you know, I never

</details>

**尼古拉·坦根**: 那么怎样的女性档案才算“完美的女人”？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's the perfect woman?

</details>

**斯宾塞·拉斯考夫**: 同样地，关键在于展示丰富多元的生活内容。展示她们有自己的朋友圈子，在做着有趣的事情。我们目前正在灰度测试一项全新功能：**利用AI为用户档案进行智能打分并给出优化建议**。

举个例子，当把我的个人资料输入该系统时，AI给我的反馈是：我的着装需要更加多元化！因为我几乎每天都穿着同一款蓝色四分之一拉链套头衫，里面套着同一款蓝色衬衫，我绝大部分照片都是这种打扮。系统建议你应该展现自己更丰富的侧面：比如展示你和朋友在一起、手里端着一杯红酒、在听音乐会、或者在海滩漫步，向对方全面呈现你丰富多彩的生活体验。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, likewise, just showing lots of content. So it's um showing that they also have friends and that they do interesting things. So we actually have a a feature that we're testing right now which uses basically uses AI to score your profile and make recommendations. So for example for my profile when we ran it through that system it said um I need more diversity in my clothing because I basically wear the same you know the same blue the same blue uh quarter zip with the same blue shirt underneath basically every day. And most of my photos were like that. And so you want to show more sides of yourself. You want to show you with your friends, you on, you know, you with a glass of wine, you at a concert, you at the beach, because you're showing, you know, diversity of of of your experiences.

</details>

**尼古拉·坦根**: 如果要从中挑出几个最核心的要素，究竟什么才真正起决定作用？是海滩、朋友，还是穿着打扮？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: If you were to pick out a few of those things, what is it that really matters? Is it like beach, friends, clothing?

</details>

**斯宾塞·拉斯考夫**: 这在很大程度上取决于你希望吸引谁。对于典型的**Gen Z**（Z世代）年轻用户来说，展示你与朋友在一起的合照，或者展现你正在参与有趣的户外活动，往往是最有杀伤力的要素。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, well, it kind of depends on on who whom you're appealing to. Uh, I think for a typical Gen Z user, it's probably you with friends or or you doing fun activities. M

</details>

### 破除社交偏见：消除刻板印象与重塑社会多样性

**尼古拉·坦根**: 大家都不想和一个‘输家’约会，对吧？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: you don't want to date a loser, right?

</details>

**斯宾塞·拉斯考夫**: 正如我之前说的，我们坚信每个人都有契合自己的另一半，因此我不作评判，世界上根本没有所谓的输家。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Well, there's, you know, we believe there's someone for everyone, so I don't pass judgment. There's no such thing as a loser.

</details>

**尼古拉·坦根**: 这确实是你们业务立足的基石。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's kind of your business model.

</details>

**斯宾塞·拉斯考夫**: 世界上没有所谓的输家，他们只是还没遇到懂他们、适合他们的那个人而已。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: There's no such thing as a loser. They're just somebody that hasn't met their their right person yet.

</details>

**尼古拉·坦根**: 这番话听起来令人深受触动。从历史上来看，传统观念中男性在社会经济地位上往往倾向于‘平视或向下兼容’寻找伴侣，而女性往往‘平视或向上兼容’（Horizontally and Up）。现在的情况还是这样吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's that sounds that sounds really good. Um, historically, um, men dated, uh, horizontally and down and women dated horizontally and up socioeconomically. Does that is it still the case?

</details>

**斯宾塞·拉斯考夫**: 我们对用户的社会经济地位数据其实掌握不多。在Tinder和Hinge这两大旗舰应用上，我们压根不会要求用户填写这类敏感隐私信息。不过在**Pairs**——我们在日本排名第一的约会应用上，我们确实会收集用户薪资，甚至还会显示血型，因为日本有着截然不同的文化规范。但总的来说，我们通常并不直接去审视这种社会经济地位带来的匹配影响。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, you know, we don't know much about the socioeconomic nature of our users. We, you know, on Tinder and Hinge, our two biggest apps, we don't ask for that information. On pairs, our are the number one app in Japan. We do we actually ask for salary. We include blood type. I mean, Japan is a very different culture. Um, but I I don't um we don't tend to look at at socioeconomic impact.

</details>

**尼古拉·坦根**: 那你的直觉判断是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's your gut feel?

</details>

**斯宾塞·拉斯考夫**: 我的直觉判断是：这种现象大概率依然存在。这属于一种根深蒂固的社会偏见与心理机制，单靠线上约会可能并没有发生太大的颠覆。

不过，线上约会带来了一项让我们深感自豪的深刻改变：**它让人们接触到了比以往广阔得多的多元人群**。试想一下，如果你主要依靠现实中的社交圈或熟人介绍来寻找伴侣，你最终交往的对象往往局限在与你拥有极为相近的社会经济地位甚至相同种族背景的狭窄圈子里。而线上约会彻底打破了信息茧房，将你推向更广阔的世界。这其实是一个非常值得深入学术研究的课题。虽然目前我还没看到系统性的定量报告，但我大胆推测：我们的产品极大地推动了跨越不同社会经济阶层的多样化关系构建。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh my gut feel is that that's probably still right. That's probably a a lifelong societal, you know, bias that probably online dating hasn't changed much. Although, I mean, we are proud of one thing that online dating has changed, which is it's it's exposed people to a much larger array of people than they otherwise would have have noticed. So, if if you were mostly meeting people through your social network in real life or through friends, you're going to end up with people of a more similar socioeconomic or even racial um you know, makeup. But online dating exposes you to a much broader array. So perhaps we I actually this would be an interesting thing to study. I haven't studied this or I haven't seen research on this but I I would guess I would speculate that we have contributed to greater diversity of socioeconomic relationships.

</details>

**尼古拉·坦根**: 在你们的平台上，男性用户的比例是多少？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Um what percentage what percentage is men?

</details>

**斯宾塞·拉斯考夫**: 我们一般不对外披露具体的性别比例，不过……

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um we don't we don't share that but um

</details>

**尼古拉·坦根**: 男性比例显著高于女性，对吧？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: it's higher than higher than women, right?

</details>

**斯宾塞·拉斯考夫**: 在Tinder和Hinge上，男性确实比女性更多一些。但在我们旗下的某些细分应用中，女性数量反而超过了男性。例如**The League**和**Pairs**就明显偏向女性用户。其中，The League是我们专门为高抱负、精英阶层打造的应用——我猜如果你去用约会软件，大概率会选择The League，它的女性用户占比相当高。

但需要强调的是，正因为Tinder具备极其强大的**流动性底池**（Liquidity Pool）——它在166个国家常年位居约会应用榜首。即便男性比例略高，我们平台上依然活跃着数以千万计的女性用户。所以在任何一个具体城市，用户都能拥有极为充沛且多元的选择空间。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: It is higher than well for Tinder it's it's higher for women and for Hinge but um some of our apps have more women than men. Um you know the league and pairs tend to skew more female um uh the league is our app for highly ambitious people. My guess is you'd be on the league if you were on a dating app. Um and uh uh and that tends to skew more female. But um uh you know because Tinder has so much liquidity, I mean has it's the number one dating app in 166 countries. Even though the there's a greater percentage of users that are men than women, we still have many tens of millions of women. And so in any given city, there's there's a wide selection of potential.

</details>

**尼古拉·坦根**: 那么女性主要浏览哪一年龄段的男性？平均年龄是多少？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So what's the average age of men that women look at?

</details>

**斯宾塞·拉斯考夫**: 在Tinder上，大约有**60%的用户是Z世代**（18至28岁之间）；而在Hinge上，同样有约60%的用户属于Z世代。因此，我们的典型用户或中位数用户年龄大致在25岁左右，主要集中在18至28岁这个核心年轻群体。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh well about 60% of our users on Tinder are Gen Z are 18 to 28 and about 60% of our users on Hinge are also Gen Z. So our typical user is kind of 25ish would probably be our median user 18 to 28 Gen Z.

</details>

**尼古拉·坦根**: 但我之前看到过一组数据研究指出：男性平均倾向于寻找25岁以下的年轻女性，而女性则更青睐40岁左右的成熟男性。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: But I just saw some numbers that um men look at women I mean the average men look at women you know sub 25 and women look at men at you know 40.

</details>

**斯宾塞·拉斯考夫**: 我个人没有专门核实过这个统计。不过这倒是个很有趣的角度，你完全可以来加入我们团队！

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Don't I haven't looked at that. That would be that's also you know you should work in our

</details>

**尼古拉·坦根**: 你们确实得好好深挖一下这些底层数据，这非常有意思，不是吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: you need to look at your numbers here because this is good fun, right?

</details>

**斯宾塞·拉斯考夫**: 是的，这确实非常有趣！你真应该加入我们的数据分析与公关传播团队，这些用户内容中可以挖掘出大量极具公关传播价值的精彩数据故事。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Yeah, this is good fun. No, you're you're uh you should you should join our our analytics PR function because there's lots of there's lots of fun data PR stories to mine from from this content.

</details>

**尼古拉·坦根**: 那么留胡须在约会市场上是呈上升趋势还是下降趋势？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Is facial hair on the way up or down?

</details>

**斯宾塞·拉斯考夫**: 你提的这些问题真是我从未准备过、也从未被其他人问到过的。目前来看，**八字胡**（Mustaches）极其风靡！蓄胡子在如今全球Z世代群体中是一件非常酷的潮流。我自己倒不是胡须爱好者，正如你所见我刮得干干净净。但不可否认，面部毛发尤其是八字胡的受喜爱程度绝对在大幅攀升。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: You're asking me all these questions I haven't prepared for or been asked by anyone. Um mustaches are all the rage. You know, mustaches are the are the cool Gen Z thing uh globally now. I uh I'm not a you know, it's not for me as you as you can tell as I sit here clean shaven. Uh but but facial hair and mustaches in particular are are definitely on the way up.

</details>

**尼古拉·坦根**: 你们能观察到时尚趋势的流变吗？比如像那些在线快时尚零售巨头一样，能够洞察全球各大城市的色彩流行趋势？比如看到某种风格正在慕尼黑流行，另一种正在法兰克福流行，这非常引人入胜。你们做过类似的数据洞察吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Yeah. Could you can you look at like fashion trends where they're going with you like you know you have the online online retailers you can basically see what colors are trending which direction in various cities in the world, right? You can see this is trending in Munich. This is trending in Frankfurt. It's really fascinating. Have you done anything?

</details>

**斯宾塞·拉斯考夫**: 坦白说我们以前还真没做过，但我已经在笔记本上记下来了，我们接下来一定会开展这项分析！你说得很对，我们拥有极其丰富的图像与行为数据，完全可以挖掘这类宏观趋势。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: No, we haven't. But I've written it down in my notepad and we now will. Uh you're right. We absolutely can. You know, can can mine that type of data? No.

</details>

**尼古拉·坦根**: 那么在约会市场上是否存在所谓的‘赢家通吃’（Winner takes all）现象？我是指，是否极少部分最帅的男性和最漂亮的女性拿走了绝大部分的关注、点赞和匹配？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Is it like a winner takes it all... in the dating is it like some women and some men get all the hits, all the likes.

</details>

**斯宾塞·拉斯考夫**: 我明白你的意思了。答案是否定的，这其实也是让我非常惊讶的一点。社会大众往往普遍认为必然存在严重的赢家通吃，但实际数据表明并非如此，**每个人都能在平台上找到适合自己的另一半**。我们看到各种体型、各种外貌、各种风格背景的用户都在不断达成美好配对。推荐算法在这里发挥了极其精妙的作用，它能将契合彼此的人推送到对方眼前。

无数人在我们的平台上找到了彼此。我的邮箱每天都被感谢信、婚礼请柬以及社交媒体上的艾特所淹没，他们都是在Tinder、Hinge或我们旗下应用上相遇并最终喜结连理的用户。我们正在真实地撮合无数美好良缘。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I see. Um, no. No. And this is a bit of a surprise to me as well. Um, you I think there there's a societal perception that that would be the case, but no, there really is a a person for everyone out there. We see um, you know, we see people of of all types, of all body types, of all appearances, of all profiles, finding matches. So people and here the recommendation algorithm is is quite good to put the right people in front of the right people. People are finding one another. I am inundated with emails and wedding invitations and comments on social media of people who have found their spouses, their partners, their relationships on Tinder Hinge or one of our apps. I mean, we are

</details>

**尼古拉·坦根**: 那么这些通过网络相识结婚的人，他们的离婚率如何？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Are divorce rates higher or lower?

</details>

**斯宾塞·拉斯考夫**: 权威调研数据表明：**通过网络相识结婚的夫妻，其离婚率其实显著低于在线下现实中相识的人群**。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: we think or we think they're lower. That's what the the research says. The people that meet online have a lower divorce rate than people that meet in person.

</details>

**尼古拉·坦根**: 为什么会这样？背后的原因是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Why do you think that is?

</details>

**斯宾塞·拉斯考夫**: 我认为原因在于：在线上约会过的群体，往往在做决定前经历了更充分的接触与深度筛选，考察了大量潜在伴侣。因此，一旦他们决定安定下来组建家庭，他们已经积累了更丰富的交往阅历，也更清晰地懂得自己到底需要什么。

这是我进入这个行业之前完全没有意识到的深度洞见：**线上约会不仅是一个了解潜在伴侣的过程，更是一个深层探索自我、认知自我的过程**。经历了完整的线上约会历程后，你对自己内心的真实偏好有了清晰的笃定，反而更有能力和意愿去长久维系一段稳固的婚姻。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, I think that they um they, you know, people that date online have have sort of played the field and and vetted lots of potential partners. So once they settle down, they've had more experience and understand more about themselves. This is another thing I didn't really appreciate until I entered the category. But online dating is as much about learning about your potential mates as it is about learning about yourself. And um I think once you've gone through that online dating journey, you're more ready to stay in a marriage because you've experimented and explored and learn more about yourself and your preferences.

</details>

### 约会社交大变局：孤独危机与线下场景重构

**尼古拉·坦根**: 斯宾塞，我们再来聊聊大众约会行为的变化。当下的约会场景究竟发生了哪些深刻转变？有什么完全不同了？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Spencer, moving on to how we date. How has the dating scene changed? What's different?

</details>

**斯宾塞·拉斯考夫**: 整体变化非常巨大。现在的约会变得更加具有**社交属性**。年轻人在约会过程中变得更具社群感与分享欲。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: It's changed a lot. It's so much more social and um you know, young people are

</details>

**尼古拉·坦根**: 当你看到全社会关于‘孤独感’（Loneliness）的冰冷统计数据时，你内心在想些什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: When you see the numbers about loneliness, what do you think?

</details>

**斯宾塞·拉斯考夫**: 我认为这非常令人心痛。这种孤独感是**对人类社会的一种生存威胁**（Existential Risk）。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I think it's tragic. It's it's a it's an existential risk to society, and

</details>

**尼古拉·坦根**: 而且医学研究表明，长期孤独对健康的危害甚至比吸烟还要严重。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: and it's worse than smoking.

</details>

**斯宾塞·拉斯考夫**: 确实如此，它的危害比每天抽烟还要致命！深度的人际联结是人类健康长寿的核心秘诀。如果你渴望长寿，建立健康、深度的亲密关系是首要条件。然而毫无疑问，社交媒体极大地加剧了这场孤独流行病。我们所有人都整天沉迷并被困在屏幕前，人与人之间的物理隔绝前所未有地严重。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: It's worse than smoking more than actually smoking. It is it is the key to longevity. If you you know if you want to live long, be in a relationship. Uh, it's been exacerbated by social media undoubtedly. We're all obsessed on on these screens.

</details>

**尼古拉·坦根**: 我看到过一份调研报告，数据显示有高达**45%的18至25岁年轻男性从未主动约过女孩子出去**。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: I saw one survey which said that 45% of men between 18 and 25 had haven't asked a girl out.

</details>

**斯宾塞·拉斯考夫**: 是的，正是如此。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Yes.

</details>

**尼古拉·坦根**: 这太令人震惊了，不是吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Shocking, right?

</details>

**斯宾塞·拉斯考夫**: 这确实触目惊心。这一方面是因为年轻一代普遍感到焦虑和胆怯；但另一方面，是因为他们极其害怕被视为‘过于激进或越界’。在过去的十年中，**MeToo运动**以及广泛的社会文化思潮重塑了社交准则。如果在十年前，一个男生在酒吧走向一位女生说：‘嗨，我可以请你喝一杯吗？’这是再正常不过的社交举动；但在今天，这很容易被解读为冒犯甚至攻击性行为。

正因如此，年轻一代迫切需要一个名正言顺的契机、借口或‘第三空间’（Third Place）来聚在一起。这正是我们全力推动**线下单身活动**的核心原因。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: It is shocking. And um you know, it is partly because they're you know, they're afraid. They're they're nervous of it. It's also because um they don't they they don't want to be perceived as overly aggressive. So the Me Too movement and and other social trends over the last 10 years have made it feel awkward and and almost like aggressive. If a man went up to a woman in a bar and said, "Hi, can I buy you a drink?" which would have been a very normal activity even 10 years ago that can be perceived as aggressive today. So young people are looking for a pretext, an excuse, a third place, a reason to get together, which is why we are organizing offline events.

</details>

**尼古拉·坦根**: 你觉得这种社交谨慎甚至隔绝的趋势，接下来是在好转、在恶化，还是会保持现状？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: do you think it's getting better or worse or just

</details>

**斯宾塞·拉斯考夫**: 我认为这个宏观趋势短期内不会扭转。不过值得注意的是：**Alpha世代**（12至18岁）与目前的**Z世代**（18至28岁）有着显著的行为分化。Alpha世代是在后疫情时代成长起来的，他们对面对面真实社交表现出了截然不同的渴望。但对于现阶段的Z世代而言，这种社交阻滞依然非常真实。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: well it's I don't think that trend is going to change. I think that um you know Gen Z 18 to 28 is All right. Gen Alpha 12 to 18 is quite different than Gen Z 18 to 28. They're going out more. They're they're post-COVID. They're hanging out.

</details>

**尼古拉·坦根**: 你认为**新冠疫情**（COVID-19）是造成这一切的主要推手吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So you think CO caused a lot of this?

</details>

**斯宾塞·拉斯考夫**: 是的，疫情绝对起到了剧烈的催化作用。虽然在此之前这种趋势就已经在悄然发生，但疫情期间长期的居家隔离，让这一代年轻人在心智成熟的关键时期缺失了极为重要的面对面交往训练，彻底重塑了他们的社交习惯。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Yes, I do think it did. Um I think there was a trend in motion already, but I think that the isolation of those young people during their formative dating years has permanently impacted them.

</details>

**尼古拉·坦根**: 但约会软件本身是否也在助长这个问题？既然大家在手机上就能滑动浏览无数人，这是否也削弱了人们走向现实的动力？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Are you but are you also contributing to the problem given that you have this endless conveyor belt of people?

</details>

**斯宾塞·拉斯考夫**: 我不这么认为。恰恰相反，我们正在构建一条非常健康、清晰的路径，引导大家从线上走向线下现实世界。我们的终极目标不是让用户永远被困在App里划屏，而是促成真实的面对面约会。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: No, I don't think we are. I think um you know I think we create a very easy on-ramp to meet someone in real life. That's the whole point. We're not trying to keep you on the app forever. We're trying to get you off the app.

</details>

**尼古拉·坦根**: 但从商业逻辑来说，如果你们太快帮用户促成了稳定关系并让他们注销应用，你们不就赚不到钱了吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: But I mean if you mess them too quickly you're not going to make much money.

</details>

**斯宾塞·拉斯考夫**: 这完全没问题！作为大股东，你们尽可放心。正如Hinge的经典品牌定位——‘一款为了被删除而生的应用’（Designed to be Deleted）。只要我们能高效促成良缘，口碑就会带来海量源源不断的新用户，这构成了正向的飞轮效应。

当下年轻人更少饮酒、注重健康，传统的酒吧搭讪文化衰退让破冰变得更困难。因此我们正在通过丰富的**线下活动**为他们搭桥铺路。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: That's okay. That is totally fine. I am positive and and is as a shareholder you should appreciate this. Our business model is totally aligned with our customers. The better the product works, the more people use it. Hinge's tagline is designed to be deleted. And that's our business model. When you delete the app because you found someone, you tell your friends, and they download the app. Um it's it's makes it harder. I mean, you know, alcohol is not very good for you. And so young people drink less, which is good for their health, but it makes meeting people harder because bars were the place where people met.

</details>

**尼古拉·坦根**: 你们具体组织了哪些类型的线下活动？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What kind of events are these?

</details>

**斯宾塞·拉斯考夫**: 这些都是充满趣味的线下活动：比如**单身匹克球比赛**（Pickleball）、单身麻将速成派对、公园徒步聚会等。我们的核心原则是‘学到新东西、动手做点事、身体动起来’（Learn something, do something, move something）。这些活动通常不依赖酒精，主打健康社交。

最重要的是，我们在这些线下活动上方覆盖了一层强大的**数字化体验层**：在Tinder应用内部，你可以直接浏览并报名这些活动。来参加节目之前，我还向你们的团队展示了目前在纽约举办的各种Tinder线下活动。在报名界面上，你可以提前看到其他报名者的照片和微型档案，提前了解是否有你想认识的人。活动结束后，你还可以直接在Tinder应用内与现场遇到的人互发消息并继续深入交流。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: These are um uh fun singles, mixers, pickle ball events, um learn how to play ma jang with singles, um go for uh you know a meetup in the park. Um you they tend to be dry events. Sometimes there's music or many of them have some sort of educational component. So learn some the way we we say learn something, do something, move something. Those are generally the themes. They usually don't have alcohol. And we have this digital layer on top of the event. So inside of the Tinder app, you can see all these fun things to do. I was just sharing with your team the uh you know, we were looking at Tinder here in New York at the events um of of fun things to do. And you can see photos and mini profiles of the people going to the events. So you can actually see, oh, are these people I want to meet? And then afterwards, you can come back to the Tinder app and message with the people you met at the event.

</details>

### 全球地缘差异与挪威的双人约会文化

**尼古拉·坦根**: 在不同国家和地理区域之间，约会行为是否存在显著的文化差异？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Is it a big difference between geographies?

</details>

**斯宾塞·拉斯考夫**: 在线下活动形式上差异不大，但在底层约会习惯和文化规范上，地缘差异极其巨大！

比如亚洲特别是**日本**，其约会文化有着极强的目的性（Intentional Culture），甚至有着父母深度参与相亲的传统。在日本等市场，父母甚至会和年轻人一起使用约会应用或过问匹配流程，这与西方文化完全不同。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Asia is very different. Asia in especially Japan involves parents in the dating... much more intentional culture.

</details>

**斯宾塞·拉斯考夫**: 再以你们**挪威**为例：我们在挪威推出了‘**双人约会**’（Double Date）功能——即邀请闺蜜或死党一起组队在App上探索约会。令人极其震撼的是，**在挪威有多达53%的Z世代女性用户在使用Double Date功能**！挪威超过半数的年轻女性都是和朋友一起在约会软件上互动的。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Oh wow. It's 53% of our female Gen Z users in Norway. So, of our users in Norway, more than half of women are dating with friends. They're on the app with a friend.

</details>

**尼古拉·坦根**: 你觉得为什么这项功能在挪威会如此火爆？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Why do you think it is?

</details>

**斯宾塞·拉斯考夫**: 因为挪威拥有一种极具凝聚力的社交文化，那里的年轻人天然喜欢拉上好友共同参与各种决策——无论是挑选衣服、看音乐会、旅行，还是寻找恋爱伴侣。再加上挪威极高的智能手机普及率以及对创新事物的高度开放度，因此当我们最初研发Double Date功能时，挪威正是我们的首发试点市场之一。事实证明这项创新取得了现象级的成功。相比之下，美国目前只有约25%的Z世代用户使用Double Date功能。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Because it's a social culture where people naturally bring friends into their, you know, into their search behavior, whether it's for clothing or concerts or travel or relationships. um high smartphone usage, openness to try new things. This is why Norway was was literally our first market or one of our first markets when we launched Double Date. We selected Norway intentionally and it's been wildly successful. That 50-ish% number compares with about 25% in the United States of our Gen Z users use Double Date.

</details>

**尼古拉·坦根**: 能再多谈谈吗？为什么挪威年轻人尤其吃这一套？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Just a bit more. Why do you why do you think this goes on well in Norway?

</details>

**斯宾塞·拉斯考夫**: 你对挪威本土文化肯定比我了解得多。但据我们专门研究社会行为学的科学家团队分析：挪威文化年轻而极具社群感，年轻人有着天然的‘带上你的朋友’（Bring your friend）思维模式，这与协同约会的理念高度共鸣。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I um well, you certainly know the culture better than I do, but the way it's been described to me by our social scientists who who study this type of thing is that the culture is incredibly social and young and people bring their friends into things that it's um you know, it's a it's a it's a social culture with um kind of a bring your friend attitude and and mindset.

</details>

**尼古拉·坦根**: 那么这些匹配模式在**LGBTQ+多元群体**中是否有着显著差异？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Are these patterns very different in the in the gay community?

</details>

**斯宾塞·拉斯考夫**: 是的，同性群体的交往模式有着很大不同。在异性恋群体中，两个人分手后通常会彻底断绝联系，极少能和前任保持亲密好友关系。但在男同群体中，朋友关系、亲密关系以及深层友谊往往是流动的、彼此交织的。

此外，在安全诉求上也有本质区别：男同群体在面对面约会时，对彼此之间的肢体暴力顾虑较少，但他们极其渴望拥有一个免受外界偏见侵扰的情感与心理避风港。我们旗下的**Sniffies**正是该领域的领军产品，它为社群构建了一个受保护的安全空间，深受用户拥戴。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, yes, the gay community tends to be I'm stereotyping of course, but um, you know, they many of them tend to seek shorter term relationships. Many of them um, have long-term relationships that with friends that also move into intimacy and friendship kind of move back and forth... Sniffies is our our gay product... and it feels like a safe space.

</details>

### 生成式AI赋能：产品体验进化与公司运营革命

**尼古拉·坦根**: 展望未来，你认为**人工智能**（AI）将如何深刻改变这一切？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How do you think AI will change this going forward?

</details>

**斯宾塞·拉斯考夫**: AI对我们公司的重塑程度怎么强调都不为过。在过去短短12个月里，我们公司内部每个人的工作方式——包括我自己在内——都发生了根本性变革。软件工程师、市场营销人员、HR、法务，所有人都在以截然不同于一年前的方式开展工作。

在我整个职业生涯中，唯一能与之相比的技术变革，是早期我在几家还没通电子邮件的公司上班；而当全员接入Email的那一刻，整个商业运作模式被彻底重构了。AI带来的颠覆正是同等量级的，它给每个员工赋予了‘超能力’。

而在面向用户的产品端，AI更是带来了革命性的推动。你可以把AI想象成一个站在男生身后的智囊朋友，以及一个站在女生身后的智囊朋友，它在悄悄帮助双方展现最美好的一面，把彼此推得更近。

例如：在发消息前，AI会自动审阅文本，筛查不当内容，并给出善意提醒：‘嘿，你这句话可能显得太激进了，对方可能会觉得带有性暗示，建议你调整一下措辞’。而在Hinge上，我们上线了**提示语反馈功能**（Prompt Feedback）：当系统提问‘你周日喜欢做什么？’如果用户随手敷衍写了一个‘早午餐’（Brunch），AI就会像好友一样互动打趣：‘拜托，斯宾塞，你能写得更走心点，告诉我们你早午餐最爱吃什么？’你说‘吃鸡蛋’，AI会继续追问：‘能不能分享上次和朋友吃早午餐时发生的最搞笑的一件事？’通过与AI的自然对话，用户最终生成了一份极具吸引力、生动丰满的个人档案，从而大大提升了成功破冰的几率。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um well for our company and I you know I know you interview a lot of executives. It's hard for me to um you know I it I I can't state enough how much it's changed the way the company operates just in the past year. The way literally every single person including me does their job has changed significantly or very significantly over the last 12 months. software engineers work differently, marketers, comm's professionals, um HR people, lawyers, like everybody does their job differently than a year ago. The only thing I can equate it to is perhaps um you know, very early in my career, I worked at a couple companies with which didn't have email yet, believe it or not. And when we all got email, everything changed and the way people work changed. That's the closest thing I've seen in my career. So, it's changed the way we work internally. Everyone has superpowers now. In terms of the product, it's also changed things radically. We use AI in the product to um to to help people get closer together. Basically, you can think of like AI is this friend that stands behind me and it's a friend that stands behind her and it helps push us closer together. How? By helping us put our best foot forward. So, we use AI, for example, to read your message before you send a message through and screen for inappropriate content and make suggestions of, hey, you're being a little forward. you might not want to. That might be perceived as sexually suggestive. You might want to change the way you're wording that. Um, we use AI to help you improve your profile, uh, to tease out content about yourself. Um, but never to present you in in an authentic way. So, for example, um, Hinge has a feature that gives prompt feedback. So, it'll Hinge will say, "What do you like to do on Sundays?" And if you write in your profile, uh, brunch, the AI will say, you know, "Come on, Spencer, you can do better than that. tell us, you know, tell us what you like to eat for brunch and you'll say eggs. It'll say, "Come on, you know, what's a funny story of the last time that you had brunch with your friends." So, you'll kind of be conversing with AI in, you know, through text in order to improve your profile. And the final output when she's looking at my profile is I will have a much more fullfeatured robust profile which will make me more interesting to her because my friend AI has encouraged me to put my best foot forward and it's it's showing.

</details>

**尼古拉·坦根**: 那么在未来5到10年之后，整个约会社交场景会演变成什么样子？你的终极推测是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So, five five 10 years from now, what is this whole scene going to look like? What's your best guess?

</details>

**斯宾塞·拉斯考夫**: 我的最佳推测是：Tinder将彻底迎来逆转，通过这条**社交化产品路线图**，重新与Z世代达成完美的**产品市场契合度**（Product Market Fit）。Tinder将彻底撕下过去‘约炮软件’（Hookup）的刻板标签，蜕变为年轻人‘与好友一同寻找真挚社交’的代名词；而Hinge则继续领跑严肃认真的婚恋市场。届时，Tinder将是年轻人步入社会使用的第一款约会软件，而Hinge将是他们步入婚姻前使用的最后一款软件。

这非常类似于**Uber**的发展轨迹：五年前，很多人还心存芥蒂：‘坐进一个陌生人的后座真的安全吗？是不是受监管的出租车更有保障？’但如今借助一系列完备的技术安全功能，大家把乘坐Uber视为理所当然，从而为Uber打开了远超市场想象的庞大增量空间。我们在安全技术上的重大突破也将解锁同样巨大的市场。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh, my best guess is that um, Tinder in particular will have really turned a corner in terms of regaining product market fit with Gen Z because of this social roadmap because Tinder will not stand for hookup, which is kind of our, you know, the stigma that the Tinder brand has had historically. Tinder will stand for a fun, safe way to meet new people with friends. It will mean dating with friends. Um, Hinge will still be the leader in the intentional dating space. So, Tinder will probably be the first dating app that one uses. Hinge will probably be the last dating app that somebody uses. And, um, will have made huge steps forward in terms of safety. So, and and who Uber, I think, is a good analogy where Uber went from like, I don't know if I feel safe getting in the backseat of a stranger's car. Maybe taxis are safer because they they're regulated. That was 5 years ago. to today. You think to yourself, well, of course I feel safe because of all these features that Uber has provided to me. And that has unlocked a massive addressable market for Uber that I think far exceeds what people expect.

</details>

**尼古拉·坦根**: 你认为未来的定价体系会发生根本转变吗？比如允许我支付一笔极高昂的费用，来换取一个极其精准完美的契合对象？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Do you think the pricing structure will change so that I can pay a heck of a large amount of money to get a really really good fit?

</details>

**斯宾塞·拉斯考夫**: 可能会有一些小众应用去做这种超高端尝试，但这类服务的潜在可寻址市场（TAM）相对较小。因为约会本质上是一门依托**网络效应**（Network Effects）的生意，我们平台需要庞大的免费用户群体来维持最充沛的流动性底池。绝大多数用户永远不需要付费，这是我们业务生态的核心基石。

因此，比起单纯探索更贵的订阅层级，我们更专注通过提升免费服务本身的撮合效能，从而间接增强付费用户的长期留存率与商业转化。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um I think we may you know you'll see some services experiment with that but I think that addressable market will be relatively small and because it's a network effects business we need we need free users like we need a lot of people who don't pay anything and many many people by far the majority of our users don't pay anything um and that's very important that's important to the liquidity pool so I don't see that changing you might see us experiment with higher higher expense products but I think more likely you'll see us improving the efficacy of the free service which will improve retention of the payers.

</details>

### Match Group的逆境突围：文化重构与产品清零

**尼古拉·坦根**: 我们把话题转向公司经营。你在2025年2月临危受命接管Match Group，当时整个公司陷入了相当大的困境。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Yeah. Um let's move uh tax a bit here. You uh took over in February 2025 and the business was in a bit of a mess.

</details>

**斯宾塞·拉斯考夫**: 当时这家公司确实迷失了方向。它严重缺乏产品创新精神，陷入了过度追求短期财报指标的官僚陷阱。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: The company had sort of lost its way. Um it had not been innovative. it had been run too much, you know, for short-term financial optimization.

</details>

**尼古拉·坦根**: 那么你接任后立即采取了什么行动？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So, what did you do then? You took...

</details>

**尼古拉·坦根**: 新官上任，你的第一步究竟抓了什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And by the way, what's the first thing you do? So, hey, you're the new boss. What do you do?

</details>

**斯宾塞·拉斯考夫**: 我做的第一件事是开启全球范围内的‘倾听之旅’（Listening Tour）。在最初的100天里，我要求自己多听少说，深入了解第一线实情。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: First thing I do is look at Well, so I did a kind of a listening tour. I tried to listen to listen more than I speak for the first 100 days or so. Uh I figured it out a little quicker than that. I

</details>

**尼古拉·坦根**: 你当时跟多少名员工进行了深度交流？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How many did you speak to?

</details>

**斯宾塞·拉斯考夫**: 足足有数百名员工。我跑遍了我们全球各地的每一个办公室，与基层员工、产品经理深入座谈。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Oh gosh, hundreds and hundreds of employees. I mean I I I went to every one of our offices globally, and sat down in small groups with people.

</details>

**尼古拉·坦根**: 而且据我从你的团队那里了解到，你平时睡眠极少，往往凌晨就投入工作了。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: and when because you don't uh you don't sleep so much. Uh I gather from your your team. So for instance you start people come in in the morning and there are dozens of emails already.

</details>

**斯宾塞·拉斯考夫**: 是的，我确实起得很早。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh off Yeah. And I mean I

</details>

**尼古拉·坦根**: 如果是你做主，你可能恨不得每天早上5点就开始全员开会了。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And had it been up to you, you probably would have been at 5.

</details>

**斯宾塞·拉斯考夫**: 我今天早上5点就起床了，昨天我刚坐红眼航班从加州飞到东海岸。我的管理哲学是：**作为全公司薪酬最高的人，我理所应当成为全公司最拼命、最勤奋工作的人**。唯有这样，才能赢得员工的尊敬。我为整个团队树立了高速推进的执行节奏。

我接手后抓的第一核心要素就是‘**人**’。我有一套经常重复的管理信念：**优秀的团队在被合理组织和充分激励的前提下，能够基于敏锐的用户洞察打造出卓越的产品；卓越的产品吸引庞大的用户受众，进而转化出丰厚的收入与利润，最终沉淀为坚实的股东价值**。整个商业飞轮的源头正是人才的组织与激励。

在我接手的第一年，我把几乎全部精力放在了人和组织上。当时Tinder是我们遭遇挑战最严峻的核心品牌，内部敬业度调查显示有高达**25%的员工处于消极懈怠状态**，仅有约40%的员工处于全身心投入的敬业状态。而一年后的今天，数据发生了惊人的蜕变：消极懈怠率直接减半，敬业度几乎翻倍，整体员工敬业度大幅提升了**17个百分点**！为我们提供全球调研的第三方专业评估机构指出，这种年内跃升幅度在其全球企业数据库中是前所未有的。

激发了团队斗志后，紧接着就是打造让年轻人尖叫的产品。为此，我做了一个极其果断的决定：**全面清空现有的产品开发路线图（Cleared the product roadmap）**！我告诉所有人：彻底忘掉过去正在做的那些琐碎修补，一切归零重新出发。为了重新读懂年轻用户，我们重启了实习生计划，暑期招募了30名优秀大学生实习生，大量引入Z世代新鲜血液，让懂年轻人的人来做属于年轻人的产品。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I've been up since 5 and yesterday I took a red eye from California to the east coast. Yeah. No, I work very very hard. I uh I think my employees deserve that. I My philosophy is I'm I'm the highest paid person at the company. I should be the hardest working person at the company. That's my that's my philosophy. Um and I, you know, I set a I set a pretty rapid pace for my team to follow. Um uh the first thing I did was look at the people. So I have this um this kind of philosophy and I say it all the time. My employees are kind of sick of hearing me say it. Great people properly organized and properly motivated build great products that are informed by consumer insights that generate audience which generate revenue and profit which then generate shareholder value. So it's this kind of circle this spiral that starts with great people properly organized and motivated. So I spent almost the first year just focused on the people. How do we make sure we have the right people in place? How do I make sure they're motivated? Uh we did an employee engagement survey for example on Tinder which was our most troubled brand. and um something like 25% of people said they were disengaged. Um and only about 40% of employees were engaged. A year later, the numbers have radically changed. So the disengagement has cut been cut in half. The engagement has almost doubled. We gained 17 points of employee engagement in a year, which our third party vendor that surveys this for companies globally says is unprecedented. They've never seen such a large improvement in employee engagement. So it starts with the people, motivation, and organization. Then they have to build cool stuff. They have to build cool stuff that attracts audience. And so the next thing we did was we completely cleared the product roadmap. I said, "Forget about everything you've been building. Let's start from scratch. What should we build for our users?" And to do that, you need consumer insights. So we started doing a lot of consumer research. We brought a lot of Gen Z users into the building. We hired a lot more Gen Z employees. We restarted the internship program. So we had no employ no college interns before I was here. This summer we had 30 college interns.

</details>

**尼古拉·坦根**: 你们目前公司全职员工总规模是多少？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How many are you all together in the firm?

</details>

**斯宾塞·拉斯考夫**: 我们全球共有大约2,000名员工。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: We're about 2,000 employees.

</details>

**尼古拉·坦根**: 这2,000人的具体职责是如何分布的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And what do they do?

</details>

**斯宾塞·拉斯考夫**: Tinder团队约有600人，Hinge团队约有500人，其余人员分布在不同细分品牌及平台共享支持职能中。我们在全球近200个国家拓展业务，团队负责产品研发、全球化营销、社交内容运营、底层推荐技术，以及最终向华尔街交付优异的财务业绩。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um well, Tinder has about 600 people. Hinge has about 500 people and uh the rest work on a variety of different brands or shared functions like finance, HR, legal. We market this product globally. We're in almost 200 countries. And so they build social assets, they market, they build technology, product, then we start thinking about monetization and you know and then the final output is the wall street performance and financial results.

</details>

**尼古拉·坦根**: 你此前拥有非常辉煌的连续创业履历，亲手打造过多家具备巨大社会影响力的行业领军企业。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: and the play you have done a lot of things before like in you have you were a serial entrepreneur you founded Zillow, you worked at Hotwire, you took companies public.

</details>

**斯宾塞·拉斯考夫**: 是的，我很早就创立了在线旅游平台**Hotwire**，后来以近7亿美元出售给了Expedia；之后我又与合伙人从零联合创立了房产科技巨头**Zillow**，并带领它成功上市。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I've started companies I you know I started a company called hotwire which We sold to Expedia for $700 million when I was 28. Then I co-founded Zillow, ran that for a decade, took it public, bought Trulia.

</details>

**尼古拉·坦根**: 在这些大获成功的企业打拼经历中，有哪些最核心的制胜法宝被你带入了Match Group？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: And what have what is it that you have taken from these experiences into the match group?

</details>

**斯宾塞·拉斯考夫**: 核心就是我前面提到的这套方法论：以顶尖人才为原点，通过科学组织与极致激励，驱动敏锐的产品创新，从而拉动增长飞轮。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh, it's basically this recipe. So, great people properly organized and motivated to build great products.

</details>

**尼古拉·坦根**: 也就是说，这套飞轮你过去已经成功验证过很多次了。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So, you've done it before.

</details>

**斯宾塞·拉斯考夫**: 是的，我在Zillow从零起步时就完整实践过这套路径，证明了它能爆发出惊人的长期复利。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I've done this before. We did this at Zillow. I mean, we started Zillow from scratch and I assembled the team that built Zillow and made it into a household name.

</details>

### 容忍失败的创新文化与AI时代人才标准

**尼古拉·坦根**: 那么在企业文化方面，你具体做了哪些根本性重塑？它发生了怎样的蜕变？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: what have you done? What have you just tell me about the corporate culture? How has that changed?

</details>

**斯宾塞·拉斯考夫**: 我们将企业文化全面转向：**高度优先并重奖大胆创新，哪怕面临失败的风险也在所不惜**。

我一直对亚马逊当年的一个经典案例推崇备至：当年亚马逊倾注全力推出Fire Phone手机试图正面硬刚苹果，结果彻底惨败。然而在一年后关停该项目时，亚马逊非但没有惩罚或开除项目组成员，反而大张旗鼓地将整个Fire Phone研发核心团队提拔晋升，并分配到公司其他重大创新岗位上！这种在失败中保护敢于冒险者的企业文化深深启发了我。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: uh we we move to a culture that prioritizes and rewards innovation even if at the risk of failure. So I was always um you know you remember when Amazon launched the Firephone they were going to compete with Apple and build a phone. When Amazon shut that down a year or two later Amazon very famously promoted the whole team that built Firephone they put them in other roles in the company. instead of firing them, they promoted them. And that story always, you know, that that always inspired me.

</details>

**尼古拉·坦根**: 从零重塑一家成熟企业的企业文化，通常需要耗费多长时间？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How long time does it take to change corporate culture?

</details>

**斯宾塞·拉斯考夫**: 我最初做好了打持久战的准备，以为至少要花上两到三年。但令人欣慰的是，我们在一年左右的时间里就看到了文化与士气的剧烈转折。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I thought it would take longer. I thought it would probably take two or three years. I was able to change it in about a year.

</details>

**尼古拉·坦根**: 你觉得在美国重组团队和调整员工，是不是比欧洲其他地区推进得更快？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: do you think it's quicker to change people in the US than elsewhere?

</details>

**斯宾塞·拉斯考夫**: 可能确实有一些法律机制上的差异，欧洲某些国家的劳动法对人员调整有着更严苛的流程限制。但在任何企业重组中，有些心力交瘁或理念不合的人员必须果断汰换，从而为那些满怀斗志、具备全新思维模式的优秀血液腾出施展舞台。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: H maybe. I mean the the employment laws are a little harder to exit people in certain countries in Europe. Um some people need to be exited and then replaced with people who have a different attitude and already are aligned with this new culture.

</details>

**尼古拉·坦根**: 在今天的环境下，你最看重并倾向于招募什么样的人才？你在面试中寻找什么特质？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: what what are what are the type of people you hire? What do you look for?

</details>

**斯宾塞·拉斯考夫**: 尤其是在当今这轮AI爆发的技术浪潮中，**我最渴望招募的是那些拥有极致好奇心、动手能力极强的折腾者与构建者（Tinkerers and Builders）**。我们现在招进来的大部分优秀人才，业余都有自己的‘副线任务’（Side Quests）和探索项目。

现在我在面试中必问的一个高频问题就是：‘你在业余时间用AI鼓捣了什么好玩的东西？’有候选人回答说：‘我下个月要和一大家子去度假，为了协调好20个人的行程，我用**Claude Code**直接手搓了一个定制Web全栈应用，让全家人同步日程、共同规划！’听到这种答案我就会两眼放光，这就是我们极度渴望的人才特质！

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Especially in this AI world, I'm just looking for people with intense curiosity who are tinkerers and builders. Um, most of our people that we hire now have side quests, side projects. Like a very common interview question I'll ask is, "What are you using AI for, you know, on the side to build and and and tinker?" And they'll say, "Well, I'm I'm going on vacation next month with my extended family, and so I built a web app for, you know, the 20 of us that are going on this trip so everybody can coordinate schedules and we can plan together." And I use Claude Code to to build that. Like that's

</details>

**尼古拉·坦根**: 那么在工作之外，你自己用AI鼓捣了些什么业余小项目？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: what What are you using for outside work?

</details>

**斯宾塞·拉斯考夫**: 在工作之外，我用AI写了一套交互式国际象棋小程序。我和我的三个孩子玩棋局时，我每走一步棋，系统就会通过短信自动推送到三个孩子的手机上，他们直接通过短信回复下一步走法。我们通过AI在短信上进行‘一对三’的父子国际象棋博弈。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: uh outside work. Um I built a chess game for my my three kids and I. So uh when I make a move, it sends a text message to all three kids and then they reply via text and it it move. So we're kind of playing oneon-ree chess using AI via text, for example.

</details>

**尼古拉·坦根**: 那你能下赢你的孩子们吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Do you beat them?

</details>

**斯宾塞·拉斯考夫**: 以前能轻松下赢，现在赢不了了！我年轻时曾是半职业级别的国际象棋选手，但现在孩子们成长得太快了。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I used to. I don't anymore. No, I I I was a kind of a semi-professional chess player when I was younger, but my kids have have gotten very good.

</details>

### 个人生活、深度阅读与历史镜鉴

**尼古拉·坦根**: 接下来聊几个轻松的个人生活问题：你在高强度工作之余通常如何放松自己？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Now, uh some personal questions. How do you relax?

</details>

**斯宾塞·拉斯考夫**: 我每个周末都会打匹克球，要么和朋友切磋，要么和家人一起打。此外，我和我太太感情极好，我们会一起喝点葡萄酒、一起在山野间长途徒步。我住处离海滩很近，大海和海浪的声音能带给我强大的精神重启。因此我给自己设定了一个目标：每年至少有100天要亲眼凝望大海，并在沙滩上长时间漫步放空。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, I play pickle ball every weekend, uh, either with friends or family. Um, I have a very close relationship with my wife. We hang out, we relax, we drink wine, we go for hikes. Um, I live pretty close to the beach and I love the ocean and the beach. They're very rejuvenating for me. So, I try to I try to see the ocean 100 days a year if possible and I go for walks on the beach quite a bit.

</details>

**尼古拉·坦根**: 在阅读方面你有什么偏好？平时都读些什么书？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What do you read?

</details>

**斯宾塞·拉斯考夫**: 我痴迷于阅读**1860年至1930年间的美国历史**。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I read American history 1860 to 1930. Uh the that's

</details>

**尼古拉·坦根**: 那段历史时期究竟有什么独特魅力深深吸引了你？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: and what's so good about that period?

</details>

**斯宾塞·拉斯考夫**: 那是美国经历极致快速工业化、社会文化剧烈动荡、商业组织形态发生颠覆性重构的激荡年代，极具历史张力。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Uh it's it was the period of rapid industrialization, huge ch cultural and and ch business change. Um and

</details>

**尼古拉·坦根**: 你觉得今天的商业与科技时代，与那个狂飙突进的年代相比有什么异同？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: how do you think today compares with that period?

</details>

**斯宾塞·拉斯考夫**: 我刚刚读完了两本宏大的商业传记：一本是罗恩·切尔诺（Ron Chernow）撰写的摩根财团史诗传记《**摩根财阀**》（The House of Morgan），另一本是关于商业巨头卡内基（Andrew Carnegie）的传记。那一代大亨的崛起历程让人叹为观止。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Well, uh you know, I just finished two biographies. one House of Morgan by Ron Cherno about JP Morgan, and then also a biography of Carnegie. And

</details>

**尼古拉·坦根**: 在他们的成功秘诀中，哪些方面让你最为触动？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: successful which parts

</details>

**斯宾塞·拉斯考夫**: 坦白说，他们当年的手段非常冷酷无情，很多在当年促成他们垄断商业帝国的行径，在现代反垄断法规与商业法下早已被判定为非法。但抛开这些阴暗面，他们构建现代商业组织与跨国企业的眼界与决断力依然令人惊叹。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: well they they were um cutthroat um but much of what they did to make them successful is illegal today. But they built incredible institutions.

</details>

**尼古拉·坦根**: 纵观这些历史风云人物，你内心最崇拜的领导者是谁？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So when you look at all these leaders who do you admire the most?

</details>

**斯宾塞·拉斯考夫**: 我最钦佩的领袖大概是**西奥多·罗斯福**（Teddy Roosevelt）。他是一位不可思议的沟通大师，他身上那种充满野性活力的紧迫感与不知疲倦的行动力，最能引发我强烈的精神共鸣。我本人也是一个永不停歇的行动派，罗斯福亦是如此。而且，他对自然保护与国家公园体制的深远贡献令我无比崇敬，他在自然环保上的超前远见领先了他所处时代整整一百年。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, I probably admire Teddy Roosevelt the most because of, you know, he was I I he was an incredible communicator. His um rambunctious sense of of urgency and activity resonates most with me. I'm I'm a I'm constantly in motion and so was Teddy Roosevelt. And his love of conservatism and nature also really motivates me. I he was a hundred years ahead of his time in recognizing the importance of environmentalism

</details>

**尼古拉·坦根**: 确实，他当年为美国乃至全球奠定的自然保护区与国家公园体系，让百年后的我们至今受益匪浅。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: and um and you we today are still grateful for what he gave to us in in terms of creating the modern national parks system.

</details>

### 摇滚巡演童年、人生至暗与听力代价

**尼古拉·坦根**: 就像你们约会应用上的用户渴望看到对方完整真实的画像一样，为了让听众更全面地看清你：回望过去，你经历过最大的个人失败或挫折是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: A bit like your audience uh on the apps, people like a full view of other people. So to get a fuller view of you uh what is the biggest personal failure you've made?

</details>

**斯宾塞·拉斯考夫**: 在我整个职业生涯中，我经历过多轮极其艰难的裁员。接任Match Group后不久我就推动了一轮组织精简，但这更多是接盘旧问题的被动调整。真正让我感到痛苦的是：2008年全球金融危机爆发时，我们在Zillow不得不推行裁员；而在2001年‘9·11’事件重创全球旅游业时，我们在Hotwire也被迫推行了裁员。在企业遭遇灭顶危机时做出裁员决定，在心理上是非常沉重的煎熬。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: You know, I've had several layoffs in my time, including one at Matchgroup shortly after I began. I don't really view that one as a failure because I didn't hire into that situation. But I in 2008, we did layoffs at Zillow in response to the financial crisis. In um 2001 at Hotwire, we did layoffs in response to the 9/11 crisis.

</details>

**尼古拉·坦根**: 这些属于不可抗力下的商业磨难，那在你的个人生活中有过惨痛的重大失误（Big Screw-ups）吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: But these are kind of business failures. What about some personal... personal failures? Big screw. Have you had some big screw-ups in your life?

</details>

**斯宾塞·拉斯考夫**: 谢天谢地，摸摸木头（Knock on wood），在个人决策上我没有经历过毁灭性的大错。如果说有什么心结，那就是挥之不去的遗憾：我的父母都已经离世，我的亲哥哥也在年轻时过早离开了我。虽然我和他们的关系一直非常亲密，但如今每每回想，我依然深深懊悔当年没有在他们健在时，投入更多的时间和精力去陪伴他们。这或许不能被定义为失败，但这绝对是我人生中最大的遗憾。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I haven't had a lot of big screw-ups in my life. Knock on wood. Um, uh, no. I mean, I have regrets. My parents have both passed away. My brother passed away at a young age, and I had very close relationships with them, but obviously I regret not having invested more time and focus in those relationships when they were available to me. They're not really failures, but they're regrets.

</details>

**尼古拉·坦根**: 有什么关于你的小秘密是绝大多数人不知道的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What are uh what's something about you that most people don't know?

</details>

**斯宾塞·拉斯考夫**: 很多人不知道我年轻时曾经是一名专业国际象棋棋手，我从棋盘博弈中汲取了大量战略思考养分。另外，我从小是在顶级摇滚乐圈子里摸爬滚打长大的，这也直接导致我现在有点重听、听力有些受损。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, you know, I I was a competitive chess player and and take chess pretty seriously and learned a lot from chess. Um, my I I grew up in and around the music industry, which is why I'm a little bit hard of hearing. I I've got a kind of

</details>

**尼古拉·坦根**: 因为你的父亲当年曾作为核心经纪人为许多传奇摇滚乐队操盘巡演，对吧？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Because your father was touring with some famous bands, right?

</details>

**斯宾塞·拉斯考夫**: 是的，我的父亲是**滚石乐队**（The Rolling Stones）、**U2**、大卫·鲍伊（David Bowie）、保罗·西蒙（Paul Simon）以及**平克·弗洛伊德**（Pink Floyd）等伟大摇滚巨星的全球巡演制作人兼首席商务经理。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: My father was the tour producer and business manager for the Rolling Stones and you two and Dave Bowie and Paul Simon and Pink Floyd.

</details>

**尼古拉·坦根**: 所以你小时候就一直跟着父亲泡在这些世界顶级巡演现场？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So, but did you come along to those tours?

</details>

**斯宾塞·拉斯考夫**: 没错！事实上，我人生中唯一一次来到奥斯陆，正是1990年跟随滚石乐队的全球巡演来到这里的。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: I did. I did. In fact, that's the the one time I've been to Oslo was with the Rolling Stones in 1990 uh on the on the the Urban Jungle.

</details>

**尼古拉·坦根**: 在那次震撼的‘城市丛林’（Urban Jungle）巡演中，哪支乐队是你心目中最喜爱的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What's your favorite band? Urban Jungle.

</details>

**斯宾塞·拉斯考夫**: 虽然我和滚石乐队相处的时间最长、看过的滚石现场演出最多，但单从音乐口味而言，**U2**才是我个人最深爱的乐队，也是我日常听得最多的旋律。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Um, you know, I spent the most time with and I've seen the most Rolling Stones concerts, but I think in terms of of musical tastes, you two is is my favorite band. They're the music that I listen to the most today.

</details>

**尼古拉·坦根**: 这段童年经历真的对你的听力造成了永久损伤吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So, did it really impact your hearing?

</details>

**斯宾塞·拉斯考夫**: 确实造成了不可逆的损伤。从两岁起，我就被带着出入各类巨型摇滚音乐节。在20世纪70年代，滚石乐队现场的声音震耳欲聋，还有莱纳德·斯金纳德（Lynyrd Skynyrd）等众多大声量乐队。今天当我在音乐会上看到父母极其明智地给两三岁的孩童戴上专业防噪隔音耳罩时，我总会感叹：我当年的童年可完全不是这样的。那时候我整个人就直接站在几十米高的舞台主音箱旁边，没有任何护耳装备，所以听力确实付出了不小的代价。

<details>
<summary>Original English</summary>

**Spencer Rascoff**: It it actually did. Yes. I mean, starting at age two, I would go to concerts. And back then in the 70s, we, you know, Stones concerts were very loud and Leonard Skard concerts and 38 Special and lots of other bands that uh that my dad was producing their tours for. And we, you know, when I'm at concerts today and I see little little three-year-old toddlers with those big headphones cuz parents are very intelligently putting headphones, I think to myself, you know, that was that was not the way I grew up. I was uh st stand s stand s stand s stand s stand s stand s stand s stand s stand s stand s stand s standing right next to the speaker and no no no uh you know no headphones for me. So I'm

</details>

### 逆潮流的职业忠告：给Z世代年轻人的奋斗箴言

**尼古拉·坦根**: 斯宾塞，除了提醒大家看音乐会记得戴护耳耳机之外，你对于刚刚踏入职场的年轻人，有哪些最重要的核心建议？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So Spencer, in addition to using headphones, uh what are the other piece of pieces of advice for young people today?

</details>

**斯宾塞·拉斯考夫**: 我的女儿今年刚满21岁，正在步入职场，而且她选择的正是你们的领域——金融服务与投资银行。我给我的女儿以及所有年轻毕业生的职业建议如下，虽然现在的年轻人可能并不爱听这些逆耳忠言：

**永远做每天早晨第一个到达办公室的人，做每天晚上最后一个离开办公室的人！**

我知道在当下强调这种投入‘并不流行’，甚至政治不正确，但全身心倾注时间的价值绝对无可替代。你必须‘身处现场’（Be in the room）。千万不要在职业生涯初期去接受一份以远程办公（Remote）为主的工作！一定要选择每天线下到岗的岗位，因为在刚毕业时你必须像海绵一样疯狂吸收周围的一切养分，身处核心决策的房间内，近距离观察高手的言传身教。

**切忌在年轻时盲目过度追求短期薪酬最大化**。如果经济条件允许，宁可选择一份起薪稍低、但能让你学到成倍知识技能的岗位，全力为自己的成长复利投资。

在人生的最初阶段，必须将拼搏与工作置于极高优先级。或许到了接近30岁甚至更成熟的人生阶段，你可以开始平衡生活、更多关照个人享受；但特别是在职业生涯起步阶段，极致的努力是任何捷径都无法替代的。我知道时代的钟摆已经偏向了‘轻松安逸’，说出这些话并不讨好，但我必须撕下温情面纱说出真话：**在年轻成长早期，没有任何捷径可以替代倾其所有的全力以赴！**

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Well, I I mean my daughter is is 21 and is entering the workforce and she's going into your field. She's going into financial services and investment banking. And the advice I give to her and other students is be, you know, students, young people might not not like this advice, but be the first person in the office in the morning. be the last person to leave the office at night. I know it's not um it's not like fashionable to say, but putting in the time that's incredibly important. You need to be in the room. Don't take a job that's primarily remote. Ideally, take a job that's in office because you want to be a sponge. You want to try to be in the room and learn as much as you can. Don't optimize for short-term income. If you can afford to take that job that pays a little bit less, but you can learn a little bit more. try to optimize for education and and learning at at your young age and put in the effort. Work hard. There will again, I know this is not a popular thing to say, but there will be time a little bit later in life, maybe even as early as your late 20s when you can start prioritizing you. And but especially early career, you need to prioritize work. And again, I I think the pendulum has swung such that that's not a very favorable thing to say anymore. But I'll I'll say the the quiet part out loud, which is there's no substitute for that type of effort, especially early career.

</details>

**尼古拉·坦根**: 是的。毫无疑问，你本人一直在身体力行这套标准，永远是办公室里最早到岗的人。作为你们重要的大股东，我们由衷敬佩并感谢你的辛勤付出与执着努力。今天与你的对话非常精彩，十分感谢！

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Yeah. Well, you for sure are putting in the hours. You are the first guy in the office and as big shareholders, we very much appreciate all your hard work. It's been great speaking to you.

</details>

**斯宾塞·拉斯考夫**: 非常感谢你的邀请，今天的交流非常畅快有趣！

<details>
<summary>Original English</summary>

**Spencer Rascoff**: Thank you for having me. This is fun.

</details>

**尼古拉·坦根**: 非常希望大家喜欢本期播客对话。如果你喜欢我们的内容，请务必点赞、订阅并开启通知小铃铛，这能极大帮助我们邀请到更多优秀的重磅嘉宾！

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Really hoped you liked the episode. If you did, please like it, subscribe, and put on the notification. This really helps us to get new great guests.

</details>