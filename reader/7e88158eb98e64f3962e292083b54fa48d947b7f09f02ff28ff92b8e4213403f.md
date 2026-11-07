---
author: New York Times Podcasts
date: '2026-08-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qdXnvr5UQBc
speaker: New York Times Podcasts
tags:
  - password-manager
  - two-factor-authentication
  - passkey
  - cybersecurity
  - digital-hygiene
title: 密码时代的终结：从密码管理器到通行密钥的数字卫生指南
summary: 本文是纽约时报 Wirecutter 播客的访谈记录。隐私与安全技术专家 Max Eddie 与主持人 Rosie Garin 深入探讨了如何通过密码管理器、双重身份验证（2FA）以及新兴的通行密钥（Passkeys）来保障个人在线安全，克服‘安全疲劳’，逐步建立健康的数字卫生习惯。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Wirecutter
  - Apple
  - Google
  - Microsoft
  - FIDO Alliance
products_models:
  - 1Password
  - Bitwarden
  - Dashlane
media_books: []
status: evergreen
---
### 密码卫生的挑战

**麦克斯**: 起初，大家会说：“千万别告诉任何人，也别把密码写下来，它们都必须记在你的脑子里。” 后来，建议变成了：“使用密码管理器吧，如果你还想把它们记在脑子里，那你就做错了。” 再后来，又是：“你必须经常更改密码。” 但现在，我们实际上认为那并不是一个很好的做法。

<details>
<summary>Original English</summary>

**Max**: First it was like don't tell anyone or write down your passwords. They all need to live in your mind. And then it was use a password manager. You know, if you're trying to keep them in your mind, you're doing it wrong. And then it was like, you got to change your passwords all the time. And now we actually don't think that's a very good practice.

</details>

**罗茜**: 我是**罗茜·加林**，你正在收听的是 **Wirecutter** 节目。

<details>
<summary>Original English</summary>

**Rosie**: I'm Rosie Garin and you're listening to the Wire Cutter Show.

</details>

**罗茜**: 嘿，我是罗茜。今天我们要聊聊密码。等等，等等，先别跳过这一集，因为关于密码的对话怎么可能有趣呢？但我要说，第一，我的嘉宾**麦克斯·艾迪**是 Wirecutter 的高级撰稿人，他撰写关于数据、隐私、安全以及如何在线保持安全的文章。第二，是的，这确实是那种你可以告诉自己可以忽略的事情之一，但我们的生活现在都在网上。我们在网上银行转账、在网上约会、在网上购物。我们分享信用卡信息、社会安全号码。你懂我的意思。所以，如果你正在努力维护自己的隐私，从使用密码管理器开始是一个不错的起步。在广告之后，我们将与麦克斯·艾迪一起探讨这些内容，并对**通行密钥（Passkeys）**进行初步介绍。

欢迎回来。我今天的嘉宾是麦克斯·艾迪。麦克斯是 Wirecutter 负责隐私和安全领域的撰稿人。麦克斯已经上过两次我们的节目了，一次是讨论携带 **VPN** 旅行的重要性。如果你还没听过，去听听那一集。另一次是聊聊去年发表的一篇我非常喜欢的文章，名叫《我尝试在互联网上销声匿迹，但失败了》。那是一篇非常棒的文章。欢迎你。

<details>
<summary>Original English</summary>

**Rosie**: Hey, it's Rosie. Today we're talking about passwords. Wait, wait, wait, wait, wait, wait. Before you skip this episode, because how could a conversation about passwords possibly be interesting? I will say number one, my guest Max Eddie is he's a staff writer here at Wire Cutter and he writes about data, privacy, security, and how to stay safe online. And number two, yes, this is one of those things that you can tell yourself it's okay to ignore, but our lives are online. We bank online. We date online. We shop online. We share our credit card information, social security numbers. You get the picture. So, if you're going out of your way to retain your privacy, getting started with a password manager is a good start. More about those and a primer on pass keys with Max Eddie after the break. Welcome back. My guest today is Max Eddie. Max is a staff writer here at Wire Cutter who covers privacy and security. Max has been on the show twice now talking about the importance of traveling with a VPN. Check that episode out if you haven't. And another time to talk through an article published last year that I really loved called I tried and failed to disappear on the internet. That was a banger. Welcome.

</details>

**麦克斯**: 谢谢。很高兴能来到这里。

<details>
<summary>Original English</summary>

**Max**: Thank you. Always happy to be here.

</details>

**罗茜**: 很高兴见到你。今天我们将讨论提高在线安全性的三种主要方法：**密码管理器（Password Managers）**、**双重身份验证（2FA）**和**通行密钥（Passkeys）**。我想人们可能普遍知道为什么密码很重要，但你能不能简单概括一下，如果你没有良好的密码卫生习惯，你面临的最大风险是什么？

<details>
<summary>Original English</summary>

**Rosie**: Good to see you. Today we're going to talk about three main ways to increase your online safety. So, password managers, two-factor authentication, and pass keys. I think people maybe generally know why passwords are important, but can you just top line, what is the biggest risk you face if you don't have good password hygiene?

</details>

**麦克斯**: 我非常喜欢你所说的“卫生”这个词，因为卫生是一种习惯，是你一直在做的事情。是的。

<details>
<summary>Original English</summary>

**Max**: I I really like the way you put that cuz like hygiene is a habit. It's something that you do all the time. Yeah.

</details>

**罗茜**: 而且我认为在考虑安全时，你需要把它看作是改变习惯，改变你生活的方式。这听起来宏大而复杂，但关于密码、密码管理器和通行密钥的好处在于，这些东西实际上会让你的生活变得更容易。所以，如果你没有良好的密码卫生习惯，面临的最大风险就是你的账户可能会被别人掌控。

<details>
<summary>Original English</summary>

**Rosie**: And I think that that's kind of what you need to think about with security. Like you're changing habits. You're you're changing the way you live your life. And that sounds huge and complicated, but the nice thing about passwords, password managers, and pass keys like what we're talking about here, like this stuff actually makes your life easier. So the biggest risk that you face if you don't have good password hygiene is that your accounts could be taken over by somebody else.

</details>

**麦克斯**: 归根结底就是这样。连接你和你的在线账户之间的主要纽带就是密码以及围绕密码的其他技术。

<details>
<summary>Original English</summary>

**Max**: That's what it comes down to. You know, the main thing between you and your accounts online is passwords and other technologies around that.

</details>

**罗茜**: 我的意思是，这可以包括任何东西，从你的银行账户到你所拥有的其他一切。任何账户都是如此。

<details>
<summary>Original English</summary>

**Rosie**: And that I mean could be anything from your bank to your whatever. I mean, anything.

</details>

**麦克斯**: 我必须承认，为了写那篇关于如何消失在互联网上的报道，我的工作让我的密码使用量有点疯狂。我发现我自己大概有 **360 个密码**。

<details>
<summary>Original English</summary>

**Max**: I I admit my job makes my password usage a little insane for that how to disappear story. I discovered I have like 360 passwords.

</details>

**罗茜**: 那真的是太多的密码了。

<details>
<summary>Original English</summary>

**Rosie**: That's a lot of passwords.

</details>

**麦克斯**: 大多数人不会像我这样，但大多数人可能也拥有几十个密码，用于从银行账户、网上购物到工作账户等一切事务。

<details>
<summary>Original English</summary>

**Max**: Most people aren't like that, but most people probably have like dozens of passwords that you use for everything from banking to online shopping to your job.

</details>

**罗茜**: 所以，我们谈到了卫生、习惯养成。我们可能也应该谈谈疲劳。我的意思是，有一种现象叫做**安全疲劳（Security Fatigue）**，我认为它是真实存在的，而且带有风险，但同时人们也很容易产生共鸣。你能聊聊这个吗？

<details>
<summary>Original English</summary>

**Rosie**: So, we talk about hygiene, habit forming. We also probably should talk about fatigue. I mean, there's this thing you you talk about security fatigue and I think it's real and it's risky, but it's also very relatable. Can you talk a little bit about it?

</details>

