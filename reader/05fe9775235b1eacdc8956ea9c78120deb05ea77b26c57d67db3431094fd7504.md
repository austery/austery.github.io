---
author: All-In Podcast
date: '2026-07-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9IMwRIei-Xc
speaker: All-In Podcast
tags:
  - ai-regulation
  - model-safety
  - self-governance
  - protein-folding
title: 播客访谈与人工智能监管提案的深度讨论
summary: 该文章记录了一场播客中，主持人与嘉宾围绕历史轶事、对人工智能行业自律提案的探讨展开。核心议题包括建立国际 AI 标准机构的建议，以及在模型安全、隐私和技术发展中的风险管理策略，并深入分析了前沿研究（如蛋白质折叠）对生物医学领域的潜在影响。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 欢迎收看 All-In 播客

**Jason Calacanis**: 各位，欢迎回到世界上最棒的播客。排名第一的播客，你们最喜欢的播客，All-In 播客。我是 Jason Calacanis，世界上最棒的主持人。当然，和我在一起的还有 Chamath Palihapitiya。

<details>
<summary>Original English</summary>

**Jason Calacanis**: All right, everybody. Welcome back to the world's greatest podcast. The number one podcast, your favorite podcast, the All-In podcast. I'm Jason Calakanis, the world's greatest moderator. With me, of course, Chimath Polyhapitive,

</details>

**Chamath Palihapitiya**: Jason，你是一个法国妓女和抢劫犯的曾曾曾曾曾孙……你可以从法国历史看出来。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: the great great great great great grandchild, Jason was of a hooker and you saw that from France and a purse snatcher.

</details>

**David Sacks**: 这源于一段法国历史。有历史记载说，他们会让你出来……Sacks，1719 年的协议是这样的，如果你被关在巴黎的监狱里，你可以获得自由，条件是你要和一个妓女结婚，然后搬到伟大的路易斯安那州。你在说什么？要接受这个协议吗？

<details>
<summary>Original English</summary>

**David Sacks**: This this comes from like a history of uh France. some history uh said they let you out of this was this was the deal in 1719 Sachs if you're a prisoner in a in Paris you were offered your freedom on the condition that you marry a prostitute and move to the great state of Louisiana what are you saying taking the deal

</details>

**Chamath Palihapitiya**: 这解释了你的某些特殊癖好，Jake，我……

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: it explains a a certain of your proclivities Jake I I

</details>

**Jason Calacanis**: 我还以为你想让我看看他们能不能为你通融一下这个规定。

<details>
<summary>Original English</summary>

**Jason Calacanis**: I thought you were asking me to see if they would extend the rule for you

</details>

**Chamath Palihapitiya**: 不，我是说你的曾曾曾曾曾祖母。我不是妓女，我是希腊人。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: no I'm saying that your great great great great great Grandma, I'm not a hooker. I'm Greek.

</details>

**Jason Calacanis**: 这就是我想明确表达的。她以前是……我们从来没有在监狱里待过。当然，David Friedberg 也在这里。兄弟，你最近怎么样？

<details>
<summary>Original English</summary>

**Jason Calacanis**: That's what I'm saying very explicitly. She was We never We never spent time in a prison. Also, of course, David Freeberg is here. How you doing, brother?

</details>

**David Friedberg**: 过着梦想般的生活。

<details>
<summary>Original English</summary>

**David Friedberg**: Living the dream.

</details>

**Jason Calacanis**: 很高兴你能回来。上周我们挺想你们的。Brad 表现怎么样？他代班代得好吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Good to be back. Missed you guys last week. How was Brad? How did he fill in?

</details>

**Chamath Palihapitiya**: 非常棒。是的，他很棒。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: It was great. Yeah. Yeah, he was.

</details>

**David Sacks**: 为特朗普账号的事小小庆祝了一番。

<details>
<summary>Original English</summary>

**David Sacks**: Trump account victory lap.

</details>

**Jason Calacanis**: 他确实小小地庆祝了一番。我们还放了《烈火战车》的音乐。还有，你在[消音]的特别时光，以及下周在[消音]的时间过得怎么样？

<details>
<summary>Original English</summary>

**Jason Calacanis**: He had a little victory lap. We played Chariots of Fire. And uh how was your special time at blank and your time next week at blank?

</details>

**David Friedberg**: 感谢你邀请我上你的节目，Jcal。

<details>
<summary>Original English</summary>

**David Friedberg**: Thanks for h Thanks for having me on your show, Jel.

</details>

### DeepMind 提出 AI 行业自律提案

**Jason Calacanis**: 好了，我们今天的日程安排得很满。有很多故事。让我们从 DeepMind 的 Demis Hassabis 说起，他刚刚发布了一项 AI 监管提案，这在兄弟们中相当受欢迎。在一篇 X 的文章中，Demis 呼吁建立一个由美国主导的国际 AI 标准机构，该提案是仿照 FINRA（美国金融业监管局）建立的。那是一个自律机构。它将受到联邦政府的监督，但由行业提供资金，并由独立的技术专家运营。前沿实验室将在发布模型前 30 天提交他们的模型。这在最初是自愿的，然后会变成强制性的。在某些时候，这些模型将针对网络安全、国家安全、生物威胁以及其他高风险领域的风险进行评估。基准测试将每季度更新一次，如果情况需要，该机构可以协调放缓开发速度。我猜那可能是指出现了网络风险等情况。从积极的一面来看，我们看到 Elon 表示这个提案很深思熟虑，OpenAI 的 Sam、Anthropic 的 Jack Clark、Sundar、Satya、Block 的 Jack Dorsey，以及 Collison 兄弟都表示支持。那么 Friedberg，谈谈你的想法吧。

<details>
<summary>Original English</summary>

**Jason Calacanis**: All right, we got a full docket today. Uh lots of stories. Let's start with uh Deep Mind's Deis Habis just dropped an AI regulation proposal and it's um it's pretty popular with the boys. In an ex article, Demis called for a US-led international AI standards body proposal is modeled after FINRA, the Financial Industry Regulatory Authority. That's a self-regulatory body. And this would be federally overseen, but industry funded and run by independent technological experts. Frontier Labs would submit their models 30 days before release. Uh, and it would be voluntary initially, then mandatory. At some point, the models would be assessed on risk to cyber security, national security, biological threats, and other high-risisk domains. Benchmarks would be updated quarterly, and the body can coordinate a slowdown in development if the situation demands it. I guess that would be if uh there was a cyber risk, etc. Looks like uh on the positive side we have Elon who said it was thoughtful, Sam at OpenAI, Jack Clark at Anthropic, Sundar, Satia, Jack Dorsey from Block, the Carlson brothers. So Freeberg um uh Freeberg, your thoughts on

</details>

**David Friedberg**: 哇，你今天可真是下足了功夫啊。你继续吧，Jason，挺好的。

<details>
<summary>Original English</summary>

**David Friedberg**: Oh, wow. Way to really way to really uh put in the effort today. Go ahead, Jason. Good.

</details>

**Jason Calacanis**: 就把话筒交给我吧。我会处理好的。让我来……

<details>
<summary>Original English</summary>

**Jason Calacanis**: Just pass it to me. I'll take care of it. Let me let me

</details>

**David Friedberg**: 你想让我干嘛？我的天，真是个不可思议的话题。

<details>
<summary>Original English</summary>

**David Friedberg**: What do you want me to do? Oh my god, what an incredible topic.

</details>

**Jason Calacanis**: 好吧，给我。让我来吧。你想让我来，对吧？三、二……

<details>
<summary>Original English</summary>

**Jason Calacanis**: All right, here. Let me do it. You want me to do it, right? Three, two,

</details>

**Chamath Palihapitiya**: 我们中有些人可是真正在乎这个话题的。开始吧。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: some of us actually care about this topic. Let's go.

</details>

**Jason Calacanis**: 好的。是啊，你在乎。好吧，我们开始。三，二。这里有一段视频，是我最初在 All-In 播客上提出这一预测的片段：“整个行业都需要受到监管，而且我认为行业需要自我监管。这是关键所在。我们需要制定一套 Google、微软、亚马逊都同意的测试标准。Elon，嘿，这些是我们应该测试的东西，他们应该在要求不懂模型的政府进行认证之前，先对每个模型进行自我认证。行业应该有自己的行业认证，就像他们在无数其他领域所做的那样。我提到过美国电影协会（MPAA）和电子游戏行业的例子。我们就应该自我认证。这是世界上最简单的事情。然后我们就可以自己发布模型，而不需要政府的介入。”

<details>
<summary>Original English</summary>

**Jason Calacanis**: Okay. Yeah, you care about it. Okay, here we go. Three, two. Here's a clip of me calling it on the All-In podcast first. The whole industry is going to need to be regulated and I think the industry needs to regulate themselves. That's the key to this. We need to have a set of tests that Google, Microsoft, Amazon all agree to. Elon, hey, these are the things we should test and they should self-certify each model before asking the government which doesn't understand the models to certify them. The industry should have an industry certification like they do for countless other things. I've talked about the MPAA and the video game industry. We should just self-certify. It's the simplest thing in the world to do. And then we could release the models ourselves without the government getting involved.

</details>

**Jason Calacanis**: Brie，你不想恭喜我又一次说中了吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Brie, would you like to congratulate me on nailing it again?

</details>

**Chamath Palihapitiya**: 首先，我认为 Demis 的提案非常聪明和深思熟虑。现在既然我知道你可能也有同样的想法，我觉得我们还是换个别的办法吧。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Well, first of all, first of all, I thought that Demis' proposal was really smart and thoughtful. Now that I know that you may have shared the same thought, I think we should just do something different.

</details>

**Jason Calacanis**: 我怎么都赢不了啊，Sacks。即使我猜中了，我也像是投中了一个半场三分。Chamath 却说：“把篮网挪开，把篮网挪开。”

<details>
<summary>Original English</summary>

**Jason Calacanis**: I can't win, Zach. Even when I nail it, I hit a halfcourt shot. Truman's like, "Move the net. Move the net."

</details>

**David Sacks**: 我认为有必要对这个提议稍微下个定义，也就是成立一个 SRO（自律组织），因为它们并非完全独立。像 FINRA 和国家期货协会（NFA）这样的 SRO，它们存在于金融市场中，它们的成立是为了让金融机构能够制定自己的监管规则，如何互相监督，如何确保每个人都在安全行事，因为它们显然都在相互交易风险。所以行业不想承担风险暴露，而且他们当然不想让事情慢下来，因为那会使市场变得低效。所以用 AI 来做类比在这里非常合适，因为行业里有很多参与者。他们都在努力推进 AI 技术，没有人希望由政府或外部来的单一监管机构对他们说，这是你们的模型必须通过的测试才能被认为是合适的。正如我们在加州看到的那样，当加州大约在一年或一年半前试图通过 AI 立法时，他们写的那些东西在当时根本就不合理。但快进一年，这些规则和要求中没有一项能真正与当今的技术相匹配。因此，像 FINRA 和 NFA 这样的 SRO 的目的在于，它们可以调整测试的运行方式，由谁来实际运行测试，并确保有合适的专家参与其中，即由独立专家来进行测试，同时受到联邦政府的监督，但不受其控制。所以在 FINRA 和 NFA 的例子中，它们最终要向参议院委员会和众议院委员会汇报，这赋予了这些委员会对这些管理机构的监督权，而这些机构本应努力确保自己做好了本职工作。因此，SRO 的概念是，可以从行业内引进那些懂得如何针对网络风险、生物风险、武器风险、社会操纵等风险来评估模型的专家。这个独立机构可以经过投票产生，可以随着时间的推移而改变，而且因为他们实际上拥有运行软件审查和此类测试的专业知识，他们的运作速度会比设立一个新的政府机构快得多。所以，这是一种非常优雅的解决方案。我想这就是为什么每个人——正如你所指出的，Jcal，而且我认为这没错——行业认识到这里需要某种程度的监督和检查点。我认为这实际上可以解决那个问题。所以我想这就是为什么大家都有点支持它的原因，因为它实际上并没有把事情交给政府。它在说：“嘿，我们将找合适的人来审视这些东西，而政府最终将拥有监督权。”

<details>
<summary>Original English</summary>

**David Sacks**: I think it's worth putting a little definition around this proposal, which is to form an SRO, self-regulatory organization, because they're not purely independent. SRO's like FINRA and the National Futures Association, they exist in the financial markets and they were created to allow the financial institutions to set their regulatory rules, how they check each other, how they make sure that everyone is being safe because they're obviously all trading risk with one another. So the industry doesn't want to have exposure and they certainly don't want to have things get slowed down because that would make the markets inefficient. So the analogy with AI is pretty appropriate here which is that there are many players in the industry. They are all trying to progress AI technology and no one wants to have a single regulatory body that comes in from the government or outside that says here are the tests you guys have to pass with your models in order for them to be appropriate. As we saw in California when California tried to pass AI legislation, I think it was about a year a year and a half ago, none of what they wrote even made sense at the time. But fast forward a year, none of those kind of rules and requirements actually map to the technology of the day. So the purpose of an SRO like FINR run NFA is they can adjust how tests are being run, who is actually running the test and make sure the right experts are involved in doing this, independent experts that is to do the testing with federal government oversight but not control. So in the case of FINRA NFA, they report up ultimately to Senate committee and House committee that gives those committees oversight of those governing bodies that are supposed to be doing the work to make sure that they're doing their frigin jobs. So the SRO concept would be that experts could be brought in from industry that know how to assess models for things like cyber risk, for things like biorisk, for things like weapons risk, social manipulation, etc., etc. that independent body can get voted on, can get changed over time, and because they actually have expertise in running software valves and running tests like this, they can operate at a faster pace than setting up a new government agency. So, it's it's kind of a very elegant solution. And I think it's why everyone, to your point, Jal, and I I'll say this is right, the industry recognizes that there needs to be some degree of oversight and checkpoints here. And I think that this could actually solve that problem. So that's why I think everyone's kind of climbing on board with it because it doesn't actually hand stuff over to the government. It says, "Hey, we're going to get the right people to to take a look at these things and the government is going to have oversight ultimately."

</details>

**Jason Calacanis**: Anthropic 和 OpenAI 有表态吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Did Anthropic and OpenAI have a point of view?

</details>

**David Sacks**: 他们都表示支持。我不认为 Dario 直接表态了，但 Dario 的总裁竖起了大拇指，然后我想 Sam 也竖起了大拇指，这意味着他们都在船上。

<details>
<summary>Original English</summary>

**David Sacks**: They both signed up to it. I don't think Daario directly, but Dario's president gave his thumbs up and then I think Sam gave his thumbs up which means they're on board.

</details>

**Jason Calacanis**: Sacks，在你看来，这是各种可能性中最好的一个吗？在他们激起了世界各国政府对这个问题如此关注之后，行业现在自己要进行自我监管了吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Saxs, is this the best of the uh possibilities in your mind? uh is the industry regulating itself after they have now provoked governments around the world to be so concerned about this issue.

</details>

**David Sacks**: 是的。而且，你知道，我和 Demis 谈过这个，这可能会让人感到惊讶，但我告诉他，我可能会支持这个提议——仅代表我自己，不代表政府中的任何人——因为我认为 SRO，也就是自律的方式，要比建立一个新的政府机构好得多。我认为新政府机构会迅速变成“AI 领域的车管所（DMV）”。Dario 称之为“AI 领域的美国联邦航空管理局（FAA）”。政府并没有评估 AI 模型的专业知识。评估标准变化太快了。你很快就会陷入排队的窘境，所有的模型都要排队等待测试，这会从长达一个月的延误开始。最终可能会变成好几个月，我们就会输掉 AI 竞赛。所以，我认为如果做得好的话，SRO 的方法将比那要好得多。我向 Demis 概述了一些我认为非常重要的标准或条件，以使这个方案行之有效。如果可以的话，我就快速过一遍这些标准。

<details>
<summary>Original English</summary>

**David Sacks**: Yeah. And I, you know, I talked to Dennis about this and this may surprise people, but I told him that I could potentially get on board with this, speaking just for myself, not on behalf of anyone in the government because I thought that an SRO, again, a self-regulatory approach would be infinitely better than creating a new government agency that I think would rapidly become a DMV for AI. Dario calls it an FAA for AI. The government does not have the expertise to evaluate AI models. The criteria are changing too rapidly. you're going to very rapidly end up with a queue where all the models would be waiting to get tested and it would start with a month-long delay. It would end up being many months and we would just lose the AI race. So, I think an SRO approach would be infinitely better than that if it was done right. And I outlined for Demis criteria or conditions that I thought were really important to in order to make this work. And if I could, I'll just run through them

</details>

<!-- chunk 2/12 -->

### AI 行业自律组织 (SRO) 的五项条件

**Speaker A**: 请讲。

<details>
<summary>Original English</summary>

**Speaker A**: please.

</details>

**Speaker B**: 好的。首先第一点，我认为这个自律组织（SRO）必须在 AI 行业内部具有广泛的代表性。它必须包括初创公司和开源社区，不能仅仅是三大实验室，你知道的，不能只是……

<details>
<summary>Original English</summary>

**Speaker B**: All right. So number one, I think the SRO has to have broad representation from within the industry, the AI industry. It has to include startups and open source. It can't just be the three biggest labs, you know, can't just be...

</details>

**Speaker A**: 不能被暗箱操作，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: the fix, right?

</details>

**Speaker B**: 是的，完全正确。这正是为了避免监管俘获的问题，对吧？如果有足够多样的利益集团得到代表，这就很难变成“红色俘获”（监管俘获）。比如，如果你让黄仁勋（Jensen）、埃隆（Elon）、扎克伯格（Zuck）参与进来，也许再加上米拉（Mera），因为她刚刚发布了一个非常有趣的……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Exactly. And that's precisely to avoid the problem of regulatory capture, right? If you have a diverse enough group of interests being represented, it's much harder for this to turn into red capture. So for example, I think if you had Jensen, Elon, Zuck, and maybe Mera because she just launched a very interesting...

</details>

**Speaker A**: 开源……

<details>
<summary>Original English</summary>

**Speaker A**: open...

</details>

**Speaker B**: 一个基于开源的平台，这在很大程度上能解决俘获问题。所以这是第一点。第二点，我认为这个机构应该只审查前沿模型，也就是真正处于前沿领域的模型。那些真正代表着人工智能最先进水平取得进展的模型，而低于这个级别的模型不应该在推向市场时受到阻碍。我确实认为，在监管下存在的一个巨大风险是，市场领导者会利用这一点来束缚较弱的模型。如果一个模型没有处于前沿水平，有什么理由去阻碍它呢？好的，这就是……

<details>
<summary>Original English</summary>

**Speaker B**: platform that's based on open mach capture problem to a large degree. So that's number one. Number two is I think that this body should only be reviewing frontier models, meaning the true frontier. The models that really represent an advance in the state-of-the-art of artificial intelligence and models below this level should not be held up from getting to market. And I do think that is a big risk under regulations is that the leaders of the market use this as a way to tie up lesser models. And there's no reason if a model is not at the frontier, why hold it up? Okay, so that's...

</details>

**Speaker A**: 所以它们必须在基准测试中排名前十，或者排名前二十。

<details>
<summary>Original English</summary>

**Speaker A**: so they have to be in maybe the top 10 performers, top 20 performers on the benchmark test.

</details>

**Speaker B**: 不，我认为，当他们在智能的关键维度上进行基准测试时，必须代表着比当前最先进水平有所提升。如果它不是阶跃性的改变，那你怎么应对某些新的增量风险呢，对吧？我的意思是，这一切都是为了应对由于智能方面出现了某种新的阶跃性变化，从而可能引入的某种增量性的灾难风险。这就引出了我的第三点：我认为这个机构应该只处理灾难性风险。据我所知，目前这些风险包括网络安全以及 CBRN（即化学、生物、放射性和核风险）。所以它不应该管那些，例如，虚假信息或微冒犯之类的事情。这不应该成为一个言论监管机构，你知道的，或者只是管那些看起来有点无关紧要的事情。设立这个机构的唯一理由就是为了应对真正灾难性的风险。这是第三点。第四点，德米斯（Demis）在他的帖子里也提到了，那就是我认为它应该首先是自愿参与的。这个新组织在被正式载入法律并成为强制性机构之前，应该先证明它是行之有效的。然后第五点是，它应该作为新监管机构的替代品。如果它只是额外增加的机构，那就违背了初衷，也没有真正支持它的理由了。所以我再说一遍，我认为这必须是一个替代方案，而不是在一堆新的监管结构之上再加码。所以，如果你做到了这五件事，我认为它会变得更容易让人接受。德米斯说过，我是说，他没有把所有这些点都写进他的博客帖子里，但他确实对我说过他基本同意。因此，如果采纳了这些建议，这可能是我们能够支持的东西。但这并不意味着我没有担忧了。例如，我很担心，你知道的，我觉得达里奥（Dario）已经表示支持这个，然而我认为这只是 Anthropic 的一个开价，意思是他们会接受这个并说“非常感谢，这比我们今天的监管要多”，但这绝不会是结束，对吧。这只会成为达里奥现在多次呼吁实现的目标——即“AI 领域的 FAA（美国联邦航空管理局）”的垫脚石。如果可以的话，作为最后一点，我只想解释一下 FAA 是做什么的，因为人们需要明白，你知道的，“AI 领域的 FAA”听起来很不错，但实际上它是一个非常极端的提议。FAA 的职责之一，是批准新的飞机设计。懂了吗？具体来说，它要求对任何新的飞机设计或重大改动进行所谓的型号认证。对于一个全新的飞机设计，需要 5 到 9 年的时间……

<details>
<summary>Original English</summary>

**Speaker B**: No, I think I think when they benchmark on key dimensions of intelligence, they have to represent an increase above where the current state-of-the-art is if it's not a step change, then how are you dealing with some new incremental risk, right? I mean, this is all about dealing with some sort of incremental catastrophic risk that could be introduced by some new step change in intelligence. And that brings me to number three, which is I think this body should be dealing with catastrophic risk only. And to my knowledge, those right now are cyber and CBRN, meaning it's, you know, chemical, biological, radiological, nuclear. So it should not be things, for example, like disinformation or microaggressions. This should not become a speech regulator, you know, or just, you know, things that seem kind of trivial. The only reason to have this is for truly catastrophic risk. So that's number three. Number four, and Demis mentioned this in his post, is that I think it should be voluntary first. This new organization should prove it works before it gets legally enshrined and becomes mandatory. And then number five is this should be a substitute for a new regulatory agency. If it's just additive, then it defeats the purpose and there's no real reason to support it. So again, I think this has to be a substitute, not an addition to a bunch of new regulatory structures. So I think if you did those five things, I think this becomes much more palatable. And Demis said, I mean, he didn't put all these points in his blog post, but he did say to me that he was bas. So I think if those notes were adopted, this is something that we could potentially get on board with. That doesn't mean I don't still have concerns. I'm quite concerned for example that you know I think Daario has expressed support for this however I think this is just an opening bid for anthropic meaning they'll take this thank you very much this is more regulation than we have today but that won't be the end of it right this will just be the stepping stone to get what Dario has now called for many times which is the FAA for AI and if I could let me just as as a final point I just want to explain what the FAA does because people need to understand you know FAA for AI sounds really nice, but actually it's a really extreme proposal. What the FAA does, among other things, is approve new airplane designs. Okay? And specifically, it requires what's called a type certification for any new aircraft design or major changes. And for an entirely new aircraft design, it takes 5 to 9 years

