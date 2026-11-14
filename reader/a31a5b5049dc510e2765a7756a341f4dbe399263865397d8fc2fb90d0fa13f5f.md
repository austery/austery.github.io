---
author: The Pragmatic Engineer
date: '2026-04-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CZs8J1ZD0CE
speaker: The Pragmatic Engineer
tags:
  - agile-methodology
  - software-development
  - artificial-intelligence
  - developer-productivity
  - technology-adoption
title: 马丁·福勒与肯特·贝克：AI浪潮下软件工程的变革与坚守
summary: 在一次深度访谈中，**马丁·福勒**和**肯特·贝克**两位软件工程界的领军人物，回顾了**敏捷宣言**诞生25年来的深远影响，并深入探讨了当前**人工智能**对软件开发领域的冲击。他们对比了AI与过去诸如**面向对象编程**、**互联网**和**微处理器**等技术浪潮的异同，强调了在技术巨变中保持批判性思维和强烈好奇心的重要性。两人讨论了AI作为“放大器”的角色、它对不同经验层次工程师职业发展的影响，以及对“代码”本质的重新定义。他们也分享了对大型企业在AI面前的“大规模混乱与恐慌”的观察，并提出了在AI时代下，如何通过坚守良好的工程实践（如**模块化代码**、**良好测试**）和专注于领域理解来保持竞争力和创新力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Martin Fowler
  - Kent Beck
companies_orgs:
  - ThoughtWorks
  - OpenAI
  - Intel
products_models:
  - Copilot
  - Emacs
  - Gemini
  - Cloud Code
media_books:
  - Refactoring Book
status: evergreen
---
### 开场与敏捷宣言的25周年

**Host**: 欢迎大家。很高兴见到各位。很高兴见到这么多友善的面孔。很多人都打招呼了，也很高兴见到**马丁**和**肯特**。我之前开玩笑说，我没想到**马丁·福勒**和**肯特·贝克**会出现在一个到处都是最热门AI初创公司的地方。但我们在这里，而且是为了一个非常非常好的理由。

<details>
<summary>Original English</summary>

**Host**: Welcome everyone. It's it's it's so nice to see all of you. It's so nice to see lot lot of friendly faces. A lot a lot of you said hi and also just really good to to meet Martin and Kent. And I was joking a little bit beforehand that I did not expect Martin and Fowler and Kent Beck to walk into a place where it's all the kind of the hottest AI startups and all of them. But here we are. And we're here for a very, very good reason.

</details>

**Kent Beck**: 什么？这到底是什么意思？

<details>
<summary>Original English</summary>

**Kent Beck**: What? What the hell is that supposed to mean?

</details>

**Host**: 哦。天哪，开始了。**肯特**会为此恨我，因为我今天已经称他为“老古董”一次了。

<details>
<summary>Original English</summary>

**Host**: Oh. Oh gosh. Here we go. So Kent is going to hate me for this cuz today I already called him old furniture once.

</details>

**Martin Fowler**: 我不觉得这公平。

<details>
<summary>Original English</summary>

**Martin Fowler**: I don't think that's fair.

</details>

**Host**: “老古董”。是啊，你是人群中的老前辈。

<details>
<summary>Original English</summary>

**Host**: Old furniture. Yeah, you're the old guy in the crowd.

</details>

**Host**: 我至少比他年轻一岁。但我很高兴你们两位都在这里。一周前，我、**马丁**、**肯特**和许多其他人都在犹他州鹿谷参加了**马丁**召集的一些非常有趣的思想家参加的“软件工程的未来”会议。我们当时在讨论，很高兴能反思25年前**敏捷宣言**是如何诞生的。当时有17个人，你们两位都在场。从那时起，你们确实帮助塑造了软件工程，并产生了重大影响。我能请你们两位回顾一下这些年、这几十年里你们收到的反馈吗？哪些想法真正深入人心？你们经常听到工程师们对你们说什么，比如“谢谢你们，我正在大量使用这个”？

<details>
<summary>Original English</summary>

