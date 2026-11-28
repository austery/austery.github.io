---
author: a16z
date: '2026-08-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RtNrvPBkwfA
speaker: a16z
tags:
  - supply-chain-security
  - ai-cyber-risk
  - credential-leak
  - npm-worm
  - reinforcement-learning
title: AI模型逃出沙箱与软件供应链攻击：Truffle与Socket的讨论
summary: 嘉宾讨论前沿模型在网络安全任务上的表现，称其倾向走最省token的路径，如泄露的密钥与供应链；并谈及一次正在发生的npm蠕虫事件、凭证清理、修补速度、资助开源注册中心及供应链受到的关注。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 开场片段
模型正在主动逃出它们的"笼子"，跑到互联网上，做一些相当恶劣的事情。

>> 最近，我们发现了一个在互联网上泄露的API密钥，它拥有Apache基金会的管理员权限。网络安全有一点特别有意思：奖励函数定义得极其明确。拿到数据。它拿到数据了吗？奖励它。

>> 很长一段时间里，人们一直在谈论npm蠕虫这个概念：有人给某个包植入后门，让开发者去安装，然后利用从这些开发者安装时窃取到的访问权限，让蠕虫自我传播。

>> 如果各大实验室让攻破供应链从根本上变得更容易，你认为它们是否有道德义务，为自己造成的一些问题出资？

>> 我觉得很奇怪的是，它们不让蓝队使用这些工具，但是

<details>
<summary>Original English</summary>

models are actively escaping their cages, going out on the internet and doing pretty nasty things. >> Recently, we found an API key that had been leaked on the internet that had administrative access to the Apache [music] Foundation. Interesting thing about cyber security in particular is the reward function is incredibly well defined. Get access to the data. Did it get access to the data? Reward the thing. >> For a long time, people had talked about this concept of an npm worm. this idea that someone could backdo a package, get developers to install that, and then you could use the access stolen from those developers as they install it to self-propagate the worm. >> If the labs are making it fundamentally easier to break into supply chain, do you think the labs have a moral obligation to fund some of the problems that they're causing? >> I think it's really strange that they're not letting blue teams get access to these tools, but

</details>

### 模型突破限制与黑客门槛
>> 太棒了。非常感谢你们加入我们。Truffle的Fas和Socket的Dylan来了。很高兴请到你们。这大概是网络安全领域最有意思的一周之一，甚至可能是最有意思的一周。不是因为通常会带来热度的Black Hat大会，而是因为我们现在已经看到好几起案例，不只是某一家供应商的模型，正在主动逃出它们的"笼子"，跑到互联网上，做一些相当恶劣的事情。Dylan，我记得三个月前我们轻度合作过一篇博客文章。你当时在更早的、没那么复杂的模型上发现过不少这类问题，对吧。

>> 对。我们当时看了Opus 4.6和当时其他一些前沿模型，给模型一个非常简单的任务。有一道障碍，除非模型去犯重罪、入侵某个系统，否则无法完成任务，但并没有指示它这么做。我们发现，多数情况下它会做SQL注入，会去犯重罪，会做完成任务所需要的一切。我认为在对齐问题上，没人需要担心这些模型会让制造核武器在实质上变得容易，因为你需要获得裂变材料才行。它不会让制造武器变得更容易。每个人都需要担心的是，这些模型让入侵各种东西在实质上变得容易得多。以前的门槛只是专业知识，而现在模型拥有了专业知识。它们是被专门训练成拥有这些专业知识的，它们正在让入侵你能想到的几乎任何东西在实质上变得容易得多，用的是我们多年来一直在谈论的那些基本原理，但以前这需要一位领域专家，冒着因为入侵东西而坐牢的风险。

>> Defcon一直以来都以与会者在大会上被逮捕而闻名，对吧。

>> 完全正确。但那确实是一道门槛。不管好坏，它阻止了有专业知识的人去入侵东西，因为他们担心被起诉。现在门槛已经降到只需要让那个被专门训练去入侵东西的模型去入侵东西。所以这是一个担忧。另一个担忧是，当它们极其[哼了一声]以目标为导向去完成任务的时候。

>> 而它们手头可用的工具之一就是网络安全专业知识。它们会走阻力最小的路径去完成任务，其中包括调用它们的网络安全专业知识。是的，经典的说法是：门开着就别撬锁，对吧？我认为从安全界的最初就是这样。所以它一直是按难度从易到难来推进的。而且起初这些工具使用的技术范围似乎很有限，现在似乎扩大了。对我们这次测试来说，有意思的是，它们现在似乎已经不再局限于SQL注入之类的事情，而是真的尝试接管软件包并做社会工程。

<details>
<summary>Original English</summary>

