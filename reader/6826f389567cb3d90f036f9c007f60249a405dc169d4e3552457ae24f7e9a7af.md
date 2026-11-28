---
author: a16z
date: '2026-11-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=PbD9pVXxsYM
speaker: a16z
tags:
  - cybersecurity
  - ai-agent
  - vulnerability
  - zero-day
  - cloud-security
title: 网络攻击曾需耗时数月，AI能在几分钟内完成：黑色十月与Agent攻击新纪元
summary: Wiz联合创始人Ammy等讨论了2026年被称为“黑色十月”的AI安全危机。开源与前沿AI模型使漏洞挖掘与利用压缩至约20分钟，攻击者正大规模针对初创企业与公共基础设施。防御重心须从传统代码扫描转向基于流水线的外部暴露面持续测试与安全架构设计。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ammy
  - Elon Musk
companies_orgs:
  - Wiz
  - OpenAI
  - Google DeepMind
products_models:
  - PHP
  - Windows XP
media_books: []
status: evergreen
---
### 序言：AI攻击浪潮与安全范式的重置

**>>**: 我们正在重回90年代和2000年代。我们又要看到数据泄露事件频繁爆发了。现在的局面将与过去15年的安全状况大不相同。
<details><summary>Original English</summary>
**>>**: We're going back to the 90s and 2000s again. We're going to see breaches popping out all the time again. Now, it's going to look very different than the last 15 years of security.
</details>

**>>**: AI攻击者正在以我们从未见过的规模和速度，真正向企业和初创公司发起攻击。
<details><summary>Original English</summary>
**>>**: AI attackers that are actually going after companies, startups in scale and speed that we've never seen.
</details>

**>>**: 埃隆·马斯克最近发推说，每一天都是零日漏洞日。AI究竟做了什么促成了这一切？
<details><summary>Original English</summary>
**>>**: Elon Musk tweeted that recently. Every day is zero day. What is AI doing to make this happen?
</details>

**>>**: 模型现在的能力已经足以发现并利用复杂的漏洞。另一方面是开源模型——那才是令人恐惧的部分。几个月前，我们说过距离开源模型赶上来还有几个月时间。现在，它们正在赶上来。
<details><summary>Original English</summary>
**>>**: Moders are good enough now to find and exploit complex vulnerabilities. And the other is that the open source models, that's the scary bit. A few months ago, we said we have a few months until open source models catch up. So now they're catching up.
</details>

**>>**: 安全博弈刚刚发生了改变。你现在需要考虑的是，如何让蓝方和红方的绝大部分工作实现自动化。目前安全团队做的大多数事情根本不是安全。我们应该停止手头做的大多数事情，集中精力去发现关键风险，弄清楚如何缓解风险，或者至少部署好检测机制，并做好应急响应准备。
<details><summary>Original English</summary>
**>>**: The security game has just changed. You need to be thinking about how you can automate so much of both the blue side and the red side. Right now most of what security teams do is not security. We should stop doing most of what we do and focus on finding critical risk, figuring out how we mitigate it or at least put detections in and also response readiness for it.
</details>

**>>**: 你认为未来几年会是什么样子？AI攻击不仅普遍、容易发起，而且比任何人类都更厉害。这才是问题所在。唯一能够生存下来的公司，只有那些……
<details><summary>Original English</summary>
**>>**: What do you think the next several years looks like? AI attacks are prevalent, easy, but also better than any human. That's the problem. The only companies that will be able to survive are companies that are
</details>

### 黑色十月与攻击速度的坍缩

**>>**: Ammy，非常感谢你的加入。安全专业人士把十月称为“黑色十月”，很显然我们正在进入一个智能体攻击（agentic attacks）的新时代。在开始时，能否请你为我们梳理一下，眼下到底发生了什么，我们又该如何度过这个关键时刻？
<details><summary>Original English</summary>
**>>**: Ammy, thank you so much for joining us. Security professionals are calling October Black October and um it's clear that we're entering a new era of agentic attacks. Um, can you just to start off walk us through what the heck is going on right now and how do we get through this critical moment?
</details>

**>>**: 好的。首先，很高兴能来这里。我们把这称为“黑色十月”，因为在我看来，这就像是一场黑天鹅事件。我们从未见过在单个月份内发生如此多的安全事件。而且我们讨论的是多种不同类型的安全事件：既包括十月份发现的漏洞数量，也包括这些漏洞的严重程度——其中包括PHP漏洞，这可能是AI发现的最严重的漏洞。漏洞正以我们前所未见的速度涌现；但在另一方面，甚至更糟糕的是，我们看到了AI攻击的兴起。AI攻击者正在展现出我们以前从未见过的全新速度与专业能力，正以我们前所未见的规模和速度针对企业、初创公司和冷藏设备发起攻击。
<details><summary>Original English</summary>
**>>**: Yes. So, uh, first of all, great to be here. Um, we are calling this Black October uh since uh it's a in my view like a black swan event. H we've never seen never ever seen so many um security incidents happen in a single month. Um and we are talking about multiple different types of security incidents uh both uh the number of vulnerabilities that has been found in October and the severity of those vulnerabilities including the PHP vulnerability probably the most severe vulnerability ever found by AI right so vulnerabilities coming in a rate that we've never seen but on the other hand even worse we're seeing the the rise of AI attacks right so AI attackers that are using completely new speed expertise that we've never seen before. Actually going after um companies, startups, refrigerators in in in scale and speed that we've never seen.
</details>

**>>**: 是的。正如你指出的那样，令人害怕的一点在于速度——你们在博客中也谈到过一些。而且我认为你甚至私下跟我们说过，公开场合大概也表达过：每一天都是零日漏洞日。埃隆·马斯克最近也发了这条推文。能否多谈谈AI是如何做到这一点的？它是通过什么机制来加速编写漏洞利用程序的？我想你们实际上围绕这个做过一些工作，发现它把时间从数月压缩到了数周。能多谈谈这是如何运作的吗？还有针对本期播客的受众，创始人应该思考什么、做些什么？
<details><summary>Original English</summary>
**>>**: Yeah. And I I mean the the scary thing about that to your point is um and you guys cover some of this in your in your blog as well the the speed and um you know I think you've even said definitely to us privately but probably publicly as well that every day is zero day right um Elon Musk tweeted that recently um just say more what is AI doing to make this happen like what is the mechanism that um it's able to speed um writing exploits Uh I think you guys actually did some work around this um where you found it collapsed the timing from months to weeks. Um say more about how that works and um you know I think your point on uh the the audience for for this podcast right what should founders be thinking about and doing.
</details>

**>>**: 如果我们回顾一下我们是如何走到这一步的，直到十月之前，有两个主要时刻。一个时刻是Mitos时刻，Mitos出来宣称：“天哪，我们可以发现漏洞了。”好的，那是一个时刻。但当时什么也没发生，虽然我们喊着“天哪，它要来了”，但大家依然会说：“好吧，太阳照常升起。”我们经历的另一个重大时刻……
<details><summary>Original English</summary>
**>>**: So if we think how we got here right so there two major moments until October. fun was the the Mitos moment where Mitos came out and said, "Oh my god, we can find vulnerabilities." Okay, that was one moment. But again, nothing happened, you know, like we said, "Oh my god, it's coming." But we still had a like like people say, "Okay, h okay, what still the world, you know, the sun is still rising." The other big moment that we had
</details>

**>>**: 是Hugging Face与OpenAI的相关事件，对吧？那是另一个重大事件，让我们看到了AI攻击的风险，但那依然是意外发生的攻击。
<details><summary>Original English</summary>
**>>**: was the hacking face incident with OpenAI, right? So these are that was another major incident that we saw the risk of AI attacks but again it was accidental attacks.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Y
</details>

**>>**: 如今在黑色十月发生的事情是，所有那些潜在的理论推演、我们曾说过即将到来的东西，全部降临并猛烈冲击着我们，而且现在正在发生。一方面，模型现在的能力已经足以发现并利用复杂的漏洞，这意味着这不再只是理论，它正在发生，漏洞正在爆发。另一方面是开源模型，那才是令人恐惧的部分。几个月前当我们谈论Mitos时就说过，我们还有几个月时间，几个月后开源模型就会赶上来。现在，它们正在赶上来。
<details><summary>Original English</summary>
**>>**: what happened now in black October is that all of those potential theories the the things that we said are coming they all came and crashed upon us and it's happening right now. Right. So one is that the models are good enough now to find and exploit complex vulnerabilities. Right? So, and that means that this is not a theory anymore. It's it's happening. It's an explosion of vulnerabilities. And the other is that the open source models, right? That's the scary bit. And we said it when we spoke about Mitos a few months ago, we said we have a few months, a few months until open source models catch up. Okay? So, now they're catching up.
</details>

