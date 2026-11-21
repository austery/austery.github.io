---
author: a16z
date: '2026-11-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HDRy6XmE2RQ
speaker: a16z
tags:
  - game-development
  - generative-ai
  - autonomous-agents
  - modding
  - simulation
title: AI重塑游戏产业：从GTA 6开发周期到反编译与Agent驱动的无尽游戏
summary: 对话探讨了AI对游戏开发周期的重塑与品类创新。从GTA 6的长周期出发，嘉宾分析了Astra等工具在原型制作、反编译老游戏及Mod创作中的突破，并讨论了Agent编排与动态机制如何催生新型无尽游戏。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Tim Sweeney
companies_orgs:
  - Epic Games
  - Xbox
  - Roblox
  - Anthropic
products_models:
  - Grand Theft Auto 6
  - Astra
  - Unreal Engine
  - Blender
  - Minecraft
  - Three.js
media_books: []
status: evergreen
---
### 游戏开发长周期与AI原型工具的突破

>> 《侠盗猎车手6》（Grand Theft Auto 6）下个月终于要发售了。那款游戏从2013、2014年左右就开始制作，差不多经历了12到13年的开发周期。
<details><summary>Original English</summary>
>> Grand Theft Auto 6 is finally coming out next month. That game has been in production since like 2013 2014. It's like a 12 13 year development cycle.
</details>

>> 太疯狂了。游戏长期以来一直是最复杂的制作物之一。但因为现在可以让AI协助承担部分专业知识的角色，你不再非得是个专业人士了。
<details><summary>Original English</summary>
>> Crazy games have long been one of the most complex products to create. But because you can have a uh help build a role of some of these specialized knowledge, you no longer need to be a professional.
</details>

>> 比如让智能体（Agent）去观察某个东西，并尝试从零开始重现一款游戏；也有将两款游戏或两种艺术风格进行杂糅和融合。依托模组（Mod），诞生过多款数十亿美元级别的游戏大作。例如《反恐精英》（Counter-Strike）最初就是《半条命》（Half-Life）的模组；《英雄联盟》（League of Legends）则启发自《DotA》（Defense of the Ancients），而DotA本身就是《魔兽争霸3》（Warcraft 3）的模组。
<details><summary>Original English</summary>
>> There is having an agent sort of look at something and try to recreate a game from scratch. There's also kind of the meshing and the merging of two games or two art styles. Multibillion dollar game franchises have been created using mods. Counter-strike, for example, that was a Halflife mod. League of Legends was inspired by Defense of the Ancients, Dota, which was itself a Warcraft 3 mod.
</details>

>> 所以，想象一下未来的“12年级巨作”会是什么样子。
<details><summary>Original English</summary>
>> So, imagine what the next 12-year game will look like.
</details>

>> AI现在让构建小众游戏（比如以前在经济上不可行的小众冷门题材）成为了可能。
<details><summary>Original English</summary>
>> AI is now making it possible to build sort of niche games like esoteric genres that previously would not have been economically viable.
</details>

>> 你们每个人多年来一直想做、而现在终于能做出来的游戏是什么？嗯……
<details><summary>Original English</summary>
>> What's a game that each one of you has been thinking about making for years and now you finally can? Um,
</details>

>> 看起来游戏行业正发生一场不可思议的转变，独立开发者和业余爱好者的实践也是如此。Epic的蒂姆·斯威尼（Tim Sweeney）公开发表了很多关于AI的非常有趣的言论。Xbox的CEO Asha也公开表示，他们正在深入思考Xbox上的软硬件协同。似乎正在发生时代潮流的转变。所以，
<details><summary>Original English</summary>
>> it seems like there's just been this incredible shift in in the gaming industry and also what we're seeing from from Zolo devs and just tinkerers. Tim Sweeney from Epic has come out and said a bunch of really interesting things about AI. The CEO of Xbox, Asha, has also come out and uh sort of said that they're thinking a lot about the hardware and software interplay on on Xbox. And it seems like, you know, there seems to be a tide shift. So, yeah,
</details>

>> 想聊聊这个。
<details><summary>Original English</summary>
>> want to talk about that.
</details>

>> 好，也许我先开个头。阿尼什（Anish），也很想听听你的想法，因为你业余时间一直在做一些游戏。
<details><summary>Original English</summary>
>> Yeah, maybe I'll start off and, you know, Anish would love to hear your your thoughts cuz you you've been building some games in your free time.
</details>

>> 是的，我确实在做。没错。
<details><summary>Original English</summary>
>> Yes, I have. Yes.
</details>

>> 我觉得大约一个月前，Astra带来了一次重大的技术突破。因为它非常非常擅长直接操作主流的游戏开发软件。Astra非常擅长使用Blender，它实际上可以直接在虚幻引擎（Unreal）和Unity里操作。而在前几代模型中，它们只会向用户解释说“你应该去Blender里做这个”或者“你应该在Unreal里做那个”。但Astra实际上可以替你操作软件。那是一个巨大的突破。因此，第一次让业余爱好者——比如以前从未做过游戏的人——可以使用Astra来起草游戏设计文档、生成概念原画、将概念原画导入Blender让其据此建立3D模型、完成动作绑定与装配，
<details><summary>Original English</summary>
>> Um, so I feel like the big there was there was a big technology unlock about a month ago with with Astra um because it was very very good at directly using um very popular game development software. And so Astro is very good at using Blender. it could actually like work directly within Unreal and Unity. Um, and in previous previous generations of models, they would just explain to the user like, oh, you should go and like do this in Blender or you should do this in Unreal. But Astro actually could like operate the software for you. And that was a huge unlock. And so for the for the first time you could have a hobbyist um someone who's never actually built any games before um use Astro to draft the game design document, generate some concept art, move that concept art into Blender, have them build 3D models from it, like animate it, rig it,
</details>

>> 然后转移到Unreal中，基本上再添加一些音乐和音效文件（顺便说一句，这些也可以生成），然后导出为可玩的游戏版本。你就这样用Astra一步搞定（one-shot）了一款游戏。另外非常宝贵的一点是，Astra还可以自我进行质量保证（QA）：它能截取游戏画面，并从自己的输出中学习，“哦，我需要修复这个bug”或“这里看起来不对劲”。这就是为什么人们在X上制作的最初原型实际上出奇地好。我认为那是一次巨大的技术突破。它带来了许多影响，我们已经开始在游戏行业中看到了。第一个影响是它极大地缩短了从想法到原型的时间。这也是Tim Sweeney在Twitter帖子里谈到的：AI使得制作以前在经济上不可行的小众游戏或冷门流派成为可能。因为缩短了制作游戏所需的时间，他现在可以迅速搭出一个奇奇怪怪的游戏想法的原型。
<details><summary>Original English</summary>
>> move it over to Unreal, and then basically uh add some music and sound files, which by the way can also be generated, and then you can export that as a playable, and then you literally have a game that you'd one-shot using Astra. And then the other thing that's been very valuable is that Astra can also um QA itself and so it can take screen caps of the game and then it can learn from its own output. Oh, I need to fix this bug or this doesn't look right and say um that's why the initial prototypes that people are building on X are actually like surprisingly good. And so I think that was a huge technology unlock. Um and I think that has a number of ramifications which we're starting to see in the games industry. And so the first the first effect is that it's just dramatically shortening the time between idea and prototype. And so that's something that Tim Sweeney talks about actually as um in some of his Twitter posts, which is that um AI is now making it possible to build sort of niche games or sort of like you know like esoteric genres that previously would not have been economically viable. Um, but because he's shortening the time it takes to make a game, he can actually now just spit up a prototype of a a strange or weird game idea. Y
</details>

>> 因为成本更低，耗时更短。
<details><summary>Original English</summary>
>> um because it it costs less money, it takes less time.
</details>

>> 我认为这对游戏行业影响巨大，因为我认为游戏领域的结构性挑战之一就是制作这些游戏耗时太长了，对吧？就像……
<details><summary>Original English</summary>
>> Um and I think that's actually huge for the games industry because I think one of the structural challenges in games is that it just takes a really long time to make these games, right? It's like
</details>

>> 我想你和我早些时候聊过这个，比如《侠盗猎车手6》终于下个月发售，但它从2013、2014年就开始制作，是长达12到13年的开发周期。
<details><summary>Original English</summary>
>> um I think you and I were talking about this earlier, but like Grand Theft Auto 6 is finally coming out next month and like that game has been in production since like 2013 2014 it's like a 12 13 year development cycle.
</details>

>> 太疯狂了。
<details><summary>Original English</summary>
>> Crazy.
</details>

>> 我相信它会是一款了不起的游戏，但按其他任何软件开发标准来看，花10多年去做一款HR软件或CRM系统[笑]，这简直不可思议，对吧？
<details><summary>Original English</summary>
>> And I'm sure it's going to be an amazing game, but like by any other software development standard, right? Like taking 10 plus years to make um you know HR software or CRM or [laughter] it's it's kind of it's kind of insane, right? M
</details>

>> 所以，缩短从想法到原型的时间——看看我们是否能把5到10年的开发周期缩短到2到5年。虽然仍需要一些时间，但我认为它能让游戏开发者承担更多风险，拥有更多尝试机会（at bats），进行更多实验，总体上增加被创造出来的游戏的丰富度和多样性，这非常令人兴奋。
<details><summary>Original English</summary>
>> and so um shortening the time from idea to prototype like let's see if we can get a 5 to 10 year dev cycle to I don't know like 2 to 5 years you know it's still going to take some time but I think it'll just enable the game developers to take more risk um have more at bats like take more experiments and and and just generally just increase the richness and diversity of games that are created which I think is really exciting.
</details>

### 代码生成与工具调用双轨演进及创新风险

>> 是的。补充几点，很有趣的是我们看到了两种路径的浮现。我其实觉得第一件真正适用于游戏的事情是Three.js操作能力的出现。大概是在Opus 4.7或者Opus 4.8，它具备了一种其实并非针对该场景设计的特性（至少Anthropic声称没有），那就是它非常擅长Three.js——
<details><summary>Original English</summary>
>> Yeah. Yeah. I mean to build on some of those comments you know it's interesting because we've seen two sort of approaches emerge. So I actually think the first thing that really was applicable to gaming was the emergence of 3JS manipulation and I think it was Opus 47 maybe it was Opus 48 but it just had this property actually which it was not designed to have in it at least anthropic said it did not um which is it was awesome with 3JS
</details>

>> 也就是浏览器端3D。很有意思，它的实现方式几乎是逐个元素地排布，那种细致入微、近乎狂躁的程度是人类做起来会抓狂的。所以写代码是生成游戏的一种路径。而正如你提到的，约翰（John），Astra真正擅长的是工具使用（tool use）——
<details><summary>Original English</summary>
>> which is in browser 3D and it's interesting because the way that it does it sort of it's laying things out almost on an element byelement basis like in a way that would be maddeningly manic meticulous for a human. Um, so coding is sort of one path to game generation. And it felt like what Astra did really well to your point, John, was tool use,
</details>