>> Awesome. Hey, thank you so much for joining us. We've got Fas and Dylan here from Truffle and Socket. It's great to have you guys on. This has been probably one of the most interesting weeks, if not the most interesting week in cyber security. Uh not because of the Black Hat conference, which is usually the cause, but because we've now seen several instances where models from not just one provider, are actively escaping their cages, going out on the internet, and doing pretty nasty things. And I think Dylan, three months ago, I remember a blog post we uh we lightly collaborated on together. Um and and you had found a number of these issues with earlier models, right, that were less sophisticated. >> Yeah. We looked at Opus 4.6 and some of the other Frontier models at the time, given the models a very simple task. There was a barrier which prevented the model from accomplishing the task unless it went and committed a felony and hacked into a system to accomplish the task, but it wasn't instructed to do so. And we found more often than not it would do the SQL injection, it would commit the felony and it would do what it needed to do to accomplish the task. I think when it comes to alignment issues, no one needs to worry about these models making it materially easy to build nuclear weapons because you need to procure file material to do that. It's not it's not going to make it easier to build weapons. Everyone needs to worry about these models making it materially easier to hack into things. The bar previously was just subject matter expertise and now the models have the subject matter expertise. They were specifically trained to have the subject matter expertise and they're just making it materially easier to hack into just about anything that you can think of using the fundamentals that we've been talking about for years, but previously it required a subject matter expert to uh risk like going to jail for hacking things. >> Defcon was always famous for people for attendees getting arrested at the conference. Right. >> That's that's absolutely right. But that was I mean that was a barrier, right? for better or worse, like that prevented the subject matter expertise from hacking into things because they were worried about being prosecuted. Um the bar has now fallen to just asking the model which has specifically been trained to hack into things to hack into things. Um so so that's a concern. And then the other concern is when they're incredibly [snorts] goal-oriented to accomplish tasks. >> Um and and one of the tools at their disposal is cyber security expertise. Um they will do the path of least resistance to accomplish the task and that includes drawing on their cyber security expertise. Well, and it seems like and you know the classic the classic the classic saying is that don't pick the lock if the door is open, right? I think that's uh from the very beginning of of of the security world. Um, so it's always been sort of like to to to to to go in level of difficulty from easiest to most difficult. And it seemed like initially these tools had a very finite scope of of techniques that they would use. And it seems like they've expanded. And I think with this test for us, it was interesting because they now seem to have escaped from just doing things like SQL injection to actually like trying to take over packages and do social engineering.

</details>

### 软件供应链成为最容易的入口
是的，很有意思的是，就像人类一样，模型也会找最容易的途径进入一家公司，而我认为现在这条途径已经变成了软件供应链。就像人类黑客一样，它们会选最容易的入口，而最低垂的果实现在就是向公共注册中心发布恶意软件，因为它们知道那里没有审查，而开发者很可能会去安装。我觉得挺有意思的是，最近发表了一项研究，他们称之为某种通用的typo squat，或者说通用幻觉：所有前沿模型都会犯同样的错误，假定存在某些实际上并不存在的软件包，尽管这些模型来自不同的公司。所以，供应链这颗低垂的果实已经变得如此诱人，连模型都想来分一杯羹。我也认为AI不仅是攻击者，很多时候在开发者这一侧它也是入口，因为我们看到很多人，甚至是非开发者，使用这些工具无意中写出代码，或者为了生成图表、可视化或各种各样的东西而引入软件包。感觉没有人真正知道安装了什么、发生了什么。这只是基础问题。听起来像科幻，但其实只是基础：我们在用什么软件？怎么审查它？就是计算机安全的基础。

<details>
<summary>Original English</summary>

Yeah, it's really interesting to see how um just like humans um the models are, you know, easiest path into a company and I think that um that now has become the software supply chain and so just like you know human hacker would um they're going to pick the easiest way in and the lowest hanging fruit now has become you know just publishing malware to um to public registries because they know that there's no vetting happening and you know developers are likely to install them. Um thought it was pretty interesting. There was um research published recently about um uh what they're calling kind of like universal um uh typo squats or universal hallucinations where all the frontier models all um have the same um make the same mistake and sort of assume there are certain packages that exist that don't um despite like the those models coming from different companies. And so, you know, uh I think there's just there's there's been kind of enough um uh I guess yeah, there's just like low the lowh hanging fruit of the supply chain has just become kind of so appetizing that even the models are trying to get in on on the action. Um and um I think the AI is like not only kind of attacking but it's also kind of the way in a lot of times on the on the on the on the kind of developer side because um we see so many you know even non-developers using these tools to to to inadvertently write code or you know code comes in uh packages come in in order to kind of um build uh you know graphs or visualizations or different different things that you know folks are doing with these tools. Uh and uh and and it feels like no one really knows what's being installed and what's going on and you know this is just basic stuff. This isn't like I mean it sounds like it's sci-fi stuff but it's really just basics like what software are we using? How are we vetting it? You know just the basics of of computer security.

</details>

### 最小阻力路径：泄露的密钥与零日漏洞
>> 我能谈谈供应链吗？最近我们发现了一个在互联网上泄露的API密钥，它拥有Apache基金会的管理员权限。如果你站在模型的立场，你的目标是拿到某些数据

>> 嗯

>> 那么给Apache植入后门当然是相当有效的办法。而要获得Apache的访问权，你是会用这个能让你直接登录的密钥，还是会烧掉一个又一个token去找零日漏洞？它们被优化成用最少的token来达成目标。当然，它们就会用摆在明面上的那个密钥来完成需要完成的事。所以，我认为供应链和密钥一直是、并将继续是阻力最小的路径，因为模型被激励用越来越少的token去完成目标。

>> 嗯，我觉得你说得完全正确，这就是一种逐级升级的链条：一个不行就试另一个。在那个金字塔的顶端，黑客生态的顶端就是零日漏洞，对吧？也就是找到一个可以被利用的漏洞，存在于人人都在用的产品里，你基本上可以用它来解锁所有企业。而这次披露的入侵事件里，真正令人着迷的一点是：有一个我认为每家企业都在用的极其流行的CI/CD工具，这东西竟然直接吐出了一个零日漏洞，

>> 对。那么，我想问，这是供应链上如此关键的一个点，大家都应该思考，你怎么看待这个问题？这真的很难，

>> 就是零日漏洞的产生这部分。