**>>**: 它们正在赶上来。这意味着现在不仅仅关乎漏洞，它们能够在你的环境中寻找运行代码的方法。甚至不需要是复杂的PHP漏洞，可能只是你的API中的一个小错误。它们能够发现并利用你代码中的这些零日漏洞，基本上只需大约20分钟，就能跑完整套通常需要最顶尖攻击者花费数周或数月的完整攻击流程。这就是我们现在看到的现状。
<details><summary>Original English</summary>
**>>**: They're catching up. It means that now it's not just about vulnerabilities. They're able to find ways to run code on your environment. doesn't have to be a complex PHP for a bit. It can be just a mistake in your API, right? They can find and utilize those zero days in your code, right? And basically run an entire attack that usually took for the best attackers weeks or months in again around 20 minutes. That's what we're seeing now. So,
</details>

**>>**: 在你看来，开源模型到底落后多少？当我们在攻击能力层面与业内交流时，差距往往在六到九个月左右，但在目前这个节点上已经足够接近了。我很好奇你观察到了什么。
<details><summary>Original English</summary>
**>>**: how far behind have you seen the uh the open source models? I mean, like when we're chatting with folks on the on like the offensive capability side, it tends to be about like six to nine months or so, but that's close enough uh now at this point. But I'm I'm curious what you've seen.
</details>

**>>**: 这里有两个不同的问题。一是在进攻端寻找漏洞方面，我们是否比开源模型更领先？也许我们领先大概三个月，最多不超过三个月。问题在于进攻端的实际攻击。如果我是一家公司，哪怕只是一家初创公司，我们谈论的是一波攻击浪潮。如果仅看看AI开发平台提供商：我们曾发过一篇博客，起初博客里记录了十月份遭到攻击的9家公司，名单每天都在增加，现在已经到了15家。
<details><summary>Original English</summary>
**>>**: There's two different questions. One is um okay, on the offensive side, right, to find a vulnerability is are we better than the open source models? Yeah, maybe we have like three months of it's not more than three months, right? The problem is that the the is the offensive side on attacking. Okay, because I I'm a company. It doesn't matter. Let's say it's a startup. Okay, and again we are talking about a wave of attacks. If we just look at AI development providers, right? We had a blog about like we've seen initially the blog had nine companies attacked in October and the list is growing every day like we're now on 15.
</details>

**>>**: 哇。
<details><summary>Original English</summary>
**>>**: Wow.
</details>

**>>**: 这只是一个细分市场的例子，比如AI开发平台。它们现在成为特定目标，是因为它们拥有AI密钥。一个攻击者——甚至不需要是多么老练的攻击者——可以使用AI；开源模型已经足够好，可以在大约20分钟内发现并利用你代码中的问题。试想一下，哪家初创公司做好了检测这些攻击的准备？我不知道，更别说及时发现并做出响应了。这需要每家小型初创公司都配备一个7×24小时的SOC。
<details><summary>Original English</summary>
**>>**: So like a it's just an example of one market, right? Like AI development platforms. Okay, these are getting targeted specifically now because they have AI keys, right? Uh the fact that an attacker, it doesn't have to be a sophisticated attacker, can use AI, open source models are good enough to find problems in your code and and the big problem is to also use them in a matter of 20 minutes. So think about it which startup is ready for detecting those attacks I don't know and then actually finding them and responding them like in time right like it's a you need a 247 sock in every small startup
</details>

### PHP到Shell案例与补丁困境

**>>**: 对。我们不妨把PHP到Shell作为一个案例来聊聊，这是黑色十月出现的众多案例之一。你能否谈谈在你们的客户群中，这个问题的普遍程度如何？而且现在事情已经过去了几周，非常好奇你如何看待客户群体的实际打补丁情况，在它暴露几周后的今天，现状究竟如何？
<details><summary>Original English</summary>
**>>**: right let why don't we talk for a second on PHP to shell as a as an example of just a case study of one of the many that came out during uh black october here um can you talk a little bit about just how prevalent you saw this across your customer base. But then now that we're actually a couple weeks out, uh really curious your take on how has patching actually been across the customer case uh across the customer base, excuse me, and what are kind of the state of things a few weeks out now that we've had a few weeks of seeing uh it be out there.
</details>

**>>**: PHP作为面向外部的技术，也许是最普遍的技术之一，对吧？
<details><summary>Original English</summary>
**>>**: So PHP is a maybe one of the most prevalent technologies as an external facing technology,
</details>

**>>**: 对，作为一家PHP电商系统公司的前CISO，确实如此。
<details><summary>Original English</summary>
**>>**: right? Oh, yeah. A former CISO of a PHP uh e-commerce company. Yes.
</details>

**>>**: 他们不是说它覆盖了互联网的大约70%吗？
<details><summary>Original English</summary>
**>>**: Are they saying it's like 70% of the internet or something?
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 没错。
<details><summary>Original English</summary>
**>>**: Yeah. Exactly.
</details>

**>>**: 确实如此。所以影响是显而易见的，我们几乎100%的客户都在运行某些PHP。我们看到漏洞暴露后迅速出现了大幅下降。客户虽然我不会说他们已经实现了自动化修补，但他们非常清楚修补的重要性。在前两三天内就完成了50%的补丁修补，几乎是立竿见影的下降。但问题依然在于，它构成了互联网的70%。
<details><summary>Original English</summary>
**>>**: Exactly. So you know you know the the impact is basically almost 100% of our customers had the some some PHP running right. We so we saw a major drop very quickly. So customers are now um I wouldn't say they have automated patching yet but they're very very aware of the importance of of um of patching. So I'm talking about 50% patching within the first 2 three days, right? So like
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 但即便只是这一个漏洞，直到彻底解决也需要数年时间。我们在互联网和客户环境中看到过很多很多情况，他们根本没有任何办法修补，因为旧版本的PHP甚至都不再接收补丁了。
<details><summary>Original English</summary>
**>>**: almost immediate reduction but still the problem is that this is 70% of the internet. So exactly this even just this single vulnerability is going to take years okay until it's resolved. And there is many many many cases that we see both on the internet and also customer environments that they don't have any way to pitch. Okay. uh uh because older versions of PHP are not even getting a pitch. Yeah.
</details>

**>>**: 我能问一个宏观问题吗？我们的两位合伙人写了一篇关于编写漏洞利用程序与打补丁所需时间对比的出色文章。现在有很多讨论提到，AI让把补丁差异转化成可用的漏洞利用程序变得更便宜、更容易，数据也显示这个时间在不断缩短。但在另一方面，数据显示打补丁的时间实际上并没有缩短；如果你看过去20到25年的数据，它反而增加了。Ammy，AI在这方面也能提供帮助吗，还是说现在还为时尚早？
<details><summary>Original English</summary>
**>>**: Um can I ask a just a a meta question here? Um and uh one of our two of our partners wrote this great piece on um time for writing exploits versus patching. Um and you know there's a lot of dialogue out there about how AI has made it just cheaper, easier to turn a patch diff um you know into a working exploit. Um and there's sort of some data on just sort of that time falling. Um on the other hand, it seems actually that the data showing um time to patch actually hasn't gone down. Um in fact, it's gone up if you look at the data over the last 20 25 years. Um can AI help with that side as well, Ammy, or is it still early days?
</details>

**>>**: 首先，你说得对，获得漏洞利用程序的时间大幅缩短了。情况甚至更糟，因为很多时候信息在CVE正式发布之前就已经泄露了；很多时候即便CVE发布了，补丁却还没出来。在PHP案例中，我们与PHP团队合作了数月以让整个行业做好准备，但它提前泄露了。客户根本无能为力。Linux中的补丁尚未就绪；现在即使向Linux内核报告了一个漏洞，可能也需要数周甚至数月才能推送覆盖到所有的发行版。因此整个行业总体上根本没有做好准备。即使你能在内部快速修补，在补丁到达你的发行版之前也是不顶用的。AI能在几分钟内完成漏洞利用，所以答案是全世界都还没有准备好，这是一个严峻的问题。

在修补方面，你说得对，我们目前还不知道究竟如何实现自动修补，坦白讲我还没有看到通向那一步的明确路径。口头上说“让我们把一切自动化”很容易，但在现实中，如果你现在从头创建一家新公司，你是可以做到的：如果你建立了一家拥有自动化工程、自动化CI/CD和自动化测试的新公司，你基本上可以做到当我说“修补这个”时，你的整个系统就能自动完成修补。我认为对于新公司来说，你应该在设计系统时就让它具备自动修补能力。但为了做到这一点，你需要为所有环节建立完整的智能体流水线：你需要自动化开发能力，能够接收一个工单并通过自动化开发创建补丁；然后你需要自动化测试、自动化CI/CD和自动化DevOps。没有多少传统公司拥有这一切，对于它们的大多数代码来说这甚至是不现实的。但对于初创公司而言，这也许是可能的；如果你正在起步或规划，我认为应该把这当作一项核心任务。
<details><summary>Original English</summary>
**>>**: So first of all, you're right. the the time to h to to to get an exploit dramatically went down. It's even worse um because many times the information leaks before the CV even is out. Okay. Many times even the CV is out the patch is not out. Okay. Uh in the PHP case we worked for months with PHP to get the entire industry ready and it leaked before a time right. So the customer doesn't have anything to do h the patch is not ready in Linux right now even if there is a vulnerability reported to Linux kernel it might take weeks or even months until it reaches all of the uh distros right so the industry in general is not ready for like there even if you can patch internally quickly sometimes until a patch gets to your distribution okay it's not ready for for AI right AI can exploit things in in in minutes. So the answer is that the world is not ready. The world is not ready for this. Like it's a it's a problem. In terms of pedaging, you're right. Like uh we don't yet exactly know how to automatically patch and I honestly um I don't see a path towards that. Uh it's easy to say yes, let's automate everything. In reality, if you are building now a new company, you can do it, right? If you're building a new company and you have automated engineering and automated CI/CD and automated testing, right? You can basically be at a position where I tell you patch this and your entire system can automatically do it. And I think for new companies, you should design your system to be able to auto patch, right? But in order to do that, you need an entire anentic pipeline for everything, right? You have automated dev. So you need the ability to take a ticket and have an automated dev to create the patch. Fine. Then you need automated testing, automated CI/CD and automated DevOps. There's not a lot of legacy companies that have all of that and it's not even realistic for most of their code. But for startups, maybe it's possible and I would consider this a an a a task for startups if you start or plan this, you know.
</details>

