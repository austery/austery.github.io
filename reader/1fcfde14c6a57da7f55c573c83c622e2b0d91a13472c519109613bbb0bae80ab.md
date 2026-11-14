---
author: a16z
date: '2026-08-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GHrnbvkVPZA
speaker: a16z
tags:
  - prompt-engineering
  - software-development
  - startup-growth
  - business-model
  - mergers-acquisitions
title: 解密 Cursor 的崛起：AI 编程领域的超级黑马与颠覆性增长逻辑
summary: 本期播客由 a16z 合伙人 Martin Casado、Sarah Wang 和 Matt Bornstein 深度对谈，剖析 AI 编程编辑器 Cursor 如何在微软 GitHub Copilot 等巨头的夹击下，凭借极致的产品偏执、果断的自我革命、创新的企业级销售体系和独特的人才战略，在两年内实现垂直起飞并成功并入 xAI 帝国的传奇历程。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Michael Truell
  - Aman Sanger
companies_orgs:
  - OpenAI
  - Anthropic
  - Microsoft
  - xAI
  - Cognition
products_models:
  - Cursor
  - GitHub Copilot
  - Claude 3.5 Sonnet
  - GPT-4o
media_books: []
status: evergreen
---
### 片头预告：人机交互界面是核心关键

**主持人**: 我们现在不需要在模型层面上与 Anthropic 和 OpenAI 竞争。人与模型之间的交互界面才是最关键的。

<details>
<summary>Original English</summary>

**Host**: We don't need to compete with anthropic and open AI on models right now. The interface between the human and the model is the key thing.

</details>

**麦特·博恩斯坦**: 如果你看当时的竞争格局，那几乎是不可思议的，甚至是有点滑稽的。

<details>
<summary>Original English</summary>

**Matt Bornstein**: If you looked at the competitive landscape, it was almost silly.

</details>

**马丁·卡萨多**: 我问过 Michael，我说，你怎么看 Cloud Code？他的回答大概是：‘听着，我们正在进军世界上最大、最广阔的市场。你永远都会遇到强大的竞争对手，但这吓不倒我们。’

<details>
<summary>Original English</summary>

**Martin Casado**: I asked Michael, I was like, what do you think about cloud code? And he said something to the extent, look, we are going after the biggest market in the world. You're always going to have formidable competitors. That does not scare us.

</details>

**麦特·博恩斯坦**: 作为创始人，我们都希望充满雄心壮志，希望把帕累托前沿推向极限，但你也必须清楚当前的曲线究竟在什么位置。

<details>
<summary>Original English</summary>

**Matt Bornstein**: As founders, we all want to be ambitious and we want to push like to the maximum point the paro frontier, but like you have to kind of know what the curve is.

</details>

**马丁·卡萨多**: 对我们来说，投资 Cursor 的决定其实非常明显。你还记得安德烈·卡帕西当时就在使用它。这显然已经成为了一种现象，是一个众所周知的品牌。

<details>
<summary>Original English</summary>

**Martin Casado**: For us, the decision to invest in curs was actually pretty obvious. You remember Andre Karpathy was using it. It was clearly a phenomenon. It was clearly like a known brand.

</details>

**麦特·博恩斯坦**: 他们在创纪录的时间里赢得了所有用户。现在，他们拥有了资产、数据和诀窍，可以构建属于自己的模型。除非你从前沿实验室开始，否则你真的无法逆向复制这种路径。那段时间肯定有一些让人惊呼的时刻，比如还记得什么时候……

<details>
<summary>Original English</summary>

**Matt Bornstein**: They went and got all the users in record time. Now they have the asset, the data, the knowhow to build their own models. You really couldn't do the flip of that unless you started as a frontier lab. They were definitely a couple of oh moments like remember when

</details>

### 初识 Cursor 与 2024 年初的 AI 编程格局

**莎拉·王**: 那么，首先我想带大家回到 2024 年初。显然，你们几位在那一年的 5 月份领投了这笔交易。但你们能带我们回顾一下，那一年第一季度和第二季度发生了什么？在官方正式达成合作之前，你们是如何开始与 Cursor 团队接触的？

<details>
<summary>Original English</summary>

**Sarah Wang**: so to kick off I actually wanted to take us back to early 2024 and you know obviously you guys led the deal in I think it was May of 2024 that year. Um, but can you walk us through what was going on in the Q1, Q2 of that year and maybe how you guys started working with Curser well before uh we ever partnered officially with them?

</details>

**马丁·卡萨多**: 好的，你需要把自己带回到 2023 年底和 2024 年初的场景中。我特意去查了一下，当时处于领先地位的模型是 **GPT-4o**、**Claude 3** 和 **Llama 3**。现在听起来感觉像很久以前的事了。

<details>
<summary>Original English</summary>

**Martin Casado**: So, you have to sort of transport yourself back to late 2023, early 2024. Um, I went back and looked it up. The leading models at the time were GPT40, Claude 3, and Llama 3. Like,

</details>

**莎拉·王**: 感觉就像一辈子那么漫长。

<details>
<summary>Original English</summary>

**Sarah Wang**: feels like forever ago.

</details>

**马丁·卡萨多**: Llama 3。

<details>
<summary>Original English</summary>

**Martin Casado**: Llama 3.

</details>

**麦特·博恩斯坦**: 那在当时其实是相当不错的模型。

<details>
<summary>Original English</summary>

**Matt Bornstein**: That was actually pretty good.

</details>

**马丁·卡萨多**: 是的，那是个非常出色的模型。当然，现在的策略已经发生了变化。当时在 AI 编程的辅助工具中，**GitHub Copilot** 处于绝对的领先地位，遥遥领先。这几乎是当时的共识。微软正在做他们最擅长的事，对吧？他们有 Copilot，有 Office 系列，还有 VS Code，把所有这些结合在一起，他们似乎无论如何都会赢得 AI 领域的这场胜利。

当时很明显，AI 辅助编程开始起作用了，但相比今天，那完全是一个不同的宇宙。当时你只有一些初步的迹象，表明你可以利用 AI 完成一些有意义的工作，但真正意义上的 AI Agent 还不存在。循环（loops）还不存在，推理（reasoning）在当时也完全没有真正展现出来。所以，那真的是一个疯狂的时期。

<details>
<summary>Original English</summary>

**Martin Casado**: That was great. Yeah, it was a great model. um you know change in strategy obviously now um the leading uh coding harness was copilot by like a mile right this this was like the consensus thing Microsoft was doing their Microsoft thing right they had copilot they had office you know they had vs code all of these things combined they were going to somehow win AI um and and so it was clear that AI coding was sort of working but it was a different universe compared to today right like like you had the sort of early signs that you could you could do meaningful work with AI, but agents didn't really exist. You know, loops didn't really exist. Reasoning didn't really exist at the time. So, it's sort of sort of a crazy time.

</details>

**麦特·博恩斯坦**: 当时有一大批公司都在切入编程这个赛道。一方面，有一类观点认为，赢得 AI 编程的唯一方法是构建基础模型，而且必须是针对编程进行特定训练的基础模型。另一方面，非常具有先见之明的是，有些公司专注于开发 AI Agent。而 Cursor 的定位则处于这两者之间。

除了开发模型，还有成百上千家公司在做 IDE 的插件（plugins）。由非常聪明的人领导的这两条路径在当时看起来都非常合理。在这些新兴领域里，最有趣的一点就是：聪明的创业者涌现出来，尝试各种非常有趣的事情。当时训练特定编程模型是非常合理的，因为基础模型在编程上的表现还没有那么好。

有一种理论是：如果我们专注于这一点，做个针对编程的专用模型，这就是突破口。而另一边做插件的人则在说：‘嘿，我们不要丢掉整个 IDE，那太疯狂了。但人类和模型之间的交互界面真的很重要，所以插件是一个很好的切入点。’

最终的结果证明，Cursor 所做的事情才是正确的道路。他们和我们一样，是坚定的‘苦涩教训（Bitter Lesson）’信奉者。当时他们会说：‘我们现在没必要去训练自己的模型。’ 当然，出于不同的原因，这一点在后来发生了变化，我们稍后会在播客中谈到。但他们当时的核心逻辑是：‘我们现在不需要在模型上与 Anthropic 和 OpenAI 进行竞争。人机交互的界面才是核心关键。’