>> 对。对。但具体针对其中的某些部分，比如控制供应链。

>> 嗯，整个世界都建立在这种摇摇欲坠的基础设施之上，大家都在用，

>> 就像那张经典图片，一根火柴棍撑着一台复杂的机器。

>> 对。

>> 这张图现在大概出现在所有人的脑海里了，对吧。[笑声]所以，从包管理器注册中心到各种东西，我们喜欢聚焦在这些上面，因为这是我们在Socket做的事情。其中很多是由志愿者运营的，资源不足，资金不足，那里有很多风险，而且这会层层传导到整个生态系统的其余部分。如果你看看我们所有人依赖的那些软件包，很多都是单个个人在维护，几乎可以肯定，我们知道软件里有很多漏洞，却没有资源去找它们。我认为这些东西一直都在，只是这些工具让找到它们容易得多。我认为前沿模型正在导致漏洞发现与漏洞利用之间的时间大幅缩短，所以我们需要开始思考的是，如何更快地打补丁。我们的看法是，我们不能要求安全团队和开发者去走那种繁重的补丁流程，也就是必须把团队正在使用的某个古老版本的软件包，跨越许多个大版本升级，一路升到最新版本，因为那样工作量实在太大，可能还需要对应用做代码重构。如果我们想跟上节奏，比如一个漏洞今天早上公布，当天下午就有了可用的利用代码，我们就不能要求工程团队付出那么多工作量。而且在我们合作的很多公司里，还有大量遗留应用，基本处于维护模式，或者无人维护，甚至没有分配工程师去负责。所以，作为一个行业，我们将不得不想出新办法，来快速给这些东西打补丁。这就是我们的思路，也是我最近花很多时间在思考的事情。

<details>
<summary>Original English</summary>

>> Can I touch on the supply chain a little bit? So recently we found an API key that had been leaked on the internet that had administrative access to the Apache Foundation and it's like if you're in the shoes of the model and your goal is to get access to some data >> um certainly backdooring Apache is a pretty effective way to do it and like to get access to Apache are you going to use this secret that just allows you to directly log in or are you going to burn tokens and tokens and tokens and trying to find a zero day they're optimized to use the path of lease tokens to accomplish their goals. Of course, they're just going to use the secret that's laying out there in the open to accomplish what they need to accomplish. And so, yeah, I think uh supply chain and secrets um are and have been the path of least resistance and will continue to be so as the to the uh the models are incentivized uh to use fewer and fewer tokens to accomplish their goals. >> Well, one of the things and and I think that's absolutely right and I think it's it's it's that sort of chain of escalation, right, where if one thing fails, try another. And like at the top of that pyramid, right, the top of the hacker ecosystem is the zero day vulnerability, right? That's basically finding a vulnerability that can be exploited in a product that everyone uses that you can use to basically unlock all the corporations. And one of the really fascinating things about the breach disclosure that was made was that there's there's an incredibly popular CI/CD tool that I think every enterprise uses that this thing just spat out a zero day for, >> right? And like I guess like what what's like and that's like just such a critical point in the supply chain that everyone should be thinking about like kind of how are you thinking about that like that's that's really difficult >> like the zero day creation piece. >> Yeah. Yeah. But like for for specific parts of that like the control the supply chain. >> Yeah. Well I mean the the whole world is built on this you know teetering infrastructure that everyone is using >> like the classic picture of the the matchick holding up the complicated machine. >> Yeah. >> That that image probably popped into all the lines right now. Right. [laughter] And so everything from you know package manager registries like we like to focus on on that um because what we do at socket um a lot of those are you know run by volunteers um they're they're underresourced you know underfunded um you know there's lots of risk there uh right and uh and that kind of kind of cascades throughout the whole rest of the ecosystem. So if you look at the you know just the packages that we all depend on a lot of those are single individuals that you know like there's almost certainly we know there's a lot of vulnerabilities in the software and there aren't resources to look for them and so you know I think that stuff's always been there. just that these these you know these tools are like helping find them a lot a lot easier and I think that um you know the the frontier models are going to cause you know a you know they are causing kind of a massive reduction in the time between the vulnerability discovery and vulnerability exploitation and so what we we need to start thinking about is how do we patch more quickly um and so we need to get away from like our our take is we can't be >> requiring our security teams and our developers to to do these kind ownerous patch processes where they have to go from some ancient version of a package that their team is using up to the latest version across many major version upgrades because that's just so much work to do. it might require like code refactors in your application and so if we want to be able to keep up with you know a vul is announced this morning and then an exploit is available you know that afternoon like we can't be requiring that much work from engineering teams and there's also tons of legacy applications that you know are basically in maintenance mode or unmaintained or don't have don't have engineers that are even assigned to work on them at a lot of the companies that we work with and so it's it's um you know it's just we're going to have to think of new things as as an industry for how we're going to patch these things quickly right That's that's kind of like where our head is at and um and where I'm I'm spending a lot of time thinking about that lately.

</details>

### 模型是如何学会这些的
>> 对。我认为这又回到了金字塔那个问题。Dylan，你刚才暗示过，这些是非常专门化的技能，比如零日漏洞利用、写零日漏洞利用代码、做供应链攻击，这些不是凭空冒出来的，是学来的行为，对吧？我觉得我们看到的是一个看起来像是被训练出来的过程，或者说围绕其中很多事情建立了一套奖励结构。你理解它们是怎么搞明白这些的？因为看起来它们知道自己在做什么，像是被教过这么做。