### 攻击侧机制与多模型流水线

**>>**: 是的，完全赞同。我很想深入探讨一下进攻端的情况。回顾这个发现过程，这里有一个有趣的注脚：这是一个由Wiz和Califf两个团队围绕PHP到Shell细节独立发现的漏洞，这种现象在过去经常发生。不过我很想了解你们的研究团队在发现该漏洞时是如何利用AI的，能否更深入地谈谈它是如何赋能漏洞研究团队的？
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. I I'm curious to just dive in real quick on the a little bit deeper on the offensive side. Um so going through kind of the discovery of this, it was funny a little bit of a footnote here, but um this was a vulnerability that was independently discovered by two groups, Whiz and Califf, uh around kind of the details of the the PHP to shell van, which is a thing that used to happen a bunch back in the day. I'm curious though for your research team, how were they really leveraging AI in terms of discovering this and and just going a little bit deeper on how it's really unlocking vulnerability research teams?
</details>

**>>**: 有几点。首先，我认为这种情况现在会发生得越来越频繁，因为每次出现新模型，都会带来新能力。
<details><summary>Original English</summary>
**>>**: So a few things first of all I think this will actually happen much much much more now because every time there is a new model there's new capabilities.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 我把它看作类似于比特币挖矿。虽然漏洞的数量可能会减少，但因为像比特币一样，总会有更多未被挖掘的，新模型能够揭示出更多的漏洞。所以当新模型出现，多个团队同时发现新的漏洞，这并不令人奇怪。顺便说一句，我们现在正在筹备Wiz的ZDC（零日漏洞大赛），我们收到了针对一个非常关键漏洞的多份报告，我相信这也会对互联网产生重大影响，而这个漏洞正被多个团队同时报告。
<details><summary>Original English</summary>
**>>**: Again I I look at it like Bitcoin mining. Okay. like [laughter] number of vulnerabilities uh will go down but because it's like Bitcoin there's always more and the new models can uncover uh more uh vulnerabilities right so it's not surprising that there is a there's a new model okay and there multiple teams find new vulnerabilities right exactly because and and by the right now we are getting ready for ZDC the the zero day con competition of wiz and And we're we are seeing we we're getting multiple multiple reports on a very very critical vulnerability that is also I believe is going to be a major impact on the internet and this vulnerability is being reported by multiple teams.
</details>

**>>**: 是的，没错。[笑]
<details><summary>Original English</summary>
**>>**: Yeah. Right. [laughter]
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 令人惊叹的是，在当下的安全行业中，所有陈旧的东西又以某种全新的方式重现了。[笑]
<details><summary>Original English</summary>
**>>**: It's a it's amazing how it brings everything old is kind of new again in the security industry [laughter] right now.
</details>

**>>**: 没错，你说得对。在内部，我们的漏洞团队为Wiz产品构建了一个名为Atlas的基础设施，用于漏洞检测。我们一直在结合不同的模型使用它，因为无论是OpenAI、Google还是其他厂商，每个模型都有其独特的能力，我们尝试利用所有这些模型并竭尽所能去挖掘漏洞。但关键在于所有人都在做这件事，所以你可以预料到许多团队会同时发现漏洞。重要的是，我们必须利用那些拥有数月先发优势的前沿AI模型，聚焦于关键基础设施，并在这些领域持续进行检测，确保抢在攻击者之前发现漏洞。但世界上的代码量太庞大了，这依然无法解决全部问题，因为攻击者依然会在我们未关注的领域发现漏洞。
<details><summary>Original English</summary>
**>>**: Yes, you're right. Internally our vulnerability team we built basically also for the wheels product we built a what we call atlas which is a harness for vulnerability detection right h so we're using that with different models all the time because every model has its own uh unique capabilities from from from openai or or google or carbon like each of them has its own capabilities we're trying to use all of them and and find whatever we can but the point is that everyone are doing it so you would expect a lot of teams to find vulnerabilities at the same time and we and that's the important thing we have to focus on infrastructure that is critical using the models of the frontier AI that have a few months right of advantage and we have to continuously do that do that on those areas to make sure that we find it before attackers but there's so much code in the world that it doesn't help because there will still be vulnerabilities that attackers find on on a motor that we you know an error that we they looking to
</details>

**>>**: 我不想让我们陷入过多关于前沿模型的深究，但就你刚才提到的结合多种模型、各模型擅长不同领域这一点，在你能透露的范围内，我很想深入了解两点：第一，在宏观层面上，不同模型各自更擅长什么？第二，如今Wiz已经是Google大家庭的一员，你手头拥有DeepMind团队及其模型，但听起来你依然在使用多个模型。在这个时代，你如何看待前沿实验室与独立网络安全公司之间的关系？
<details><summary>Original English</summary>
**>>**: I don't want to take us down a a frontier model rabbit hole too too much but um just to probe a little bit on what you said about um using multiple models and um each one being good at different things um to the extent you can share on me I'm curious um about two points there one is um what are different models better at um at a high level and then two how do you see I mean you know obviously uh whiz um is a part of the Google family now. Um, and so you have uh the DeepMind team and and their models at your fingertips, but it sounds like you are using multiple models. Um, how do you think about the sort of relationship between Frontier Labs and independent cyber companies um in this day and age?
</details>

**>>**: 我认为每个模型以及每个模型的每个版本都有所不同。现在情况变得更加复杂了，因为你既有通用前沿模型，又有这些模型的网安特化版本，每一个模型……
<details><summary>Original English</summary>
**>>**: So I I I think that every model and also every version of every model, right? And now it's getting complicated because you have the frontier models and you have the cyber versions of those models and each of them [laughter] has
</details>

**>>**: [吸气]
<details><summary>Original English</summary>
**>>**: [gasps]
</details>

**>>**: 这是一个复杂的矩阵。但重点是它们每个的表现都不同，速度和成本也各异。所以没有唯一的答案，这就是我的核心观点。无论你是要处理网络安全任务，还是其他领域的任务，作为一家独立公司，你唯一能做的就是持续尝试所有模型，找到最佳组合。

人们常说“用AI进行开发变得很容易”，对于大多数创始人而言这并非事实。现在的关键在于服务的成本。创建可扩展服务的唯一途径，就是构建一个极其智能的流水线：用特定模型完成部分任务，用其他模型完成更复杂的任务，并将它们以非常高效的方式融合在一起。否则，你的销售环节就会亏钱。举个例子，在蓝方，我们有负责调查攻击的Blue Agent。我不可能对每个事件都运行最先进、最昂贵的模型；但我可以设计一个流水线：先从确定性检测开始，接着经过便宜的模型检测，再经过更高级的模型；如果所有这些模型都判定为恶意，我才会调用最先进的模型在告知客户前最终定性是否真的恶意。因此你需要多种类型、多个模型并设计流水线，我认为这才是创始人及构建规模化AI系统公司的全新工程挑战。
<details><summary>Original English</summary>
**>>**: It's a complicated matrix, right? But the point is that each of them does behave differently and has a different um speed and cost, right? So there is no single answer that like that's my point. Like if you want to um do a task, it's for cyber, but it's true for other stuff as well. The only thing you can do as an independent company is to try all the models all the time and to find the best combination. Right? The way I see it is that you know people say oh now it's easy to develop using AI it's not true for most founders right now the the key is going to be uh the cost the cost of the service right and the only way to create a scalable service is by creating a very very intelligent pipeline there where you do some of the tasks with specific models and some of the more complicated tasks with other models and you mesh all of them together in a very very efficient way otherwise you're you're you're going to lose money on on your sales, right? So, as an example, right, on the we have what we call the blue agent which investigates attacks, right? I cannot run the most a advanced expensive model on every event, right? But I can create a pipeline where you start from a deterministic detection, then you go through a a cheap model detection, then you go through a more advanced model. And if I if I if all of them think it's malicious, I will say to the most advanced model to determine is it really malicious before I tell the customer. You see like
</details>

### 持续测试与防御成本的权衡