</details>

**Speaker A**: 才能获得认证。

<details>
<summary>Original English</summary>

**Speaker A**: to get the certification.

</details>

**Speaker B**: 而如果你仅仅是想修改一下证书，我猜是为了，你知道的，重大变更，或者我甚至不确定变更需要多大程度，这都要花三到五年的时间。比如，波音 737 Max 就花了大约 5 年时间。所以这是基于许可的监管。没有批准，就不能进行商业飞行。这是安全第一。听着，在防止飞机坠毁的情况下，这可能是有道理的，但是当你谈论 AI 模型时，你是在谈论用一个可能完全处于政府控制之下、完全由政府批准的系统，去替换一个每几个月就发布新版本的系统。所有东西都必须被认证，你可以预见时间线会从几个月拉长到几年。再说一遍，我认为如果那样的话，我们肯定会输掉 AI 竞赛，因为中国是不会遵守那些规则的。所以总结一下，如果让我选择是成立一个“AI 领域的 FAA”还是一个我称之为“AI 领域的 DMV（机动车管理局）”的机构，我更愿意选择德米斯提议的“AI 自律组织（SRO）”，也就是自我监管的路径。但是我们真的必须保持它的纯粹性和公正性，因为否则的话，它只会成为即将到来的新一波监管浪潮的探路石，它会成为发生大规模监管俘获的载体。

<details>
<summary>Original English</summary>

**Speaker B**: And if you merely want to amend a certificate, I guess for you know major changes or I'm not even sure how major the changes need to be, it takes three to five years. So the Boeing 737 Max, for example, took about 5 years. So this is permissionbased regulation. There's no approval, no flying commercially. It's safety first. Look, that might make sense in the case of preventing plane crashes, but when you're talking about AI models, you're talking about replacing a system that is releasing new versions every couple of months with one that is potentially fully under the control of government, fully government approved. Everything has to be certified, and you could expect the timeline to go from months to years. Again, I think we'll just simply lose AI race if that happens because China is not going to abide by those rules. So just to sum up, if my choices are between FAA for AI or what I would call the DMV for AI, I would much rather go for Demis' SRO for AI, the self-regulatory approach. But we really have to keep it honest and pure because again otherwise it'll just be the opening bid in a coming new wave of regulation and it will be the vehicle for massive regulatory capture.

</details>

### 防止监管俘获与开源的重要性

**Speaker A**: 就如你所说，它不能施加限制。

<details>
<summary>Original English</summary>

**Speaker A**: To your point, it can't restrict.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 不能限制开源。我认为这太重要了，因为所有其他这些努力都需要你花钱，而这往往就是监管俘获发生的地方，你必须让初创公司和开源社区能够有效地参与竞争。查马斯（Shimoth），你对这个新的自治机构有什么想法吗？

<details>
<summary>Original English</summary>

**Speaker A**: Can't restrict open source. I think that's so important because all of these other efforts require money that you have to spend which is always where regulatory capture happens and you have to enable startups and open source to compete effectively. Shimoth, any thoughts on this new self-governing body?

</details>

**Chamath**: 我认为这非常重要，我希望它能尽快成立。我们需要记住的一点是，将会涌入大量的资金，试图影响政治通道的两边，以一种能产生某种形式的监管俘获的方式来监管这一切。只是我们还不知道具体会是什么方式。所以，我们越快通过真正建立一套规则并取代联邦监管的需求，来避开那条歧途，就越是一件非常重要的事情。当然，说到底，你在某些方面仍然会有联邦的监管，因为你依然有在这些标准中扮演重要角色的商业活动。你仍然有司法部（DOJ）。所以，这并不意味着这里会变成法外之地。但它能防止的是，少数几个参与者利用他们的资产负债表和资本来本质上“过河拆桥”。我认为如果那种情况发生了，我们的处境就会非常糟糕。所以我认为德米斯的提议非常有意义，我们应该赶紧推进它。

<details>
<summary>Original English</summary>

**Chamath**: I think it's really important and I hope it happens quickly. The thing we have to keep in mind is there's going to be a torrent of money that's going to try to influence both sides of the political aisle to regulate this in a way that creates some form of regulatory capture. We just don't know what. And so the faster we avoid that off-ramp by actually establishing a set of rules and superseding the need for federal oversight is a really important thing. Now, at the end of the day, you still have federal oversight in some ways because you still have commerce that plays a huge role in these standards. You still have the DOJ. So, it's not as if it's going to be a wild west. But what it prevents is a handful of actors using their balance sheets and their capital to essentially pull the ladder up. And I think if that happens, we're in a really bad place. So I think Demis' proposal makes a ton of sense and we should just get on with it.

</details>

**Speaker A**: 好的。

<details>
<summary>Original English</summary>

**Speaker A**: All right.

</details>

**Speaker B**: 嗯，是的。但是前提是，我是说再次强调前提，我认为我们必须确保，我是说听着，在我看来这里有五个条件，但我认为我们必须确保它是纯粹的。即使在 FINRA（美国金融业监管局）的例子中——这是德米斯使用的类比，即我们应该像 FINRA 那样建立这个机构——FINRA 最终还是向政府汇报的。它是向美国证券交易委员会（SEC）汇报的。因此，你知道的，如果我们真的要设立这个新的 SRO，它将向政府中的哪个部门汇报呢？将会有一场巨大的争夺战，然后它将受到政治压力的影响。软件行业以前从未以这种方式被监管过。我们没有专门针对软件的监管机构。我们是对的，但那些问题也很重要。但我的观点是，我只是想说这些事情从来都不是理想的。但如果面临的选择是：我们要么扼杀开源并束缚整个市场导致双头垄断，要么选择这个（SRO），我会说这个……

<details>
<summary>Original English</summary>

**Speaker B**: Well, yes. But provided I mean again just provided that I think we we make sure that I mean look in my view there there are five conditions but I think we do have to make sure it's pure. Even in the FINRA example, that's the analogy that Demis used was that we should set this up in the same way that that FINRA is set up. FINRA does report in ultimately to the government. It reports into the SEC. And so, you know, if we are going to set this new SRO, where is it going to report to in the government? There's going to be a huge food fight over that and it will then be subject to political pressure. The software industry has never been regulated in that way. We do not have a dedicated regulator for software. We're right, but those issues are important. But my point is, h I'm just saying these things are never ideal. But if the choices are we kill open source and we lad pull the entire market, so there's a duopoly or there's this, I'd say this

</details>

**Chamath**: 绝对是这样。这就是我论点的核心，它绝对是两害相权取其轻。我不确定这是否是我们仅有的两个选择，但越来越毫无疑问的是，监管 AI 的压力正变得越来越大。坦率地说，这一切都可以追溯到 Anthropic 的政府行为。

<details>
<summary>Original English</summary>

**Chamath**: for sure. And and that's and that's that's the crux of my argument is it's definitely the lesser of two evils. I'm not sure those are the only two choices, but increasingly there's no question that the pressure is coming to regulate AI more and more. And frankly, this all goes back to anthropics government.

</details>

**Speaker A**: 他们招惹了老虎（引火烧身）。他们招惹了老虎。

<details>
<summary>Original English</summary>

**Speaker A**: They poke the tiger. They poked the tiger.

</details>

**Chamath**: 是的。好吧，不仅如此。

<details>
<summary>Original English</summary>

**Chamath**: Yeah. Well, it's it's more than that.

</details>

**Speaker A**: 他们正在给老虎喂肉。

<details>
<summary>Original English</summary>

**Speaker A**: They're funding the meat the tiger.

</details>

**Chamath**: 是的。实际上我想更新一下这个情况，因为……

<details>
<summary>Original English</summary>

**Chamath**: Yeah. I want to give an update on that actually cuz

</details>

**Speaker A**: 我会说所谓的招惹老虎，就像是让美国公众感到非常恐慌，然后政府就介入了。是的。

<details>
<summary>Original English</summary>

**Speaker A**: I would say poking the tiger of like the American public getting really freaked out and then the government stepping in. Yeah,

</details>

**Chamath**: 完全同意。实际上这方面有几个数据点支撑。我只想快速更新一下。所以，在去年的 10 月份，我发推文说 Anthropic 正在推行一种基于散布恐慌的复杂的监管俘获策略，然后大家都对这个有点抓狂了。这再一次像是一个非常热门的观点或者辛辣的观点……

<details>
<summary>Original English</summary>

**Chamath**: totally. And there's a couple of data points on that actually. I just want to give a quick update. So in October of last year, I tweeted that Anthropic is running a sophisticated regulatory capture strategy based on fear-mongering and everyone kind of went crazy over this. This was again like a very hot take or spicy take at the

</details>

<!-- chunk 3/12 -->

### Anthropic的监管俘获策略与各州人工智能立法

**David Sachs**: 当时人们一度以为我是在欺负一家小初创公司。现在我想大家应该都能清楚地看清真相了，那就是，看吧，这根本不是什么规模很小的小初创公司。他们现在已经拥有了高达一万亿美元的市值估值。Gavin Baker甚至认为，在他们完成首次公开募股（IPO）之后，市值将会达到惊人的三万亿美元。这实际上已经是当前规模最大、最具影响力的大型科技巨头公司之一了，而且我认为，无论从几乎所有的评判标准来看——当然也包括营业收入这种硬性指标——他们都绝对是目前处于绝对领先地位的人工智能（AI）公司。所以我认为，人们现在都能非常清楚地看到，他们手中掌握着极其庞大的资源，而且他们正在将这些庞大的资源集中投入到一种特定的努力之中，这就好像Jimoth你刚才所生动描述的那样，这是一种“过河拆桥”（pull up the ladder）的行径，同时这也是最为经典、最为典型的监管俘获（regulatory capture）行为。刚好就在前几天，Politico上发表了一篇文章。这篇文章的标题叫做“深入解析Anthropic在各州逐步收紧AI规则的计划”（inside Anthropic state-by-state plan to ratchet up AI rules）。这篇文章中明确写道：“人工智能巨头Anthropic正在推行一种‘比拼’（oneupmanship）的策略，这种策略旨在鼓励各州实施越来越严格的人工智能护栏，而不是围绕着一套单一的法规来划定统一的界限。”所以，他们最基本的想法是，他们首先让一套法规在某一个特定的州获得通过，比如说加利福尼亚州的SB53法案，然后这本来应该成为至少所有蓝州（民主党控制的州）的立法范本。但是随后，随着每一个新州的加入，他们实际上都会让这些法规变得越来越严格、越来越无所不包。所以，现实中实际上并不存在一个稳定的平衡点。他们试图达到的目的是，推动每一个新增的州出台越来越多的、更加严苛的法规。因此，这篇文章实际上向我们解释了，他们所做的事情与我们想要建立单一国家层面框架的初衷是完全背道而驰的。他们实际上想要的就是这种拼凑起来的、支离破碎的法规体系，因为他们再一次利用了他们在州一级制造的压力，来强加越来越多、越来越严格的法规。而且，就像我去年说过的，Anthropic是导致那种正在严重破坏初创企业生态系统的州级监管狂热现象的主要责任人。再说一次，当时大家都觉得我的想法疯了。我觉得现在已经有非常充足的证据可以清楚地表明，这就是他们的真实议程和意图。而且，嗯——

<details>
<summary>Original English</summary>

**David Sachs**: then people thought that I was beating up on a little startup. Now I think everyone can kind of see the truth which is look this is not a little startup. They already have a trillion dollar market cap valuation. Gavin Baker thinks it'll be at three trillion after they IPO. This is actually one of the biggest of the big tech companies and they are I think by pretty much every criteria including revenue the leading AI company. So I think people can see now that they have enormous resources and they're putting those resources behind an effort to like Jimoth you said pull up the ladder and it's classic regatory capture and there was an article in Politico just the other day. is called inside Anthropic state-by-state plan to ratchet up AI rules. And what it says is quote AI giant Anthropic is pursuing a strategy of oneupmanship that encourages states to impose increasingly tougher AI guard rails rather than a line around a single set of regulations. So the basic idea is that they get a set of regulations passed in one state like California's SB53 and that was then supposed to be the model at least for all the blue states. But then with each new state, they actually make the regulations more and more strict, more and more all-encompassing. So there's not actually a stable equilibrium. What they're trying to do is drive each incremental state to more and more regulations. And so this is actually an article explaining that they're doing the opposite of trying to create what we wanted, which was a single national framework. they actually want the patchwork because they're using again the pressure they're creating at the state level to impose more and more regulations. And again, what I said last year was that Anthropic was principally responsible for the state regulatory frenzy that is damaging the startup ecosystem. Again, everyone went crazy at the time. I think now there's plenty of evidence showing this is their agenda. And um

</details>

**Jimoth**: 顺便说一句，他们在这件事上最终是会赢的，因为各个州都拥有非常大的主权权利，就像我们在自动驾驶技术上所看到的情况一样，最终将由各州来做决定。这不会是一个联邦层面自上而下的强制性命令。各州有权自己做决定，这正是美国的本质所在。

<details>
<summary>Original English</summary>

**Jimoth**: and by the way, they're going to win that because states have great sovereignty rights and like we're seeing with self-driving the states are going to decide. It's not going to be a federal mandate. The states get to decide just the nature of the US.

</details>

**David Sachs**: 其中的原因在于——

<details>
<summary>Original English</summary>

**David Sachs**: The reason why

</details>

**Speaker A**: 就现实情况而言，他们会在几个州赢得这场胜利的，对吧，Zach？

<details>
<summary>Original English</summary>

**Speaker A**: they're going to they're going to win on that in a couple of states, right, Zach? Just realistically,

</details>

**David Sachs**: 他们在很多个州都已经赢了。他们已经在加利福尼亚州、伊利诺伊州和纽约州赢了，我的意思是他们正在所有的蓝州获胜，甚至可能包括一些红州（共和党控制的州）。但是，听着，归根结底，Anthropic的那些论点之所以能够被广泛接受、能够找到市场，是因为当你去找政府官员，并对他们说“请监管我”时，你要知道，你在那里就会拥有更大的权力，因为在政府机构里几乎没有任何人会拒绝这种提议，他们绝对不会说“哦，不，不，不，我们不够资格，比如，我们不想要政府监管干预”。

<details>
<summary>Original English</summary>

**David Sachs**: they've won in a bunch of states. They already won in California and Illinois and New York and I mean they're winning in all the blue states and maybe even some red states. But look ultimately the reason why anthropics arguments are finding purchase is because when you go to the government and say please regulate me you know you should have more power there there's hardly anyone in government who will ever say oh no no no we're not qualified like we don't want government

</details>

### 支付行业的巨额并购与整合前景

**Moderator**: 是的，政府里面很少有人会坚持那样的基本原则，政府里的大多数人在听到这种请求时都会毫不犹豫地说：“非常感谢你，我们还能拿走什么其他的权力呢？”我认为这正是当前科技行业里很多人正在犯的一个大错误，他们天真地认为自己可以通过简单地做出让步来收买政客或者收买整个政治体系。不，那是行不通的，那只会导致监管压力的不断攀升和不可控的升级。政府会非常乐意地接受这些现成的权力，然后再转过头来继续向你索要更多、更多、更多，直到整个行业完全处于政府的绝对控制之下。所以，在未来的某个特定时刻，我认为这些科技公司将必须拿出一点骨气来，去进行坚决的抗争，并明确决定他们到底愿意在哪里划清界限。如果Demis所提出的SRO（自律组织）就是那条底线，如果他们能坚定地说：“好吧，我们认为这就是正确的解决方案，我们打算就在这里进行抗争，必须是这样。作为这种让步的交换，我们需要获得优先权，我们需要将其他一些明确的条件写入法律，以确保界限就划在这里”，如果是这样的话，那么我认为这还能行得通。但我认为如果你只是有点像是在免费把权力拱手相让，而所有这些公司都只会一味地附和说：“哦，是的，尽管监管吧，把SRO交给我们就好。”那么这绝对不会是事情的结局。这只会成为政府索取权力的一个开盘价而已，政府肯定还会回来索取越来越多、越来越多的东西。好了，让我们继续向下推进我们今天的议程吧。Stripe，这目前仍然是一家私人公司，我想这大概让它的很多股东感到非常懊恼吧。呃，现在当他们进入这件事的第二天，是的，我的意思是我个人所在的几个基金里面有很大的仓位，比如大家都在喊，上市吧，伙计们。他们现在正在为你的母校，David Sachs，也就是PayPal，出价530亿美元，而PayPal本身是一家上市公司。Stripe和私募股权基金Advent正在联合提议以每股大约60美元的价格来收购PayPal，相比目前的股价这是一个小幅的溢价。大多数市场人士认为它的最终成交价会更高，更可能会是每股70美元左右。很明显，PayPal的股票在听到这个消息后应声大涨。然后——

<details>
<summary>Original English</summary>

**Moderator**: yeah there are very few people who are principled that way and most people in the government will say thank you very much what else can we take and this is the mistake that I think a lot of people in the tech industry are making is they think that they can just buy off politicians or the political system by making concessions. No, that will just lead to a ratcheting up of the pressure. The government will be happy to take this and then come back for more and more and more until it's fully under government control. So, at some point, I think these companies are going to have to grow a spine and fight and decide where they're willing to draw a line. And if Demis' SRO is the line, if they're saying, "Okay, we think this is the right solution and we're going to fight here and this has to be it and in exchange for this we need preeemption and we need, you know, other things written into law that make sure this is where the line is, then I think it can work. But I think if you're just kind of offering it up for free and all these companies are just going to say, "Oh yeah, regulates, give us the SRO." That will not be the end of it. That will just be the opening bid and the government will come back to take more and more and more. Yeah. All right, let's keep moving through the docket here. Stripe, which is still a private company, much to the chagrin of many of the shareholders, I think. Uh, now as they go into the second day on this, yes, I mean, I'm in I'm in a couple of funds that have large positions like go public, boys. They are bidding bidding 53 billion for your alma mada, David Sachs, PayPal, which is a public company. Stripe and the private equity fund Advent are jointly offering to acquire PayPal for about 60 bucks a share, which is a small premium. Most people think it'll go for more like $70 a share. PayPal stock jumped on the news obviously. And

</details>

**Speaker B**: 你们有没有弄清楚这件事情的底细，到底是怎么回事？真的只是Stripe和Advent这两家吗？因为后来有其他的人报道说Block也参与了这笔交易。

<details>
<summary>Original English</summary>

**Speaker B**: were you able to get to the bottom of this that was it just Stripe and Advent? Because then somebody else reported that it was also Block.

</details>

**Moderator**: 是的，Block也参与进来了。

<details>
<summary>Original English</summary>

**Moderator**: Yes, Block is coming in as well.

</details>

**Speaker B**: 这实在是太让人感到困惑了。其他几乎所有的媒体消息来源在这一点上似乎都莫衷一是，报道得乱七八糟。

<details>
<summary>Original English</summary>

**Speaker B**: It's so confusing. every other media source is like they're all over the place on this.

</details>

**Moderator**: 是的。不，我觉得这是因为这是一个突发性的新闻事件，也许他们当时正试图对这件事情严格保密。

<details>
<summary>Original English</summary>

**Moderator**: Yeah. No, it's I think it's because it was a breaking story and maybe they were trying to keep it quiet.

</details>

**Speaker B**: 不过，如果Block确实参与其中，与如果他们完全没有参与相比，这可是有着天壤之别的一件重大事件。我认为——

<details>
<summary>Original English</summary>

**Speaker B**: It's a huge deal though if if Block is a part of it versus if they're not. I think

</details>

**Moderator**: 是的。Block（其前身为Square）是Jack Dorsey创办的知名支付公司，他是我们这个行业里面极少数几个曾经创造过两家百角兽（decacorns，指估值超过百亿美元的超级初创企业）的杰出企业家之一。而且，呃，他们在这项庞大的联合收购要约中贡献了高达170亿美元的股权。他们究竟将如何拆分和消化PayPal内部的那些庞大资产，将是摆在面前的一个巨大问题。显然，除了PayPal本身，他们还拥有许多其他不同的品牌，其中包括Venmo等。我只是在这里大胆地猜测一下，这些资产可能会与Block现有的资产产生极佳的化学反应和高度的契合度。Stripe拥有Bridge。那是他们在2025年斥资10亿美元重金收购的一家稳定币基础设施公司。而PayPal有SIUSD，这是一款已经在市场上流通的稳定币。那是他们自家的稳定币产品。所以，稳定币业务绝对是这笔庞大交易中的一个极为重要的组成部分。但最重要的一点依然是，PayPal目前仍然是一个不可忽视的行业超级巨头。Sachs，他们拥有高达4.39亿个消费者账户。25年前你们确实在那边做对了一些非常了不起的事情。它至今仍然成功地经受住了时间的严酷考验。

<details>
<summary>Original English</summary>

**Moderator**: Yes. And Block, formerly known as Square, is Jack Dorsey's uh payment company, one of the few entrepreneurs to ever create uh two decacorns in our industry. And uh they're contributing 17 billion in equity in the combined offer. how they um chop up what's inside of PayPal would be the big question. Obviously, they own, you know, a number of different brands including Venmo in addition to PayPal. That might go really well with the I'm just taking a guess here with the block assets. Stripe owns Bridge. That's their stable coin infrastructure company they acquired for a billion dollars in 2025. PayPal has SIUSD which is already in circulation. That's their stable coin. So, stable coins are part of this. But the biggest thing is PayPal is still a juggernaut. Sachs 439 million consumer accounts. You did something right there 25 years ago. It still the test of time.

</details>

**David Sachs**: 这确实有点不可思议。真的非常不可思议。

<details>
<summary>Original English</summary>

**David Sachs**: It's kind of amazing. It really is.

</details>

**Moderator**: 经过了这么长的一段时间，它依然能够保持如此强劲的发展势头，这难道不是很不可思议吗？是的。品牌能够持续保持如此旺盛的生命力这么久，这本身就是一件非常奇妙的事情。

<details>
<summary>Original English</summary>

**Moderator**: Isn't it amazing that it's still that strong? Yeah. It's weird when brands keep going for that long.

</details>