**麦克斯**: 在过去的 20 年里，我认为人们对于自己在互联网上应该如何保持安全的建议感到非常困惑。起初是：“千万别告诉任何人，也别把密码写下来，它们都必须记在你的脑子里。” 后来是：“使用密码管理器，如果你想记在脑子里，那你做错了。” 接着是：“你必须经常更改密码。” 而现在我们其实认为经常改密码并不是一个好习惯。再接着是：“你必须在所有账户上添加双重身份验证。” 人们就会觉得：“什么是 2FA？你们现在又要求我学习这些新系统吗？” 现在我们又有了通行密钥，这是一种更新的技术。我非常理解那些对此感到倦怠的人。作为一个报道这个领域的撰稿人，从我的角度来看，这很令人兴奋，因为我们正在解决一个关于技术的根本性问题。密码本身就是一个根本性的问题。

<details>
<summary>Original English</summary>

**Max**: Over the last, let's say, 20 years, I think people have been feeling very jerked around by the advice that they're given about how to be safe on the internet. First, it was like, don't tell anyone or write down your passwords. They all need to live in your mind. And then it was use a password manager. you know, if you're trying to keep them in your mind, you're doing it wrong. And then it was like, you got to change your passwords all the time. And now we actually don't think that's a very good practice. And then it was you have to add two-factor authentication to everything. And then people like, what's 2FA? What are all these other systems you're now asking me to learn? And now we've got pass keys and even newer technology. I really empathize with people who are burnt out on this. From my perspective as someone who covers this, like it's exciting because we're we're fixing a fundamental problem about technology. Like passwords are a fundamental problem

</details>

**罗茜**: 展开聊聊为什么密码是一个根本性问题。

<details>
<summary>Original English</summary>

**Rosie**: and talk about why they're a fundamental problem.

</details>

**麦克斯**: 密码之所以是根本性问题，是因为人类很不擅长创造密码，而计算机却非常擅长猜测密码。一旦密码泄露，就会引发各种各样的问题。而且因为我们真的不擅长设置密码，我们发明了各种走捷径的方法。很多人曾对我说：“哦，我用密码没问题，我有一个好密码，在所有地方都用它。” 我以前也是这样。我记得我上大学的时候，我觉得自己很聪明，我有一个简单的密码用于不重要的网站，一个好的密码用于重要的网站。但如果你现在把这两个密码输入到专门计算破解时间的计算器里，结果显示破解只需几秒钟或几分钟。这太糟糕了，这就是问题所在。

<details>
<summary>Original English</summary>

**Max**: Well, passwords are a fundamental problem because we're bad at making them and computers are great at guessing them and if they are exposed they cause all sorts of problems and because we're really bad at making them we've come up with all sorts of shortcuts around that. So like a lot of people have told me it's like oh I don't have a problem with passwords. I have one good password that I use everywhere. And I was like this. Like I I remember when I was in college, I'm like, I'm so smart. I've got like a crappy password that I use for crappy sites and a good password I use for good sites. And if you plug either of those now into like the there are calculators that will tell you how long it takes for that password to be guessed, it's like seconds and minutes. Like it's

</details>

**罗茜**: 这真的很糟糕，这就是问题症结。

<details>
<summary>Original English</summary>

**Rosie**: it's bad. That is the problem.

</details>

**麦克斯**: 重复使用密码有什么坏处？如果你在重复使用密码，一旦该密码以任何方式暴露或被盗，所有使用它的网站现在就都变得脆弱不堪。因为聪明的攻击者在拿到你的凭据后，第一件事就是在多个网站上尝试登录。如果是针对性更强的攻击，他们可能会获取有关你可能拥有账户的网站的信息，有很多方法可以获取这些信息，然后他们就会以此为突破口。举个好例子，我就在这里自揭短处吧：曾经有一家新闻网站的评论区发生了大规模数据泄露，我用的那个密码恰好和我的 Facebook 密码是一样的。当那个泄露故事爆出来后，几个小时之内，就有人在 Facebook 上冒充我发帖。这很烦人。有人会想：“最坏的情况能怎么样呢？”但如果有人冒充你向你的家人要钱呢？你不需要是什么特别的大人物，这种事就可能发生在你身上。这真的很可怕，不仅会对你的个人声誉造成很大的损害，还会影响到你关心的每一个人。这是关于安全的另一个深刻理念：我们经常谈论保护自己。但如果由于安全疲劳或其他原因这无法激励你，那就想想你爱的人和你在乎的人，因为任何影响到你的事情都会影响到他们。如果你的电子邮件被黑，如果你的 Facebook 账号被黑，它就会被用来对付你最关心的人。

<details>
<summary>Original English</summary>

**Max**: What is it about reusing passwords that's not good? If you are reusing your password, if that password is exposed or stolen in any way, all of those sites are now vulnerable because the first thing that a savvy attacker is going to do when they get their hands on credentials is to try them on multiple sites. And if it's a more targeted attack where they might have some kind of information about the sites where you might have accounts and there's a number of different ways to get that information, then they have something to work off of. So, you know, if great example again, I'll I'll just air my dirty laundry here. So, there was this big data breach at a a news site in its comment section and that password was the same one I was using on Facebook. And when that happened, when that story broke within like a couple hours, someone was like making posts as me on Facebook. And that's annoying. Like people like, "Oh, what's the worst that could happen when someone impersonates me to my family and gets money from them?" you don't need to be anyone special for that to happen too. And that's really frightening like that that does a lot of damage not just like your personal reputation but like everyone you care about. And this is another like deep idea around security. Like we talk about it a lot in terms of protecting yourself. And if that doesn't motivate you because of security fatigue or or whatever, think about the people you love and the people you care about because anything that affects you is going to affect them cuz if your email gets hacked, if your Facebook account gets hacked, it will be used against the people you care the most about.

</details>

### 密码管理器的作用

**罗茜**: 好的，为此我们谈到了密码管理器。什么是密码管理器，为什么它很有用？

<details>
<summary>Original English</summary>

**Rosie**: Okay, so to that end we come to password managers. What is a password manager and why is it useful?

</details>

**麦克斯**: 密码管理器是一个可以为你保存、重放和创建密码的应用程序。它能做人类不擅长做的关于密码的一切事情。因此，你可以用它来创建非常非常长的密码。你可以为自己拥有的每个网站和服务创建唯一的密码，然后当你在登录这些网站时，你不需要记住它们，因为密码管理器会帮你拉出并自动填写密码。这解决了很多密码带来的问题。它不能解决所有问题，还有很多其他问题依然存在，但这是人们可以做的一件非常直接的事情，能让你在网络上更安全。就像密码管理器和双重身份验证，这是我在职业生涯中，每个安全专家都在告诉我的事情：如果人们做到了这两件事，他们的网络安全程度将会有客观的提升。

<details>
<summary>Original English</summary>

**Max**: So a password manager is an application that saves, replays and creates passwords for you. It does everything with passwords that we are bad at. So you can use it to create really really really long passwords. You can create unique passwords for every site and service you have and then you don't need to remember them when you go to those sites because the password manager pulls it up and fills it in for you. That fixes so much of the problem with passwords. It doesn't fix everything and there's a lot of other problems that remain, but it is a very straightforward thing that people can do that will make you safer online. It's like password managers, two-factor authentication. Those are the things that every security expert has been telling me my entire career. like if people do these things, they will be objectively safer online.

</details>

**罗茜**: 当我帮我妈妈设置好密码管理器时，这真的改变了她的生活。在此之前，她用的是一张边缘已经磨损的索引卡，上面的墨水也化开了，根本看不清。当时我就觉得一定有更好的方法。虽然拥有自己的离线系统没什么不对，但我想不出还有什么离线系统能比密码管理器更方便。离线系统确实有它的优势，对吧？比如没有人能偷走那张卡，那张卡是地球上最安全的东西。但密码管理器要灵活得多。当你由于某种原因去修改密码时，密码管理器应该能捕获该信息并自我更新。当你开始使用密码管理器时，还能获得其他一些隐藏的好处。最主要的一点当然是你的安全性更好了，同时你不用承受那么多的认知负担。你不必记住密码，只需要记住密码管理器的**主密码（Master Password）**即可。还有一些更细节的地方，比如密码管理器被配置为在匹配的网站上显示对应的密码。如果你在一个网站上，你知道自己有该网站的密码，但你的密码管理器没有弹出提示，那你可能正处于一个钓鱼网站上。这是一个细节，虽然这不一定是它的主要设计目的，但这是另一个提示你可能需要慢下来仔细查看正在做什么的线索。