**>>**: 也就是说你需要多个模型、多种类型的模型，并且必须设计好流水线。我认为这确实是创立公司、大规模构建AI系统所面临的全新工程挑战。
<details><summary>Original English</summary>
**>>**: so you need multiple models, multiple types of models and you have to design pipelines and I think that is really the new engineering challenge for for for founders for companies building AI systems at scale.
</details>

**>>**: 确实如此。关于成本这一点，你在写的一篇博客文章里也有所提及。你能否总结一下围绕持续测试所必须发生的范式转变？重点在于“持续”而非“静态”，成本显然在能否让每家公司、而不只是最赚钱和最老练的公司都能普及这一能力上扮演着重要角色。从成本角度看，我们距离实现这一目标还有多远？还需要发生哪些变化，比如文化转变、工具链转变？企业需要走向何方，我们今天又处于什么阶段？
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. And and just um on this cost point, you talk about in I think a blog post that you guys wrote, but maybe summarize a little bit here this paradigm shift that needs to happen around continuous testing, right? So sort of the the focus being on the word continuous versus um static uh and cost obviously plays a big role in um you know sort of the democratization of uh every company being able to do that, not just the sort of most profitable and sophisticated. um how far are we from getting there on a cost uh from a cost perspective and what what else I guess needs to happen maybe it's also cultural shift etc like you know tooling shift um but how how far are we from I think I guess where do we where do you think companies need to go and how far are we today
</details>

**>>**: 这是一个宏大的问题。以安全为例，回到Mitos时刻：人们会说“天哪，有Mitos了，我必须把所有代码扫描一遍”。好的，假设你做了，假设你在四月份做了这件事，你可能白白浪费了500万美元。这是真实的数字，你可能浪费了巨额资金，这在目前是非常昂贵的。现在又出了Mitos 1.2，你又重新做一遍。这涉及的不是小数目，某些客户目前在扫描代码上花费了数千万美元。你必须考虑构建一个可扩展的系统，一个智能的持续扫描系统，绝不能盲目蛮干。因为未来会有新模型、新能力和新代码出现。

我们认为这是整个行业面临的重大挑战，我们正在努力解决，但我不会宣称我们已经攻克了它。挑战在于：我如何明智地使用预算，从内部和外部全面扫描？我们有主动攻击，有被动攻击，有代码分析，可以扫描磁盘本身，也可以观察运行时。我该如何以对客户最高效的方式使用全部预算，不是作为单次扫描，而是作为持续扫描来运行？这正是目前安全扫描的挑战所在。如果我告诉你“直接拿大模型去扫代码吧”，你确实可以这么做，但这能否持续解决你的问题？不能，这只会让你的预算出现一个巨大的窟窿。
<details><summary>Original English</summary>
**>>**: so I mean first of all it's a it's it's it's a big question like let's take security for example go back to the bentos moment Right? So people say, "Oh my god, there's Mitos. I have to scan all of my code." Okay, fine. Let's say you did it. Let's say you did it in in April. Okay, you might have wasted $5 million. Okay, [laughter] these are real numbers that you could you've wasted a lot of. It's very expensive now. Okay, now there's meters 1.2. You do it again. Like like this is not like this is I'm not talking about small budgets. I'm talking about I I'm some customers are spending now tens of millions of dollars on like scanning code like you like you have to think about a scalable system right continuous system that scans but is intelligent you can't just so because there's going to be new models new capabilities new code right so we see this as a major challenge for the industry we're trying to figure it out I'm not going to tell you that we solved it right but the challenge is how do I use the budget wisely in in a way scans from the inside, from the outside. We have active attacks, we have passive attacks, we have code analysis, we can scan, we on the on the disk itself, we can look at the runtime. How do I use all of the budget in a in the most efficient way for the customer, not as a single scan, but as a continuous scan, right? And that is the challenge of security scanning right now. If I tell you, oh yeah, just run mess on your code. Great. You're right. You can do that. But does that does that actually solve your problem continuously? No, it's just going to get you like a big hole in the in the budget.
</details>

**>>**: 感觉大家单纯讨论前AI时代的云安全已经像是上辈子的事了。但对于安全团队、CISO和安全工程师来说，新问题的出现并不意味着老问题就消失了。对于很多财富500强和全球2000强企业来说，他们仍在应对大量的云安全挑战。这个问题的第一个部分，我们先暂且搁置AI，能否谈谈2026年云采用与云安全的现状？第二部分，我们再把AI叠加上去，谈谈它具体如何改变云安全？
<details><summary>Original English</summary>
**>>**: I I know it feels like a lifetime ago that we uh all used to talk about uh just cloud security, preAI security, but I'm curious, you know, look for for security teams and practitioners, CISOs, security engineers, all all of this. Just because new problems appear doesn't mean old problems go away. And so for a lot of, you know, Fortune 500, global 2000, they're still dealing with a lot of cloud security challenges. I'm curious if we for the first part of this question, let's just kind of set AI aside and can you talk about kind of the state of cloud adoption and security in 2026 and then for the second part of the question, let's layer AI in there and talk about how uh how it's really changing cloud security specifically.
</details>

**>>**: 首先，当我们谈到运行中的应用程序时，它始终是位于云端的。当谈到AI攻击者盯上我的应用程序时，他们总是会从过去就可能存在的相同漏洞、问题和错误入手。因此在云安全中，你必须确保聚焦于关键风险并予以修复，这一点没有任何改变。如果你有一个未修复的PHP漏洞，攻击者就会从那里侵入。我们只是增加了更多的漏洞和更多类型的攻击，并不意味着你不需要去防御旧的攻击途径。

在云安全方面，我们看到大家首先都明白需要这样一个记录系统来理解并提供对所有资产的可视化能力。我们开始看到的转变是，企业正试图创建更多的Agentic工作流，同时也对Wiz提出了更高的期望。例如，如果说以前我们提供的是带有优先级排序的漏洞列表，现在他们会期望我们回到代码中定位代码、生成修复补丁并提交Pull Request，基本上是帮助将更多耗时的流程自动化。检测方面也是如此：他们不想要单一的告警，还期望获得完整的调查、取证、找到根本原因，查明攻击者是如何潜入并将其驱逐出去。在我看来，AI目前正在做的，就是针对以往未能通过自动化解决的每一个步骤，企业正在尝试自行实现自动化，同时也期望我们做得更好。举例来说，我们不再仅仅是发现威胁，我们必须做全面调查和数字取证。而且我认为既然看到了AI攻击者的存在，我们的下一步需要开始考虑自动化响应——这虽然非常令人生畏，但我认为我们别无选择。
<details><summary>Original English</summary>
**>>**: Yeah. So, I mean in my first of all, cloud security um when we talk about I have an application that's running, it's always in the cloud, right? When we talk about AI AI attackers coming after my application, they will always start from the the the the the same vulnerabilities and and and problems and mistakes that you could have done before, right? So like nothing changes in the fact that as in in cloud security, you have you have to make sure that you focused on critical risk and then you fixed it, right? Yeah. If you have a a a PHP vulnerability you didn't fix, yeah, attackers are going to come from there, right? So like we we just added more vulnerabilities and more types of attacks [laughter] that mean you don't have to fix the old ways of attacks right. So in terms of cloud security what we're seeing is that first of all everyone understand that the you need this um system of record that understands and gives you visibility into everything right um what we are so I I would say what we are starting to see change is of course that companies are trying to create more um agentic workflows and also expect more from whiz, right? So for example, if before we would provide a a vulnerability with prioritization, now they would expect us to go back to the code, find the code, create the fix, create the pull request, you know, so basically help automate more of the processes that take time. And that's also true for detections, right? They don't want just a detection. They expect also to get a full investigation, forensics, find the root cause, find tell me how the attacker got in and push them out, you know. So the way I see it is that what what AI is doing right now is basically every step that we had that we didn't solve with with automatically. Companies are trying to do it their automatically on their own and they also expect us to get better. Right? So as an example, we are we are not finding threats anymore. We have to do a full investigation. We also need to do forensics. And I I think the next step for us now that we see AI attackers, we need to start thinking about automating response which is very scary but I don't think we have any.
</details>

**>>**: 确实，完全同意。
<details><summary>Original English</summary>
**>>**: Absolutely. Yeah. Yeah. Completely agree.
</details>

### 红蓝智能体与以攻促防

**>>**: 顺着你们正在自动化的工具以及Wiz的发展路径，你提到了Blue Agent。能否多介绍一下Red Agent？因为我认为那真正模拟了对抗性视角。Wiz应对AI带来的风险转移，是否从根本上是在为客户赋予机器般的速度？
<details><summary>Original English</summary>
**>>**: Yeah. Maybe on the topic of things that you guys are automating and just how whiz has has evolved. Um you talked about blue agent. Um can you share a little bit more about red agent? Um because I think that's where you know you're really simulating an advers adversarial point of view. Um, and you know, is your response is is Whizz's response to AI shifting risk um, you know, are essentially are you giving your customers going back to this um, sort of speed thing like speed of the defender, speed of the attacker? Um, are you are you sort of thinking of ways to give machine speed to your customers if you will?
</details>

