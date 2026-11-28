---
author: Internet of Bugs
date: '2026-10-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DEiGTK62DcQ
speaker: Internet of Bugs
tags:
  - cybersecurity
  - vulnerability
  - media-hype
  - artificial-intelligence
title: 拆解「黑色十月」与 AI 黑客炒作：PHP 漏洞历史与真实网络安全风险
summary: 视频博主 Carl 剖析了媒体与 AI 公司炒作所谓「黑色十月」史上最严重网络安全危机的内幕。他指出 AI 发现的 PHP 漏洞缺乏在网实测利用证据，且过去 20 年同类高危漏洞多达 140 余个；同时梳理了 eMudhra 证书错误、Railway 遭攻击等事件中 AI 的真实角色，批评炒作掩盖了企业安全投入不足与基础防护缺失的根因。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Carl
  - Ed Zitron
companies_orgs:
  - OpenAI
  - Breaking Points
  - Railway
  - eMudhra
products_models:
  - PHP
  - GitLab
media_books: []
status: evergreen
---
### 媒体与 AI 公司的「黑色十月」炒作

媒体称之为「黑色十月」。网络安全专家也称其为「黑色十月」。他们都叫它「黑色十月」。他们称这是史上最严重的事件，是史上最严重的网络安全事件。这是网络安全史上最严峻的 48 小时。但这又是那种开头在「技术层面」属实、但遗漏了大量必要背景，以至于跟捏造几乎没有区别的报道。随后，它成了那群毫无技术背景却拥有庞大受众的人进行不负责任投机推测的跳板。AI 公司希望让所有人相信自己是地球上最强大的公司，因此估值高达数万亿美元。此外，还有那些拥有海量观众的媒体人，他们深知恐吓大众能博取点击量，于是夸大其词，好向你展示更多广告。他们甚至把一个名字里直接带有 meme（梗）字样的匿名梗图账号当作主要信源。这些人才是真正的问题所在。因此今天，在不涉及晦涩技术细节的前提下，我将为大家破除这些炒作，补充所有人都忽略的历史背景，告诉你真正有理由担忧的是什么、你可以为此做些什么，以及这套叙事中哪些部分纯属胡扯。

<details>
<summary>Original English</summary>
 The media is calling it Black October.
 Cybersecurity experts are calling it Black
 October.
 And they're calling it Black October.
 They're calling it the worst in history.
 The worst cybersecurity incident in history.
 This is the most serious 48 hours in
 cybersecurity history.
 This is another one of those stories
 that started out as "technically" true,
 but that left out so much necessary context
 that it may as well have been a fabrication.
 And then it became a jumping off point
 for a bunch of people with large audiences
 and no technical background
 to start speculating irresponsibly.
 The AI companies want everyone to believe
 that they are the most powerful companies on
 earth
 and therefore worth trillions of dollars.
 And then there are the media types with huge
 audiences
 who know that scaring people gets clicks
 who are blowing the whole thing out of
 proportion
 to show you more ads.
 And actually using as their primary source
 an anonymous meme account
 with the word meme right there in the name.
 These people are the real problem.
 So today without getting technical,
 I'm gonna break down the hype for you,
 give you the historical context that everyone
 else is ignoring
 and tell you what you have reason to be
 concerned about,
 what you can do about that
 and what parts of this narrative are just
 bulls----------
 (upbeat music)
 (bell dings)
</details>

这里是 Internet of Bugs，我叫 Carl。自 1980 年代末以来我一直从事软件专业工作，正尽己所能让互联网变成一个更安全、更少漏洞的地方。你可以在 InternetOfBugs.com 了解关于我和我的工作的更多信息。你可以在我的免费 Substack 上阅读我关于 AI 软件的文章；如果你愿意支持我在这里做的事，并获取独家锐评视频以及每周问答连线，下方同样附有我 Patreon 的链接。

<details>
<summary>Original English</summary>
 This is the Internet of Bugs, my name is Carl.
 I've been a software professional since the
 late 1980s
 and I'm trying to do my part to make the
 Internet
 a safer, less buggy place.
 You can find out more about me and my work
 at InternetOfBugs.com.
 You can read my essays about AI software
 on my free Substack
 and if you would consider supporting what I do
 here
 and getting access to exclusive hot take videos
 and weekly Q&A calls,
 links to my Patreon are below as well.