**Host**: I'm at least a year younger than him. Uh but we're I I I'm psyched that both of you are are here and a week ago me, Martin Kent, and a bunch of other people were in Deer Valley, Utah in the future of software engine conference that Martin pulled together some some very interesting thinkers and we were talking about like it was nice to reflect that 25 years ago the agile manifesto was created. There were 17 people and and two of you and you were two of you were there. Since then, you've really helped shape software engineering as you've helped influence and and you've had major contributions. Could I ask both of you to like recap what the feedback you've gotten over over these these years, these decades, what ideas really stuck with engineers? what what what do you hear a lot they tell you like thank you for this I'm using a lot of this

</details>

**Martin Fowler**: 这是个非常有趣的问题，我真的没有好好反思过。我的意思是，很多人泛泛而谈我们所做的工作，无论是广义上的**敏捷**还是具体到我这边的**重构**，因为那是我写的一本书。但我不知道其中是否有任何部分是必然的。

<details>
<summary>Original English</summary>

**Martin Fowler**: that's a really interesting question I haven't really reflected on that I mean a lot of people talk about things in general that we've worked on um whether it's agile broadly or refactoring particularly in my case because that was a book I worked on um but I don't know anything where any of the pieces of that necessarily

</details>

**Kent Beck**: 我会得到“非常感谢您的**测试驱动开发**”。我也会得到“这个**测试驱动开发**毁了我的生活。我的狗离开了我，我的房子烧毁了，这都是你的错。” 所以，我不知道。这回答你的问题了吗？

<details>
<summary>Original English</summary>

**Kent Beck**: so I Get thank you so much for test driven development. I also get this test test driven DEVELOPMENT ruined my life. My dog left me, my house burned down, and it's all your fault. So, I don't know. Does that answer your question?

</details>

**Host**: 我认为**TDD**一直备受争议。我曾经一度是信徒，然后又讨厌它。但这很有趣，因为我觉得很多东西都是这样的，对吧？它们旨在引发思考，旨在推动你前进。

<details>
<summary>Original English</summary>

**Host**: I I think TDD has has been very divisive. I I've been a I' I've been a convert at some point and then I I hated it. But it's interesting because I feel a lot of a lot of the are like this, right? They're meant to be provocative. They're meant to push you.

</details>

**Kent Beck**: 是的，我昨天也和一个正在大力推动**AI**前沿的人聊天。他的评论是：“多亏了你们过去20年来对**TDD**的所有推动，因为它现在变得非常重要，我们有了**AI代理**。”听到这样的反馈很有趣，因为我总是对此持怀疑态度，因为我希望它是真的。你知道，我是那种听到自己喜欢的东西时，会想“我这是不是在凭空捏造？”的人。但对我来说，它确实有道理，你知道，当我们拥有一个强大**精灵**（AI）时，你真的必须学会如何验证它是否在为你做正确的事情。

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. I also got uh was actually chatting with somebody uh yesterday who's really pushing the AI envelope. And his comment was, well, thank goodness for all of your pushing of TDD for the last 20 years because it's really important now we've got AI agents. And uh it it's interesting to hear that feedback because um I'm always suspicious of it cuz I want it to be true. You know, I'm the kind of guy who when when I hear something I like, I'm I'm kind of thinking, am I just making this up? But uh it does make sense to me that, you know, when we've got a big powerful genie, you really have to learn how to verify that it's doing the right thing for you,

</details>

**Martin Fowler**: 这正是我们已经实践了25年的事。

<details>
<summary>Original English</summary>

**Martin Fowler**: which we've been practicing for 25 years.

</details>

**Kent Beck**: 是的。好吧，我的意思是，我自己并不是一个强大**精灵**，但我仍然需要测试来确保我做的是正确的事情。

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. Well, I mean, I'm not a big powerful genie myself, but I still needed the tests to make sure I was doing the right thing.

</details>

### AI时代下软件工程师的日常与挑战

**Host**: 这里的很多人都会通过我们一起做的播客认识你们。他们可能读过你们的一些书。**马丁**，你真的是一个完美的作家。但你能告诉我们，你现在都在忙些什么？你日常的工作是什么样的？你是如何与技术保持同步的？我收到过一条非常无礼的评论，我还在为此在**领英**上和人争论。他们说：“哦，你们的会议，你们请来的作者都脱离了技术。”我说：“你甚至知道**马丁·福勒**和**肯特·贝克**是谁吗？” 但我只是想问，这些天你们到底在忙些什么？认真的。