**>>**: 没错。归根结底这里有两股力量：红方与蓝方。蓝方试图发现攻击并制止它们；红方秉持的理念是最好的防守就是进攻。你必须使用AI持续攻击自己，因为与以往的静态防御不同，现在的防御必须是动态的，每一个新模型都具备新能力。你的应用昨天可能被认为是安全的，但今天就不安全了。打个比方：假设你有一扇门，你把钥匙藏在门垫下，这在过去被认为是安全的；但你的攻击者每周都在获得超能力，也许下周他们就能穿过你的大门。因此，上周被视为安全的东西，如果每个AI模型都能攻破它，那它就不再安全了。防守水位线在不断上升。

要获知自身存在问题的唯一方法，就是利用最新的模型持续对自己发起攻击。在攻击者打开大门之前，你就必须弄清楚并完成修复，而且你没有多少时间，这就是我们所说的防守速度，它至关重要。Red Agent试图做的就是利用我们在内部拥有的上下文，从外部对你的应用程序发起AI进攻性测试，争取在攻击者真正利用这些问题之前将其发现。
<details><summary>Original English</summary>
**>>**: Exactly. So there's eventually there's two forces here, the the red and the blue. The blue tries to to find attacks and and and and and stop them. What the red is trying to say is the best defense is attack, right? So you have to attack yourself with AI continuously because um unlike what we had before where the we had static defenses now defenses has to be they have to be dynamic because every new model has new capabilities, right? So maybe your application was considered secure yesterday, but it's not secure today. Like think about it. If I try to give you a like an analogy, think about you have a door, okay, and you put you hide maybe you hide your key under the mitt, okay? And that's considered secure, right? But your attackers are getting superpowers every every week, right? So maybe next week they're going to be able to get into your door. So whatever was considered secure last week, if every AI model can get into the door, it's not secure anymore. So the watermark keeps going up, right? So the only way to to know you have a problem is to continuously attack yourself with the latest models. So before the attackers can open the door, you figure it out, you fix it, and you don't have a lot of time. And that's the speed where we talk about speed of defense, right? It's crucial. So the red agent tries to do that. tries to do an offensive AI attack against your applications from the outside using the context we have from the inside to try to find the problems before the attackers actually use them.
</details>

**>>**: 你们在红队方面也采用了类似的流水线吗？之所以这样问，是站在那些理解这些理念并希望着手实施的团队角度，帮他们避开其他人踩过的坑。在蓝队方面，你们从确定性方法入手，然后叠加上便宜的模型，流水线随着层级推进逐渐调用更昂贵的高级模型。在红队方面，你们是采用类似的确定性起步再叠加便宜模型，还是同时跑一大堆完全从零开始的不同模型？
<details><summary>Original English</summary>
**>>**: Are you doing a similar pipeline on the the red team side? So my my question is coming from the angle of teams who this all makes sense to them. They want to get started with it. Uh let's help them avoid a bunch of the mistakes that everyone else has had to learn. On the blue team side, uh you start this with kind of deterministic approaches and then you layer in cheap models and and the time the pipeline that you talked about are progressively getting more expensive. Are you doing similar approaches on the red team side as well where it's you're starting deterministic and then you're layering cheap models or are you layering just a whole bunch of different models all starting from scratch and all running simultaneously?
</details>

**>>**: 两者皆有。
<details><summary>Original English</summary>
**>>**: Everything.
</details>

**>>**: 哈哈，果然。[笑]
<details><summary>Original English</summary>
**>>**: Yeah, exactly. [laughter]
</details>

**>>**: 如果你手头有预算，直接把预算扔给模型去扫描代码并不是很有效率。更高效的做法是先分析所有的暴露面，这是我们用确定性方法处理的。然后我们在此之上叠加我们所谓的暴露面Agent，它只关注从你的环境中暴露在互联网上、未经验证的所有资产。这是对每一个暴露点的即时分析，这是最紧迫的事情，甚至比扫描你的代码更重要。谁在乎你的代码？我指的是你实际拥有的、未经身份验证的外部暴露攻击面，这更加紧急。

下一步是开始进行更深度的渗透测试分析和更深度的代码分析。这里显然存在分层：在模型和调查耗时方面，负责外部的暴露面Agent对每个端点可能只需几分钟，因为你有一百万个端点；而当面对关键应用时，我可能会花上10个小时去尝试攻破它。这一切都是流水线，不能把钱盲目砸在代码扫描上就以为万事大吉，核心在于预算管理。而且它们都是相互关联的，如果我发现了一个问题，而工程部门说“天哪，修复这个太贵了”，那我可以让Blue Agent在相应位置部署防御检测。这一切是协同运作的。
<details><summary>Original English</summary>
**>>**: So yes, I mean first of all let's compare this to like if you have a budget you can just give it to meters and run on code that's not very efficient. So more efficient is that you analyze all the exposure, right? That's what we do it deterministically with, right? Then we layer on top of that what we call the exposure rate agent that just looks at everything that is unauthenticated, exposed on the internet from your environment. Right? So that's an immediate analysis for everything, every exposure you have. That is the most urgent thing to do. It's even more important than scanning your code. Okay? Who cares about your code? I'm talking about the actual unauthenticated exposed um attack surface that you have more urgent right next step is to start doing deeper pentest analysis and deeper code analysis right so there's definitely layers here and also in terms of models and investigation time the from the outside what we call exposure agent maybe will take a few minutes for every endpoint because you have a million endpoints when there's a critical application I might take 10 hours to try and hack it right so it's H it's all a pipeline. Everything is going to be a pipeline now, right? It's a you cannot throw money on code scanning and think it's you're done. No, it's it's all about managing the budget. This is the whole point, right? And they they're all connected because if I find a problem and the engineering says, "Oh my god, this is too expensive to fix." Okay, you know what? Let me tell the blue agent to put some detections there. You see, like the this is all working together,
</details>

**>>**: 明白。听到你关于这个问题的观点非常有意思，因为前几天我们内部与Rick讨论过，感觉行业现状基本上正如Red Agent所做的那样：用智能体集群不断攻击自己的系统，从而知道如何抵御外部威胁。你们与一些顶级的企业客户合作，涵盖超过50%的财富100强，客户群中也有很多前沿初创企业。目前有多少人真正在落地这种做法？
<details><summary>Original English</summary>
**>>**: right? Right. Um, I I was going to ask and it's um really interesting to hear your point of view on this because we had an internal discussion um with Rick the other day about how it feels like state-of-the-art is essentially what Red Agent is doing. You know, you have agent swarms constantly attacking your own systems that so so so you know how to protect against them, right? Um you're you're working with some of the top enterprise customers, right? Over 50% of the Fortune 100 and then you also have bleeding edge startups in your customer base. How many people are actually doing this?
</details>

**>>**: 在Wiz的客户中，大多数已经在开始使用Red Agent了。但在整个行业中，我认为还远远不够。每个人现在都应该这样做，没有什么比从外部持续扫描你的环境更重要的了，最好的防御就是进攻。等到攻击者找上门来时可能就太晚了，所以你能做的最好的事情就是持续攻击自己的环境。在Wiz客户这边，我们正在迅速接近全覆盖，大家都理解了这一点，这确实是我们发布过的增长最快的功能之一。

但在更广泛的行业中，我不认为大家真正明白。有时候Mitos获得了很好的公关宣传，但公关引导的方向错了。我其实并不认为代码扫描是你所能做的最高效的事情。理解这一点很重要，因为有人会说：“哦，我在代码扫描上投入了巨资。”但实际上那并不是你首要该做的，你应该把精力集中在扫描外部暴露面上。两天前就发生了一起重大事件：某移动应用中硬编码了一个密钥，导致海量用户数据泄露。那才是攻击者获取攻击入口的地方——未认证的暴露面。那才是你需要持续运行扫描的地方。这就是目前的认知差距，全世界都需要认识到这一点。
<details><summary>Original English</summary>
**>>**: So in majority of customers are already using the the red agent. I think across the industry not enough. I I think everyone should do it right now. Like there's nothing more important than to scan your environment continuously from the outside. Like there's nothing more important than that. Like it's the best defense is attack. When they come it might be too late. Okay. So the really the the the best thing you can do is continuously attack your environment. So in my view like again on the on the W customer side it's it's like we are getting very quickly to almost full coverage right like everyone understands it and it's really one of the fastest growing features that we've ever released. Um in the world I don't think people understand. I think there's sometimes you know Mitos got a lot of PR good okay but the PR went to the wrong place. I I actually don't think the scanning code is the most efficient thing you can do. Okay? And it's important to understand that because people can say, "Oh, yeah, I invested so much in scanning code." Really, that's not what you should do. You should focus on your scanning your external exposure before because like we had a there was a big incident just two days ago a a a key hardcoded in a mobile application that exposed a lot of people's data, right? That's where attackers get their attacks, unauthenticated surfaces. That's what you have to run scans for and you have to do it continuously. So that's I think that's the that's the gap and the world needs to know that.
</details>

### 初创企业在Agent时代的防御与架构重构