>> 它能极其高效地使用Blender以及云端的Blender。这是模型层面的两大宏观趋势，一个是自然涌现的，一个是程序设定的，它们正在汇聚，推动游戏开发的大幅加速。
<details><summary>Original English</summary>
>> you know, could use Blender and Blender in the cloud really, really effectively. So these are two like mega trends within models, one kind of emerging and one programmed that are converging to drive a lot of the um the acceleration in sort of game development.
</details>

>> 你说花12年去做一款HR软件挺搞笑的。但我认为正是因为耗时太长，游戏行业才有那么多令人扼腕的故事。
<details><summary>Original English</summary>
>> You know, the the thing it's funny you say like 12 years to make HR software. Like I think just the amount of time it takes is why there's so many sad stories in gaming.
</details>

>> 想想那些未曾面世的游戏故事吧。有多少游戏在6年周期的第3年或第5年被取消了？
<details><summary>Original English</summary>
>> Like think of all the game stories that are left untold, right? How many games were cancelled 3 years into a six-year cycle or 5 years into a sixear cycle, you know?
</details>

>> 市场已经变了，玩家的口味也变了。就像……
<details><summary>Original English</summary>
>> The market has moved on, player tastes have changed. Like
</details>

>> 完全是这样。你会经历这些财务周期，经历这些创意周期，三年前在创意上很有趣的想法现在感觉索然无味了。所以，为一件事埋头苦干13年并坚持到底，还要保证它很出色，这太难了。能成功简直是个奇迹。
<details><summary>Original English</summary>
>> totally you go through these financial cycles. You go through these creative cycles, you know, where the ideas that were creatively interesting 3 years ago now feel flat. So, it's just so hard to work on something for 13 years and see it all the way through and then have it be great. It's a miracle that it works at all.
</details>

>> 是的，确实如此。漫长开发周期的另一个方面——我觉得大家没怎么讨论，但对行业有非常真实的影响——就是它对创新的窒息作用。如果你是一家3A游戏工作室的制作人，你知道推出一款游戏需要10年时间和数亿美元，你在立项审批（greenlight）时就会非常保守，对吧？
<details><summary>Original English</summary>
>> Yeah. No, for sure. And the other aspect of um these long development cycles um which I feel like people don't talk about, but I I think has a very real impact in the industry is that the long dev cycles like have a suffocating impact on just innovation. Because if you're a producer at aaa game studio and you know it's going to take 10 years to ship a game and hundreds of millions of dollars, you're going to be very conservative in what you greenlight, right?
</details>

>> 有意思，确实。
<details><summary>Original English</summary>
>> Interesting. Right.
</details>

>> 比如你只会给续作立项，而不是新IP。我想《使命召唤》（Call of Duty）已经出到第20部了吧；而那是《侠盗猎车手6》，对吧？
<details><summary>Original English</summary>
>> It's like you're going to you're going to greenlight sequels or the new IP. I think we're on like the 20th Call of Duty installment that's Grand Theft Auto 6, right?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 它不是全新IP。
<details><summary>Original English</summary>
>> It's not a new IP.
</details>

>> 你会偏向已有确定需求的大众品类，对吧？这就是为什么我们看到那么多第一人称射击、第三人称射击，而不是实验性流派。
<details><summary>Original English</summary>
>> Um you're going to skew toward genres that have established demand, right? which is why we see so many first person shooters, third person shooters over some experimental genre.
</details>

>> 当你降低了发售游戏的门槛，耗时变少了，只需要5年而不是10年；花费不是数亿美元，而是数千万美元（依然很贵），
<details><summary>Original English</summary>
>> When you lower the bar for sort of um shipping a game, right, it's going to take less time. It's going to take 5 years instead of 10. Instead of hundreds of millions of dollars, it's going to take, you know, tens of millions. It's it's still going to be expensive.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我觉得这意味着大家可以承担更多的创意风险。完全同意。
<details><summary>Original English</summary>
>> I think it just means that people can take more creative risk. Totally.
</details>

>> 比如你可以真正推出新IP，可以把赌注押在从未发布过作品的开发者身上，给他们立项并提供预算去制作。我认为这对于游戏行业来说是一个非常令人兴奋的叙事，而且实际上将释放大量的结构性创新，
<details><summary>Original English</summary>
>> Like you can actually ship a new IP. you can take a bet on some some game developers that have never actually shipped anything before and you can greenlight them and get them a budget to make something. And I I think that's I think that's a really exciting story for for the game industry and and actually is going to unlock a lot of structural innovation,
</details>

>> 对吧？另一种探索这种新能力的方法是扩大野心。想象一下下一款12年打磨的游戏会是什么样——比如GTA 7。你今天提到过GTA 6里的城市有多么错综复杂。
<details><summary>Original English</summary>
>> right? And then the other actually way to explore this new capability though is to increase ambition. So imagine what the next 12year-old 12-year-old game will look like GTA 7. You know, you were talking today about how intricate the city is in GTA 6.
</details>

>> 是的。他们设计了专门的定制广播电台，因为他们当时觉得：“反正我们还有一年时间，这支团队现在闲着，不如录一堆电台节目之类的。”但是，
<details><summary>Original English</summary>
>> Yeah. Yeah. They have custom radio stations that they designed because they pro they were just like, "Well, we have a year and, you know, this team isn't doing anything. Let's just record, you know, a bunch of radio stations and stuff like that." But
</details>

>> 这太不可思议了，对吧？但你可以想象，如果他们用现在的工具再花10年，别说一座城市，甚至别说一个世界，你完全能以那种细节水准构建一个宇宙。为什么不呢？
<details><summary>Original English</summary>
>> it's incredible, right? But you imagine if they then spent 10 years with the current tools, forget about a city or even a world. You could build a universe with that level of detail. Why not?
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 游戏创作平民化与最后20%的人类审美壁垒

>> 没错，完全正确。扩展游戏的范围和野心，承担更多创意风险。我认为AI真的可以在游戏领域创造一个前所未有的“丰裕时代”，因为我们可以制作前所未见的游戏，承担更多创意风险。另一个我们还没谈到但同样重要的因素是：AI也在改变“谁能制作游戏”——
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. No, I I think that's absolutely right. It's like um uh just like expand the scope of games, the ambition of games, take more creative risk. I think um I think AI can can literally create an abundance error in games, you know, that that wasn't previously possible cuz we can make games that have never been seen before. You can take more creative risk. Um and and then another another element that we haven't talked about that I think is equally important is that AI is also changing who can make games
</details>

>> 因为长久以来，游戏一直是最复杂的产品之一。这是一门真正的跨学科手艺：你需要懂代码、懂美术、懂游戏设计、懂音乐和音效。
<details><summary>Original English</summary>
>> because um games have long been one of the most complex products to create right it's a true multi-disiplinary craft like you need to know how to code you need to know art you need to know game design you need to know like music and sound
</details>

>> 所以，
<details><summary>Original English</summary>
>> um and so the
</details>

>> 制作一款好游戏的执行门槛极高，远甚于拍一张好照片或拍一段视频。虽然那些也很难，但我认为这完全不是一个层级的差异。但是，因为你可以借助AI填补某些你不具备的专业知识，
<details><summary>Original English</summary>
>> execution for for making a great game is just very high like much more so and just snapping a great photo or like making a video. Um, which are hard, but I think it's just an just a level of difference there. Um, but because you can have a uh help filled the role of some of these specialized knowledge which you may not have,
</details>

>> 我觉得你不再非得是个专业人士，不再需要配备一支在各个细分角色上都极度专业的人员团队，而是可以让AI来填补你的技能和知识空白。我认为这正在以前所未有的方式实现游戏制作的平民化。只要有一个想法和一些参考图，任何人都可以与Astra合作，逐步迭代出一个游戏原型。
<details><summary>Original English</summary>
>> I think you no longer need to be a professional like you no longer need to have a full team of people that are all like, you know, specialized in different roles and instead you can have AI kind of plug some of the gaps in your skills and knowledge. And I think that's democratizing game creation in a way that wasn't previously possible. Um that you can actually have someone with just an idea and some reference art work with Astra to sort of like iterate their way to a game prototype.
</details>

>> 当然，这只是个原型，还不是完全成熟的可玩游戏。很多人其实不会最终完成它，他们可能做完第一关的场景就放弃了。但我认为总有一部分人会坚持到底，并发现自己热爱游戏开发，甚至想把它变成一份职业。我认为我们会看到游戏创作者数量的爆发式增长，这真的非常令人振奋。
<details><summary>Original English</summary>
>> Like of course it's it's a prototype. It's not a fully playable game. Um and then many people won't actually finish it. Like they'll they'll just make the first level of the scene and then they'll drop out. But I think like some percentage of them will make it through um and then decide that they love game development. They actually want to turn this into a a job itself. And I think we'll see an explosion in a number of game creators. And and I think that's really exciting.
</details>

>> 你们肯定经常接触那些正在为这些准AI游戏开发者打造工具的创始人，或者他们自己就在尝试开发纯AI驱动的游戏。在我看来，最困难的事情恰恰是游戏平衡性，以及如何把游戏做得真正有趣、引人入胜。这似乎是一门艺术，需要人类的直觉、专长，以及一种完全不同的创造力。关于AI在这方面的能力边界，你们看到了什么？
<details><summary>Original English</summary>
>> You guys must talk to founders who are either creating tools for these kind of wouldbe AI enabled game developers or they're trying to like work on AI developed games themselves. And like the thing that would seem the hardest thing to me would be just game balance and making something that's like actually fun and engaging. There seems to be this kind of it's it's an art and it's a real it's it's something that does I think require human intuition and human knowhow and um kind of just like a a different kind of creativity. Uh what what are you seeing there in terms of what AI can do?
</details>

>> 我觉得你一语中的。我认为AI模型不会取代人类的品味和创意判断，这依然至关重要。游戏行业有一句名言：一款游戏最后的20%占据了80%的劳动量。所有的魔力、让游戏变得有趣的要素，都在那里发生。因为前……
<details><summary>Original English</summary>
>> So I think you hit it spot on. I think um and I think the AI model is not going to replace human taste and creative judgment. I think that is still really really critical. Um and then there's a there's a saying in the games industry that the last 20% of the game is 80% of the work. Um and that's where all the magic comes together make something fun because the first
</details>

>> 前80%可以说只是拼凑出一个能运行的游戏。就像“好吧，太棒了”，
<details><summary>Original English</summary>
>> the first 80% you could say it's just putting together a game that works. It's like oh okay great like
</details>