<details>
<summary>Original English</summary>

**Host**: So, a lot a lot of folks here, they will know you from the podcast that we did together. They might have they probably read some of your books. Barton, you're really perfect writer, but can you tell us what are you up to these days? What does your day-to-day look like? How do you stay in touch with technology? I got a really rude comment that I'm still I got to fight into someone on LinkedIn about this. They said like, "Oh, your your conference like you're having authors here who are like out of touch with technology." And I'm like, "Do you even know who Martin Valer and Kemp Beck is?" But I just want wanted to to ask like these days, how what are what are you up to? Seriously?

</details>

**Martin Fowler**: 嗯，当我完成**重构**书的第二版时，那是在五六年前了，我曾考虑过写另一本书。我有一些写了一半的书放在那里。但我决定我不应该那样做。相反，我应该做的是和那些仍在实际项目中，编写实际代码的人合作，让他们把他们的想法和所学分享出来。所以，从那时起，这一直是我的主要项目，主要集中在**martinfaller.com**网站上，因为嘿，我能控制它。没有哪个大公司会突然介入并把它搞砸。至少在我没有出卖它并从中获得大量金钱的情况下。

<details>
<summary>Original English</summary>

**Martin Fowler**: Well, my I when I finished the second edition of Refactoring Book, which was, you know, five or six years ago, I toyed with the idea of writing another book. I've got several half-written books out there to work on, and I decided I should not do that. Instead, what I should do was work with people who are actually still doing real work on real projects, writing real code as it were. Um, and get them to get their ideas out and what they learn out. So, that's been my main project ever since, primarily focused on the martinfaller.com website because, hey, I control that. There's no big corporation that's going to sweep in and and clobber it. At least not without my um me selling out and getting lots of money out of it. Um

</details>

**Martin Fowler**: 随着**AI**时代的到来，我一直非常热衷于捕捉这些变化。我的主要关注点是试图重新理解人们工作流程的细节以及他们究竟在做什么。他们与**精灵**（AI）之间有哪些对话，正如**肯特**所说。而且，如果你在审查这些东西，你在寻找什么？特别是我们人类仍在做哪些决策，以及决策流程是如何变化的。所以，我的兴趣不在于我自己在做什么，而在于我的同事们在做什么，并试图传播这些。这才是我的重心。

<details>
<summary>Original English</summary>

**Martin Fowler**: and um as the AI thing has come, I've been very keen to capture that. And what my big focus is on is trying to re understand details of people's workflow and what exactly they are doing. what are the kind of conversations they're having with the genie as as Kent um calls it and you know what if you're reviewing things what are you looking for if and particularly what decisions are you are we the humans still making and how is that decision flow changing um so that's my interest is it's not what I'm doing it's what my colleagues are doing and trying to spread that around and that's that's my focus

</details>

**Kent Beck**: 我的个人使命是帮助**极客**们在这个世界上感到安全。然而我们的同行们现在并不感到安全，这有充分的理由，也有一些不充分的理由。我注意到的一件事是，25年来，我们似乎总有答案。有人来找我们说“我们有太多bug了”，我们就会说“好吧，这是你写测试的方法”。“哦，我不能写测试。”“好吧，这是你设计以便可以写测试的方法。”就像按下录音机播放键一样。而现在改变的是，此刻没有人知道任何事情的答案。

<details>
<summary>Original English</summary>

**Kent Beck**: and so I've been uh my personal mission in life is to help geeks feel safe in the world. And uh our people do not feel safe right now for some good reasons and some not good reasons. And one of the things I noticed is for 25 years we've kind of had the answers. Somebody comes to us and says we have too many bugs. Or like all right, well here's how you write tests. Oh, I can't write tests. Well, here's how you design so you can write tests and just kind of press play on the recorder. And the thing that's changed is at this moment nobody knows the answers to anything.

</details>