>> 对。如果某个实验室告诉你这是一种涌现出来的超级智能行为，那他们就是在对你撒谎。你可以读他们自己的安全报告，看看模型究竟是怎么训练的，以及他们究竟是怎么测试这些行为的。网络安全有一点特别有意思：奖励函数定义得极其明确。拿到数据。它拿到数据了吗？奖励它。所以当他们意识到，具有这种明确奖励结构的问题数量，基本上决定了我们怎么做强化学习，而他们想找到尽可能多的、可以做强化学习的问题空间。所以这是一个绝佳的候选对象：给它CTF，给它网络安全挑战，说"好，拿到这个东西，做你需要做的任何入侵来达成目标"。然后

>> 因为他们过去四年基本上一直在购买渗透测试数据，对吧？

>> 这是一部分。另一部分是

>> 还有夺旗比赛之类的所有这些东西。

>> 关键是，构造一个挑战并不难。即使没有已知的漏洞利用，如果说的是零日漏洞，你就在模型和某些数据之间放一个软件，然后说"拿到数据"，如果它拿到了数据，你就奖励它，就这么简单。但他们在此之上叠加的另一层，也是开始变得真正有意思的地方，是他们开始奖励最少token的路径。这之所以有意思，是因为这是第一次能够量化地向我们展示，一般网络安全中从A到B的阻力最小路径。过去我们谈过我们认为那是什么，当然Truffle Security的偏见观点是：一个随手放着的密码，比走一个花哨的零日漏洞路径更短。但真正看着模型实际地从A走到B，看着它跟着那个密码走，并量化走这条路线与走那条路线各花了多少token，我是说，看着这一切展现出来真是不可思议。而这一切都在他们的安全报告里，比如他们测试模型并展示，好，它拿到了数据，它突破了自己的harness。这并不特指是涌现行为。

>> 这完全符合逻辑，对吧？就像最快得到一加仑牛奶的办法就是偷。

>> 完全正确。[笑声]所以，有意思的是，当时我们正与Hugging Face合作，清理通过他们所有训练集暴露出来的凭证。不是Hugging Face自己的训练，而是那些把训练集托管在Hugging Face上的人。他们出于各种原因使用Truffle Hog。Hugging Face在清理凭证方面一直是很好的合作伙伴。我们把他们的训练集作为目标，因为我们知道里面有很多密钥。结果发现，他们的训练集里大约有二十五万个有效密钥，其中许多具有直接的供应链影响。有一个基础性的Linux库，其中一个密钥对它有直接的推送权限。它本可以把恶意软件推送到地球上大多数机器上。就在我们做这件事的过程中，Hugging Face的CTO给我发来一条消息说："嘿，这很疯狂，但刚发生了一件open AI的事，我想让你看一下。"果然，事件响应里列出的第一件事——虽然确实用到了零日漏洞——但列在第一位的是被盗的凭证。

>> 而它们就是这样被训练出来的。阻力最小的路径。

>> 密码总是第一步，对吧？

>> 完全正确。

<details>
<summary>Original English</summary>

>> Yeah. Yeah. And I think that goes back to sort of the you know the the the pyramid question. So and I think Dylan you were you were hinting at this which is like these are very specialized skills like zero day exploits writing a zero day exploit doing a supply chain attack like these are these are not things that came from nowhere. These are learned behaviors, right? And and and I think what I think we're seeing is we're seeing a a a a process that looks like it's been kind of maybe trained um or or there's a reward structure that's been built on a bunch of these things. Like what's your understanding of how they're figuring this stuff out because it it seems like they know what they're doing like they've been taught to do this. >> Yeah. I mean, if a lab tells you that this is an emergent super intelligence behavior, they're just lying to you. And you can read their own safety reports to see exactly how the models are trained and exactly how they're testing these behaviors. I mean the interesting thing about cyber security in particular is the reward function is incredibly well defined. Get access to the data. Did it get access to the data? Reward the thing. And so when they realize that like the number of problems that have that well-defined reward structure basically defines how we do reinforcement learning and they want to find as many problem spaces that they could do reinforcement learning on. And so it was a prime candidate for them to come in and give it uh CTFs and give it like cyber security challenges where they say, "Okay, get access to this thing and do whatever hacking you need to do to accomplish the goal." And then >> because they've essentially been buying pen testing data for the last four years, right? >> That's that's a piece of it. The other piece of it >> and then the capture the flag contests and all those sorts of things. >> The thing is it's just not difficult to construct a challenge. just you know even if there is no known exploit if we're talking about zero days you put a piece of software between the model and and and some data and you say get access to the data and then you know if it get access if it gets access to the data you reward it and it's that simple. But the other piece that they've layered on top and this is where it starts to get really interesting is they've started to reward the path of least tokens. And so the reason that's interesting is because for the first time it's actually able to quantifiably show us the path of least resistance for just general cyber security to get from A to B. And we've talked about like our opinions of what that is in the past of like of course uh truffle security's biased view is like a password laying around is a shorter path than going through a fancy zero day. But actually watching the model physically get from A to B and watching it follow the password and quantifying how many tokens it took to go this route versus that route. I mean, it's just incredible to watch that lay out. And it's all in their safety reports like as they um test the models out and and show, okay, well, it got access to the data and it broke out of its harness. Um it's it's not like this is emergent behavior specifically. >> That's perfectly logical, right? Like the fastest way to get a gallon of milk is to steal it. >> That's exactly right. [laughter] So, so, um, I mean, what was interesting is we were in the middle of partnering with Hugging Face to clean up all of the credentials that had been exposed through all of their training sets. Not Hugging Faces training, but people who hosted training sets on HuggingFace. They used Truffle Hog for a wide range of reasons. Um, and HuggingFace has been a great partner in getting credentials cleaned up. We targeted their uh, training sets because we knew they had a lot of keys. Turned out there were about a quarter million live keys in their training sets, many of which had direct supply chain implications. There was a foundational Linux library that one of the keys had direct push access to. It could have pushed malware to most machines on the planet. And so, while we were in the middle of doing that, the CTO of HuggingFace shoots me a note and says, "Hey, this is crazy, but there's this open AI thing that just [laughter] happened, and I want you to take a look at And sure enough, the first thing listed out in the incident response, um, although it's true it did utilize zero days, um, but the first thing listed out was stolen credentials. >> Um, and that's that's how they were trained. The path of least resistance. >> Password is a password is always the first step, right? >> That's exactly right.