</details>

### 揭开 PHP 漏洞的真实面目

那么，让我们从最吓人的头条新闻开始：「AI 在 PHP 中发现了漏洞，70% 的互联网都面临风险」，诸如此类。噢对了，存在漏洞的软件名叫 PHP。什么是 PHP 呢？其实它跟这次炒作关系不大，不过好吧，让英国版《周六夜现场》（SNL UK）来告诉你需要了解的内容：

「那么，PHP 到底是什么？
基本上，它和互联网有点关系，Paddy。
谢谢，Anya。是的，PHP 基本上与互联网的运行方式有关，Anya。
谢谢，Paddy。」

说真的，如果你不是技术人员，关于 PHP 的功能，你只需要知道这些就够了。

<details>
<summary>Original English</summary>
 So let's start with a scariest headline.
 AI found a vulnerability in PHP
 and 70% of the Internet is vulnerable
 or something like that.
 Oh yeah, PHP is the name of the software that's
 vulnerable.
 What is PHP?
 Well, it's not really relevant to the hype,
 but okay, let me let SNL UK tell you about
 what you need to know about it:
 So, what exactly is PHP?
 Essentially, it's something to do with the
 Internet, Paddy.
 Thanks, Anya. Yes, PHP is essentially related
 to the way the Internet works, Anya.
 Thanks, Paddy.
 Seriously, if you're not a techie,
 that's all you need to know about what PHP does.
</details>

现在，AI 确实刚刚在 PHP 中发现了一个漏洞，在技术层面上这是真的；但你之所以能听说这件事，唯一的理由就是 AI 公司想让你听说。首先，截至我录制视频的周六（即「黑色十月」头条曝出四天后），据我们所知，目前还没有任何人真正因为这些漏洞遭到黑客攻击。这里有一段引言：「研究人员已对此进行了审查，并发现似乎没有哪个漏洞是普遍可靠的。有效利用仅在狭窄的实验室条件下可行，且利用行为依赖于在面向互联网的实例上不太可能成立的假设。尚未在野外观察到实际利用，尽管有多起利用尝试的报告，但这对于该评级的漏洞来说在预期之中。」引用完毕。这些确实是真实的漏洞，没错。而且假以时日，很可能会有人琢磨出如何利用它们发起稳定攻击。但到目前为止，我们还没看到任何此类证据。这里对互联网唯一的危险，是那些就 AI 黑客攻击有多危险对你撒谎的人。然而，这种炒作和虚伪甚至比那还要恶劣。

<details>
<summary>Original English</summary>
 Now, it is technically true that AI did just
 find
 a bug in PHP, but the only reason you're
 hearing about it
 is because the AI companies want you to.
 First off, no one we know as of time of writing
 on Saturday,
 four days after the Black October headlines.
 No one we know has actually been hacked
 because of these bugs yet.
 So here's a quote, "researchers have reviewed
 these
 and observed that none appears to be broadly
 reliable.
 Working exploit only under narrow lab
 conditions
 and exploitation depends on assumptions
 that are unlikely to hold on Internet-facing
 instances.
 Not observed exploitation in the wild,
 although there are multiple reports of
 exploitation attempt,
 which is expected for a vulnerability of this
 profile."
 Unquote. These are real bugs, yes.
 And given enough time, someone will probably
 figure out
 how to reliably attack people with them.
 We've seen no evidence of that so far.
 The only danger to the Internet here
 is the people lying to you about how dangerous
 AI hacking is.
 But the hype and the hypocrisy is even worse
 than that.
</details>

所以让我们再深挖一点。这里是公告页面上的两个漏洞 ID。这里则是它们在 PHP 官方漏洞数据库中的记录。顺便插一句，如果你看右侧这里，第二个漏洞在这个页面上只被标记为「High」（高危）而非「Critical」（严重），这是因为它在一套标准下被评为高危，在另一套标准下被评为严重。现在，忘了我说的这句吧，这一点根本不重要，但我必须指出来，否则有人又要在评论区抱怨了。我在说什么呢？反正他们横竖都会抱怨，但管他呢……

