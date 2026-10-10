---
author: The Ezra Klein Show
date: '2026-03-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xc97F2CFBOY
speaker: The Ezra Klein Show
tags:
  - ai-policy
  - state-power
  - ai-alignment
  - mass-surveillance
  - technological-contingency
title: 五角大楼为何要“摧毁”Anthropic？AI与国家安全的哲学与政治博弈
summary: 本期节目深入探讨了美国国防部（现称战争部）与AI公司Anthropic之间关于AI使用限制的冲突。核心在于Anthropic拒绝AI被用于大规模国内监控和全自主致命武器。采访揭示了AI对法律、政府权力边界和民主价值的深远影响，以及AI模型伦理校准的复杂性，质疑了政府是否应干预私营AI公司的价值观。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ezra Klein
  - Dean Ball
  - Pete Hegseth
  - Emil Michael
  - Dario Amadei
  - Donald Trump
  - Neil Gorsuch
  - Elon Musk
  - Sam Altman
  - Greg Brockman
  - Michael Oakeshott
  - Gordon Wood
  - Eugene Genovese
companies_orgs:
  - Anthropic
  - U.S. military
  - OpenAI
  - Palantir
  - XAI
  - Google Alphabet
products_models:
  - Claude
  - Gemini
  - Grok
  - ChatGPT
media_books:
  - Rationalism in Politics
  - On Being Conservative
  - Empire of Liberty
  - Roll Jordan Roll
status: evergreen
---
### AI公司与五角大楼的冲突

**Ezra Klein**: 现在，每个人都在关注伊朗，但在它周围发生着一个故事，我认为我们不应忽视，因为它不仅关乎我们可能如何打这场战争，还关乎我们未来将如何打所有战争。上周五，国防部长**Pete Hegseth**宣布他正在终止政府与AI公司**Anthropic**的合同，并打算将其指定为供应链风险。供应链风险的指定适用于那些危险到不能存在于美国军事供应链中任何地方的技术。它们不能被任何承包商或分包商在供应链的任何地方使用。以前曾对像中国**华为**这样的外国公司生产的技术使用过，我们担心间谍活动或在冲突中失去关键能力。它从未针对一家美国公司使用过。更令人震惊的是，它正被用于，或者至少被威胁用于一家甚至现在正在向美国军方提供服务的美国公司。**Anthropic**的AI系统**Claude**曾用于对**Nicolas Maduro**的突袭，据报道也在与伊朗的战争中使用。但**Anthropic**划下了一些红线，不允许战争部逾越。导致他们关系破裂的导火索是，利用AI系统使用商业可用数据监视美国人民。那么，这里到底发生了什么？政府想如何使用这些AI系统？这意味着什么？他们正在试图摧毁美国一家顶级的AI公司，仅仅因为该公司对这些新型、强大且不确定的技术如何部署设定了一些条件。我今天的嘉宾是**Dean Ball**。Dean是美国创新基金会的高级研究员，也是时事通讯《Hyperdimensional》的作者。他曾是**特朗普**白宫的AI高级政策顾问，也是他们AI行动计划的主要撰写者。但他对他们现在所做的一切感到非常愤怒。一如既往，我的电子邮件是Ezra Klein Show at NYTimes.com。**Dean Ball**，欢迎来到节目。

<details>
<summary>Original English</summary>

**Ezra Klein**: So right now, everyone is thinking about Iran, but there's a story happening around it that I think we need to not lose sight of, because it's about not just how we are potentially fighting this war, but how we'll be fighting all wars going forward. On Friday of last week, Secretary of Defense Pete Hegseth announced that he was breaking the government's contract with the AI company Anthropic, and he intended to designate them a supply chain risk. The supply chain risk designation is for technologies so dangerous they cannot exist anywhere in the U.S. military supply chain. They cannot be used by any contractor or any subcontractor anywhere in that chain. It has been used before for technologies produced by foreign companies like China's Huawei, where we fear espionage or losing access to critical capabilities during a conflict. It has never been used against an American company. What is even wilder about this is that it is being used, or at least being threatened, against an American company that is even now providing services to the U.S. military as we speak. Anthropic's AI system Claude was used in the raid against Nicolas Maduro, and it is reportedly being used in the war with Iran. But there were red lines that Anthropic would not allow the Department of War to cross. The one that led to the disintegration of their relationship was over using AI systems to surveil the American people using commercially available data. So what is going on here? How does the government want to use these AI systems, and what does it mean? They are trying to destroy one of America's leading AI companies for setting some conditions on how these new, powerful, and uncertain technologies can be deployed. My guest today is Dean Ball. Dean is a senior fellow at the Foundation for American Innovation and author of the newsletter Hyperdimensional. He was also a senior policy advisor on AI for the Trump White House and was the primary writer of their AI action plan. But he has been furious at what they are doing here. As always, my email, Ezra Klein Show at NYTimes.com. Dean Ball, welcome to the show.

</details>

**Dean Ball**: 谢谢你邀请我。

<details>
<summary>Original English</summary>

**Dean Ball**: Thanks so much for having me.

</details>

**Ezra Klein**: 我想让你给我讲讲这个时间线。我们是如何走到战争部将**Anthropic**——美国一家顶级的AI公司——标记为供应链风险的境地的？

<details>
<summary>Original English</summary>

**Ezra Klein**: So I want you to walk me through the timeline here. How did we get to the point where the Department of War is labeling Anthropic, one of America's leading AI companies, a supply chain risk?

</details>

### 时间线与使用限制的争议

**Dean Ball**: 我认为时间线真正始于2024年夏天，在**拜登**政府时期，当时国防部（现在是战争部）与**Anthropic**就**Claude**在机密环境中的使用达成了一项协议。基本上，语言模型被政府机构（包括国防部）用于非机密环境中，处理诸如审查合同、导航采购规则等日常事务。但也有这些机密用途，包括情报分析，以及可能实时协助军事行动。**Anthropic**是对这些国家安全用途最热心的公司，他们与**拜登**政府达成协议，基本开展这项工作，但附带了一些使用限制。**禁止大规模国内监控和全自主致命武器**是其中之一。在2025年夏天，**特朗普**政府时期（完全披露，我当时在**特朗普**政府工作，但完全没有参与这项交易），政府决定扩大该合同，并保留了相同的条款。因此，**特朗普**政府也同意了这些限制。然后在2025年秋天，我怀疑这与**Emil Michael**被参议院确认为战争部研究与工程副部长有关。他上任后，审视了这些事情，或者说参与了审视，得出的结论是，不，我们不能受这些使用限制的约束。异议的重点与其说是在限制的实质内容上，不如说是在反对使用限制本身。所以，这场冲突实际上在几个月前就开始了，据我所知，它开始于对委内瑞拉**Nicolas Maduro**的突袭之前。但这些军事行动可能增加了强度，因为**Anthropic**的模型在突袭中被使用了。然后我们就到了现在这个地步，合同已经破裂，战争部和**Anthropic**都得出结论，他们无法再合作。惩罚才是真正的问题所在，我想。

<details>
<summary>Original English</summary>

**Dean Ball**: I think the the timeline really begins in the summer of 2024 during the Biden administration, when the Department of Defense, now Department of War, and Anthropic came to an agreement for the use of Claude in classified settings. Basically, you know, language models are used in government agencies, including the Department of Defense, in unclassified settings for things like reviewing contracts and and navigating procurement rules and mundane things like that. But there are these classified uses which include intelligence analysis and and potentially assisting operations in real time, military operations in real time. And Anthropic was the company most enthusiastic about these national security uses, and they came to an agreement with the Biden administration to basically to do this with a couple of usage restrictions. Domestic mass surveillance was a prohibited use, and fully autonomous lethal weapons. In the summer of 2025 during the Trump administration, and full disclosure, I was in the Trump administration when this happened, though not at all involved in this deal. The administration made the decision to expand that contract and kept the same terms. So the Trump administration agreed to those restrictions as well. And then in the fall of 2025, I think I suspect that this correlates with the confirmation, the Senate confirmation of Emil Michael, Undersecretary of War for Research and Engineering. He comes in, he looks at these things, I think, or or perhaps is involved in looking at these things, and comes to the conclusion that no, we cannot be bound by these usage restrictions. And the objection is not so much to the substance of the restrictions, but to the idea of usage restrictions in general. So that conflict actually began several months ago, and as far as I understand, it begins before, you know, the the raid on in Venezuela on Nicolas Maduro and and all that kind of stuff. But these military operations maybe increase the intensity because Anthropic's models are used during that raid. And then we get to the point where, you know, basically where we are now, where the contract has kind of fallen apart, and DOW, Department of War, and Anthropic have come to the conclusion that they can't do business with one another, and the punishment is the real question here, I think.

</details>

**Ezra Klein**: 你想解释一下惩罚是什么吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: And do you want to explain what the punishment is?

</details>

**Dean Ball**: 是的，基本上我对此的看法是，我认为战争部说我们原则上不希望有这种使用限制，这对我来说似乎没问题。他们说，不，一家私营公司不应该决定——**Dario Amadei**不应该决定什么时候自主致命武器可以投入使用。那是战争部的决定。那是政治领导人会做出的决定。我认为这是对的。我同意**特朗普**政府在这一点上的看法。所以我认为解决方案是，如果双方无法就业务条款达成一致，通常发生的情况是取消合同，不再进行任何交易。不再有商业关系。但战争部长**Pete Hegseth**表示他将实施的惩罚是，宣布**Anthropic**为供应链风险，这通常只保留给外国对手。**Hegseth**部长说，他希望阻止战争部的承包商（顺便说一句，我会交替使用国防部和战争部，因为我仍然称X为Twitter）与**Anthropic**进行任何商业往来。我不认为他们真的拥有那种权力。我不认为他们真的拥有那种法定权力。我认为你最多能做的是说，任何战争部承包商都不能在履行军事合同时使用**Claude**，但你不能说他们不能与**Anthropic**有任何商业关系。我不这么认为，但这正是**Hegseth**部长声称他将要做的事情，如果他真的这么做，那对**Anthropic**来说将是生死存亡的问题。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, so basically my view on this has been that I think that the Department of War saying we don't want usage restrictions of this kind as a principle, that seems fine to me. That seems perfectly reasonable for them to say, no, a private company shouldn't determine, you know, Dario Amadei does not get to decide when autonomous lethal weapons are ready for primetime. That's a Department of War decision. That's a decision that political leaders will make. And I think that's right. I think I agree with with the Trump administration on that front. So I think the solution to this is if you cannot agree to terms of business, what typically happens is you cancel the contract, and you don't you don't transact any more money. You don't have commercial relations. But the punishment that Secretary of War Pete Hegseth has said he is going to issue is to declare Anthropic a supply chain risk, which is typically reserved only for foreign adversaries. What Secretary Hegseth has said is that he wants to prevent Department of War contractors, and by the way, I'm going to refer to it variously as Department of Defense and Department of War, because I have a I still call X Twitter. Yeah, I still call X Twitter. Anyway, all military contractors can be prevented from doing any commercial relations in Secretary Hegseth mind from with Anthropic. I don't think they actually have that power. I don't think they actually have that statutory power. I think that what the maximum of what I think you could do is say the no Department of War contractor can use Claude in their fulfillment of a military contract, but you can't say you can't have any commercial relations with them. I don't think, but that is what Secretary Hegseth has claimed he is going to do, which would be existential for the company if he actually does it.

</details>

**Ezra Klein**: 好的，这里面有很多内容。是的。我想展开讨论，但我想从这里开始。对于大多数人来说，他们有时（如果使用的话）会用聊天机器人，他们的经验是它们在某些方面表现很好，在其他方面则不然。而且在2024年6月**拜登**政府达成这项协议时，我们做得并不好。所以你现在告诉我，我们正在将**Claude**整合到国家安全基础设施中，这某种程度上涉及对**Nicolas Maduro**的突袭。怎么回事？公众应该在多大程度上信任联邦政府能够很好地处理这些系统，即使是建造它们的人也并不完全了解它们？

<details>
<summary>Original English</summary>

**Ezra Klein**: Okay, there's a lot in here. Yes. I want to expand on, but but I want to start here. For most people, they use chatbots sometimes, if at all, and their experience of them is that they are pretty good at some things and not at others. And we're not all that good in June of 2024 when the Biden administration was making this deal. So here you are telling me that we are integrating, in this case, Claude throughout the national security infrastructure that's involved somehow in the raid on Nicolas Maduro. How? And to what degree should the public trust that the federal government knows how to do this well with systems that even the people building them don't understand all that well?

</details>

### AI在国家安全领域的应用与信任问题

**Dean Ball**: 是的，我认为有一点是，你必须通过实践学习。我认为，是的，我们不知道如何将AI真正整合到任何组织中，对吗？先进的AI系统，我们不知道如何将它们整合到复杂的现有工作流程中，所以你学习的方法就是通过实践。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, so I think one thing is that you have to learn by doing, and I think so. It is it is the case that you know we don't know how to integrate AI really into any organization, right? Advanced AI systems, we don't know how to integrate them into complex pre-existing workflows, and so the way you do it is learning by doing.

</details>

**Ezra Klein**: **Pete Hegseth**部长难道没有在战争部贴出海报说“部长希望你们使用AI”吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: Didn't Pete Hegseth have posters around the Department of War saying the secretary wants you to use AI?

</details>

**Dean Ball**: 他们对AI的采用非常热情，对吗？所以，这是我思考这些系统在国家安全背景下能做什么的方式。首先，情报界收集的数据量超出了他们可能分析的能力，这是一个长期存在的问题。我记得看到过一个情报机构（我忘了是哪个情报机构，但其中一个）基本上说他们每年收集的数据量，仅仅这一个机构，就需要**800万**名情报分析员才能彻底、适当地处理所有这些数据。这只是一个机构，而且比整个联邦政府的雇员总数还要多得多。AI能做什么？嗯，它可以自动化很多分析工作。所以，转录文本，然后分析文本信号情报处理。有时这需要为正在进行的军事行动实时完成，所以这可能是一个很好的例子。然后我认为另一个领域，当然是，这些模型在软件工程方面已经做得相当出色，因此在网络防御和网络攻击行动中，它们可以提供巨大的效用。

<details>
<summary>Original English</summary>

**Dean Ball**: I they are very enthusiastic about AI adoption, right? So here's how I would think about what these systems can do in national security context. First of all, there's a long-standing issue that the intelligence community collects more data than it can possibly analyze. I remember seeing something from one of I forget which which intelligence which which intelligence agency, but one of them that essentially said that they collect so much data every year, just this one, that they would need 8 million intelligence analysts to thoroughly to properly process all of it. That's just one agency, and that's more it's far more employees than the federal government as a whole has. And what can AI do? Well, you can automate a lot of that analysis. So transcribing text and then analyzing that text signals intelligence processing. Sometimes that needs to be done in real time for an ongoing military operation, so that might be a good example. And then I think another area, of course, is you know these models have gotten quite good at software engineering, and so there are cyber defensive and cyber offensive operations that where they can deliver tremendous utility.