这是 Michael 和 Aman 从 Cursor 成立之初就说得非常清楚的一点。他们常说：‘未来的编程看起来会像伪代码。’ 我记得 Michael 经常强调这个观点。当你去看一些旧的计算机科学论文时，会有一个展示算法的章节，它不是用实际代码写的，而是用伪代码。我们现在虽然不能完全用伪代码写程序，但很有可能你只需要把旧论文里的伪代码块拿出来，现在的模型就能直接帮你实现。这是 Cursor 团队从一开始就坚信的。事实证明，他们在这个问题上是完全正确的。真正重要的是将程序员的意图精简到最小的规格说明（specification）。

正如 Martin 所说，在那个环境下，我们和大量在这个赛道上探索各种路线的、非常聪明的创业者进行了交流。而 Cursor 团队在其中脱颖而出。

<details>
<summary>Original English</summary>

**Matt Bornstein**: That's there was a continuum of like companies going after coding, right? So, on one hand, you had those that like the only way to win coding is to build a base model and it has to be a coding specific one. And on the other hand, you had, you know, very preciently, by the way, companies just focus on agents, right? And like cursor was somewhere in between. And and not only models, there were a million companies doing plugins, too. And both of these were very reasonable things to do done by very smart people, right? Like that that's what's so interesting about these new spaces. It's like smart entrepreneurs show show up and do really interesting things. And in this case, model training was very a very reasonable thing to do because the models weren't that good at coding yet. And there was sort of a theory that if we focus on this and do a coding specific model, it'll that's the breakthrough. people doing plugins on the other side were sort of saying hey like let's not toss out the whole IDE like that would be a crazy thing to do but like the interface between human and and model is really important so so plugin is a great place to go um you know it just kind of turned out that the thing that cursor was doing was the right thing to do right they they like us they were very bitter lesson pilled you know at the time they would have said oh there's no need for us to go train our own model of course that changed later for different reasons which we're going to get into later in this podcast but it's like we don't need to compete with anthropic and open AI on on models right now. Um the interface between the human and the model is the key thing and this is something that that I remember Michael and Aman saying like a lot and saying just saying very clearly from the earliest days of of cursor saying code in the future will look like pseudo code like I remember Michael making this point a lot like when you look at old you know like computer science papers there's a section it's like here's the algorithm not in code but in like pseudo code which you know I'm sure many people um you know are used to and you know we don't exactly write in pseudo code now but probably you could like probably you could just take the pseudo code, you know, block from an old paper and and like the models now would implement that. This is like really what the cursor guys thought from the very beginning. And they've proven to be exactly right about this, right? It's like this sort of natural languageish specification like pairing the programmer's intent down to the minimum possible spec. That's what really sort of matters now. So, so anyway, so we're in we were in this world as Martine said, we, you know, we're talking to a ton of very smart um very interesting people working on coding in various ways. Um you know the cursor team kind of stood out because

</details>

### 高 Conviction 投资决策与 VS Code 分叉争议

**马丁·卡萨多**: 他们脱颖而出不仅是因为他们对世界的看法与我们一致，更重要的是，当时许多在顶尖 AI 公司（如 OpenAI、Midjourney、Replicate 等）工作的优秀工程师都在使用它，并非常认同这种模式。

而且，这支团队表现出了非同寻常的专注力。我记得我们邀请 Michael 来向我们的合伙人会议进行路演。整场会议 90% 的时间里，他都在对各种提议说‘不’。

<details>
<summary>Original English</summary>

**Martin Casado**: because not only did they sort of align with the things that we thought about the world um more importantly smarter people than us you know you know engineers working at at the time the leading AI companies like OpenAI, MidJourney, Replicate a bunch of others. Um you know all all kind of use this and subscribe to this model. Um and the team frankly just seemed kind of special right like they had an unusual degree of focus. Um, I remember we we we got Michael to come pitch our GP group. Um, and 90% of the meeting was him saying no to things,

</details>

**麦特·博恩斯坦**: 对于那些在做自己热爱产品的创始人来说，这真的非常罕见。风投（VC）总是会问你一些很愚蠢的问题，比如‘你们未来可能还会做些别的什么’，或者提出一些不着边际的关联想法。而 Michael 只是非常礼貌地坐在那里听完所有问题，然后淡淡地回答：‘嗯，很有趣。但不，我们不打算做那个。’

<details>
<summary>Original English</summary>

**Matt Bornstein**: which which which is just like like for for like founders out there working on products that you love. Like VCs will always ask you kind of dumb questions about other things you might do or things you're related to or whatever. And Michael literally just sat there and like very politely listened to all the questions and said, "Hm, interesting. No, like we're not going to do

</details>

**莎拉·王**: 等等，在这个点上，我能问你们一个问题吗？因为我太深刻地记得那场会议了。当你带 Michael 进来进行 A 轮路演时，他拒绝的其中一件事就是关于‘分叉 VS Code’的争议。

当时有一种更为普遍的共识认为，相比于直接分叉（fork）VS Code，做 VS Code 的插件会是更好的企业级路径，大家普遍不看好分叉。我记得 Martin 或者你们两个问他：‘你打算用这种分叉的媒介来获取企业客户吗？’ 

他当时看着我们所有人的眼睛，带着极高的信念给出了回答。我想转问你们，当时你们对他的回答有什么看法？是什么让你们有信心在当时做出一个在外界看来非常非主流（contrarian）的赌注？

<details>
<summary>Original English</summary>

**Sarah Wang**: Wait, wait, actually on that point, can I ask you guys a question?" um because I remember that meeting so vividly when you brought uh Michael in for the A and one of the things that he said no to was actually and you know to your point on like there were a lot of plugins, right? And so there was this maybe more consensus thought that a VS Code fork versus the plugin into VS Code would one would be better for enterprise and it wasn't the former it would be the latter. Um, and I recall I think it was you Martin or maybe it was both of you asking him, "Well, are you going to get enterprise customers with this medium?" Right. And he looked at all of us in the eye with high conviction and you know, well, I'm going to turn it back to you and like what did you think of his answer and um what gave you guys the conviction to take a pretty n I would say a pretty contrarian bet at the time.

</details>

**麦特·博恩斯坦**: 他们当时对为什么选择目前的‘设计空间’有着非常严密的逻辑阐述。例如，为什么不做一个针对编程的基础模型？他们解释说，事实证明，人并不会直接用‘代码’来跟这些模型沟通，而是使用人类的自然语言。因此，这个模型必须理解人类在语言中所蕴含的丰富经验。这意味着，要建立一个编程模型，你实际上是在开发一个前沿的语言模型，而这是极度困难且昂贵的。同时，其他公司做插件的路线在面对‘自动补全（Tab-complete）’这种更高级和需要深度整合的体验时，往往会遇到瓶颈。

所以，在我们看来，他们的每一个决定都是经过深思熟虑的。同时，他们也高度关注产品本身，这在 AI 圈子里其实并不常见。他们由衷地相信，只要能做出极度优秀的产品，产品本身就会被用户自发采用。这种理念和埃隆·马斯克 (Elon Musk) 的想法非常相似。

这也决定了他们的很多商业决策。比如，如果你真正相信产品，你就绝对不会去做插件，因为做插件意味着你只是别人产品的一部分；如果你真正相信产品，你不会在很早期就去铺企业级销售，而是会放在后期，因为优秀的产品本身就是最强的市场推广（Go-to-market）武器。

马特，不知道你是否同意，当时他们对于自己是什么样的一家公司、要做出什么样的决定，有着极度清晰且一致的认知。而相比之下，我们见到的许多其他公司更像是一种大杂烩——‘我们把这些都试一遍，我们也不确定什么能行。’ 他们一会儿做插件，一会儿做咨询服务，一会儿做其他东西。而 Cursor 是一以贯之的纯粹产品公司，在解决他们认为纯粹的产品问题。

<details>
<summary>Original English</summary>