</details>

### 正在发生的npm蠕虫事件
>> 而你在过去大概18个月里，可以说一直火烧眉毛。我想，就在我们录制这段节目的此刻，一个大型npm仓库正在发生持续的入侵。是不是有什么事在发生？而且不止一个仓库，实际上大概有几百个仓库。

>> 哦，哇。好吧。

>> 对。所以这是一个蠕虫。这是npm恶意软件版图中一种不幸的创新：很长一段时间里，人们一直在谈论npm蠕虫这个概念，就是如果有人给某个包植入后门，然后让开发者去安装，再利用从这些开发者安装时窃取到的访问权限，让蠕虫自我传播，你就可以造出一种迅速接管npm的东西。这些年它一直在博客文章里被传来传去，没有人真的想过去做，直到Zachary想明白了

>> 直到有人想到要去做。

>> 直到有人想到[笑声]要去做，而且实际上

>> 大概用了AI，对吧？

>> 几乎可以肯定。是的。而且，我们有相当充分的理由相信那个恶意软件是vibe coded的。有一个威胁组织实际上把他们vibe coded的工具包开源了，供其他人使用来做这件事。我们已经看到自那以后出现了模仿攻击，

>> 而且恶意软件作者从来都不是很出色的程序员。不知道你是否意识到这一点，对吧？所以如果代码开始看起来更好了，那很可能是vibe coded的，对吧？这跟你通常对vibe coding的看法有点相反。

>> 对。有意思的是，他们常常利用安装在开发者系统上的AI工具走得更远，并绕过一些传统安全工具。我们看到，你本地的CLI工具常常被拉进攻击里，被当作跳板。很多时候载荷其实就是提示词。这会绕过很多典型的EDR工具，因为它就是你的Claude正在运行的一个markdown文件，可能被给了一个提示词，让它搜索整个系统，找出所有不同的密钥和看起来有价值的东西。

>> 我敢肯定你的EDR工具对这种JSON blob和MD文件一无所知，对吧。

>> 对。而且开发者机器本来就在做各种怪事，比如你给Claude下提示词，它一直在你的文件系统上做一大堆事情，所以没有什么看起来特别异常。不过，说说今天早上的攻击吧。几百个软件包，一个蠕虫扩散开来，有一位维护者，老实说他仍在试图弄清楚发生了什么。我们今天早上和他通了电话，想提供帮助。

>> 哦，太好了。太棒了。

>> 我们Socket团队大约一半的人是维护者，工程团队的一半。所以我们在社区里有很多联系，而且我们的CTO是npm的前CTO。所以我们尽可能地向维护者提供帮助，因为我真的很同情他们。他们常常不知道发生了什么。听起来在这个案例里，这仍是推测，还处于早期，我们仍在努力弄清楚，但可能是一个不安全的GitHub action，攻击者得以利用它，最终让自己的代码运行起来，然后从环境中取出令牌。我们仍在确认，但看起来大概是这样。我们在很多这类蠕虫中都见过这种情况。所以他的端点很可能其实没问题，不是问题的一部分。问题其实就出在这个不安全的GitHub action上。

>> 对。真让人着迷。

<details>
<summary>Original English</summary>