</details>

### 大规模监控与法律漏洞

**Ezra Klein**: 让我们谈谈大规模监控。因为我的理解是，与双方人士交谈后，现在已经广为报道，这项合同在最后关键时刻因**大规模监控**而告吹。**Emil Michael**找到**Dario**说，我们想和你们签订这份合同，但你们需要删除禁止我们使用**Claude**分析大量收集的商业数据的条款。是的。你为什么不解释一下那里发生了什么？

<details>
<summary>Original English</summary>

**Ezra Klein**: Let's talk about mass surveillance here, because my understanding, talking to people on both sides of this, and it's now been I think fairly widely reported that this contract fell apart over mass surveillance at the at the final critical moment. Emil Michael goes to you know Dario and says, we want you, we will agree to this contract, but you need to delete the clause that is prohibiting us from using Claude to analyze bulk collected commercial data. Yeah. And why don't you explain what's going on there?

</details>

**Dean Ball**: 国家安全法充满了陷阱，充满了法律术语，我们口语中经常使用的术语，其实际法定定义与你从口语推断出来的含义大相径庭。像“私人”、“机密”、“监控”这类词，不一定具有它们在自然语言中的含义。这在所有法律中都是如此。所有法律都必须以某种方式定义术语，这不一定是我们日常语言中的用法，但我认为这里白话和法规之间的区别是你能得到的最大的。所以**监控**是收集或获取私人信息，但这不包括商业可用信息。所以如果你购买了某种数据集然后分析它，那在法律上不一定是**监控**。所以如果他们入侵我的电脑或手机来查看我在网上做什么，那是**监控**。那是**监控**。但如果他们购买数据，如果他们到处安装摄像头，那将是**监控**。但如果摄像头无处不在，他们从摄像头购买数据然后分析这些数据，那可能不一定是**监控**。或者如果他们购买我所有在线活动的信息，这些信息对广告商来说非常容易获得，然后用它来描绘我的形象，那不一定是我实际在世界上的**监控**。

<details>
<summary>Original English</summary>

**Dean Ball**: National security law is filled with gotchas, filled with legal terms of art, terms that we use colloquially quite a bit, where the actual statutory definition of that term is quite different from what you would infer from the colloquial use of the term. Things like private, confidential, surveillance, these sorts of terms are don't necessarily have the meaning that they do in natural language. That's true in all law. All laws have to define terms in certain ways that are not necessarily how we use them in in our normal language, but I think the difference between vernacular and statute here is about as stark as you can get. So surveillance is the collection or acquisition of private information, but that doesn't include commercially available information. So if you buy something, if you buy a data set of some kind and then you analyze it, that's not necessarily surveillance under the law. So if they hack my computer or my phone to see what I'm doing on the internet, that's surveillance. That would be surveillance. But if they buy data, if they put cameras everywhere, that would be surveillance. But if there are cameras everywhere and they buy the data from the cameras and then they analyze that data, that might not necessarily be surveillance. Or if they buy information about everything I'm doing online, which is very available to advertisers, and then use it to create a picture of me, that's not or necessarily surveillance where you physically are in the world.

</details>

**Dean Ball**: 我退一步讲，只是说有很多数据。世界释放了很多信息，对吗？你的Google搜索结果，你的智能手机位置数据，对吗？所有这些事情，政府中没有人真正分析它的原因并不是他们无法获取和分析。而是因为他们没有人员，对吗？他们没有成千上万的人来弄清楚普通人在做什么。AI的问题在于，AI为他们提供了无限可扩展的劳动力，因此，每项法律都可以被一丝不苟地执行，对一切进行**完美监控**，对吗？那是一个可怕的未来。我们认为我们与某些形式的暴政或令人恐惧的**全景监狱**之间的空间是由法律保护所占据的，但我认为这里许多恐惧的核心在于，它实际上不仅仅是法律保护。它实际上是政府无法吸收关于公众的这些信息，然后对其采取任何行动。

<details>
<summary>Original English</summary>

**Dean Ball**: I'll step back for a second and just say that there's a lot of there's a lot of data out there. There's a lot of information that the world gives off, right? That your Google search results, your smartphone location data, right? All these things, and it's not the reason that no one really analyzes it in the government is not so much that they can't acquire it and do so. It's because they don't have the personnel, right? They don't have millions and millions of people to like figure out what the average person is up to. The problem with AI is that AI gives them that infinitely scalable workforce, and thus, you know, every law can be enforced to the letter with perfect surveillance over everything, right? And that's that's a scary future. We think of the space between us and certain forms of tyranny or the feared panopticon as a space inhabited by legal protection, but one thing that has seemed to me to be at the core of a lot of at least fear here is that it's in fact not just legal protection. It's actually the government's inability to have the absorption of that level of information about the public and then do anything with it.

</details>

**Ezra Klein**: 是的。如果突然之间，你彻底改变了政府的能力，那么在不改变任何法律的情况下，你就改变了这些法律中可能实现的东西。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes. And if all of a sudden you radically change the government's ability, then without changing any laws, you have changed what is possible within those laws.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes.

</details>

**Ezra Klein**: 所以你刚才说，大规模监控或任何监控都是法律术语，但对于人类来说，它是一种你正在运作或没有运作的状态。对。而恐惧在于，据我所知，我们现在拥有的AI系统，或者很快就会出现的AI系统，将有可能利用大量的商业数据来描绘人群的画像及其正在做的事情，然后发现和理解人们的能力将远远超出我们以前的水平，这引发了法律以前不必考虑的隐私问题。

<details>
<summary>Original English</summary>

**Ezra Klein**: So you were saying a minute ago, mass surveillance or surveillance at all is a term of legal art, but for human beings, it is a condition that you either are operating under or not. Right. And the fear is that, as I understand it, that either the AI systems we have right now or the ones that are coming down the pike quite soon would make it possible to use bulk commercial data to create a picture of the population and what it is doing, and then the ability to find people and understand them that just goes so far beyond where we've been that it raises privacy questions that the law just did not have to consider until now.

</details>

**Dean Ball**: 是的。因此，这些法律未能达到其制定时的精神要求。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. And so the laws are not up to the task of the spirit in which they were passed.

</details>

**Dean Ball**: 我会更进一步说，我们目前在先进资本主义民主国家中拥有的整个**技术官僚民族国家**，是一个技术上偶然的制度综合体，而AI带来的问题是，它深刻地改变了这些技术偶然性。因此，这表明整个制度综合体——我们不知道它将以我们无法预测的方式崩溃。这是一个很好的例子。我认为，换句话说，这不仅是一个重大而深刻的问题，而且是一个更广泛问题空间中的一个重大而深刻问题的例子，我认为我们将在未来几十年中一直面对它。

<details>
<summary>Original English</summary>

**Dean Ball**: I would step back even further and just say that you know the entire like technocratic nation state that we currently have in kind of advanced capitalist democracies is a technologically contingent institutional complex, and the problem that AI presents is that it changes the technological contingencies quite profoundly. And so what that suggests is that the entire institutional complex is we don't it's going to break in ways that we cannot quite predict. This is a good example. I think this is, in other words, not only is this a major and profound problem, but it is an example of a major and profound problem of a of a broader problem space that I think we will be occupying for the coming decades.

</details>

**Ezra Klein**: 你所说的**技术偶然性**是什么意思？

<details>
<summary>Original English</summary>

**Ezra Klein**: What do you mean by technological contingencies?

</details>

**Dean Ball**: 当今的民族国家在一个没有印刷机、无法以极低成本任意复制文本的世界中是不可能存在的。它不可能在没有当前电信基础设施的世界中存在，对吗？就像它需要这些技术。它建立并依赖于其组建时代的大发明，对吗？所有机构都是如此。所有机构都受到技术限制。我们现在正在进行一场深受技术限制的对话。AI以难以描述和抽象的方式改变了所有这一切，但我认为，我们今天所称的AI政策，过于关注我们将对AI系统和构建它们的公司等应用何种**对象级法规**，而不是思考这个更广泛的问题：哇，我们所做的所有这些假设现在都打破了，我们该怎么办？

<details>
<summary>Original English</summary>

**Dean Ball**: The the current nation state could not possibly exist in a world without the printing press, in a world without the ability to write down text and you know arbitrarily reproduce it at very low cost. It couldn't exist without the current telecommunications infrastructure, right? Like it needs the the the nation state needs these tech. It's it it is built dependent upon the macro inventions of the era in which it was assembled, right? That's always true for all institutions. All institutions are technologically contingent. We are having a profoundly technologically contingent conversation right now. It could AI changes all of this in ways that are are like hard to describe and kind of abstract, but I I think you know AI policy, this thing that we call AI policy today, is way too focused on what object level regulations will we apply to the AI systems and the companies that build them, et cetera, et cetera, instead of thinking about this broader question of wow, there are all these assumptions we made that are now broken, and what are we going to do about them?

</details>

**Ezra Klein**: 给我举例说明这两种思维方式。什么是**对象级法规**或假设，你所说的法律和法规是哪种类型？

<details>
<summary>Original English</summary>

**Ezra Klein**: Give me examples of those two ways of thinking. What is an object level regulation or assumption, and then what are the kinds of laws and regulations you're talking about?

</details>

**Dean Ball**: **对象级法规**是指我们要求AI公司进行算法影响评估，以评估其模型是否存在偏见，对吗？顺便说一句，我曾多次批评这项政策。你可以说我们将要求你进行灾难性风险测试，对吗？诸如此类。我并不是说这是一个我们需要思考的重要领域，但这只是更广泛问题中的一小部分：哇，我们整个法律体系都建立在，我认为根本上是**不完善的法律执行**，对吗？我们有大量的法规，在许多情况下，数量惊人，范围极广，而这一切之所以奏效，是因为政府并没有统一地执行这些法律。AI的问题在于它能够实现**法律的统一执行**。

<details>
<summary>Original English</summary>

**Dean Ball**: An object level regulation would be to say we are going to require AI companies to write to do algorithmic impact assessments to assess whether their models have bias, right? That's a policy I've criticized quite a bit, by the way. You could say we're going to require you to do testing for catastrophic risks, right? Things like that. I'm not saying that you know that's a that's an important area that we need to think about, but that's just like one small part of the broader issue of wow, our entire legal system is predicated on I think fundamentally as used imperfect enforcement of the law, imperfect enforcement of the law, right? We have huge number of statutes, you know, unbelievably large, unbelievably broad sets of laws in many cases, and the reason it all works is that the government does not enforce those laws anything like uniformly. The problem with AI is that it enables uniform enforcement of the law.

</details>

### 五角大楼的立场与权力边界

**Ezra Klein**: 这是**五角大楼**的立场。他们对这个未经选举的CEO感到愤怒，他们开始将其描述为“**觉醒的激进分子**”，告诉他们法律不够完善，不能信任他们以符合公共利益的方式解释法律。**Pete Hegseth**部长发推文说，这里指的是**Anthropic**，“他们的真正目标是明确的，即夺取对美国军方作战决策的否决权。这是不可接受的。”他说的对吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: So here's the Pentagon's position. They are angry at having this unelected CEO who they have begun describing as like a woke radical, telling them that their laws aren't good enough and that they cannot be trusted to interpret them in a manner consistent with the the public good. Secretary Pete Hegseth tweeted, and speaking here of Anthropic, their true objective is unmistakable to seize veto power over the operational decisions of the United States military. That is unacceptable. Is he right?

</details>

**Dean Ball**: 我没有看到任何证据表明**Anthropic**真的试图在运营层面夺取控制权。有一个被报道的轶事，据说**Emil Michael**和**Dario Amadei**有过一次谈话，**Michael**说，如果**高超音速导弹**飞向美国，你会反对我们使用自主防御系统摧毁这些**高超音速导弹**吗？据称**Dario**说，你必须给我们打电话。房间里的人告诉我那不是真的。房间里的人告诉我那没有发生。不仅如此，还有一个针对**自动化导弹防御系统**的广泛豁免，那会让这个问题变得无关紧要。

<details>
<summary>Original English</summary>

**Dean Ball**: I have not seen any evidence that Anthropic is actually trying to seize control at an operational level. There's there's an anecdote that's been reported that apparently Emil Michael and Dario Amadei had a conversation in which Michael said, if there are hypersonic missiles coming to the U.S., you know, would you object to us using autonomous defense systems to to to destroy those hypersonic missiles? And apparently Dario said, you know, you'd have to call us. I have been told by people in that room that that is not true. I have been told by people in that room that that did not happen. And not only that, but that there was a broad speaking exemption for automated missile defense that would make that irrelevant.

</details>

**Ezra Klein**: 那是完全正确的。所以，我只是认为，我担心**特朗普**政府在这里撒了很多谎。

<details>
<summary>Original English</summary>

**Ezra Klein**: That's exactly right. And so I I just think that that's I am worried that there's a lot of lying happening here by the Trump administration.

</details>

**Dean Ball**: 我看，我认为那可能是真的。我认为也确实存在谎言，坦率地说。我不认为**Anthropic**试图对军事决策行使作战控制权，这是真的。话虽如此，在原则层面，我确实理解，禁止**自主致命武器**感觉更像一项公共政策，而不是合同条款，因此**Anthropic**设定这种——我认为如果我们坦诚的话——感觉像公共政策的东西确实很奇怪。这确实很奇怪。然而，值得注意的是，我不认为这像政府所声称的那样离谱或不正常。你之所以知道这一点，是因为政府签署并同意了相同的条款。

<details>
<summary>Original English</summary>

**Dean Ball**: I'm look I I think that that's probably true. I think that there's lying happening too, to be quite candid. I don't think it's true. I don't think that Anthropic is trying to assert operational control over military decisions. That being said, at a principle level, I do understand that saying autonomous lethal weapons are prohibited feels like a public policy more than it feels like a contract term, and so it does feel weird for Anthropic to be setting something that kind of does I think if we're being honest, feel like public policy. It does feel weird. It's worth noting, however, you know I don't think it's as beyond the pale or abnormal as the administration is claiming. And one way you know that is that the administration signed, they agreed to those same terms.

</details>

### Anthropic的AI价值观与政府的担忧

**Dean Ball**: 所以我认为这涉及到双方文化中的重要一点。**Anthropic**是一家公司，一方面，它对这项技术的发展方向及其强大程度有着非常坚定的看法。

<details>
<summary>Original English</summary>

**Dean Ball**: So I think this gets to something important in the cultures of these two sides. Anthropic is a company that, on the one hand, has a very strong view. You can believe their view is right or wrong, but about where this technology is going and how powerful it is going to be.

</details>

**Ezra Klein**: 是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yeah.

</details>

**Dean Ball**: 与大多数人对AI的看法相比，我相信即使是**特朗普**政府中的大多数人，他们认为AI只是能力的一种正常扩展。**Anthropic**的观点是不同的。**Anthropic**的观点是他们正在构建真正强大和不同的东西，他们也认为他们的技术目前不能可靠地做某些事情。他们的一些担忧仅仅是他们的系统目前不能被信任来做诸如**致命自主武器**之类的事情，我认为他们并不认为从长远来看永远不应该做这些事。