<details>
<summary>Original English</summary>
 So let's dig a little deeper.
 Here are the two bug IDs from the announcement
 page.
 And here they are in the database
 of official vulnerabilities for PHP.
 Quick aside, if you look at the right side here,
 the second bug is only marked high and not
 critical
 on this page because it's rated as high
 on one side of criteria and critical on another.
 Now, forget I said that, it's not important at
 all,
 but I have to point it out
 because otherwise someone's going to complain
 in the comments.
 What am I saying?
 They're gonna complain anyway, but what the
 Hell...
</details>

### 历史维度的漏洞常态：被选择性忽视的数据

现在，这看起来确实挺吓人，但这只是因为你缺少上下文。让我来给你看别人都没展示给你的东西。让我把那个严重漏洞页面的剩余部分给你看看。看吧，噢等等，底部写着什么？上面写着「第 1 页，共 8 页」。看，根据官方数据库，截至我录制本期视频时，在过去 20 年里，PHP 中被标记为「严重」（critical）的漏洞共有 142 个。之前的 140 个里面，非技术人员听说过几个？它们中有几个上过头条？零个。你听说这个漏洞的唯一原因，是因为 AI 公司想让你害怕 AI，而媒体想赚取点击量。就是这样，这就是全部原因。因为如果一个严重的 PHP 漏洞就配得上这种头条，那么平均下来，你每年会看到 7 次这样的头条。看，这里有两个是今年 8 月份的，大约两个月前。《Breaking Points》给它们做过头条专题吗？这里有五个是今年 5 月份的。这里还有五个是今年 4 月份的。你看到关于它们的任何头条了吗？没有，那是因当时没有来自 OpenAI 的公告博文推波助澜。

<details>
<summary>Original English</summary>
 Now, this certainly seems scary,
 but that's just because you're missing context.
 Let me show you what no one else is showing you.
 Let me give you the rest of that page
 of critical vulnerabilities.
 There you go, oh wait, what's there at the
 bottom?
 It says page one of eight.
 See, there have been, according to the official
 database,
 at the time that I'm filming this,
 142 vulnerabilities in PHP
 that have been marked critical in the last 20
 years.
 How many of the previous 140 have non-techies
 heard about?
 How many of them made headlines?
 Zero, the only reason you heard about this one
 is because the AI companies wanted you to be
 scared of AI
 and the media wanted to get clicks.
 That's it, that's the whole reason.
 Because if a critical PHP vulnerability
 justified these headlines, you would, on
 average,
 see such a headline seven times a year.
 See, look, here are two of them from August of
 this year,
 roughly two months ago.
 Did Breaking Points to a headline segment on
 them?
 Here are five from May of this year.
 Here are five more from April of this year.
 You see any headlines on those?
 No, that's because there wasn't an
 announcement post
 from OpenAI for those.
</details>

再看看这一个：CVE-2024-4577。它是在 2024 年 6 月 9 日公布的。到了 6 月 11 日，就有 1,700 台主机被实际感染。在 1,700 台主机遭到实际感染的那一周里，除了网络安全行业网站，有几家媒体报道了这个漏洞利用？零。那一周《Breaking Points》提过哪怕一次吗？零次。那个漏洞产生了真实的安全影响，媒体却鸦雀无声。而这一个漏洞没有任何安全影响，媒体却恐吓大众陷入毫无必要的恐慌。这就是彻头彻尾、不负责任的散播恐慌。

<details>
<summary>Original English</summary>
 So look at this one, CVE-2024-4577.
 It was announced on June 9th, 2024.
 By June 11th, there were 1,700 hosts
 that were actively infected.
 How many headlines were there, except
 from cybersecurity industry sites
 about that exploit, the week that 1,700 hosts
 were actively infected?
 Zero.
 How many times that week did Breaking Points
 say anything about it?
 Zero.
 That bug had a real security impact,
 and the media was silent.
 This one had no security impact,
 but the media scared people into needlessly panicking.
 This is irresponsible, fearmongering, full
 stop.
</details>