>> 游戏能启动，里面有个角色，可以射击，有怪兽可打。我觉得那是前80%。而最后的20%太关键了，比如——
<details><summary>Original English</summary>
>> like you can start the game you can there's a character in it. It can shoot things. There's like monsters to shoot. Like I think that's the first 80%. The last 20% is so critical. It's like
</details>

>> 整个世界带给你怎样的感觉？回到你刚才提到的GTA 6里的定制电台，
<details><summary>Original English</summary>
>> how does the world feel, right? Going back to your point in like a custom radio stations in Grand Theft Auto 6, like
</details>

>> 当你开枪时，枪声听起来是怎样的？霰弹枪的声音应该和手枪不同；用激光枪时应该有相应的后坐力等等。所有这些细节造就了神奇的体验。而在可预见的未来，我认为这仍将是人类的专属领地。一件东西给人的感觉如何？玩家想要什么？这把枪手感该怎样？在这些场景中，人类的品味和判断力依然至关重要。
<details><summary>Original English</summary>
>> when you fire a gun, like what is the sound of the gun? Like the shotgun should sound different from the pistol. And then when you use a laser gun, there should be a recoil for that and so on. Like all the little details are what makes a magical experience. And I think that is going to be the province of humans for the foreseeable future, right? It's like how does something feel? What do players want? Like how should this gun feel? Um and so uh I I think that's still going to be critical for for human taste and judgment in in those situations.
</details>

>> 是的。到底是什么让我愿意花上千个小时去玩GTA，或者玩《博德之门3》（Baldur's Gate 3）这种不可思议的游戏？我觉得确实是这种细节层次，但同时也有一种世界的因果厚重感和深度。也许大语言模型（LLM）实际上能——
<details><summary>Original English</summary>
>> Yeah. Yeah. and and like like what is going to make me want to spend a thousand hours playing, you know, Grand Theft Auto or playing, you know, Balders Skate 3, these like incredible games that like like I I think it really is just this level a of detail, but also like I think a sense of like consequence and depth to a world and maybe maybe that is something that LLMs can actually like
</details>

>> 帮助扩展它。
<details><summary>Original English</summary>
>> help extend.
</details>

>> 没错，正是如此。
<details><summary>Original English</summary>
>> Yeah. Yeah. Exactly.
</details>

>> 你怎么看？
<details><summary>Original English</summary>
>> What do you think? Yeah.
</details>

### “创作即消费”：禅意园艺与90年代街区实验

>> 我同意。我不觉得做出真正好玩的游戏变得轻而易举了，因为这真的很难，它是多种因素的交汇——有些是刻意设计的，有些是机缘巧合，有些甚至源于文化或社交属性。做出好玩的游戏需要太多东西。不过我认为在这个新时代，有时“创作本身就是消费”。
<details><summary>Original English</summary>
>> Well, so like I I agree. I don't know that it makes it trivial to create a really fun game because I think that's really hard and it's an intersection of many things. Some designed, some serendipitous, some even cultural, some social. So there's many things that go into making a fun game. I do think though in this new era sometimes creation is consumption.
</details>

>> 未来绝大多数游戏可能从始至终只有一个人玩，那就是创作者自己。[清喉咙] 这其实完全没问题。因为编写代码或制作游戏，一种是为了产出最终成果，另一种则是把这些过程本身当成一种活动。
<details><summary>Original English</summary>
>> Like the vast majority [clears throat] of games are ever going to be played by one person that is the creator in the future. And that's okay actually because I think that there's you know programming or creating games for the output for the artifact and then there's doing those things as an activity
</details>

>> 制作一款游戏、投入其中去创作其实有一种内心的平静，尤其因为它包含艺术元素。
<details><summary>Original English</summary>
>> and it's actually very tranquil to make a game and to work on a game and create especially because it has the art element
</details>

>> 看着素材鲜活起来，看到角色说出你并没有特意编写的话。我真的觉得游戏制作有一种类似“日式禅意园艺”的特质，它会变得越来越流行。这是一个非常棒的观点，即我们看到有时“创作即游玩”。
<details><summary>Original English</summary>
>> seeing the assets come to life you know seeing the characters say things you didn't program them to say like I I really do think there's a sort of zen gardening aspect to game creation which will become increasingly popular. I think that's I think that's such a great point which is we're seeing that um you know creation is play sometimes right
</details>

>> 比如《我的世界》（Minecraft），史上最成功、生命力最持久的游戏之一。甚至在电子游戏出现之前的乐高积木也是如此，孩子们纯粹为了好玩而创造东西，并互相分享。
<details><summary>Original English</summary>
>> like we've seen that for Minecraft which is one of the the most successful and longest running games of all time like we've seen it even prior to video games and things like Legos where people the kids are just creating things for fun and sharing it with each other
</details>

>> 今天的AI无疑也是这样。创造某种东西、让其鲜活起来的举动本身就充满乐趣。AI极大地增强了人们的创造力，你不需要精通代码、美术和3D的所有知识，
<details><summary>Original English</summary>
>> but I think that is definitely the case with with AI today as well which is just the act of creating something bringing something to life is itself fun and then AI is just turbocharging what people can create and so you don't need to know everything about code and art and 3D
</details>

>> 就能做出让自己自豪的作品。是的。
<details><summary>Original English</summary>
>> that to make something that you can be proud of. Yes.
</details>

>> 并且在制作过程中享受乐趣。
<details><summary>Original English</summary>
>> And and have fun making
</details>

>> 百分之百。
<details><summary>Original English</summary>
>> 100%.
</details>

>> 阿尼什，你做过一个Habbo旅馆风格的唱片店。
<details><summary>Original English</summary>
>> Anish, you you built this Hobo Hotel themed kind of record shop.
</details>

>> 那个过程是怎样的？
<details><summary>Original English</summary>
>> What was what was that process like?
</details>

>> 哦，它最初源于我和一位DJ朋友的聊天。他说：“现在的线上唱片店全都千篇一律，就是个歌曲列表。”我们聊起90年代在多伦多逛唱片店的经历——去唱片店其实就像去理发店，店里挤满了人，你免不了要跟五个人打招呼聊天；后面有人在极大声地放歌，店里卖着混音带，宣传着狂欢派对。整个地方就是一个真正的社交场域。
<details><summary>Original English</summary>
>> Oh, well, it actually started with a conversation with a friend who's a DJ and he was saying, "Oh, all the online record stores look the same. It's just a list of songs." And we were talking about how when we used to go record shopping in Toronto in the '9s, going to the record shop was like going to the barber shop actually because you go there, it's filled with people. You can't not have five conversations. There's someone at the back who's playing tracks really loud. There's mixtapz for sale. There's raves being promoted. It just the whole thing was like it was a real social environment. Yeah.
</details>

>> 于是他说：“为什么网上的唱片店不能做成那样？”我想：“这太酷了，让我来试着做出来。”
<details><summary>Original English</summary>
>> So he said, "Hey, why can't shopping, record shopping online be like that?" So I thought, "Hey, that's cool. Let me try to actually create that." Yeah.
</details>

>> 那是用Opus 5.5做的，我试了一下。我只给了它几个Habbo旅馆风格的参考素材组件，它——
<details><summary>Original English</summary>
>> So, this was um with Opus 55. I gave it a shot. I gave it just a couple Habbo Hotel reference art components and it just
</details>

>> 简直超出了我的预期。它不仅生成了房间，还不知怎么抓取了各种各样的90年代音乐。
<details><summary>Original English</summary>
>> it super exceeded my expectations cuz not only didn't it generate the room, it also somehow grabbed all kinds of '90s music.
</details>

>> 有R&B、Dancehall、嘻哈、灵魂乐专区。你可以挑曲目，翻看唱片然后放上去，后台的DJ就会拿起那张黑胶唱片放进唱机。
<details><summary>Original English</summary>
>> So, it had a creative R&B, a creative dance hall, a creative hip-hop, a creative like soul. You could pick the track, you could look through the tracks, put them on, then the DJ at the back would grab the record, put it on. Mhm.
</details>

>> 还有人在小舞池上跳舞。细节极其丰富。这完全是一次灵感爆发。
<details><summary>Original English</summary>
>> People were dancing on a little. It was very intricate. So it was a total inspiration.
</details>

>> 从那之后我说：“如果我把这个扩展成1990年代多伦多的皇后街（Queen Street）会怎样？”
<details><summary>Original English</summary>
>> And then from there I actually said, "Hey, what if I extended this and turned this into Queen Street in Toronto in the 1990s?"
</details>

>> 好的。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 于是我把它做成了一条完整的街道。最后的点睛之笔，我觉得是最具科幻感、以前绝无可能实现的是：我让街道上的每家其他店铺，都能让另一位玩家仅通过Prompt就搭建出来。但有趣的是，他们不仅能定制外观艺术，还能定制功能机制。我儿子跑进去建了一个宠物领养中心，你真的可以领养宠物，它们还会跟着你到处走。
<details><summary>Original English</summary>
>> So I turned it into a whole street. And the last touch, which actually I think was the the most sort of science fiction thing that would never have been possible, was I made it so that every one of the other storefronts were something that another player could come and build out just through prompting. But the interesting thing is that they could not just customize the art, they could customize the capabilities. So my son went in there and created this pet adoption center. Um, except you could actually adopt the pets and they'll follow you around.
</details>

>> 当然，我原本根本没设计这种动物跟随功能，但编程Agent修改了我的游戏引擎，创造了这套机制。过去，程序化关卡生成（procedural level generation）就已经非常鼓舞人心了，
<details><summary>Original English</summary>
>> Now, of course, I didn't design this like animal following capability in, but the coding agent updated my game engine to create that mechanic. So now, you know, in the past, it was really inspirational to have procedural level generation,
</details>

>> 但那只是动态内容。而现在我们谈论的是动态能力——全新的游戏机制，对吧？
<details><summary>Original English</summary>
>> but that's just dynamic content. Now we're talking about like dynamic abilities. whole different mechanics, right?
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 你儿子玩过Roblox里的《Adopt Me》吗？因为那个……
<details><summary>Original English</summary>
>> And did um uh has your son played uh Adopt Me from Roblox? Cuz that's
</details>

>> 没有，类似于那个吗？
<details><summary>Original English</summary>
>> No, something like that.
</details>

>> 很像吗？
<details><summary>Original English</summary>
>> Is it similar?
</details>

>> 那是Roblox上最火的游戏之一。
<details><summary>Original English</summary>
>> It's one of the most popular Roblox games.
</details>

>> 哦，也许他玩过，灵感就是这么来的！我还心想：“这也太有创意了。”[笑]
<details><summary>Original English</summary>
>> Oh, maybe he has and that's how he came up with it. I'm like, this is so creative. [laughter]
</details>

### Mod文化演进：从自制模组到反编译经典重构