**David Sachs**: 但是现在面临的严峻问题是，这个产品已经变得非常老旧，甚至可以说是陈旧不堪了。我认为它的年增长率只有7%左右，当然，对于它已经成长到的如此庞大的基数来说，这其实也是一个不小的数字，它的基数确实很大，但不可否认的是，产品本身已经变得有些过时了，在某种程度上，它已经变成了一个传统的遗留产品。我其实非常好奇，很想听听Stripe的那些人打算如何去解决这个棘手的问题，因为我觉得这是一个非常非常难以解决的难题。也许他们根本不打算去解决它，也许他们只是想通过更高效的运营来管理它，然后像挤牛奶一样不断榨取它的剩余商业价值——

<details>
<summary>Original English</summary>

**David Sachs**: But the problem is that the product is getting very long in the tooth. I think it's only growing 7% a year which is a lot on the base that you know it's it's grown to it's a big base but the product has become somewhat obsolete and in a way it's a legacy product. I'd be curious to hear from the Stripe guys how they would fix that cuz I think that's a very hard problem to fix. Maybe they wouldn't maybe they would just run it more efficiently and kind of milk it

</details>

**Speaker B**: 也就是算是玩一出经典的私募股权资本运作的把戏。另一个完全不同的问题在于——

<details>
<summary>Original English</summary>

**Speaker B**: kind of do a private equity play. The different question

</details>

**Moderator**: 真正值得我们去深入探讨的有趣问题是，Advent、Stripe以及Block这三方如果成功联手，他们共同孕育出来的唯一一种“结晶”或者说最终成果将会是什么样子？我认为只可能有一个结果，那就是你们正在打造一个足以与Visa和Mastercard（万事达卡）全面抗衡的超级竞争对手。

<details>
<summary>Original English</summary>

**Moderator**: the interesting question to ask is what is the only kind of baby that advent and stripe and block could have together and I think there's one which is you are creating a competitor to Visa and Mastercard

</details>

**Moderator**: 因为你现在一举拥有了多达六亿甚至七亿的庞大用户账户基础。你还拥有了极其庞大且完善的稳定币基础设施。你同时也拥有了Stripe在过去15或20年的时间里潜心建立起来的所有那些顶级的风险管理基础设施。在早期，外界对Stripe商业模式最大的批评声在于，他们必须煞费苦心地去建立非常多、非常繁杂的增值服务，因为大家在当时一直普遍认为，作为构建在传统支付轨道之上的一个中间商，他们所能赚取的那些微薄抽成，最终实际上会在激烈的市场竞争中被无情地侵蚀和淘汰掉。现在非常值得称赞的是，他们做得如此之好、如此之出色，以至于人们所担忧的那些情况并没有发生。但我认为这一切在现在的意义在于，你可以大胆地进行垂直整合，并且能够提供从头到尾的一条龙全方位服务（soup to nuts）。这很可能是从中得出的、顺理成章的最明显的结果。通过这种深度的整合，现在Stripe就顺理成章地获得了极其宝贵的、超低成本支付轨道的访问权，成本几乎可以无限趋近于零，并能够以此将其业务版图拓展到世界各地的每一个角落。Block同样也能从中获益，而Advent则可以将大量的资金源源不断地注入其中。因此，如果这一切真的能够完美结合在一起，那将是非常非常强大的力量。Rbert，这一切到底说明了什么呢？关于那些已经达到如此惊人规模的私募市场公司，以及关于Stripe可能永远都不会选择上市的猜测？我的意思是，一家私募股权公司如何能够在这种复杂的结构下，在两三年或者是四年的短暂时间里，顺利获得他们预期的高额投资回报呢？难道他们最终会选择把手中更多的份额转卖给Stripe吗？对于这里的这种复杂结构以及深远的资本市场影响，你到底有什么看法和独到见解呢？

<details>
<summary>Original English</summary>

**Moderator**: because you now have upwards of 6 or 700 million accounts. You have massive stable coin infrastructure. You have all of the riskmanagement infrastructure that Stripe has built over the last 15 or 20 years. The big critique of Stripe's business model early on was they had to build so many value added services because everybody always thought the take that they could make as a middleman sitting on top of the traditional rails would effectively get competed away. Now to their credit, they've done such a good job that that hasn't happened. But I think what it means now is you can vertically integrate and go soup to nuts. That is probably the most obvious thing to make out of it. So that now Stripe gets access to an ultra- lowcost set of payment rails literally like to zero brings it everywhere all over the world. So does block advent can pour money into it. So it's quite powerful if it comes together. Rbert, what does this say about private market companies at scale and Stripe potentially never going public? I mean, how does a private equity firm get their return on this investment in 2, three, four years? Do they wind up selling more of it to Stripe? What are your thoughts here on the structure and capital market implications here?

</details>

**Rbert**: 我认为未来在市场上我们将会看到更多类似于这样的交易。如果你仔细看看Ryan Cohen对eBay的出价，我认为——

<details>
<summary>Original English</summary>

**Rbert**: I think there's going to be more of these kinds of deals. If you look at Ryan Cohen's bid for eBay, I think

</details>

<!-- chunk 4/12 -->

### 用AI重塑传统数字企业

**Speaker A**：这可能是我认为正在显现的第二条趋势线上的一个点，也就是说，那些所谓的AI原生派，正在审视那些所谓的第一代数字原生企业。这些企业已经变得成熟、陈旧、缺乏活力，不再由创始人管理，也没有意识到AI带来的机遇，尚未发挥出它们的潜力，或者在很多方面开销过度。当你作为一个现代AI运营者审视这些企业时，你会觉得：“这到底是怎么回事？这东西被利用得太不充分了。他们没有很好地利用他们的网络。他们运营得不好。他们开销太大。他们没有用好AI。”于是，一系列显而易见的机会就出现了。我认为资本市场——就像我们看到的Josh Kushner整合会计师事务所，以及General Catalyst正在做类似的项目——你可以利用资本去收购那些传统服务型企业，并对它们进行“AI化”改造。我认为这是一种思路的延伸，即审视传统的数字企业，并对它们进行“AI化”。这样的公司有一大串，大约有二三十家。所以，如果你审视公开市场，你会说：“嘿，看看那些在互联网早期甚至近期崛起、如今不再由创始人掌舵且陷入停滞的软件公司和网络企业，这里面蕴藏着巨大的机会。现在的问题是，作为资本提供者，你会选择和谁合作来执行这家企业的复兴计划？”你总不能去雇个麦肯锡顾问来替你做这事。必须是最顶尖的人才，必须是这个行业里最合适的玩家。所以，我认为Ryan Cohen通过他在Chewy和GameStop做的一些事情，显然证明了他的实力，当然这还有争议。我花了一些时间采访他，以了解他的……

<details>
<summary>Original English</summary>

**Speaker A**: it's probably a second dot on a line that I think is emerging, which is folks that are call it AI native are looking at call it first generation digital native businesses that have become mature and old and stale and aren't run by the founders anymore and have not yet realized the opportunities with AI, have not yet realized their potential. or overspending in a lot of ways. And when you take a look at those businesses as a modernday AI operator, you're like, "What the hell? This thing is so under uh utilized. They're not using their network well. They're not operating well. They're overspending. They're not using AI well." And there's a set of opportunities that become quite obvious. And I think the capital markets as we've seen with like Josh Kushner's roll up of accounting firms and General Catalyst has a project like this where you can kind of use capital to go buy you know in those cases traditional services businesses and AIify them. I think this is part of a line of maybe looking at traditional digital businesses and AIifying them. And there's a long list of these. There's a couple dozen of them. So I think if you looked at the public markets and you said, "Hey, where are all these kind of software companies, network businesses that emerged in the early part of the internet or even in the more recent part of the internet, aren't run by their founders anymore, have stalled out, there's a massive opportunity. Now the question as a capital provider is who do you partner with to go and execute that operational revival of that business?" You're not going to go hire some Mckenzie consultant to do that work for you. It's got to be the best of the best. It's got to be the right players in the business. So, I think Ryan Cohen has proved his metal obviously with some of the things that he's done with Chewy and GameStop and that's obviously debatable. I spent some time interviewing him to understand his

</details>

**Speaker B**：那是在All-In访谈节目上。你可以去我们的频道里找，是上个月的事。

<details>
<summary>Original English</summary>

**Speaker B**: This was on the Allin interview program. You can go to our channel and find it there. It's last month.

</details>

**Speaker A**：感谢你的推广。显然，谈到支付领域，谁能比Stripe更合适呢，或许Jack Dorsey也会在这里扮演一个角色。顺便说一句，因为资本——我的意思是，如果你想想那170亿美元的股权出资，在技术上意味着Stripe和Block向现金投资者出售了170亿美元的股权。这笔现金随后将用于收购PayPal。因此，Stripe和Block最终将拥有PayPal的一部分股份。私募股权投资者则拥有Block和Stripe的一部分股份。而在已经公布的交易文件中不明确的地方（因为我认为这与公开市场无关），是谁会在交易完成后实际运营PayPal。我打赌他们会把公司交给Stripe的人，然后说：“伙计们……”

<details>
<summary>Original English</summary>

**Speaker A**: Thanks for the plug. And obviously, when it comes to payments, who better than Stripe and maybe Jack Dorsey plays a role here. And and by the way, I think because capital I mean, if you think about that $17 billion equity contribution, what that technically means is Stripe is selling and Block is selling $17 billion of equity to the cash investors. That cash is then going to buy a PayPal. Therefore, Stripe and Block end up owning a piece of PayPal. The private equity investors own a piece of Block and Stripe. And what is not clear in the deal docs that were published cuz I don't think it's relevant to the public markets is who's actually going to operate PayPal post close. And my bet would be that they're going to hand it over to the Stripe guys and say you guys

</details>

**Speaker C**：我觉得这很明显。是的。因为他们是最有资格的，而且他们将在其中拥有最大的利益。呃，你……

<details>
<summary>Original English</summary>

**Speaker C**: I think that's clear. Yeah. Because they're the most qualified and they will have the biggest stake in it. Uh you're

</details>

**Speaker A**：所以我想我会做一个预测。我认为eBay和PayPal可能只是一波巨型交易浪潮的开始，在这波浪潮中，那些你可以称之为疲软的数字企业将被复兴。在充沛的资本支持和合适的运营者的共同作用下，我认为这可能会成为一场巨大的……

<details>
<summary>Original English</summary>

**Speaker A**: so I think I so I I will make a prediction. I think that eBay and PayPal are probably the beginning of a wave of mega deals of call it flaccid, you know, digital businesses that can be revived, okay, with the blue chew of capital and the right operator and I think that there's probably a big

</details>

**Speaker C**：一场巨大的浪潮即将到来。

<details>
<summary>Original English</summary>

**Speaker C**: a big wave of this to come.

</details>

**Freeberg**：另一件事是，这可能不是最终的结算价格。我认为价格可能会比现在的水平再高出10%到15%。并且我要说的是，某个人必须非常仔细地考虑提出一个有竞争力的报价。哦，一个某某人，他的指纹可能还留存在最初的PayPal上，他可能也有四五万亿的市值可以运作，而且他最近刚刚完成了一笔600亿美元的收购。我们这里可没有什么内幕消息。

<details>
<summary>Original English</summary>

**Freeberg**: The other thing is this is probably not the final clearing price. I think the price is probably another 10 to 15% higher from here. And and I will say that there is a certain individual that must look very closely at putting in a competitive bid. Oh, a certain individual who may may have his fingerprints on the original PayPal who might also have $4 or5 trillion in market cap to play with who also made a $60 billion acquisition recently. We don't have inside information here.

</details>

**Speaker B**：说到你的观点，Freeberg，

<details>
<summary>Original English</summary>

**Speaker B**: To your point, Freeberg,

</details>

**Freeberg**：对吧？

<details>
<summary>Original English</summary>

**Freeberg**: correct?

</details>

### 新的并购剧本

**JL**：这正在成为一种剧本。有一家叫Bending Spoons的公司刚刚上市。他们买下了一堆非创始人领导的资产。以14亿美元收购了AOL，以14亿美元收购了Vimeo，还有WeTransfer、Eventbrite、Bright Code等，都是他买的。

<details>
<summary>Original English</summary>

**JL**: This is becoming a playbook. There's a company called Bending Spoons that just went public. They bought a bunch of non-founderled assets. AOL for 1.4 billion, Vimeo for 1.4 billion, We Transfer, Eventbrite, Bright Code with him.

</details>

**Speaker D**：我刚才还在私信他。

<details>
<summary>Original English</summary>

**Speaker D**: I was just DMing with him.

</details>

**JL**：他太厉害了。我和这家伙一起出去玩过。他绝对是个可怕的运营杀手。他买下了Evernote。

<details>
<summary>Original English</summary>

**JL**: He's He's awesome. I've hung out with this guy. This guy is an absolute freaking operational killer. He he bought Evernote.

</details>

**Speaker E**：对。在米兰。

<details>
<summary>Original English</summary>

**Speaker E**: Yeah. In Milan.

</details>

**JL**：是的，他完全在米兰运营这一切。他买下Evernote后直接介入，对这些企业进行诊断。他会问：“你们在什么地方超支了？又在什么地方投入不足？你们在产品上做错了什么？在营销上又做错了什么？”然后他就会不可思议地把问题解决掉。他就是一个杀手，他接手了所有这些所谓的Web 2.0时代的知名企业，让它们重新焕发活力，把它们打包整合，让它们像印钞机一样赚钱，并降低运营成本。

<details>
<summary>Original English</summary>

**JL**: And yeah, he runs the whole thing from Milan. He bought Evernote and he just goes in and he diagnoses these businesses. He's like, "How are they being over where are you overspending? Where are you underpending? what are you doing wrong with the product and what are you doing wrong with marketing and he just faking fixes it and he's just a killer and he's taken all of these what were called web 2.0 I know businesses and he's revitalized them, rolled them up and printing cash out of them and leverage the cost to run them lower.

</details>

**Speaker F**：听我说的意思，他正在使用年轻的、具备“AI优先”思维的高管。

<details>
<summary>Original English</summary>

**Speaker F**: He's using young AI first executives from what I'm talking

</details>

**Speaker G**：完全同意。这是一个很好的指出，JL。就像Bending Spoons是这种战略的集合体一样，但对于这些超大型交易，我认为未来还会有更多。我想说的是，我们过去几年一直在讨论的最重要的一点是，在Lina Khan的怒火下，风险投资在过去几年里一直处于困境。然后特朗普一当选，所有从事企业发展的高管都说：“嘿，看来并购（M&A）又重新回到菜单上了。”现在我们看到一笔接一笔的交易达成，人们不再害怕做交易了。Uber今天刚收购了Delivery Hero，这会让他们的收入猛增20%。是的，尽管他们被稀释了10%，但这将使他们的收入激增24%左右，就是这么疯狂。我认为这将成为未来几年最大的故事，伴随着所有的这些流动性。我经常和有限合伙人（LP）以及家族办公室交谈，他们都在问：“嘿，你们的下一只基金什么时候发？嘿，下一笔交易是什么时候？”因为现在人们相信风险投资了，这得益于SpaceX的分配和所有这些并购。自从唐纳德·特朗普当选总统以来，我们有四五家公司被收购。感谢我们的总统唐纳德·J·特朗普把并购重新放回了菜单上。Sachs，并购又回来了。Sachs，你为什么不向PayPal出价呢？

<details>
<summary>Original English</summary>

**Speaker G**: totally. It's a great call out JL like bending spoons is the roll up of this sort of strategy but for these mega deals I think there's more of them to come. I will say uh you know the the high order bit here uh which we talked about for a couple years was venture capital was on the ropes for a couple of years under the wrath of Lena Khan and then once Trump got elected all the executives working in corporate development said hey looks like M&A's back on the menu and now we're seeing deal after deal after deal get consummated people are no longer scared of doing deals Uber just bought delivery hero today uh That's going to like jump their revenue by 20. Yeah. And that's going to jump their revenue by like they're getting diluted 10%. It's going to jump their revenue 24% or something crazy like that. And this is going to be I think the big story the next couple of years and all this liquidity. Talking to LPs and family offices, which I do on a regular basis, they're all like, "Hey, when's your next fund? Hey, when's the next deal?" Because now people are believing in venture because of the SpaceX distributions and all this M&A. And we have four or five companies that got bought since Donald Trump was elected president. Thank you my President Donald J. Trump for putting M&A back on the menu. Sachs M&A back on the menu. Why didn't you make a bid saxs for PayPal?

</details>

**Sachs**：曾经经历过，不想再重蹈覆辙。

<details>
<summary>Original English</summary>

**Sachs**: Been there, done that.

</details>

**Speaker G**：曾经经历过。好吧。

<details>
<summary>Original English</summary>

**Speaker G**: Been there, done it. Okay.

</details>

**Sachs**：不，但你看，你必须要有协同效应。

<details>
<summary>Original English</summary>

**Sachs**: No, but look, you have to have synergies.

</details>

**Speaker G**：曾有过那么一刻，大概是15年前，他们邀请Sachs回去当CEO。

<details>
<summary>Original English</summary>

**Speaker G**: There was a moment, this was like 15 years ago where they asked Sachs to go back and be the CEO.

</details>

**Sachs**：那是真的。我记得那是在一次扑克牌局上。是的，他和我立刻飞到拉斯维加斯，在那里度过了一个周末来考虑这件事。

<details>
<summary>Original English</summary>

**Sachs**: That was right. I remember that at the poker game. Yeah. He and I immediately flew to Vegas and spent the weekend there to think about it.

</details>

**Speaker H**：就像，你知道吗？

<details>
<summary>Original English</summary>

**Speaker H**: Like, you know what?

</details>

**Sachs**：我不是……不，他们没有要求我呃，但我当时……好吧，不，我从来没有收到过offer，但当时已经到了最后两名候选人什么的，而且是我和另一个人之间的竞争。实际上，他们最终选择了一些，你知道的，像传统的信用卡高管那样的人。老实说，这就是PayPal停滞不前的原因：早在2002年被收购时，他们基本上赶走了所有的创始人，剔除了所有的创始DNA，然后它就有点变成了由咨询顾问类型的人在管理。你必须记住，在那个时候它是被eBay收购的，而Meg Whitman曾在宝洁和迪士尼工作过，在贝恩待了八年，所以那是一种非常企业化的思维。我的意思是，在那个时代所有的互联网公司中，它绝对是最具企业官僚主义的，他们把PayPal的创始一代看作是一个麻烦，就像一群他们无法控制的牛仔。他们没有做出任何努力来留住这些人，而且我认为当这些人全部离开时，他们反而松了一口气。接着这就催生了“PayPal黑帮”，因为你知道，通常在一次收购中，你会把所有的人才都锁定下来，但在这种情况下……

<details>
<summary>Original English</summary>

**Sachs**: I wasn't No, they didn't ask me to uh but I was... Well, no, I I never got the offer, but it was down to like final two or something and it was between me and someone else. And actually, they ended up going with some, you know, like traditional like credit card executive. And to be honest, that's why PayPal has stagnated is that as soon as it was acquired back in 2002, they basically blew out like all the founders, all the founding DNA and it was just kind of run by, you know, consulting types. You got to remember at that time it was acquired by eBay and Meg Whitman had worked at Proctor and Gamble and Disney and she spent like eight years at Bane and it was like a very corporate mindset. I mean among all the internet companies of that era it was definitely the most corporatist and they saw the founders the founding generation at PayPal is just a problem just a bunch of like cowboys they couldn't control they made no effort to retain them and I think they were kind of relieved when they all left and then that's what created the PayPal mafia was that you know normally in an acquisition you'd lock up all the talent but in this case

</details>

**Speaker I**：他们把这些人锁在了门外。他们觉得：“这些人很难管理，赶紧换锁。”

<details>
<summary>Original English</summary>

**Speaker I**: they locked them out they're like these guys hard to manage change the keys

</details>

**Sachs**：我早就说过，叫它“PayPal黑帮”是用词不当。这实际上是“PayPal大流散”。

<details>
<summary>Original English</summary>

**Sachs**: I've said for a long time it's a misnomer to call it the PayPal mafia. It's really the PayPal diaspora.

</details>

**Speaker I**：完全赞同。

<details>
<summary>Original English</summary>

**Speaker I**: Totally.

</details>

**Sachs**：我们的家园被占领了，他们烧毁了我们的神庙，然后把所有人都赶了出去。

<details>
<summary>Original English</summary>

**Sachs**: Our homeland was taken over and they burned our temple and then kicked everybody out.

</details>

**Speaker I**：是的。

<details>
<summary>Original English</summary>

**Speaker I**: Yeah.

</details>

**Sachs**：这就是为什么整个“PayPal黑帮”会创办那些公司的原因。

<details>
<summary>Original English</summary>

**Sachs**: And that's why the whole PayPal mafia got started with all those companies.

</details>

**Speaker J**：但是，也正因为如此，

<details>
<summary>Original English</summary>

**Speaker J**: But as a result of that,

</details>

**Speaker K**：几十年来，我不会说任何人是受害者。那是……

<details>
<summary>Original English</summary>

**Speaker K**: for for decades, I don't say anyone's a victim. That's

</details>

**Speaker L**：听着，当你收购一家公司时，你有权决定如何处置那项资产。

<details>
<summary>Original English</summary>

**Speaker L**: Look, when you when you acquire a company, you get to decide what to do with that asset.

</details>

<!-- chunk 5/12 -->

### 收购传闻与PayPal的困境

**Speaker A**: 完全同意。这就是现实。但并没有人对此感到不满，大家都在想：“好吧，这给了我们继续前进的资本，我们将去追求下一个目标。”

<details>
<summary>Original English</summary>

**Speaker A**: Totally. So, I mean, that was just the reality. But it's not like, you know, I don't think anyone was bitter about it. They're all like, "Okay, this give us the capital to go. I'll do the next thing we want to do."

</details>

**Speaker B**: 顺便说一句，他们的新任CEO，恩里克（Enrique），真的很棒。我以前见过他，他们显然做得很好，这也是为什么他们可能收到这些收购要约的原因，因为在过去几年里，他们一直在收紧这项业务。

<details>
<summary>Original English</summary>

**Speaker B**: Well, the new CEO, by the way, Enrique, is really aces. Uh, I've met him before and they're doing a great job. Um, apparently, which is why they probably got these offers because they've been tightening that business up for the last couple years.

</details>

**Speaker C**: 不，他们得到这些报价的原因是其市值已经跌到了300多亿美元。我的意思是，这可是一家曾经价值2000亿美元的公司，不是吗？大概是。

<details>
<summary>Original English</summary>

**Speaker C**: Well, no, the reason they got these offers is the market cap is down to, you know, was down in the what, like 30 something billion. I mean, this is a company that was worth 200 billion, wasn't it? Roughly

</details>

**Speaker B**: 我记得最高点是3220亿。

<details>
<summary>Original English</summary>

**Speaker B**: 322, I think, was the peak.

</details>

**Speaker C**: 嗯。在这次收购报价之前，它已经跌到了300到400亿美元。所以它能吸引报价的原因是它的估值被打压得太惨了。现在的问题是，其他人还能用它做点什么吗？