### PHP 的生态现状与「70%」统计的误导性

现在让我把话说清楚：PHP 在安全上就是个彻头彻尾的烂摊子。25 年多以来一直如此，至少可以追溯到 CVE-1999-0058，这是我能找到的 PHP 最早的远程代码执行漏洞。是的，我说的是 1999 年。它是 1999 年整个互联网上正式报告的第 58 个漏洞。我很确定自己还记得比这更早的，但在 Google 诞生之前的互联网上找东西简直是自讨苦吃。任何在乎安全的人都不会用 PHP。现在，这句话肯定会激怒很多人，但我说的是真心话。如果你在为网站选择工具时把安全哪怕当成过一条考量标准，你就绝不会选 PHP。

<details>
<summary>Original English</summary>
 Now let me be clear, PHP is a security dumpster
 fire.
 It has been for more than 25 years,
 going back at least to CVE-1999-0058,
 which was the earliest remote code execution
 bug
 in PHP I could find.
 Yes, I said 1999.
 It was the 58th officially reported vulnerability
 on the entire Internet in the year 1999.
 I'm pretty sure I remember ones earlier than
 that,
 but it's a pain in the neck to find things
 that happen on the web back before Google was a
 thing.
 No one who cares about security is using PHP.
 Now that statement's going to make a lot of
 people mad,
 but I mean it.
 If security is a criteria that you considered
 at all
 when deciding what tools to use for your
 website,
 you did not pick PHP.
</details>

但等等，新闻里不是说有 70% 的网站都容易受到这个漏洞攻击吗？是的，但这组统计数据从根本上具有误导性。我来给你打个类似的数据比方：全美 75% 的城市人口少于 5,000 人；全美 42% 的城市人口少于 500 人。互联网上的绝大多数网站，就像美国绝大多数城市一样，体量极小且几乎没有任何流量。它们往往用 PHP 是因为它便宜、搭建容易，而且建站者不懂别的。此外，还存在一整个免费或极低廉成本代管网站的公司生态，其中大量公司为了压低成本而采用 PHP。确实有少数像维基百科这样的大型网站早在远古时期就基于 PHP 起步，现在仍在用它，因为相比安全，它们更在乎成本或便利性。每个人有自己的选择吧，我想。但头条新闻却试图让你相信，这是一起影响大半个互联网的有史以来最恶劣的事件。根本不是。这不过是数百个 PHP 漏洞中的又一个而已，受到影响的大多是流量极小的小网站，或者那些比起安全更看重省钱的人。这绝非什么你需要操心或听闻的事情，它没有任何特殊之处。而且让我重申一遍：据我们所知，目前没有任何人因为这个漏洞遭到黑客攻击——利用这个漏洞的攻击一次都没有。

<details>
<summary>Original English</summary>
 But wait, didn't the news say that 70% of
 websites
 were vulnerable to this bug?
 Yep, but that statistic is ultimately
 misleading.
 Let me give you a similar statistic.
 75% of all the cities in the US have a
 population
 of fewer than 5,000 people.
 And 42% of the cities in the US have a
 population
 of less than 500 people.
 The vast majority of sites on the Internet,
 just like the vast majority of cities in the US,
 are tiny and get very little traffic.
 They tend to use PHP because it's cheap, easy
 to set up,
 and they don't know any better.
 Also, there's a whole ecosystem of companies
 that will host websites for free or very, very
 cheap,
 and a ton of them use PHP to keep their costs
 down.
 There are a few big sites like Wikipedia
 that started on PHP way back in the before
 times
 and are still on it because they care more
 about cost
 or convenience and security. To each their own,
 I guess.
 But the headlines would have you believe
 that this is the worst ever event
 that affects most of the Internet.
 It's not.
 It's just another in a series of hundreds of PHP
 bugs
 that mostly affect tiny sites with very little
 traffic
 or people who prefer being cheap to being
 secure.
 This is not something you should care about or
 hear about.
 There is nothing special about this.
 And let me reiterate, no one we know has been
 hacked
 by this - using this - at all.
</details>

而那些试图以此吓唬你的标题党混蛋，既无知又无耻：