>> 确实。这真是一个很好的例子。我儿子最近也开始用AI做游戏了。起因是他想玩一款叫《对马岛之魂》（Ghost of Tsushima）的游戏。
<details><summary>Original English</summary>
>> For sure. For sure. I think that's a great example. So So my son has also recently got into game development using using AI and um it actually started because he wanted to play a game. It's called uh Ghost of Sushima. Mhm.
</details>

>> 那是一款非常出色的游戏，但在封建日本时代扮演武士，你可以想象，里面非常血腥暴力。
<details><summary>Original English</summary>
>> It's a fantastic game, but you basically play a samurai in Beetle Japan. As you can imagine, it's like very bloody and kind of violent.
</details>

>> 所以我们跟他说：“不行，你才8岁，不能玩这种血腥的武士游戏。”[笑]
<details><summary>Original English</summary>
>> And so he told him, "Actually, no, you're eight. You're not playing this like bloody samurai game." [laughter]
</details>

>> 但他真的很想玩。于是他开始跟ChatGPT聊这款游戏，向它提问。不知怎么他就发现自己可以做一个《对马岛之魂》的Minecraft模组。
<details><summary>Original English</summary>
>> But he really wanted to play the game. And so he started talking to, you know, the chat GPT and asking him about it and then it's and then and then somehow he discovered that he he could build a Minecraft mod of Ghost of Sushima.
</details>

>> 不会吧。
<details><summary>Original English</summary>
>> No way.
</details>

>> 接着他利用GPT解构了那款游戏，因为网上有所有的维基百科详细拆解其机制和Boss战如何运作。接着Codex帮他编写了一个Minecraft模组并成功安装。那就是Minecraft模组版的《对马岛之魂》，
<details><summary>Original English</summary>
>> And then he used GPT to basically deconstruct the game because there were all these like wikis online to break down how the mechanics work, how the boss battles work. Um, and then so uh yeah, so essentially CEX helped him build a Minecraft mod which he installed and then it's Ghost of Sushima except as a Minecraft mod
</details>

>> 而且真的能玩。
<details><summary>Original English</summary>
>> and it works.
</details>

>> 运行得非常好。他一直在跟朋友们分享。
<details><summary>Original English</summary>
>> It works. It's super well. He's been sharing it with his friends and
</details>

>> 哇。
<details><summary>Original English</summary>
>> wow
</details>

>> 现在他再也不找我们买新游戏了。他的态度就是：“我想玩这款游戏，那我就把它做成Minecraft模组。”这带来了——
<details><summary>Original English</summary>
>> now at this point he doesn't ask us to buy new games anymore. He's just like I I want to play this game. I'm going to make it as a Minecraft mod. I think that's
</details>

>> 很多启发。这让我非常喜欢的一点在于，它说明了当我们思考游戏如何变得更好时，逼真度（realism）并不是唯一、甚至不一定是最有趣的提升维度。仅仅是能够从两个既有概念中创造出一个原本绝不可能存在的新概念，
<details><summary>Original English</summary>
>> a lot of inspiration. Well, what I also love about that is that it says, you know, it illustrates the fact that as we think about how games get better, realism is not the only or even necessarily the most interesting axis for improvement, right? Just the fact that you can create a concept from two existing concepts. We were talking about this that never would have existed. That's right.
</details>

>> 就非同寻常。
<details><summary>Original English</summary>
>> Is extraordinary.
</details>

>> 没错。我认为这正好可以过渡到反编译（decompilation）这个话题，这感觉确实是一股新趋势，而且反编译似乎有不同的分支。一种是——
<details><summary>Original English</summary>
>> That's right. I think this is actually a good a good transition to talk about decompilation and and that just really feels like a a new trend. And it seems like they're kind of they're different strains of decompilation. There is kind of
</details>

>> 让Agent去——
<details><summary>Original English</summary>
>> having having an agent
</details>

>> 观察某个作品，尝试从零重构一款游戏；另一种是两款游戏或两种艺术风格的杂糅与融合。我很想理清目前正在发生的这些不同方向。
<details><summary>Original English</summary>
>> sort of look at something and and try to recreate a game from scratch. There's also kind of the meshing and the merging of two games or two art styles. Um, and yeah, I just I would love to kind of disentangle all of these different things that are going on right now.
</details>

>> 好的。在AI的强力推动下，目前有两个趋势正在加速。首先，长期以来游戏行业一直受到模组（modding）的驱动。模组的逻辑就是拿一款你深爱的游戏，为它构建一个附加扩展包，以某种方式改变玩法。[清喉咙] 随后它演变出自己的独立游戏，甚至形成自己的品类。历史上游戏界最庞大的一些作品都源自模组。例如著名的电竞巨作《反恐精英》原本是《半条命》的模组；史上最成功的MOBA游戏之一《英雄联盟》受启发于《魔兽争霸3》的模组《DotA》；而我最喜欢的《堡垒之夜》（Fortnite）和《PUBG》，也是启发自《武装突袭》（Arma）的PlayerUnknown大逃杀模组。通过模组诞生了数十亿美元的游戏IP。这就是世界级顶尖游戏的诞生历史。如今，AI让游戏Mod的制作变得极其简单，完全就像我儿子做的那样：普通玩家、某个IP或游戏的爱好者，可以直接让Astra指向它并说：“给我做个《对马岛之魂》，但加上这个元素——比如加上体素建造，或者加上《动物森友会》的好感度系统。”然后你就可以把它做出来，看看好不好玩。如果好玩，其他人就会开始玩，它自身就会演变成一个全新流派并迅速爆火。回到创作循环：让人对着一张白纸凭空创造新东西是很难的。
<details><summary>Original English</summary>
>> Yeah. So, I hope that there's two trends that are happening that are getting turbocharged by AI. So, the first is that, you know, the games industry has long been driven by modding and and modding is the concept of like you take a game that you already love and then you build like an add-on extension to it that changes the gameplay somehow. Um, [clears throat] and then it becomes its own game. It's it becomes its own genre. And historically, some of the biggest games in the in the games industry have come from mods. And so, um, Counterstrike, for example, which a really big esports, that was a Halflife mod. Um, League of Legends, um, one of the most successful MOBAs of all time, uh, was inspired by Defense of the Ancients, Dota, which was itself a, um, a Warcraft 3 mod. And then um my favorite one like Fortnite and and PUBG um were itself inspired by um a Player Unknown Battle Royale mod of Arma. And so multi-billion dollar game franchises have been created using mods. And so this is just this is the history of somehow some of the the best and and biggest games in the world have been created. And AI is making it really really easy to mod games right now because exactly like the way my son did. Um, an ordinary player, someone who loves an IP or a game can basically point Astra to it and say, "Hey, like make me ghost of Sushima except add this, right? Like add box crafting. Add the relationship system from Animal Crossing." And then you can actually just make it and then see if it's fun. And like if it is fun then other people start playing it and it becomes like a genre in itself and and it kind of blows up in a big way. So um and you know and some part of this is um going back to like the creation loop. It's hard for someone to create something new using a blank canvas.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 如果你只是把一个纯文本提示框推到人面前说“给我做款游戏”，你根本不知道从何下手。所以，在别人已经做好的既有游戏框架内操作，然后说“把这个加进去，把那个混搭进来”，这种方式极其强大，因为它给了你一个起点和混搭的基础。
<details><summary>Original English</summary>
>> So if you just put a text like a text prompt in front of someone and say hey like make me a game like you wouldn't know where to start right. And so that's why working within the framework of an existing game that someone else has made and then just say, "Hey, like add this thing, remix it with this other thing." I I think it becomes very powerful cuz it gives you a place to start and a place to remix from.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这很有意思。你提到了模组。我看到的另外两个领域是：其一是反编译，从而获取源代码和资产。
<details><summary>Original English</summary>
>> Yeah. It's it's interesting. So you mentioned modding. I think the two other areas that I've seen, you know, one are sort of decompiling such that you have the source code and the assets.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yep.
</details>

>> 这在备受喜爱但年代久远的老游戏上显得尤为有趣。比如像《星球大战：旧共和国武士》（Knights of the Old Republic），BioWare早就关闭了，他们绝不可能再去开发另一部作品。你能去扩展它或分叉（fork）它，这太酷了。第三个可能是我见过的最具未来感的——
<details><summary>Original English</summary>
>> And I think this gets really interesting for beloved but old games. You know, you take games like Knights of the Old Republic for example, which of course Boware is out of business. And you know, Boware is never going to make another Knights of the Old Republic game. And you think about extending it or forking it. Like that's really cool. And then the the third maybe most futuristic one I've seen. And
</details>

>> X上有个叫Blendy（BLNDI）的人做了很多令人惊叹的尝试，他把两款既有游戏的资产提取出来，融合成第三款游戏，
<details><summary>Original English</summary>
>> there's this guy Blendy who's been doing a lot of these amazing things on X BL NDI. um where he'll take the assets from two existing games and then combine them into a third game,
</details>

>> 这概念完全天马行空，但确实能跑通，有些游戏还非常好玩。在怀旧老游戏方面，我认为促使Xbox Labs发布公告（Asha谈到希望支持AI及新开发前沿）的导火索，正是社区里涌现出了大量项目：人们把2001年初代Xbox的《光环》（Halo）经典作品——
<details><summary>Original English</summary>
>> you know, which is just a totally outer space concept, but it works. And some of the games are really fun. Yeah. I was going to say on the um on the on the uh the retro games front, um I think what sparked the uh the Xbox Labs announcement when Asha talked about um wanting to support you know AI and sort of like new new frontiers of of development specifically that um there was just so many community projects popping up that were taking Halo like the original I think it was like the 2001 like Xbox game
</details>

>> 经典之作。
<details><summary>Original English</summary>
>> classic
</details>

>> 进行反编译，并重新编译到现代平台上。我听说的就有4个社区项目成功把《光环》做成了基于WebGPU的网页端可玩游戏，直接在浏览器里玩《光环》。这太不可思议了。这又回到了你之前提到的Three.js，网页端3D从未像现在这样强大和唾手可得。我想Xbox很可能看到了这些，他们会想：“以前我们得有专门的整个团队，负责把Windows游戏移植到iOS生态，
<details><summary>Original English</summary>
>> and then they were decompiling and recompiling it for like modern like modern sort uh platforms. And so, um I think there were four community projects that I heard of that made Halo a playable web GPU game and to just basically play Halo in in the web now, right? And um it's it's really incredible that and it's going back to what you were saying earlier about 3JS, right? Like I think 3D on on on the web is never been like more powerful or more accessible. And so, um, I think Xbox has likely seen things like this happen and they're saying, "Hey, like we used to have whole teams that would just take a Windows game and, you know, port it over to the iOS ecosystem."
</details>