<details>
<summary>Original English</summary>

**Speaker C**: Mhm. And before this offer, it was down to what 30 to 40 billion. Yeah. So the reason why it's attracting offers is it's so beaten up. And so now the question is, can anyone else do something with it?

</details>

**Speaker D**: 关于你提到的“必须产生协同效应”，在这个时代，任何优秀的运营者在这种情况下能带来的核心协同效应不就是人工智能吗？无论是这项业务还是其他业务，你都可以利用推动自动化、产品开发、组织内外效率提升的工具，使产品真正对用户更好，或者只要能被出色地执行就可以。

<details>
<summary>Original English</summary>

**Speaker D**: To your comment about you've got to have synergies. Doesn't it seem to be the case that in this era the the core synergy that any great operator can bring to the table in this sort of a scenario is AI? Like you can leverage whether it be in this business or others you can leverage tools that drive automation that drive product development that drive improvements and efficiencies across the organization that make the product actually better for the user etc etc that simply potentially obviously being well implemented.

</details>

**Speaker A**: 听着，我认为你必须有一个产品愿景，即你将如何使用人工智能来改善整个用户体验。确实，你只是可以使用人工智能来提高效率，这将提高你的盈利能力和收益。所以在财务层面上，你可以让收购发挥作用。但在我看来，PayPal面临的生存问题是，你要处理的是一个有25年历史的产品。这和我们在大约27年前创建的东西是一样的。它改变了一点，但没有那么多。问题在于那种交互模型已经过时了。所以，除非你有一个关于如何使其复苏和使该产品焕发活力的愿景，否则我认为，是的，它可能是一个不错的金融操作。

<details>
<summary>Original English</summary>

**Speaker A**: Well, look, I think you have to have a product vision of how you would use AI to make the whole user experience better. And yes, you're right that you could just use AI to drive efficiencies and that'll improve your profitability and earnings. And so on a financial level, you could make the acquisition work. But it seems to me that the existential issue for PayPal is that you're dealing with a product that's 25 years old. I mean, it's the same thing that we created back, you know, like 27 years ago. I mean, it's changed a little bit, but not that much. And the problem is that that that interaction model is legacy. And so, unless you've got a a vision of how to resuscitate it and rejuvenate that that product, I think, yeah, it could be a good financial play. Maybe

</details>

**Speaker B**: 我觉得他们是在收购这些账户。

<details>
<summary>Original English</summary>

**Speaker B**: I think they're buying the accounts.

</details>

**Speaker E**: 是的。查马斯（Chamath），你说的很有意思。因为对于Stripe来说，它拥有的优势在于他们拥有大量的商户，对吧？所以他们已经成为商户通过API接受付款的首选机制。我认为他们每年的交易额大约是两万亿。我觉得PayPal是1.7万亿。所以实际上，Stripe现在比PayPal还要大一点。但PayPal拥有而Stripe没有的，是消费者关系。你知道，超过4亿的活跃消费者账户。所以你说的对，查马斯，如果能以某种方式将商户关系与所有这些消费者账户结合起来，然后绕过信用卡网络，理论上就会有更多在自家网络上完成的交易。

<details>
<summary>Original English</summary>

**Speaker E**: Yeah. I mean, what you're saying, Jamoth, is Yeah. what you're saying is interesting because with Stripe, I mean, this is the advantage that Stripe has is that they have a ton of merchants, right? So, they've they've become the preferred mechanism for merchants to basically accept payments via APIs. And I think they're doing about two trillion a year of annual transaction volume. I think PayPal is doing 1.7. So, actually, Stripe is a little bigger than PayPal now. But the thing that PayPal has that Stripe doesn't really have is the consumer relationship. So, you know, over 400 million active consumer accounts. So, you're right, Jimoth, that if if somehow you could combine the merchant relationships with all those consumer accounts and then bypass the credit card networks cuz there'd be a lot in theory there could be a lot more on us transactions.

</details>

**Chamath**: 完全正确。那才是价值所在。PayPal已经拥有了Braintree。所以，现在你将Stripe和Braintree这两个本来是竞争对手的业务结合在一起，它们就不再是竞争对手了。然后，Block能提供给你的是整个销售终端的基础设施，并且你还得到了Cash App。所以你把它们都整合在一起，我认为这是向Visa和万事达卡（Mastercard）发出的一次警告。

<details>
<summary>Original English</summary>

**Chamath**: Exactly. And that's where the value is. PayPal already owns Brainree. So, now you have Stripe and Brainree that effectively were competitors that won't be. And then what block gives you is an entire point of sale infrastructure and you get the cash app. So you put it all together and I think it's a it's a shot across the bow for Visa and Mastercard.

</details>

**Speaker E**: 查马斯，你刚才提到的Braintree是另一个重要业务，因为这是一个非常强大的业务，你甚至可能都不知道PayPal拥有它。Venmo也是，它吸引了很多年轻人。所以你其实触及了两代人。你吸引了X世代和千禧一代。这能带来很高的投资回报率。

<details>
<summary>Original English</summary>

**Speaker E**: Brainree is the other one that I think you just mentioned there Chimath that's important because that is a very strong business that you don't even know that PayPal owns. Venmo is also that speaks to a lot of young people. So you're kind of getting two generations. You're getting Gen X and millennials. Uh a lot of bang for your buck there. Yeah,

</details>

**Speaker C**: 扎克（Zach）说得对。他们拥有足够多的资源，可以建立端到端属于自己的交易网络。

<details>
<summary>Original English</summary>

**Speaker C**: what Zach said is true. They have enough of the things to go end to end on their own rails.

</details>

**Speaker A**: 这是一个非常...

<details>
<summary>Original English</summary>

**Speaker A**: That is a very

</details>

**Speaker E**: 是的，问题是你是否能将其全部打包成消费者真正会选择的形式，因为说“好吧，我们把Stripe的商户关系和PayPal的消费者关系结合起来，我们不用信用卡了”是一回事。但如果消费者不想要那样呢？

<details>
<summary>Original English</summary>

**Speaker E**: Yeah, the question is whether you can package it all together in a way that the consumer will actually choose because it's one thing to say, well, we take the merchant relationships of Stripe and the consumer relationships of PayPal, we don't do that. But what if the consumer doesn't want that?

</details>

**Speaker C**: 不，你不能那样做。我认为你应该做的是，去找所有使用Stripe的商户，对他们说：“我们会给你们3%、4%或5%的折扣”，他们会说：“好的。”这样你就会看到价格在各个地方下降。想象一下，如果Shopify对他们所有的商户说，好的，你们有两个选择，老方法还是新方法。新方法，你们能多把2%、3%或4%的利润装进口袋。他们当然会选择新方法。

<details>
<summary>Original English</summary>

**Speaker C**: No, you don't do that. I think what you do is you go to places like all of the merchants that use Stripe and say, "We'll give you a 3 or four or 5% discount and they'll be like, "Okay." And so you'll see these prices that just, you know, fall everywhere. Like imagine if Shopify was like to all their merchants, okay, you have two choices, the old way or the new way. The new way, you put another two or three or 4% in your pocket. Of course, they're going to pick the new way.

</details>

**Speaker E**: 这是现代并购的悖论。你知道，如果你从保护消费者的角度来看，这最终对消费者是非常有利的。这将降低价格。他们收购这个并不是为了……

<details>
<summary>Original English</summary>

**Speaker E**: Well, and this is the paradox of like modern M&A. You know, if you look at protecting the consumer, this will ultimately be great for the consumers. This is going to lower the prices on it. They're not buying this to

</details>

**Speaker C**: 好的，你说的很有趣。如果这真的发生了，对消费者来说太好了。这就是为什么如果这件事发生在两年前……

<details>
<summary>Original English</summary>

**Speaker C**: Okay, you're saying something really interesting. It is so good for consumers if this were to happen. This is the exact reason why if this had happened two years ago,

</details>

**Speaker E**: 是的。

<details>
<summary>Original English</summary>

**Speaker E**: yeah,

</details>

**Speaker C**: 这在反垄断审查中就等同于一次肠道检查。我的意思是，天哪，两年前你甚至连碰这笔交易的边儿都不可能。

<details>
<summary>Original English</summary>

**Speaker C**: this would have been the antitrust equivalent of a coloctyl exam. I mean, oh god, you would not even get one step close to doing this deal two years ago.

</details>

**Chamath**: 嗯，这确实很有意思。反垄断的核心问题是你如何定义市场。因此，如果你将市场定义为商户API，那么杰森（JCal），这就是Stripe对阵Braintree。然后政府会说，那是不能合并市场份额的。

<details>
<summary>Original English</summary>

**Chamath**: Well, that's that's really interesting actually. I mean, the key question with antitrust is how do you define the market? And so, if you define the market as, you know, APIs for merchants, then JCAL, it would be Stripe versus Brainree. And then the government would say, well, that's you can't consolidate share.

</details>

**Speaker C**: 然而，如果真正的市场是Visa和万事达卡，那是终极双头垄断。如果PayPal能为那个市场增加竞争，而那个市场比API市场大得无可估量……

<details>
<summary>Original English</summary>

**Speaker C**: However, if the real market is Visa and Mastercard, that's the ultimate duopoly. And if PayPal can add competition to that market, which is infinitely larger than APIs.

</details>

**Chamath**: 完全正确。

<details>
<summary>Original English</summary>

**Chamath**: Exactly.

</details>

**Speaker C**: 那么它实际上就是促进竞争的。因此，你如何定义市场决定了它是反竞争还是促进竞争的。而且那些人足够聪明，他们读过足够多的书，不会把这件事搞砸。

<details>
<summary>Original English</summary>

**Speaker C**: Then it's actually pro competitive. So how you define the market determines whether it's anti-competitive or prompetitive. And those guys are smart enough and they've read enough books where they won't [ __ ] this one up.

</details>

### 苹果起诉OpenAI涉嫌窃取商业机密

**Jason (JCal)**: 好的，让我们进入下一个话题。有人在起诉OpenAI。这次是苹果。7月10日，苹果针对OpenAI提交了一份41页的诉讼，指控其涉嫌窃取商业机密。苹果称OpenAI窃取了他们的知识产权来开发其消费者硬件设备。还记得我们在流动性（Liquidity）活动上有莎拉·弗里尔（Sarah Frier），我向她询问了这个新设备，她说它非常人性化且招人喜爱。她给我们透露了一点内幕。嗯，结果苹果指控这可能部分是他们的知识产权。苹果前iPhone设计副总裁唐·坦（Tang Tan）现在是OpenAI的首席硬件官。据称，他指示在OpenAI面试的苹果求职者带上所谓“实际零件”去面试，进行所谓的“展示和讲解”。前苹果高级技术工程师钱古（Changu）给一位仍在职的苹果同事发了这样一条短信：“哈哈，我发现我可以访问网络存储了。太搞笑了。”在这一切发生的同时，OpenAI在过去一两年里从苹果挖走了400多名员工。非常庞大的挖角数量。苹果和蒂姆·库克（Tim Cook）已经受够了，查马斯。蒂姆·库克开了绿灯。尽管这听起来很疯狂，山姆·奥特曼（Sam Altman）还是找到了，找到了坑害又一个合作伙伴的方法。他坑了埃隆（Elon），他最初的恩人。查马斯，如果你没记错的话，iPhone的人工智能默认选项本来应该是ChatGPT。所以他们利用了这种关系，山姆利用了这种关系让他成为了最重要的AI平台（即iPhone）的默认选项，而现在这却演变成了一场大规模诉讼。你对此有什么看法？

<details>
<summary>Original English</summary>

**Jason (JCal)**: All right, let's get to the next topic. Somebody else is suing Open AI. This time it's Apple. On July 10th, Apple filed a 41page lawsuit against OpenAI over alleged alleged stolen trade secrets. Apple says Open AI stole their IP to develop their consumer hardware device. Remember, we had um Sarah Frier at Liquidity and I uh probed her on this new device and she said it was very human and lovable. She gave us a little bit of the goods. Well, it turns out Apple is alleging that maybe this is partially their IP. Tang Tan, Apple's former VP of iPhone design, is OpenAI's chief hardware officer. He allegedly directed Apple job candidates interviewing at OpenAI to bring quote actual parts to interviews to quote show and tell in the interviews. Changu, former Apple senior technical engineer, sent this text message to a still employed Apple colleague. Quote, "lol, I found out I can access the network storage. So funny." During all of this, OpenAI has poached over 400 Apple employees over the last year or two. Big numbers of poaching. Apple and Tim Cook have seen enough chimoth. Tim Cook green lit this. As insane as this is, Sam Waltman has found a way found a way to screw yet another party. Screwed Elon, his first benefactor. Chimati, if you remember correctly, the default for iPhone AI was supposed to be chat GPT. So they took this relationship, Sam took this relationship where he got to be the default on the most important platform for AI, the iPhone, and now it's wound up in a massive lawsuit. What are your thoughts on this?

</details>

**Chamath**: 在硅谷的25年里，我还没怎么见过苹果如此好诉讼。所以这对OpenAI来说显然是一个令人担忧的数据点。在这些事情上，他们更多是被动反应，而不是主动出击。所以，肯定是发生了什么非常非常让他们生气的事情。

<details>
<summary>Original English</summary>

**Chamath**: I haven't really seen Apple very latigiously in 25 years in Silicon Valley. So that's obviously a concerning data point for OpenAI. They're very reactive more than they are proactive on these things. So, there must have been something that really really upset them.

</details>

**Jason (JCal)**: 极其恶劣。是的。

<details>
<summary>Original English</summary>

**Jason (JCal)**: Egregious. Yeah.

</details>

**Chamath**: 所以，我不知道。这得靠法庭来理清。我不太想八卦，因为谁知道到底发生了什么，谁说了什么等等，但任何人都绝不应该从前雇主那里偷东西。任何人都不行。

<details>
<summary>Original English</summary>

**Chamath**: So, I don't know. It's going to take a court to sort this out. I don't really want to gossip because like who knows what's actually going on and who said what and blah blah blah, but nobody should be stealing things from their former employer. Nobody.

</details>

**Jason (JCal)**: 这是显而易见的。

<details>
<summary>Original English</summary>

**Jason (JCal)**: Obvious.

</details>

**Chamath**: 这是绝对不被允许的。这是显而易见的。这些人非常非常聪明，也非常成功。你知道，这可能就是OpenAI想要他们的原因，也是他们招募这些人的原因，然后你……

<details>
<summary>Original English</summary>

**Chamath**: You're just not allowed. It's just obvious. These people are very, very smart and they're very successful. And you know that's why OpenAI probably wanted them and that's why they wanted them you know and you

</details>

<!-- chunk 6/12 -->

### 关于商业机密与离职带走IP的争论

**Chamath**: 你只需要带着你所积累的集体智慧去他们那里，我认为这就足够了。你不需要这么做，尤其是作为一个资深人士。所以我只是希望这些事情不是真的，因为我不认为 Sam、Sarah 或者那里的任何其他任何人试图诱导这种情况发生。我不这么认为。

<details>
<summary>Original English</summary>

**Chamath**: come to them with the collective wisdom of what you've accumulated and I think that's sufficient. You don't need to especially as a senior person do this. So I just hope that this stuff isn't true because I think I don't think that Sam or Sarah or anybody else there are trying to induce this to happen. I don't think so.

</details>

**Moderator**: 是的，我怀疑他们是否有意诱导，但我确实相信这是真的，否则苹果就不会提起诉讼了。Sacks，当我们看到这个事情时，也许你想的话可以打开视野来谈谈，或者你也可以谈得很具体，但从本质上来说我们拥有一个自由市场，加州通常也没有竞业禁止协议，你可以随时随地去你想去的地方，但我们确实遇到过这样的例子，你知道，Waymo 那个著名的案子，你知道他们带了一些知识产权去了 Uber，当时 Travis 和他的团队说，离开这栋大楼，你的工作被取消了，你不能把这些信息带到这里来。在这个案子中，似乎也许他们没有刻意诱导，但这种情况确实发生了一段时间。所以，请从宏观的角度给我们讲讲你认为这里发生了什么，以及它对整个行业意味着什么。

<details>
<summary>Original English</summary>

**Moderator**: Yeah, I doubt they induced it but I do believe that it's true or Apple wouldn't have brought it. Sachs when we look at this maybe you could open the um aperture here if you want or you can just go very detailed but the nature of we have a free market we don't have non-competes in California generally speaking you can just employment at will go where you want but we have had instances you know whimo famously uh you know brought some IP to Uber when they did Travis and the team said leave the building your job is rescinded you don't get to bring that information here. In this case, it seems maybe they didn't induce it, but it occurred for some period of time. So, take us through big picture what you think is going on here and what it means for the industry.

</details>

**Sacks**: 嗯，就像 Chamath 说的，我完全不知道这里发生了什么。我的意思是，这只是一场诉讼。所有的事实都只是指控。我们还不知道真相。这件事将由法院来裁决。所以我真的不想对这里发生的事情发表意见。但是，如果人们想知道如何避免这类纠纷的非常简单的经验法则，那就是当员工离开前一家公司并加入新公司时，千万不要带走任何东西。

<details>
<summary>Original English</summary>

**Sacks**: Well, like Jamas said, I have no idea what's going on here. I mean, these this is a lawsuit. The facts are all alleged. We don't know. It's going to be adjudicated. So, I really don't want to opine on what happened here. But if people want to know a very simple rule of thumb for how to avoid these types of disputes is just when an employee leaves their previous company and joins the new company, just don't take anything with you.

</details>

**Moderator**: 你能带到新工作的唯一东西就是你脑子里的知识。

<details>
<summary>Original English</summary>

**Moderator**: The only thing you can bring to your new job is what's in your head.

</details>

**Sacks**: 你的记忆。

<details>
<summary>Original English</summary>

**Sacks**: Your memories.

</details>

**Moderator**: 你的记忆。那没问题。不管你脑子里有什么，你都可以带走。但是绝不能带走其他任何东西。

<details>
<summary>Original English</summary>

**Moderator**: Your memories. That's fine. Whatever is in your head, you're allowed to take. But never leave with anything else.

</details>

**Sacks**: 不能带 U 盘，不能带 CD，不能带文档，什么都不行。

<details>
<summary>Original English</summary>

**Sacks**: No thumb drives, no CD, no documents, no nothing.

</details>

**Moderator**: 只能带你脑子里的东西就没问题。Friedberg，对于 OpenAI 似乎越积越多的诉讼案，你有什么想法吗？运气不好？

<details>
<summary>Original English</summary>

**Moderator**: Just what's in your head is okay. Fraberg, any thoughts here on just the number of lawsuits that seem to be piling up over at Open AI? Bad luck.

</details>

**Friedberg**: 几个点连成一条线，我想是这样的。

<details>
<summary>Original English</summary>

**Friedberg**: Couple dots make a line, I guess.

</details>

### AI 模型的数据泄露与隐私危机

**Moderator**: 好吧，就是这样。说得非常好。几个点连成一条线。好吧，本周 SpaceX 发生了数据泄露。他们在 5 月底推出了 Grok Build 的公开测试版。最新的代码模型 Grok 4.5 驱动了 Grok Build。我一直在玩它。它非常出色。这是一个在 Cursor 内部工作的代码工具。呃，SpaceX 之前告诉用户，Chamath，在会话期间，你代码库中的任何内容都不会传输到 xAI 的服务器上。但实际发生的情况是，根据报告，每次开发人员使用 Grok Build 时，该工具都会在不提醒用户的情况下，将他们的整个代码库发送到 SpaceX 的云服务器上，不仅仅是执行特定代码任务所需的那些文件，而是所有的东西，密码、API 密钥可能都被上传到那里了，所有的修改日志等等。呃，隐私设置本来是应该阻止这种情况的，但它没有起作用。SpaceX 在 7 月 13 日悄悄地通过在他们的服务器上拨动开关，禁用了这个上传功能。埃隆·马斯克，我们播客的朋友，在 X 上承诺之前所有上传的数据都已经被删除了，我想应该是这样。呃，作为回应，SpaceX 开源了 Grok Build。那是他们的测试工具。所以，这是开源社区和 AI 主权的又一个开源胜利或胜利。你对此有什么想法吗？显然，这不是故意的，但就像我们过去几个月在 All-In 播客中一直讨论的那样，对于这些模型来说，信任非常重要。

<details>
<summary>Original English</summary>

**Moderator**: Okay, there you go. Very well said. Couple of dots make a line. Okay, SpaceX had a data leak this week. They launched Grock Build in public beta at the end of May. The newest coding model, Grock 4.5, powers Grock build. I've been playing with it. It's extraordinary. It's a coding tool that works inside of Kurser. Uh, SpaceX previously told users, Shimoth, nothing from your codebase is transmitted to XAI servers during a session. But what actually was happening is every time a developer or according to reports used Grock build the tool was sending their entire codebase to SpaceX cloud servers out without alerting the users not just the files that were needed to do that specific coding task just everything passwords API keys could have got pulled up there all the uh change logs etc. Uh the privacy setting was supposed to stop this but it didn't work. SpaceX quietly disabled the upload on July 13th by flipping a switch on their servers. Elon Musk, friend of the pod, promised on X that all previously uploaded data has been deleted, I guess. Uh, and in response, SpaceX open-source rock build. That's their harness. So, that's another opensource win or win for the open-source community and AI sovereignty. You got any kind of thoughts on this? Obviously, this was not intentional, but trust is important uh with these models as we've been talking about for the last couple of months here on the All-In podcast.

</details>

**Chamath**: 实际上，我会把这件事与我本周早些时候在 CNBC 上发表的评论联系起来，而这又建立在 Alex Karp 前一周的评论之上。AI 中的隐私非常脆弱，也非常容易被破坏。这还是在优秀企业付出最大努力的情况下。比如，你知道，你可能因为性格怪癖而不喜欢埃隆，但他非常值得信赖。他过于透明了。所以，值得赞扬的是，他们立刻就关闭了它。但我的结论是，在 AI 领域潜伏着各种不明显的隐形数据泄露途径。因此，如果你认为你可以拨动 ZDR（零数据保留）开关——这是业界用来告诉你一切都会安然无恙的神奇术语，我认为答案和信息应该是：事情并不会安然无恙，因为你无法保证其中的任何一项。所以模型公司在给你这些零数据保留政策时，可能已经尽了最大努力。但我认为现实情况是，你正在不知不觉中泄露信息。尽管他们尽了最大努力，可能仍然存在一些他们自己都不知道的后门，直到像这个例子中那样被其他人发现。所以所有这些都说明你需要有一个分层的生态系统。你必须有第三方。听着，这对我来说可能很有偏见，因为这部分地反映了我们在 8090 为大型企业实施我们的软件工厂时所做的事情。但是它之所以运作得如此之好，正是因为这个原因。你需要一个独立的第三方层来连接这些模型，以管理这种风险，因为到处都是后门。