<details>
<summary>Original English</summary>

**Rosie**: I think it changed my mom's life when I helped her get set up with a password manager because prior to that, she had like an index card fraying at the edges and you couldn't read them cuz the ink had bled and it was just like there has to be a better way. Yeah, there's nothing wrong with having your own system, but there's not a offline system that I can imagine like that that is easier than a password manager. Like it has its advantages, right? Like no one's going to get that card. That card is the safest thing on the planet, but a password manager is more flexible. When you go to change your password, for whatever reason, the password manager should capture that information and update itself. And there's other little things that when you start using a password manager, you get the benefit of like the main one of course is your security is better. You also don't have like as much cognitive load. Like you don't have to remember your passwords. You just need to remember the password for your password manager. But smaller things like your password manager is configured to show the password for the site that you're on. If you're on a site and you know you have a password for it and your password manager doesn't show up, you might be on a fishing site. It's a little thing like that. Like that's not even really its intended purpose, but it's another little clue that maybe you should slow down and take a look at what you're doing.

</details>

**罗茜**: 我以前还没想过这一点。除了存储密码并在网站上帮你填写密码之外，你还期望密码管理器做些什么？

<details>
<summary>Original English</summary>

**Rosie**: I had not thought about that. Are there things you could expect a password manager to do beyond just storing your passwords and helping you fill in when you're on a site?

</details>

**麦克斯**: 其中一个主要功能是它可以存储和检索任何敏感信息。例如，我把我的“已知旅客号码”（Known Traveler Number，机场快速安检预检时要用到的东西）存放在密码管理器里，因为我确实需要定期拿出来用，但我永远记不住它在哪里，所以它就直接存在我的密码管理器中。信用卡信息也在里面。虽然还有很多其他方法来进行自动填充，但密码管理器非常灵活，而且随时随地跟着我。所以这是我使用它的一个场景。

另外，密码管理器的一大作用是它们可以生成复杂、漫长且唯一的密码。这样你就不用自己动脑子想了，也不需要记住。你可以根据当时的需求更改密码生成的规则。它们非常非常灵活。

<details>
<summary>Original English</summary>

**Max**: One of the main ones is that it can store and retrieve any sensitive information. So, I put my known traveler number, the thing you're supposed to use for like pre-check when you go through airport security. I keep that in my password manager because I I do need to pull that out periodically and I will never remember where it is. So, it just it's in my password manager. You know, credit cards are in there, too. You know, there's a lot of other ways to do this kind of autofill stuff, but a password manager is very flexible and it's always with me. So, that's one thing that I use it for. One of the main things that password managers do is that they create complex, long, unique passwords. So, you don't have to do any of that and you don't have to remember any of that. And you can change the rules for how that's generated to whatever meets your needs at the time. They're very very flexible

</details>

**罗茜**: 比如字母、数字、特殊字符、以及超级特殊的字符。

<details>
<summary>Original English</summary>

**Rosie**: like letters, numbers, special characters, extra special characters.

</details>

**麦克斯**: 是的，没错。我喜欢的一个功能是，有些密码管理器甚至会移除相似字符。比如这是小写的“l”还是一个垂直的竖线？它会把容易混淆的字符去掉，你就不用担心这个了。或者它会使用完整的单词组合来创建密码短语，你有很多方法可以根据你的情况进行调整。我建议大家做的一件事是，尽量把密码设置得和网站所接受的限制一样长。我个人使用 30 个字符的密码，因为为什么不呢？反正我不需要记住它们。这就是密码管理器的用处，我花钱买它就是为了干这个的。

<details>
<summary>Original English</summary>

**Max**: Yeah, exactly. And one one of the features I love is like some password managers will actually remove similar characters. So is that a lowercase L or a vertical line? Gets rid of that so you don't have to worry about that. or it will create pass phrases that use like whole words or there are lots of different ways that you can adjust it to your situation, whatever makes sense. One thing I do recommend that people do is, you know, just go ahead and make it as long as the website will accept. Like I use 30 character passwords because why not? I'm not remembering any of this. That's the password manager stuff. I'm paying it to do that.

</details>

### 如何选择与迁移

**罗茜**: 是的。这很自然地引出了我们对推荐选择的讨论。关于密码管理器，Wirecutter 推荐哪些？

<details>
<summary>Original English</summary>

**Rosie**: Yeah. Okay. So, paying that is a I think a good segue into what your picks are. What does wire cutter recommend in terms of password managers?

</details>

**麦克斯**: **1Password** 是我们测试过的最好的密码管理器，而且已经保持这个地位很长一段时间了。1Password 非常易于使用，在很多方面使用起来甚至是一种享受，它在这方面完全把竞争对手甩在了身后。它是使用密码管理器最简单、最友好的方式。它会引导你完成整个设置过程。它在管理用于访问的主密码方面也做了一些非常独特的事情，虽然与其他产品有些不同，但仍然非常直观，而且更加安全。大体上，人们似乎能够理解并学会使用它，这很棒。

我们还推荐 **Bitwarden** 作为免费的密码管理器选择。它也有付费订阅服务，这同样是一款非常优秀的密码管理器。它是开源的，虽然不像 1Password 那样华丽和流畅，但在其本职工作上非常出色。这就是我自己在用的那款。

安全领域的一个大真理是，即使是一个不那么好的密码管理器，也比没有密码管理器要好，而且大多数密码管理器都很棒。所以，如果你已经在使用 Google 或 iPhone 中内置的密码管理器，那很好，如果你愿意，继续用就行。但我们推荐的第三方密码管理器拥有更多功能，更易于使用，并且能做到内置管理器做不到的事情。

<details>
<summary>Original English</summary>

**Max**: So, one password is the best password manager we've tested and has been so for quite a while. One password is just very easy to use, almost a pleasure to use in many ways that it just blows the competition out of the water in that respect. It is just the simplest, friendlyest way to use a password manager. It'll walk you through the whole process of it. It also does some very unique things with how it manages your password to access it. It's a little bit different than others, but it's still pretty intuitive and it's more secure. And by and large, it seems that people are able to figure it out and work with it, which which is great. We also recommend Bit Warden as a free password option. It also has a paid subscription, and that's just another really good password manager. It's open- source, and it's not as flashy and slick as one password, but it is very good at what it does. That's the one I use. A big truth in security in general is like even a not good password manager is better than no password manager at all and most password managers are good. So, you know, if you've already been using the built-in password manager in Google or in your iPhone or what have you, that's great. Stick with it if you want to stick with it. But the password manager that we recommend have more features. They're easier to use and they can just do things that those default password managers can't.

</details>

**罗茜**: 我用 **Dashlane** 已经有一段时间了。它挺好的。我的意思是它作为一个密码管理器能正常工作。我曾考虑过换用别的东西，但我一直被“从一个密码管理器迁移到另一个密码管理器”的想法吓到了。我能指望的最好结果是不是只能全部重新开始？

<details>
<summary>Original English</summary>

**Rosie**: I've been using Dashlane for a while. It's fine. I mean it's a password manager and it works. I have thought about using something else, but I've been intimidated by the idea of migrating from one password manager to another is the best I can hope for there kind of starting over.

</details>

**麦克斯**: 不，在密码管理器之间迁移非常简单。每个密码管理器都会允许你从另一个密码管理器导入和导出密码。这实际上是我在最近一轮测试中重点测试的内容之一：这个过程有多容易？这些产品在迁移过程中有什么难点？大多数情况下，它的工作原理是：你点击导出，它会吐出一个包含你所有密码和登录信息的电子表格，然后你打开新的密码管理器，把文件拖放到新软件里，它就会自动完成剩下的工作。

我要借此机会提醒大家一件事：**导出的文件在用完后一定要删掉**。因为那个文件里有你所有的明文密码，你绝对不希望它留在电脑里。