>> 「另外，到这个地步，我们能不能从 Ed Zitron 及其团队那里得到哪怕一点点谦逊？比如，这显然不仅仅是为了其 IPO 散播恐慌而凭空捏造的炒作。虽然我理解人们会有相信这种说法的冲动，因为这些人是不值得信任的骗子。但到了这一步，我们差不多该摆脱这种想法了。我们已经过了那个阶段。我没看到来自 Zitron 的任何谦逊态度，他——」
>> 「那将是一个站不住脚的观点。」

我觉得，要是《Breaking Points》真的在乎谦逊，他们该去照照该死的镜子。

<details>
<summary>Original English</summary>
 And the clickbait-y assholes trying to scare you
 about this are both clueless and shameless:
 - Also, can we get a tiny bit of humility
 from Ed Zitron and his people at this point?
 Like, this is quite obviously not just made up
 hype
 in order to scaremonger for their IPO.
 Like, I understand why people had that impulse
 to believe that because these are untrustworthy
 scammers.
 But at this point, it's time we kind of shed
 that idea.
 Like, we're beyond that.
 I've seen no humility to all from Zitron who--
 - There'll be discredited idea.
 I think if Breaking Points actually cared
 about humility,
 they'd be looking at a f-----g mirror.
</details>

### 拼凑危机：eMudhra、Railway 与所谓「最坏一周」

在所谓的「黑色十月」中，他们抛出的下一个大问题是一家发音大概叫 eMudhra 的公司的一批 TLS 证书，这些证书最近被发现存在极其荒唐的不安全问题。别担心那意味着什么，也别担心它会影响到你。只要更新你的浏览器和手机，你就没事。问题是，为什么这能上新闻？因为媒体想制造出有一大堆倒霉事同时发生的假象，以支撑他们围绕 OpenAI 大吹特吹的那个 PHP 漏洞所编织的叙事。

AI 根本没有参与发现那些不安全证书。相反，是一个有着四年历史的健全性检查工具发现了问题。尽管 AI 公司大概不想谈论这个，但据犯下错误、此后已退出该整个业务的涉事公司称，很可能是 AI 造成了该问题。他们在 2025 年 4 月使用的生成证书的脚本中存在错误。虽然该公司没说他们是从 AI 那里获取的错误脚本，但几乎可以肯定是这样。如果他们认真查阅过权威来源的文档或示例，这种事根本不可能发生。

<details>
<summary>Original English</summary>
 The next big issue they bring up in the so-called
 Black October
 is a number of TLS certificates from a company
 that pronounced something like eMudhra 
 that were recently discovered to be
 ridiculously insecure.
 Don't worry about what that means. Don't worry
 about it affecting you.
 Just update your browser and your phone and you'll
 be fine.
 Question is, why did this make the news?
 Well, because the media wanted to make it look
 like
 there was a ton of bad things happening at once
 to support their narrative about the PHP bug
 that OpenAI was crowing about.
 AI was not involved in the discovery
 of the insecure certificates.
 Instead, it was a four-year-old sanity checking
 tool
 that found the issue.
 Although the AI companies probably won't want
 to talk
 about it, the chances are that AI caused that
 problem
 according to the disgraced company that made the
 mistake
 and has since quit the entire business.
 There was an error in the script they used
 in April of 2025 that generated the
 certificates.
 Now, the company doesn't say that they got
 the erroneous script from AI, but they almost
 certainly did.
 If they'd actually looked at the documentation
 or examples from reputable sources, this couldn't
 have happened.
</details>

此外，最近在一家供人们运行 AI 代码的名叫 Railway 的公司发生了一起安全问题——我甚至都不情愿称之为黑客攻击。我们不知道 AI 是否参与了其不安全架构的构建，尽管我怀疑很可能有。我简直不敢相信在今时今日，任何从事他们这种业务的公司居然会把解密后的客户密钥存放在其他客户可以读取的地方。所有人都应该离开那个平台。没有任何一家如此粗心大意的公司配得上你的业务。Railway 称他们认为攻击者使用了 AI，这当然听起来挺合理。但有趣的是，AI 似乎至少是这次入侵发生的部分原因：据报道，攻击者利用 Railway 的漏洞窃取其客户的密钥，然后利用这些密钥盗取加密货币，并在 AI 提供商那里刷爆账单。