<details>
<summary>Original English</summary>

**Chamath**: I would actually connect this to my comments on CNBC earlier this week, which built on top of Alex Karp's comments the week before. Privacy in AI is very fragile and it's very brittle. And this is despite the best efforts of great businesses. Like, you know, you may not like Elon for personality quirks, but he is incredibly trustworthy. He's overly transparent. And so, to their credit, they shut it off immediately. But my takeaway is that there are all kinds of non-obvious data leak vectors lurking in AI. And so if you think that you're going to flip a ZDR switch, zero data retention, which is the magic term that the industry uses to tell you that everything's going to be okay. I think the answer and the message should be it's not going to be okay because you can't guarantee any of it. So the model companies when they give you these zero data retention policies are probably trying their best. But I think the reality is you are leaking information where you don't know it. and they despite their best efforts may still have trap doors that they don't even know about until it's figured out by somebody else like in this example. So all of this speaks to you have to have a stratified ecosystem. You have to have third parties. Now look that's very biased for me because it's in part what we do for large enterprises at 8090 when we implement our software factory. But the reason why it's working so well is this exact reason. You need an independent third party layer to interface to these models to manage this exposure because there are trap doors everywhere.

</details>

**Moderator**: 这就是 Sacks 在一篇非常有趣的博客文章中所说的。你们看到了吗？

<details>
<summary>Original English</summary>

**Moderator**: And that's what Sachi just said in a really interesting blog post. Did you guys see that?

</details>

**Friedberg**: 是的。

<details>
<summary>Original English</summary>

**Friedberg**: Yeah,

</details>

**Chamath**: 我认为那写得非常出色。

<details>
<summary>Original English</summary>

**Chamath**: I thought that was excellent.

</details>

**Sacks**: 反向信息悖论。

<details>
<summary>Original English</summary>

**Sacks**: The reverse information paradox.

</details>

**Friedberg**: 是的。

<details>
<summary>Original English</summary>

**Friedberg**: Yeah,

</details>

**Chamath**: 那正是他得出的核心结论。他是在 Alex Karp 假设的崩溃论点上进行扩展的。你知道 Karp 提出的观点是关于有技术能力的企业希望控制他们的计算模型、权重、数据和超额收益（alpha）。但是他把这个想法进一步深化了。我的意思是，他从 Karp 的想法开始，然后他给出了一个秘诀，一个让企业如何将其落地运作的路线图。他说的是，企业必须建立一个真正的信任边界，将私有评估、租户内部专有的学习循环、解耦编排以及对自己输出内容进行微调的明确权利结合起来。所以他罗列了一系列相当技术性的事情，企业应该做这些事情，以实现 Karp 所说的企业真正想要的对其 AI 计算模型、数据及其超额收益的运营控制。所以这真的很有趣。我想现在这些公司的领导者之间正在进行一场虚拟的、几乎像大学宿舍里的头脑风暴会议，他们在集思广益讨论其中的一些概念，并在此基础上进行扩展。对吧。

<details>
<summary>Original English</summary>

**Chamath**: that's exactly the the takeaway that he left with. He was building on Alex Karp's supposed crash out. You know the point that Kart made about how enterprises who have technical ability want control over their compute models, weights, data and alpha. But he he went further with that idea. I mean he started with Karp's idea but then he kind of provided a recipe a road map for how enterprises should operationalize that. And what he says is that enterprises they have to establish a real trust boundary with private eval proprietary learning loops inside the tenant decoupled orchestration and the explicit right to fine-tune their own outputs. So he kind of goes through a litany of fairly technical things that enterprises should do in order to achieve the operational control that Karp was saying that enterprises really want over their AI compute models and data their alpha. So it's really interesting. I think now there's you know a virtual almost like college dorm session going on between the leaders of these companies who are brainstorming some of these concepts and now extending them. Right.

</details>

**Sacks**: 而且现在发生的情况是，你开始看到某种不算是联盟、但像是一个生态系统的形成，它试图创造一种替代方案，以取代单一封闭的模型堆栈，这正是 Anthropic 和某种程度上的 OpenAI 想要去往的方向，他们希望你被锁定在他们的技术堆栈中，使用他们的模型、他们的工具，他们控制数据等等所有这些，而现在你开始看到所有这些不同的公司……

<details>
<summary>Original English</summary>

**Sacks**: And what's happening is you're starting to see the formation of not really an alliance but like an ecosystem that is trying to create alternatives to you know a monolithic closed model stack which is where anthropic and to some extent open AAI want to go is they want you to be locked in to their to their stack right their models their harness they control the data all you know all of that and now you're starting to see all these different companies

</details>

### AI 模型的代币成本之争

**Chamath**: 并且为了让他们这么做的特权，你还要支付巨额的溢价，这更是荒唐透顶。所以，我看到了这些数据，Nick，也许你能找到这段相关视频。我希望你找到的相关视频是，Ramp 的 CEO Eric Glyman，我想他今天上了《Squawk Box》节目，谈论了一项新功能，你可以通过 Ramp 卡管理员工的代币最大使用量。但我看到的数据是，在 Fable 上一百万个代币大概是……Sacks，56 美元。从 Soul 那里获取一百万个大概是 26 美元，这和 Quad 48 是一样的。而在 Grok 上输入一百万个代币只需要大约 1.50 美元。

<details>
<summary>Original English</summary>

**Chamath**: and you pay a huge premium for the privilege for them to do it, which is even more insane. So, I I saw this data and Nick, maybe you can find this companion clip. The companion clip I'd like you to find is Eric Glyman, who's the CEO of RAMP, was on Squawkbox, I think today, talking about a new feature where you can manage the token maxing of your employees through your ramp card. But the data that I saw was that a million tokens on Fable is about sachs 56 bucks. A million from soul is about 26 bucks which is the same as quad 48. A million input tokens from on Gro is about $1.50.

</details>

**Moderator**: 好的。

<details>
<summary>Original English</summary>

**Moderator**: Okay.

</details>

**Chamath**: Z 大约是 1.50 美元。埃隆的大约是 1 美元，而中国的模型是 50 美分。

<details>
<summary>Original English</summary>

**Chamath**: Z is about a $150. Elon's about a dollar and the Chinese models are 50.

</details>

**Chamath**: 哇。所以在整个数据主权让你失去竞争优势的基础上，你能想象你还要为了承担这种风险，为每一百万个输入代币额外支付 56 美元吗？这真是疯了。

<details>
<summary>Original English</summary>

**Chamath**: Wow. So on top of the whole data sovereignty bleeding your alpha away, can you imagine that you're paying 56 bucks as well per million input tokens for that risk? That is insanity.

</details>

**Moderator**: 我在使用 Perplexity 计算机，他们已经开始支持 Grok，并且已经支持了 GLM52。所以当你比如使用 Claude 或 OpenAI 时，你只能使用他们的模型。于是我开始尝试折腾这些不同的模型，我给了它基本上完全相同的产品需求文档（PRD），我说我想做一个支持深度链接的播客播放器。所以，就像我们如果谈论，我不知道，Mythos（神话），它就会跨越所有不同的科技和商业播客，把所有关于 Mythos 的片段都给我播放出来，但会整合成一个信息流。我就觉得，这对于我准备节目会非常有帮助，而且也会很有趣。我试着做了一下。花了几个小时。在新的 Grok 上花了 11 美元。它如此便宜，简直可笑。

<details>
<summary>Original English</summary>

**Moderator**: I'm using perplexity computer and they started supporting Grock and they already support GLM52. So when you're like you're using Claude or OpenAI, you can only use their model. So I started effing with the different models and I gave it all the same basically PRD and I said I want to make a podcast player that deep link. So, like if we were talking about, I don't know, Mythos, it would play me all the miso methos clips across all the different tech and business podcasts, but make it into one stream. And I was like, this would be like really helpful for me for prepping for the show and just be interesting. I did it. It took a couple of hours. It cost $11 on the new Grock. It was hilarious how cheap it was.

</details>

<!-- chunk 7/12 -->

### Token Spend Management and Misaligned Incentives

**Speaker A**: 此外，我不知道你是否看到了——

<details>
<summary>Original English</summary>

**Speaker A**: And then adding to this, I don't know if you saw

</details>

**Speaker B**: 抱歉，你有没有试过在 Fable 上做，看看它到底贵多少？

<details>
<summary>Original English</summary>

**Speaker B**: Sorry. Did you try to do it on Fable to see how much more expensive it was?

</details>

**Speaker A**: 我没有。我没有，因为我 200 美元账户上的 Fable 积分用光了。所以，你知道，看看这个片段。Nick，放一下 Eric Glenn 的那个片段。那挺有意思的。

<details>
<summary>Original English</summary>

**Speaker A**: I didn't. I didn't because I was out of Fable credits on my $200 account. So, you know, look at this clip here. Nick, play the clip from Eric Glenn. That's kind of interesting.

</details>

**Eric Glenn**: 我们很高兴今天能推出 Token 支出管理功能。它对 RAMP 和非 RAMP 客户都开放。

<details>
<summary>Original English</summary>

**Eric Glenn**: We're thrilled to be launching token spend management today. It's available to RAMP and non-RAMP customers.

</details>

**Speaker A**: 他说得完全正确。在过去一年里，我今天早上看了一下数据，RAMP 客户的 Token 支出增长了 21 倍。

<details>
<summary>Original English</summary>

**Speaker A**: And he's exactly right. Over the last year, I looked at the stats this morning, token spend among RAMP customers has grown by 21 times.

</details>

**Speaker C**: 21 倍。

<details>
<summary>Original English</summary>

**Speaker C**: 21 times.

</details>

**Speaker A**: 21 倍。

<details>
<summary>Original English</summary>

**Speaker A**: 21 times.

</details>

**Speaker C**: 不是 21%，我们说的是 21 倍。

<details>
<summary>Original English</summary>

**Speaker C**: Not 21%, we're talking about 21 times.

</details>

**Speaker A**: 完全正确。所以，作为一名首席财务官（CFO），差个几美分实际上可能还不错。照目前的速度发展下去，可能会差上好几美元。而且听着，我觉得对于许多 CFO 来说，他们经常对账单感到非常惊讶，因为 AI 公司实际上建立的机制是，你有一个账单，你可以随心所欲地花钱。CFO 很难主动看到人们到底在把钱花在哪里，而且每次他们推出新模型时，费率往往都会上涨，所以这里的激励机制非常错位。因此，我们正在努力做的一部分工作，就是让 CFO 们能够轻松看到支出、理解支出，并控制支出。

<details>
<summary>Original English</summary>

**Speaker A**: That's exactly right. So being off by a few pennies as a CFO actually might be quite nice. At the rate it's going, it might be several dollars. And look, like I think that for many CFOs, they're often very surprised by the bill because what the AI companies have functionally set up is you have a tab. you can spend as much as you want. It's very hard for CFOs to see proactively what people are spending on and every time they're introducing new models, the rates often go up and so there's very misaligned incentives. So part of what we're trying to do is make it easy for CFOs to see the spend, understand the spend, and control it.

</details>

**Speaker C**: 谢谢你，Nick。他在那里说了一件非常重要的事情，因为如果你的工程师在没有引导的系统里随机操作，然后以 56 美元的价格烧掉一百万个 Token，他所谈论的最终会对盈利产生下游影响。而且最终，很多这些公开市场的 CFO 会来到华尔街，然后他们将错过盈利预期，因为在某个时候他们的运营支出超标了。如果事情每几个月就增长 21 倍，总有人会错过某个季度的预期。我不知道是谁，但肯定会有人。而且它不仅会是，你知道，我原本推测可能就是这里或那里差个几美分，他们得解释说是因为 Token 支出的原因。他说按照这个速度，它可能会高达几美元，这也可能是真的。我认为我们都在试图表达的观点是，除非你控制住这一点，并且能够直接说出你赚了多少钱，否则这就只会是一条死路。这就是一个烧钱的熔炉。

<details>
<summary>Original English</summary>

**Speaker C**: Thanks, Nick. He's saying something so important there because if your engineers are going off randomly in an unguided system and then just ripping through million tokens at 56 bucks, what he's talking about is the eventual downstream impact to earnings. And that eventually a bunch of these public market CFOs are going to show up to Wall Street and they will have missed earnings because they're upex at some point. If things are 21xing every few months, somebody's going to miss a quarter. I don't know who, but somebody. And it's not just going to be, you know, I was speculating it'll be a few pennies here or there, which they'll have to say is because of token spend. He's saying it could be as much as dollars at this rate, which also could be the case. I think the point that we're all trying to make is unless you get a control of this and you can directly say how much money you're making, this is a bridge to nowhere. It is a money burning furnace.

</details>

### The Market Opportunity in Open Models

**Jason**: 好消息是，这一切正在创造一个巨大的市场机会。Sachs，Bit Tensor，Subnets，托管 Grock 4.5 的 GLM52。现在——

<details>
<summary>Original English</summary>

**Jason**: The good news is this is all creating a massive market opportunity. Sachs, Bit Tensor, Subnets, GLM52 hosting Grock 4.5. Now

</details>

**Speaker A**: 在 Inkling 中，Inklink 镜像了 Marott 的新模型，现在每个人都在说，“嘿，等一下。我能给你一个更好的价格。你现在付两美元。我能给你一美元。这是——”

<details>
<summary>Original English</summary>

**Speaker A**: in Inkling, Inklink mirror Marott's new model in everybody's now saying, "Hey, wait a second. I can give you a better deal. You're paying two bucks. I can get you one buck. This is

</details>

**Jason**: 不，不。人们现在支付的是 26 到 56 美元。他们本应该支付 50 美分。

<details>
<summary>Original English</summary>

**Jason**: No. No. People are paying between 26 and 56 bucks. They should be paying 50 cents." Exactly.

</details>

**Speaker A**: 好吧，你知道，而且——

<details>
<summary>Original English</summary>

**Speaker A**: Well, you know, and

</details>

**Speaker D**: Inkling 的公告挺有意思的，因为我认为那里的价值主张是，她明确表示，看，我们不是前沿智能。我们就在那之下，但我们是一个用于微调这些开源模型的平台，而这些开源模型要便宜得多得多，然后你可以基于微调达到你想要的结果。所以那非常有趣。

<details>
<summary>Original English</summary>

**Speaker D**: the Inkling announcement was kind of interesting because I think the value prop there is she's explicitly saying that look, we're not frontier intelligence. We're just under that, but we're a platform for fine-tuning these open models which are much much cheaper and then you can achieve the result you want based on fine-tuning. And so that's really interesting.

</details>

**Jason**: 是的。但是，你知道，如果 Anthropic 得逞的话，这些开源模型就不会存在太久。

<details>
<summary>Original English</summary>

**Jason**: Yeah. And uh but you know these open models won't be around for very long if Anthropic has its way.

</details>

**Speaker D**: 他们想阻止它是原因的。这只是因为他们拥有如此大的垄断地位。

<details>
<summary>Original English</summary>

**Speaker D**: There's a reason they want to stop it. It's just they have such a monopoly.

</details>

**Jason**: 你的大部分产品每百万个 Token 卖 50 美分，而他们自己的卖 56 美元，这当然了。你当然不希望那种事情发生。你当然希望他们……你想试图阻止它。

<details>
<summary>Original English</summary>

**Jason**: Of course you're selling most of the product for 50 cents per million tokens when they're selling theirs for 56 bucks. Of course you don't want that to happen. Of course you want them you want to try to stop it.

</details>

**Speaker A**: 但话虽如此，他们仍然在疯狂增长。只是为了澄清一点，我的意思是，是的，你知道，你看到开源模型正在发生这种爆炸性的有趣事情，就像你说的，最新构建的是开源的，思维机器也是开源的，等等等等，但是——

<details>
<summary>Original English</summary>

**Speaker A**: But that being said, they're still growing like crazy. Just to be clear, I mean, yes, you know, you are seeing this explosion of interesting things happening with open models like you said, you know, the latest rock build is open, thinking machines open and so forth and so on, but still

</details>

**Jason**: 我的意思是，他们还在增长。在收入增长方面，他们仍然是行业领导者。所以，这些事情是同时发生的。而且——

<details>
<summary>Original English</summary>

**Jason**: I mean, they're growing. They're still the industry leader in terms of revenue growth. So, these things are happening side by side. And

</details>

**Speaker C**: 是的，我认为有趣的是，如果不是 CFO 们表示“我无法控制支出”，Eric 是不会发布这款 RAMP 产品的。

<details>
<summary>Original English</summary>

**Speaker C**: yeah, I would I think that the interesting thing is Eric would not have released this ramp product unless CFOs were like, I can't control the spend.

</details>

**Jason**: 是的。然后他就说，“好吧，给，让我为你构建它。” 然后，如果有足够多的 CFO 实际上开启了那个功能，并开始对支出进行速率限制，因为也许他们没有获得投资回报率（ROI），而工程师并不关心 ROI。工程师只会想，我要使用最新最好的模型。

<details>
<summary>Original English</summary>

**Jason**: Yes. And then he's like, "Well, here, let me build it for you." And then if enough CFOs essentially turn that feature on and start to rate limit how it's spent because maybe they're not getting the ROI and the engineer doesn't care about ROI. The engineer is like, I want to use the latest greatest model.

</details>

**Speaker C**: 是的。而且也许你并不需要它。也许 Mirror 说得对。对于 95% 的任务，你应该降低一个级别，尤其是当它的成本只有 1/100 时。但是工程师永远不会做出那种权衡，因为他们永远不想去考虑这个问题。你说得对。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah. And maybe you don't need it. Maybe Mirror's right. And for 95% of the tasks, you should be at one level lower, especially when it costs 1/100th of the cost. But the engineer will never make that trade-off because they'll never want to think about it. You're right.

</details>

**Jason**: 而且他们也不与金钱挂钩。CFO 是与金钱挂钩的，而工程师则想要在使用最新最好的东西上进行探索。

<details>
<summary>Original English</summary>

**Jason**: And also they're not tied to the money. The CFO is tied to the money and the engineer wants to go on an exploration on using the latest greatest thing.

</details>

**Speaker C**: 是的。如果你在预订你的旅行，你会说，你甚至都不看价格。你会说，“是的，只要给我订商务舱就行。给我订个好酒店。” 然后像是差旅部门会处理那些事情。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah. If you're booking your travel, you're like, you don't even see the price. You're like, "Yeah, just put me in business class. Put me in a nice hotel." And like the travel department handles that.

</details>

### The Impact of Local Compute

**Jason**: 你说了一件非常有趣的事情。如果让你猜的话，你觉得有多少 Fable 5 的提示词仅仅是那种本该在普通机器上运行的一般性任务？

<details>
<summary>Original English</summary>

**Jason**: You're saying something really interesting. What percentage, if you had to guess, of fable five prompts are just average Michigan that should be running.

</details>

**Speaker C**: 98%。98%。我把它用在了我本可以用 Quen 来做的愚蠢事情上。嗯，我想这是我在这里做出的微观预测。Mark German，他在苹果公司方面可以说是最懂行的了，他说，而且你知道，我们将迎来一位新 CEO 接替 John Furnus……

<details>
<summary>Original English</summary>

**Speaker C**: 98%. 98%. I was using it for stupid stuff that I could be using Quen for. Um I think this is my like micro prediction here. Mark German, who's like the most in then guy when it comes to Apple, he says, and you know, we got this new CEO coming in for um uh John Furnus.

</details>

**Jason**: 是的。

<details>
<summary>Original English</summary>

**Jason**: Yeah.

</details>

**Speaker C**: 他是一位硬件工程师。M7 Ultra，因为，我们现在用的是 M5 芯片。你可以获得大概 456、512 GB 的内存。他说 M7 Ultra 将支持多达 1.5 TB。这是他们已经支持的内存的两倍。所以，如果你想想前沿模型，比如上一代的模型，这就像是一个 Opus 级别的模型在你的 Mac Studio 上运行。你们都用 Mac Studio，你们是富有的风险投资家，不管怎样。你们会想，“是的，我会买一台四五千美元的电脑。” 这将改变一切。你会看到雇主们说，“哦，我完全可以在本地的 Mac Studio 上运行，你知道，我 90% 的工作负载，甚至 99% 的工作负载。” 我认为苹果现在绝对是一个值得强烈买入的股票。而且，我这不是财务建议，但我的天哪，如果他们做对了这件事，那家公司就能在 AI 领域通吃。

<details>
<summary>Original English</summary>

**Speaker C**: And he is a hardware engineer. M7 Ultra uh because M we're on M5 chips now. you can get like, you know, 456, 512 gigs of RAM. He says M7 Ultra is going to support as much as 1.5 terabytes. That's double what they're already supporting. So, if you think about uh Frontier models, like the last generation, this is like an Opus level model running on your Mac Studio. You guys all use Mac Studios, you're rich venture capitalists, whatever. You're like, "Yeah, I'll take a four or $5,000 computer." This is going to change everything. you're gonna have employers go, "Oh, I can just run, you know, 90% of my workloads, 99% of the workloads on the local uh Mac Studio." I think Apple is a screaming buy right now. Uh and I this not financial advice, but my lord, that company could just run the table on AI if they get this right.

</details>

**Jason**: 好吧。

<details>
<summary>Original English</summary>

**Jason**: All right.

</details>

**Speaker C**: 苹果。

<details>
<summary>Original English</summary>

**Speaker C**: Apple.

</details>

**Jason**: 是的。因为他们将要赚一大笔钱。

<details>
<summary>Original English</summary>

**Jason**: Yes. Because I they're going to make such a fortune.

</details>

**Speaker C**: 让我解释一下。这就像 iPhone 一样。当时大家都嘲笑 iPhone。觉得人们出价过高了。其实并没有。当第一代 iPhone 问世时，很多人认为那不过如此。

<details>
<summary>Original English</summary>

**Speaker C**: You got Let me explain. It's just like the iPhone. Everybody laughed at the iPhone. People overpaid. They did not. When the first iPhone came out, many people that was it.

</details>

**Jason**: 确实。Steve 反应很大。我至今还能听到他的嘲笑声。

<details>
<summary>Original English</summary>

**Jason**: That's true. Steve was the big one. You can I can still hear him laughing.

</details>

**Speaker C**: 不，如果你想想他们是如何通过硬件、通过他们的设备赚钱的，他们只会通过这种内存架构支持运行本地模型，对 Claude 和 OpenAI 施加巨大的下行压力。当人们的桌面上能有无限量的 Token 时，那将会非常疯狂。我跟你说——

<details>
<summary>Original English</summary>

**Speaker C**: No, if you think about how they make money off of hardware, off of their devices, they will put so much downward pressure on Claude and Open AAI by just putting local models and supporting them with this memory architecture. It's going to be wild when people have unlimited tokens on their desktop. I'm telling you,

</details>

### Energy Constraints and Decentralized Data Centers