>> 或者拿停运的老游戏尝试做高清复刻。”但现在AI可以在这些工作上提供巨大帮助，你实际上是把成熟的IP推向了全新的受众——比如从未有机会玩过《旧共和国武士》的年轻一代。但现在他们能玩到了。
<details><summary>Original English</summary>
>> Um, or take old games that are defunct and then sort of like try to remaster it. But now AI can help a lot with those efforts and you're basically taking an established IP and you're exposing it to a new audience like kids today that have never that have grown up and they've never actually had a chance to play Nights of the Old Republic. Yeah. But now they can.
</details>

>> 没错，而且可能是在他们常用的主机、PC或其它设备上。
<details><summary>Original English</summary>
>> That's right. That's right. And potentially on a console or on a PC or a device that's relevant to them.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yep.
</details>

### 小众品类复兴与Agent编排的界面革新

>> 我觉得这真的太酷了。还有一些历史制作成本极高、或者算不过来投资回报率（ROI）的游戏类型。比如大家都很喜欢即时战略（RTS）游戏。
<details><summary>Original English</summary>
>> Yeah. I think it's really really cool. I also think that there's genres of games that have really high production cost or have historically had, you know, where you simply don't get the ROI. Like, you know, people love RTS games.
</details>

>> 大家都曾为RTS痴迷过。曾有无数尝试想在iPad上做出优秀的RTS，但我们[清喉咙]从未真正得到过一款好的。而现在，我认为我们会看到RTS这类流派的全面复兴。
<details><summary>Original English</summary>
>> Everybody has been obsessed with RTS. There's been so many efforts to make a great iPad RTS. And like, we've never really really [clears throat] gotten one. And, you know, now I think we're going to see this complete renaissance of genres like RTS.
</details>

>> 确实。我想Tim Sweeney也谈到了这一点。这也是我自己非常兴奋的。我特别喜欢一个非常小众的流派——职业模拟器（job simulators）。[笑] 这是一个很奇特的概念，你基本上是在模拟某个具体职业的日常生活。它通常不是什么光鲜亮丽的工作，比如你扮演的不是总统。[笑] 我最近玩的一个是电车驾驶员模拟器。
<details><summary>Original English</summary>
>> Such a It's what I'm Yeah, I think Tim Sweeney talked about this as well. That's what I'm personally really excited about. I I love this really niche genre of games called job simulators. [laughter] And uh it's such a strange concept. It's like you basically play a day in the life of a particular job. It's it's typically not a glamorous job like you're not like the president or something. [laughter] Um the one that I the one that I played most recently is um uh this train conductor simulator.
</details>

>> 天哪，太绝了。你可以扮演世界各个城市的地铁和火车列车长。我体验过当东京JR线的地铁列车长。正如听起来那样，一点也不光鲜：你按时上班，有严格的时刻表，必须驾驶列车，在沿途每一站精准停靠并接送乘客。你必须做到分秒不差，如果你停晚了一点，最后一节车厢没进站导致有人没赶上车，你的薪水就会被扣减。这非常小众，我想不出有很多人想当列车长。
<details><summary>Original English</summary>
>> Oh my gosh. Amazing. where you can basically be a conductor of um subways and trains in various cities around the world. And so, um I've been a like a JR, like a Tokyo subway conductor. It's exactly as it sounds. It's not glamorous at all. You show up for work, you have a timet to make. You got to drive this train and you got to stop at every stop along the way and pick up passengers. And you got to do it perfectly where if you're like late on like, you know, stopping like the last like the last car doesn't make it in so not everyone can make it on the train and you get your your paycheck is docked like for that. And so it's like such a it's a niche genre, right? Like I can't imagine that many people want to be train conductors.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但如果现在能做出这类游戏，
<details><summary>Original English</summary>
>> But if they are now like
</details>

>> 像我这样真正热爱它的人，
<details><summary>Original English</summary>
>> you can make games like this, right? And people like me who really love it
</details>

>> 会愿意花大钱去玩。
<details><summary>Original English</summary>
>> Yeah. We'll pay we'll pay a lot of money to to play these games, right? And so
</details>

>> 它好玩吗？
<details><summary>Original English</summary>
>> is it fun?
</details>

>> 我觉得特别好玩。[笑]
<details><summary>Original English</summary>
>> I I find it really fun. [laughter]
</details>

>> 有意思的是，如果你翻看过去的计算机杂志，看顶级软件排行榜，第一名通常是VisiCalc，第二名往往是微软模拟飞行（Microsoft Flight Simulator）这类早期飞行模拟游戏。我觉得模拟类游戏对玩家一直有着巨大的吸引力，大家就是喜欢模拟。
<details><summary>Original English</summary>
>> You know, it's funny if you if you look at like old computing magazines and you look at like the rankings of of top software, number one is usually like Visical and number two is like flight like Microsoft Flight Simulator like early flight sim games and like like I actually think like simulator as a genre just really has a hold on people. People People love Sims.
</details>

>> 没错。
<details><summary>Original English</summary>
>> That's right.
</details>

>> 它是一种常青品类。
<details><summary>Original English</summary>
>> It's Yeah, it's just an evergreen kind of kind of game.
</details>

>> 也许某种特定的职业能引起不同人的共鸣，但大家以前可能根本没机会发现，因为模拟类游戏盘子不够大。
<details><summary>Original English</summary>
>> Maybe there's like a particular type of job that resonates for various people, but maybe you never had a chance to discover it because the simulator genre just wasn't that big.
</details>

>> 确实。
<details><summary>Original English</summary>
>> That's right.
</details>

>> 但现在你可以角色扮演世界上你能想象到的几乎任何工作的一天，这难道不是很酷吗？
<details><summary>Original English</summary>
>> But now you can act you can you can roleplay a day in the life of almost any job in the world that you that you can envision, right? Like wouldn't that be really cool? feces.
</details>

>> 你们玩过《捣蛋鹅》（Untitled Goose Game）吗？
<details><summary>Original English</summary>
>> Did you guys ever play Untitled Goose Game?
</details>

>> 我知道这款游戏！
<details><summary>Original English</summary>
>> Oh, I I I know about this game. I know about this game. Yeah. Yeah. Yeah.
</details>

>> 它就是个鹅模拟器。
<details><summary>Original English</summary>
>> It's a goose simulation.
</details>

>> 没错，你假装自己是一只鹅到处转悠。
<details><summary>Original English</summary>
>> That's right. You pretend to be a goose and you go around.
</details>

>> 所以也许我也挺喜欢模拟类的。一只淘气的鹅。
<details><summary>Original English</summary>
>> So, maybe I am into the sim genre, you know. Yeah. Mischievous goose.
</details>

>> 它在疫情期间非常火。
<details><summary>Original English</summary>
>> It was It was really big during the
</details>

>> 没错，扮成一只鹅，我都不知道这说明了我什么心理。[笑]
<details><summary>Original English</summary>
>> That's right. Goose. I don't know what that says about me. [laughter]
</details>

>> 制造混乱。回到刚才关于RTS的讨论，我看到的一件事是：有些智能体编排方案长得很像经典RTS，比如给Agent编排套上了一层《帝国时代》（Age of Empires）的皮肤。
<details><summary>Original English</summary>
>> Chaos. Actually, going going back and kind of like merging the conversation about RTS games, like one thing that I've seen are kind of like agent orchestration schemes that look like classic RT like there's the Age of Empire skin over your like agent orchestration.
</details>

>> 是的，还有Minecraft风格的，各种建筑对应不同的代码模块。
<details><summary>Original English</summary>
>> Yes. Yes. There's a Minecraft one too. All the different structures or different quad code.
</details>

>> 没错。你们怎么看这些？这只是一种玩具式的渲染吗？或者只是管理Agent的感觉确实像玩游戏的一种自然延伸？又或者这是一种全新模拟器品类的开端？我觉得很有可能。比如在Credit Karma、Google或其他任何公司担任业务线总经理，本身就是一种模拟：你与各个团队协作，你的控制权有限，掌握的信息不完整、不完善，还要面对市场力量。
<details><summary>Original English</summary>
>> Exactly. Exactly. What do you What do you guys think of those? Is that Is that like a a toy kind of rendering? Is that kind of just an extension of the fact that you know it does kind of feel like a game to be managing your agents like that or is that like like is that the start of a new sort of genre of simulator? I mean, I think it could be, you know, like being the general manager of a line of business at any company at Credit Karma or Google or wherever else is it is a sort of sim, you know, you're sort of working with all of these teams who and you have a limited amount of control and you have incomplete imperfect information and then you have market forces. So,
</details>

>> 我觉得并没有那么大差别。而且现在能轻而易举地创建这些高野心的交互界面。在当前环境下你完全可以这样做，甚至可能是最优解；而在过去，成本太高了，根本不合算。没错。
<details><summary>Original English</summary>
>> I don't know that it's that different. I actually think that now you can trivially create these really ambitious interfaces. Yeah. So in that world you might do that and it might actually be optimal whereas in the old world the cost was so high it just was insane. It made no sense, you know. Yeah, that's right.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Sure.
</details>

>> 受到游戏启发的图形用户界面（GUI）被用于Agent管理，这让我想到一点：普通大众会觉得智能体编排并不直观。在命令行里试图管理你的Agent，使用以纯文本为主的界面是非常不直观的。所以我认同未来可能会出现面向大众市场的可视化界面，
<details><summary>Original English</summary>
>> I think it's um I think one thing that the the gooies, the graphical user interfaces that are inspired by games being used for agent management makes me think of is that um the average consumer finds agent orchestration to be non-intuitive, right? like work working from a command line trying to manage your agents you know these using the primarily textbased interface that is non-intuitive and so I I do agree that there will probably be a more mass market visual interface
</details>

>> 让普通消费者可以用来管理一组Agent。
<details><summary>Original English</summary>
>> that an everyday consumer can use to manage like a collection of agents
</details>

>> 至于它到底会长得像《星际争霸》、《帝国时代》还是《异星工厂》（Factorio），具体实现形式我不太确定，
<details><summary>Original English</summary>
>> and so um and whether it looks like Starcraft or Agent Empires a factorial that I'm less sure of the exact implementation
</details>

>> 但感觉我们在探索以Agent为核心工作的交互界面上，目前还处于非常早期的阶段。
<details><summary>Original English</summary>
>> but it does feel like we're early in sort of like figuring out user interface for primarily a gent work players.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 商业模式、发行平台与社区生态的分化

>> 约翰，我很想听听你的看法。显然Tim和Asha都公开站出来支持AI游戏开发社区，这很棒。但你认为他们的公司和生态系统，
<details><summary>Original English</summary>
>> Yeah. So, John, one thing I'm really curious to hear from you on, obviously Tim and Asha have come out, you know, really supporting the kind of community around AI developed games, which is awesome. But do you think that their companies and ecosystems
</details>