**Kent Beck**: 所以我一直在努力做的是，既为了满足我自己的**极客**好奇心，也为了尽可能地探索和发现如何利用这些新工具提高效率，然后向下一代人展示这些，他们过去习惯于得到答案。哦，我遇到了一些麻烦，让我去书里找解决方案。这在过去20年都有效，但在过去一年中它不再有效，而且在很长一段时间内都不会有效。所以，作为前辈，我认为我们有责任不仅要展示如何有效使用这些工具，还要展示如何**弄清楚**如何有效使用这些工具，因为这是一整套不同的技能。

<details>
<summary>Original English</summary>

**Kent Beck**: And so what I've been trying to do is both for my own geeky curiosity satisfaction, let me go back into explore mode and find out as well as I can uh what you can do to be effective with these new tools and then demonstrate that to the next generation of people who've been used to getting answers. Oh, I'm having some trouble. let me look up in the book what the solution is that that worked for the last 20 years and it doesn't work for the last year and won't work for the an extended period. So, as seniors, I figure it be behooves us to demonstrate not just how to use these tools effectively, but how to figure out how to use these tools effectively because that's a whole different set of skills and you say all right we don't know what what will come how no one has to figure it out.

</details>

### AI：比以往更强大的技术变革

**Host**: 我想带你们回到你们的职业旅程。你们在这里分享的一件事是，你们比我们很多人，包括我自己，以及房间里的很多人，都见证了更多的变化。你们还记得曾经有过一项技术变革，其不可预测性或可怕程度与现在的**AI**类似吗？在你们的职业生涯中，最接近的是什么？

<details>
<summary>Original English</summary>

**Host**: I wanted to take you back into your professional journey. One thing that you share here you have seen a lot more than a lot of us myself included a lot of people in in the room as well. Do you remember a time where there was a technology change which looked similarly kind of unpredictable or scary like AI does right now? What was the thing that comes the closest in your career?

</details>

**Martin Fowler**: 嗯，没有任何东西能像**AI**这样产生如此巨大的影响。我的意思是，这与我们之前面临的任何事物都完全不同。在较小的规模上，我会说，我们非常深入地参与了**面向对象语言**的发展。我的意思是，这吓坏了很多人，但对我们来说并没有那么可怕，因为我们是其中的一部分。我会说，**互联网**的影响对我们所有人都有巨大的影响。当然，很明显，我们当时正在推广**敏捷软件开发**的挑战，这对很多组织产生了巨大的影响，因为你可以通过他们抵制它的程度来判断。但关于**AI**的特点是，所有这些事情我们都在谈论它们有多重要，多有价值，并试图说服人们它们的重要性。是的，甚至是**互联网**，这听起来可能令人惊讶，但当时确实有人认为它不重要。但对于**AI**，关于其重要性几乎没有争议。人们无法否认它的重要性。

<details>
<summary>Original English</summary>

**Martin Fowler**: Well, nothing has hit with the magnitude of AI. That's I mean this is a a whole size difference from anything that we've faced before. um on a smaller scale um I would say and we were very much involved in the the growth of object-oriented languages I mean and that scared a lot of people it didn't scare us so much because we were part of it um I would say that the impact of the internet um had a huge impact upon us all um and of course obviously we were spreading the the the challenge of agile software development and that had a very big impact on a lot of organizations because you could tell by how hard they resisted it. Um, but the thing about AI is that you know all of these things we were talking about how important they were and how valuable were and trying to persuade people of the importance of them. Yes, even the internet that may sound surprising but there were people who would weren't thinking that was important. Um, but AI there's kind of no argument about how important it is. People can't I mean you cannot put blinkers on to deny the importance of this thing.

</details>

**Kent Beck**: 我想到的另一个类比是**微处理器**的引入。在那之前，计算机是一个大盒子。你不能搬动它们。如果你想要另一个，你得再次抵押你的房子。那是一个大事件。当**Intel 4004**出现时，我还是个在硅谷的**程序员**的儿子，我们当时想：“等等，那是一台电脑。”天哪，可能性突然扩大了。如果你能弄清楚如何编写软件，如果你能弄清楚如何围绕这个东西设计硬件，你就能突然做一些我们甚至无法想象的事情。所以，我认为**AI**的一部分就是这种想象力的扩展。所以，我正在写一些极其雄心勃勃的项目。我正在研究一个持久化**Smalltalk**。我正在为**Rust**编写库质量的代码。我只是，你知道，任何我能想象到的尝试，我都会去尝试，看看结果。现在，其中很多会失败，那没关系。那是这个过程的一部分。但这并不是**上天**第一次开启并给我们带来了大量新机会。