**Speaker D**: 我不知道你们是否看到了这个，但是，有一家叫做 Sunun 的非常大的太阳能公司。他们本周刚刚宣布，他们正在制造可以放在你家里的分布式数据中心区块。另一家这样做的公司是 SPAN，他们与英伟达（Nvidia）合作。所以，Jason，正如你所说，你看到了边缘计算的这种碎片化和分布，我认为这是一个主题。绝对是一个主题。

<details>
<summary>Original English</summary>

**Speaker D**: I don't know if you guys uh saw this, but um there's a very large solar company called Sunun. They just announced this week that they're making distributed data center blocks that you can put in your house. Another company that did it is company called SPAN that partnered with Nvidia. So to your point Jason, you're seeing this fragmentation and distribution of edge compute which I think is a theme. Definitely a theme.

</details>

**Jason**: 嗯，这同时也是在追逐能源，对吧？比如，如果你有一些太阳能设备，如果你有额外的电池电量，嘿，我们就在晚上以便宜的价格给你电池充电。

<details>
<summary>Original English</summary>

**Jason**: Well, it's also chasing energy, right? Like if you've got some solar, if you've got excess battery power, hey, we power up your batteries at night cheaply.

</details>

**Speaker D**: 我想我上周告诉过你这个，我们现在极度缺乏电力。到 2050 年，美利坚合众国将面临相当于 2 个半加州能源消耗量的缺口。2.5 个加州，这可是世界第四大经济体。到 2050 年，我们将短缺加州消耗的所有能源的 2.5 倍。本周有一家叫 PGM 的大型公用事业公司举行了拍卖，它服务于宾夕法尼亚州、新泽西州、马里兰州，你知道，一共 13 个州。那次拍卖是他们发布一条远期曲线，并说，“嘿，听着，伙计们，这是我预测的负荷，这是我需要的能量。” 于是人们注册参与，基本上就是每天拿到一个有保证的回报率，这样他们在未来就必须交出能源。有点像远期期权。他们大概需要 7 到 8 吉瓦（GW）。

<details>
<summary>Original English</summary>

**Speaker D**: I think I told you this last week, we are so massively short electrons. By 2050, the United States of America will be 2 and 12 California's worth of energy in deficit. 2.5 Californians, the fourth largest economy in the world. we will be short 2.5x of all of the energy consumed by California by 2050. This week there was an auction by this huge utility called PGM which serves Pennsylvania, New Jersey, Maryland, you know, 13 states. And that auction is where they publish a forward curve and say, "Hey, listen guys, here's my forecasted load and here's how much energy I need." And people signed up to essentially get paid a guaranteed rate every day so that they have to fork over the energy in the future. Kind of like a forward option. They needed like seven or eight gawatt.

</details>

<!-- chunk 8/12 -->

### Data Centers, Energy Independence, and Regulation

**Speaker A**: 他们有大约156兆瓦的电力或者之类的出现了。好吧，我们现在在电力和电价方面处境非常糟糕。

<details>
<summary>Original English</summary>

**Speaker A**: They had 156 megawatts or something show up. Well, we are in such a bad place right now on electrons and electricity prices.

</details>

**Speaker B**: 你看到我们那哥们这周干了什么吗？

<details>
<summary>Original English</summary>

**Speaker B**: Did you see what our boy did this week?

</details>

**Speaker C**: 我们需要……所以这是“表后”（behind the meter）发电，这是不一样的。顺便说一下，埃隆（Elon）需要这么做，只是想让你们知道，因为在孟菲斯存在一个问题，在如何让 Colossus 超级计算机项目落地方面，他非常聪明，因为在监管方面这并不会……

<details>
<summary>Original English</summary>

**Speaker C**: We need So this is behind the meter, which is different. And he Elon needed to do this by the way just so you know because there's an issue in Memphis where he was very clever about how he was able to get Colossus off the ground that regulatory it's not

</details>

**Speaker B**: 解释一下这个。

<details>
<summary>Original English</summary>

**Speaker B**: explain this

</details>

**Speaker C**: 当你试图为一个数据中心供电时，通常你使用的是所谓的电网电力。所以你去找当地的公用事业公司说：“嘿，请从那条主输电线上给我接一条线。”这就是你为数据中心供电的方式。当电网容量耗尽或积压严重时，你就必须进行所谓的“表后”操作，这意味着在你拥有的私有土地上，你自己建一些发电设施。但是，这有个问题。你可能会想，那很聪明啊。是的，但就像美国的任何事情一样，监管层出不穷，一层叠一层。你需要克服的最复杂的监管体系之一就是《清洁空气法》的许可。所以，即使你说你要做表后发电，然后你会想，那我能用什么呢？太阳能可以，但对大多数地方来说占地面积太大了。电池也可以，但你首先需要有电来充电。所以人们使用天然气。埃隆非常聪明地买了一大堆类似18轮重型卡车的引擎。他收购了制造这些设备并提供移动发电机组的公司，然后你懂的，把它们固定在地上运行，本质上这些属于个人用途。由于它们是个人使用，所以原本要受《清洁空气法》许可的约束，但当你把它们作为一个整体区块运作时，你就可以主张它不受该条款限制。现在，有像Bloom Energy这样的新解决方案，它允许你拥有庞大的安装规模，同时仍然符合个人使用的清洁空气许可范畴。因此，对于埃隆未来的所有算力产能，他都需要把这个落实到位，以便获得清洁空气许可，并能够拥有清晰的视野去继续建设国内的数据中心。总之……

<details>
<summary>Original English</summary>

**Speaker C**: when you try to power a data center typically you have what's called grid power. So you go to the utility in the area and you say, "Hey, please run me a line off of that main transmission line." And that's how you power your data center. When that runs out or is so backlogged, you have to do what's called behind the meter, which means on your own property that you own, you build something for yourself. Now, there's a problem with that. You would think, well, that's smart. Yes, but like in everything in America, there's regulation on top of regulation on top of regulation. And one of the most complicated regulatory schemes that you have to overcome is clean air permitting. So even if you say you're going to do behind the meter, then you're like, well, what can I do? Solar you can do, but it takes too much space for most places. Batteries you can do, but you need to generate the electricity in the first place. So people use natural gas. So Elon cleverly bought a ton of 18-wheeler like engines basically. He bought the company that makes all this and provides mobile and then just you know pin them to the ground and then ran it and you know those are personal use essentially and so they came under the clean air permitting requirements but then when you act as a block you could make the claim that it doesn't. Now, there are new solutions like Bloom Energy, which allows you to have huge installations and still fall under the personal use clean air permit. And so for all of Elon's future capacity, he needed to have this in place so that he gets the clean air permits and he's able to have a clean run of sight to continue to build domestic data centers. Anyway,

</details>

**Speaker A**: 说到这里，这就是你关于能源的小型TED演讲，但是，伙计们，我们现在的处境很糟糕，而且只会变得更糟。说到数据中心，萨克斯（Sachs），在我的家乡，伟大的纽约州，每个人都“最喜欢”的社会主义州长凯西·霍楚尔（Kathy Hochul）……

<details>
<summary>Original English</summary>

**Speaker A**: speaking there's your little TED talk on energy, but uh we are in a bad place, guys, and it's only getting worse. Speaking of um data center sachs, everybody's favorite socialist governor Kathy Hochel in uh the great state of New York, my hometown,

</details>

**Kathy Hochul (Quote)**: “它们由化石燃料驱动，推高了我们的碳足迹。它们占据了大量土地，可能挤占农业用地和开放空间。底线是，进步不应该伴随着更高的公用事业账单、枯竭的供水或噪音污染。因此，我们别无选择，只能应对这些庞大设施带来的挑战。这就是为什么今天我将签署全国首个在全州范围内暂停建设超大规模数据中心的禁令。”

<details>
<summary>Original English</summary>

**Kathy Hochul (Quote)**: powered by fossil fuels, they drive up our carbon footprint. They occupy massive amounts of land, potentially displacing agricultural space and open spaces. The bottom line is progress shouldn't arise with a higher utility bill, depleted water supply, or noise pollution. So we have no choice but to address these challenges created by these massive facilities. That is why today I'll be signing the nation's first ever statewide moratorium on hyperscale data centers.

</details>

**Speaker A**: 她在那里面说的关于数据中心的每一件事都是毫无根据的指控。所以让我们逐一反驳。她说它们耗尽了所有的电力。嗯，是的。我的意思是，听着，如果你不生产更多的电力就连接到电网，并迫使数据中心与居民用户竞争用电，那么确实，你可能会推高公用事业价格。但是，如果你按照查马斯（Chamath）所说的，让他们进行“表后”建设，那么他们就会自带电力。这也是总统自其政府执政伊始就一直提倡的——让AI公司成为电力公司。所以，这就是解决能源问题或公用事业问题的方法。然后她谈到了，你懂的，吞噬土地。现实情况是，这些数据中心是土地利用效率的典范。我们这个国家有大量的土地。显然，你可以找到有足够开阔土地的地方来建设数据中心。相对于土地使用而言，数据中心的经济影响和价值同样是现存最好的投资回报率（ROI）之一。所谓的噪音污染，那很大程度上是虚构的，是可以处理的。你显然不会想把这些东西建在居民区旁边，只要保持一点距离就可以了。整个水资源消耗的说法很大程度上是一个骗局。

<details>
<summary>Original English</summary>

**Speaker A**: Everything she's saying there is a false accusation uh on the data center. So let's just go one by one. So she's saying that they eat up all of the power. Well, yeah. I mean, look, if you connect to the grid without producing more power and you force data centers to compete with, you know, residential ratepayers, then yeah, you could drive up utility prices. However, if you do what Chamas said and let them build behind the meter, then they bring their own power. And that's what the president has advocated for since the beginning of his administration is let the AI companies become power companies. So, that is the way to solve the energy problem or the utility problem. Then she's talking about, you know, eating up land. The reality is these data centers are a model of land use efficiency. We have a ton of land in this country. Obviously, you can find places where there is enough open land to build a data center. The economic impact and value of a data center relative to the land use again is one of the best ROIs there is. The supposed noise pollution that's largely made up that can be dealt with. You obviously don't want to put these things right next to a residential area, but create a little bit of distance and it's fine. The whole water consumption thing is largely a hoax.

</details>

**Speaker D**: 现代数据中心会循环利用水资源。

<details>
<summary>Original English</summary>

**Speaker D**: The the modern data centers uh recirculate the water,

</details>

**Speaker C**: 是闭环系统。

<details>
<summary>Original English</summary>

**Speaker C**: closed loop systems.

</details>

**Speaker A**: 对。而且我认为有一项研究表明，一个典型数据中心的用水量只相当于两个半In-N-Out汉堡店。我是说，In-N-Out汉堡连锁店的用水量。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And I think there was a study that showed that a typical data center uses the same amount of water as two and a half in-n-out burgers. So, in-n-out burger chains.

</details>

**Speaker D**: 我的意思是，如果你们真的关心水资源，大家拜托去管管杏仁种植吧。

<details>
<summary>Original English</summary>

**Speaker D**: I mean, just go after the almonds if you're concerned about water, people, please.

</details>

**Speaker A**: 有……是的，或者高尔夫球场。我的意思是，有很多，你懂的，有很多水资源的使用方式要浪费得多。所以当你把经济影响与所有这些不同的事物进行比较时，数据中心老实说就像是我们作为一个国家能建设的最好的东西之一。但是——

<details>
<summary>Original English</summary>

**Speaker A**: There's there Yeah. Or golf courses. I mean there's many, you know, there's many uses of water that are way more wasteful. So when you compare economic impact to all these different things, data centers are like honestly one of the best things we could be building as a nation. But

</details>

**Speaker C**: 而且还有所有这些税收和增量收入。你看到那篇文章了吗？我觉得大概是在北达科他州之类的地方，那里的老师从涌入的税收中获得了三四万美元的奖金。有所有这些好的一面。

<details>
<summary>Original English</summary>

**Speaker C**: and there's all these taxes and incremental revenues. Did you see the article where I think it was in North Dakota or something where like teachers were getting like 30 and $40,000 bonuses from all the tax revenue that was coming in? There's all these upsides.

</details>

**Speaker A**: 没错。它们产生了大量的税收。它们创造了蓝领建筑业的繁荣。那种说它们建成后就没有工作岗位的说法是不真实的。在那里你确实会有持续的就业机会。还有，哦，关于霍楚尔（Hochul）提出的观点，最后还有一件事。她说它造成了大量污染。天然气，也是这些数据中心最主要的供电方式，是我们目前拥有的燃烧最清洁的能源之一。

<details>
<summary>Original English</summary>

**Speaker A**: That's right. They generate um a lot of tax revenue. They've created a blue-collar construction boom. It's not true that there's no jobs once they're built. That you do have ongoing jobs there. And then oh, one final thing just on the point that Hochel was making. She said it created a lot of pollution. Natural gas, which is how most of these data centers are powered, is one of the most clean burning sources of power that we have.

</details>

**Speaker C**: 百分之百赞同。

<details>
<summary>Original English</summary>

**Speaker C**: 100%.

</details>

**Speaker A**: 这些数据中心已经成为了人们对人工智能所有焦虑的替罪羊，这已经变成了一种非常笨拙的方式，试图在创新的齿轮中搞破坏，并试图拖慢整个进程。

<details>
<summary>Original English</summary>

**Speaker A**: These data centers have become the scapegoat for all the angst that people have about AI and it's kind of become this very clumsy way of trying to throw a wrench in the gears of innovation and just kind of slow the whole thing down.

</details>

**Speaker D**: 我只想说，欢迎来到德克萨斯州。我们这里有充足的土地。她的提议和演讲中非常愚蠢的一点，除了那些在事实上完全错误的内容之外，就是纽约州大概有80%的地方还未开发。伙计们，开车去纽约上州看看吧。你们脑子里想的都是纽约市。是的，纽约市很拥挤。你去纽约上州看看，纽约州实际上有70%到80%的土地是未开发的。有那么多的土地。这太荒谬了。纽约非常庞大。它是巨大的。

<details>
<summary>Original English</summary>

**Speaker D**: All I have to say is welcome to Texas. We got plenty of land here. And what's so stupid about her proposal and her talk, aside from the thing she got completely factually incorrect, is New York State is like 80% underdeveloped. Drive upstate, folks. You're thinking of New York City. Yes, New York City is packed. You go upstate, it's literally 70 to 80% of the land in New York State is undeveloped. There's so much land. It's ridiculous. New York is giant. It's giant.

</details>

### The Politics of Data Center Protests

**Speaker A**: 关于本周的这个话题，我只想向参议员戴夫·麦考密克（Dave McCormick）致敬。他在宾夕法尼亚州卡莱尔（Carlisle）的陆军战争学院举办了一场国防与创新峰会，我们一群人也去了，还有人来发表演讲，举办了一场CEO圆桌会议，很多国防公司的CEO等人都参加了。但是克里斯·赖特（Chris Wright）和萨克斯也在那里，并且——

<details>
<summary>Original English</summary>

**Speaker A**: On this topic this week, I just want to give a shout out to Senator Dave McCormack. He had a defense and innovation summit in uh Carlisle, Pennsylvania at the Army War College which a bunch of us went to plus came gave a speech had a CEO round table a lot of defense company CEOs etc. But Chris Wright was there at Sachs and

</details>

**Speaker B**: 我的好兄弟。

<details>
<summary>Original English</summary>

**Speaker B**: my guy

</details>

**Speaker A**: 他很棒，克里斯提到了一个疯狂的故事。他说，你知道，其中有很多共同的资金支持，因为迪娜·鲍威尔（Dina Powell）在台上问了这个问题，他说那些抗议数据中心的人有着大量共同的融资模式，他说你实际上可以把根源追溯到在另一个时代抗议水力压裂法（fracking）的同一批人。所以他说，这就像是这些都只是他们用来筹款、维持饭碗的政治幌子。他们就像是拿钱办事的职业抗议者。他们就这么不知从哪里冒出来。我以前没意识到有这样的共性，但他们确实是同一批人。

<details>
<summary>Original English</summary>

**Speaker A**: he's great and Chris mentioned this insane story. He said you know there is a lot of common funding because Dina Powell asked this question on stage and he said there's a lot of common funding patterns of these people that are protesting um the data centers and he said you could actually trace it back to the same people that in a different era were protesting fracking. And so he was saying like it's these are all just hobby horses that they use to raise money, have a job. They're like professionally paid protesters. They kind of just show up out of nowhere. I didn't realize that there was such a commonality, but they're the same people.

</details>

**Speaker B**: 我怎么也想不明白的一件事是，为什么Anthropic还在资助这些想要扼杀新建数据中心的团体。有一个叫做“Public First”的组织，达里奥（Dario）刚给他们捐了第一笔七位数级别的捐款，然后Anthropic的一堆其他员工也捐了，而且你知道，所有这些团体都在试图用新的法规来拖慢AI的发展，并让建造新数据中心变得更困难。到了某个时候，你不得不怀疑，我的意思是，这是监管俘获，还是他们只是忘了初衷？因为拖慢Anthropic收入增长的头号因素不是需求，我认为是数据中心中算力的可用性。所以你就会想，所有这一切的意义到底是什么？

<details>
<summary>Original English</summary>

**Speaker B**: The thing that I just can't understand for the life of me is why Anthropic is still funding these groups that want to put the kibosh on new data center construction. There's one called public first where Daario just gave his first seven figure contribution and then a bunch of other employees at anthropic gave it and you know all these groups are trying to slow down AI development with new regulations and making it harder to build new data centers and at a certain point you just have to wonder I mean is this regulatory capture or they just kind of lost the plot because the number one thing slowing down the growth of anthropics revenue it's not demand I think it's the availability of compute in data centers. And so you're just kind of wondering like what is the point of all of this?

</details>

**Speaker A**: 太真实了。

<details>
<summary>Original English</summary>

**Speaker A**: It's so true.

</details>

**Speaker B**: 我和政界的一位人士谈过这件事，他们的理论是，民主党人不会永远暂停数据中心的建设。他们会暂停，直到他们觉得自己在足够掌控局面的情况下，能够……

<details>
<summary>Original English</summary>

**Speaker B**: I was talking to someone in politics about this and the theory that they had is well the Democrats aren't going to pause the data centers forever. They're going to pause them until they feel like they're in enough control that they can

</details>

<!-- chunk 9/12 -->

### Data Centers, Energy Policies, and Geopolitics

**Speaker A**: 制定所有的规则。所以换句话说，他们把这称为暂停（moratorium）。我认为这确实意味着数据中心建设将要停止，但最终他们会处于这样一个位置，可以说：“好吧，如果你想重新启动这些东西，你想解除暂停，这就是我们的条件。” 然后我们就会迎来这种，你知道的，大政府、由民主党定义的 AI 监管体系，而且你知道它将包括一个新的监管机构和新的言论控制措施，社交媒体的整个“信任与安全”议程将被移植过来。这是……我交谈过的一个人，这就是他推测的真实议程：最终一旦特朗普不再担任总统，或者在未来某个民主党政府时期，他们最终会解除暂停，但必须按照他们的条件。现在，我认为这是一种非常危险的做法，因为你知道，特朗普还要再当两年总统，在那之后谁也不知道会发生什么。即使你在大概两年半或三年后解除暂停，那些项目也需要几年的时间才能重新启动。所以当你谈论数据中心的暂停时，它并不像几个月的停顿。至少需要整整五年时间，然后你才能在纽约州启动另一个数据中心。为了让你们知道情况有多糟糕，这里有一条曲线可以用来为数据中心资产定价。我想你们都知道这一点，但我手头有这样一个资产组合，这是我和我的合伙人妮塔（Nita）积累起来的。非常有趣的是，当我们和所有的超大规模云计算企业（hyperscalers）谈论给我们一个报价时——因为我们正试图搞清楚我们应该保留它、建设它还是干脆把它卖掉——最令人难以置信的是，在曲线的最前端，价格极端到了什么程度。当你在今天拥有可验证的、可通电的电力时。而原因正是你所说的一切，萨克斯（Saxs），那就是当你展望未来时，你知道，我们以前说过，大约 40% 的这些项目正在被搁置和停止。因此，这就造成了可用能源的巨大缺口，无法实际推动 AI 的使用。所以，在某种程度上，如果你真的想要，你知道，药物发现，或者你想要癌症诊断，或者你想要更好的医疗保健或更好的法律咨询，我们实际上可能无法基于现有的所有需求来提供这些服务，因为电力跟不上。能源跟不上。而它之所以跟不上，是因为人们只是在条件反射地抗议一些他们并不完全清楚理解的东西。所以我认为这是一个非常、非常大的问题。

<details>
<summary>Original English</summary>

**Speaker A**: dictate all the rules. And so in other words, they're calling this a moratorum. And I think it does mean that the data centers are going to stop but eventually they're going to be in a position to say okay here are our terms if you want to turn these things back on right you want to lift the moratorum and then that's when we get this you know big government democrat defined AI regime and you know that it's going to consist of a new regulatory agency and new speech controls the whole trust and safety agenda from social media will be ported over that's this was this One person I was talking to, this is what he was speculating is the real agenda is that eventually once Trump is no longer president or in some future Democratic administration, they will eventually lift the moratorum but on their terms. Now I think that's a really dangerous thing to do because you know Trump is president for another two years and then no one knows what's going to happen after that. And even if you lift the moratorum in say 2 and 1/2 or 3 years, it's going to take a couple of years for those projects to even ramp back up. So when you start talking about a moratorium on data centers, it's not like a a few month pause. It's probably a good 5 years at least before you know you can get another data center switched on in the state of New York. Just so you know how bad it's gotten, there's a curve that you can use to price data center assets. And I think you guys know this, but I have this portfolio of these assets that myself and my partner Nita have accumulated. And what's so interesting is when we talk to all of the hyperscalers about giving us a price because we're trying to figure out whether we should keep it or build it or just sell it, the most incredible thing is how extreme the price is at the front end of the curve. When you have verifiable energizable power today. And the reason is exactly everything that you're saying, Saxs, which is that when you look out into the future, you know, we've said this before, but it's about 40% of all these projects are getting mothballled and stopped. And so it's creating this massive deficit of available energy to actually drive the use of AI. So to the extent that you actually want, you know, drug discovery or you want cancer diagnosis or you want better healthcare or better legal advice, we may actually not be able to service it based on all of the demand that exists because the power isn't there. The energy isn't there. And the reason why that's not there is because folks are just kind of reflexively protesting something that they don't completely understand clearly. So I think it's a really it's a really big problem.

</details>

**Speaker B**: 我的意思是，我们将会看到 GPU 追逐能源。就像“哪里有能源”，就把 GPU 开到那里去，这就是将要发生的事情，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: I mean, we're going to have GPUs chasing energy. like where's their energy and just drive the GPUs there is what's going to happen right

</details>