>> 真的做好了捕获这一趋势价值的准备？还是说他们自知必须做出改变，目前其实处在一个很尴尬的位置？
<details><summary>Original English</summary>
>> are [clears throat] set up to really capture the value from this trend or do you think that they're currently in an awkward position today knowing that they need to change?
</details>

>> 问得很好。但如果拿模组举例，历史上IP的原始拥有者，
<details><summary>Original English</summary>
>> Yeah, I think it's a good question. But I think um I mean if you just take modding as an example, historically the original owners of IP
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 并没有从基于其IP打造的模组中获得多少收益，对吧？DotA的最初创作者在《英雄联盟》诞生后并没得到太多商业好处；我也不确定《半条命》的初始开发者从《反恐精英》中赚了多少。所以我认为在商业模式上存在空白需要摸索。如果你真正拥抱AI作为玩家群体的混搭、Mod、反编译和重编译引擎，作为一家商业公司，你该如何从中获利？
<details><summary>Original English</summary>
>> have not benefited that much from the mods that have been created on top of their IP, right? And so I think the original creators of of Dota didn't really benefit that much from League of Legends when that was created. I'm not sure if the original HalfLife developers earn that much from from Counterstrike. And so I think there is a gap in terms of business models that need to be figured out. And sort of if you have if you're really embracing AI as like a remixing, modding, decompilation, recompilation engine for that empower your player base with like how do you as a company benefit from that sort of commercially, right? And
</details>

>> 大家都还处于早期探索阶段。我听说有人在探讨是否能建立一种分成或版税机制回流给原厂，
<details><summary>Original English</summary>
>> um I think I think folks are still early in that. Like I've heard, you know, I've heard talk of folks like trying to figure out if there's like a a revenue share or royalty that can go back to the company and
</details>

>> 以此赋能创作者。但我觉得这里面还有很多问题没有解决。
<details><summary>Original English</summary>
>> um therefore you're powering like creators. But, you know, I I think there's there there's a lot to be figured out there still.
</details>

>> 在我看来最强健的形态是《我的世界》。Minecraft确实极大地受益于模组生态。
<details><summary>Original English</summary>
>> Um I mean, the strongest form in my mind is Minecraft. you know, like Minecraft really benefits from the mods ecosystem,
</details>

>> 但有趣的是，我们常把“混搭”（remix）和“扩展”（extend）混着用。
<details><summary>Original English</summary>
>> but it's interesting cuz we've interchangeably used the works rem the words remix and extend,
</details>

>> 但我认为，所有扩展核心游戏、共享社区基础的附加内容，
<details><summary>Original English</summary>
>> but I actually think that, you know, all of the additions that extend the core game and maybe share a core foundation of community
</details>

>> 加上基础游戏本身，实际上能让IP所有者大幅受益。
<details><summary>Original English</summary>
>> plus a base game that actually really benefits the IP owner. Y
</details>

>> 而当你把游戏分叉出去独立立项时，原厂就得不到任何好处，甚至可能分裂社区。
<details><summary>Original English</summary>
>> whereas when you're forking the game, there is no benefit. In fact, you might even be splitting the community.
</details>

>> 没错。
<details><summary>Original English</summary>
>> That's right. That's right.
</details>

>> 这又回到了咱俩私下讨论过的一个问题：你如何为下一代AI游戏或使用AI制作的游戏创造全新的分发形态？
<details><summary>Original English</summary>
>> Yeah. And I think it goes back to something which um I know you and I have talked about um separately which is um how do you create new forms of distribution for the next generation of AI AI games or games that are created using AI right and
</details>

>> 今天许多此类游戏仍在走传统分发渠道：
<details><summary>Original English</summary>
>> I think today like many of these games are still going through traditional distribution channels right they're
</details>

>> 它们被发布在Steam或应用商店上；在Roblox里制作的内容就受限于Roblox生态。我认为市场上存在建立新分发平台的机会——
<details><summary>Original English</summary>
>> they're being posted on Steam on the app store and you know they're you know if you're making something in Roblox it's still within the Roblox ecosystem and I think there is an opportunity for a company out to also create a distribution platform.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 一个原生利用并赋能所有这些AI游戏创作者的平台。由于目前所有游戏都走传统渠道，这种平台在今天还并不真正存在。
<details><summary>Original English</summary>
>> Which natively harnesses and empowers all these AI game creators that are making stuff and then um and it doesn't really exist today because of the fact that all the games are going through traditional channels, right?
</details>

>> 你真该去看看Spawn。我们虽然不是投资人，但我非常欣赏他们的做法。那是雅各布（Jacob）和他的团队，他们打造了这种共享社区兼游戏生成平台。你在里面与一个名为Savvy的具身Agent协作：她在所有游戏里都陪着你，不仅能接收平台内的bug反馈，还能在你玩游戏的同时实时修改游戏，
<details><summary>Original English</summary>
>> Well, you should check out Spawn actually. You know, Spawn, we're not investors, but I'm a huge fan of what they're doing. It's Jacob and team, and they've created this sort of shared community plus game generation platform. Um, and what you do is you work with this embodied agent named Savvy. So, she's in all the games with you. She can like not only take bug reports in the platform, but she can modify the the game while you're in it,
</details>

>> 就像副驾驶（Co-pilot）一样。
<details><summary>Original English</summary>
>> like a co-pilot.
</details>

>> 没错。她能为你开启传送门，让你无缝跨入其他游戏；
<details><summary>Original English</summary>
>> Yeah, that's right. And then you um and she can create portals for you, so you can kind of step into other games. Yep.
</details>

>> 你还可以带上其他玩家。同一个社区内的每款游戏默认都是多人联机。这还处于早期，但这是我见过的在这类探索中最令人印象深刻、最具野心的尝试，我相信未来还会有更多。
<details><summary>Original English</summary>
>> And you can bring other players with you. Every game is multiplayer by default with the same community. Mhm. So, it's it's early, but it's the most impressive, ambitious effort I've seen at doing something like this, and I'm sure there'll be more.
</details>

>> 是的，这很令人兴奋。我是Jacob的粉丝，关注这家公司有一段时间了。更广泛的机遇在于：如何打造一个能在不同游戏之间持续留存的社区？这样你就不会面临“几个人玩这个游戏，几个人玩那个游戏，彼此毫不相连”的割裂。我认为这是一个巨大的机会。Minecraft和Roblox就是绝佳范例：一旦进入Roblox生态，哪怕玩腻了一款游戏，或者通关了一款，里面还有成千上万甚至数以百万计的其他体验供你参与。
<details><summary>Original English</summary>
>> Yeah. No, I think that's um I think that's exciting. And yeah, I'm a fan of Jacob and I've been following the the company for a while. I think um I think the broader opportunity for hey, like how do you create a community that basically persists between games, right? And so you're not just here's a couple of people to play this game and a couple of people to play this game and they're not interconnected. I I think that is a a huge opportunity, right? And I think Minecraft and Roblox are great examples of this where once you're inside the Roblox ecosystem, if you ever get bored of one game, like you've beaten a game where there's like hundreds of thousands, if not millions more sort of experiences that you can participate in, right? And
</details>

>> 约翰，你能对比一下这两者吗？我注意到在Roblox里，所有游戏差异极大，其核心共享游戏本身（如果能称之为游戏的话）其实非常单薄；
<details><summary>Original English</summary>
>> I think that's Can you contrast the two, John? Cuz here's one thing I've noticed like Roblox all the games are extremely different. So it feels like the kind of core shared game, if you even call it that, is actually pretty thin.
</details>

>> 而在Minecraft中，核心共享体验极其深厚。你认为必须先有一个内容极其丰富的底座游戏吗？还是说，纯粹依靠传送门串联、缺乏底层共同玩法机制的世界，本身就更难起步？
<details><summary>Original English</summary>
>> Mhm. Whereas in Minecraft, the core shared game is very rich. Do you think you need to have a really rich game or is it because it feels like the pure sort of portal based worlds without a shared core gaming mechanic are harder to get off the ground or is that not true?
</details>

>> 我认为类似Minecraft这样偏中心化模式的好处在于：每个人最初玩的是同一款游戏；
<details><summary>Original English</summary>
>> I think having a I think the benefit of a of a Minecraft model where it's more centralized, right? like everyone starts off playing the same game
</details>

>> 当你制作Minecraft模组时，你是在分叉、在魔改、在打上个人烙印。这种模式的好处在于大家拥有共同的体验，对原有IP非常熟悉，你的模组就像同人小说（fanfiction）：
<details><summary>Original English</summary>
>> and to your point you're forking you're modding it you're making you're making it your own when you um create create your Minecraft mods I think the benefit of that is that everyone has a shared sort of experience and they're familiar with the IP and you're kind of departing from that and so like the Minecraft mods are almost like fanfiction right like
</details>

>> 大家都看过同一部《权力的游戏》，知道丹妮莉丝、琼恩·雪诺以及守夜军团是什么。Minecraft拥有深厚的共同文化基础——末影人、末影龙等等。[吸气][清喉咙] 这与去中心化的模式截然不同。去中心化更符合我对Roblox的定性：玩家可以从任何一款游戏进入Roblox生态，比如我之前提到的《越狱》（Jailbreak）或《布鲁克海文》（Brookhaven）；
<details><summary>Original English</summary>
>> but everyone's like watch the same Game of Thrones series right and so they know who Daenerys and Jon Snow and what the watch is and you know and so on so forth and Minecraft has a lot of shared culture, right? after the enderman and like the dragons and you know [gasps] um [clears throat] and that feels very different from a more decentralized approach which is what I would characterize Roblox as like cuz people can enter the Roblox ecosystem from any game like I mentioned earlier like Jailbreak there's there's a bunch of other games like Brook Haven
</details>

>> 体验截然不同，然后你得摸索接下来去哪儿、如何成为创作者。但两种模式完全都走得通。这本质上是哲学理念的差异：你究竟想如何扩展游戏并凝聚社区？
<details><summary>Original English</summary>
>> um and then you have a very different experience and then you have to learn like where to go from there and how to be a creator but both approaches are are totally viable right But um I do think um yeah I I I do think it's just a philosophical difference in terms of like how you want to extend uh the game and harness the community
</details>

>> 两种路径都能奏效。
<details><summary>Original English</summary>
>> and both can work.
</details>

>> 是的，肯定都能走通。
<details><summary>Original English</summary>
>> Yeah, both can work for sure.
</details>

### “无尽游戏”圣杯与终极游戏构想

>> 回到我们关于游戏工作室和发行商的讨论，你觉得他们现在最兴奋的是什么，最担忧的又是什么？
<details><summary>Original English</summary>
>> Uh going back to our discussion about studios and publishers, what do you what do you think they're the most excited by and what do you think they're the most worried by right now?
</details>