<details>
<summary>Original English</summary>

**Kent Beck**: So the the other analogy that I have is to the introduction of the microprocessor. Before that, computers were a big box. You couldn't move them around. If you wanted another one, you'd mortgage your house again. It was a it was a big it was a big deal. And I was a kid in Silicon Valley with my dad as a programmer when the Intel 404 hit and we went, "Wait a minute, that's a computer." Oh my goodness, the the possibilities suddenly expanded. If you can figure out how to write software, if you can figure out how to design hardware around this thing, you can suddenly do things we can't even imagine. And so, uh, I think part of AI is this expansion expansion of imagination. So, I'm writing projects that are ridiculously ambitious. I'm uh working on a persistent small talk. I I'm writing library quality code for Rust. I'm just, you know, anything I can imagine to trying to do, I'm going to try and do it and see. Now, a bunch of those fail and that's fine. That's part of this process. But um it it's not like this is the first time the heavens have opened and and we've been brought tons of new opportunities

</details>

### 技术变革中的怀疑与好奇

**Host**: 回到**面向对象**的普及，或者**微处理器**。你还记得当时行业里的感受吗？经验丰富的专业人士，他们在这个新世界里茁壮成长，而那些被抛在后面的人，他们之间有什么区别？

<details>
<summary>Original English</summary>

**Host**: and back either with with object-oriented spreading or with microprocessors. Do you remember what the the feeling was in the industry and what was the difference between experienced professionals who you know just got thrived in this new world and ones who were just honestly left behind?

</details>

**Martin Fowler**: 是的，所有这些情况都存在着一种矛盾的感觉，介于追逐炒作的人和那些说“这没什么特别的”人之间。我认为你总是需要**怀疑**和**好奇心**之间的平衡，才能做到这一点，而且你是有选择性的。我的意思是，我曾经对一些重大的变化持完全的怀疑态度。我的意思是，比如**区块链**，我对此非常怀疑。但是，正如我喜欢说的，关于我对技术的怀疑，它根深蒂固，因为这些年来我看到了行业里太多“**蛇油**”式的宣传。我的怀疑必须是绝对和全面的，这意味着我必须怀疑我的怀疑，这需要**好奇心**。我认为这就是关键所在，你必须足够好奇，才能说这看起来像，但也许不是。我如何探究才能发现那里有一些东西正在出现？

<details>
<summary>Original English</summary>

**Martin Fowler**: Yeah, there with all of those there was that sense of the mix between the the the people chasing the hype and the the people who were saying no this is nothing special. Um I think it you've always got to have that balance of skepticism and curiosity um in order to be able to do that and you are selective about it. I mean I have been completely skeptical about some big um changes. I mean um blockchain for instance I was extremely skeptical about that um and but as I like to say you know about about my skepticism about technologies which is well rooted because I've seen so much snake oil projected out by the industry um over the years my skepticism has to be absolute and total which means I have to be skeptical about my skepticism and that requires that curiosity and I think that's where the thing is you've got to be curious enough to say may this looks like but maybe it isn't. How do I probe in order to detect that there's signs of of something coming out there?

</details>

**Kent Beck**: 是的。我能进行最小的实验是什么，以验证它是否满足我自己的要求？每个人的满意度都会不同，这取决于这个说法是否属实。这项技能在过去一年中突然变得宝贵了**一千倍**，那就是这项技能，它能让你说：“我能做些什么最少的事情，以验证这个说法是否属实，直到我满意为止？”

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. What what's the smallest experiment I can run to verify to my own satisfaction and everybody's level of satisfaction is going to be different whether or not this claim is true. That's that's the skill that has suddenly in the last year become a thousand times more valuable is that skill of saying what's the least I can do to validate for my to my own satisfaction whether this claim is true or not.

</details>