**Matt Bornstein**: They actually had a very reason articulation for why where they were in the design space makes the most sense. So for example um why wouldn't you build a coding specific foundation model. So what they said at the time uh was it turns out that you don't speak to these models in code. You speak to these as humans and natural languages. Therefore the the model has to like understand like the the breadth of human experience in language, right? And so you know that means in order to build a coding model you're actually building you know a frontier language model and that's just a very hard thing to do. And then of course you know there are other companies doing it and there much more focused problems like t complete to do. So I think every one of their decisions was was very reasoned in our opinion. Um they were also very product focused um which you actually don't see a lot in AI. So they they really believe that you can build a product, the product, you know, if it's really good will be adopted, which by the way is very similar to how Elon thinks. um and that dictated a lot of their decisions. Like if you really believe in the product, you would never do a plug-in because then you're part of somebody else's product. If you really believed in the product, you wouldn't do enterprise early, you do it later because the product itself is the kind of go to market motion. And so there was a I would say and and Matt let me know if you would agree tremendous clarity on exactly what type of companies they the type of company they were and the decisions that they said or uh were all fell from that consistently right where many of the companies we saw were kind of these pastiches of we'll try all of these different things we're not quite sure what's going to work you know so their plugins and their services and their whatever whatever whatever this was a product company going after what they considered to be a product problem.

</details>

**马丁·卡萨多**: 是的，完全正确。而且我认为他们拥有追求极致产品形态的雄心和勇气。作为创始人，我们都想有野心，把帕累托前沿推到极致，但你必须知道前沿曲线的形状。他们非常清楚这条曲线的走势，并没有被非产品层面的事情分心。

我记得，在我们努力说服 Cursor 团队接受我们投资期间，我曾问过 Michael 他工作之外有什么爱好。他好像完全无法理解这个问题。他一脸困惑地问：‘你什么意思？’ 我说：‘就是你不在办公室的时候做什么？’ 他还是那副表情：‘我不懂你在说什么。’ 

我还记得在达成投资后我们共进午餐。当时我谈到了互联网早期的类似情况，Michael 看着我说：‘当时我才五岁。’ 我们大家都笑坏了。

但令人赞叹的是，不仅是 Michael，所有的联合创始人虽然非常年轻，但他们都是这些历史的资深学习者和研究者。这种特质我们在许多顶尖创始人身上都能看到。他们能够以极高的效率去研究并吸取前人遭遇的教训。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. No, I think that's exactly right. And and and I think they had the ambition and the courage to kind of do the maximal form of what the product would look like, right? Like I think, you know, as founders, we all want to be ambitious, right? And we want to like push like the to the maximum point the paro frontier, but like you have to kind of know what the curve is. And they and they and they just kind of knew what the curve was, right? And didn't get distracted by the by the sort of non-product things. Um, I remember uh I when we were trying to convince the cursor team to let us invest in their company. Um, uh, I asked Michael once what he did for fun like outside of outside of work. And I was like, he didn't understand the question. He's like, what do you think? Like I'm like, when you're not in the office, he's like, what do you mean? You know, I al I also remember by the way when we had the lunch after we did the investment and you know I was talking about something about like like internet days that were similar. He was like, I was five and we're like, but but like I mean what's amazing about not just Michael but all the founders is like even though they were pretty young when a lot of these things happened like they actually were kind of students of of all this history which is a trait that we see Alex Trampel talks about this a lot. We see this across all of our top founders that they're like able to study and really learn from what's kind of happened before.

</details>

### 从 Series A 到 Series B 的垂直起飞

**马丁·卡萨多**: 我想把这个问题抛回给你，莎拉。对于我们早期投资团队来说，当时投资 Cursor 的决策其实非常直接：团队极其优秀、极其专注。我们团队里有一半人本身就是 Cursor 的深度用户。你还记得安德烈·卡帕西也发推文赞美它。它显然已经成为了一种现象和知名品牌，用户增长曲线呈现出近乎垂直的渐进增长。

所以作为早期阶段的投资者，这非常简单。但对于成长型（growth）投资者来说，这通常是一个不那么显然的决策。你在第一场会议上听到的东西可能会与典型的成长型投资评估逻辑产生冲突。但你非常快速地领投了下一轮（B轮）。能不能跟我们聊聊，你是如何突破传统成长型投资的评估框架，并在极短时间内确立极强信念的？

<details>
<summary>Original English</summary>

**Martin Casado**: Um I'm going to turn the question back on you. Um I I think Matt would agree for for us the decision to invest in cursor at the was actually pretty obvious. Um the the the team was phenomenal. It was incredibly focused. All of us were users. Um like we you know like half the team actually used cursor. Uh you remember Andre Karpathy was using it. It was clearly a phenomenon. It was clearly like a known brand. the growth was asmmptoic. So from an early stage investor is a pretty straightforward decision. It was a much less obvious decision for a growth investor. And so like I think probably what you heard in that first meeting maybe was a little bit dissonant with how you'd growth invest but then you very very quickly led the next round. So maybe talk through how you kind of like got past the typical growth evaluation and and got conviction.

</details>

**莎拉·王**: 是的，这里的整个时间线压缩得太疯狂了。现在回想起来都觉得不可思议。我记得你们是在 5、6 月份（初夏）领投了 A 轮，而到了 10 月份，我们就已经完成了 B 轮。这显然是垂直起飞的态势。

那年夏天发生了几件事。你们提到安德烈·卡帕西发推文推荐他们，然后他们上了 **Lex Fridman** 的播客，对未来编程的愿景进行了极其深刻的探讨。这又回到了 Martin 刚才说的一点：他们是在重新想象一切。

但你不能用传统的成长型投资备忘录（growth memo）来套用这样的公司。你必须打破常规。

<details>
<summary>Original English</summary>

**Sarah Wang**: Yeah, I mean I think the timelines are so compressed here. It's crazy to think back on because I remember you guys led the A in May, June, right? early summer and by October we had done we did the B and so it was clearly just vertical liftoff and there were a couple things that summer right you you guys talked about Andre Carpathy tweeting about them but they went on Lex um incredibly thoughtful uh discussion of how they thought about their vision for like coding going forward um and so I think it comes back to Martine something you said which is they were just reimagining everything right and you you know you just talked about this as well Matt I um but you can't you can't write growth memos that way. Like

</details>

**麦特·博恩斯坦**: 别管备忘录了，你当时被这个项目深深吸引了。你一直在给我们打电话，所以你是怎么说服大卫·乔治 (David George) 他们的？毕竟成长型投资通常需要看极其严谨的业务指标支撑。

<details>
<summary>Original English</summary>

**Matt Bornstein**: never mind you. So you know you got the bug you know cuz you were calling us and we were so how did you convince David George like don't you have to show like you know

</details>

**莎拉·王**: 是的，这真的很有趣，因为面对这个案子你必须打破常规。虽然当时的用户增长势头是近乎垂直的，但他们打破了太多传统商业常识。

我记得 Martin 第一次把我介绍给 Michael，我们在那天一起喝了杯咖啡。Michael 他们的动作极快。我为他们整理了一些关于公司下一阶段成长画像的材料，试图向他们展示：成长型阶段的商业化路径是什么样的。

但我们提出的很多所谓的‘行业共识’被他们直接击碎了。例如，我们说：‘我们可以帮你物色一位销售负责人。根据历史经验，当自助服务（Self-serve）的自然增长在 2500 万到 5000 万美元 ARR 开始放缓时，引入销售高管是极其合理的。’ 

Michael 盯着我的眼睛，平静地回答说：‘我们的自助服务不会放缓。’ 

当你把这些变量拉进财务预测模型时，你会发现所有传统的假设都失效了——你不能假设他们在五年后会像常规 SaaS 公司那样增速放缓到 25%。所以，当时做成长型投资决策的核心，就是主动抛弃一些我们过去用来评估常规软件公司的历史假设。我非常庆幸我们当时有勇气这样做。

<details>
<summary>Original English</summary>