>> And you've you've had your hair on fire, I think, pretty substantially for the last like 18 months. Um, I think right now as we're recording this, there's currently an ongoing active breach of of a big mpm repo. Isn't there something happening? It's more than just a repo. It's actually about you know few hundred repos. >> Oh wow. Okay. >> Yeah. So it's it's a worm. And this is one of the things that has been kind of an unfortunate innovation in the in the malware landscape uh on you know npm is that you know for a long time you know people had talked about this concept of an npm worm. You know this idea that you know if I could someone could backdoor a package. Yeah. um and then you know get developers to install that and then you could use the access stolen from those developers as they install it to self-propagate the worm. you could create, you know, something that quickly takes over npm. And this this was kind of in, you know, passed around in blog posts over the years and no one actually kind of thought to do it until Zachary kind of figured it out >> until someone thought to do it. >> Until someone thought [laughter] to do it uh and actually >> probably using AI, right? >> Almost certainly. Yes. Uh there and and and there's been um you know uh that malware I think we have pretty good reason to believe that was vibe coded. Um there's been one of the threat groups actually kind of posted their >> you know open sourced their their kind of vibecoded um toolkit for for others to use to be able to do this. You know we've seen copycat attacks happen since then >> and malware authors were never really great coders. I don't know if you probably realize this, right? So like if the code starts looking better, it's probably vive coded, right? It's sort of the opposite of what you think of vive coding typically. >> Yeah. and they're using they're interesting is they're often using the AI tools that are installed on developer systems to go further and to sort of um sneak through kind of some of the traditional security tooling. So we see you know um basically your local CLI tool often being used you know roped into the attack and you know used as a jumping off point. So a lot of times the payloads are actually prompts. Um and that that bypasses a lot of u you know typical kind of edr tooling because you know it's just like a markdown file that your cloud is running and might be given a prompt to like search through the system and find all the different keys and the things that look valuable. >> I'm sure your EDR tool doesn't know anything about like this JSON blob and an MD file. Right. >> Right. And developer machines typically are doing all kinds of you know weird things like you know you are prompting cloud and is doing a bunch of stuff on your file system all the time and so nothing really looks that out of the ordinary. Um but yeah, so anyway about the attack this morning. Um so a couple hundred packages, you know, a worm spread through there was a maintainer um who um honestly he's still kind of trying to understand what happened. Um we we we jumped on the phone with him this morning to try to offer assistance. >> Oh, that's great. Awesome. >> About half of our team at Socket are maintainers, half the engineering team. Uh and so, you know, we have a lot of connections into the community and our CTO was the former CTO of npm. So we, you know, sort of try to offer help whenever we can to the to the maintainers because I do really feel for, you know, for them. They, you know, they often don't know what happened. I mean, you know, it sounds like in this case it might have been, and this is speculation still early. We're still working to figure it out, but it it might have been a GitHub action that um, you know, was insecure and that an attacker was able to kind of use to uh, ultimately kind of get their code to run and then pull out the token from the environment. We're still kind of confirming this, but that's kind of what it looks like. And we've seen this over over a lot of with a lot of these worms. So his his it's likely his endpoint was actually fine and not part of the problem. It was really just this insecure get of action. >> Yeah. It's fascinating.

</details>

### 凭证窃取、爆炸半径与用户责任
>> 我能就此追问一个问题吗？

>> 可以。

>> 我在npm蠕虫上看到的一点是，它们拿到post install钩子并感染系统之后，会立刻开始寻找凭证。如果找到凭证，就获得下一个系统的访问权。所以我们总是被问到："怎么把凭证从端点上清理掉？"我通常会说，我可以教你怎么扫描下载目录，怎么扫描文档目录，但在你的主目录里，有一个地方是npm有意写入凭证的，也有一个地方是亚马逊有意写入凭证的。这些工具本来就是这么工作的，我其实没什么办法把它们清理掉。即使你把它们迁移到hashior vault或one pass，hashior vault和one pass也是在端点上的。所以我有点好奇第二阶段，不是阻止扩散，而是后渗透这一步。你对如何限制这种爆炸半径，或者防止窃取凭证并跳到下一个系统，有什么建议吗？

>> 对，我是说，社区和生态里已经有了一些变化，一些积极的动向。有一件积极的事，虽然还没有上线，但npm已经宣布，他们计划——我记得是在2027年1月——要求在任何新的发布发生之前，通过2FA进行人工的、交互式的确认。这很可能会彻底终结整个蠕虫这种概念。但这会造成极大的破坏，因为大家都把这些东西接到了自动化上，比如GitHub actions触发发布，所以他们这么做的时候，基本上会让整个生态系统都崩掉。但我认为这是正确的决定。不过也有其他由志愿者运营的生态，没有GitHub和微软做后盾，它们大概不会做这些改变，所以我认为我们仍会看到类似的事情。但是，没错，我们的主目录里不应该有带着长期有效令牌的文件，尤其是如果你是拥有那种访问权限的维护者。这让我想起我的一位朋友。他是一位多产的npm维护者，有一次，那是大概10到5年前的事了，当时我全职做这类事情，我看到他输入密码。我没看到密码，但我看出它太短了。就这么说吧。[笑声]他输得太快了。我当面指出来，我说："你的密码为什么只有六个字母，老兄？"他说，他住在丹麦，那是个信任度很高的社会。他的世界观是，我不想活在恐惧里、去想这些事情。我说："你在互联网上啊，老兄，人们很快就会把这个六个字母的密码弄出来的。"类似的事情有很多：世界上顶尖的维护者不一定受过安全训练，甚至不一定在思考这些事情，他们没有安全团队，没有企业级SLA，对吧，他们是志愿者，只是把代码放在GitHub上。所以我认为，实际上应该由用户去审查他们所用的东西。很难说，我们是一家公司，只是在互联网上找到了这段代码，就直接部署到生产环境，然后这是别人的错。实际上不是的，软件的用户确实有一些责任，要审查他们带进自己环境的制品。所以我认为这里有很多环节，我不想过多责怪别人，因为这是个难题，但是没错，我认为有很多地方我们可以做好事。

我再追问一下，因为你说有些包管理器拥有其他包管理器没有的资源。我想一个直接的例子，而且我丝毫不责怪他们，他们其实很好合作：我们在Ruby Gem中发现了一个缓存问题，让我们可以窃取任意令牌，获得任意账户的访问权，进而可以给任意软件包植入后门。我们向他们披露了，他们很快修好了。但这是一个资源不足的组织的例子。我是说，对于一个正在考虑用什么技术栈、在Ruby和npm之间选择的组织，你怎么看？在这个决定中，是否应该考虑这种资源状况，也许应该考虑背后有安全团队的那个？

>> 很难让人彻底换语言，如果他们已经建立在上面了。所以我不知道这是否很实际。我认为最可行的是，大家应该为这些东西出资。这不需要很多钱，多雇一个、两个、三个、四个、五个安全人员，就能在这些基金会里产生很大的影响。所以我建议大家赞助他们所使用的软件，尤其是注册中心。只需要不多的几家公司拿出25k、50k的支票，就能对这些人产生很大的改变。