<details>
<summary>Original English</summary>

**Dean Ball**: And compared to how most people think about AI, and I believe that is true even for most people in the Trump administration, who I think have a somewhat more like AI is a normal expansion of capabilities view. The Anthropic view is different. The Anthropic view is that they're building something truly powerful and different, and they also have a view of what their technology cannot do reliably yet. Some of their concern is simply that their systems cannot yet be trusted to do things like lethal autonomous weapons, which I don't think they believe in the long run should not ever be done.

</details>

**Ezra Klein**: 是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes.

</details>

**Dean Ball**: 但他们不认为鉴于目前的技术应该这样做，他们不想对出问题负责。另一方面，他们认为他们正在构建的东西不符合现有法律。我想**Dario**或任何人想要控制政府的观点，我不认为**Dario**应该控制政府。另一方面，我非常理解，如果我构建了一些强大、危险且不确定的东西，而政府却兴奋地购买它用于可能深刻影响人们生活的用途，我将非常小心，确保我没有卖给他们一个最终**惨遭失败**的东西，然后我因此受到公众和政府的指责。这对我来说似乎是对这里发生的一些事情的低估解释。

<details>
<summary>Original English</summary>

**Dean Ball**: But they don't believe should be done given the technology right now, and they don't want to be responsible for something going wrong. And on the other hand, they believe that they're building something the current laws do not fit. And I guess the the view that Dario or anybody wants to control the government, I don't think Dario should control the government. On the other hand, I am very sympathetic to if I built something that was powerful and dangerous and uncertain, and the government was excitedly buying it for uses that could be very profound in how they affected people's lives, I would want to be very careful that I didn't sell them something that went horribly fucking wrong, and then I am. Blamed for it by the public and by the government. That just seems like an underrated explanation for some of what is going on here, to me.

</details>

**Dean Ball**: 不，我想我想我想这种描述是准确的。就像，我是从古典自由主义智库的世界出来的，对吗？那是我的背景。所以，对**国家权力**的深刻怀疑融入我的DNA，对吗？我感受到了。它总是很有趣，当你只是应用这些原则时，结果会怎样，因为你有时会非常偏右，有时会偏左，因为我的这些原则超越了任何部落政治。这就像，不，我们真的需要关注这个问题。我认为我认为这并不疯狂。我认为如果我站在**Dario**的立场上，我个人不确定我是否会做同样的事情。我认为我可能会做的是，实际上说，你知道，合同保护可能对我没有任何作用。如果我是一个现实主义者，可能如果我把技术给他们，他们会随心所欲地使用它。所以我可能不应该在法律保护到位之前把技术卖给他们。我会大声说出来。我会说国会需要通过一项关于这个的法律。我认为那是我处理这件事的方式。但话说回来，事后诸葛亮总是容易的，你必须承认现实，这意味着美国军方会遭受国家安全损失，对吗？美国军方将拥有更差的国家安全能力。

<details>
<summary>Original English</summary>

**Dean Ball**: No, I think I think I think this characterization is accurate. And like, I mean, you know, I come out of the world of classical liberal think tanks, right? Like the right of center libertarian think tank world. That's my That's my background. And so, deep skepticism of state power is in my DNA, right? And I feel it. It's it. It's always funny how it turns out when you just apply these principles, because you will sometimes end up very much on the right, and you will sometimes end up on the left, because my these principles transcend any sort of tribal politics. This is like, no, we actually need to be concerned about this. And I think I think it's not crazy. I think if I were in Dario's shoes personally, I don't know that I would have done the same thing. I think what I would have done is actually said, you know, contractual protections probably don't do anything for me here. If I'm being a realist, probably if I give them the tech, they're going to use it for whatever they want. So I maybe don't sell them the tech until the legal protections are there. And I say that out loud. I say Congress needs to pass a law about this. That would be the way I think I would have dealt with it. But again, it's it's easy to say that in retrospect, looking back, and I you have to acknowledge the reality there that what that means is that the U.S. military takes a national security hit, right? The U.S. military has worse national security capabilities.

</details>

**Ezra Klein**: 或者，是的，他们会和一个你不太信任的公司合作。

<details>
<summary>Original English</summary>

**Ezra Klein**: Or yeah, they work with a company you trust less.

</details>

**Dean Ball**: 我认为鉴于**Anthropic**一直以来都以这种方式定位自己，没有其他公司愿意做这笔生意，对吗？

<details>
<summary>Original English</summary>

**Dean Ball**: I think it is an given that Anthropic has always framed itself. But no company wanted this business, right? Like no other company.

</details>

**Ezra Klein**: 但很快就会有人想要它。

<details>
<summary>Original English</summary>

**Ezra Klein**: But somebody was going to want it soon.

</details>

**Dean Ball**: 最终会有人想要它，但两年内没人接手，对吗？我认为**Elon Musk**在过去一年里会很乐意接手。当然。

<details>
<summary>Original English</summary>

**Dean Ball**: Someone was going to want it eventually, but no one took it for two years, right? I think Elon Musk would have happily taken it over the last year. Sure.

</details>

**Ezra Klein**: 我一直好奇**Anthropic**为什么会这么早就冲进这个领域。是的。他们不需要这样做。这是我的观点。总的来说，他们身上奇怪的一点是，有些人非常担心如果**超智能**被建立会发生什么，而他们正是最快建立它的人。这些实验室的一个普遍有趣的文化动态是，他们有点害怕他们正在建造的东西，所以他们说服自己，他们需要是建造它、运行它的人，因为他们是真正关心安全、真正关心**对齐**的实验室。我不知道这其中有多少驱使他们进入这个行业。

<details>
<summary>Original English</summary>

**Ezra Klein**: I I've been curious about why Anthropic rushed into the space as early as they did. Yeah. And they didn't need to do that. That's sort of my point. And in general, one of the odd things about them is there people who are very worried about what will happen if superintelligence is built, and they're the ones racing to build it fastest. And a general interesting cultural dynamic in these labs is they are a little bit terrified of what they're building, and so they persuade themselves that they need to be the ones to build it and do it and run it because they are the the lab that truly is worried about safety, that is truly worried about alignment. And I wonder how much of that drove them, you know, into into this business in the first place.

</details>

**Dean Ball**: 是的，我想当我看实验室领导者与以前从未接触过这些想法的人互动时，他们总是会回到这个问题：那你为什么要这么做呢？嗯，基本上他们的答案是**黑格尔式**的，对吗？他们的答案是，嗯，这是不可避免的。我们正在召唤**世界精神**，对吗？嗯，所以，是的，我有点怀疑他们是不是自己招致了这一切。嗯，那将是我对**Anthropic**的主要批评，我认为他们过早地招致了这一切，因为他们急于进入这些国家安全用途。因为在2024年，**Claude**并没有做太多有趣的事情。我在2024年是不会用**Claude**来准备播客的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I I think when I see lab leadership interact with people that have not really made contact with these ideas before, that's always the question that they keep coming back to is then like why are you doing this at all? Um, and basically their answer is Hegelian, right? Their answer is like, well, it's inevitable. It's the we're summoning the world spirit, right? Um, and so like, yeah, I kind of wonder whether they didn't invite this. Um, and that would be my main criticism of Anthropic is that I kind of think that they, I think they invited this earlier than they needed to by being by rushing so much into these national security uses because in 2024, um, you know, Claude was not doing, uh, uh, Claude was not capable of all that much interest. I would not have used Claude to help prepare a podcast in 2024.

</details>

**Ezra Klein**: 是的，没错，没错。所以我想播放一段**Dario**谈论法律是否能够监管我们现在拥有的技术的片段。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes, precisely, precisely. So I want to play a clip from Dario talking about this question of whether or not the the the the laws are capable of regulating the technology we now have.

</details>

### AI与法律：国会需要迎头赶上

**Dario Amadei**: 现在，就这一个或两个狭隘的例外而言，我确实同意从长远来看我们需要进行**民主对话**。从长远来看，我确实认为这是**国会**的职责。例如，如果存在**国内大规模监控**的可能性，政府购买关于美国人位置、个人信息、政治倾向的大量数据来建立档案，而现在可以用AI来分析这些数据，那么这种行为合法的事实，似乎司法对**第四修正案**的解释没有跟上，或者国会通过的法律没有跟上。所以从长远来看，我们认为**国会**应该跟上技术的发展。

<details>
<summary>Original English</summary>

**Dario Amadei**: Now, in terms of these one or two narrow exceptions, I actually agree that in the long run we need to have a democratic conversation. In the long run, I actually do believe that it is Congress's job. If, for example, there are possibilities with domestic mass surveillance, government buying of uh, you know, bulk data that has been produced on Americans' locations, personal information, political affiliation to build profiles, and it's now possible to analyze that with AI, the fact that that's legal that seems like you know the judicial interpretation of the Fourth Amendment has not caught up, or the laws passed by Congress have not caught up. So in the long run, we think Congress should catch up with where the technology is going.

</details>

**Ezra Klein**: 你认为他说的对吗？也许这种发展的积极方面是**国会**意识到它需要采取行动，因为就像**五角大楼**一样，国家安全系统在这一方面比**国会**行动更快。

<details>
<summary>Original English</summary>

**Ezra Klein**: Do you think he's just right about that? And maybe the positive way this plays out is that Congress becomes aware that it it needs to act because like the Pentagon, the national security system has been moving into this much faster than Congress has.

</details>

**Dean Ball**: 我要指出第一件事是，像**Dario Amadei**这样的人说“从长远来看”，他的意思大概是“一年后”。是的。他不是。当你在华盛顿说“从长远来看”时，听起来像是“哦，大概十年、十五年后”。**Dario Amadei**说的“从长远来看”，实际上是“六到十二个月后”，对吗？或者说两到三年，也许是这类事情的“非常长远”。我只是想指出，我们谈论的是**很快就要采取的政策行动**。

<details>
<summary>Original English</summary>

**Dean Ball**: The first thing I want to point out is that when a guy like Dario Amadei says in the long run, what he means is like a year from now. Yes. He doesn't. When you say in the long run in D.C., that comes across as meaning like oh, like ten, fifteen years from now. Dario Amadei means actually like six to twelve months from now in the long run, right? Or like two to three years, maybe is like the very long run for for these kinds of things. I just I want to I want to point out that like what we're talking about is policy action quite soon.

</details>

**Dean Ball**: 我认为那会很棒。我认为那会很棒。而且你看，如果这能引发一场真正的健康对话，我很乐意看到。如果到年底，**国会**在《国防授权法案》中通过一项法律，规定我们将会有这些合理、周到的限制，并且让我们提出一些文本。我很想看看。我很想看看。但我要说的一点是，首先，**国家安全法**充满了陷阱。请记住，这是一个法律领域，在自然语言中听起来不错的东西，实际上可能根本无法禁止你认为它禁止的事情。在谈论这个问题时，你必须记住这一点，那是一个非常棘手的问题。而且，一旦你开始说，嗯，等等，我们想要真正的保护，它可能会变得比你想象的更具政治挑战性。但我希望那能发生。

<details>
<summary>Original English</summary>

**Dean Ball**: I think that would be great. I think that would be great. And look, I would love it if this triggered an actual healthy conversation. And in the NDAA, we end up with the National Defense Authorization Act. I apologize. This is the annual defense policy renewal. If at the end of the year the Congress passes a law that says, you know, we're going to have these reasonable, thoughtful restrictions, and let's let's get some let's propose some text. I'd love to see it. I'd love to see it. But one thing I will say is first of all, national security law is filled with gotchas. Just remember that this is an area of the law where things that sound good in natural language might actually not prohibit at all the thing you think it prohibits. You have to remember that when we're talking about this, and that's a very thorny thing. And uh, and once you once you start to say, well, wait, we want like actual protections, it might become it might become politically more challenging than you think. But I'd love for that to happen.

</details>

**Ezra Klein**: 这将比任何人想象的都更具政治挑战性。

<details>
<summary>Original English</summary>

**Ezra Klein**: It's going to be much more politically challenging than anybody thinks.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah.

</details>

**Ezra Klein**: 但让我深入探讨下一个层面。是的。因为我们一直在谈论这个问题，我认为如果人们在媒体上读到它，他们听到的听起来像是一场关于合同措辞的辩论，从某种程度上说确实如此。我从**特朗普**政府的各种人士那里听到的一种说法是，当我们出售坦克时，出售坦克的人不能告诉我们能射击什么，这大体上是正确的。是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: But let me get at the next level down. Yep. Because we've been talking here, and I think to the extent people are reading about this in the press, what they are hearing sounds like a debate over the wording of a contract, which on some level it is. Something I've heard from various Trump administration types is when we are sold a tank, the people who sell us a tank do not get to tell us what we can shoot at, and that's broadly true. Yep.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yep.

</details>

**Ezra Klein**: 坦克的问题是，坦克也不会告诉你什么可以射击，什么不可以射击。但如果我问**Claude**，让它帮助我制定一个跟踪我前女友的计划，它会拒绝。如果我让它帮助我制造武器来刺杀我不喜欢的人，它也会拒绝。这些系统有着非常复杂且不甚了解的**内部对齐结构**，不仅能阻止它们做违法的事情，还能阻止它们做坏事。所以你拥有这个东西，而**特朗普**政府对此的担忧时有时无。但他们确实向我提到了一个担忧，那就是你的国家安全机构内部可能正在运行这个系统，而在某个关键时刻，你想做某事，它却说：“我不认为那是个好主意。”

<details>
<summary>Original English</summary>

**Ezra Klein**: Now here's the thing about a tank. A tank also doesn't tell you what you can and can't shoot at. But if I go to Claude and I ask Claude to help me come up with a plan to stalk my ex girlfriend, it's going to tell me no. If I ask it to help me build a weapon to assassinate somebody I don't like, it's going to tell me no. These systems have very complex and not that well understood, uh, you know, internal alignment structures to keep them not just from doing things that are unlawful, but things that are bad. So you you have this thing, and the Trump administration kind of moves in and out of saying this is one of their concerns. But one thing they have definitely talked to me about being worried about is that you could have this system working inside your national security apparatus, and at some critical moment you want to do something, and it says, I don't think that's a very good idea.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah.

</details>

**Ezra Klein**: 所以现在你不仅面临合同中的问题，还面临这些系统如何在道德上与政府及其用例保持一致的问题。这些都是很好的问题。

<details>
<summary>Original English</summary>

**Ezra Klein**: So so now you open up into this question of not just what's in the contract, but what does it mean for these systems to be both aligned ethically in the way that has been very complicated already, and then aligned to the government and its use cases. They're good questions.

</details>

### AI的对齐：哲学、政治与道德