**Sarah Wang**: Yeah. You know it's so funny because and I think you had to think out of the box for this one. I mean, of course, the the momentum was vertical, but there were so many things that they defied conventional thinking where I remember I the first time, you know, Martin, you introduced me to Michael, we got a coffee that day, you know, as Michael, you know, they move quickly. Uh, so I pulled some stuff together for them, right? Because we're um, you know, we're trying to show them, hey, this is the next stage of what growth looks like. And there's so many conventional pieces of conventional wisdom that they just completely broke. Like we would say, hey, we'll help you find a sales leader because, you know, previously it made sense to start layering a sales leader at 25 to 50 million of ARR when self-serve starts to peter out. Michael looks me dead in the eye and it's like self-serve is not petering out, right? And so then you start to pull these drivers that you're like, oh, these assumptions that would go into any growth model historically, you can't have that asmmptoing at 25% growth in five years, right? And so I think a lot of the growth investment decision at the time was throwing out some of the assumptions that we would typically make on how a company would, you know, eventually start to slow growth. Um, I'm very glad that we did that. Um, and then the second piece is we should talk about the competitive landscape, right? Because you mentioned co-pilot. I was I was actually going to say and actually I I think Matt deserves a ton of credit here which is we talk about now in retrospect how it was a pretty easy decision on the series A but you know you know Matt Matt Matt led the early deal and he saw something uh a lot of people didn't which was this which is if you looked at the competitive landscape it was almost silly which is you had a large incumbent which is Microsoft that had a company at scale that had the open weights and they own VS code so everything you know everything would say that there's just no way that you could survive relative to this this this one single competitor. We'll talk about the other ones um later. And I and I think that also was one thing you said about Michael was what I witnessed. It' be great to hear Matt, which um and I even remember when Matt said this early on, he was like, you know, they have a good answer for everything, which when you have founders that are students of what they do, they're very consistent in their answers. Um, and you know, and this this is not listen, I I think when we did the deal, it was pretty obvious, but it wasn't so obvious six months before. Uh, you know, and Matt and the team had that deep conviction way back then. And I think for every one of these races there there are mirrors of that. Anyways, is this

</details>

### 与微软及 Anthropic 的多维度竞争

**麦特·博恩斯坦**: 是的，确实如此。人们常常觉得风险投资是一项个人运动，但事实并非如此。我们整个团队当时都在全力以赴地推进这个案子。在长达一年的时间里，我们内部实际上专门成立了一个‘Cursor 专案组’。

而且，这些家伙聪明得近乎离谱，纯粹的智商极高。他们能够在技术深度和商业格局之间进行无缝的上下文切换，极其敏捷地吸收各种市场数据并迅速做出反应。

但在当时，面对微软的竞争确实让人觉得疯狂——你要去分叉微软拥有并主导的 VS Code，还要在微软拥有 OpenAI 权重、拥有庞大的企业级销售队伍和有史以来最强企业分销渠道的背景下，用更小、更精干的模型去和他们竞争？微软拥有超过一亿的用户，几乎掌控了整个生态链的每一个环节。

按常理推断，这种竞争根本没有活路。但我们一直倾向于在大市场中把赌注压在最具实力的独立开发者工具上。即使对手看起来非常庞大和可怕，独立的工具往往能凭借极致的专注赢得用户的偏爱。

<details>
<summary>Original English</summary>

**Matt Bornstein**: Yeah, totally. And look, I mean, people think venture capital is like an individual sport. Like, it's not at all at all. I mean, our whole team was working working on this at the time. Um, you know, I think it was over a year. We literally had a cursor team on our team like within our team. Was great, Ro was great, you know, you you led the team. I mean, it was So, but but yeah, no, you're exactly right. I mean, I I mean, these guys are crazy smart, right? They're like off the charts sort of just just raw intelligence. Yeah. um they're able to do this thing we talk about a lot like context switch between tech and markets um really really seamlessly and and and um they like in ingest data right whether it's historical data or like things happening in the market and act very very quickly which you which you said before Sarah but spec but spec I agree with that but specifically it was just kind of crazy to think you're going to fork something from Microsoft who owns the thing and then you're going to you know compete with them with smaller models Even they own the opening eye weights and they have enterprise sales force and they have greatest yeah enterprise distribution ever you know it's so interesting right it's it's like they have 100 million developers they own everything they literally own every piece of that like you know it's it's so interesting right because like that's definitely the conventional wisdom and like it's usually correct the conventional wisdom in many of these cases um you know one of the data points at the time was it was actually um Marco on our team set up a dinner where Aman John sat right next to John Schwman and um they talked like a lot about cursor and I I think John's thing was like oh yeah I tried cursor but like our code base I think he was at anthropic at the time like our our like monor repo just like immediately killed it right it's like I couldn't even load the code base and and like I think like the next day Aman came back he's like oh we made some changes like here you can and not only is like speed of iteration but like you know we just look for these little data points where it's like like actually like doing a plugin or or just like writing on top of VS Code is not is clearly not going to work because like the smartest people in the world have tried it and it doesn't work right so it's like so these guys were sort of listening to and and historically we as a team have always bet on the independent in in a large market right if there's a leading independent we'll always bet even if the incumbent seems very scary I do think it's worth talking about competition because my you know my experience with all of our experience with cursor is that there was always like a looming existential threat and we almost forget about it. But like you know, of course, Copilot was the big one and then remember the whole Windsurf thing. So like Windsor actually did this very smart thing where they went to YC and there was a lot of YC users using it. So you kind of had this kind of whole movement on Windsurf um and you know Cognition was a phenomenal company actually was making real waves with agents and they've done a great job with that. And then you had the first version of cloud code um that came out and like that was kind of like a you know uh a competitive thing and so like you kind of go through like there was always some competition and and one thing I would say and I would love again to actually hear your perspective on is like it is such a pleasure to work with founders that are entirely unfased.

</details>

**马丁·卡萨多**: 是的。通常情况下，当面临巨大的竞争压力或突发事件时，很多创始人会陷入焦虑并频繁打电话寻求安慰。但他们完全不为所动，保持了 100% 的冷静。他们虽然保持了高度的警惕与偏执（paranoid），但始终极其沉着（unfazed）。

我们很幸运参与了他们从 A 轮开始的每一轮融资，并且随着时间的推移，我们投入的资金规模越来越大。莎拉在 B 轮和 C 轮中展现了极强的信念。说实话，说服合伙人团队投资 C 轮是一次更为艰难的对话。在 B 轮时，你还可以凭借垂直上升的强劲势头轻松过关——毕竟，谁能在短短四个月内就实现从 400 万美元到 5000 万美元 ARR 的暴涨？

<details>
<summary>Original English</summary>

**Martin Casado**: You know like normally like you know founders have this things happen are calling and they're kind of freaking out and whatever. Um they were 100% unfazed by the competition. Yeah. Paranoid but unfazed. I'll never forget um you know and we we we've been lucky to do I think all of all of their rounds starting from the A. Um but the one we invest in every cursor around we did. Yeah. With I think increasing amounts of dollars. But um Sarah Sarah coled the B and the C. That's real conviction. That was a harder conversation to convince the team for the C. you know, at at the B you could argue, God, just bet on vertical momentum. obvious the who grows from four to 50 in like four months or whatever, but this the um or actually no, it was it was the D. So Claude Code, not to take us on a time travel trip again, but Claude Code came out May 2025 um with a splash. You know, it wasn't the pickup wasn't right away, but obviously formidable. Um and I remember there was around um I think a couple months after three months after that and I asked Michael I was like what do you think about Claude Code and he said something to the extent actually you know exactly what you're saying here which is look we are going after the biggest market in the world there's going to be competitors in fact there's been a rotating cast of characters from the very beginning co-pilot Microsoft co-pilot was the first one cla code is one of a rotating set of characters and you know we think in big markets you're always going to have formidable competitors that does not scare us um and you know I just remember being somewhat blown away by the clarity of that comment um the lack of fear right there's there's humility as well like it's humility mixed with bravado and I just think that is kind of the winning combo when you're going after these juggernauts like that

</details>