**Speaker C**: 让我再补充一个层面，那就是他们不仅试图阻止在美国建设数据中心，他们还试图阻止在国际上，在我们的朋友、盟友和伙伴国家建设数据中心。而他们这样做的方式是，那些阻止数据中心建设的同样政治力量，也是所有这些新的芯片出口管制背后的推手。所以他们想让向越来越多国家（包括我们的朋友和盟友）出口芯片变得越来越困难。因此，这里将不会有数据中心。我们的盟友那里也不会有数据中心。我的意思是，我们打算把这些东西放在哪里？

<details>
<summary>Original English</summary>

**Speaker C**: let me add one layer to it which is they're not only trying to stop data centers from being built in the US they're trying to stop data centers from being built internationally in our friends allies and partner countries and the way they're doing that is the same political forces that are stopping data centers are also behind all these new export controls on chips so they want to make it harder and harder to export chips to more and more countries including our friends and allies and so there's not going to data centers here. There's not going to be data centers in our allies. I mean, where are we going to put these things?

</details>

**Speaker D**: 我的意思是，那些盟友有无限的能源，中东。比如，如果你想要一些数据中心，

<details>
<summary>Original English</summary>

**Speaker D**: I mean, those allies have unlimited energy, Middle East. Like, if you want some data centers,

</details>

**Speaker A**: 嗯，有趣的是，杰森（Jason），你知道，我们在中东做了一堆数据中心的事情，然后它就有点停滞了。意思是，并没有出现我认为会发生的那种增长，因为它是一个地理位置非常便利的地方。它被称为中东是有原因的。所以，你知道，你可以从那里非常快速地在 200 毫秒内服务 40 亿人。

<details>
<summary>Original English</summary>

**Speaker A**: well, what's funny, Jason, is, you know, we did a bunch of Middle East data center stuff and then it's kind of stopped. Meaning, like there wasn't this growth that I thought would happen because it's a very conveniently placed geography. It's the Middle East for a reason. And so, you know, you can serve 4 billion people very quickly in under 200 milliseconds from there.

</details>

**Speaker A**: 相反，发生的事情是亚洲出现了这种爆炸式增长，特别是澳大利亚，这让我有点惊讶，因为我原本以为那些人在 DSA（数字服务法案之类的监管）上走得更远，你知道的，极左派。我以为这些事情是不会发生的，但他们却能够达成大笔交易。所以，以这种奇怪的方式，所有这些其他国家都在奔跑着，试图迅速拥抱这些东西。他们做得还不错。他们正在做的事情，有点像是要取代美国所需要的一些能源。但问题是，我们需要在这里有足够的盈余，因为这里才是大多数商业活动将被创造出来的地方。这真的是，我认为应该——

<details>
<summary>Original English</summary>

**Speaker A**: Instead, what happened was there was this explosion in Asia and specifically in Australia, which kind of surprised me because I would have thought that those folks are a little bit even further out on the DSA, you know, far left. I thought these things would not have happened, but they they were able to get big deals done. So, in this weird way, you have all of these other countries kind of running to try to embrace this stuff quickly. They've done a decent job. They're doing stuff to sort of like displace some of the energy that that is needed in the US. But the problem is we need to have enough surplus here because this is where most of the commerce is going to get created. That really that I think should

</details>

**Speaker E**: 这些……这些都是“奢侈品式”的监管。就好比，如果你是纽约州或加利福尼亚州，你能够负担得起去说，你知道吗，我们不需要这个。对我们来说，多一个数据中心是件奢侈的事情。但如果你是澳大利亚，你可能真的需要这笔钱。如果你是德克萨斯州，你可能真的很想要这笔钱。所以这就是最疯狂的地方，比如道德标榜（virtue signaling）只能走到这一步，直到你的债务占 GDP 的比例足够高，或者你的生产力足够低，又或者你的外国直接投资（FDI）足够低的时候，你就会说，好吧，你知道吗，去他的吧，我们就是要建一个数据中心。但另一件事是，如果你看到这周发生的事情，阿联酋现在能够进口同类最佳的顶尖芯片了，所以就如你所说的，杰森，我认为这重启了循环，你必须非常仔细地关注中东，因为在那里建设这些东西非常有吸引力。

<details>
<summary>Original English</summary>

**Speaker E**: these are these are luxury regulations. Like you can afford if you're New York State or California to be like, you know what, we don't need this. This is a luxury for us to have an extra data center. If you're Australia, you might really need the money. If you're Texas, you might really want the money. So this is what's so crazy like virtue signaling only goes so far until your debt to GDP is high enough and or your productivity is low enough andor your foreign direct investment is low enough where you're like all right you know what screw all that we're just going to build a data center but the the other thing is if you saw what happened this week the UAE now is able to import the best-in-class leading chips and so to your point Jason I think it restarts the cycle where you have to look very carefully at the Middle East because it's a very attractive place to build these things

</details>

**Speaker F**: 顺便说一下，你看到了……即使你只是……如果你考虑到光纤和你们刚才谈论的毫秒级延迟，是的，你可以覆盖那 40 亿人，但我不知道你有没有看到巨大的星链（Starlink）版本，现在他们生产了一个非常大的版本，我想你大概买到了其中一个企业版，但还有一个更大的企业版，他们可以把它们捆绑在一起，这样你就开始达到比如 10Gb、20Gb 的网络配置，所以这意味着你几乎可以把这些东西放在任何地方。

<details>
<summary>Original English</summary>

**Speaker F**: and by the way you saw the you even if you just if you think about fiber and the milliseconds as you're talking about yes you can get to the four billion people but I don't know if you saw the the giant Starlink versions now they make like a really big version I think you got like one of the enterprise versions but there's like an even bigger enterprise version and they can bundle them together and you're starting to get to like 10 gig 20 gig setups so that means you could start putting these things almost anywhere

</details>

**Speaker B**: 这也就等于又增加了一个——

<details>
<summary>Original English</summary>

**Speaker B**: which gets also like adds another

</details>

**Speaker D**: 我们能看看你的片段吗？就是你之前提到的那个，

<details>
<summary>Original English</summary>

**Speaker D**: can we see your clip. The thing that you were mentioning before,

</details>

### Media Influence and Public Sentiment

**Speaker G**: 就你的观点而言，这在中东并不像在中东那样普遍，那里有君主制国家和不是由民主统治的政府，但在民主国家，我们看到这种反数据中心的运动正在占据上风。这张图表对我来说，在理解美国这种令人难以置信的反转基因（anti-GMO）情绪从何而来的过程中，总是起到了一定的作用，

<details>
<summary>Original English</summary>

**Speaker G**: this is not to your point as prevalent in the Middle East where you have monarchies and governments that aren't ruled by democracy, but in democracies, we see this anti-data center movement taking hold. This chart is something that for me always kind of played a role in my understanding of where the incredible anti-GMO sentiment came about in the United States,

</details>

**Speaker G**: 这棒极了。今日俄罗斯（Russia Today），这家俄罗斯媒体机构于 2010 年在美国推出。他们在 2022 年被拜登赶出了美国。你可以看到，在今日俄罗斯存在于美国之前，并没有反转基因情绪。转基因生物自 1996 年就存在了。那是他们第一次在美国进行大规模商业推广，而且相当普遍地存在了大概 14 年多，之后大家才开始认为转基因生物是坏东西。我们必须摆脱转基因生物。你可以用一百种不同的方式，非常有针对性地、具体地问人们关于这件事的事实、转基因的科学知识以及所有这类东西，但每个人总是有一个原因说明他们为什么不要这些东西，就像我们现在听到的关于 AI 和数据中心的言论一样。结果发现，如果你追溯所有带有这种反转基因情绪的媒体——这种情绪最终被“妈妈博客（mom bloggers）”采用，最终进入社交媒体的信息流，最终被所有人当成真理接受。其中很多都源于俄罗斯在这个时代发起的媒体推送。你实际上可以在显示 GMO 的谷歌趋势数据中看到这一点，这就像是一篇详细的报告。然后，随着今日俄罗斯开始被不同的媒体切断联系，人们停止转发他们，停止反映他们的观点，并停止撰写追随今日俄罗斯的文章，美国的反转基因情绪下降了，我认为你可以看到这种情况可以追溯到几十年前。你知道克格勃在冷战期间设计了一种被称为“定向措施（directed measures）”的行动，其真正目的是试图通过影响媒体来发起一场影响力运动。所以，通过外国媒体散布这种政治宣传，特别是针对西方民主国家。而你——

<details>
<summary>Original English</summary>

**Speaker G**: which is great. Russia Today, this Russian media outlet launched in the US in 2010. They were kicked out of the US by Biden in 2022. And you can see that prior to Russia today existing in the US, there was no anti-GMO sentiment. GMOs were around since 1996. That's when they first had their big commercial launch in the US and were pretty prevalent for, you know, 14 plus years before everyone started to think GMOs are bad. We got to get rid of GMOs. And you could ask people a hundred different ways very pointedly and specifically about the facts on the matter and the science of GMOs and all this sort of stuff, but everyone always had a reason why they didn't want them, similar to what we're hearing now with AI and data centers. And it turns out that if you track back all of the media that had all this anti-GMO sentiment that ultimately got picked up by the mom bloggers that ultimately got put into social media feeds that ultimately everyone just accepted as truth. A lot of it originated in this Russian media push that happened around this era. And you can actually see this on the Google trend data that shows GMO and it's kind of write up. And then as Russia Today started to get cut by different media outlets and people stopped retweeting them and stopped reflecting them and stopped writing articles that followed Russia Today the anti-GMO sentiment declined in the US and I think you can see this going back decades. You know there's this effort that the KGB kind of designed during the cold war called directed measures which was really meant to try and create an influence campaign through affecting media. So putting this kind of propaganda out through foreign media, particularly targeted western democracies. And you

</details>

<!-- chunk 10/12 -->

### AI 基础设施与外国影响力

**Speaker A**: 你知道，你可能会认为，也许可以追溯到德国在核能方面发生的事情，这在根源上多少有些相似。但一系列这样的推动力量，如果你是一个相当理性的人，并且能够就这些技术的科学价值、经济价值和益处进行真正客观的辩论，那么这些阻力似乎是毫无道理的。但出于某种原因，我们称之为“激进分子”的群体对这些技术变得高度敏感。他们大喊我们必须摆脱这些技术。每个人都有各种各样毫无根据、缺乏科学依据的理由，来解释为什么他们想要消除它们。然后你就会觉得，等一下，我们是怎么落到这个地步的？我们这简直是在束缚自己的手脚。我认为我们今天在美国看到了类似的情况，也就是发生在数据中心上的事情。这种对他们所谓的 NOS（网络操作系统/数据中心）的资金支持、媒体对这种论调的支持、以及媒体的转发造势。然后你去问人们，今天发布的一项民意调查显示，超过 50% 的美国人认为数据中心增加了水和电的成本。即使数据中心正在全面循环利用水资源，并且他们自己生产电力，人们对数据中心仍然存在这种令人反感的抵触情绪。所以，在美国发生了一种根深蒂固的心理转变。然后你知道的，人们会有这样的想法：‘好吧，我讨厌富人，我讨厌科技，我讨厌 AI，我不想要这些东西中的任何一样，我就是不想要这些东西。’

<details>
<summary>Original English</summary>

**Speaker A**: you know, you could argue that maybe you could trace back what happened in Germany with nuclear energy as being kind of similarly originated. But there have been a series of these pushes that seem nonsensical if you're fairly rational and can have an actually objective debate about the scientific merit, the economic merit, the benefits of these technologies. But for some reason, what we call the activist community become heightened to them. Say that we've got to get rid of them. And everyone's got these different unfounded, scientifically unfounded reasons why they want to get rid of them. And you're like, wait a second, how did we end up in this place that we're literally handicapping ourselves. And I think we're seeing something similar happening with data centers in the US today. The funding of the NOS's as they're being called, the media that's supporting this, the retweeting of the media. And then you asked people, there was a poll that came out today, something north of 50% of Americans believe that data centers increase the cost of water and electricity. Even if the data center is fully recycling the water and they're producing their own electricity, there's still this kind of repugnant reaction to the data center. And so there has been this like deeply sewn psychological shift that's happened in the United States. and and and you know, people have these, well, I hate the rich, I hate tech, I hate AI, I don't want any of this stuff, I don't want any of this stuff,

</details>

**Speaker B**: 但是这一切的根源究竟在哪里呢？我确实很担心这其中存在某种程度的，怎么说呢，可以称之为来自外国的……

<details>
<summary>Original English</summary>

**Speaker B**: but where does it all come from? I do worry that there's some degree of kind of call it foreign,

</details>

**Speaker A**: 你知道的，影响力……

<details>
<summary>Original English</summary>

**Speaker A**: you know, influence

</details>

**Speaker B**: 影响力。我不太喜欢“影响力”这个词，因为每个人都似乎在随便使用它，但这里面确实存在某种程度的，比如……

<details>
<summary>Original English</summary>

**Speaker B**: influence. I I don't love the word influence because everyone kind of everyone captures it up, but there is some degree of like

</details>

**Speaker A**: 我会说这其中存在外国势力的利益。我们姑且就这么称呼它吧。

<details>
<summary>Original English</summary>

**Speaker A**: I would say there's there's foreign interest. Let's let's call it that.

</details>

**Speaker C**: 不，我认为远不止于此。就在一个月前，仅仅一个月前。

<details>
<summary>Original English</summary>

**Speaker C**: No, I think it's more than that. So just one month ago, just one month ago,

</details>

**Speaker A**: OpenAI 发表了一篇博客文章，题为《与中国（PRC）相关的影响力行动正在针对美国的 AI 辩论》，Politico 报道了这件事，许多其他网站也进行了报道。基本上他们想表达的是，事实上许多人都在说，中国是许多这些影响力运动的幕后推手，试图塑造美国对 AI 数据中心的态度。

<details>
<summary>Original English</summary>

**Speaker A**: OpenAI published a blog post called PRC linked influence operations are targeting AI debates in the US and Politico covered this and a lot of other sites covered this. Basically what they are saying and in fact many people are saying is that China is behind a lot of these influence campaigns to shape US attitudes on AI data centers.

</details>

**Speaker B**: 这很说得通。这非常有道理。而且国会将对此展开调查。这确实说得通，因为这符合他们的利益，对吧？如果他们能阻止我们建设这种必要的基础设施，

<details>
<summary>Original English</summary>

**Speaker B**: It makes sense. It makes a lot of sense. and there's going to be a congressional investigation of this. It does make sense cuz it is in their interest, right? If they can stop us from building this necessary infrastructure,

</details>

**Speaker A**: 那么这正是中国赢得这场 AI 竞赛的一种方式。

<details>
<summary>Original English</summary>

**Speaker A**: then that's a way for China to win the AI race.

</details>

**Speaker B**: 如果他们能控制市场，如果他们能促使 Anthropic 去，你知道的，‘过河拆桥’，如果他们能扼杀美国的开源运动，并限制需求或减少对更低端、更便宜模型的选择性和选项，你仔细想想这会造成什么后果。以每百万输入 token 56 美元的价格。我是说，相比于世界其他地区只要 50 美分的价格。突然之间，当你的成本比别人高出 50 到 100 倍时，一家远远不如你的公司也能轻易打败你。

<details>
<summary>Original English</summary>

**Speaker B**: If they can the market, if they can incentivize anthropic to, you know, pull the ladder up, if they can kill open source in the United States and constrain demand or the optionality and choice of lower, cheaper models, think about that for a second. at $56 per million input tokens. I mean, versus 50 cents for the rest of the world. All of a sudden, it doesn't take a company that's much much worse than you to beat you when your cost is 50 to 100x more.

</details>

**Speaker A**: 对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Right?

</details>

**Speaker B**: 这仅仅是数学算账。但这笔账根本就对不上。

<details>
<summary>Original English</summary>

**Speaker B**: That's just the math. The math ain't mapping.

</details>

**Speaker A**: 你知道，Sasha 曾指出过这一点，这些企业不仅在用金钱为 AI 买单。他们通过向那些前沿模型喂送他们专有的知识，再次付出了代价，对吧？以及他们所有的超额收益（Alpha）。所以，这就像是遭受了双重打击。

<details>
<summary>Original English</summary>

**Speaker A**: You know, it's Sasha made the point that these enterprises are not just paying for AI with money. They're paying again by feeding those frontier models their proprietary knowledge, right? And all their their alpha. So, it's like a double whammy.

</details>

**Speaker B**: 这就像是，它不仅变得更加昂贵，而且你还可能是在抵押你的未来。

<details>
<summary>Original English</summary>

**Speaker B**: It's like it's more expensive and you're potentially mortgaging your future.

</details>

**Speaker C**: 听着，让我们坦诚一点。显而易见的是，外国政府有巨大的动机试图操纵和影响美国国内的各种动向。我认为我们应该直接承认这一点。认为这种事情没有发生的想法是非常天真的。现在的问题是，我们必须能够指出它并直接戳穿它，因为否则显而易见正在发生的情况是，有很多美国人会轻易相信这一切，他们不会从第一性原理出发去思考问题。

<details>
<summary>Original English</summary>

**Speaker C**: Look, let's be honest. It is obvious where foreign governments have an enormous incentive to try to manipulate and influence the comingings and goings in America. I think we should just acknowledge that. The idea that that doesn't happen is very naive. Now the question is we have to be able to call it out and put our finger on it because otherwise what is clearly happening is that there's a lot of Americans that will just fall for this and they will not think from first principles.

</details>

### AI 监管与对未知的恐慌

**Speaker A**: 我们在 AI 方面存在一种巨大的、非常严重的道德恐慌。听着，当你在谈论 AI 可能导致的灾难时，我们到底在讨论什么？我们谈论的是未来可能发生的事情。目前还没有发生任何与此类似的事情。你知道，即使是每个人都在谈论的网络安全风险，

<details>
<summary>Original English</summary>

**Speaker A**: We have a huge we have a huge moral panic going on with respect to AI. Look when you talk about catastrophes that could result from AI. What are we talking about? We're talking about things that might happen in the future. Nothing resembling this has happened yet. you know, even the cyber risk that everyone's been talking about,

</details>

**Speaker B**: 失业问题

<details>
<summary>Original English</summary>

**Speaker B**: job loss

</details>

**Speaker A**: 或者是失业问题，结果是这些担忧没有一个是成真的。到目前为止，我们还没有看到其中任何一种情况发生。但我认为，我们正处于摧毁我们经济皇冠上明珠的边缘，那就是我们所拥有的自由市场创新体系，这种快速迭代的文化：任何有绝佳想法的人都可以去筹集风险资本，启动他们的想法，创立他们的公司。而我们正处于这样一个边缘，你知道，我们现在正在讨论的是“奥弗顿之窗”（Overton window，指公众能接受的政策范围）已经移动了多远，以至于我们竟然真的在说：为我们的行业创建一个像 FINRA（美国金融业监管局）那样的机构，可能比所有其他替代方案都要好。FINRA 是由一群股票经纪人组成的，他们在制定规则。但那个行业上一次出现任何创新是什么时候了？我的意思是，我猜 Robinhood 实现了免费交易。也就仅此而已了。

<details>
<summary>Original English</summary>

**Speaker A**: or job loss, it's like none of it's turned out to be true. We haven't seen any of it so far. But we're on the threshold, I think, of destroying the crown jewel of our economy, which is the system of free market innovation that we have, this culture of rapid iteration of anyone with a good idea can go raise risk capital and start their idea, start their company. And we're on the verge, you know, now we're talking I think about how far the Overton window has moved where we're actually saying that creating a FINRA for our industry might be better than all the alternatives. FINRA is a bunch of stock brokers writing rules. And when's the last time there was ever any innovation in that sector? I mean, I guess Robin Hood made trading free. That was it.

</details>

**Speaker B**: 那确实是个大创新。是的。订单流支付（PFOF）。

<details>
<summary>Original English</summary>

**Speaker B**: That was a big one. Yeah. Flow.

</details>

**Speaker A**: 好的。但这并不是真正的创新。好吧。这只是一种关于定价模式的创新。而我们现在竟然真的在说，这可能是最不坏的选择——建立一个相当于由一群股票经纪人组成的机构来制定新规则，而所有这些（非美国）AI 公司却都不需要遵守这些规则。这太疯狂了。我们将要——我们将要白白扔掉我们在这个领域拥有的领先地位。顺便说一句，Kimi（月之暗面旗下模型）的 K3 刚刚发布，人们都在说它现在已经跻身顶尖行列了。它非常非常接近前沿水平了。我们在对中国的优势可能只剩下几个月的时间了，甚至可能更短。而我们却要为那些还没有显现出来的风险，去制定所有这些疯狂的规则，设立新的监管机构。

<details>
<summary>Original English</summary>

**Speaker A**: Okay. But that's not real innovation. Okay. That's like an innovation with respect to a pricing model. And we're actually saying that that might be the least bad alternative is having the equivalent of a bunch of stock brokers creating new rules that all these AI companies are not going to have to abide by. It's crazy. We are going to we are going to throw away the lead that we have in this. And by the way, Kimmy K3 just came out and people are saying it's it's now right up there. It's very very close to the frontier. We may have months on China if that. and we're going to create all these crazy rules and new regulatory bodies for risks that have not manifested yet.

</details>

**Speaker D**: 这种情况值得监控，但不值得恐慌。这就好比，你应该监控自动驾驶汽车和失业问题的状况。中国显然就在这么做。他们最近刚停止发放自动驾驶汽车的许可证，这就是个例子，因为自动驾驶发展得太好了，导致他们正在流失就业岗位，并且……出现了一些人在聚集，引发了一点社会动荡。所以他们干脆说，我们要让自动驾驶汽车……实施许可制，并且他们现在停止发放任何新的许可证，实施了许可证的暂停令。像 Mythos 这样的系统值得关注，看看它是否能黑进你的系统。Palo Alto Networks 正在对其进行检查，其他人也在检查。这一切都值得监控，但是的，今天并没有因为 AI 而发生任何灾难。没有任何怪物从你的 ChatGPT 窗口里跳出来。你知道，最坏的情况就是你消耗掉了一些 token，你知道，好吧，太棒了。那就是——那就是最大的问题了。

<details>
<summary>Original English</summary>

**Speaker D**: It's worth monitoring the situation, but it's not worth panicking. Like, you should monitor the situation with self-driving cars and job loss. China is certainly doing that. They just stopped giving out permits for self-driving cars as an example because it's going so well and they're losing jobs and and there are people who are getting there's a little civil unrest. So they just said we're going to make self-driving cars um licensed and so they're not giving out any more license moratorium on license for now. It's worth watching Mythos and if it could hack your system. Palo Alto Network's checking it out, other people checking out. It's all worth monitoring but yes it there's no disaster here today because of AI. nothing's jumping out of your chat GPT window. You know, the worst case scenario is you blow out some tokens, you know, okay, great. That that's that's the biggest

</details>

**Speaker A**: 现在只有极少数的公司真正处于前沿，并且他们都进行了安全测试和红队演练，以及所有这些……