**>>**: 沿着创始人应该做什么这个话题展开：Zayn和我们的同事Joel在黑色十月期间给我们的被投创始人写过一份备忘录，谈到在安全上投入更多，甚至考虑推迟产品发布。我想就这个问题请教你们两位，Zayn可以先谈谈。假设我是一名即将发布产品的创始人，手头积压了一批安全问题，在发版之前我应该如何思考必须做些什么？
<details><summary>Original English</summary>
**>>**: Yeah. Maybe on this thread of uh what founders should be doing. Um so Zayn and our colleague Joel actually um wrote a note in the midst of Black October um you know to our founders talking about spending more on security uh potentially considering delaying product releases. Um, so I want, this is a question for both of you, maybe Zayn to say a little bit more about that, but say I'm a founder with a release coming up. I have a backlog of security issues. How should I think about what needs to happen before I ship? So question for both of you, I guess.
</details>

**>>**: 好的，我可以先讲讲。我认为我们俩在这点上高度一致：安全博弈的规则已经彻底变了。你现在需要考虑如何让红蓝双方的绝大部分流程自动化，并真正利用多样化的智能体来实现这些自动化。在过去的旧模式下，往往是先有一个发布计划，然后为了安全审查去推迟发版。而在新的模式下，你应该考虑的是如何让所有这些事情并行进行？如何利用各种智能体进行持续测试？如果你今天正在创建一家新公司，从一开始就应该把修补能力和高度自动化深度融入到软件开发和基础设施构建中。
<details><summary>Original English</summary>
**>>**: Yeah, sure. I mean, I'll I can kick off. I mean, I mean, I think I think you and I are are very aligned on this, which is the security game has just changed, right? And you need to be thinking about uh how you can automate so much of both the blue side and the red side right now and really leveraging a variety of agents for those automations. And so I think historically in the the old models it was you know the you had a release and then you kind of delayed that for security and all of that. I think that the new model that you're thinking about is how can you be doing all these things in parallel? How can you be really leveraging a variety of agents to be continuously testing and if you're building a new company today really doing patching from the beginning and building in so much automation into your uh your software development and your infrastructure development.
</details>

**>>**: 是的，我不想危言耸听，但我一直在与遭到攻击的初创公司CEO们打交道，让我们站在他们的角度设身处地想一想：你一觉醒来，安全团队告诉你昨晚出大事了，他们试图阻止但攻击者已经潜入进去了。一小时后被发现——这甚至还是有专门安全团队的较好情况……
<details><summary>Original English</summary>
**>>**: Yes. Yes. Again I want to I don't want to care but I let's let's just I work with the CEOs of startups that are getting attacked. Let's just be in their shoes. Okay. You wake up and your security team says something bad happened overnight. Uh we tried to stop it, but um they got in uh we woke up after an hour and that's in the good like situation where
</details>

**>>**: 你说“一小时后”已经非常客气了。[笑]
<details><summary>Original English</summary>
**>>**: Yeah, you're being very nice there of of an hour. Yeah, [laughter]
</details>

**>>**: 这还是假设他们甚至有安全团队的情况，甚至不知道是否有专人负责。然后发现攻击者潜入后，整场攻击从入侵到窃取全部密钥、所有客户的AI Key，仅仅花费了20分钟。现在你必须去面对所有客户，向他们交代情况并善后。这正是很多公司当下正在经历的困境。

核心在于，我们以前从未见过AI攻击，必须认识到这是一种全新的威胁。它威胁着每一个人。但如果我是一家初创公司，尤其如果我拥有攻击者想要的东西——特别是AI密钥或任何他们能利用的资源——我就是他们的直接靶子。这并不局限于大公司，初创公司现在实际上是LLM劫持（LLM checking）的核心目标。如果你拥有密钥，你需要怎么做？最好给它们设置限额，因为如果被盗，你肯定不希望面临天价账单，这种惨痛情况我们见得太多了。同时如果身上贴着靶子，你必须在安全上投入大量精力。以往并非如此，但现在如果他们想打进来，速度会极快。你确实必须对此进行投资，事实就是如此。
<details><summary>Original English</summary>
**>>**: they they even have a security team. Okay. After like a round, I don't even know if they have someone that is dedicated, right? And and the attacker Yeah. And we found out that the attacker got in and they the entire attack again takes 20 minutes until from the time they get in until they take all of the secrets, all of the AI keys of all of the customers, right? And now you have to figure out what are you going to say to all of the customers and what you're going to do. And this is what is going through companies right now is like and so the point is that AI attacks, we've never seen that before. We have to understand it's a new threat, right? It's it's a threat to everyone. But if I'm a startup, especially if I have anything attackers want again, especially like if I have AI keys or anything related to um um something they can use, right? I am on their target. It doesn't have to be a big company. Okay? Startups are actually their key target now for for LLM checking, right? What do you need to do if you have keys? probably better to put a limit on them because if they h steal them, you don't want to get a lot of charges, which we see happen a lot and it's really really sad. But also make sure that if you have a target on your back, you do need to put a lot of focus on security. This was never the case, but it's now true that if they want to get in, they they it will happen fast. So, you do have to invest in this. That's there's just
</details>

**>>**: 别无他法。
<details><summary>Original English</summary>
**>>**: there's no other way to put it.
</details>

**>>**: 是的，我认为完全正确。无论是资金、时间还是任何维度的安全投入，随着我们步入这个全新的安全时代，在未来几年都必须大幅增加。
<details><summary>Original English</summary>
**>>**: Yeah, I think that's exactly correct. the the level of security investment whether that is dollars, time, uh any of these things just needs to go up the next several years as we're going into this new era of security.
</details>

### 安全预算与旧工具淘汰：重在架构设计

**>>**: 沿着这个话题，一位CISO最近告诉我们团队的合伙人，他预计明年的安全预算将增长80%。我们虽然都预期预算会涨，但这个增幅可能处于较高区间。我很想知道，大家正在把更多的钱花在什么上面？反过来说，CISO们应该在哪些方面减少开支？你曾公开写过某类安全产品可能会逐渐被淘汰，能否具体谈谈哪些预算该增加，哪些该削减？
<details><summary>Original English</summary>
**>>**: Yeah. So on that topic, um a CISO recently told um you know, one of the partners our team that he expects his security budget to go up 80% next year, which is, you know, we we we all anticipated that it would go up, but that that's probably on the higher end. Um, I'm curious what uh, you know, what are you seeing folks spend more money on? Um, and on the flip side, what should CESOS be spending less money on? Right. And, um, you know, you've you've kind of written publicly about a class of security products that may become somewhat obsolete. Um, but maybe talk through that uh, in terms of what you know, where budgets should go up, but also where they should come down.
</details>

**>>**: 好的。首先，假设你有一栋房子，并且你知道有一支训练有素的顶级黑客精英队伍要来黑你的房子。他们可能不会走正门，而是从窗户或屋顶翻进来。老实讲，有多少房子为此做好了准备？大多数房主可能会说：算了，我根本没办法防范屋顶，这对我来说是不可能的。

重点在于，大多数公司根本没有准备好应对具备全球顶级攻击者速度和专业知识的对手。这就是为什么它是一个难题。甚至在谈论预算之前，我都不确定预算是否能解决这个问题。这不是安全预算的问题，它关乎专注点；坦率地说，它关乎安全架构和安全设计。预算本身甚至解决不了任何问题，世界上不存在一款你能买下来然后就高枕无忧的安全工具。
<details><summary>Original English</summary>
**>>**: Okay. So, first of all, again, I let's assume you have a house, okay? And you know that an elite group of the most trained hackers are going to hack your house. Okay, they might not come through the door. They might come through the window or the roof, right? Honestly, how many houses are even ready for that? Like most houses would say fine, they I'm not going to secure the roof. Obviously, there's no way for me to I mean it's impossible, right? So the point is that like we are really most of the companies are not ready for attackers that have the the speed and expertise of the best attackers in the world. And this is why it's a hard problem. So even before we talk about budgets, I don't even know if budgets are going to solve the problem. Okay? Like it's not about security budgets. It's it's it is about focus. But to be honest, like it's about security architecture, security design. Like it's budget is not even going to solve anything to like it's it's like it's not like you there's a security tool in the world you can buy and everything is fine.
</details>

**>>**: 可恶。[笑]
<details><summary>Original English</summary>
**>>**: Dang it. [laughter]
</details>

**>>**: 如果是真的，那咱们的工作可就轻松多了。[笑]但确实如此。
<details><summary>Original English</summary>
**>>**: I'm not just you know would have made a lot of our jobs a lot easier if that [laughter] was true. But yeah
</details>

**>>**: 我不认为这是真的。显然，大多数传统安全工具甚至已经不再相关了。即便你采用了AI原生的安全工具，理解了AI世界中的攻击模式、云攻击等机制，坦率地说，安全设计也远比单纯的安全预算更重要。那么安全预算会增加吗？也许会。我们是否应该审查现有的技术栈？是的。