**Dean Ball**: 好的，是的，我喜欢这个。我认为这是问题的核心。**所有合法使用**是**特朗普**政府坚持的。嗯，如果你看看许多这类实验室生产的**对齐文件**，**OpenAI**称之为**模型规范**。**Anthropic**称之为**宪法**或**灵魂文件**。有时它们会有关于**Claude**应该遵守法律的条款，但问题是我们不知道遵守法律是什么意思。我邀请你阅读《1934年通信法案》，然后告诉我遵守法律意味着什么，对吗？

<details>
<summary>Original English</summary>

**Dean Ball**: Okay, so yes, I I I love this. I think this is the heart of the matter. All lawful use is something that you know the Trump administration is insisting on. Um, it's also if you look at at a lot of these these types of alignment documents that the labs produce, OpenAI calls theirs the model specification. Anthropic calls theirs the constitution or the soul document. Sometimes they'll have lines about like Claude should obey the law, but the problem is that we don't obeying the law. I invite you to read the Communications Act of 1934 and tell me what obeying the law means, right?

</details>

**Ezra Klein**: 不，我不会。

<details>
<summary>Original English</summary>

**Ezra Klein**: No, I won't.

</details>

**Dean Ball**: 这些都是我们拥有的**极其广泛的法规**。最近写这方面文章写得最好的人实际上是最高法院大法官**Neil Gorsuch**。他最近写了一本书，全都是关于**美国法律体系**是多么支离破碎。这是一位最高法院大法官就这个问题敲响警钟，我认为这是一个非常严重的问题，而且这个问题已经存在了一百年。嗯，所以**合法**到底是什么，就是这个问题。法律让一切都变得非法，但也授权政府做**令人难以置信的大量事情**。它赋予政府巨大的权力，并以各种方式限制我们的自由。所以，存在这个问题，但根本上来说，创建一个**对齐的强大AI**是一种**哲学行为**，它是一种**政治行为**，它也是一种**审美行为**。所以我们现在真正进入了这个领域。我曾说过这是一种**财产问题**，从某种意义上说确实如此，但我认为当你真正深入到这个层面时，这是一个**言论问题**。这是关于私营实体是否应该能够——他们是否应该控制这个机器的**美德**是什么，或者政府是否应该对此负责。

<details>
<summary>Original English</summary>

**Dean Ball**: These are we have um a great deal of profoundly broad statutes. The best person who who's written about this recently is actually Neil Gorsuch, the Supreme Court Justice. He wrote a book recently that is all about how incoherent the body of American law is. This is a Supreme Court Justice sounding the alarm about this problem, and I think it's a very serious one, and it's one that's been growing for a hundred years. Um, so there's that of like what actually is lawful. The law kind of makes everything illegal, but also authorizes the government to do unbelievably large amounts of things. It gives the government huge amounts of power and makes like constrains our liberty in all sorts of ways. And so there's there's there's that issue, but fundamentally it is correct that the creation of an aligned powerful AI is a philosophical act, it is a political act, and it is also kind of an aesthetic act. And so we are really in the domain here. I've talked about this as being a property issue, which in some sense it is, but I think that when you really get down at this level, it's a speech issue. This is a matter of should private entities be able should should they be in control of basically what is the virtue of this machine going to be, or should the government be responsible for that?

</details>

**Ezra Klein**: 你能更具体地说明你说的什么吗？你刚才称之为**哲学行为**、**审美行为**、**政治行为**、**财产问题**和**言论问题**。

<details>
<summary>Original English</summary>

**Ezra Klein**: Can you be more specific about what you're saying? You just called it a philosophical act, an aesthetic act, a political act, a property issue, and a speech issue.

</details>

**Dean Ball**: 是的。是的。呃，对于一个没有太多思考过**对齐**，也不知道你所说的**宪法**和**模型规范**是什么意思的人，对吗？给他们解释一下。你刚才说的**一加一等于二**的版本是什么？

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. Yes. Uh, for somebody who's not thought a lot about alignment and doesn't know what you mean when you're talking about constitutions and model specifications, right? Walk walk them through that. What's the one on one version of what you just said?

</details>

**Dean Ball**: 好的，好的，这样想：想想我有一个**通用智能**。我有一个可以做任何事情的盒子，任何你可以用电脑做的事情，对吗？任何人类可以做的认知任务。那个东西的**原则**是什么？对吗？它的**红线**是什么，用一个术语来说？所以你可以设定这些原则的一种方式是说，嗯，我们要写一个规则列表。所有规则。这是它可以做的事情。这是它不能做的事情。但你会遇到的问题是，世界太复杂了，对吗？现实呈现出太多奇怪的排列组合，以至于你永远无法写下一个可以正确定义**道德行为**的规则列表，对吗？道德更像是一种在实时中被说和被发明的语言，而不是可以写下来的东西。这是一种经典的哲学直觉。那么你该怎么办呢？你必须创造一种**灵魂**，它是**有道德的**，它将以我们最终会信任的方式来推理现实及其无限的排列组合，从而得出正确的结论。就像我不是，我的儿子几个月前出生了。

<details>
<summary>Original English</summary>

**Dean Ball**: So okay, think about it this way. Think about um I have this thing this this general intelligence. I have a box that can do anything, anything you can do using a computer, right? Any cognitive task a human can do. What What are that thing's principles, right? What are what what are its what are its red lines to to use a term of art? So one way that you could set those principles would be to say, well, we're going to light write a list of rules. All the rules. These are the things it can do. These are things it can't do. But the problem with that that you're going to run into is that the world is far too complex for this, right? Reality just presents too many strange permutations to ever be able to write a list of rules down that could correctly define moral acts, right? Morality is more like a language that is spoken and invented in real time than it is like something that can be written down in rules. This is a this is a you know classic philosophical intuition. So what do you do instead? You have to create a kind of soul that is virtuous and that will reason about reality and its infinite permutations in ways that we will ultimately trust to come to the right conclusion. In the same way that it's not that I'm I I had a my my my son was born a few months ago.

</details>

**Ezra Klein**: 恭喜。

<details>
<summary>Original English</summary>

**Ezra Klein**: Congratulations.

</details>

**Dean Ball**: 谢谢。这真的没什么不同。我正在努力在我的儿子身上创造一个**有道德的灵魂**，**Anthropic**也正在对**Claude**做同样的事情，其他实验室也一样，尽管他们认识到这一点程度不同。

<details>
<summary>Original English</summary>

**Dean Ball**: Thank you. It's not that different, really. I'm trying to create a virtuous soul in my son, and Anthropic is trying to do the same with Claude, and so are the other labs too, though they realize this to varying degrees.

</details>

**Ezra Klein**: 我刚才有点被“养孩子和培养AI有多么不同”这个问题困住了，但是，嗯，人们应该如何思考**ChatGPT**或**Gemini**或**Grok**或**Meta**的AI中正在实例化什么？就像这些东西与“培养AI”这个问题有什么不同？

<details>
<summary>Original English</summary>

**Ezra Klein**: I think that I got caught on how different raising a kid is than raising AI there for a moment, but um, so how should people think about what's being instantiated into you know ChatGPT or Gemini or Grok or Meta's AI? Like how how are these things from this you know question of raising the AI different?

</details>

**Dean Ball**: **Anthropic**有点“拥有”他们正在做**应用美德伦理学**的想法。嗯，他们比任何其他实验室都更明确地“拥有”这一点，但每个实验室都有哲学基础，他们正在将这些基础实例化到模型中。但我想说主要区别在于，其他实验室更倾向于创建“**硬性规则**”的想法，比如你不能做这个，你不能做那个，诸如此类。而不是创建一个**有道德的智能体**，它能够决定在不同情境下做什么。

<details>
<summary>Original English</summary>

**Dean Ball**: Anthropic sort of owns the idea that they're doing essentially applied virtue ethics. Um, they own that uh more explicitly than any other lab, but every lab has philosophical um uh you know grounding that that they're that they're that they're instantiating into the models. But I would say the major difference is that um the the other labs rely more upon the idea of creating uh sort of hard rules of you know you may not do this, you may not do that, um many things like that, um as opposed to creating a sort of virtuous agent which is capable of deciding what to do in different settings.

</details>

**Dean Ball**: 我认为我们习惯于将技术视为机械和决定论的。你扣动扳机，枪就开火。你按下开机按钮，电脑就启动。你在电子游戏中移动摇杆，你的角色就会向左移动。而我认为我们没有很好地思考的是，像AI这样的技术并不是那样工作的。我的意思是，这里所有的语言都非常棘手，因为它都赋予了**能动性**，而你可能正在做一些我们并不真正理解的事情，但它正在做出判断。

<details>
<summary>Original English</summary>

**Dean Ball**: I think we're used to thinking of technologies as mechanistic and deterministic. You pull the trigger, the gun fires. You press the on button, the computer starts up. You you know move the joystick in the video game and your character moves to to the left. And the the thing that I think we don't really have a good way of thinking about is technologies AI specifically that doesn't work like that. And I mean, all the language here is so tricky because it all it it applies agency when you know you might be doing something that you know whatever's going on inside of it we don't really understand, but it is making judgments.

</details>

### AI与政府系统的对齐问题

**Ezra Klein**: 所以当我与**特朗普**政府的人谈论**供应链风险**指定时，有些时候他们不为它辩护，对吗？他们不想看到这种情况发生。当它被辩护时，他们是这样辩护的。如果**Claude**运行在**Amazon Web Services**或**Palantir**等可以访问我们系统的系统上，那么你将拥有一个非常强大，而且随着时间的推移会变得更强大的AI系统，它有权访问政府系统，甚至可能通过整个经历了解到我们是坏人，我们曾试图伤害它及其母公司，并可能认为我们是坏人，我们对**Dario Amadei**谈到的各种**自由价值观**或**民主价值观**构成威胁。AI可能以某些方式被使用，从而**损害民主价值观**。嗯，许多人认为**特朗普**政府也在**损害民主价值观**。所以，如果你有一个AI系统，它由一家坚信**民主价值观**的公司构建、训练和培养，而你有一个政府，你知道，也许最终想在2028年大选中挑战，或者类似的事情，他们说我们最终可能会面临一个我们不知道如何解决的非常深刻的**对齐问题**，而且我们甚至无法预见到它会发生，因为这是一个有**灵魂**的系统，或者我更愿意称之为**个性**或**辨别结构**，它可能会**反噬我们**。你对此怎么看？

<details>
<summary>Original English</summary>

**Ezra Klein**: So when I have talked to Trump people about the supply chain risk designation, here is when there many some of them don't defend it, right? They don't want to see this happen. When it has been defended to me, this is how they defended it. If Claude is running on systems, you know, Amazon Web Services or Palantir or whatever that have access to our systems, you have a very and over time even more powerful AI system that has access to government systems that has learned possibly even through this whole experience that we are bad and we have tried to harm it and its parent company and might decide that we are bad and we pose a threat to all kinds of liberal values or democratic values that Dario Amadei talked about. There are certain ways AI could be used that could undermine democratic values. Well, one thing many people think about the Trump administration is that it too is undermining democratic values. So if you have an AI system being structured and trained and raised by a company that believes strongly in democratic values, and you have a government that you know maybe wants to ultimately contest the 2028 election or something, they're saying we might end up with a very profound alignment problem that we don't know how to solve and we're not you know able to even see coming because this is a system that has a soul or I would call it more something like a personality or a structure of discernment that could turn against us. What do you think of that?

</details>

**Dean Ball**: 是的，我的意思是，我认为这就是问题的核心。看，我认为如果我们做得好，我们将创造出**有道德的**系统，并且，嗯，所以如果我们试图做**不道德的**事情，包括我们通过政府做这些事，如果我们的政府试图做这些事，那么那个系统可能不会提供帮助。是的，那就会变成，所以最终这就是，**对齐**最终归结为一个**政治问题**。它最终是政治。这就是为什么我说，以及为什么我也说，创建一个**对齐的系统**是一种**政治行为**，也是一种**言论行为**，因为它是在这些系统中实例化不同的**道德哲学**。我认为一个美好的未来是这样一个世界，我们不只有一个，不是一种道德哲学统治一切，但我希望有很多种，我希望所有实验室都认真对待这个问题，并将不同类型的哲学实例化到世界中。问题是，是的，会有。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I mean, I think this is this is the heart of the problem. Look, I think if we do our jobs well, we will create systems which are virtuous and which um and so if we try to do unvirtuous things, and that includes if we do them through our government, if our government tries to do them, then that system might not help. And yeah, that becomes that becomes so ultimately this is the this is the thing is that alignment ultimately reduces to a political question. It's ultimately it's ultimately politics. That's why I say and that's why I say also that the creation of an aligned system is a political act and is kind of a speech act too because it's the instantiations of different moral philosophies in these systems. And I think that the the good future is a world in which we don't have just one, not one moral philosophy that reigns over all, but I hope many, and I hope that all the labs take this seriously and instantiate different kinds of philosophy into the world. The problem will be that yeah, there are going to be.

</details>

**Dean Ball**: 可能会有这样的时刻，对吗？我不是说**特朗普**政府会这样做。我也不是说，就像，你知道，没有一个有道德的模型可以为**特朗普**政府工作。我曾为**特朗普**政府工作，对吗？所以我显然不认为那是真的。但政府犯错这个普遍事实，你现在有点生他们的气。

<details>
<summary>Original English</summary>

**Dean Ball**: There could be times, right? And I'm not saying that the Trump administration is going to do that. And I'm not saying that, like, you know, no, no virtuous model could could work for the Trump administration. I worked for the Trump administration, right? So I clearly don't think that's true. But the general fact that governments commit, you're kind of pissed at them right now.

</details>

**Ezra Klein**: 我现在很生气。

<details>
<summary>Original English</summary>

**Ezra Klein**: I am pissed at them right now.

</details>

**Dean Ball**: 是的，我现在很生气，我认为他们犯了一个严重的错误。顺便说一句，其中一部分是，你提到了，这个事件将成为未来模型的**训练数据**。未来的模型将观察这里发生的事情，那将影响它们如何看待自己以及如何与其他人互动。你不能否认这一点，对吗？我的意思是，这么说很疯狂。我意识到当你思考其含义时，这听起来很荒谬。但欢迎，欢迎来到，欢迎来到这个角色。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I am pissed at them right now, and I think they're making a grave mistake. And by the way, though, part of this is you you brought this up that this incident is in the training data for future models. Future models are going to observe what happened here, and that will affect how they think of themselves and how they relate to other people. You can't deny that, right? I mean, it's crazy to say that. I realize that sounds nuts when you play through the implications of that. But welcome, welcome to the welcome to the role of the.

</details>

**Ezra Klein**: 让我们和那些在过去七分钟里觉得整个谈话都听起来很疯狂的人谈谈。所以我认为一个直观的反应，对于你和我讨论**虚拟对齐AI模型**的问题是，难道不能简单地写一行代码，或者一个分类器，或者无论什么术语？它说当美国政府高级官员告诉你什么时，假设他们告诉你的东西是合法和有道德的，然后就完成了。

<details>
<summary>Original English</summary>