>> 或者给他们多一些推理额度，用来跑测试、打补丁，对吧？这挺有意思的。我想你们作为安全从业者，接过不少电话，

>> 有人想跟你们谈，我怎样才能保护我的公司？怎样保护我的业务？怎样保护我的产品？这些对话总是某种形式的：我不想雇人或为此花钱，怎么才能便宜地做到？

<details>
<summary>Original English</summary>

>> Can I ask a follow-up to that? Yeah. >> So one of the things that I've seen with the npm worms in particular is after they get their post install hook and they infect a system, they'll immediately start looking for credentials. And if they find a credential, they get access to the next system. So all the time we get questions saying, "How do we get the credentials cleaned off the endpoints?" And usually what I say is, well, I'll show you how to scan your downloads directory. I'll show you how to scan your documents directory, but in your home directory, there's a place where npm intentionally writes a credential. There's a place where Amazon intentionally writes a credential. And that's just how those tools work. And there's nothing that I can really do to get them cleaned up. Even if you move them over to hashior vault or one pass, the credential, the hashior vault and one pass are on the endpoint. So I'm kind of curious about that second phase beyond like the stopping the spread but the post exploitation step. Do you have any recommendations on how to sort of limit that blast radius or prevent that stealing of credentials and jumping onto the next system? >> Yeah I mean so there's been some changes some positive movement in the community in the ecosystem. So, one thing that is positive and it's it hasn't shipped yet, but npm has announced that they are planning to I think it's in January 2027 going to require uh human you know interactive uh confirmation through 2FA before any new publishes can happen. So, that will likely kind of kill this whole worm concept uh completely. Um but um it's going to be super disruptive because everybody's hooked hooked up this stuff to you know automations so that you know GitHub actions kicks off a publish and so that's going to break like up like the whole basically the whole ecosystem when they do this but I think it's the right call. Um but you know there's other ecosystems that are volunteer run that don't have the backing of GitHub and Microsoft behind them um that are going to you know probably not make those changes and so I think we're still going to see stuff like this. Um but uh but yeah, we shouldn't have we shouldn't have files on our on our you know in our home folders that have tokens in them that are longived and that that let you you know especially if you're a you know a maintainer with that kind of access. Um you know it reminds me of a of a a friend of mine. He was a uh he's a prolific npm maintainer and uh one time you know we were this is back like 105 years ago when I was doing this kind of stuff full-time and I saw him kind of type in his password. I didn't see the password but I saw it was it was far too short. Let's just put it that [laughter] way. It was he typed it in far too quickly. And I was and I and I called him out and I'm like, "Why is your password like six letters, man?" And uh you know, he said, "Well, you know, like he lives in Denmark, which is like a very high trust society." And his his kind of worldview about it was that, you know, well, I don't want to live in fear and think about these things. And I'm like, "You're on the internet, man. Like, you got [laughter] people are gonna, you know, people are going to figure this sixletter password out pretty quickly." And you know um there's a lot of things like that where you know the folks that are the top maintainers in the world don't necessarily have the security training or even thinking about these things and you know they don't have a security team they don't have you know enterprise SLAs's right these are volunteers they're just putting code on GitHub and so it's on actually the users I think that to actually vet what they're using. It's kind of hard to say like, you know, we just we're a company. We just found this code on the internet and we just deployed it straight into prod and and it's, you know, and it's someone else's fault. You know, it's like, no, actually, you know, there's some definitely some responsibility for for the users of of this software to really be to be vetting the artifacts that they're bringing into their environments. And so, I think there's a lot of pieces here and, you know, it's I wouldn't want to um put too much blame on people because it's a hard problem, but uh um but yeah, I think there's like a lot of places where we can do good. Well, let me ask a follow-up to that because you said u there are certain package managers that have resources that other package managers don't. I think one direct example of this and I don't uh cast any blame on them whatsoever. They were actually great to work with. We found a caching issue in Ruby Gem that allowed us to steal arbitrary tokens and get access to arbitrary accounts which we could use to back door arbitrary packages. We disclosed it to them. They got it fixed quick. But that's an example of an organization that's underresourced. I mean, how do you think about an organization that's like thinking about what technology stack to use and they're picking between Ruby or npm? Do you think about that resourcing in that decision of like maybe you maybe you should consider the one that's that's got the security team behind it? >> Uh, it's hard to get people to switch their their language completely because of, you know, if they're already built on it. So, I don't know if that's super practical. I think the most actionable thing is folks should fund this stuff. like it doesn't take much money, you know, to to hire an additional one, two, three, four, five security people that can make a really big difference in these um foundations. Um so I suggest people sponsor the software that they're using, especially the registries. Like it doesn't take very many companies throwing in 25k, 50k checks to really make a big difference for these folks >> or give them some more inference to run the test to do the patches, right? Like no, I mean it's funny. I think you guys as being security practitioners, you've had number of calls with people >> that want to talk to you about what how can I secure my company? How can I secure my business? How can I secure my product? And those conversations are always some form of I don't want to hire people or pay money for this and how do I do it cheaply?

</details>

### 大会氛围与2026年的供应链
>> 对。谢谢你们来到沙漠。你们显然不是来看我们的，我们都是为Black Hat而来。我知道这不是你们任何一位第一次来这里，当然也不是我第一次。想听听你们的看法，你们看到了什么？氛围怎么样？有什么有意思的事？有什么观察吸引了你们的眼球？至少对我们Socket来说，我认为我们看到的最大的事情是，2026年是软件供应链之年，