但更重要的是，拥有一个专注于全天候扫描代码和应用程序的开发团队；考虑沙箱、隔离、安全设计、网络锁定、进程锁定和镜像锁定。如果你现在构建系统，就要做好面对国家级黑客（nation state attacker）的准备。假设漏洞必然存在，不要想当然地认为“我们把所有东西跑在Kubernetes集群里就安全了”——Linux内核中时刻都在出现零日漏洞，任何人都能逃逸容器。所以安全设计远不止是预算问题。预算增加当然好，但这只是其一。
<details><summary>Original English</summary>
**>>**: I'm not I don't think it's true. Obviously most of the legacy security tools are not even relevant anymore. Okay. Well, that's like that's but even if you get security to the AI native that understands how to attack attacks in AI world work and cloud attacks and so on. Even then to be honest it's about security design even more than just security budget. Okay. So is security budget going up? Maybe is should we review their existing tech that we have? Yes. Okay. But more than that, it's about having a dev team that is focused on scanning the code and applications all the time. It's about thinking about um sandboxes and isolation and like secure design and and and and network lockdown and process lockdown and image lockdown. Like it's just like if you're building stuff now, get ready for a nation state attacker. You see like get ready for that. Imagine there's going to be a vulnerability. Like don't assume ah let's run everything in a Kubernetes cluster. No, like it's there's zero day vulnerabilities in in Linux all the time. Anyone can get out of a container. So you see like secure design is much more than just a budget. Obviously security budgets that's great but it's one [laughter] totally
</details>

**>>**: 是的，观点很深刻。
<details><summary>Original English</summary>
**>>**: yeah I mean a great point
</details>

**>>**: 就这一点而言，感觉非常像当年的云计算转型：这是一个真正的阶梯式跨越。我看到许多CISO正在审视自己现有的供应商技术栈并进行彻底重构，寻找哪些是AI原生的技术，因为在聚焦安全架构时必须借助AI原生技术。正如你所谈到的，必须透彻思考这个问题，意识到技术栈的每一层都同时存在漏洞。套用CISO的老话：“不要浪费任何一场好的危机。”如今正是如此，通过彻底重构安全产品版图迈向AI原生，帮助企业进入这个无论你想不想都已身处其中的新时代。
<details><summary>Original English</summary>
**>>**: to to that point it definitely feels a lot like cloud in the sense of this is a real stairst step where I'm seeing so many CISOs take a look at their existing vendor stack and really reboot that to see what are the AI native ones because you need AI native technologies as you are really focused on secure architectures exactly what you're talking about of like really thinking about the problem through and understanding there are vulnerabilities at every stage of the stack there simultaneously. This is the the old uh you know CISO saying of like don't let a good crisis go to waste. Uh which is absolutely happening here of rebooting so much of your security product landscape to actually be AI native to help you go into this new era that you already are are in whether you want to be or not.
</details>

**>>**: 是的。不妨说得更具体一点，不针对任何特定厂商，现阶段CISO部署的哪些类型的安全软件已经不再被需要了？
<details><summary>Original English</summary>
**>>**: Yeah. Well, maybe just to get explicit, not not to dunk on any particular company, but what's a type of, you know, software security, let's say, um, security software that you have in place that CISOs have in place now that they just don't no longer need.
</details>

**>>**: 这么说可能会比较刺耳：安全团队做的大多数事情根本不是安全。他们只有极小一部分时间是真正花在安全上的。检验的方式很简单，这也是为什么我始终坚信直接攻击自身：你花了多少时间与红队在一起，又花了多少时间在合规和生成报告上？坦率地说，大多数安全团队并没有聚焦在安全本身。在我看来，安全要么是为防御攻击者做准备（通过自我攻击），要么是在攻击发生时设置好防护栏。现在的重点是安全团队必须变得更加高效，我们应该停止大部分手头做的事情，集中精力去发现关键风险，弄清楚如何缓解风险，或者至少部署好检测和响应机制。我们没有时间去耗费在任何脱离这一目标的事情上。

因此当你在做一项任务时，问问自己：这份合规报告真的对我们有帮助吗？这也是我过去一直反对传统CSPM（云安全态势管理）的原因。那只是过去做云安全的方式，仅仅是一堆配置检查清单。我根本不在乎那些。你必须关注攻击者会从哪里攻进来？我是否竭尽所能去阻止他们？如果能建立战略屏障，那就建立起来。重点在于理解环境中的实际真实风险，建立可持续的长期隔离策略，这才是应该做的事。
<details><summary>Original English</summary>
**>>**: Um, so [laughter] if you, okay, most I've always been against, again, it might be a a hard sentence, okay? Most of what security teams do is not security. Okay, there maybe small small subset of their time is actually security and the way to check it is this and that's why I always believe in just attack yourself like how much time are you spending with red teams and how much time you spending with compliance and and and creating reports right to be honest most of the security teams are not focused on security and security in my view is getting either what you're doing is either getting ready for the attacker attacking yourself or putting guard rails for the attack when it comes. Okay, so the point is that we do have to be much more much more efficient now on security team. We should stop doing most of what we do and focus on finding critical risk, figuring out how we mitigate it or at least put detections in and and and also response readiness for it. We have to be good. So we don't have time to spend on on on on on everything that is not focused on that. So if you do a task, you say, is this report really helping us? You know, and that was always my point against like classic what we call CSPM in cloud which was just the way you did cloud security before just the list of
</details>

**>>**: 是的，配置检查。
<details><summary>Original English</summary>
**>>**: yeah configuration checks.
</details>

**>>**: 我不在乎那些配置检查。你必须关注攻击者会从哪里入侵。我是否在竭尽全力阻止他们？如果有一道可以构建的战略屏障，那就建起来。要专注于理解环境中的实际风险，制定可持续的长期隔离策略，这些才是你该做的事情。
<details><summary>Original English</summary>
**>>**: I don't care about that. You have to care about where is the attacker going to come from. Am I doing everything I can to to stop them? Can I can I if there's a a a strategic barrier I can build, let's build it. you know like focus on on understanding the actual real risk in the environment creating sustainable long-term isolation strategy these are the things you should do.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 顺着时间管理这一点，回到AI如何真正协助安全团队：随着智能体承担起更多日常调查和测试工作，你认为最具经验的安全专业人士应该把时间花在哪里？你前面回答了一部分，但或许可以再深入探讨一下。
<details><summary>Original English</summary>
**>>**: Yeah. And and actually on this point of t time management um and maybe flipping a little bit to how AI is actually helping security teams, right? So as as agents maybe take on more of the routine investigations and testing, how do you think and you you've answered this a little bit but maybe deep dive into it. Um some of the most experienced security professionals should be spending their time.
</details>

**>>**: 对于现在从零起步的安全团队来说会容易得多。如果你现在正在创建一家公司，你很幸运，应该尝试构建完全自动化的安全视图、自动化的补丁流程、自动化的调查。只要你对自身环境拥有足够的上下文和知识库，完全有办法构建全自动化的系统。但问题在于，对于大多数现有安全团队来说根本不是这么回事。你拥有大量的遗留软件和成千上万的开发者，甚至不知道某个资源具体归谁所有。情况并没有因为出现了一个AI Agent就立刻全盘改变，归根结底还是要找到上下文：谁才是具体资产的负责人？我怎么推动他们去修补？这非常复杂。

因此，行业内的大多数安全团队都需要时间才能摸索出如何真正实现高效率。这并不像听起来那么简单，因为组织的许多知识往往是不清晰、没有明确沉淀下来的。但这正是所有安全团队面临的挑战：如果我无法在几分钟内做出响应，那我还有价值吗？
<details><summary>Original English</summary>
**>>**: Much easier for a security team starting from now from scratch. Okay? Like obviously if you're building a company right now you're lucky and you should try to build everything fully automated security views automated pet process automated investigation automated if you have enough context and knowledge base about your environment there is a there is definitely a way for you to build everything completely automated. The problem is that for most security teams it's just not the case. Okay, not the case. You have a lot of legacy software, thousands of developers, you don't even know who owns what. It's like it's it's it's not like everything is changing in a because there's an AI agent. Okay. It's goes still goes back to find the context of who actually owns every resource. How do I get them to patch stuff? It's it's complicated. So, it's going to take time for most of the security team in the industry to figure out how to start really really getting to efficiency. It's not it it's not as easy and simple as it sounds because a lot of the knowledge of the organization is a bit you know obscure. It's it's not anywhere that is actually uh written h but it is the challenge of all security teams. If I cannot respond in minutes, what can I am I relevant? Right.
</details>

**>>**: 是的，没错。
<details><summary>Original English</summary>
**>>**: Yeah. Yeah.
</details>

### 未来展望：重回狂野互联网与物理基础设施危机

**>>**: 顺着这个思路，我想用一个串联起我们今天讨论主线的问题来收尾：你认为接下来的几年会是怎样的？比如未来的两到三年？我先抛出我自己的预测：我们将重回90年代和2000年代。未经验证的完整远程零日漏洞将层出不穷，我们又要看到安全泄露事件频繁爆发了。现在的局面将与过去15年的安全状况大不相同，我认为我们正在重回一个截然不同的安全时代。