<details>
<summary>Original English</summary>

**Max**: No. Um to move between password managers is very straightforward. Every password manager will let you import and export passwords from another password manager. This was actually one of the things I tested in my most recent round of testing was how easy was that process? What what was hard about it for these products. Most of the time how this works is you hit export, it spits out a spreadsheet of all your passwords and login information, and then you go to your new password manager, you drag and drop it on there, and it does the rest. I will take this opportunity to just remind people something. Delete that file afterward because that file has all your passwords in it. You really don't want that.

</details>

**罗茜**: 还要清空垃圾桶。

<details>
<summary>Original English</summary>

**Rosie**: Empty the trash.

</details>

**麦克斯**: 是的，绝对要。然后，我总是鼓励人们对于这些事情不用操之过急。感觉上好像你必须快速做出巨大改变，但如果你正在从一个密码管理器迁移到另一个，你可以先试用一段时间。看看它是否获取了你所需要的所有数据。你有没有遇到什么问题？过了一段时间，根据你的需要，你就可以开始删除和关闭旧的密码管理器了。没有理由非得一下子把它们全部扔掉并马上完成。

<details>
<summary>Original English</summary>

**Max**: Yes, absolutely. And then, you know, I always encourage people to take their time with stuff. It often feels like you have to make big changes really fast. If you're migrating from one password manager to another, try it out for a while. See if it got all the stuff that you need. Do you have any problems? And then after however long you need, then you can start deleting and shutting down your old password manager. There's no reason that you got to like dump it all and do it all at once.

</details>

**罗茜**: 另外，我想知道，因为我使用的是 Dashlane，但我同时也使用 iPhone 自带的密码管理器。有什么理由让我不应该同时使用多个密码管理器吗？

<details>
<summary>Original English</summary>

**Rosie**: In addition to that, I'm wondering because I use I use Dashane, but I also use the password manager that comes on the iPhone. Is there any reason I shouldn't be using more than one?

</details>

**麦克斯**: 我认为从组织整理的角度来看，只用一个是更容易让你知道自己的密码存在哪里。

<details>
<summary>Original English</summary>

**Max**: I think that it's just easier for you to know where your passwords are

</details>

**罗茜**: 在结构上更明确。

<details>
<summary>Original English</summary>

**Rosie**: organizationally.

</details>

**麦克斯**: 对。再次重申，如果这种方式对你有效，那就可以，我不会说不让你这么做。但如果你遇到类似“我不知道那个密码在哪里，我知道我创建过，但我不记得它存哪儿了”的情况，这就会成为一个问题。我们推荐的所有密码管理器都是基于云端的。当你将它们安全地存储在云端时，它们在你的所有设备上都是随时可用的。这样就解决了你刚才说的问题，对吧？你知道它就在那个密码管理器里，而密码管理器存在于你所有的设备上。

<details>
<summary>Original English</summary>

**Max**: Yeah. And again, like if it works for you, it works for you. And I'm not going to tell you otherwise. But if you're ever in a situation where you're like, I don't know where that password is. I know I have it, but I don't know where it is. That can create a problem. And all the password managers that we recommend are cloud-based. When you have them stored on the cloud securely, they're available on all your devices all the time. So, that sort of gets around the problem you're talking about, right? You know that it's in the password manager and the password manager is on all of your devices.

</details>

**罗茜**: 所以，当我们谈到慢慢迁移，或者只是从不用密码管理器过渡到使用它时，我们需要一次性更改所有密码吗？

<details>
<summary>Original English</summary>

**Rosie**: So, when we talk about migrating slowly or even just getting started from not using a password manager to using one, do you need to change all of your passwords at once?

</details>

**麦克斯**: 不，绝对没必要。

<details>
<summary>Original English</summary>

**Max**: No, absolutely not.

</details>

**罗茜**: 那样做也太让人望而生畏了。

<details>
<summary>Original English</summary>

**Rosie**: That's also intimidating.

</details>

**麦克斯**: 这极其令人望而生畏。我实际上认为最好的方法是划分优先级，先解决最重要的事情。**网上银行**、**社交媒体**，还有一个常常让人们感到意外的，是你的**个人电子邮件**——或者你使用最频繁的那个电子邮箱。你绝对应该在这些账户上加上最强的安全保障。因为在任何网站上都有“忘记密码”的功能，如果攻击者能够控制你的电子邮件，然后使用那个“忘记密码”的工具，他们就可以开始接管你所有的其他账户，几乎没有什么能阻止他们。所以这是第一位的：整理好你的个人电子邮件安全。

然后，我觉得慢慢来完全没问题。比如当你在浏览各个网站时，退出来重新登录，让密码管理器随手捕获并记录它。我们推荐的大多数密码管理器都有非常有用的工具，可以识别弱密码、重复使用密码和已泄露的密码。所以利用好这些工具，先从已被泄露的密码开始修改，因为那些密码是你确切知道已经被流传在外的。修复这些密码，然后顺着列表往下做，也许可以设定一个计划，比如每周四更新五个密码。

<details>
<summary>Original English</summary>

**Max**: It's hugely intimidating. I actually think the best way to go about this is to prioritize the most important things. Banking, social media, one that surprises people, your personal email or whatever email you use the most. You absolutely should be putting the most amount of security on that. The forgot my password function on any website. If a attacker is able to get a hold of your email and then use that forgot my password tool, they can just start taking over all your accounts and there's very little to stop them. So that's like number one. Get your personal email sorted out. And then I think it's fine to you know move slowly like as you go to websites log out log back in let the password manager capture it as you go. Most of the password managers that we recommend have very useful tools that can identify weak reused and breached passwords. So use those tools. Start with the breached passwords. Those are the ones that you know are out there somewhere. So fix those and then work down your list of stuff and maybe set a day like every Thursday I update five passwords or what have you.

</details>

**罗茜**: 卫生习惯。

<details>
<summary>Original English</summary>

**Rosie**: Hygiene.

</details>

**麦克斯**: 是的。如果你试图一次性完成所有事情，你会感到倦怠。我认为人们在面对个人安全时最糟糕的做法就是放弃。我们总觉得事情失去了控制，有巨大的外部力量在与我们对抗，但实际上你在这件事上拥有很大的自主权，它可以真正赋予你掌控安全的能力。

<details>
<summary>Original English</summary>

**Max**: Yeah. You know, if you tried to do it all at once, you're going to burn out. And I think the worst thing that people can do with personal security is is just give up. It always feels like we're out of control and these huge forces are pushing against us, but actually you have a lot of agency in this stuff and it can actually really empower you.

</details>

### 密码管理器高级技巧

**罗茜**: 好的，快速回顾一下。密码，它们真的很烦人。但密码管理器能帮上大忙。现在很多手机里都集成了它们。麦克斯在 Wirecutter 网站上有一些非常棒的推荐。网络安全总是在演变，感到安全疲劳是非常非常正常的。我们一步一步来，采用一些安全措施总是比什么都不用要好。所以去试试密码管理器，试试双重身份验证（2FA），尽量保持安全。

麦克斯，在你的关于密码管理器的文章中，提到了四个额外的建议，可以帮助人们充分利用密码管理器。我想梳理一下。第一点你之前提到了，就是**创建超长密码**。

<details>
<summary>Original English</summary>

**Rosie**: Okay, quick recap. Passwords, they're a real pain. And password managers can help. They're integrated in many phones now. And Max has some great recommendations on the Wire Cutter website. Online security is always evolving and it's very, very real to feel fatigued. Um, baby steps. Using some measures is always better than using nothing. So try out password managers, try out two-factor authentication or 2FA, and stay as safe as you can. Now, Max, in your article on password managers, you have four additional tips to help get the most out of your password manager. I want to run through those. The first you mentioned before, which is creating extra long passwords.

</details>

**麦克斯**: 是的，既然你的密码管理器在承担这些繁重的工作，为什么不把密码设置得尽可能长、尽可能复杂呢？需要注意的是，并非每个网站都能很好地支持超长密码。时至今日，仍然有一些网站不允许你设置超过 8 个字符的密码。我简直不敢相信这些网站还在运营，这太疯狂了。但总的来说，尽量让密码变得越长、越复杂、安全性就越好。