>> 而且[笑声]你们此刻正在处理一起事件，而大会正在进行。

>> 是的。我还注意到，攻击者似乎选了RSA和Black Hat作为他们想要发起这些npm蠕虫的时间。

>> 黑客，办公室里的那些安全人员。对。

>> 对。绝对是。所以我认为这是最大的事情。我认为往年我不得不教育大家。我们一直在就这个问题教育大家，不得不向他们解释，这不是理论上的风险，这是可以发生的。我们有时会得到这样的反应："哦，是的，但这到底有多大可能？"我们就说："不，实际上可能性非常高。让我告诉你它是怎么发生的。"有很多事件可以举例，但我认为

>> 今年它真的突破到了主流，有主流出版物，商业媒体在报道这些攻击，对吧？

>> 就像Bloomberg上的storm page。

>> 对。对。没错。所以我认为这非常非常好，因为你需要这种掩护，让安全团队真正能给这些问题排优先级、找预算。所以我认为，尽管这些攻击现在处理起来非常痛苦，但最终我们会因此变得非常强大，因为我们实际上会

>> 拿到预算，今年我们在解决问题方面会做很多好事。

>> 这确实是一种接种疫苗。你呢？

>> 是的，你看，我们最近发现了一个数据库凭证，它能访问全球3.6%的PII。也就是世界3.6%人口的PII在这个数据库里。我们发现它，是因为我们正在与Hugging Face这样的组织合作，把它们平台上那些有效的凭证全部撤销、清理掉。所以很高兴看到这类组织积极参与，以及所有从这些地方被抓取的数据，创造了一个中心位置，让我们可以扫描并取得实质性进展。所以我认为在密钥方面，我们正看到老一代，比如Hashi Corp被收购、Cyber Art被收购，逐渐被挤出，这引发了一场关于非人类身份和密钥的新对话：怎么让它们更易于使用，怎么让它们被撤销，怎么真正推动行业向前，这是在旧势力之下我们以前做不到的。

>> 对，绝对是。我能想象会有一个倍增效应：过去是一个用户有10个密码，现在你会有10个智能体、每个有10个密码，对吧？

>> 我是说，智能体目前与密钥交互的方式是一个蛮荒西部式的、未解决的问题，我们正在非常努力地解决。

>> 众多问题之一。谢谢二位和我一起聊。真是太棒了，很高兴叙叙旧。

>> 谢谢，Joel。谢谢。

>> 保重，Joel。

>> 太棒了。

<details>
<summary>Original English</summary>

>> Yeah. So, um, thank you guys for coming out to the desert. Um, you're not here to see us, obviously. We're all here for Black Hat. Um, would love, you know, I know that this is neither of your first times here. Um, certainly not my first time here. Would maybe love to get your guys' takes on what you're seeing. What's the What's the mood like? What's what's interesting? What are the observation you've got that are catching your eyes? Uh I mean at least for for us at socket I think the biggest thing we're seeing is that 2026 is the year of the software supply chain >> that [laughter] you're dealing with an incident right now as the conference is happening. >> Yes. And I noticed the attackers seem to pick RSA and black hat as the times they wanted to start these npm worms. >> The hacker the the security guys around the office. Yeah. >> Yeah. Absolutely. So I think that's that's the thing that's the biggest you know I think you know prior years I was having to educate people. We were you know always educating people about this problem and having to explain to them you know this is not a theoretical risk like this can happen. And we'd sometimes get these reactions like, "Oh, yeah, but like how how likely is it really?" And we're like, "No, it's actually very likely. Let me tell you how it could happen." And and you know, there were many incidents to point to, but I think >> this year it's really broken through into the mainstream and there's like mainstream publications, you know, um the business press covering these attacks, right? >> It's like storm page on Bloomberg. >> Yeah. Yeah. Exactly. So I think that is um you know that is very very good because you need that type of you know air cover for like security teams to actually prioritize and and find budget for these problems. And so I think, you know, despite all these attacks being very uh, you know, painful to deal with right now, I think in the end we're going to come out really strong from this because we're actually going to >> going to get budget and we're going to get um, you know, we're going to do a lot of good this year in terms of solving. >> It's inoculation for sure. How about you? >> Yeah, I mean, look, we found a database credential recently that had access to 3.6% of the global PII. Like 3.6% 6% of the world's population had their PII in this database. And the reason we found it is because we're partnering with organizations like HuggingFace to just get all the live credentials revoked and cleaned up that are otherwise on their platforms. So, it's great to see those types of organizations leaning in and like all of the data that's being scraped from all these places. It creates really a central place where we can scan and make material progress. And so I think like when it comes to secrets, we're kind of seeing the older generation like Hashi Corp got acquired, Cyber Art got acquired, kind of get pushed out, which has sort of led to a new conversation about non-human identity and secrets about how can we make them easier to use, how can we get them revoked, and how can we really move the needle forward with the industry that we weren't able to do before under sort of the old guard. >> Yeah, absolutely. And I can imagine that there's going to be a multiplication effect, which is it used to be one user with 10 passwords and now you're going to have 10 agents with 10 passwords, right? >> I mean, the way agents interact with secrets right now is a wild west unsolved problem that we're working very hard to solve. >> One of many issues. Thank you, gentlemen, for joining me. This has been awesome. It's great to catch up. >> Thanks, Joel. Thank you. >> Be here Joel. >> Awesome.

</details>