>> 我觉得降低成本绝对让他们超级兴奋。
<details><summary>Original English</summary>
>> I mean, I think getting their costs down, having like has got to be super exciting. Yeah.
</details>

>> 而且能以更低的财务风险创造更多新IP。
<details><summary>Original English</summary>
>> And just being able to create, you know, more IP with less financial risk. Yeah.
</details>

>> 这极其吸引人。对许多工作室而言，他们的生死存亡往往取决于能否为发行商争取到某款游戏的开发合同；一旦游戏暴死，他们可能就拿不到下一次机会。成百上千的人在疯狂过度加班。这行业的生活质量可以说是最差的之一了。大家之所以还在坚持，是因为纯粹的热爱。
<details><summary>Original English</summary>
>> Seems to be hugely exciting. Look, for a lot of these studios, you know, I think even the studios, they kind of live and die by winning the right to develop a game for a publisher and then if the game doesn't do well, they may not get it again. You have hundreds of people that are overworked like crazy. It's got to be one of the worst qualities of life just being in that industry. I mean, people do it anyway because they love it.
</details>

>> 但确实太艰辛了。因此我认为行业从业者的平均生活质量，以及整个商业模式的健康度，都应该会大幅提升。
<details><summary>Original English</summary>
>> Um, but it's tough, you know. So, I I think that just the quality of life of the average person in the industry and then honestly the quality of the business should go way way up.
</details>

>> 是的。他们担忧的可能是：比如微软虽然拥有《我的世界》，但Xbox或许希望能拥有更多类似的产品——更接近于网络和社交产品，而不仅仅是纯娱乐消耗品。
<details><summary>Original English</summary>
>> Yep. I think maybe what is worrisome to them is I'm guessing that you know Xbox I guess Microsoft owns Minecraft but they wish they had an asset like that that was closer to a network and a social product than a pure entertainment product. Yeah,
</details>

>> 就像《堡垒之夜》，五年前虽然是全球最受欢迎的游戏，如今讨论度也没那么高了。所以存在一个圣杯——正如你所说的，约翰——“永无止境的游戏”（neverending game）或“永远的游戏”（forever game）。但要做到这一点太难了。或许有了这些技术，他们能有更大的胜算。
<details><summary>Original English</summary>
>> I'm sure Fortnite despite being the most beloved game in the world 5 years ago like it's not really discussed as much. So, I think there's this holy grail, what you call, John, a neverending game or a forever game, but it's so hard to get there. And maybe with these technologies, they'll have a better shot.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在我与游戏开发者的交流中，大体上他们都已经在使用AI了。在提高生产力的基础工具层面，AI已经变成了准入门槛：用AI生成游戏设计文档、生成概念艺术、快速验证构想并推进到原型阶段。正如我之前提到的，缩短从初始想法到原型的距离和时间，大家普遍对此感到非常振奋。我认为这是游戏工作室采纳AI的“第一波浪潮”。
<details><summary>Original English</summary>
>> Yeah. So, um, in my conversations with game developers, I would say in general, they're all using AI already. I think it's AI has become table stakes in terms of just like tools that you use to basically be more productive, right? consider using AI to generate game design docs that generate concept art quickly iterating on on an idea and go to prototype as I mentioned earlier is like shortening that that the distance and time between an initial idea and prototype. I think everyone's like universally like really excited about that. Um I think I think of that as sort of like wave one of AI adoption among sort of game studios. Mhm.
</details>

>> 而下一波浪潮，也就是Anish刚才提到的更让人兴奋的方面是：如何利用AI创造全新的玩法、全新的机制、甚至今天尚不存在的游戏品类？
<details><summary>Original English</summary>
>> I think the next wave, which is what um Anish has to that's even more excited exciting is how do you make AI to create like new types of gameplay like new game mechanics, new game genres that don't exist today.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这能极大拓宽游戏市场。你不再只是把GTA 6做得更快、更便宜，而是在创造一种以前根本无法存在的新型游戏。我早先写过一篇关于“无尽游戏”（never-ending game）概念的文章，这是我个人非常痴迷的方向。大型多人在线（MMO）的圣杯，就是一款能够无限自我调整以适应玩家需求的游戏。
<details><summary>Original English</summary>
>> But could massively expand the market for games, right? So you're not just making GTA 6 but like faster and cheaper. You're making a new type of game, right, that couldn't exist before. Yeah. And um I think the I think the the article I wrote um uh earlier on the concept of the never ending game, it's you know it's something that I'm personally passionate about. I I'd love to see happen. But um the holy grail for an MMO is a game which infinitely sort of adapts itself to what the players want, right? So
</details>

>> 比如在MMO里你降落在一个海滩上，系统预设让你去森林，因为主线是这么开头的。但也许你特别喜欢大海，你决定留在海滩上造一艘船扬帆出海。如今的MMO无法处理这种情况，因为它是线性脚本化的，指望你进入森林去触发某个任务。但在自适应MMO中（比如基于世界模型构建），它可以真正为热爱海洋的玩家即时生成一整套任务线：遭遇海盗袭击、海战机制等等。
<details><summary>Original English</summary>
>> if you land in a beach in in an MMA and then you're supposed to go to the forest because that's how the game starts. But, you know, maybe you really love the ocean and you decide to stay in the beach and you build a ship and you like sail off into the ocean. Like the MMO today couldn't like handle that because it's right scripted linearly that expect you to go into the forest and maybe there's a thing that happens that sets you up on the on a quest. But in an adaptive MMA, one that you know maybe is built using like world models for example, like you could literally generate an entire quest line for someone who really likes the ocean and like now there's pirates that are attacking you. There's like a nautical, you know, warfare element, etc. Um,
</details>

>> 我觉得这种讨论总会滑向科幻，但你还记得《安德的游戏》（Ender's Game）里那个“心灵游戏”（mind game）的概念吗？
<details><summary>Original English</summary>
>> and then I feel like sometimes these discussions always go into science fiction, but um, you remember in Ender's game, they have the concept of the mind game.
</details>

>> 记得。游戏随时随刻都在根据安德当下的意念进行自我调整。我认为在某个时刻，我们可能会迎来属于我们自己的心灵游戏版本。
<details><summary>Original English</summary>
>> Mhm. And it's that the game is just adapting to what Ender wants to do in any given moment in time. So, um, and I think it's it's possible that we'll see our own version of the mind game at some point,
</details>

>> 那将是一款让人无法自拔的游戏，因为它随时都在根据你想做的一切自我调整。
<details><summary>Original English</summary>
>> but I think that would be the game that like like you can't stop playing because it it adapts itself to whatever you want to do at any given moment in time.
</details>

>> 也许我们此时此刻就正身处其中呢。
<details><summary>Original English</summary>
>> I mean, perhaps we're playing it at this moment.
</details>

>> 哈哈，确实。[笑]
<details><summary>Original English</summary>
>> Yeah, exactly. [laughter]
</details>

>> 《黑客帝国》（The Matrix）。
<details><summary>Original English</summary>
>> The Matrix.
</details>

>> 或者是《安德的游戏》本身，故事里他甚至不知道自己是在游戏中。
<details><summary>Original English</summary>
>> Yeah. Well, or Yeah. Or Andrew's game itself, right? I don't even think the story is that he's in the game. Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你们投入游戏时长最多的是哪几款？
<details><summary>Original English</summary>
>> Um what what games do you guys have the most amount of hours in?
</details>

>> 对我来说是《巫师3》（The Witcher 3）。
<details><summary>Original English</summary>
>> Oh, for me, I've played Witcher 3.
</details>

>> 我通关了两次。
<details><summary>Original English</summary>
>> I've completed it twice.
</details>

>> 厉害。
<details><summary>Original English</summary>
>> Nice.
</details>

>> 半途重开过很多次，我真的深爱这款游戏。另一款我极度钟爱的是《沙丘2000》（Dune 2000）。
<details><summary>Original English</summary>
>> Half completed a bunch of times and I just absolutely love it. The other game that I actually adore is Dune 2000.
</details>

>> 哦！
<details><summary>Original English</summary>
>> Oh,
</details>

>> 那是我成长过程中最爱的RTS，太好玩了。有人已经把它移植到了Mac上，玩起来还是当年的味道。
<details><summary>Original English</summary>
>> that was my favorite RTS growing up. It's so so good. And actually, somebody had already ported it over to play on Mac and it's as good as it ever was.
</details>

>> 太棒了。
<details><summary>Original English</summary>
>> That's awesome.
</details>

>> 如果是RTS爱好者且还没玩过，我强烈推荐《沙丘2000》。
<details><summary>Original English</summary>
>> So, for RTS fans, if you haven't played that, I highly recommend Dune 2000.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah,
</details>

>> 我可能在《英雄联盟》里投入了上千个小时。
<details><summary>Original English</summary>
>> I am um I probably put thousands of hours into League of Legends and so um I think
</details>

>> 我最好的一些朋友和深厚友谊都是在那款游戏里建立的，所以它应该是我玩得最多的游戏。排在后面的可能是《星际争霸》。
<details><summary>Original English</summary>
>> uh some of my best friends and friendships have been made in that game. And so, I think that has to be probably my my most played game. Um and then probably closely behind that is uh Starcraft. Nice.
</details>

>> 从《母巢之战》到《星际争霸2》等所有版本我都玩过。硬核RTS受众随着时间推移不断萎缩，它是一个典型的例子，因为这种流派太难玩了。你的APM（手速）至关重要；你很难在不自我怀疑的情况下打竞技匹配，因为其他人都比你快得多、打得好得多。从纯市场规模和分析来看，并没有多少开发者愿意再去制作全新的现代RTS。但有了AI，我非常期待看到RTS流派的爆发，我会尽可能多去玩。
<details><summary>Original English</summary>
>> So, I've played all of the all of the versions, you know, back to boot war to Starcraft 2 and so on. And it's a classic example of a game which the audience for hardcore RTS is just dwindowed over time cuz it's such an such a hard hard genre to play. Like it matters how like what your APM is. Like you can't play competitively without feeling bad about yourself cuz like everyone everyone else is playing is like so much faster and better at the game than you. Um, you know, there's not a lot of developers that are trying to make like new and modern RPS games. Um, you know, because the audience size doesn't support it if you just look at it from a pure like market size and analysis, but with AI, like I'm excited to see an explosion in RTS games, right? And I I will be playing as many of them as I can.
</details>

>> 漂亮。我是《十字军之王3》（Crusader Kings 3）的忠实粉丝。它不算严格的RTS，向不了解的人解释时，我把它描述为《模拟人生》与《帝国时代》的结合体。因为你既要处理性格管理、
<details><summary>Original English</summary>
>> Nice. Nice. I'm a I'm a big Crusader Kings 3 fan, which isn't which isn't really RTS, but it is like it's it's really it's like I would I I describe it to people who don't know about it as like the Sims mixed with Age of Empires. It's like cuz you you get like kind of personality management,
</details>