**麦特·博恩斯坦**: 是的，虽然这听起来可能有点抽象，但这就像是杰夫·贝佐斯 (Jeff Bezos) 式的风格：如果你足够聪明且确信自己是正确的，在面对巨头竞争对手时，这种心态能赋予你极强的定力和专注度。

不过，他们并非没有面临过真正危急的‘惊吓时刻’，但这些时刻几乎都与模型的底层演进有关。比如，你还记得 **Claude 3.5 Opus** 发布的时候吗？当时大家都在度假，突然之间，全世界的人都在惊呼：‘天啊，底层模型的迭代速度比我们想象的要快得多！’ 还有 **GPT-5 (Mythos)** 的预发布版本出来、人们开始拿到测试权限时，大家也感受到了巨大的冲击。模型的发展速度太快、表现太好了。

我认为 Cursor 团队在这一过程中非常了不起、但可能没有获得足够赞誉的一点是：他们在短短两年时间里，以极其果断和决绝的方式，完成了好几次‘自我革命（cannibalization）’。这非常像里德·哈斯廷斯 (Reed Hastings) 领导 Netflix 转型时的魄力。

他们起初是一个 IDE 平台，然后迅速转型为 Agent 平台，接着又跨越到了模型层。对于一个初创团队来说，能有这样的战略纪律和自我否定的勇气，是非常罕见的。

<details>
<summary>Original English</summary>

**Matt Bornstein**: and I know it sounds vague but like things like this it just it's it's almost a baso Bezosish thing which if you're smart and right like it actually like gives you I think the confidence and the focus to to like have that kind of attitude when you when you have this like mega competitor sort of coming after you. Yeah. Then I'll say I will say they were definitely a couple of oh [__] moments but they were always around models. Like remember when Opus 45 came out? Like we're all on vacation and I think everybody in the world class was like oh [__] all that's true. you know, these things are moving much much faster um uh than any of us thought. And then I think the same thing when the pre-release of Mythos came out and people had access to it. These models were getting so good so fast. And I think another thing that the cursor team probably doesn't get, you know, the the level of credit for um is to the extent they cannibalized themselves so dramatically in like a Reed Hastings type way in a matter of two years, right? So they were first an IDE and then they you moved to an agent platform then they moved to a model platform and it's very very tough for you know founding teams to actually have to discipline.

</details>

### 极致自我革命与商业化模式的跨越

**马丁·卡萨多**: 当年安德烈·卡帕西那篇著名的推文指出了‘Tab、Tab、Tab’（自动补全）在未来的局限性。当时大家突然意识到，那种单纯的代码自动补全在未来可能变得不那么重要了。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. Tab was the big thing when we you know Karpathy had that famous uh post. I guess he has a lot of famous posts where he's like tab tab tab. Yeah. Exactly. Like that kind of doesn't matter that much anymore.

</details>

**莎拉·王**: 是的，这正好引出了他们沿途所做的一些关于商业模式的重大战略决策。

关于那些‘惊吓时刻’，我不确定他们自己是否会把这些看作危机，因为他们似乎不太受社交媒体（如 Twitter/X）上各种舆论的左右——我们这些投资人反而天天在上面刷个不停。

在 2025 年夏天，网上有很多文章质疑他们的毛利率（gross margins）等等。还有在 GPT-5 (Mythos) / Claude Opus 发布后的阶段。这些都是非常不同但极具挑战的时期。

<details>
<summary>Original English</summary>

**Sarah Wang**: Yeah. I actually think that's a good segue to maybe some of the other strategic decisions they made along the way um around business model and um to your point on oh [__] moments I don't I don't know if they would consider this that because I don't think the vagaries of Twitter impact them as much um as their as the investor yeah as the rest of us just like scrolling all day but um it was probably summer of 25 uh where there There's a lot of [__] written about their gross margins, etc. And then of course, you know, post the Opus 45 maybe Janu January period. I mean, we should all talk about that because that was kind of those are both different but interesting times.

</details>

**麦特·博恩斯坦**: 是的。我总觉得 Twitter/X 上的舆论主要是被多巴胺、肾上腺素和幸灾乐祸的情绪所驱动的。人们在网上说的话与商业世界的真实运行情况之间，往往存在着巨大的脱节。尽管网上有很多杂音，但他们的业务实际上发展得非常好。

令人惊奇的是，许多关于业务质量（business quality）的讨论往往都源自投资人。但历史规律表明，**技术变革总是发生得比商业模式的清晰化更早**。

如果你们还记得互联网早期的发展，我们在很长一段时间里甚至都不知道该如何通过它来变现。先不要谈毛利率了，当时甚至连如何赚钱都没想明白。而在这里，你拥有的是近乎无限的用户需求和爆发式增长。

所以，网上的那些讨论只是人们为了显得自己聪明而进行的无谓审判，去挑剔一个处于萌芽期的颠覆性技术的商业模式。事实证明，这些质疑者每次都被证明是错的。

<details>
<summary>Original English</summary>

**Matt Bornstein**: Yeah. I mean, one thing else I uh is I just feel like X is driven by like tail chasing adrenaline sinking in shot and Freud and there tends to be a massive disconnect by what people say on X and like how the business is actually doing and so even though there was a lot of this the business tended to do very well and it's so interesting is so much of this often comes from investors especially things talking about like business quality But text transformations always precede figuring out the business. Like if you guys remember the internet, like we didn't even figure out how to monetize it for a long time. Forget margins, making any money at all, right? And here you've got like unlimited demand, unlimited growth and and margins. So, you know, I think this tends to be, you know, a e exit its own kind of echo chamber as people say it, but also b every single wave you have investors trying to say something that sounds smart, which is like picking apart, you know, the business model of a nent tech transformation and I just think historically they've always been proven wrong.

</details>

**麦特·博恩斯坦**: 引用 Martin 之前说过的一句话：先是技术变革，然后是商业模式的成熟。

在 Cursor 的案例中，他们的战略非常清晰：先在创纪录的时间里获取所有核心用户。现在，他们拥有了庞大的用户群、数据资产和模型开发的技术诀窍。他们已经有能力在此基础上构建自己的闭环模型。

如果不以极致的产品作为切入点来汇聚海量用户，你是无法完成这个反向飞轮的。这种‘后门突破（backdoor）’的战略非常令人振奋，尽管他们在早期为此承受了很多外界对于毛利率的指责。

<details>
<summary>Original English</summary>

**Matt Bornstein**: Yeah. Yeah. For sure. I mean I I you know I think I'm going to borrow this quote from something you said Martin but you know first comes the technical transformation then comes the business model and in this case like I think the the strategy where they went and got all the users in record time now they have the assets the data the knowhow etc to build their own models right you really couldn't do the flip of that unless you started as a frontier lab um and it you know it's clearly paying off in this combo that we'll talk about later. But um I think seeing that kind of kind of backdoor strategy um was really inspiring and they they took a lot of heat for it.

</details>

### 世界级的企业级销售跃升与独特招聘哲学

**马丁·卡萨多**: 那么，莎拉，你认为 Cursor 是如何转型成为一家极其擅长销售和市场拓展（GTM）的公司的？

在早期，我记得跟 Michael 建议过好几次：‘你们应该开始投资销售团队了。’ 他总是回答说：‘不，我们不打算做那个。’ 

当时他们只是极其简单地在官网上挂了一个 `enterprise@cursor.com` 的邮箱：‘如果你是企业客户，请发邮件到这个邮箱。’ 

但现在，他们显然已经构建了极其强大的企业销售能力。他们是如何完成这级跳跃的？

<details>
<summary>Original English</summary>

**Martin Casado**: So Martine, how do think Curser really became a salesdriven company or or a company that's good at sales because you know early on I think I I told Michael a few times too. It's like oh you better invest in sales. He's like nope not going to do that. They literally set up enterprise atcursor.com. It's like if you're an enterprise, send your inquiries to this. But but like but obviously now they're very good at sales, right? And and and or go to market in generally like how how do you think they made that jump?

</details>

**麦特·博恩斯坦**: 这确实是个极好的问题。以我的观察，这归结于他们对于自己所做的任何事情都秉持着极其严谨的‘研究者’心态。无论是一次融资，还是一次重大的产品决策，他们都会像做科研一样去彻底解构。