<details>
<summary>Original English</summary>

**Max**: Yeah, you know, your password manager is doing the heavy lifting. Why not make it as long and as crazy as you want? Um, the caveat here is that not every website is cool about this. There are to this day still websites that won't let you do longer than eight characters. And I cannot believe these are still in business. Like that's insane. But in general, make it as long as you can because you don't have to worry about it. And the longer the more complex, the better.

</details>

**罗茜**: 第二个建议是关于**安全地共享密码**和其他信息的。聊聊这个。

<details>
<summary>Original English</summary>

**Rosie**: The second tip here is about securely sharing passwords and other information. Talk about that.

</details>

**麦克斯**: 是的，密码管理器通常内置了向其他人共享密码或你存储在其中的任何其他信息的工具。通常是共享给密码管理器的其他用户。所以如果你想这样做，你可能必须让家人加入家庭计划，但也不全是这样。这能给共享增加一些保护。

你必须始终记住，任何东西一旦离开你的控制，别人就可能用它做出不好的事情。所以不要把密码分享给你不信任的人。密切关注密码状态，使用软件提供的限制访问的工具。另外作为延伸，有些密码管理器甚至设有帮助家庭成员从已故亲人那里**继承密码**的机制。你肯定不想被锁在父母或祖父母的账户之外，这实际上是一个非常实用的功能。

<details>
<summary>Original English</summary>

**Max**: Yeah, password managers usually have tools built in to share passwords or any other information that you have stored in the password manager with other people. Typically other users of the password manager. So you like you might have to get your family on a family plan if you want to do this, but not all the time. And it puts some protections around it. Now you always got to keep in mind that anytime something leaves your control, someone can do something bad with it. So like don't share it with people you don't trust. Keep tabs on it. use the tools that they provide to limit its access, but just be aware that, you know, you only want to share it with trustworthy people. An extension of this is that some password managers are set up to actually help family members inherit passwords from people that have passed on. You know, you don't want to get locked out of your parents or grandparents accounts. This is actually a very useful thing to do.

</details>

**罗茜**: 你提到了“保护你的密码免受窥探”。你指的是什么？对于密码管理器一个很自然的担忧就是，它像是一个“单点故障”——如果有人攻破了你的密码管理器，他们就得到了你的一切。

<details>
<summary>Original English</summary>

**Rosie**: You have protecting your passwords from prying eyes. What did you mean by that? A very understandable concern about password managers is that it's like a single point of failure. Like if someone can get your password manager, they get everything. And that's very understandable.

</details>

**麦克斯**: 这完全可以理解。但你可以采取很多措施来防止这种情况发生。比如你可以给密码管理器加上双重身份验证（2FA），这样即使有人得到了你的主密码，他们依然进不去你的数据库。我们推荐的所有密码管理器都使用**端到端加密（End-to-End Encryption）**，所以即便服务商自己也无法访问你的数据。这些安全防线都是为了保护你的信息。

那么，如果密码管理器在你的手机上，而手机不在你手里了呢？这是一个大问题。如果你的手机被没收，或者没有妥善锁好，你得确保自己有所防备。查看一下你的密码管理器要求你重新进行身份验证的频率，将其设置为适合你的较低时间。也许是每天一次，也许是每几个小时，这样每隔一段时间，你确实需要输入主密码来证明你就是你。

还要学会使用帮助你定位和保护丢失手机的工具，苹果和谷歌都有类似服务，非常强大有用。当你去旅行时，可以考虑完全登出你的密码管理器，等到到达安全地点后再登录。如果你在手机解锁的状态下丢失了它，那可能会暴露你的很多信息。1Password 还有一个类似的工具叫做“旅行模式”，可以限制在特定情况下哪些密码在本地可用。

我们还建议学习如何临时禁用手机上的**生物识别（Biometrics）**。面部识别或指纹解锁确实很方便，而且很安全，但这可能会违背你的意愿被强行执行。比如有人抢走你的手机，对准你的脸，这样就解锁了手机；或者强行把你的手指放在指纹传感器上。所以大多数手机现在都有临时停用生物识别的方法。在任何你认为手机可能离开你身体的情况下（比如机场安检，或者在音乐会等陌生而拥挤的排队场所），为什么不花点时间临时禁用生物识别呢？一旦你手动输入一次密码解锁后，生物识别功能就会自动重新启用。这非常简单，但思考你的设备在脱离控制时会发生什么非常重要，这超出了密码管理器的范畴。

<details>
<summary>Original English</summary>

**Max**: There's a lot of things you can do to keep that from happening. You're going to put 2FA on your password manager so that even if someone gets your password, they're not getting into your password manager. All the password managers that we recommend use end toend encryption so they can't even access your data. Like these are the things that are out there to protect your information. Now, what happens when it's on your phone and then your phone is not in your hands anymore? That's a big problem. So, if your phone is confiscated or, you know, it's not properly secured, you want to make sure you're doing something about that. So, look at how often your password manager requires you to reauthenticate, set that to something low that works for you. Maybe it's every day, maybe it's every 44 hours, what whatever works for you. So that every now and again, you do actually have to put your password into your password manager to prove that you're you learn how to use the tools that help you track and secure stolen or lost phones. Both Apple and Google have this for their devices. They're very powerful. They're very useful. When you're traveling, consider logging out of your password manager altogether and logging back in when you get to a, you know, a safe location. If you lose your phone or your phone is stolen while it's unlocked, that can expose a lot of your information. So, just don't even have that on there. One Password has a similar tool called travel mode that lets you limit what passwords are available and what circumstances. We also recommend learning how to temporarily disable biometrics on your phone. So, biometrics are really convenient and great. Like, it saves you a lot of time and they're very secure, but it can be done against your will. like someone could snatch your phone, hold it up to your face, and then that could open your phone or someone can put your finger on the fingerprint reader. So most phones now do have a way to deactivate biometrics temporarily. Any situation where you think your phone is going to leave your person? So like airport security, you're in like a really long line in a place you don't know, like you're at a concert or something, why not just take a minute to disable biometrics temporarily? And once you put in the passcode, biometrics are back on. So it's very very simple but it's always important to think about what happens to your devices and this is beyond password managers. So excuse me but you always want to think about what you what is happening to your devices when you don't have control of them.

</details>

### 双重身份验证

**罗茜**: 最后一个建议是在你逐步升级密码时，在账号上启用双重身份验证（就是你刚才提到的 2FA）和通行密钥。在你具体解释这些之前，我想先暂停一下，因为你在网站上写了另一篇很棒的文章，名为《通行密钥是新的密码，你现在就应该开始使用它们》。这篇文章详细介绍了什么是通行密钥以及它们为什么重要。所以我想休息一下，在广告之后我们再深入探讨。我们马上回来。

欢迎回来。我今天的嘉宾是麦克斯·艾迪。这一集关于密码卫生以及如何在网上让自己更安全。在休息前，我们讨论了使用密码管理器的重要性，以及它如何帮助你整理密码以保持安全。现在我想聊聊双重身份验证 2FA 以及我最近经常听到和看到的一个新工具：通行密钥。告诉我们你所知道关于双重身份验证的一切以及它为什么有用。或者说不用“一切”，因为你懂的太多了。

<details>
<summary>Original English</summary>

**Rosie**: The last piece of advice here is enabling two-actor authentication to FA as you have referred to it and pass keys on your accounts as you go through and upgrade your passwords. I want to pause before you explain those because you wrote another great article on the site called pass keys are the new passwords. You should start using them now. And that goes into detail about what pass keys are and why they're important. So I want to take a quick break and dig deeper into that on the other side. We'll be right back.

Welcome back. My guest today is Max Eddie, a staff writer here at Wire Cutter who covers privacy and security. This episode is about password hygiene and how to keep yourself a bit safer online. So before the break, Max, we discussed the importance of using a password manager and all of the ways it can help you organize your passwords to stay safer online. And now I want to talk about twofactor authentication, 2FA, and a new tool I've been seeing and hearing about more and more, pass keys. So tell me everything you know about two-factor authentication and why it's useful. Or maybe not everything, cuz you know a lot of stuff.