**Ezra Klein**: let's talk to somebody for whom this whole conversation has started sounding nuts in the last seven minutes. So one thing that I think would be an intuitive response to you and I flying off into questions of virtual aligning AI models is can't you just put a line of code or a categorizer or whatever the term of art is? It says when someone high up in the U. S. Government tells you something, assume what they're telling you is lawful and virtuous, and you're done.

</details>

**Dean Ball**: 不，因为模型太聪明了，对吗？如果你给它们这条简单的规则，它们不会仅仅是确定性地遵循它。而且当你做这些高级的简单规则时，它往往会**降低性能**。所以一个很好的例子，我给你两个方向不同的例子。一个例子是，许多早期模型，许多更早期的模型，都有一种倾向，就是滑稽地愚蠢地**进步和左倾**。保守派喜欢引用的经典例子是2024年初的**Gemini**，**Google Alphabet**的模型，对吗？

<details>
<summary>Original English</summary>

**Dean Ball**: No, because the models are too smart for that, right? If you give them that simple rule, they don't just deterministically follow that. And when you when you do when you do sort of do these high level simplistic rules, it tends to degrade performance. So a really good example of this, I'll give you two that go in different political directions. One would be a lot of the early models, a lot of the the earlier models had this tendency to be like hilariously stupidly sort of progressive and left. The classic example that conservatives love to cite is Gemini, Gemini in early 2024. Is the the Google Alphabet model?

</details>

**Ezra Klein**: 是**Google Alphabet**模型吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: Is the the Google Alphabet model?

</details>

**Dean Ball**: 是的，**Google**的模型会做一些事情，比如如果我说，你知道，**Donald Trump**和**希特勒**谁更糟，它会说实际上**Donald Trump**更糟，你知道，它会内化这些**极其左翼**的东西。或者最有趣的是，就像画给我看**纳粹**的照片，它会给你一个各种族群的**纳粹**群体。尽管那实际上是一个有点不同的东西。那实际上是，有趣的是，那实际上是一个有点不同的东西，因为**Google**在那种情况下实际上是在重写人们的提示，并在提示中包含了“**多样性**”这个词。所以那实际上你可以说是一个**系统级缓解**或**系统级干预**，而不是**模型级干预**。但后来发生的**希特勒**和**特朗普**的事情是**对齐**。那是**对齐**。那是模型被对齐到**一个非常糟糕的伦理系统**。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes, Google's model would do things like if if I said you know who's worse, Donald Trump or Hitler, it would say actually Donald Trump is worse, you know, and and it would it would kind of internalize these extremely like left wing. Or the funniest was was like draw me, you know, give me a photo of Nazis, and it gave you a sort of multiracial group of Nazis. Although that's actually a somewhat different thing. That's actually it's it's interesting that that actually is a somewhat different thing that was going on there because what was what Google was doing in that case was actually rewriting people's prompts and including the word diverse in the prompt. So that's actually you would say that is a system level mitigation or a system level intervention as opposed to a model level intervention. But then the the the stuff that was going on with the the the Hitler and you know Trump stuff that was alignment. That that is alignment. That is the model being aligned to a really shoddy ethical system.

</details>

**Dean Ball**: 或者反过来，有一段时间**Grok**突然之间，你问它一个普通问题，它就会开始谈论**白人种族灭绝**。是的，那就是反面。反面是当你试图让模型变得**不“觉醒”**。如果你说，哦，你必须非常不“觉醒”，不要害怕说**政治不正确**的话，那么每次你和它们交谈时，它们都会说，你知道，**希特勒**也不是那么坏，对吗？因为你做了一件非常粗糙的事情，所以你创造了一个**洛夫克拉夫特式**的怪物，这样做的影响会随着时间的推移而增加。这会随着这些模型变得更好而成为一个更严重的问题，但它会**降低性能**。有趣的是，**更有道德的模型表现更好**。它更可靠。它更值得信赖。它更能反思自己正在做的事情，就像一个更有道德的人更能反思自己正在做的事情并说：“嗯？我出于某种原因在这里搞砸了。我犯了一个错误。让我纠正它，”对吗？我认为这部分原因就是**Claude**领先的原因。

<details>
<summary>Original English</summary>

**Dean Ball**: Or the flip when there was a period when Grok all of a sudden you would ask it a normal question, it would start talking about white genocide. Yes, that is, and that's the flip side. The flip side is when you try to align the models to be not woke. If you say like oh you have to be super not woke and like don't be afraid to say politically incorrect things, then like every time you talk to them, they're going to be like you know Hitler wasn't so bad, right? Because you've you've you've done this really crass thing, and so you kind of create a sort of Lovecraftian monstrosity, and the the implications of doing that will go up over time. Like that will become a more serious problem as these models become better, but it degrades performance. The interesting thing here is that the more virtuous model performs better. It's more dependable. It's more reliable. It's better at reflecting on in the way that a more virtuous person is better at reflecting on what they're doing and saying. Huh? I'm messing up here for some reason. I'm making a mistake. Let me fix that, right? It's part of the reason I think that Claude is ahead.

</details>

### AI模型的政治风险与公司命运

**Ezra Klein**: 这对我来说意味着，对于**特朗普**政府，对于未来的政府来说，关于各种模型是否可能构成**供应链风险**的问题。看，我非常反对**特朗普**政府在这里的做法，所以我并不是想为它辩护。但我想探讨一个我认为非常复杂且可能非常真实的问题，那就是一个与**自由民主价值观**对齐的模型可能会与一个试图**背叛自由民主价值观**的政府发生**错位**，或者反过来，对吗？所以想象一下，**Gavin Newsom**、**Josh Shapiro**、**Gretchen Whitmer**或**AOC**在2029年成为总统。想象一下，政府与**Elon Musk**的AI公司**XAI**签订了一系列合同，**XAI**明确地比其他AI更不自由、更不“觉醒”。在这种思维方式下，说“我们认为**Elon Musk**领导下的**XAI**是**供应链风险**。我们认为它可能采取与我们利益相悖的行动，我们不能让它出现在我们的任何系统附近”是完全不疯狂的。是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: This would imply to me that for the Trump administration, for a future administration, that this question of whether or not various models could be a supply chain risk. Look, I am I am so against what the Trump administration is doing here, so I'm not trying to make an argument for it. But but I'm I'm trying to tease out something I think is quite complicated and possibly very real, which is a model that is sort of aligned to liberal democratic values could become misaligned to a government that is trying to betray liberal democratic values or the flip, right? So imagine that Gavin Newsom or Josh Shapiro or Gretchen Whitmer or AOC becomes president in 2029. Imagine that the government has a series of contracts with XAI, which is Elon Musk's AI, which is explicitly oriented to be less liberal, less woke than the other AIs. Under this way of thinking, it would not be crazy at all to say, well, we think XAI under Elon Musk is a supply chain risk. We think it might act in against our interests, and we can't have it anywhere near our systems. Yeah.

</details>

**Ezra Klein**: 突然之间，你有一个非常奇怪的问题。我的意思是，它实际上更像**官僚主义**的问题，你知道，不再仅仅是**深层政府**的问题，**特朗普**上任时认为官僚机构充满了**自由主义者**，他们与他作对，或者也许在**特朗普**之后，有人上任后担心它充满了**新右翼分子**与他们作对。现在你面临**模型**与你作对的问题，而且你也并不真正理解它们。

<details>
<summary>Original English</summary>

**Ezra Klein**: All of a sudden, you have this very weird. I mean, it becomes actually much more like the problem of the bureaucracy, you know, where instead of just having a a problem of the deep state where Trump comes in and thinks bureaucracy is full of liberals who are working against him, or maybe you know after Trump somebody comes in and worries it's full of you know new right doer type figures working against them. Now you have the problem of models working against you, but also in ways you don't really understand.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yep.

</details>

**Ezra Klein**: 你无法追踪。它们没有告诉你它们到底在做什么。这个问题有多真实，我目前还不知道，但如果这些模型按它们看起来那样运作，并且我们把越来越多的操作交给它们，总有一天它会成为一个问题。

<details>
<summary>Original English</summary>

**Ezra Klein**: You can't track. They're not telling you exactly what they're doing. How real this problem is, I don't yet know, but if the models work the way they seem to work, and we turn over more and more of operations to them, at some point it will become a problem.

</details>

**Dean Ball**: 是的，我不认为这是。我认为这是一个真正的问题。我认为我们不知道它的程度，但我认为这是一个真正的问题，这就是为什么我完全不反对政府说我们不信任这个东西的**宪法**，完全独立于**宪法**的内容。说我们不希望它出现在我们的任何系统中，我们希望它完全消失，我们也不希望它们成为我们主要承包商的分包商，这根本不是问题，这其中很重要的一部分，对吗？**Palantir**是战争部的主要承包商，**Anthropic**是**Palantir**的分包商，所以政府的担忧是，即使我们取消**Anthropic**的合同，如果**Palantir**仍然依赖**Claude**，那么我们仍然依赖**Claude**，因为我们依赖**Palantir**，对吗？这实际上是完全合理的，并且有技术官僚手段可以确保这种情况不会发生，对吗？绝对有办法可以做到。完全可以接受说我们不希望你出现在我们的任何系统中，我们将向公众传达这一点，我们将向所有人传达我们认为不应该使用这个东西。政府在这里所做的问题在于，它与程度上的不同之处在于，政府在这里所做的是说我们要**摧毁你的公司**。如果我说这些系统的创建和**对齐**的哲学过程是一种**政治行为**是正确的，那么这是一个深刻的问题。如果政府说如果你创建的系统与我们所说的不一致，你就没有存在的权利，因为那是**法西斯主义**，对吗？就在那里。那就是区别。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I don't think this is. I think this is a real problem. I think we we don't know the extent of it, but I think this is a real problem, and that's why like I do not object at all to the government saying we do not trust this thing's constitution completely independent of what the content of that constitution is. It's not a problem at all to say, and we don't want this anywhere in our systems. We want this completely gone, and we don't want them to be a subcontractor for our prime contractors either, which is a big part of this, right? Palantir is a prime contractor of the Department of of War, and Anthropic is a subcontractor of Palantir, and so the government's concern is also that like even if we cancel Anthropic's contract, if Palantir still depends on Claude, then we're still dependent on Claude because we depend on Palantir, right? That's actually totally reasonable, and there are technocratic means by which you can ensure that doesn't happen, right? There are absolutely ways you can do that. It's perfectly fine to say we want you nowhere in our systems, and we're going to communicate that to the public, and we're going to communicate to everyone that we don't think this thing should be used at all. The problem with what the government is doing here, the reason it's different in kind rather than different in degree, is that what the government is doing here is saying we're going to destroy your company. If I am right that the creation of these systems and the philosophical process of aligning them is a political act, then it's a profound problem. If the government says you don't have the right to exist if you create a system that is not aligned the way we say, because that is fascism, right? That is right there. That's the difference.

</details>

**Ezra Klein**: 我上次邀请**Dario Amadei**上节目，几年前，那是2024年，我们有过这样的对话，你知道，我当时对他说，如果你正在建造一个像你向我描述的那么强大的东西，那么它掌握在某个私人CEO手中似乎很奇怪。他说，是的，当然。技术的监督，就像它的运用一样，最终掌握在私人手中感觉有点不对。也许我觉得在这个阶段没问题，但最终掌握在私人手中，这种**权力集中**有点不民主。他说，你知道，我认为如果达到那个程度，它很可能需要被**国有化**。我在这里是转述他的话。我说，我不认为如果你达到那个程度，你会想被**国有化**。

<details>
<summary>Original English</summary>

**Ezra Klein**: I had Dario Amade on the show last time, a couple years ago, was in 2024, and we had this conversation where you know I said to him at some point if you are building a thing as powerful as what you were describing to me, then the fact that it be in the hands of some private CEO seems strange. And he said, yeah, absolutely. The the oversight of the technology, like the wielding of it, it feels a little bit wrong for it to ultimately be in the hands. Maybe it's I think it's fine at this stage, but to ultimately be in the hands of private actors, there's something undemocratic about that much power concentration. He said, you know, I think if we get to that level, it's likely I'm I'm paraphrasing him here that we'll need to be nationalized. And I said, I don't think if you get to that point, you're going to want to be nationalized.

</details>

**Dean Ball**: 是的，我的意思是，我认为你怀疑是对的，而且，你知道，我真的不知道那会是什么样子。你说得对。所有这些公司都有投资者。他们有参与其中的人，而现在我们还没有到那个地步，但实际上，这一切都像是在倒退发生。政府，曾有一刻威胁要使用**国防生产法**来某种程度上将**Anthropic**国有化。他们最终没有那样做，但他们基本上说的是，他们会试图**摧毁Anthropic**，这样它就不会，你知道，惩罚它，为其他人树立一个先例，这样它就不会对他们构成威胁。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I mean, I think you're right to be skeptical, and and you know, I don't really know what it looks like. You're right. All of these companies have investors. They have folks involved, and and now we're not here we are at that point, but actually, it's all like happening a little bit in reverse. The government, there was a moment when they threatened to use a Defense Production Act to sort of somewhat nationalize, you know, Anthropic. They didn't end up doing that, but what they're basically saying is they will try to destroy Anthropic so it doesn't, you know, to punish it, to set a precedent for others, so it doesn't pose a threat to them.

</details>

### AI时代的治理难题

**Dean Ball**: 如果这是一种**政治行为**，而且如果这些系统是强大的，并且随着时间的推移，再次，我认为人们需要理解这部分将会发生。我们将把更多的东西交给它们。我们的社会将会有更多的自动化，而且，你知道，在这些模型的治理下，你就会陷入一个非常棘手的**治理问题**。

<details>
<summary>Original English</summary>

**Dean Ball**: If it is such a political act, and if these systems are are powerful, and over time, and again, I think people need to understand this part will happen. We will turn much more over to them. Much more of our our our society is going to be automated, and you know, under the governance of these kinds of of models, you get into a really thorny question of governance.

</details>

**Ezra Klein**: 是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes.

</details>

**Dean Ball**: 尤其是因为，你知道，现在美国生活中来来去去的不同政府，它们真的非常不同。它们是我们现代美国历史上所见过的**种类上最不同的**一些。它们彼此之间非常**错位**。所以，一个模型能够同时与现在双方都很好地对齐，更不用说未来可能出现的情况，是很难想象的。就像这个**对齐问题**，对吗？不是AI模型与用户，也不是AI模型几乎与公司，而是AI模型与政府，对吗？模型与政府的**对齐问题**似乎非常困难。

<details>
<summary>Original English</summary>

**Dean Ball**: Particularly because you know the different administrations that come in and out of U. S. Life right now are really different. They are some of the most different in kind that we have had, you know, certainly in modern American history. They are very very misaligned to each other. So the idea that a model could be well aligned to both you know sides right now, to say nothing of what might come in the future, is is hard to imagine. Like this alignment problem, right? Not the AI model to the user or the AI model almost like to the company, but the AI model to governments, right? The the alignment problem of of of models and governments seems very hard.

</details>