当他们深入研究市场后，他们意识到丰厚的利润率存在于企业级市场。常规的大模型厂商为了竞争，往往会选择对个人用户层级进行限制甚至收费，但底层模型层竞争又使得个人用户价值摊薄。但当规模扩大后，企业级客户能够贡献极高的利润和商业价值。

所以，为了公司的长期商业可行性，必须切入企业级市场。那里不仅是预算最集中的地方，也是溢价空间最高的地方。既然他们已经通过优秀的产品构建了极佳的漏斗顶部（top-of-funnel）流量引擎，进入企业级市场就成了顺理成章且至关重要的下一步。

一旦他们下定决心做这件事，他们就会毫无保留地全速推进。这可能是科技行业历史上搭建起最专业、最高效的销售团队之一的过程。莎拉，你在销售人才的招聘上深度参与了，你可以具体聊聊这个扩张过程。

<details>
<summary>Original English</summary>

**Matt Bornstein**: Yeah, it's it's a great question. So here' be my best guess. Um which is they they are very much a students of whatever they do. They're very thoughtful every raise, you know, um every product decision. Um and I I think as they learn more about the market, they realize that the margins were in the enterprise. So very classically if you view your competitive set say the large labs the large labs will basically subsidize or give away the single serve tier. Um but then they actually have they command great margins in third party and they command greater margins in the enterprise and you know is really at scale and and as the company has always gone they decided okay like so you know for future viability we need to go into the enterprise that's where a the bulk of the spend is but also a lot of the margin the margin tends to be the value here. we've created a great you know top offunnel engine and so um you know this is existential and this important and then when they decided to do it they really went in and that's the f that may be the fastest grad of a sales team in the history of the planet right I mean um I mean you know you were you were very involved Sarah for example on recruiting so maybe talk about that actual expansion because it was it was

</details>

**莎拉·王**: 是的，这印证了那句名言：‘你做任何事情的方式，就是你做所有事情的方式。’ 

他们在招聘和市场拓展人才上的思考，完全折射出了他们做产品时的严苛标准。在这里我们必须向 Jordan、Roman 以及他们的整个团队致敬。他们从零开始，亲手打造了这个极其强大的商业引擎。他们是我合作过的最优秀的一群人。

此外，创始人们也拿出了极其夸张的精力——他们会将 40% 的时间花在招聘上。

<details>
<summary>Original English</summary>

**Sarah Wang**: yeah I mean it's um it's so neat to see you know that expression how you do anything is how you do everything. You you really see it. So much of what you guys are talking about and how they thought about product etc. um was reflected in how they did hiring and go to market hiring in particular and we got to shout out Jordan and Roman and their their team there who in the early days built that that engine from that that engine from scratch. They're just the most incredible you know some of the most incredible people I've ever worked with. Um but we've all ever worked with and um

</details>

**麦特·博恩斯坦**: 对于以技术和产品见长的创始人来说，能够坚持将 40% 的时间投入到招聘中，这简直令人不可思议。我以前从未在其他公司见到过这样的执行力度。

而这种高投入带来了极其显著的成效。公司的本质就是你所建立的团队。他们将这一原则贯彻到了极致。这与常规的靠猎头广撒网的招聘方式完全不同。

我记得 Oscar 当时频繁地坐红眼航班飞往欧洲，去亲自说服并敲定一些核心候选人。这种高强度的招聘节奏是持续不断的。

<details>
<summary>Original English</summary>

**Matt Bornstein**: well they all they also spend 40% of the time recruiting. Which is amaz which is amazing for for for technical product founders to spend 40% of the time recruit. I've never actually seen it before. Absolutely. And it is so effective and like a company really is the team that you build and they took this to heart. Like everybody talks about it. Everybody talks about like doing a class route. It's entirely different where it's like how often was Oscar, you know, hey, I'm on a redeye to Europe to close some like literally like ice near it was constant.

</details>

**莎拉·王**: 是的，大家都应该去读一读关于他们独特招聘实践的文章。

虽然很多内容关注的是他们如何招募天才技术人才（比如工作学习制等），但他们在招募一线客户经理（AE）时的深思熟虑也是前所未有的。

他们会对候选人进行极其深度的背调。我们会和他们一起在办公室坐上 8 个小时，逐个分析候选人的资源与背景。

他们并不想沿用老旧的模式去招人，而是清楚地知道：‘我们要以全新的方式来建立这家公司，所以我们需要具备特定画像（profile）的 AE。我们会主动锁定并说服他们加入，而不是坐在办公室等着别人投简历。’

这些在技术和 GTM 端的极致人才战术，最终带来了极其惊人的商业结果。他们在创纪录的时间里，成功渗透到了超过 50% 的《财富》500 强企业中。这比我们见过的任何软件公司都要快。

<details>
<summary>Original English</summary>

**Sarah Wang**: Totally. And you know, there was that great piece that Bri wrote about their hiring practices that everyone should read. Um, a lot of that focuses on their edge hiring, like the work study, all this stuff, right? But even on the go to market hiring when the thought that they would put into hiring a single AE, right? And of course, like this is nothing new, but just the back channel, back channel, back channel ethos, they had that to a tea. They knew exactly what they were looking for in founding AES. You know, I remember we would go there and sit in their office for eight hours helping them source stuff like that. And they weren't like, oh, we want to do it the old way. We're like that that's not going to we're building a company in a new way, right? So, we want very specific AES that um fit this profile. We're going to go get them. we're not just going to wait for people to walk in the door. All of those things that have been written a bit on the edge side, they did that on the go to market side and clearly to phenomenal results. I mean, they got to over 50% of the Fortune 500 and I think faster than anyone we've ever seen.

</details>

**麦特·博恩斯坦**: 你们能不能具体聊聊，他们是如何将技术人才招聘的成功经验，迁移并应用到销售人才招聘上的？因为很多创始人都在这个问题上感到头疼——如何完成从招程序员到招销售的跨越？

<details>
<summary>Original English</summary>

**Matt Bornstein**: Can you talk about specifically how they applied the lessons in hiring to to like AE hiring because this is something I think our founders deal with a lot like like you know I you know dealt with this a lot personally like like like how how do you actually make that jump and like what what lessons really do carry over? Or or that you observe in person.

</details>

**莎拉·王**: 好的。虽然这听起来不是什么绝对的商业机密，但他们会去深入分析一个人职业生涯的每个历史阶段，去印证究竟是谁在关键的战役中发挥了核心作用。

他们会进行极度细致的背景调研：‘这是这一赛道中最顶尖的 10 家销售驱动型公司，让我们再深入一层，找出这些公司里最优秀的 10 个团队，然后锁定直接推动了这些业绩增长的、排名第一和第二的核心 AE。’ 

然后，他们会发起密集的交叉背调：去询问候选人的前主管、主管的主管、甚至主管的主管的主管，直到多方交叉证实‘这确实是一位现象级的 AE’。

同时，在早期，他们非常看重候选人处理‘不确定性’的能力。因为在 GTM 模式尚未完全固化的阶段，你不需要一个只会照本宣科执行既定销售手册的人，而是需要能够探索边界的开拓型人才。

正是因为 Jordan、Roman 和早期团队在招聘画像上的精准把控，他们才得以在不稀释 Cursor 独特团队文化的前提下，实现了商业化团队的超常规扩张。

<details>
<summary>Original English</summary>

**Sarah Wang**: No. Yeah. And and you know hopefully I think this has been written about so hopefully it's not sharing alpha but the way that they think about sort of epochs of a person's career or of a company and who was the key dial in making that happen. I love this intense research period that goes on where it's like hey this these are the top 10 companies who have seen great in this type of selling and then let's go a level deeper. Here are the top 10 teams within those companies and then here are the one and number one and number two single AES who drove that change and accounted you know again back channel back channel back channel right like who their boss their boss's boss and their boss's boss's boss would say this is a superstar AE and of course in the early days it was like can they deal with some uncertainty because you don't want someone who can just run a playbook at this point maybe they can get those people but in the early days right the founding AE set was super strong and I think figuring out what does the best look like at what period of time and then which individuals drove that that's so applicable for engineering obviously product building but on the go to market side as well and um I think that nailing the right star who did it at the right time is really hard I mean it narrows the base that you can hire from completely but because you know I think Jordan Roman and the early team got that right they just were able to scale it quickly without losing the cursor culture