<details>
<summary>Original English</summary>

**Speaker A**: There's only a handful of companies that are even at the frontier and they all have safety testing and red teaming and all the rest of

</details>

**Speaker D**: （他们）做得很好。

<details>
<summary>Original English</summary>

**Speaker D**: doing a good job.

</details>

**Speaker A**: 是的，我的意思是别搞这些了。我只是在质疑我们现在是否需要一个庞大的监管机构来开始做所有这些……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I'm saying stop that. I'm just questioning whether we need some vast regulatory apparatus now to start doing all

</details>

### Dario Amodei 的末日论

**Speaker B**: 这绝对是不成熟的，我们这样做是因为受到科幻小说的影响，以及 Dario（Amodei，Anthropic 首席执行官）在那儿危言耸听地说所有工作都会消失。我的意思是，那——那——那简直是最荒谬的事情，当时他说，比如他很恐慌地表示，到 2026 年，80% 或 90% 的工作岗位都会消失。他原话是怎么说的来着？Nick，帮我查一下他的确切说法。我想他是说 50% 的……

<details>
<summary>Original English</summary>

**Speaker B**: certainly premature and we did this because of science fiction and Daario saying all jobs are going away. I mean that that that was the most ridiculous thing when he said like he's panicked that it's going to be 80 or 90% jobs in 2026. What was his claim? I Nick get the exact claim. I think he said 50% of

</details>

**Speaker D**: 他说，他说的是，随着 AI 的发展，他说 50% 的初级知识工作者岗位将在 1 到 5 年内消失。那是一年前的事了。所以……

<details>
<summary>Original English</summary>

**Speaker D**: He said he said with it he said 50% of entry-level knowledge worker jobs are going away within 1 to 5 years. That was one year ago. So

</details>

**Speaker B**: 这确实有点荒谬。是的。我是说这，但他甚至还不知道该如何使用这些工具呢。

<details>
<summary>Original English</summary>

**Speaker B**: it's a little ridiculous. Yeah. I mean it's but he's not even know how to use the tools yet.

</details>

**Speaker A**: 他自从 GPT-2 问世以来就一直处于一种恐慌状态中。

<details>
<summary>Original English</summary>

**Speaker A**: He's been in a state of panic since GPT2.

</details>

**Speaker B**: 是的。是的。我的意思是……

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes. I mean

</details>

**Speaker A**: 记得吗，他们曾希望——他们希望对使用 10 的 25 次方浮点运算次数（FLOPs）的模型进行监管审批。对吧。而现在几乎每一个人工智能模型都远远超过了那个阈值。

<details>
<summary>Original English</summary>

**Speaker A**: remember they wanted they wanted to have uh regulatory approval for models that use 10 to the 25th flops. Right. And every single AI model is like well past that threshold now.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 而且我们还没有看到任何实质性的危害。听着，他们过去认为 10 的 25 次方 FLOPs 将拥有足够的算力来创造出，你知道的，终结者，你知道的，创造出“天网”。

<details>
<summary>Original English</summary>

**Speaker A**: And we haven't seen any of the the harm. Look, they thought that 10 to the 25th flops would be enough compute to create, you know, the Terminator, you know, to create Skynet.

</details>

**Speaker C**: 无意冒犯，Freeberg，但某个人的恐慌发作，某个人的焦虑症可能已经塑造了这里历史的整个进程，就像——Dario 是不是有……我不是在拿这事开玩笑，但是他是不是有焦虑方面的问题，导致他对这些东西过度担忧了，还是说这仅仅是夸大妄想？上我们的播客来聊聊吧，Dario。邀请一直向你敞开。过来一起聊聊。我敢肯定，在你刚刚指控他有恐慌发作之后，他一定会“非常乐意”来参加这个播客的，但是……

<details>
<summary>Original English</summary>

**Speaker C**: No offense, Freeberg, but one guy's panic attacks, one guy's anxiety condition might have shaped the whole course of history here like Dar does Daario have like I'm not making light of it, but does he have an anxiety issue where he's like overly concerned about this stuff or is it just delusions of grandeur? Come on the pod, Dario. Invite's open. Come hang out. I'm sure he'd love to come on the pod after you just accused him of having a panic attack, but

</details>

**Speaker A**: 我的意思是，他似乎……

<details>
<summary>Original English</summary>

**Speaker A**: I mean, he seems

</details>

<!-- chunk 11/12 -->

### AI 策略与活动预告

**Speaker A**: 就像他陷入了一个永远无法摆脱的困境。

<details>
<summary>Original English</summary>

**Speaker A**: like he's in a perpetual one.

</details>

**Speaker B**: 不，让我告诉你，听着，我觉得这可能是心理作用，但我确实认为有一个非常合理的策略，而且是一个非常简单、直接的策略。第一，把自己包装成一家安全的 AI 公司。第二，禁止不安全的 AI。第三，盈利。

<details>
<summary>Original English</summary>

**Speaker B**: No, let me tell you, listen, I it could be psychological, but I actually think that there's a strategy that makes a lot of sense, and it's a very simple, straightforward strategy. Number one, brand yourself as a safe AI company. Number two, ban unsafe AI. Three, profit.

</details>

**Speaker A**: 是啊，就是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, there you go.

</details>

**Speaker B**: 这就是策略。相当聪明。好了，各位。去 allin.com/events 网站，报名参加九月份的 Allin 峰会。奖学金申请已经开放。现在让我们和我们的好兄弟 David Friedberg 一起，快速进入精彩、深入、扎实的科学角环节。在进入科学角之前，我要帮 Ronnie Dog 领养机构呼吁一下。我非常喜欢索诺玛（Sonoma）的这家家庭狗狗救援机构。去看看他的 Instagram 链接。天哪，他又来了。

<details>
<summary>Original English</summary>

**Speaker B**: That's the strategy. Kind of brilliant. All right, everybody. Go to allin.com/events and sign up for the Allin Summit in September. Scholarships are open. Let's do a quick amazing deep robust science corner with our boy David Friedberg. Before we get into the science corner, I'm going to give a shout out to Ronnie Dog for adoption. I love family dog rescue in Sonoma. Check out his Instagram link. God, here he goes

</details>

**Speaker C**: 在视频简介里。这只狗需要一个家。他曾经被寄养，但失去了寄养家庭。谁来把他领走吧。他很棒的。好了，让我们开始吧。

<details>
<summary>Original English</summary>

**Speaker C**: in the description. This dog needs a home. He was fostered and he lost the foster home. Someone come and grab him. He's awesome. All right, let's get into this.

</details>

**Speaker A**: 我们就是这么干的。他想……

<details>
<summary>Original English</summary>

**Speaker A**: This is what we're doing. He's trying to

</details>

**Speaker D**: 他想获得更多的关注度（Q points）。

<details>
<summary>Original English</summary>

**Speaker D**: he's trying to get more Q points.

</details>

**Speaker E**: 那只狗看起来很好吃。

<details>
<summary>Original English</summary>

**Speaker E**: That dog looks delicious.

</details>

**Speaker B**: 恶心。

<details>
<summary>Original English</summary>

**Speaker B**: Gross.

</details>

**Speaker C**: 你已经不住在斯里兰卡了。Chamath。

<details>
<summary>Original English</summary>

**Speaker C**: You don't live in Sri Lanka anymore. Chamath.

</details>

**Chamath**: 是啊，说真的。

<details>
<summary>Original English</summary>

**Chamath**: Yeah, seriously.

</details>

**Speaker D**: 斯里兰卡无故躺枪。

<details>
<summary>Original English</summary>

**Speaker D**: Sri Lanka taking a spray.

</details>

**Speaker A**: 在斯里兰卡你们是怎么腌制那只狗的？

<details>
<summary>Original English</summary>

**Speaker A**: How do you marinate that dog in Sri Lanka?

</details>

**Chamath**: 在斯里兰卡有什么就用什么。不用盐和胡椒，还是你喜欢放点别的？你知道，就放点盐和胡椒。

<details>
<summary>Original English</summary>

**Chamath**: Do what you got to do in Sri Lanka. Salt and pepper free or do you like something else? You know, just a little salt and pepper.

</details>

**Speaker D**: 腌制 12 个小时。你用什么调料？

<details>
<summary>Original English</summary>

**Speaker D**: 12 hour marinade. Do you use bolet?

</details>

**Speaker A**: 噢，你喜欢加点酸奶和葛拉姆马萨拉（印度香料）吗？也许来点辣的。你们想聊聊逆转衰老的话题吗？

<details>
<summary>Original English</summary>

**Speaker A**: Oh, do do you like do you like a little yogurt and garam masala? Maybe do a little spicy. Do you guys want to talk about reversing aging?

</details>

**Chamath**: 是的。所以，我想聊聊，但我得下线了。好了，伙计们。我得去埃菲尔铁塔了。保罗，我来顶着。观众们会留下的。

<details>
<summary>Original English</summary>

**Chamath**: Yes. So, I want to talk about but I got to drop. All right, guys. I got to go to the EIFFEL TOWER. PAUL, I'LL COVER IT. THE audience will stick around.

</details>

### 科学角：逆转衰老的新突破

**David Friedberg**: 科学角时间。好了。那么，Chamath，如果你想的话也可以先下线。我一个人来做科学角。过去我们讨论过山中因子（Yamanaka factors），这是一种可以进入细胞并逆转细胞衰老的蛋白质，能让细胞重新表现得像年轻细胞一样。非常神奇。在这个领域有很多进展正在发生。但这周刚刚发表的一篇让大家都快疯掉的论文，是由 Calico 联合发表的。Calico 是谷歌旗下那种超级神秘、他们不被允许谈论的年龄逆转初创公司，这次是与一家名为 Revel Pharma 的组织合作。他们关注的焦点是被称作细胞外基质（extracellular matrix）的部分。也就是细胞外部会衰老的部分。那么，细胞外部的衰老到底是什么样子的呢？随着时间的推移，糖分和脂肪会与我们细胞之间区域的蛋白质结合，然后堆积起来。它们不会被清理掉。由于它们堆积且未被清除，这就使得你的身体更难清理那个区域、维护那个区域。这会导致粘连。它会导致结合。进而降低流动性，最终导致我们的皮肤长出皱纹，让我们关节的活动变得更加困难。

<details>
<summary>Original English</summary>

**David Friedberg**: Science corner. All right. So, Chamath, you can drop two if you want. I'll cover science corner solo. So in the past we've talked about Yamanaka factors which are these proteins that can go into cells and reverse the aging of the cell and the cell starts to act young again. Pretty amazing. And uh there's a lot of advancement happening on that front. But this paper that came out just this week that everyone's kind of going crazy about was put out uh jointly by Calico which is Google's kind of you know age reversal startup that's super secretive that they're not allowed to talk about in partnership with a group called Revel Pharma. And what they focused on was what's called the extracellular matrix. The parts outside of the cell that age. And and what does aging actually look like outside of the cell? Well, over time, sugars and fats bind to proteins in the area between our cells and they accumulate. They don't get cleaned off. And as they accumulate and they don't get cleaned off, they make it harder for your body to clean out that area, to maintain that area. It causes stickiness. It causes binding. And that reduces mobility. and ultimately leads to things like wrinkles in our skin, makes it harder for our joints to move.

</details>

**Speaker B**: 那就是内脏脂肪吗？

<details>
<summary>Original English</summary>

**Speaker B**: Is that what visceral fat is?

</details>

**David Friedberg**: 不，这叫做糖化（glycation）。所以，它是糖和脂肪与那些存在于细胞外基质中的蛋白质的结合。

<details>
<summary>Original English</summary>

**David Friedberg**: No, it's called glycation. And so it's the binding of sugar and fat to the proteins that sit in that extra cellular

</details>

**Speaker B**: 在细胞之间。完全正确。

<details>
<summary>Original English</summary>

**Speaker B**: in between the cells. Exactly.

</details>

**David Friedberg**: 没错，就是细胞之间那整个粘稠的区域。当你年轻时，这里运作良好，一切都很顺畅。如果蛋白质分解了，它们会被替换掉。但随着年龄增长，糖分和脂肪会粘附在这些蛋白质上，将它们堵塞。当它们被堵塞时，你的身体就无法修复它们。无法清理它们。更重要的是，它改变了那些蛋白质的结构和形状。因此，像胶原蛋白这样原本离得很远的东西就会粘在一起。这会导致皱纹等问题，还会导致活动不便。它还会引起炎症，因为此时这些蛋白质看起来和原本应该的样子不一样了。你的身体就会开始攻击它们。这就激活了炎症。这就是为什么我们随着年龄增长炎症越来越多的原因之一。其中一种被称为晚期糖基化终产物（这是这些东西的专业术语）的关键物质叫 CML。CML 算是这种细胞外基质中形成并驱动衰老的主要分子，没有什么东西能分解它。所以，这些科学家着手尝试创造一种酶。酶是一种能够分解某种物质的蛋白质，他们想制造一种能分解 CML 的酶。记住，蛋白质只是一系列氨基酸。而这些氨基酸是由 DNA 编码的。所以你可以放入三个字母的 DNA 来产生一个氨基酸。你真的可以打印出 DNA，然后把它放进细菌里去制造蛋白质，接着测试这些蛋白质看看它们能做什么。这就是现在蛋白质合成和蛋白质测试的现代时代。于是这些人开始行动，他们瞄准了目标 CML，试图弄清楚如何才能真正降解 CML，清理那个细胞外基质，从而逆转衰老。他们从 AlphaFold 开始，利用 AlphaFold 寻找一种能够结合 CML 并激活某种能将其分解的酶促过程的蛋白质。然后他们提取了 AlphaFold 找到的那种产自细菌的蛋白质。他们生产了它。他们开始对其进行测试，接着他们开始寻找该蛋白质中可以进行优化的那些结合物或部分，并利用 DNA 编程来对其进行修改，制造了数百甚至数千种变体来测量其活性，也就是它分解 CML 的能力有多强。他们通过五个不同的周期递归地进行了这项工作。最终，当他们在试管中使这种蛋白质能很好地分解 CML 后，他们开始在我们体内常见的蛋白质上测试它，比如酪蛋白、胶原蛋白、眼部的视黄醇蛋白、血红蛋白。他们能够清除 52% 到 97% 的 CML，直接将其降解掉。

<details>
<summary>Original English</summary>

**David Friedberg**: And so it's that whole gunky area in between the cells that when you're young works well, everything's smooth. The proteins get replaced if they break down. And as you get older, sugars and fats kind of stick to these proteins, block them up. And as they get blocked up, your body can't repair them. It can't clean them. And more importantly, it changes the structure and the shape of those proteins. So things like collagen that are far apart stick together. And that causes things like wrinkles and that causes immobility. And it also causes inflammation because then those proteins kind of look different than they're supposed to. And your body starts to attack them. And that activates inflammation. And that's why we get one of the reasons why we get more and more inflammation as we get older. And so one of the key what are called advanced glycation end products that's the term for these things is called CML. CML is kind of the predominant molecule that that gets formed in this extracellular matrix that's driving aging and nothing breaks it down. So these scientists set out to try and create an enzyme. An enzyme is a protein that breaks something down um that can break down CML. And remember, a protein is just a series of amino acids. And those amino acids are programmed by DNA. So you can put three letters of DNA to make an amino acid. So you can literally just print DNA and then put it in a bacteria to print proteins and then test those proteins to see what they do. That's the the modern kind of era of kind of protein synthesis and protein testing. And so these guys kind of went out and they took the target which is CML and tried to figure out okay how do we actually degrade CML clear that extracellular matrix and reverse aging. And they started with AlphaFold and they used Alphafold to find a protein that could bind to CML and activate an enzyatic or process that would break it down. And then they took that protein from AlphaFold that comes out of a bacteria. They produced it. They started to test it and then they started to find some of the binders or the parts of that protein that they could make better and they used you know DNA programming to change it and they made hundreds and then thousands of variants of it to measure activity which is how good is it at breaking down the CML and they did this recursively five different cycles and then eventually they tested it once they' kind of gotten it breaking down the CML really well in a test tube they started to test it on the proteins that we would find in our body, cassine, collagen, retinal proteins which are in your eye, hemoglobin, and they were able to get rid of 52 to 97% of the CML, just degraded away.

</details>

**David Friedberg**: 然后他们发现了几个位点，在那些位点能够降解超过 90%。接着，他们取了老年患者捐献的真实人体皮肤，将这种酶涂在那些皮肤上，结果消除了皮肤上 55% 的 CML，这基本上将皮肤的年龄逆转到了 31 岁的状态。这可是来自于 70 岁以上患者的皮肤，仅仅是在皮肤上涂抹了这种酶。因此，这可以说是 AlphaFold 与所谓的定向进化（directed evolution）相结合的突破性展示。在定向进化中，你改变 DNA 的顺序从而改变蛋白质的结构，去测试不同的蛋白质，进行高通量筛选，最终制造出一种当今自然界中不存在的全新蛋白质，它能为人类健康带来非常深远的改变。那么接下来的问题是，好吧，太棒了，这种酶太厉害了。我们该如何让它进入我们的身体？我们该如何让它进入细胞外基质？它会是一种面霜吗？会是一种注射剂、一种补充剂吗？我们最终能否注射一种 mRNA 疫苗，让蛋白质在我们体内产生，并开始从内部进行降解？还有很多问题有待解答，但我认为，它确实为我们指明了一条光明的发展道路。

<details>
<summary>Original English</summary>

**David Friedberg**: And then they um they found several sites where they were able to degrade over 90%. And then they took actual human skin from elderly patients that had donated their skin and they put this enzyme onto that skin and they were able to eliminate 55% of the CML on the skin which basically reversed the skin's age down to the age of a 31y old. This is from greater than 70 year old patients just by putting this enzyme on the skin. And so it's kind of a groundbreaking demonstration of combination of alphafold what's called directed evolution where you change the order of the DNA that changes the structure of the protein to test different proteins do high throughput screening and ultimately make a novel protein that doesn't exist in nature today that can do something pretty profound for human health. And now the next set of questions is okay well great this enzyme is awesome. How are we going to get it into our bodies? How are we going to get it into that extracellular matrix? Is it going to be a cream? Is it going to be a shot, a supplement? Could we eventually take an RNA shot that makes the protein inside of our body and starts to do the degradation from within? A lot of questions kind of still to be answered, but it really, I think, lights a great path forward.

</details>

**Speaker B**: 真是太神奇了，对于我们正在开发的这些新型疗法来说。这真是牛逼爆了。我是说，兄弟，你看，我现在的臀部和肩膀到处都有这种关节痛。好像在所有地方你都能感觉到自己正在变老。

<details>
<summary>Original English</summary>

**Speaker B**: Amazing for these novel therapies that we're developing. It's [ __ ] awesome. I mean, dude, likeing, you know, all my I got all these joint pains in my hip and my shoulder now. Like everything you can feel yourself getting older.

</details>

**David Friedberg**: 嗯，那个，我现在就可以告诉你。那不会是首选市场。首选市场将是化妆品和……

<details>
<summary>Original English</summary>

**David Friedberg**: Well, that's I I will tell you this right now. That will not be the first market. The first market will be cosmetic and

</details>

**Speaker B**: 皮肤化妆品。没错。

<details>
<summary>Original English</summary>

**Speaker B**: cosmetic skin. Yeah.

</details>

**David Friedberg**: 那将是一个万亿美元级的市场。如果你们能研发出一种面霜，

<details>
<summary>Original English</summary>

**David Friedberg**: It will be a trillion dollar market. If if you can create a cream,

</details>

**Speaker B**: 老兄，如果你真的能把这种酶涂在皮肤上并让它吸收，

<details>
<summary>Original English</summary>

**Speaker B**: dude, if you could put this enzyme literally on your skin and have it absorb

</details>

**David Friedberg**: 变成一种面霜。

<details>
<summary>Original English</summary>

**David Friedberg**: a cream.

</details>

**Speaker B**: 是啊。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**David Friedberg**: 游戏结束。仅仅那块市场本身就是 2 万亿美元。不过，说真的，兄弟，AI，让我们聊聊 AI 的应用吧，这就是为什么它实际上非常棒，为什么大家都应该能达成共识，而且你不会被一些外部的心理战（psyop/scop）所蒙蔽。这真是太震撼了。我的意思是，这次是用 AlphaFold 去发现这个东西，让它进化并推动了这个结果。每个人都能从中受益。在这个时代，我们能拥有这样的工具，真的是意义非凡。

<details>
<summary>Original English</summary>

**David Friedberg**: Game over. It's it's a that that alone is $2 trillion. But I mean, dude, AI, let's just talk about applications of AI, why it's actually awesome that everyone should be able to agree on and you can't be convinced by some foreign scop. This is [ __ ] awesome. I mean, this was alpha full used to discover this thing and evolve it and drive this outcome. Everyone can benefit from it. It's just so profound that we have this tool at our disposal in this day and age.

</details>

**Speaker B**: 我觉得非常棒。总之，感谢大家留下来收看科学角。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's pretty awesome. Anyway, thanks for sticking around for Science Corner.

</details>

**Speaker C**: 伙计们，我爱你们。

<details>
<summary>Original English</summary>

**Speaker C**: Guys, I love you.

</details>

**Speaker A**: 好的，兄弟。也爱你。

<details>
<summary>Original English</summary>

**Speaker A**: All right, bro. Love you, too.

</details>

**Speaker D**: 我们会让你的盈利继续狂飙。我们把它开源给……

<details>
<summary>Original English</summary>

**Speaker D**: We'll let your winners ride. We open sourced it to

</details>

<!-- chunk 12/12 -->

**Speaker A**: ……粉丝们，他们为此简直疯狂了。

<details>
<summary>Original English</summary>

**Speaker A**: ... the fans and they've just gone crazy with it.

</details>

**Speaker B**: 最好的闺蜜是我的狗占据了你的车道。

<details>
<summary>Original English</summary>

**Speaker B**: Queen of besties are my dog taking your driveways.

</details>

**Speaker C**: 哦天哪，我的男装裁缝要碰面了。

<details>
<summary>Original English</summary>

**Speaker C**: Oh man, my habitasher will meet.

</details>

**Speaker D**: 我们都应该直接开个房间，然后举办一场盛大的群交派对，因为他们都太没用了。就像他们只是需要释放这种性张力。

<details>
<summary>Original English</summary>

**Speaker D**: We should all just get a room and just have one big huge orgy cuz they're all just useless. It's like this like sexual tension that they just need to release.

</details>

**Speaker E**: 你的脚。

<details>
<summary>Original English</summary>

**Speaker E**: Your feet.

</details>

**Speaker F**: 我们需要买点周边商品。

<details>
<summary>Original English</summary>

**Speaker F**: We need to get merch.

</details>

**Speaker G**: 我要全力以赴。我要全力以赴。

<details>
<summary>Original English</summary>

**Speaker G**: I'm going all in. I'm going all in.

</details>