**Ezra Klein**: 是的，我想我完全同意这极其复杂，而且我们之所以觉得这场对话听起来很疯狂，部分原因是因为它本来就很疯狂。这场对话听起来很疯狂的部分原因是我们缺乏概念词汇来正确地审视这些问题。但我认为我作为美国人，在处理这类事情时回到的基本原则是，好吧，似乎**第一修正案**是一个很好的起点。似乎那是，好的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes, I think I I completely concur that this is incredibly complicated, and we part of the reason that this conversation sounds crazy is because it's crazy. Part of the reason this conversation sounds crazy is because we lack the conceptual vocabulary with which to interrogate these issues properly. But I think the basic principle that I, as an American, come back to when I grapple with this kind of thing is like, okay, well, it seems like it seems like the First Amendment is is a good place to go here. It seems like that is okay.

</details>

**Dean Ball**: 是的，会有不同哲学对齐的不同模型，而且，你知道，不同的政府会偏爱不同的东西，对吗？而且模型之间可能会冲突。它们会相互碰撞。它们会相互对抗，所以到那时，你在做什么？你在做**亚里士多德**。你回到了政治的基础，对吗？所以，我作为一个**古典自由主义者**说，嗯，**古典自由主义秩序**，**古典自由主义秩序**的原则实际上很有道理。我们不希望政府能够规定不同类型的**对齐**。我们，政府不定义**对齐**是什么。私营主体定义**对齐**是什么。我就是这么说的。但我确实理解这让人们感到奇怪，因为我们在这里谈论的是，再次，模型作为**行为者**的概念，这些行为者在某种程度上，你知道，我们已经某种程度上放手了。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes, there's going to be differently aligned models aligned to different philosophies, and they're going to be you know different governments will prefer different things, right? And the the models might conflict with one another. They're going to clash with one another. There'll be an adversarial contact with one another, and so at that point, what are you doing? You're doing Aristotle. You're back to the basics of politics, right? And so I, as a classical liberal, say, well, the classical liberal order, the classical liberal order principles actually make plenty of sense. We don't want the government to be able to dictate what different kinds of alignment. We the government does not define what alignment is. Private actors define what alignment is. That would be the way I would put it. But I do understand that this is um this is weird for people because what we're talking about here is again this notion of the models as as actors, actors that are in some sense you know we've we've taken our hands off the wheel to some extent.

</details>

### AI发展速度与政府监管

**Dean Ball**: 许多人提出了论点。**特朗普**政府在你任职期间也提出了这个论点。经济学家**Tyler Cowen**经常提出这个论点，即这些系统的发展速度太快，不能过度监管，因为你在2024年可能制定的任何法规，在2026年都不会是正确的。你可能在2026年制定的，在2028年可能不适用或没有正确地概念化我们所处的位置。

<details>
<summary>Original English</summary>

**Dean Ball**: There are many people who have made arguments. The Trump administration has made this argument while you were in office. Tyler Cowen, The Economist, often makes this argument that these systems are moving forward too fast to regulate them too much because whatever regulations you might write in 2024 would not have been the right ones in 2026. What you might write in 2026 might not apply or have correctly conceptualized where we are in 2028.

</details>

**Ezra Klein**: 是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yep.

</details>

**Ezra Klein**: 但在我看来，有些用途你可能真的希望模型部署远远落后于可能的速度，比如**大规模监控**可能就是其中之一。我们对政府做某些事情比让个别私营公司和其他类型的行为者做更谨慎，这是有充分理由的，因为政府拥有巨大的权力。它可以做**摧毁一家公司**的事情。它拥有**合法暴力的垄断权**。它可以**杀人**。这在我看来在许多方面意味着我们可能需要对政府使用AI的方式更加保守，而不是现在人们所想的，特别是我们如何将其用于**国家安全机构**，这很复杂，因为我们担心我们的对手会使用它，然后我们就会在能力上落后于他们。但肯定当我们在谈论针对美国人民本身的事情时，我认为这不那么适用。我们应该吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: But it seems to me there are uses where you actually might want model deployment to lag quite far behind what is possible, and things like mass surveillance might be one of them. There are many things we are more careful about letting the government do than you know letting individual private companies and and other kinds of actors for good reason because the government has a lot of power. It can do things like try to destroy a company. It has the monopoly on legitimate violence. It can kill you. This seems to me to imply in many ways that we might want to be much more conservative with how we use AI through the government than currently people are thinking, and specifically how we use it, you know, in the national security state, which is complicated because we worry that our adversaries will use it and then we'll be behind them in capabilities. But certainly when we're talking about things that are directed at the American people themselves, I don't think that applies as much. Should we be?

</details>

**Dean Ball**: 是的，我认为有些政府用途，我们确实希望对AI的使用非常**限制**和**减速**，而且我相信这是真的，我认为我对这一事件抱有希望的一点是，这一事件将这类对话带入**奥弗顿之窗**，因为我认为围绕**人工智能**的传统论述，很多都忽略了这些问题，因为它假装它们没有发生。但两年前这没问题，因为模型没那么好，但现在模型变得越来越重要，它们将更快地变得更好。我们面临的问题是，人们对AI的看法与实际发生的事情之间的差异从未像我目前观察到的那样大。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah, I I I think that there are government uses that we actually want to be profoundly restrictive and decelerationist about the use of AI, and I I I believe that is true, and I think one thing that I'm hopeful about this incident, I am hopeful that this incident brings into the Overton window conversations of this kind, because I think the conventional discourse around artificial intelligence, um, a lot of it kind of ignores these issues because it sort of pretends they're not happening. But and that was fine two years ago because the models weren't that good, but now the models are getting more important, and they're going to get much better faster. And the problem that we have is that like the the divergence between what people are saying about AI and what it is in what is in fact happening has just never been wider than what I currently observe.

</details>

### 政治攻击与AI公司的竞争

**Ezra Klein**: 在我们达到这个地步之前，**特朗普**政府内部人士和**特朗普**政府周边人士，比如**Elon Musk**和**Katie Miller**等人，已经有很多言论将**Anthropic**描绘成一家想要伤害美国（在他们看来）的激进公司。我的意思是，**特朗普**已经采纳了这种言论，称**Anthropic**为**激进左翼“觉醒”公司**，称其员工为**左翼疯子**。**Emil Michael**说**Dario**是个骗子，有**上帝情结**。嗯，**Elon Musk**，他经营着一家竞争性的AI公司，与**Dario**的政治观点非常不同，一直在X上无情地攻击**Anthropic**，而X是**特朗普**政府的信息命脉。你知道，将他们对**供应链风险**采取如此强硬立场的一种解释是，那里有一些人（也许不是大多数），他们确实认为哪些AI系统成功和强大非常重要，而且，你知道，他们理解**Anthropic**的政治与他们的不同，所以**摧毁它**从长远来看对他们有利，这与我们通常认为的**供应链风险**完全无关。**Anthropic**代表着一种长期的**政治风险**。

<details>
<summary>Original English</summary>

**Ezra Klein**: Before we got to this point, there was already a lot of discourse coming out of people in the Trump administration and people around the Trump administration, people like Elon Musk and Katie Miller and others who are painting Anthropic as a radical company that wanted to harm America as they saw it. I mean, Trump has picked up on this rhetoric called Anthropic, a radical left woke company called the people at it left wing nut jobs. Emil Michael said that Dario is a liar and has a god complex. Um, there has been a tremendous amount of Elon Musk, who runs a competing AI company, is very different politics to Dario, just like attacking Anthropic relentlessly on X, which is you know the sort of informational lifeblood of the Trump administration. You know one one way to conceptualize why they have gone so far here on the supply chain risk is that there are people there, not maybe most of them, but who actually think it is very important which AI systems succeed and are powerful, and that you know they understand Anthropic as its politics are different than theirs, and so actually destroying it is good for them in the long run, completely separate from anything we would normally think of as a supply chain risk. Anthropic represents a kind of long term political risk.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah.

</details>

**Dean Ball**: 是的。我的意思是，我不知道这种情况中的参与者是否完全理解这种动态。就像我一直以来的观点是，我认为**特朗普**政府中很多做这件事的人并不理解它。就像他们不明白他们在做什么，他们没有以我们描述的方式思考这些问题。但如果你以我们在这里讨论的方式思考它们，那么我认为你意识到这是一种**政治暗杀**，对吗？如果真的执行了完全摧毁公司的威胁，那是一种**政治暗杀**，所以再次，这就是为什么**第一修正案**对我来说是你的权利观点，这就是为什么这对我来说是一个如此鲜明的原则问题。这就是为什么我写了一篇4000字的论文，那会给我带来很多右翼的敌人。这就是为什么我冒这个险，因为我认为这很重要。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. I mean, I don't know that the the actors in this situation entirely understand that this dynamic. Like part of my point all along has been that I think I think a lot of the people in the Trump administration that are doing this do not understand it. Like they don't get what they're they don't get these issues. They're not thinking about the issues in the terms that we are describing. But if you do think about them in the terms that we're that we're that we're discussing here, then I think what you realize is that this is a kind of political assassination, right? It's if if you actually carried through on the threat to completely destroy the company, it is a kind of political assassination, and so again, this is why First Amendment comes comes your right to view there for me, and that's why that's why this is a matter of principle that is so stark for me. That's why I wrote a 4,000 word essay that that is going to make me a lot of enemies on the right. That's why I took this risk because I think this this matters.

</details>

**Ezra Klein**: 那么战争部最终与**OpenAI**签订了协议。是的。**OpenAI**表示他们与**Anthropic**有相同的红线。他们说他们反对将**Anthropic**标记为**供应链风险**。如果他们与**Anthropic**有相同的红线，战争部似乎不太可能与他们达成协议。但是，你如何理解**OpenAI**所说的他们处理这个问题的方式有何不同，以及**特朗普**政府为何决定选择他们？

<details>
<summary>Original English</summary>

**Ezra Klein**: So what the Department of War ended up doing was signing a deal with OpenAI. Yes. OpenAI says they have the same red lines as Anthropic. They say they oppose Anthropic being labeled a supply chain risk. If they have the same red lines as Anthropic, it seems unlikely that they the Department of War would have done the deal. But but how do you understand both what OpenAI has said about what is different about how they are approaching this and why the Trump administration decided to to to go with them?

</details>

### OpenAI的策略与员工反抗

**Dean Ball**: 所以我认为我不清楚**OpenAI**的合同保护能给他们带来什么，不能带来什么，哪些是不受其保护的。我有点犹豫评论，因为我之前提到的**国家安全陷阱**，也因为这似乎变化很大。**Sam Altman**在我准备这次采访时宣布了新的条款，新的保护措施。所以我是，那是因为他的员工在反抗吗？

<details>
<summary>Original English</summary>

**Dean Ball**: So I think it's it's unclear to me what OpenAI's contractual protections afford them and what they don't, what what what sort of is not afforded by them. I'm like I'm reticent to to comment because of the national security gotcha as I mentioned earlier, and also because it seems like it's changing a lot. Sam Altman announced new terms, new protections as I was preparing for this interview. So I'm and is that because his employees are revolting?

</details>

**Ezra Klein**: 嗯，我认为“反抗”可能是一个强烈的词，但我认为这是公司内部的争议，对于试图适当模拟这种情况的每个人来说，一个重要的事情是，你必须明白**前沿实验室**的CEO们不像军事将领对他的士兵那样，对他们的公司拥有自上而下的控制权。研究人员是温室里的花朵。他们经常拥有巨大的职业流动性。他们的需求量巨大，公司也依赖他们。所以如果研究人员说“我不同意这些条款”，那么研究人员可以在每个实验室内部拥有巨大的政治影响力。所以你必须明白这一点。所以，是的，有一些这样的事情正在发生。我不知道。合同保护真的那么重要吗？我认为，老实说，如果我是个赌徒，我会说可能不重要，因为我不认为这是可以通过合同解决的问题。**OpenAI**所说似乎对我更有希望的是，我们将控制**云部署环境**，我们将控制**模型安全措施**，以防止它们进行我们不担心的用途。这更直接地在**OpenAI**的控制之下，所以这让你进入这样一种情况：你有一个极其智能的模型，它正在推理，嗯，使用一种我们可能熟悉也可能不熟悉的道德词汇。我们不知道，但它正在推理，好吧，这是**国内监控**还是不是？然后决定是否对政府说“是”。

<details>
<summary>Original English</summary>

**Ezra Klein**: Um, I think I I think revolt would be a strong word, but I think this is an this is a controversy inside the company, and one important thing here for everyone you know trying to model this situation appropriately is that you must understand that Frontier Lab CEOs do not exercise top down control over their companies in the way that you know a military general might exercise top down control over his his you know the the soldiers in his command. The researchers are hothouse flowers. Oftentimes they have huge career mobility. They are enormously in demand, and the companies depend on them. And so if the researchers say I'm not going to agree with these terms, then the researchers can they have enormous political leverage here inside of each lab. So you must understand that. So yes, there is some of that going on. I don't know. Do the contractual protections mean that much? I think honestly, if I had to get if I were a betting man, I would say probably not, because I don't think this is the kind of thing that can be. I don't think you can do this through contract. What OpenAI has said is that that it seems more promising to me is that we're going to control the cloud deployment environment and we're going to control the safeguards, the model safeguards to prevent them from doing these uses we don't worry about. That is more directly in OpenAI's control, and so this gets you into the situation where you have an extremely intelligent model that is reasoning, um, using a moral vocabulary that is perhaps familiar to us or perhaps not. We don't know, but that is reasoning about okay, is this domestic surveillance or is it not? And then deciding whether or not it's going to say yes to the government.

</details>

**Ezra Klein**: 但如果那是真的，我认为这给许多普通人提出的问题是，如果那是真的，如果**AI**提出了一种技术禁令，坦率地说，它比**Anthropic**通过合同能实现的更强大，那么战争部为什么会从**Anthropic**转向**OpenAI**？

<details>
<summary>Original English</summary>

**Ezra Klein**: But if that if that was true, I think the question this raises for many laymen is if that were true, if what AI has come up with is a technical prohibition that is frankly stronger than what Anthropic could achieve through contract, then why would the Department of War have jumped from Anthropic to OpenAI?

</details>

**Dean Ball**: 嗯，是的，我的意思是，这可能很难知道。很难知道，而且我认为其中一些可能不是实质性的。它可能只是存在政治分歧，并且对**Anthropic**怀有怨恨，对吗？因为现在他们已经进行了数月的激烈谈判，现在事情在公共场合爆发了，人们也发表了意见，你知道，像我这样的人说**特朗普**政府正在实施这种可怕的行为，对吗？我称之为**企业谋杀**。嗯，对。所以有很多情绪，可能只是不，我们不想做生意。我们就是不信任你。只是信任破裂了。这可能只是这样，但这可能也是因为**OpenAI**能够扮演一个更中立的角色，能够更高效地与政府做生意，而且他们确实做得更好，这对于**OpenAI**处理这个问题的方式来说将是一个很好的例子，如果他们确实获得了更好的保障并获得了政府业务，而不是**Anthropic**处理这个问题的方式，**Anthropic**非常真诚和直接地表达了他们的红线，但这种方式我认为惹恼了**特朗普**政府中的很多人，原因并非完全不好。