</details>

### Cursor 的极客办公美学与“终极 M&A”

**马丁·卡萨多**: 外界对 Cursor 的文化有很多讨论。我想听听你们对他们文化的直观感受。

我之前的印象是，他们完全被写代码和构建系统这件事情占据了。这并不是因为他们有自虐式的加班狂倾向，而是因为他们发自内心地热爱编程、热爱系统设计。我们三个人有时也会有这种单纯的技术热情，所以非常能感同身受。这种极客精神成为了他们团队最核心的文化驱动力。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah, which you know a lot's been written about the cursor culture. I'm curious, you know, maybe you guys can share your own um impression of it. You know, I I mentioned earlier that like you know, kind of coding was all that they did. It my impression at the time and and like we you know, the the the founders could could correct us on this like my impression at the time is they weren't doing that because they're obsessed with work and I think they're still not doing it because they're obsessed with work. literally just like love writing code and love systems and and like I think the three of us sort of you know can feel that way at times too right like that that's like a very very understandable thing and that seemed to be the driving cultural you know kind of impetus at at at the time is a very small team everybody had that had that attitude and like we're orienting towards the future of like what is this actually going to be and that kind of like you know from an edge standpoint and a product standpoint like very narrowly focused on what they were trying to accomplish and like how how to run the team

</details>

**麦特·博恩斯坦**: 但这里存在一个巨大的悖论：如果你去审视他们后来的实际行动，你会发现他们把大量的时间投入到了非纯技术的事务上——招聘、商业化模式的探索、市场拓展、甚至是复杂的商务拓展（BizDev）和并购。

一个纯粹的产品极客团队，在面临公司发展的关键节点时，能够毫不犹豫地将精力转移到商业化所必需的每一项重度任务上，这体现了极强的务实精神和商业适应力。正是这种能力，帮助他们成功穿过了软件行业历史上竞争最惨烈的红海。

想象一下，你一上来就跟微软直接竞争，接着又要在正面战场与 Anthropic 这样的超级独角兽交锋。这些巨头拥有近乎无限的算力、资金和分销垄断地位。在短短两年内，你不仅要在产品上不断自我革命、重塑 GTM 模式，最后还要主导和执行科技史上最复杂的并购（M&A）交易。这太不可思议了。

<details>
<summary>Original English</summary>

**Matt Bornstein**: but there's This is a huge paradox cuz I totally agree. I 100% agree. However, if you actually detailed their actions later on, that's not the conclusion you'd get to like what do they spend their time on? It was like recruiting, go to market, understanding business models, bisdev. And so, in a way, again, I like just totally agree. And again, on one hand, you have a very product focused team that comes from the tech that literally wanted to build products that they that they wanted to use. Listen, I I think that high-powered founding teams work on exactly what is needed by the business and I think they did a very good job and I think it allowed them to navigate the most uh competitive market we probably ever see. Has there been a more competitive market than coding then? I mean, it's just it's hard to imagine. There's so many companies database wars. Yeah. I mean, you have very intense competition in like relatively narrow markets. I mean, databases are huge, but compared to coding, I actually think it's much smaller, right? like for like I mean coding is kind of the meta category right like like it's like all expression of like human thought in like economic form is kind of like coding I mean imagine like starting competing with Microsoft ending ending up competing with say anthropic you know both of these kind of you know mega companies with tremendous amount of capital and power and distribution in the meantime you evolve like ex like fundamentally your product approach and you change your go to market and then you engage in the most complicated M&A of all time and all in a matter of two years. Like I think this is so crazy, right? Like the magnum opus of like you know startup or just like totally

</details>

**麦特·博恩斯坦**: 是的。当被问及什么是娱乐时，他们的回答也是写代码。

但他们也非常清醒地意识到：要真正改变软件开发的未来，仅仅关在屋子里写代码是不够的，必须在商业战场上取得决定性的胜利。

他们展现出了超常的成熟度。例如，这种极致的品味（taste）和细节把控力，不仅体现在产品上，甚至延伸到了他们办公空间的布置上。

当你走进他们的办公室，你会看到挂着的氛围彩灯，以及著名的‘无鞋’规定——每个人都换上舒适的拖鞋，让办公室营造出一种舒适的家的氛围。这种北欧式的舒适设计（Hygge style），让团队成员自然而然地愿意长时间留在这里工作。

他们曾经在一个二手高端家具商那里精心挑选了一款特定的沙发，以符合他们对办公空间特定美感和调性的追求。这种对于‘气场’的塑造，对于激发团队的创造力和思维空间，起到了非常微妙且关键的作用。这实在不像是一个常规的 20 出头的年轻团队会去花心思打磨的细节。

<details>
<summary>Original English</summary>

**Matt Bornstein**: there's definitely something to what you're saying, right? Like in the beginning these guys were incredibly focused on the product and literally enriching their own lives. Like literally they would be coding for fun. Like when I finally got them to admit they did something for fun, it was like oh that's also coding. But like yeah which like which by the way is the only guilty guilty. Yeah, it's the only fun left to any of us by the way, you know, now that the models have like, you know, brought the post scarcity future to us. It's like coding is like, you know, the last fashion. Um, you know, and but but like there was always awareness or at least I always thought talking to Michael like he was always aware of the game if if that makes sense. Like like he truly was and they were all truly in love with coding and creating great products, but like they kind of knew that building an enduring company or great company isn't just about product obsession. And I just got the sense he always kind of understood that and and like was thinking a couple of Yeah. Listen, if your goal is changing software, that's a critical it's critical to get the business right. Yeah. Yeah. I was going to add an anecdote that's not related to um them coding, but the other thing that you know we've sort of seen across a number of founders, but Michael and Sale and Aman, they they sort of embodied this is this again how you do anything is how you do everything, right? And so of course this detail attention to the product very artisan there's craftsmanship right overused taste they have taste in spades but it extended to not only they did hiring on the edge go to market side but even the space they created the events they throw like I remember walking into their office and thinking wow in my early 20s I would not have paid attention to putting I don't know twinkle lights here they famously no shoes right but you'd go in you'd put on your slippers and it would feel you feel at home like hence why everyone was there working all the time because you're like this feels great like home and they um you know they it was very hege the Scandinavian style and I remember going to their second office when they finally um expanded and complimenting them on a couch or something cuz I think I was redoing my own house at the time and they were like oh yeah we got that from a secondhand like very hegeay uh furniture dealer and so they were going after a specific look and feel. And I just was struck by that because I was like, "Wow, that is not how I remember guys in their early 20s, like thinking about the space that you create and are in, how that leads to the product and, you know, mind space you're in."

</details>

**马丁·卡萨多**: 这也直接体现在他们的品牌和市场策略中。他们对于市场推广的发声方式极其克制与挑剔。

我们曾经提出过很多商业活动和推广的建议，但他们会明确拒绝：‘不，这不符合我们的调性。我们不想显得廉价或充满营销感（spammy）。’ 他们在说‘不’的战略定力上，再次展现出了极强的原则性。

在人员流转上也是如此。如果发现团队成员在文化或能力上不再契合，他们会以极快的速度做出艰难的优化决策。这种坚决和果断，也是埃隆·马斯克式的核心特质。

这种极高的执行纪律——一旦做出战略决策，就绝对不打折扣地彻底执行——是他们最隐秘也最强大的核心力量。无论是决定不去趟某些浑水，还是进行艰难的人员优化，他们都有着无与伦比的勇气与韧性。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah, there there's there's actually a nice adjacency here to a lot of the decisions they made. So, so marketing was a very obvious one. They were very very particular like we use X, that's not our voice. We're not spammy. We made so many suggestions. I remember we're like, "Oh, like let's do this event. No, that's not our style." Mhm. So they're very good at saying no for sub. Um I will say that they were also very good about this when it came to personnel. Like if if there wasn't a fit, they make the hard decision pretty quickly. Um you very very rarely see this with early founding teams and they they're very consistent about that. And so I would say it's almost this kind of untalked about probably greatest strength of the company is that once they made a decision it doesn't matter how hard that was whether it's deciding not to enter a market deciding to like be very limited in what they're doing like they kind of follow through or like you know uh who who would stay in the company who wouldn't stay in the company and so you know kudos to them for actually you know having the the the courage and the tenacity for these tough decisions which is sort of an Elonish trait. too.