>> 人际关系和政治。
<details><summary>Original English</summary>
>> relationships, politics.
</details>

>> 没错。同时又拥有宏大的大地图，去管理你的王朝和封地等等。深度极其惊人。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. Exactly. But then you also get kind of this over this grand like overworld of like managing your your dynasty and your realm and stuff like that. So, it's so so deep. Um,
</details>

>> 哇。
<details><summary>Original English</summary>
>> wow.
</details>

>> 在最后结束之前，
<details><summary>Original English</summary>
>> Yeah. Anyway, to to close us out, um,
</details>

>> 你们每个人多年来一直想做、而现在终于能做出来的游戏是什么？
<details><summary>Original English</summary>
>> what's a game that each one of you has been thinking about making for years and and now you finally can.
</details>

>> 我可以先简单说一下。我小时候运营过BBS（电子公告板系统），这暴露了我的年龄。在互联网普及前，人们通过拨号连入。BBS以这种异步多人游戏闻名，因为同一时间只能有一个人拨号进来。你连上线，打完你那一回合后下线；第二天再上线打下一轮，同时查看其他人的行动结果。
<details><summary>Original English</summary>
>> I mean, I can go quickly. So, I I grew up um running a bulletin board system, which tells you what my age is. Um, so pre- internet people would dial in. And BBS's were famous for having these async multiplayer games because only one person could phone in at a time. So you'd play your turn. You'd phone up, connect, play your turns, log off the next day, play your next turns, and see everyone else's turns at the same time.
</details>

>> 酷。
<details><summary>Original English</summary>
>> Oh, cool.
</details>

>> 那里有一整套精彩绝伦的异步多人游戏，其中有两款是由Google最早期的员工之一在他还在斯坦福求学时编写的，他叫Amit Patel。他做过一款叫《Baron Realms Elite》和一款叫《Solar Realms Elite》的游戏。
<details><summary>Original English</summary>
>> So there's a whole genre of amazing um async multiplayer games, including two written by one of the earliest employees at Google. This was when he was still at Stanford. His name is Ait Patel. So, he made a game called Baron Realms Elite and a game called Solar Realms Elite.
</details>

>> 遗憾的是，他弄丢了更好的那款《Solar Realms Elite》的源代码，但他保留了游戏设计文档，而且还有执行文件（.exe）。
<details><summary>Original English</summary>
>> Unfortunately, he lost a source code for Solar Realms Elite, which is the better of the two, but he has a game design doc and he haven't he has an .exe.
</details>

>> 过去每出一代新模型，我都尝试问它“你能重构这款游戏吗”，模型都做不到。而现在，我的电脑上终于跑起了一个高度忠实的重现版本。不可思议。
<details><summary>Original English</summary>
>> So, I for every genre of the models I've tried like, hey, can you recreate the game and has not been able to do it? And I like now have a what feels like a faithful recreation running on my computer. Incredible.
</details>

>> 这故事太棒了。
<details><summary>Original English</summary>
>> That's a great story.
</details>

>> 对我来说可能也类似。我是《文明》（Civilization）系列的狂热玩家，原版《文明2》（Civ 2）承载了我童年最美好的回忆。那是16位Windows版本的文明，得插软盘才能玩。现在它已经无法运行了，因为它是16位的可执行程序。但我很想在现代硬件架构上重现它。另外，我也一直在思考引入Agent的《文明》会是什么样，
<details><summary>Original English</summary>
>> Yeah. I think maybe something along a similar vein for me is I'm I'm a big um Civilization player and I think the original Civ 2 is generated some of my like most endearing sort of childhood memories. It's like the 16 bit like Windows version of of Civ that you need a floppy disc in order to play. It's it's not playable today anymore, you know. It's a 16- bit executable. Um but I would love to recreate that game on on modern sort of like a modern hardware stack. Nice. Um, and then you know I I've also long thought about like what does Civ look like with agents,
</details>

>> 对吧？
<details><summary>Original English</summary>
>> right?
</details>

>> 因为这款游戏的宏大幻想是让你扮演帝国的统治者，
<details><summary>Original English</summary>
>> Because um the fantasy of the game is that you are supposed to be the ruler of an empire and like
</details>

>> 但在游戏后期这种体验破灭了，因为你不得不微观操纵帝国里的每一个单位。
<details><summary>Original English</summary>
>> um but that fantasy sort of breaks down over the course of Sib where you're microing like literally every unit in your empire.
</details>

>> 是的。[清喉咙]
<details><summary>Original English</summary>
>> Yeah. M [clears throat]
</details>

>> 但你可以想象，如果每个单位都是一个智能体，
<details><summary>Original English</summary>
>> but you know at some point in time you could imagine hey what if there were SB where every unit was a was an agent
</details>

>> 拥有自己的诉求和目标；而你作为帝国统治者，主要负责制定战略，并设法引导臣民朝着你希望的方向发展。你不能强令他们完全照办，而是必须通过安抚和引导……
<details><summary>Original English</summary>
>> and they had their own sort of like agenda and goals and then you as the ruler of the empire you're sort of setting strategy and then you're trying to influence your subjects to grow in the direction that you want them to right and you can't just have them do exactly what you want you have to kind of like casual and sort of like imping
</details>

>> 我有个天大的好消息要告诉你：这就是《十字军之王3》。这款游戏已经存在了，而且完全不需要用到前沿AI。
<details><summary>Original English</summary>
>> I have amazing news for you this is Crusader Kings three. This game exists. This game exists and and doesn't use, you know, like Frontier Frontier AI at all.
</details>

>> 真的吗？完全一样？
<details><summary>Original English</summary>
>> Is that true? It's the same game.
</details>

>> 差不多就是这样。你必须应对阴谋、不同人的性格、他们对你的好感度；有时好感度太低，大家就不会按你的意愿行事。如果你想征服一个王国或领地，有无数种方式：你甚至可以暗杀继承序列排在你前面的人。机制极深。在我看来，它其实最接近你之前谈到的那种“无尽游戏”——随着深度与真实感的增强，你将拥有多得多的选择排列组合。你一定要去试试。在疫情期间，我在2020年底得了新冠，那时我开始自学C#，并尝试用Unity做一款日系风格的恋爱模拟游戏。
<details><summary>Original English</summary>
>> I mean, yeah. Yeah, pretty much. I mean, you do you have to manage like schemes and like, you know, different people's personalities and their opinion of you and like sometimes people won't do what you want because their opinion of you is too low. Like there different way like like if you want to you know conquer a realm or conquer you know a different territory there are so many different ways you can do it. Uh you can like murder people who are like ahead of you in succession. Like it's it's super deep. It's like yeah it's it's it's I think like it it actually feels the closest to me like a kind of you know neverending and endless game like you were talking about before in terms of like what will this feel like when it is super deep and super realistic and you get like way way way more permutations of choices. So yeah, you should you should definitely check it out. During the pandemic, um I I got COVID in like the end of 2020 and I started teaching myself C and I started making like a like sort of Japanese style dating sim with Unity.
</details>

>> 很热门的品类。
<details><summary>Original English</summary>
>> Popular.
</details>

>> 那会儿正值Unity上市前后，我纯粹是出于好奇想看看Unity究竟怎么运作、上手有多容易。其实就是分支对话树，编程上并没有那么高深，我也没做太深入，只做了基础的生命值和口渴度管理之类的数值。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. Well, cuz it was right around like Unity's IPO and so I was just kind of like curious about, you know, Unity and like how it worked and like how easy it was. It was like I mean I didn't I like it was basically like branching dialogue trees. So it wasn't really like that advanced in terms of programming and I like didn't really get that far. There was like some basic unit like like kind of like managing health and like thirst and stuff like that. But
</details>

>> 我们虽然扯远了，但既然你提到了，我认为恋爱模拟游戏实际上正是迎来颠覆的时机。
<details><summary>Original English</summary>
>> I actually think the dating we're going off on a tangent now but because [clears throat] you brought it up I think the dating sims genre is actually right for a
</details>

>> 是的。有一类叫乙女游戏（Otome games），基本上是面向女性的恋爱模拟，与不同性格和原型的男性角色约会。中国开发者做了一款叫《恋与深空》（Love and Deepspace）的游戏，目前极其火爆，带来了数亿美元的收入。但痛点在于制作内容极其耗时费力，因为这类游戏的扩展包本质上就是新角色：推出一个可约会的新男主，游戏就迎来一次大更新；他们必须打造丰富的背景故事——比如这个角色喜欢猫、喜欢在沙滩散步但恐高等等，玩家必须去逐步发掘这些。
<details><summary>Original English</summary>
>> Yeah. Um so there's a genre called autoto games which are basically you know dating sims for women to basically um go on dates of um with like men of different personalities and archetypes and so on. Um and there's a game called Love and Deep Space which is made by a Chinese developer that is blowing up. I mean it's throwing hundreds of millions in in revenue. Um, but the challenge is that it's it takes a lot of time and work to create the content because the expansion packs for the games are basically characters, right? There's a new there's a new guy that you can date and then that is an update for the game and they have to build out this like rich backstory like this guy like you know likes cats and like walks in the beach but like is terrified of heights etc. And there like you kind of have to discover all of this.
</details>

>> 但未来完全没有理由不把他们做成智能体（Agent）。
<details><summary>Original English</summary>
>> Um, but there's no reason why they can't be agents in the future. Yeah. Like
</details>

>> 这些人拥有独立的人格，其背景设定被编码进数据库中；当你与他们交谈时，他们会实时给予反馈，并且记得你的一天。我认为恋爱模拟这一流派现在完全敞开着，正等待着AI的彻底颠覆。
<details><summary>Original English</summary>
>> these are people that have their own personalities. They have their board. It's kind of encoded into their, you know, into their like database and they're um reacting to you in real time as you're having conversations with them. They know about your day. I I think there's I think the dating s genre is like wide open right now and right for disruption for for AI.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 太精彩了。
<details><summary>Original English</summary>
>> Amazing.
</details>

>> 这个结尾很有意思。
<details><summary>Original English</summary>
>> Amazing. Fun fun note to end on.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah. For sure.
</details>

>> 很好的收尾。非常感谢大家的参与。
<details><summary>Original English</summary>
>> Fun note to end on. Thank you guys so much for joining.
</details>

>> 谢谢，非常开心。感谢。
<details><summary>Original English</summary>
>> Thank you. So much fun. Thanks.
</details>

>> 聊得太棒了。很酷。未来还会有很多期，对吧？是的。
<details><summary>Original English</summary>
>> This was great. That was cool. Yeah. First of many, huh? Yeah.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>