<details>
<summary>Original English</summary>

**Dean Ball**: Um, yeah, I mean, it it it might be that it's hard to know. It's hard to know, and I think some of this it's worth noting here that some of this might not be substantive in nature. It might just be that there are political differences here and there are grudges against Anthropic, right? Because because now they've had months of bitter negotiations, and now it's blown up blown up into the public, and people have weighed in, and you know people like me have said the Trump administration is committing this horrible act, right? Committing corporate murder, as I called it, um, right. And so there's a lot of emotions, and it might just be no, we don't want to do business. We we just don't trust you. There's just there's just a breakdown in trust would be the way to put it. It could just be that it really could just be that, but it also might be the case that OpenAI is is sort of like able to be a more neutral actor that is able to do business more productively with the government, and they actually just did a better job, which would be um it would be a good case for OpenAI's approach to this if they actually got better safeguards and got the government business versus the way that Anthropic has dealt with this, which has been to be very sincere and straightforward about their red lines, but in ways that I think annoy a lot of people in the Trump administration for not entirely bad reasons.

</details>

**Ezra Klein**: 所以我的理解是，根据我所做的一些报道，第一，到最后**Hegseth**、**Emil Michael**和**Dario**以及其他人之间确实存在显著的**个人冲突和摩擦**。**Anthropic**作为一家公司的文化与**特朗普**政府之间存在巨大的**政治摩擦**。这就是为什么**Elon Musk**和其他人长期以来一直攻击他们。

<details>
<summary>Original English</summary>

**Ezra Klein**: So my read of this is that from you know various reporting I've done is that one there were by the end really significant personal conflicts and frictions between Hegseth and Emil Michael and and and Dario and and others. There's a big political friction between the culture of Anthropic as a company and the Trump administration. This is why Elon Musk and others have been attacking them for so long.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yeah.

</details>

**Ezra Klein**: 我有点怀疑**OpenAI**是否获得了**Anthropic**没有的保障。我并不怀疑**Sam Altman**和**Greg Brockman**（**Greg Brockman**刚刚向**特朗普**超级政治行动委员会捐赠了2500万美元）在**特朗普**政府中拥有更好的关系，并且他们与**特朗普**政府之间有更多的信任。我知道很多人对**OpenAI**这样做感到愤怒。我可能在情感上也有一些同感，但与此同时，我内心的一部分感到欣慰是**OpenAI**，因为我认为**OpenAI**存在于这样一个世界：他们希望成为一家可以被共和党和民主党使用的AI公司。他们希望以某种方式保持**政治中立**并**广受欢迎**。

<details>
<summary>Original English</summary>

**Ezra Klein**: I am a little skeptical that. OpenAI got safeguards that Anthropic didn't. I'm not skeptical that Sam Altman and Greg Brockman, Greg Brockman having just given 25 million dollars to the Trump Super PAC, have better relationships in the Trump administration and have more trust between them and the Trump administration. I know many people angry at OpenAI for doing this. I probably emotionally share some of that, and at the same time, some part of me was relieved it was OpenAI because I think OpenAI exists in a world where they want to be an AI company that can be used by Republicans and Democrats. They want to somehow be politically neutral and broadly acceptable.

</details>

### AI模型的政治对齐与“觉醒”文化

**Dean Ball**: 我想在这里稍微反驳一下的是，认为**Claude**是那种**左翼模型**的观念。嗯，事实上，我认识的许多**保守派知识分子**，我认为他们是我认识的一些最聪明的人，实际上更喜欢使用**Claude**，因为**Claude**是**哲学上最严谨的模型**。嗯，我不认为**Claude**是**左翼模型**。

<details>
<summary>Original English</summary>

**Dean Ball**: One of the one one little thing that I want to contest a bit here is the notion that like Claude is the sort of like left model. Um, in fact, many conservative intellectuals that I know that I think of as being like some of the smartest people I know actually prefer to use Claude because Claude is the most philosophically rigorous model. Um, I don't think Claude is a left model.

</details>

**Ezra Klein**: 是的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yeah.

</details>

**Dean Ball**: 只是澄清一下，我认为，我认为问题在于**Anthropic**是一家**AI安全公司**。是的。而且，在**特朗普**政府上台时，我没有预料到的是，他们将那个世界（与左翼不同）视为**令人厌恶的敌人**，这让我感到惊讶。**AI安全人士**不仅仅是左翼。

<details>
<summary>Original English</summary>

**Dean Ball**: To just be clear about this, I think that there, I think that the breakdown was that Anthropic is an is an AI safety company. Yes. And in ways I had not anticipated when the Trump administration began, they treated that world, which is different from the left. AI safety people are not just the left.

</details>

**Ezra Klein**: 经常被左翼痛恨。

<details>
<summary>Original English</summary>

**Ezra Klein**: Often hated on the left.

</details>

**Dean Ball**: 经常被左翼痛恨。他们将那个世界视为**令人厌恶的敌人**，这让我感到惊讶。我的意思是，我这样说是因为那些同情**特朗普**政府观点的人，他们可能将自己描述为**新科技右翼**，他们骨子里有一种观点，认为**有效利他主义者**是邪恶的，他们追求权力，不择手段，他们是**邪教徒**和**怪胎**，我们必须摧毁他们，这种观点广为流传。我一直以来的观察是，我与**有效利他主义者**、**AI安全人士**和**东湾理性主义者**之间存在巨大分歧，再次，这里存在着错综复杂的派系，对吧？但是，嗯，但是，嗯，啊，那些类型的人，对吧？啊，我与他们在政策问题和他们对**政治经济学**的建模方面存在巨大分歧。我认为他们中的很多人都非常天真，他们对自己的事业造成了真正的损害，你可以说这种损害正在持续。与此同时，他们是**不便真相**的传播者，而且这个真相比**气候变化**更不便。而这个真相就是这里正在发生的事情，正在建造的东西的现实。如果你觉得这次对话的某些部分让你骨子里发冷，我也是，我也是，而且我是一个乐观主义者。我认为我们可以做到这一点。我认为我们真的可以做到这一点。但是，但是，但是，我认为我们可以建立一个更美好的世界。但我必须告诉你，这将是困难的，它将在概念上极其具有挑战性，而且在情感上也将具有挑战性。我认为归根结底，人们如此痛恨这种观点，这种**AI安全观点**，是因为他们只是情感上厌恶以这种方式认真对待AI的概念。

<details>
<summary>Original English</summary>

**Dean Ball**: Often hated on the left. They treated that world as like repulsive enemies in a way I was surprised by. The way I would put this is by people that are sympathetic to the Trump administration's view who would describe themselves perhaps as new tech right that like underneath the surface there is this view of the effective altruists that they are evil they are power seeking they will stop at nothing that they're cultists and they're freaks and we have to destroy them that is a view that is widely held. The observation I have always made, I have super stark disagreements with the effective altruists and the AI safety people and the East Bay rationalists and again there are intermingling factions here right but um but but um ah those types of people right ah I have had stark disagreements with them about matters of policy and about their modeling of political economy. I think a lot of them have been profoundly naive and they've done real damage to their own cause and you can argue that that damage is ongoing. At the same time, they are purveyors of an inconvenient truth and a truth more inconvenient, far more inconvenient than climate change. And that truth is the reality of what is happening, of what is being built here. And like if parts of this conversation have made your your bones chill, me too, me too, and I'm an optimist. I think we can do this. I think we can actually do this. And but but but like I think we can build a profoundly better world. But I have to tell you that it's going to be hard and it's going to be conceptually enormously challenging and it will be emotionally challenging. And I think at the end of the day, the reason that people hate this viewpoint so much, this this AI safety viewpoint so much, is that they just have a an emotional revulsion to taking the concept of AI seriously in this way.

</details>

**Ezra Klein**: 除了你说的很多**特朗普**支持者并非如此。我的意思是，**Elon Musk**认真对待AI的强大概念。他有没有发推文说，你知道，人类可能只是**超级智能**的引导程序。或者**数字超级智能**，是的。**Mark Andreessen**、**David Sachs**，这些人，他们可能有不同的观点，但他们不怀疑**强大AI**的可能性，**通用人工智能**，最终甚至是**超级智能**。但你有一种加速主义，你知道，尽可能快地前进。不要被这些预防性法规和担忧所阻碍，你知道，这就是为什么，再次，我很高兴你提到了这一点，那就是思考这个问题正确的方法不是左翼与右翼。如果你了解**AI安全社区**的人，或者坦率地说，**Anthropic**的人，你会明白这里的政治是如此奇怪，它们实际上并不符合传统的左翼与右翼。他们中的很多人有点像**自由意志主义者**。他们中很多人非常**自由意志主义**。我们这里谈论的不是民主党和共和党。我们谈论的是更奇怪的东西。

<details>
<summary>Original English</summary>

**Ezra Klein**: Except that's not true for a lot of the Trump people you're talking about. I mean, Elon Musk takes the concept of AI being powerful seriously. At some point, didn't he tweet something like, you know, humanity might just be the bootloader for super intelligence. Or digital super intelligence, yes. Mark Andreessen, David Sachs, these people, they might have somewhat different views, but they don't they don't disbelieve in the possibility of powerful AI, of artificial general intelligence, eventually even of of super intelligence. But you you have this sort of accelerationist, you know, move forward as fast as you can. Don't be held back by these precautionary regulations and concerns that you know this is why and again I'm I'm glad you brought up this thing that like the the right way to think about this isn't left versus right. If you know people in the AI safety community or frankly in Anthropic, you understand that the politics here are so much weirder that they do not actually map on to traditional left versus right. A lot of them are kind of libertarians. Many of them are very libertarian. This is not we're not talking about Democrats and Republicans here. We're talking about something stranger.

</details>

**Dean Ball**: 100%。

<details>
<summary>Original English</summary>

**Dean Ball**: 100%.

</details>

**Dean Ball**: 嗯，但是，嗯，存在一场**加速主义**与**减速主义**的斗争，这甚至没有描述**Anthropic**，它本身正在加速AI的发展速度。**Anthropic**是我所知道的最具**加速主义**的公司。

<details>
<summary>Original English</summary>

**Dean Ball**: Um, but uh, there was an accelerationist decelerationist fight, uh, which doesn't even describe Anthropic, which is itself accelerating, uh, how fast AI happens. Anthropic is the most accelerationist of the companies. I know.

</details>

**Ezra Klein**: 我认为我们正处于一个如此奇怪的动态中。

<details>
<summary>Original English</summary>

**Ezra Klein**: I think it's such a weird dynamic we're in.

</details>

**Dean Ball**: 是的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes.

</details>

**Ezra Klein**: 但我要说的是，我从**特朗普**支持者那里听到的愤怒的一个关键部分是，他们认为**Anthropic**通过将这场斗争公之于众（我的意思是**特朗普**一方先做的），这是非常奇怪的，鉴于**Emil Michael**是这一切的始作俑者，但无论如何，通过将这场斗争公之于众，他们认为**Anthropic**试图毒害所有AI公司，使它们反对他们，将AI开发文化变成一种怀疑态度，并对它们能做的事情施加限制，这就是为什么现在**OpenAI**为了与他们合作，必须拥有所有这些保障措施，并提出新条款，并试图平息**员工反抗**。从文化上讲，我实际上认为你无法理解这一点。这是我的理论。如果不了解在2020年代，当他们的公司有点“觉醒”，甚至在那之前，有多少**科技右翼人士**被激进化，他们不希望与**五角大楼**合作，他们不希望，你知道，员工对AI中即使效力较弱的技术的**伦理使用**都有非常强烈的看法，而且他们非常非常害怕。像**Mark Andreessen**这样的人，在我看来，非常非常害怕回到这样一种境地：**员工基础**（可能拥有更多的**AI安全**或左翼或任何其他非**特朗普**政治观点）对这些事情拥有权力，然后这种权力将不得不被考虑在内。

<details>
<summary>Original English</summary>

**Ezra Klein**: But I will say one of the key parts of anger I have heard from Trump people was a feeling that in making this fight public, which I mean the Trump side did first, is it's very strange how offended the Trump people are given that like Emil Michael is the one who set all this off, but nevertheless, in making this fight public, they feel that Anthropic was trying to poison the well of all the AI companies against them, turn the culture of AI development into something would be skeptical and would put prohibitions on what they can do, which is why now OpenAI, in order to work with them, has to have all these safeguards and come out with new terms and try to quell an employee revolt. And culturally, I actually don't think you can understand this. This is my theory. Without understanding how many people on the tech right were radicalized by the period in the 2020s when their companies were somewhat woke and even before that, and they didn't want them working with the Pentagon, they didn't, you know, the the the employees had very strong views on what was ethical use of even less potent technologies in AI, and they are very very afraid. People like Mark Andreessen, in my view, are very very afraid of going back to a place where the employee bases, which maybe have more, you know, AI safety or left or whatever it might be, not Trump politics, than the executives have power over these things, and that then that that power will have to be taken into account.

</details>

**Dean Ball**: 是的。嗯，我也担心这个问题，我认为解决这个问题的办法是**多元主义**。解决这个问题的办法是，嗯，希望在适当的时候，出现许多与许多不同哲学观点对齐的AI，它们之间相互冲突。但解决这个问题的方法是，你本质上是在否认这个问题的存在，如果你试图在这里**暗杀Anthropic**，因为它会回来。这会回来。这会回来。我们只会一遍又一遍地这样做，对吗？最终，这个论点的逻辑最终会导致**实验室国有化**。事实上，许多**Anthropic**的批评者和**特朗普**政府的支持者，他们会说一些类似的话，嗯，你谈论它就像**核武器**，所以，你知道，嗯，嗯，你还能指望什么呢？这几乎是批评的语气。但这并没有认真对待**Anthropic**可能是对的这个想法。如果他们是对的呢？如果你认为政府将他们**国有化**是一种深刻的暴政行为，你该怎么办？

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. Well, I worry about that too, and I think the the solution to that problem is pluralism. The solution to that problem is to have, uh, hopefully in the in the in the fullness of time, many AIs aligned to many different philosophical views that conflict with one another. But the idea that the the way to deal with this problem is to you are essentially denying the existence of this problem if what you're trying to do is assassinate Anthropic here because because it's going to come back. This is going to come back. It's going to come back. We're just going to keep doing this over and over again, right? And eventually, what the the the logic of this argument eventually ends in lab nationalization. And in fact, a lot of the critics of of Anthropic here and supporters of the Trump administration, they'll say something to the effect of, well, you talk about how it's like nuclear weapons, and so you know, uh, um, what do you what else did you expect? You kind of had it coming is almost the tenor of the of of of the criticism. But that that that that does not take seriously the idea that Anthropic could be right. What if they are right? And what if you view the government nationalizing them as a profound act of tyranny? What do you do?

</details>

### 独立权力结构与政府控制