</details>

**麦克斯**: 对于大多数人来说，2FA 就是你在输入密码之后要做的另一件事。例如，你必须输入发送到手机上的验证码，或者通过应用程序生成的代码，或者做其他事情。很多人把它看作是“双重”，就是你必须做的第二件事。从理论上讲，身份验证有三种不同的维度来证明你是你：**你所知道的东西（Something you know）**、**你所拥有的东西（Something you have）**以及**你本身代表的特征（Something you are）**。

“你所知道的东西”就是密码，它存在于你的脑海中。“你所拥有的东西”比如你的手机。当你在手机上使用 Duo、Google Authenticator 或 Authy 等 2FA 应用程序时，这证明了你拥有自己的手机。“你本身代表的特征”是指生物识别，比如指纹扫描或面部扫描。当我们从这三者中选择两个结合在一起时，它们是不同类型的身份验证，攻击者极难同时获取这两者，这就是双重身份验证——用两种不同的维度来保障账户的安全。

<details>
<summary>Original English</summary>

**Max**: So for most people 2FA is like another thing that you do after you enter your password. So you'll have to enter a code that's sent to you on your phone or generated by an app or you'll have to do some other thing. So a lot of people look at it's like oh two factor it's your second thing you have to do and this is where it gets philosophical. It's actually from this sort of theory of authentication where there's three different ways to authenticate yourself to anything else. There's something you know, something you have, and something you are. So something you know is a password. It lives in your brain. You know it. Something you have is like your phone. When you are using a 2FA app on your phone like Duo or Google Authenticator or Authie, that is proving that you have your phone. That's the thing you have. And something you are is biometrics like a fingerprint scan or a face scan. So when we take two of those three and put them together, they're different kinds of authentication and it's really unlikely that an attacker would be able to get both of them and that's two-factor authentication. Two different factors to secure your accounts.

</details>

**罗茜**: 艾迪教授，那么 2FA 有什么使用局限需要注意吗？因为它听起来已经非常非常安全了。

<details>
<summary>Original English</summary>

**Rosie**: Professor Eddie, what so does 2FA have any limitations then to bear in mind? Cuz it sounds very very secure.

</details>

**麦克斯**: 它确实非常非常安全。我真的想强调一下，正如我谈到密码管理器时所说的那样，虽然我们要开始讨论 2FA 的缺点，这些缺点是真实存在且需要被理解的，但任何 2FA 都比没有 2FA 要好，就像不完美的密码管理器也比完全不用要好一样。如果大家不能从这期节目里带走别的，请至少用上密码管理器并开启 2FA。只要你们中有一个人这么做了，我今晚睡觉都能踏实得多。

2FA 的一大缺点是，如果你缺少了这第二个维度，如果你的这件备用设备不在身边，你就会面临无法轻松登录的窘境。比如，如果你使用手机上的 APP 来生成 2FA 动态码，而手机刚好不在身边，你就很难登录你的账户了。

不过这有很多规避的办法。最简单的方法之一就是创建所谓的**备份验证码（Backup Codes）**。这通常是由网站生成的一串数字和字母，你可以把它们存在安全的地方、打印出来，或者存放在你密码管理器中非常安全的地方。在紧急情况下你可以输入这些备份验证码，证明你的身份以绕过身份验证。

2FA 的另一个重要问题是，某些类型的 2FA 可以被拦截。例如，如果你通过手机短信接收验证码，攻击者完全有可能拦截这条短信并在你使用之前将其用掉。因此，我们通常告诉大家**尽可能不要使用基于短信（SMS）的双重验证**。不过无论好坏，它依然是目前最常见的 2FA 形式。再次重申，不完美的 2FA 也比没有强。

此外，有些 2FA 可以被钓鱼。如果我在手机上生成了验证码，但我却把它输入到了一个钓鱼网站里，那这没有用。现在坏人也拿到了这个验证码。虽然这些动态验证码有时间限制，但这些钓鱼攻击设计得非常巧妙，它们完全有可能得手。所以在输入这些信息时一定要非常小心。我们之前也说过，有些生物识别身份验证可能会在违背你意愿或你不知情的情况下发生，比如在非自愿的情况下读取你的面部或指纹。

<details>
<summary>Original English</summary>

**Max**: It it is very very secure and I I really want to emphasize like I said with password managers you know we're going to start talking about the drawbacks of 2FA which are real and important to understand but any 2FA is better than no 2FA in the same way that even a a mediocre password manager is better than no password manager. So really want to underline if you take nothing from this please just get a password manager and turn on 2FA. I will sleep so much better if just one of you does it. So the the big drawback of 2FA is that if you don't have your second factor, if that other thing is not available to you, you're not going to be able to easily log in. So if you are, for example, using an app on your phone to generate 2FA codes and you don't have your phone, then you will not very easily be able to log into your account. A lot of caveats to this. One of the easiest ways to prevent this from happening is to create what are called backup codes. These are a list of numbers and letters typically that are generated on whatever site it is you have an account and you store them someplace safe, print them off, put them in your password manager someplace very safe because you can enter these codes in an emergency, prove who you are and get past a lot of the extra layers of security. Another big concern with 2FA is that some kinds of 2FA can be intercepted. So, for example, if you're getting a code sent to your phone, it is possible that someone could intercept that and then use it before you can use it. So, in general, we tell people not to use 2FA over SMS. That's by text message whenever possible. For better or for worse, it is probably the most common kind of 2FA. And again, bad 2FA is better than no TOFFA at all. Along with a 2FA that can be intercepted, some 2FA can be fished, right? So if I'm generating codes on my phone, if I put that into a fishing site, doesn't matter. Now the bad guy has it. They can use it. There's a time limit on these, but these attacks have been very well conceived. They will probably work. So always be very careful about where you're putting in this information. We said this earlier, but some kinds of 2FA could be done without your knowledge or consent. Like if it's biometrics, your face could be read or your fingerprint could be read without you necessarily wanting or knowing that that was happening.

</details>

**罗茜**: 我在电影里看到过这种情节。

<details>
<summary>Original English</summary>

**Rosie**: I've seen that in the movies.

</details>

**麦克斯**: 是的。

<details>
<summary>Original English</summary>

**Max**: Yeah.

</details>

### 通行密钥的崛起

**罗茜**: 接下来聊聊通行密钥（Passkeys）。我一直在听到关于通行密钥的消息。但我不得不承认我还没有真正尝试过。什么是通行密钥？它们是如何运作的？

<details>
<summary>Original English</summary>

**Rosie**: Moving over to pass keys. I'm been hearing about pass keys. I admittedly have not really waited into this yet. What is a pass key? How are they developed?

</details>

**麦克斯**: 在技术层面，通行密钥是一种数字凭证，使用**非对称密钥加密（Asymmetric Key Encryption）**向网站安全地证明你的身份。

<details>
<summary>Original English</summary>

**Max**: On a technical level, a pass key is a digital credential that uses asymmetric key encryption to securely identify you to a website. You don't need to know.

</details>

**罗茜**: 那个概念我是知道的，但它在实际使用中究竟是什么样子的？

<details>
<summary>Original English</summary>

**Rosie**: Well, that I know, but like what else is it? Yeah.

</details>

**麦克斯**: 是的。这就是它有点微妙的地方，因为就像《黑客帝国》里说的，没有人能被直接告知通行密钥是什么，你必须亲眼见识一下。所以你可以去你可能已经拥有账号的 Google 账户上，创建一个通行密钥体验一下。或者去我们在 Wirecutter 上写的文章里看看截图，我们一步一步地展示了整个流程，你可以直观地看到它长什么样。

我真的认为，一旦人们亲手尝试并对其有了任何程度的了解，它的价值就会变得显而易见。通行密钥和密码很像，它们都是无形的，保存在你的设备和云端。但与密码不同的是，你再也不需要手动输入它了。所以，这是一种无需输入密码就能向网站验证你身份的方法。