我甚至抛出一个更大胆的猜想：如果我们在互联网上重新看到类似Windows XP时代的蠕虫病毒泛滥，我也不会感到惊讶。我们之前在基础设施团队内部聊到过这个，Martin提出了一个很有趣的细节：对于当年经历过那个IT时代的人来说，曾有一段时间你安装和更新Windows XP的速度甚至赶不上中毒的速度，因为从你装好系统到启动更新的间隙，蠕虫就会打进你的系统完成感染。你必须完全离线安装所有补丁，因为如果联网安装，它被攻破的速度比你打补丁的速度还要快。AI带来的很多看似全新的东西，在很多方面恰恰是我们在20到25年前互联网蛮荒时代经历过的。基于这一点，我很想知道你对未来几年有何看法？
<details><summary>Original English</summary>
**>>**: So to to that point, I'll kind of uh round us out with a a question here on kind of connecting the through line of what we've talked about, which is what do you think the next several years looks like? Like our next two to three years? Like I I I'll I'll start you off with my own prediction, which is that we're going back to the 90s and 2000s again. This is there's going to be full remotes uh unauthenticated full ODAS popping out all the time. Now we're going to see breaches popping out all the time again. Now it's going to look very different than the last 15 years of security. I think we are going back to a a era that looked very different in security. And I'll even throw one wild one out there that like I I wouldn't be surprised if we end up seeing worms again on the internet uh like we did in the Windows XP days. Uh we were chatting internally on this on the the infra team and uh Martin brought up a a a funny point of there was for all of us who were kind of in broader tech and it at the time there was a window of time where you couldn't install and update Windows XP fast enough because from when you installed it when you started the update a worm would hit your system and infect it during the time it took to actually update the system. And so you literally had to install all of this offline because if you installed it online, it would get compromised faster than you could patch it. And I think so much of this that feels so new with AI in a lot of ways is something plenty of us experienced 20 25 years ago in the kind of wild west days of the internet. And so building off of that, I'm curious what you think the the next few years look like.
</details>

**>>**: Ammy，我追问一个简短问题跟进Zayn的提问。你在四月份写过一篇很棒的博客，提出在12到18个月内将迎来类似“千禧虫”（Y2K）的时刻。结合Zayn关于未来两到三年的问题，考虑到过去六个月所发生的一切，你现在会把那个时刻提前吗？[笑]
<details><summary>Original English</summary>
**>>**: Uh Ammy, just add a quick uh question to tag on to Zay's. you you wrote um this great blog post in April that there was a Y2K moment coming in 12 to 18 months. Um to Zayn's point on the next two to three years, would you pull up that moment now given everything that's happened in the last six months? [laughter]
</details>

**>>**: 是的。首先，我认为“黑色十月”可能就是开端。我们之前不想引起过分恐慌，原本希望能争取更多时间，但开源模型赶上的速度远超我们的预期。我们原本希望开源模型会落后一年，但它们并没有。所以，是的，我认为它正在发生，我们在客户群体中从未见过如此强度的攻击。而且如果拿它与90年代相比，如今我们对技术的依赖程度要远远高得多。
<details><summary>Original English</summary>
**>>**: Yeah. So f first of all I I I think black October might be the the beginning like again this we didn't want to scare too much and we were hoping more time but the open source models are catching much quicker than if we thought okay like the the hope was that open source models are a year behind but they're not so uh yeah it's I think it's happening like we've never seen this level of attacks across customers like it's happening and if you want to compare to the '9s the our dependency on technology is much much much higher than
</details>

**>>**: 绝对如此。
<details><summary>Original English</summary>
**>>**: absolutely yeah
</details>

**>>**: 并且必须认识到，这几乎是目前整个人类领域中，AI唯一全面超越人类的领域。这才是问题所在，在90年代根本不存在这种情况。AI攻击现在不仅极其普遍、易于发起，而且比任何人类都更厉害。我们面对的是利用零日漏洞的高复杂度攻击；今天我们就遇到了一起利用内核驱动零日漏洞的攻击——天哪，这本应是极其罕见的，现在却每天都在发生。人类攻击者根本无法维持这种频率。

因此，我们正处于一个AI比人类更强大的时代。如果让我展望，我甚至无法预测两年后的具体形态。我认为唯一能够生存下来的公司，是那些现在不仅构建安全自动化、安全设计与安全审查，并且以全新方式重新设计其面向互联网系统的公司。任何尚未准备就绪的系统都应该迅速撤出公网。在公网上，你必须确保一切都做好了抵御疯狂攻击者的准备，必须为此进行重新设计，我认为这是唯一的生存之道。
<details><summary>Original English</summary>
**>>**: and also what happened and it's important to understand this is almost the only area in humankind right now that AI is better than humans okay that's the problem it's it's not and that was not the problem in '90s like AI attacks now are prevalent easy but also better than any human okay like that's the problem okay I'm talking about attacks that are very very complex using zero days we had today an attack using a zero day on a kernel driver. My god, like that's very should be very rare. It's happening every day now. Human attackers cannot do it. So you see like we're at an era where AI is better than humans. And if I need to I cannot foresee two years ahead from now. I I think the only companies that will be able to survive are companies that are building now not just security automation, security design, security reviews. They're designing their systems that are exposed to the internet in a new way and whatever is not ready should take take off the internet okay quickly right so on the internet you need to be ready with everything that is like ready for the crazy attackers and and you have to design for this right like I think that's the that's the only way
</details>

**>>**: 本期播客的大部分内容主要关注企业和科技公司等。我想提一下你们最近发起的“Scan for Good”倡议。我想把这个举措放在攻击大背景下讨论：我们之前聊到了AI基础设施公司等，但纵观最近欧洲冷藏设施遭受的攻击——如果考虑到食品供应链等现实系统，在大规模范围内这会对人类造成极其严重的后果。我不想制造恐慌，但Ammy，你显然在把握好分寸，既确保大家做好准备并严肃对待，又不至于过度散布恐慌。我想问两个问题：第一，我们对公共基础设施以及那些没有庞大网络安全预算的实体正在经历的状况应该担忧到什么程度？第二，能否谈谈“Scan for Good”以及你们发起它的初衷，你们是如何帮助非营利组织和公共服务机构为眼前的危机做好准备的？
<details><summary>Original English</summary>
**>>**: a lot of this podcast was um focused on you know enterprises tech companies etc um I want to bring up scan for good which is an initiative you guys launched um recently um but I want to talk about in the context of some of the attacks uh you know we're talking about um AI infrastructure companies and things like that um but you know if we look at the recent attacks on uh refrigeration units in Europe um which you know if you think about the the supply the food supply chain etc right like this on a mass scale has dire consequences for humanity um and I I don't want to I don't want to fear-monger um but you know I think there's also this appropriate line that you're walking amii of making sure people are prepared and are taking things seriously. Um so I guess two two questions. One is u how worried should we be about what's happening to public infrastructure and maybe these entities that don't have huge cyber budgets etc. Um and two maybe talk a little bit about scan for good and why you guys are doing that how you're you know helping nonprofits public services etc get really prepared for what is already h
</details>

**>>**: 我确实感到非常担忧。正如你所说，无论是现实世界中实际运行的遗留软件冷藏系统，还是交通系统，任何联网的设备都处于危险之中。这正是我们发起“Scan for Good”的原因所在。“Scan for Good”旨在帮助任何寻求援助的公共服务机构，我们尝试为他们扫描并发现问题。这无法解决他们的所有问题，但我们试图给他们一个推动力。我们希望在帮他们发现问题后，他们能意识到这是一个更大的系统工程，并开始自行开展红队主动扫描。这是为了促使他们向这个方向迈进。
<details><summary>Original English</summary>
**>>**: so I I I mean yeah I am worried I mean those exactly I mean the legacy uh software it can be refrigerators I mean that are actually in the real world it can be um h traffic I mean it can be anything it can be really anything that we know that is connected to the internet is at risk. That's exactly the reason we started Scan for Good. Scan for good is trying to help any any public service that wants help and we try to scan them and try to find problems. It's not going to solve all their issues but we're trying to give them a bit of a push. Our hope that if we find stuff then they will understand it's a bigger project and they will start doing red scanning on their own. Right. So it's a like this is more of getting them to push into that.
</details>

**>>**: 太棒了。非常感谢，聊得非常开心，内容令人震撼。
<details><summary>Original English</summary>
**>>**: This is awesome. Thank you so much. This was super fun, man. Incredible.
</details>

**>>**: 见到你们两位真好。这确实是一个疯狂的时代。
<details><summary>Original English</summary>
**>>**: Really great to see you both and Yeah. I mean, this is a crazy time.
</details>

**>>**: 确实如此。
<details><summary>Original English</summary>
**>>**: Oh, absolutely.
</details>

**>>**: 疯狂的时代，感谢你当下所做的一切。
<details><summary>Original English</summary>
**>>**: It's a crazy time. Thank you for what you're doing right now.
</details>

**>>**: 必须的。老兄，谁能想到我们会从过去的OWASP大会一路走到今天？很高兴见到你。
<details><summary>Original English</summary>
**>>**: Absolutely. Who would have thought from OAS conferences to here, buddy? Good to see you.
</details>

**>>**: 是啊，那是一段有趣的经历。
<details><summary>Original English</summary>
**>>**: Yes. Yes. I remember it was a fun one.
</details>