**Martin Fowler**: 但这里面还有另一步，你必须意识到你早期的互动可能并非一个真实的信号。我的意思是，当我开始玩弄**AI**时，大概是一年半前，那是**Copilot**之类的东西，我当时很不以为然，对吧？我的意思是，我是一个**Emacs**爱好者。我设置了**Emacs**。那是一个真正的编辑器。我设置了**Emacs**，这样我就可以让它自动提示和完成，因为**Emacs**有能力做到这一点。我用了大约三四天，然后就放弃了，因为有时它会给你一些很棒的东西，但大多数时候它给你的都是垃圾，你会立即按下**Control+K**删除它。如果这就是我对**AI**的印象，而且我说这就是我对**AI**的看法，我就会像对待**区块链**一样，立即把它打入“蠢货”名单。但另一方面，我还在不断探索。所以我在这方面最有价值的发现是隔壁房间里**西蒙·威利斯**的博客，我读了，从中我学到的一点是，要用好这个工具，你必须学会如何用好它。这对于**面向对象**也是如此，人们会说“哦，对象”，你看他们当时在做什么，他们并没有很好地使用对象。事实上，我们，**肯特**和我，当时就觉得他们用的是**C++**和**Java**，但他们并没有真正做那些真正的事情。但关键是，你还必须倾听外面的人的声音，并能够以批判的眼光阅读，形成一种判断，即如果你确实遇到了**西蒙·威利斯**这样的人，他是在夸大一切美好的事物，还是在同时认识到真正的问题，并给我提供真实的信息？我发现这真的是一个很重要的判断。我的意思是，当人们给你好坏兼具的平衡，而且最重要的是，他们愿意说“我不知道”时，那里面就值得倾听。所以他，还有我**ThoughtWorks**的一些同事，比如**迈克·梅森**和**比特·伯克尔**，他们真的让我明白，哦，我不应该过分依赖我的第一反应。

<details>
<summary>Original English</summary>

**Martin Fowler**: But there's also another step in there that you also got to be aware that your early interactions may not actually be a true signal. I mean, when I started playing around with AI, I guess it was the co-piloty like stuff about a year, year and a half ago, I was pretty unimpressed, right? I mean, I I set up I'm an Emacs guy. I set up Emacs. The one true editor. Um, I set it I set up Emacs so that I could just have it prompt and complete automatically because, you know, Emacs is capable of doing that. And I used it for maybe three or four days before I just got because sometimes it would give you something wonderful but most of the time it gave you such garbage that you would just control K right away. And if that had been my impression of AI and I have said that's what I think of AI, I would have just immediately flip the bozo switch on it just like I did with blockchain. But on the other hand, I'm also probing out there. So my my most valuable discovery in all of this is in the room next door Simon Willis's blog which I read and one of the things that I took from that was to use this tool well you have to learn how to use it well which was also something very true of object orientation people would say oh objects you know and I you look at what they were doing you're not using objects very well in fact we kind of mckent I were kind of at yeah they were using C++ and Java they didn't actually do the real stuff. Um, but the the point was you have to be also listening to the folks out there and being able to read with a critical eye and getting a sense of okay, if you do run across a Simon Willis, is he hyping everything wonderful or does he seem to be recognizing real problems at the same time and giving me straight stuff? And that I found was a really I mean when people give you that balance of good and bad and also most importantly are prepared to say I don't know then that that involves something to listen to. So him and also some of my colleagues in Fort Works like Mike Mason and Bit Berkel they really kind of showed me that oh I've shouldn't be relying too much on my initial reactions.

</details>

**Kent Beck**: 是的，而且它每周都在变。我我我我这周尝试用**Gemini**做点什么，结果一塌糊涂。这个**Gemini**，这个**Cloud Code**，然后它工作得很好，然后又不行了。然后我用**Gemini**做同样的事情，这周它就行了，上周却不行。你知道，人们想要答案，但答案却在不断变化。所以在这个环境下，你不可能拥有答案。这是坏消息。好消息是，没有人有答案。所以你和别人一样聪明，因为你和别人一样无知。

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah and it can change week to week. I I'll I'll I'll I'll try something with Gemini one week fails miserably. This Gemini thing cloud code then that works pretty well and then it's doesn't work well and then I tried Gemini for the same thing and it works this week and it didn't work la last week. That's a you know people want the answer and the answer is changing. So you can't possibly in this environment have the answer. Now, that's the bad news. The good news is nobody else has the answer either. So, you're just as smart as everybody else because you're just as ignorant as everybody else.