它有很多好处。首先也是最明显的一点是它是一次非常安全的加密交换。这个通行密钥不会被忘记，也非常难被攻破。如果网站遭遇了数据泄露，黑客也无法获得你的通行密钥，因为是你自己保存着它。登录时需要额外的身份验证，比如输入手机的 PIN 码，或者进行面部或指纹扫描。这就增加了多层安全性。同样重要的是，**每个通行密钥仅能与你创建它的那个特定网站配合使用**。这让它几乎无法被钓鱼，也无法以任何方式被克隆。

<details>
<summary>Original English</summary>

**Max**: Yeah. And this is where it gets kind of tricky because much like the Matrix, no one can be told what a pass key is. You kind of have to see it for yourself. So go to Google where you probably already have an account, create a Pasi, try it out. Go to our story on Wire Cutter. Take a look at the screenshots. We walk you through the whole process so you can see what it's like. I really think that once people see it and get any kind of familiarity with it, the value becomes immediately obvious. A pass key is a lot like a password. It's intangible. It lives in your devices and on the cloud, but unlike a password, you don't interact with it at all anymore. So, it is a way to authenticate yourself to a website without using a password. It has a lot of benefits. The first and most obvious one is that it is a secure exchange. That pass key can't be forgotten. It's very difficult for that to be breached. You know, if the website gets breached, they're not going to be able to get your pass key. You've got that. That's yours. It requires additional authentication. You put your PIN in. you do a scan or something. So, it's more layers of security around it. And importantly, each pass key only works with the site where you created it. So, it makes it very difficult for that to be fished. It makes it very difficult for that to be cloned in any way.

</details>

**罗茜**: 也就是说，理论上你将拥有许多许多个不同的通行密钥。你拥有的通行密钥数量会和你的密码数量一样多。

<details>
<summary>Original English</summary>

**Rosie**: So, you are going to theoretically have many many many different pass keys. You have the same number of pass keys as you would passwords.

</details>

**麦克斯**: 是的。理论上，你拥有的通行密钥数量至少会和你要登录的网站数量一样多。但它其实是一种完全安全的密钥交换形式。我想让大家理解的核心结论是：**通行密钥将彻底取代密码**。你不再使用传统密码了。我们利用现代技术构建了极其安全的交换机制，并用它来替代传统密码。我们砍掉了在中间环节导致我们困扰多年的各种麻烦漏洞。

<details>
<summary>Original English</summary>

**Max**: Yeah. Like you're going to have as many pass keys as you have websites at minimum. And it is just this way to have a completely secure exchange. Like the the goal here, the thing that that I think people need to take from it, bottom line, pass keys replace passwords. You don't do passwords anymore. We leverage the technology that we have that is very, very good at creating secure exchanges. And we use that instead of passwords. We cut out all of the gooey stuff in the middle that's been causing us problems for as long as we've had passwords.

</details>

**罗茜**: 当我在手机上或者在网上遇到通行密钥时，它的登录流程看起来会是什么样的？

<details>
<summary>Original English</summary>

**Rosie**: What is it going to look like when I'm on my phone or online and I encounter a pass key?

</details>

**麦克斯**: 如果你已经在设备上为某个网站创建了通行密钥，当你开始登录时——不论是当你刚打开登录页面还是刚输入用户名，屏幕上就会弹出一个小提示框说：“嘿，你已经有这个网站的通行密钥了，我们用它来登录吧。” 或者你也可以手动点击一个按钮说“我使用通行密钥登录”。然后它就会使用这个密钥，接着就直接登录了。有时候你只需要输入解锁手机的 PIN 码（或者按一下指纹/刷一下脸）就行了，仅此而已。有时我甚至希望步骤多一些，这样感觉上更“脚踏实地”，但实际上它就是这么好用，直接就登进去了。这真的很棒。

<details>
<summary>Original English</summary>

**Max**: So, if you have a pass key already on your device, when you start the login process, either when you land on the login site or when you enter just like your username, a little thing pops up and says, \"Hey, you've got a pass key for this. Let's use that instead.\" Or you might have to click a button and say, \"I have a pass key.\" And then it'll use that instead. And then it just logs in. You'll have to sometimes enter a pin number, but that's it. Yeah. I wish there were more steps because it would feel so much more like tangible, but again, it just it just works. It's kind of great.

</details>

**罗茜**: 那么如何开始使用它们呢？在刚才的例子中，我已经为某个网站设置好了通行密钥，但我要怎样先拿到它呢？我该如何开始第一步？

<details>
<summary>Original English</summary>

**Rosie**: So, how do you get started using them? Because that example, I already have a pass key for whatever website. How do I get my pass key? How do I get started?

</details>

**麦克斯**: 我认为最好的开始方式是去亲身试一下，学习如何使用。谷歌账户就很适合用来做这个测试。谷歌账户允许你为一个账户创建任意多个通行密钥，你可以反复尝试。这非常简单和灵活。所以你可以登录你的 Google 账号，转到账号设置，找到通行密钥选项并创建一个，然后尝试用它登录，你就能体验到这个新流程。

我觉得在没有亲自体验前，我很难用言语解释得特别透彻，因为它真的太直接、太简单了。我们之前谈到了安全疲劳，在概念上我们太习惯了传统密码，而通行密钥彻底拿掉了密码，这有时会让人感觉失去了对过程的掌控，会让人感到困惑，觉得陌生甚至有些害怕。但一旦你开始使用，你就会发现：“天呐，这真的太方便了。”

<details>
<summary>Original English</summary>

**Max**: Yeah, I think the best way to get started is to sort of try it out and learn how to use it. Google accounts are really good for this. A Google account will let you create as many pass keys as you want for an account. You can play around with it. It's very, very simple and flexible. So, yeah, log into your Google account. go to your account settings, create a pass key, go through that process, and then try it out, and you'll be able to work through that flow. You know, I I feel like we're not doing a great job of explaining this, and it is just because it's very very straightforward and simple once you do it, and we talked about security fatigue earlier that it's hard to conceptualize this. We're so used to passwords and this takes that away, and it can feel like you're losing control. It can feel confusing. It is so different and that's scary and weird, but once you start doing it, it's like this is so much so much easier.

</details>

**罗茜**: 我甚至觉得它变得太容易了。因为至少，当你有一个保存在密码管理器里的复杂密码时，你知道它是由 15 个包含美元符号、大小写字母的字符组成的，这让我觉得它很复杂、很安全。但是到了通行密钥，在我目前仅有的几次体验中，我觉得这太方便了，简直好得不真实。

<details>
<summary>Original English</summary>

**Rosie**: Well, I've almost felt that it's too easy because at least, you know, with a password, a complicated password that exists in my password manager, I know that there are 15, you know, dollar signs and capital letters and lower letters and it's going to be complex. With a pass key, in my experience so far, it's like this seems too good to be true.

</details>

**麦克斯**: 是的，就是那种“无形感”，对吧？因为你什么都看不到。在密码管理器中，你可以点开查看那一长串复杂的密码，从而获得一种它确实在起作用的安全感。这里面有一个奇妙的矛盾：如果通行密钥向你展示它的底层代码，你根本看不懂；但对普通人来说，它用起来却无比丝滑，而这正是设计初衷。苹果、微软和谷歌等科技巨头投入了大量的精力，让它变得快速、无缝且可靠。它正在不断演进，未来有望彻底取代传统密码，在这个过程中它会变得越来越灵活，越来越好用。

通行密钥的底层设计决定了，**在你创建通行密钥的网站上，它们并不会保存你的私钥副本**。这意味着，哪怕该网站以后发生了数据泄露，对你也毫无影响，你的信息在他们服务器上是安全的。这正是通行密钥在概念上优于密码的核心原因之一。对于传统密码而言，只要你保存密码的网站被攻破了，你也就随之泄露了。

<details>
<summary>Original English</summary>