</details>

### 终极并购与创始人集成艺术

**麦特·博恩斯坦**: 是得，这非常像埃隆。这也直接反映在他们最终与 xAI 的并购整合中。

从技术的层面上看，这是一次教科书般的完美结合：xAI 拥有极其庞大的算力资产，而 Cursor 团队拥有海量的开发者数据和最顶尖的交互入口分发渠道。

在愿景层面上，双方都坚信：软件和代码开发是通往改变人类计算形态乃至改变人类未来的必经之路。

在文化层面上，两家公司都极度推崇硬核的产品和工程文化，推崇极致的迭代速度以及果断快速的决策作风。我参与过很多科技行业的并购案，但这次并购的战略契合度绝对是我见过的案子里最完美的。

<details>
<summary>Original English</summary>

**Matt Bornstein**: It's also very Yeah, I I actually think that these these two company I mean we just like you know talk about the M&A a little bit um are very good fits are very good fits on on like a technical level right like Elon has a compute they have the distribution and the data um on a vision level they both think that you know code is the path to changing all of compute and maybe all of humanity uh but also on a cult culture level right they're very product engineering focused very very very um very product engineering heavy, very fast iterating, you know, they make hard decisions very quickly. And so, I mean, I've been involved in a lot of M&A and uh I would say this is probably the best fit I've ever seen as far as just the full package.

</details>

**莎拉·王**: 完全赞同。这让样我想起了我们在 SpaceX 上的早期投资经历。

我们是在 2019 年首次接触 SpaceX。在当时，外界普遍认为它只是一家纯粹的商业火箭发射公司。但 SpaceX 团队当时就坚定地告诉我们：‘不，我们要构建全球卫星通信网络，我们要为全世界的每一个人提供互联网服务。’ 当时天空中连一颗 Starlink 卫星都还没有。但最终，他们完全兑现了这一诺言。

Cursor 团队在许多关键的商业节点上，不仅实现了他们的预测，更是大大超出了我们的所有预期。在面临看似无法战胜的巨头竞争对手时，依然以令人难以置信的速度夺取市场并实现自我升华，这种特质在 SpaceX、Starlink 以及 Cursor 身上有着高度的映射。

同时，两家公司在发展历程中，都无数次遭遇过外界‘关于公司即将走向灭亡’的看衰与质疑。但两支团队在面对怀疑时所展现出的超强文化韧性与定力，是我最为敬佩的地方。

<details>
<summary>Original English</summary>

**Sarah Wang**: Yeah, couldn't agree more. I mean, there there's a funny analogy with our experience with on the SpaceX side. I remember we met them in 2019. Back then it was fully a launch business, but the SpaceX team was like, "No, we're going to launch global communications. We're going to power the internet for everyone in the world." They had no, you know, nothing at the time, no Starlink satellites in the sky. And of course, they they did it right. And if you think about the Cursor team, um, telling us and, you know, they actually beat every forecast they ever gave us. But, oh, by a lot. There's just so many Elonish characteristics of moving fast, going after large markets, winning them in the feet of impossible competitors, you know, Comcast, right? Right. in in the Starling case um that there's so many parallels totally different venues obviously but um fascinating to see that there's another thing I would say also um which I think between kind of Elon and and and cursor like SpaceX and cursor is like in both cases the consensus was decrying the death of both companies so many times you know so I think there's also like this kind of like you know cultural perseverance to the naysayers which I I actually really respect on both sides.

</details>

**莎拉·王**: 我还想探讨关于 Cursor 团队在开展小规模并购（M&A）及合并其他创始人团队时的哲学。

在当前的 AI 行业中，人才争夺战已经白热化。那些能够高效通过‘并购/并购式招聘（acqui-hire）’来吸纳顶尖工程与产品人才的公司，将获得巨大的战略优势。

Cursor 很早就启动了这种动作。他们从不担心所谓的管理或运营复杂度：‘我们不在乎整合的过程会有多繁杂，我们只在乎能不能把最优秀的人才带进来。’ 

因为他们对自己的团队文化有着极强的信心，相信自己能够将任何新团队迅速融入并同化。在后期，比如对 **Graphite** 的并购，则体现了更为深刻的商业模式与战略互补思考。

他们对于如何将其他初创公司的创始人（Founder）吸纳并委以重任，形成了一套极其独特的打法。

<details>
<summary>Original English</summary>

**Sarah Wang**: Actually, I do have one other real question I wanted to ask you guys. Cursor is also really good at doing M&A like like doing me. Yeah. Yeah. Yeah. I would love to know a little bit more like from your perspectives like why why they were and what the philosophy was and all that. Um so I will say listen so uh there is such a war for talent um right now that the companies that have figured out how to do uh talent via acquisition can really get ahead. I mean there's just a lot of advantage there. And so the early motions that they did were of of that nature which is like really good team you know they'll just go ahead and do the acquisition. And what was really nice about Cursor, they were just never worried about like operational complexity. They're just like it doesn't matter how messy it is, we'll go ahead and do it. They also didn't really worry too much about their ability to set culture because they were just so good at it. Like again, like that was just part of it. Um it wasn't until later like the Graphite acquisition where they started thinking about acquisitions in terms of strategic direction. Um and of course that was a much larger acquisition. Um and you know listen I I think um the company was so fast like who who knows to the extent that they would have figured out how to integrate all of these things and execute on them in in the limit um just because like you know like now they're part of a very large acquisition but I will say that they approached these in the same way that they approached everything which was incredibly thoughtful. They had a plan. They executed quite well. And so this may be the most concentrated company in the history of companies having done M&A,

</details>

**麦特·博恩斯坦**: 在现在的硅谷，当一个大公司的 CEO 能够自豪地说‘我的公司里有十几个前初创公司创始人（ex-founders）在工作’时，这是一种极高荣誉的勋章。

Cursor 在这一点上堪称行业典范。比如他们成功收购并引入了 Koala 的 Tito，以及引入 Adam Ward 负责人才端的建设。

他们并不是简单地把这些被并入的创始人塞进普通的个人贡献者（IC）岗位上，而是真正让他们深度参与甚至主导公司的核心建设。这在操作上其实是极其困难且复杂的，但他们凭借坚定的定力和包容度，成功将这种非传统的‘创始人集成（Founder Integration）’打法转化为了公司超常规增长的推进器。

<details>
<summary>Original English</summary>

**Matt Bornstein**: you know, admitted everything else. Yeah, I was going to say I feel like there's this badge of honor now when a CEO of a company says I have exfounders in my company. Um, and I think it should be a badge of honor, right? I don't know how many what that stat is for Curser. Do you guys know? Um, but I remember and they have so many great founders there, but uh I remember when they brought on Tito from Koala and then Adam Ward on the talent side actually and just seeing firsthand the leverage that they got from bringing in someone who was a founder CEO effectively but slotted really well into the cursor culture and just take that to great heights and add to the acceleration like I think that playbook you know I don't know I'm sure they're not the ones who started it per se in this new Genai era But they certainly are, I think, one of the best examples of how to integrate founders really, really well into your company. It's funny, right? Because Anthropic kind of gets that tag a lot now. It's like, oh, like exec at company A just went to take an IC role at Entropy, but like cursor kind of did this first and they weren't just like slotting people into IC roles. Like they're actually building the company this way, which I Yeah. I thought it's very it's very um unconventional, but but like really it's actually operationally incredibly complex. That's a conventional wisdom. Yeah. Yeah. Yeah. And I I think it's actually true. I mean, I think it's not that they, you know, um did something that people think is hard but is actually easy. I think it's actually hard and they just managed to pull it off, you know, credit to them.

</details>