</details>

**Host**: 这能让人安心吗？

<details>
<summary>Original English</summary>

**Host**: Is that reassuring?

</details>

**Host**: 这能让人安心吗？举手示意。有一点让我觉得有点相似的是，回到2001年，差不多正好是25年前，当**敏捷宣言**问世时，那个网站上列出了所有17个名字，**肯特·贝克**是第一个。我们为什么是第一个？

<details>
<summary>Original English</summary>

**Host**: Is that reassuring? By a show of hands. One thing that struck me as like a bit of a similarity is back in 2001 when the almost exactly 25 years ago when the agile manifesto came out with that website with all the 17 names listed and Kent Beck being the first one. Why were we the first one?

</details>

**Kent Beck**: 按字母顺序，严格按字母顺序，但它是一个无尽的快乐源泉。你可以充分利用它。

<details>
<summary>Original English</summary>

**Kent Beck**: Alphabetical strictly alphabetical but it is a source of unending joy. You can very much take of that.

</details>

### 敏捷与AI的对比：承诺与现实

**Host**: 这在行业中引发了一些非常有趣的事情，因为我的解读是，如果你使用**敏捷**，这里有四个相当简单易懂、易于认同的东西，可以构建更好的软件，更快、更便宜、质量更高，应有尽有。现在，当我想到为什么这么多公司都在采用**AI**时，他们也期待同样的事情：更好、更快、更便宜等等。所以，我想请你反思一下，**敏捷**实际上是如何发展的？说到“**蛇油**”式的宣传。

<details>
<summary>Original English</summary>

**Host**: That that that kicked off some really interesting things in the indust industry because what what my interpretation was like well use this agile here's these four pretty simple easy to understand and easy to identify with things to build better software faster cheaper higher quality you name it. Now, when I think of why so many companies are adopting AI, they're kind of expecting the same thing, better, faster, cheaper, and so on. And so, I wanted to can you reflect on how agile actually went? Speaking of snake oil,

</details>

**Kent Beck**: 嗯，事实证明人们不想要更快、更便宜、更好的东西。

<details>
<summary>Original English</summary>

**Kent Beck**: well, it it turns out that people don't want faster, cheaper, better.

</details>

**Host**: 跟我说说更多。

<details>
<summary>Original English</summary>

**Host**: Tell me more.

</details>

**Kent Beck**: 在一个公司内部，激励机制与实际实现这些目标是如此不一致。所以作为**极客**，我们努力实现这些目标，说“嗯，它好40%，便宜12%，而且脂肪更少”。如果这与他们在组织内部的激励不一致，人们会因此惩罚你。是的。在理想的组织中，每个人都会关心同样的事情。但这并不是它运作的方式。

<details>
<summary>Original English</summary>

**Kent Beck**: Inside a company, the incentives are so misaligned with actually achieving that. And so so as as geeks trying to achieve that and say, "Well, it's 40% better and it's 12% cheaper and it's less fattening." Uh people will punish you for that if that doesn't in align with their incentives inside of organizations. Yeah. In the ideal organization, everybody would care about the same things. And that's just not the way it works.

</details>

**Kent Beck**: 但是。

<details>
<summary>Original English</summary>

**Kent Beck**: But I

</details>

**Kent Beck**: 所以我们还没有解决这个问题。所以如果**AI**到来并承诺同样的事情，我们将会看到完全相同的反应。

<details>
<summary>Original English</summary>

**Kent Beck**: so and and we haven't touched that problem. So if AI is coming along to promise the same things, we're going to see exactly the same reaction.

</details>

**Host**: 这正是我想要问的，回顾你所看到的**敏捷**，现在已经25年了，它的发展速度要慢得多。你现在在**AI**身上看到了哪些相似之处？你认为曲线会如何发展？还有，**敏捷**运动与**AI**有什么非常不同的地方？**敏捷**运动以非常缓慢的方式席卷了整个行业，而现在是**AI**。

<details>
<summary>Original English</summary>

**Host**: And and this is what I I wanted to ask like looking back from what you've seen for agile now 25 years and it played out at a lot lot slow slower pace. What similarities do you see right now