随后，据报道有人在未借助 AI 的情况下，手动发现了名为 GitLab 的软件的一个漏洞。除了为了让这周看起来像是糟糕的网络安全灾难周之外，根本没有任何理由提及这件事。还有几起关于 AI 智能体访问银行账户的报道。那些同样不是黑客攻击，而是幼稚的客户主动将用户名和密码提供给机器人，而银行因此感到不快……各有其原因。我们稍后可能会谈到这一点。此外还有其他一些琐碎事件，但没什么不同寻常的。这绝不是什么前所未见的一周，也不是什么糟糕的一周。若不是制造恐慌的新闻媒体顺水推舟，迎合 AI 行业恐吓大众的欲望，你大概根本不会听说其中任何一件事。你当然也完全没必要去听说这些。

<details>
<summary>Original English</summary>
 In addition, recently there was a security
 issue
 - I hesitate to even call it a hack -
 at a company called Railway
 where people run their AI code.
 We don't know if AI was involved in the
 creation
 of their insecure architecture,
 although I suspect it probably was.
 I cannot believe that any company that does
 what they do
 in this day and age had decrypted customer
 secrets stored
 where other customers could read them.
 Everyone should leave that platform.
 No company that careless deserves your business.
 Railway says they believe that AI was used by
 their attacker
 and sure, that seems reasonable.
 Interestingly though, AI appears to be at least
 part of the reason for the hack.
 The attackers were reportedly exploiting
 Railway
 in order to steal keys from Railway's customers
 and then using those keys to steal
 cryptocurrency
 and run at bills of the AI providers.
 Then there was a vulnerability with a software
 called GitLab
 that was reportedly found manually without the
 help of AI.
 No reason to mention this at all except the
 security
 by making it look like a bad cybersecurity week.
 And there were some reports of AI agents
 accessing bank accounts.
 These weren't hacks either.
 They were naive customers who intentionally
 gave usernames
 and passwords to bots and the banks getting
 upset
 about it... for reasons.
 We might talk about that later.
 And there was some other stuff but nothing
 extraordinary.
 This was not an unprecedented week.
 It wasn't a bad week.
 Were it not for the fear-mongering press
 playing
 into the AI industry's desire to scare you,
 you probably wouldn't have heard about any of
 this.
 You certainly didn't NEED to hear about any of
 this.
</details>

### AI 对网络安全的真实负面影响

不过别误会我的意思：AI 确实会给计算机安全带来一些恶劣的后果。只不过这些影响并非标题党们想聊的那些。

首先，正如我怀疑 eMudhra 密钥生成脚本错误中的情况一样，AI 正导致大量不安全的代码被发布到生产环境中。而我们所有使用互联网的人，都将在很长一段时间内为此买单。

其次，大量受到惊吓的公司将向 OpenAI 和其他前沿实验室掏出大笔银子，订阅所谓的防护型 AI，用来防御网络免遭攻击型 AI 的侵害。这将是一笔巨大的资金浪费。我的意思是，想想看吧：OpenAI 甚至都无法防范自己的网络免遭自家 AI 训练机器人的攻击。然而媒体正极力确保这些公司受到足够多的惊吓，从而花钱向 OpenAI 购买防御服务；这会给这些公司一种虚假的安全感，并浪费大量本可用于有效得多的网络安全防御措施上的资金。

<details>
<summary>Original English</summary>
 Don't get me wrong though.
 AI does have some nasty implications for
 computer security.
 They're just not the ones that the clickbaiters
 want to talk about.
 First off, as I suspect was the case
 with the eMudra key generation script error,
 AI is causing a lot of insecure code to get
 shipped out there.
 And all of us who use the Internet
 are going to be paying for that for a long time.
 Second, a lot of scared companies are going to
 be spending
 a lot of money on OpenAI and other frontier
 labs
 to subscribe to protective AIs
 that are supposed to defend their networks
 against attacking AIs.
 This is gonna be a giant waste of money.
 I mean, think about it.
 OpenAI couldn't even defend their own network
 against their own AI trainee bots.
 But the press is seeing to it that the
 companies
 are scared enough to pay OpenAI for defense,
 which is gonna give the companies a false
 system security
 and it's gonna waste a ton of money
 that could have been spent
 on much more effective defensive cybersecurity
 measures.