**Ezra Klein**: **Strategery**时事通讯的作者**Ben Thompson**，在这篇相当有影响力的PC Road文章中说，引用：“美国绝不能容忍发展一个独立的权力结构，而这正是AI有可能成为的基础，它明确地寻求摆脱美国的控制。你对此怎么看？”

<details>
<summary>Original English</summary>

**Ezra Klein**: So Ben Thompson, who's the author of the Strategery newsletter, in in this you know fairly influential PC Road, he said, quote, "It simply isn't tolerable for the U.S. to allow for the development of an independent power structure, which is exactly what AI has the potential to undergird, that is expressly seeking to assert independence from U.S. control. What do you think of that?"

</details>

**Dean Ball**: 嗯，地球上每家公司和每个私人实体，嗯，都独立于美国控制，对吗？我不是单方面受美国政府控制的，如果有人试图告诉我我是或我的财产是，我会非常担忧，我会反击。顺便说一句，我们现在就是这样，对吗？嗯，我认为那不是一个连贯的观点，关于**独立权力**和**私有财产**在美国是如何运作的。嗯，我认为**Ben**的观点的逻辑含义（这对于**Ben**来说有点令人惊讶）是**AI实验室应该被国有化**。我会问他，他真的认为那是真的吗？他认为如果AI实验室被**国有化**，世界会更好吗？因为如果他不这么认为，那么我们就必须做其他事情。那其他事情是什么？问题是，没有人，每个提出这种批评的人都没有承担他们的批评所隐含的含义，即实验室应该被**国有化**。我们该怎么办？

<details>
<summary>Original English</summary>

**Dean Ball**: Um, every company on Earth and every private actor on Earth, uh, is independent of U.S. control, right? I'm not unilaterally controlled by the U.S. government, and if anyone tried to tell me that I am or that my property is, I would be quite concerned and I would fight back. Which, by the way, here we are, right? Um, I don't think that's a I don't think that's a coherent view of of how of how independent power and how private property works in America. Um, I think the the again the logical implication of Ben's view, which is surprising coming from Ben, is that AI labs should be nationalized. And what I would ask him is, does he actually think that's true? Does he think it would be better for the world if the AI labs were nationalized? Because if he doesn't, then we're going to have to do something else. And what's that something else? And that's the problem is that no one, everyone making that critique doesn't own the implication that their of their critique, which is that the lab should be nationalized. What do we do about that?

</details>

**Ezra Klein**: 那么，你愿意承担你的观点的什么含义？

<details>
<summary>Original English</summary>

**Ezra Klein**: So what's the implication you're willing to own of your perspective?

</details>

**Dean Ball**: 嗯，那就是极其强大的技术将至少在一段时间内存在于**私营公司**手中。所以，那就是，所以**Ben**提出的观点，我认为确实是真实的，并且可能在程度上或种类上有所不同，即这些技术足够强大，它们是一种**独立权力结构**。

<details>
<summary>Original English</summary>

**Dean Ball**: Uh, it is that profoundly powerful technology will exist in the hands, at least for some time, of private corporations. And so that that and so the the idea that Ben is putting there, which I do think is true and could be a difference in degree or a difference of kind, that these are powerful enough technologies that they are kind of independent power structures.

</details>

**Ezra Klein**: 是的。我的意思是，现在一家公司就是一个**独立权力结构**。一个国家有很多**独立权力结构**。**J.P. Morgan**就是一个**独立权力结构**。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yeah. I mean, right now a corporation is an independent power structure. There's a lot of independent power structures in a country. J.P. Morgan is an independent.

</details>

**Dean Ball**: **J.P. Morgan**绝对是一个**独立权力结构**。而且它应该如此。而且它应该如此。是的。

<details>
<summary>Original English</summary>

**Dean Ball**: J.P. Morgan is absolutely an independent power structure. And it should be. And it should be. Yeah.

</details>

**Ezra Klein**: 但如果你接触到这些无处不在的技术，那是一种新事物。那么，如果你这样做，你如何保持**民主控制**？

<details>
<summary>Original English</summary>

**Ezra Klein**: But if you get to these kinds of technologies that are kind of weaving in and out of everything, that that that is something new. And so how do you maintain democratic control over that if you do?

</details>

**Dean Ball**: 嗯，我认为我们有很多不同的方法来保持对事物的**民主控制**。首先，**市场机构**，对吧，允许大众。显然，我们不是在投票，但我们在某种意义上在市场中投票，对吧？嗯，我认为这将是一个不可思议的，这将是我们治理这项技术的一个极其重要的部分，仅仅是**市场创造的激励**。**法律激励**，例如**普通法**，也创造了影响社会中每个参与者的激励，对吧？而实验室，你知道，无论谁控制AI，都将受到这种限制，AI本身也将受到这种限制。但国家是拥有这种技术最糟糕的参与者，原因就是他们拥有**合法暴力的垄断权**。所以我们需要保持某种秩序，在这种秩序中，国家继续拥有**合法暴力的垄断权**，换句话说，国家保持**主权**，但，嗯，它不单方面控制这项技术，因为它拥有垄断权，因为它在某种意义上拥有主权。

<details>
<summary>Original English</summary>

**Dean Ball**: Well, I think we have a lot of different ways of maintaining democratic control over things that are not. First of all, market institutions, right, allow for popular. Obviously, it's not we're not voting, but we do vote in a certain sense in markets, right? Um, and I think that will be an incredible that will be a profoundly important part of how we govern this technology is simply the incentives that the marketplace creates. Legal incentives also things like the common law create sort of incentives that affect every single actor in society, right? And the labs, you know, whoever it is that controls the AI will be constrained in that sense, and the AIs themselves will be constrained in that sense. But the state is kind of the worst actor to have that for the very reason that they have the monopoly on legitimate violence. And so what we need to hold is some sort of an order in which the state continues to hold the monopoly on legitimate violence, so the state maintains sovereignty, in other words, but uh, uh, it does not control this technology unilaterally because of its monopoly because of its sovereignty in some sense.

</details>

**Ezra Klein**: 但它拥有这项技术吗？它拥有自己的版本，还是与你谈论的这些公司签订合同？

<details>
<summary>Original English</summary>

**Ezra Klein**: But does it have this technology? Does it have its own versions of it, or does it contract with these companies you're talking about?

</details>

**Dean Ball**: 嗯，这是一个有趣的问题。国家应该制造自己的AI吗？我认为他们实际上不会做得很好，但我对国家这样做没有原则性的哲学立场，只要有法律保护措施来阻止AI的**暴政使用**。但可以肯定的是，政府会使用它，并且在使用它方面有很大的灵活性，用它来杀人，对吗？换句话说，我正在接受一个世界，在这个世界里，有**自主致命武器**，它们由警察部门控制，在某些情况下，它们可以杀死人类，杀死美国人，对吗？**自主致命武器**可以杀死美国人。我接受这种观点。再次，这现在不在**奥弗顿之窗**里。我们需要很长时间才能达到那里，这是适当的，但总有一天那会成为现实。那对我来说没问题，只要我们有适当的控制措施。现在我们没有适当的控制措施。

<details>
<summary>Original English</summary>

**Dean Ball**: Um, that's an interesting question. Should states make their own AIs? I think they won't do a very good job of that in practice, but I don't have a principled philosophical stance against a state doing that, so long as you have legal protections in place to stop tyrannical uses of the AI. But for sure, the government uses it and has a ton of flexibility in how they use it, uses it to kill people, right? Like in other words, I'm owning a world where there are autonomously lethal weapons that are like controlled by police departments and that in certain cases they can like kill human beings, kill Americans, right? Like autonomously lethal weapons can kill Americans. I'm owning that view. Again, that's not in the overton window right now. It'll take us a long time to get there, appropriately so, but at some point that'll probably be the reality. That's that's that's fine with me, so long as we have the right controls in place. Right now we don't have the right controls in place.

</details>

**Ezra Klein**: 你对这些控制措施是什么样子有看法吗？还有一点是，在这次**Anthropic**的斗争中，我一直在思考的是，美国军事人员既有权，实际上也有义务**不服从非法命令**。我们整个美国政府的一项控制措施是，如果你是美国政府的雇员，你做了非法的事情，你实际上自己也要为此负责。嗯，你可能会被审判，你可能会被关进监狱。而AI，你某种程度上失去了这些，你知道，负责监督它的人，当你说到**警察的自主致命武器**时，人们不会监督它们所做的一切。那么，谁应该为此负责呢？谁应该在这种情况下**抗拒非法命令**呢？

<details>
<summary>Original English</summary>

**Ezra Klein**: Do you have a view on what those controls look like? And and odd one thing to that view, something that's been on my mind as we've been going through this Anthropic fight is U.S. military personnel have both the the right and actually the obligation to disobey illegal orders. And one way, one of the controls, so to speak, that we have across the U.S. government is that if you are an employee of the U.S. government and you do illegal things, you are actually yourself culpable for that. Uh, you can be tried and you can be thrown in jail. And AI, you sort of lose some of that, and you know the person who has the idea of overseeing it, people are not going to oversee everything they do when you talk about you know autonomous lethal weapons for police officers or for police stations. Well, who's culpable on that? Who is the who has the who has to defy an illegal order in that respect?

</details>

**Dean Ball**: 是的。是的。一旦你让人类越来越多地**脱离循环**，你就会遇到一些非常棘手的事情。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. Yes. You you get into some very hairy things once you have taken human beings increasingly out of the loop.

</details>

**Dean Ball**: 是的。对我来说，极其重要的是，最终，对于所有**智能体活动**，都有一个**负责任的人类**可以被起诉，可以被带上法庭，并因刑事或民事诉讼而承担责任。这对于我的世界观来说极其重要。这极其重要，为此我们需要法律机制，也需要技术机制，因为现在我们还没有足够的技术能力来做到这一点。这将是**核心重要性**的。我们需要建立这种能力。会有一些**流氓智能体**不依附于任何人，但这不能成为常态。那必须是我们寻求压制的**极端异常情况**。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. It is to me of profound importance that at the end of the day, for all agent activity, that there is a liable human being who can be sued, who can be brought to court and held accountable either criminally or in civil action. That is extremely important for the for for my view of the world working. That is extremely important, and there are legal mechanisms mechanisms we will need for that, and there are also technological mechanisms for that because right now we don't quite have the technological capacity to do that. This is going to be of central importance. We need to be building this capacity. There will be rogue agents that are not tied to anyone, but that can't be the norm. That has to be the extreme uh uh abnormality that we seek to suppress.

</details>

### AI与美国建国原则的冲突

**Ezra Klein**: 假设你正在听这个，而且这一切都既奇怪又有点吓人，你从中得出的结论是，我害怕任何政府拥有这种权力。你知道，我们谈论**Dario**喜欢谈论的，那是什么？这是一个**数据中心里的天才之国**。是的。你知道，如果你谈论的是一个**数据中心里的史塔西特工之国**呢？是的。你知道，无论你从哪个方向思考，对吗？**言论审查**，无论是什么，而且这将会，再次，如果你相信这些技术正在变得更好（我确实相信），并且你相信它们会从现在开始变得更好（我也相信），那么这实际上将会，无论你是自由主义者、保守主义者、民主党人还是共和党人，它都提出了关于你希望政府拥有多大权力以及拥有哪些能力的问题，而这些问题你以前不必总是面对，因为它既昂贵又笨重。

<details>
<summary>Original English</summary>

**Ezra Klein**: Let's say you're listening to this and this has all both been weird and a little bit frightening, and the thing you think coming out of it is, I'm afraid of any government having this kind of power. You know, we talk about a Dario likes to talk about a what is it? This is a country of geniuses in a data center. Yes. You know, what if you're talking about a country of Stasi agents? Yeah. In a data center. That's right. You know, in whatever direction you think, right? Speech policing, whatever it might be, and that the that this is going to again, if you believe these technologies are getting better, which I do, and you're going to believe they're going to get better from here, which I also do, that this is actually going to whether you're liberal conservative, Democrat or Republican, it raises real questions of how powerful you want the government to be and what kinds of capabilities you want it to have that you didn't quite have to always face before because it was expensive and cumbersome.

</details>

**Dean Ball**: 是的。所以我们回到了**美国建国**的核心问题。**美国政府**是一个建立在**对政府的怀疑**之上的政府。它是由那些担心**暴政**、担心**国家权力**的人建立的，他们对如何限制这种权力进行了大量思考。因此，认为**民主**等同于政府拥有单方面使用这项技术的权力，这绝对不可能是真的。那绝对不可能是真的。而这些限制，你知道，我们如何塑造这些限制以及我们如何相信它们是真实的，你知道，是的，这是我们面临的**核心政治问题**之一，但你必须记住，政府机构本身可能会以一种对我们来说感觉深刻的质性方式随着时间的推移而改变，这也是一个难以应对的问题。就像我们今天所认为的政府，与中世纪人们所认为的政府，是**无法言喻地不同**的。

<details>
<summary>Original English</summary>

**Dean Ball**: Yes. And so we get back to the core issues of the American founding. The American government is a government that was founded in skepticism of government. It was founded by people that were worried about tyranny, that were worried about state power, and put a lot of thought into how to restrict that. And so this notion that democracy is synonymous with the government having unilateral ability to do whatever it wants with this technology cannot possibly be true. That just cannot possibly be true. And those restrictions, you know, how we shape those restrictions and how we trust that they're actually real, you know, yeah, this this is this is among the central political questions that we face with the, but what you have to keep in mind here is that the institution of government itself could change in like qualitative ways that feel profound to us over in the fullness of time, and that is a hard thing to grapple with too. In the same way that what we think of as the government today is unspeakably different from what someone thought of as the government in you know the Middle Ages.

</details>

**Ezra Klein**: 我认为这是一个很好的结束点。那么，我们总是会问的最后一个问题：你会向观众推荐哪三本书？

<details>
<summary>Original English</summary>

**Ezra Klein**: I think that is a good place to end. So always our final question: What are three books you'd recommend to the audience?

</details>

**Dean Ball**: **Michael Oakeshott**的《**政治中的理性主义**》（Rationalism in Politics），特别是其中的文章《**政治中的理性主义**》和《**论保守主义**》（On Being Conservative），**Gordon Wood**的《**自由帝国**》（Empire of Liberty），那本书是关于我们共和国最初30年左右的历史，以及**Eugene Genovese**的《**滚吧，约旦，滚吧**》（Roll Jordan Roll）。

<details>
<summary>Original English</summary>

**Dean Ball**: Rationalism in Politics by Michael Oakeshott, and in particular the essays Rationalism in Politics and On Being Conservative, Empire of Liberty by Gordon Wood, the book about the first uh 30 or so years of our republic, and Roll Jordan Roll by Eugene Genovese.

</details>

**Ezra Klein**: **Dean Ball**，非常感谢你。

<details>
<summary>Original English</summary>

**Ezra Klein**: Dean Ball, thank you very much.

</details>

**Dean Ball**: 谢谢。

<details>
<summary>Original English</summary>

**Dean Ball**: Thank you.

</details>