**Max**: Yeah. And and it's that intangibility of it, right? like there's nothing there. Like in your password range, you could look it up and see the big long password and feel assured that it does something. And this is just this weird contradiction with pass keys where like if you actually saw any part of it, it wouldn't make any sense at its technical level, but at the person level, it's as seamless as can be. And this is by design. A lot of work has gone into making this fast, seamless, reliable. It's supported by Apple, Microsoft, Google. It's hopefully going to take off and become the new password and it's continuing to evolve. There's changes happening to it making it a little bit more flexible, a little bit easier. The way pass keys are designed is that the sites you create pass keys on, they really don't have they don't have a copy of your pass key. So, if there's like a data breach on that site, that doesn't affect you. Like your information is safe. This is part of why Pasis like as a concept just are better than passwords. For passwords to work, you can be breached on the site where you have them.

</details>

**罗茜**: 使用通行密钥目前有什么局限或缺点吗？

<details>
<summary>Original English</summary>

**Rosie**: Are there any limitations or disadvantages to using pass keys?

</details>

**麦克斯**: 目前最大的局限是**并非所有的网站都支持通行密钥**。这让人感到有些沮丧，因为对用户而言，它明明更好、更容易也更安全。对于企业来说也同样更有利，因为这意味着会减少数据泄露事故，也不会再有用户因为忘密码而登录不上的问题，这理应能解决大部分账号管理上的麻烦，但现在它依然没有普及到所有角落。以我目前的感受，只有当我在网站上偶然发现可以使用通行密钥时，才会感到一阵惊喜，但它确实还没有无处不在，你不得不主动留心去寻找它。

<details>
<summary>Original English</summary>

**Max**: So, right now the biggest limitation about pass keys is that not all sites support it. And it's a little bit frustrating because it is better for users. It's easier. It's more secure. In many ways, it's better for companies because there's going to be hopefully fewer data breaches and people not being able to log in. Like, it should iron out a lot of those problems, but it's still just not everywhere yet. Right now, I would sort of describe it as when I can use a pass key, it's like a pleasant surprise, but it's not everywhere. So, you have to keep an eye out. You have to go looking for it.

</details>

**罗茜**: 我们应该期待它继续成长并变得无处不在吗？

<details>
<summary>Original English</summary>

**Rosie**: Should we expect that it will continue to grow and become ubiquitous?

</details>

**麦克斯**: 推动这项技术的幕后人员当然是这样认为的。只要看看苹果、谷歌和微软都在其所有的操作系统平台上全力支持通行密钥，你就知道他们的态度了。通行密钥的优势是显而易见的。

不过目前它还有另一个限制：**几乎所有的网站在你注册账户时仍然需要你先设置一个传统密码**。在理想的“通行密钥乌托邦”中，你甚至根本不需要设置密码，这辈子都碰不到传统密码了。但我们目前还没有走到那一步。这项技术依然在推广的初期。所以你依然需要使用你的密码管理器，你注册这些新账号时依然要为它们配上 2FA 验证，因为这是注册流程中的一环。

<details>
<summary>Original English</summary>

**Max**: So, the people behind it certainly think so. You can just look at Apple, Google, and Microsoft putting their support behind this into all of their platforms. They certainly think so. The advantages are there. Another limitation of pass keys though is that pretty much every site is still going to require that you create a password when you make an account there. Now, and like an idealized pass key utopia, you don't even do that. You don't even you never touch a password anymore. But we're not there yet. This technology is still rolling out. So, you're still going to be using your password manager. You're still going to be using 2FA on these accounts because you have to do that as part of the creation process.

</details>

### 总结与行动指南

**罗茜**: 所以归根结底，你给出的建议是：密码管理器是必须使用的，对吧？

<details>
<summary>Original English</summary>

**Rosie**: So, ultimately, it sounds to me like the advice is password manager. Yes.

</details>

**麦克斯**: 是的。

<details>
<summary>Original English</summary>

**Max**: Yes.

</details>

**罗茜**: 尽快去下载和配置一个。

<details>
<summary>Original English</summary>

**Rosie**: Get it ASAP.

</details>

**麦克斯**: 用起来。

<details>
<summary>Original English</summary>

**Max**: Use it.

</details>

**罗茜**: 在能使用双重验证（2FA）的地方，尽量开启它。

<details>
<summary>Original English</summary>

**Rosie**: Use two-factor authentication 2FA when you can.

</details>

**麦克斯**: 尽可能多地去用。

<details>
<summary>Original English</summary>

**Max**: As often as you can.

</details>

**罗茜**: 没错。

<details>
<summary>Original English</summary>

**Rosie**: Oh, yeah.

</details>

**罗茜**: 之后，如果你在网站上遇到了通行密钥的提示，那就大胆尝试一下。

<details>
<summary>Original English</summary>

**Rosie**: And then if you encounter a pass key, try it out.

</details>

**麦克斯**: 对的。你现在对通行密钥了解得越多，未来的过渡就会变得越轻松。FIDO 联盟（FIDO Alliance）的网站上有一份列表，列出了目前支持通行密钥的网站，如果你想采取更积极主动的态度，可以上网查看那份列表。去看看对你最重要的一些网站的账号安全设置。下一次当你的手机屏幕上弹出一个提示问“你想要为此账户创建通行密钥吗？”的时候，别犹豫，去创建它。

<details>
<summary>Original English</summary>

**Max**: Yeah. The more you learn about using Pasis right now, the easier that transition will be. There's a list on the Phto Alliance site of sites that do support Pas right now. If you want to go be proactive about it, look at that. Go look at the account settings for the sites that are most important to you. And the next time you see a little nag pop up on your phone that says, "Hey, do you want to create a pass key for it?" Go for it. Do it.

</details>

**罗茜**: 麦克斯，非常感谢你的深入见解。一如既往地感谢你。

<details>
<summary>Original English</summary>

**Rosie**: Max, thank you for the insight. Always appreciate it.

</details>

**麦克斯**: 非常感谢。

<details>
<summary>Original English</summary>

**Max**: Thank you so much.

</details>

**罗茜**: 如果你想了解更多关于麦克斯在数据、隐私、安全方面的报道，可以去 Wirecutter 官网查看。我们会在节目说明中附上他关于通行密钥和密码管理器的文章链接。

一如既往，我们非常感谢您的收听。我们下期节目再聊。本期 Wirecutter 节目由我——罗茜·加林担任执行制片人，由阿比盖尔·基尔（Abigail Keel）制作。工程支持来自马蒂·马齐洛（Mattie Maziello）和尼克·皮特曼（Nick Pitman）。今天的节目由凯瑟琳·安德森（Catherine Anderson）混音。原创音乐来自丹·鲍威尔（Dan Powell）、玛丽安·洛萨诺（Marian Lozano）、艾丽西亚·埃图普（Alicia Etup）、罗文·尼斯托（Rowen Nisto）、凯瑟琳·安德森（Catherine Anderson）和戴安·黄（Diane Wong）。克里夫·利维（Cliff Levy）是 Wirecutter 的副发行人和总经理。本·弗曼（Ben Fman）是 Wirecutter 的总编辑。我是罗茜·加林，谢谢您的收听。

<details>
<summary>Original English</summary>

**Rosie**: If you want to learn more about Max's reporting on data, privacy, security, you can check out Wire Cutters website. We will link his articles about pass keys and about password managers in our show notes. As ever, we so appreciate you listening. Talk soon. The Wire Cutter Show is executive produced by me, Rosie Garin, and produced by Abigail Keel. Engineering support from Mattie Maziello, and Nick Pitman. Today's episode was mixed by Catherine Anderson. Original music by Dan Powell, Marian Lozano, Alicia Etup, Rowan Nisto, Katherine Anderson, and Diane Wong. Cliff Levy is Wire Cutter's deputy publisher and general manager. Ben Fman is Wire Cutters editor and chief. And I'm Rosie Garrett. Thank you for listening.

</details>

**旁白**: 最显而易见的问题，也是我们制作这期内容的初衷——

<details>
<summary>Original English</summary>

**Narrator**: The most obvious question, the reason [clears throat] we created this,

</details>

**主持人**: 我的密码到底是什么？

<details>
<summary>Original English</summary>

**Host**: what's my password?

</details>

**麦克斯**: 是的，你的密码是什么？你的主密码到底是什么？家伙59（Guy 59）。

<details>
<summary>Original English</summary>

**Max**: Yeah. What is your password? What is your master password? Guy 59.

</details>