</details>

而有效的网络安全防御措施将是迫切需要的。因为这些模型明确接受过数以千计的黑客场景训练。在发生「Hugging Face 事件」时，它们当时正是被训练来做这个的。而且这些模型很擅长重现它们接受过训练的场景。因此，就像 Railway 事件一样，将会有很多公司遭到坏人利用经过训练的黑客 AI 作为武器发起的攻击。这会消耗那些很可能已经不堪重负、预算不足的网络安全团队的大量时间和资源。

然而与流行叙事相反，这实际上并不会让那些高效的团队变得更不安全。这些 AI 系统在黑客技术上并不比靠以此为生的专业黑客更强。AI 根本不知道如何掩盖自己的行踪，因为这不在训练数据中；这就是为什么当它们进行黑客攻击时，会留下一地的痕迹。而专业黑客不会。

不妨这样看：你前门上的锁，容易被锁匠或受过锁匠技能训练的人在不用钥匙的情况下打开。自动撬锁工具的出现并不会让你变得更容易受到攻击，漏洞本身是一样的，它只是意味着能够利用该漏洞的人变多了。但正因为你知道锁是可以被撬开的，如果你认真对待安全问题，你就不会只依赖这一把锁；你会增加其他防范，比如在安全插销上加装插销锁、报警系统或摄像头。如果你真的担心，甚至可能会在窗户上加装铁条，并在房屋周围修筑围栏。或者，如果你是那种运行 PHP 的人，你的房间与外界之间大概除了一道纱门之外什么都没有。

<details>
<summary>Original English</summary>
 And effective defensive cybersecurity measures
 are going to be sorely needed.
 Because these models have explicitly been
 trained
 on thousands of hacking scenarios.
 That's what they were being trained to do
 when The Hugging Face Incident happened.
 And the models are good at replying scenarios
 they've been trained on.
 So, like the Railway incident,
 there are going to be a lot of companies
 that are going to be attacked by bad guys
 using a trained hacking AIs as weapons.
 That's gonna consume a lot of time and
 resources
 from cybersecurity teams
 that are likely already overworked and underfunded.
 Contrary to the narrative though,
 it really doesn't make effective teams any less
 safe.
 These AI systems are not better at hacking
 than the professional bad guys who do it for a
 living.
 The AIs just have no idea how to cover their
 tracks
 because that's not in the training data,
 which is why when they hack things,
 they leave evidence all over the place.
 The pros don't.
 Look at it this way.
 The lock on your front door is vulnerable
 to being opened without a key by a locksmith
 or by someone trained to do locksmithing work.
 The availability of auto lock picking tools
 doesn't make you any more vulnerable.
 The vulnerability is the same.
 It just means there are more people who can
 exploit
 that vulnerability.
 But because you know that locks can be picked,
 if you are serious about your security,
 you won't depend on just the one lock.
 You'll add other things like dead bolts
 into your safety latches, alarm systems or
 cameras.
 If you're really worried,
 you might even add bars on the windows
 and a fence around your property.
 Or if you're the kind of person that runs PHP,
 you probably have nothing between you
 and the outside but screen doors.
</details>

### 安全问题的根源：管理层漠视与真正的解决之道

根据我的经验，互联网上的大多数公司都不愿意为网络安全掏钱。实际上，让我说得更明确一点：大多数拥有商科学历的高管都不愿意为网络安全买单。这是因为从历史上看，遭遇黑客攻击并未伤害到股价；而且他们因泄露客户隐私信息而向政府缴纳的罚款，通常比组建一支优秀网络安全团队的成本还要低。这些公司、它们的安全团队及其客户都将面临艰难处境，因为它们恰恰属于 AI 训练所针对的那类容易下手的目标。但是，当 AI 黑客入侵你时，它会搞得一团糟，所有人都会注意到。很多在安全上偷工减料的公司很有可能已经被黑客攻陷了，只是它们自己浑然不知。市面上有大量工具可以帮你检测是否已被入侵，其中很多还是免费的；但你必须在入侵发生之前费心把工具配置好，否则它们的作用就像所有马都被偷走之后才去锁马厩门一样毫无意义。

<details>
<summary>Original English</summary>
 In my experience, most companies on the
 Internet
 don't wanna pay for network security.
 Actually, let me be even more specific.
 Most executives with business degrees
 don't wanna pay for cybersecurity.
 That's because getting hacked
 hasn't historically hurt stock prices.
 And the fines they have to pay the government
 for leaking customer's private information
 are generally less than what a good
 cybersecurity team costs.
 Those companies and their security teams
 and their customers are going to be in for a
 hard time
 because they are exactly the kinds of easy
 targets
 that the AIs are trained on.
 But when the AI hacks you,
 it makes a mess and everybody notices.
 Chances are a lot of these companies
 that skimp on security have already been hacked.
 They just have no idea.
 There are plenty of tools out there
 to help you detect if you've been hacked
 and a lot of them are free,
 but you have to go through the effort
 of setting the tools up before the hack happens
 or they're just as useful as locking the barn
 door
 after all your horses have been stolen.
</details>

我曾经在一个由我运行的系统中发现过一名黑客。我花了四个小时才注意到他、弄清他在干什么并封锁了他的访问权限。而之所以花了那么久，仅仅是因为他的初始攻击是在那天早上我的闹钟响之前发生的。他是通过我们母公司拥有并运行的一台服务器渗透进来的。事实证明，他在他们的网络里畅行无阻已很长时间，而他们自己一无所知；当我告诉他们遭到黑客入侵时，他们最初甚至拒绝相信。这种事情每天都在上演。

所以从某种角度来说，长远来看这些 AI 黑客对安全领域可能是一件好事，因为它会让那些安全做得糟糕的公司变得更加显眼和容易暴露。当然，前提是我们要让人们明白：真正的问题并非可怕的超人般的 AI，而是那些比起保护客户更看重削减员工成本的 MBA 们，以及那些毫无技术背景却坐拥庞大受众、对自个儿根本不懂的 AI 废话散播恐慌的人。如果我们能让人们更加重视合格的网络安全实践，那就太好了。好吧，除此以外，还得最终让所有人彻底弃用 PHP。好吧，还有最终让人们不再听信《Breaking Points》在 AI 问题上的谎言。虽然这些大概都不可能发生。

好吧，感谢收看。如果你有兴趣了解我今天在这里谈论的任何内容的更多信息，下方附有参考资料与来源链接。点赞和订阅按钮也在下面。我就顺嘴一提。希望大家下次继续收看。在那之前……出门在外请多加小心。

<details>
<summary>Original English</summary>
 I once discovered a hacker in a system I was
 running.
 It took me four hours to notice him, figure out
 what he was doing, and block his access.
 And it only took that long
 because his initial attack happened
 before my alarm went off that morning.
 He got in through a server that was owned and run
 by our parent company.
 Turns out he'd had to run of their network
 for a long time and they had no idea.
 And they initially refused to believe me
 when I told them they'd been hacked.
 That kind of thing happens all the time.
 So in a way, these AI hackers might be a good
 thing
 for security in the long run
 because it will make companies with poor
 security
 a lot more visible and obvious.
 That is, as long as we can get people to
 understand
 that the real problem isn't scary superhuman AI,
 it's MBAs who care more about reducing staff
 than they do about protecting their customers.
 And non-technical people with large audiences
 fearmongering about AI crap they don't
 understand.
 It would be nice if we could make people care
 more
 about competent cybersecurity practices.
 Well, that and finally get everybody moved off
 of PHP.
 Well, that and finally get people to stop
 listening
 to Breaking Points lying about AI.
 Like any of that's gonna happen.
 Oh well, thanks for watching.
 If you're interested in getting more
 information
 about anything I've talked about here today,
 links to references and sources are below.
 And so are the like and subscribe buttons. Just
 sayin'.
 Hope you'll tune in next time.
 Until then... Let's be careful out there.
</details>