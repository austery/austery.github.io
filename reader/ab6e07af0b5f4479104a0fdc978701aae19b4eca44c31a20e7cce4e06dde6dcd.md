---
author: The Pragmatic Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=OrXKvOjR-vI
speaker: The Pragmatic Engineer
tags:
  - technical-debt
  - software-testing
  - system-observability
  - agile-development
  - communication-alignment
title: 测试、技术债与“以慢为快”的软件工程实践
summary: 文章探讨了测试作为手段的观点、技术债的偿还时机，以及通过前期规划、明确共识和确保可观测性来“以慢为快”的工程实践，强调避免沟通误解和盲目追求速度。
insight: ''
draft: true
series: ''
category: testing
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 测试与技术债的观点

你写过一篇非常有趣的博文，我来引用一下：“测试是达到目的的手段。手段并不重要。”

<details><summary>Original English</summary>
You wrote a very interesting blog post which I'm going to quote, "Tests are a means to an end. The means are unimportant."
</details>

>> 用这种测试确实可以做一些非常了不起的事情，但归根结底，你仍然是在整个事情的后期阶段才在做这件事情。事实上，大家最终在某种程度上——无论他们是否承认——都在生产环境中进行测试。我们现有的工具没有一个好到足以保证无论那是什么的质量。

<details><summary>Original English</summary>
>> There is absolutely amazing stuff that you can do with that testing, but in the end, you are still doing something at the late stages in the game. It's true that everybody in the end in some way, whether they admit it or not, is testing and prod. None of the tools that we have are good enough to guarantee whatever it is.
</details>

>> 技术债只有在你必须偿还时才会带来伤害。是的，你完全有可能陷入这样一种境地：不幸的是，甚至在找到产品与市场匹配度之前，你就可能已经负债累累、走投无路了。但是在很多地方存在的一种观点，比如，“哦不，每一丁点债务都是坏的，它总是必须被还清”，这在现实中是站不住脚的。

肖恩，非常高兴能邀请到你。

<details><summary>Original English</summary>
>> Technical depth only hurts if you have to pay it back. Yes, you can very much get yourself into a position where unfortunately before you even found product market fit, you might have debted yourself into a corner, but the idea that exists in a lot of stuff where it's like, oh no, every single bit of debt is bad. It always has to be paid off. It's not borne out in reality.

Sean, great to have you.
</details>

### 早期经历与入行软件开发

>> 谢谢。我们得从我们发现的这个不可思议的事实开始聊起：我工作过的第一家做专业软件的公司，叫作 Senset。S-E-N-S-E-N ne-T。你工作过的第一家公司叫什么？

<details><summary>Original English</summary>
>> Thank you. We need to start with this crazy fact that we discovered the first company I ever worked for that did professional software, it was called Senset. S E N S E N ne T. What was the first company that you worked for?
</details>

>> Senset。S-E-N-S-E-N-T。

<details><summary>Original English</summary>
>> Senset. S E N S E N T.
</details>

>> 而且它们是不同的公司。你的那家在纽约。

<details><summary>Original English</summary>
>> And they're different companies. Yours was in New York.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我那家在匈牙利的布达佩斯。

<details><summary>Original English</summary>
>> Mine was in Budapest, Hungary.
</details>

>> 噢，我之前不知道你的那家在布达佩斯。嘿。

<details><summary>Original English</summary>
>> Oh, I didn't I didn't know yours was in Budapest. Hey.
</details>

>> 是的。把时间倒回你第一份工作之前的很久，你是怎么进入科技行业的？实际上，你当时是真想进入科技行业，还是音乐才是你的兴趣所在？

音乐绝对更符合我的兴趣，但是大学毕业后，我发现自己完全不知道自己要做什么。我开始翻自己的通讯录，找到的第一个表示我可以去借住的人住在纽约市。于是我就去了，我的一位好朋友当时也住在那里。最终他……我当时找不到工作。我差一点得到一份工作，是去给一位美国参议员当演讲撰稿人。但我没有拿到那份工作。后来一个朋友帮我在 Scholastic 找了一份修电脑的工作。

接着另一个朋友告诉我：“嘿，如果你去学 Perl，你就可以搬到波士顿，而且你就能……你知道，我大学时的一帮校友在那里创办了一家初创公司。”于是我学了 Perl，而大约在我花了三到四个月把 Perl 学到足够好以胜任那份工作的时候，那家初创公司已经倒闭了。然后事情就开始变成……

<details><summary>Original English</summary>
>> Yeah. And rewinding the clock uh a lot before your first job, how did you get into tech? In fact, did you even want to get into tech or was it was music more your thing?

Music was definitely more my thing, but uh I graduated from college and I realized I had no idea what I was going to do and I just started going through uh my address book and the first person I found who said I could come stay with them uh lived in New York City. So I went and a good friend of mine was also living there and uh he eventually he was like I couldn't I couldn't find a job. I got close to getting one which was as a speech writer for a US senator. Uh but I did not get that. And a friend got me a job fixing computers at Scholastic. And then another friend told me, "Hey, if you learn Pearl, you can move to Boston and you can, you know, there was a bunch of people I'd gone to college with who started startup. So I learned Pearl and right about the time that I finished being good enough learning Pearl over the course of three to four months to, you know, do that. uh that startup had collapsed and then it started just be like
</details>

>> 那时候正好赶上互联网泡沫破裂。

不，不，那甚至还在互联网泡沫破裂之前。那是一群脾气暴躁的人在一起共事。但在那个节点上，情况开始变成我确实喜欢这个，我很享受它。我更早的时候、在十几岁的时候接触过一点，因为当时有一款叫《淘金者》（Lode Runner）的电子游戏，我非常喜欢《淘金者》，真的很想做出类似《淘金者》的东西。所以我让我祖母给我买一本关于计算机编程的书，但我对计算机编程一无所知，我祖母对计算机编程也一无所知。于是她去了德克萨斯州沃斯堡的一家电脑店，那里的店员给了她一本关于 Commodore 64 机器语言的书。

所以我当时觉得：“哇，编程真的很难，不过确实就是通过那种方式入的门。”这也是我第一次意识到：“噢，这是一件别人会付给我很多钱的事情。”当时我就想：“我没有其他任何可以让人付给我很多钱的本事了。我应该把这个学得非常精通。”

<details><summary>Original English</summary>
>> there was a dotcom bust right around that time.

No, no, that was that was even before the.com bust. That was a combustible set of human beings uh working together. But yeah, at that point it started being like I I like this. I enjoy it. I'd done it a bit like earlier on uh when I was like a teenager cuz I there was a video game LoadRunner and I I loved LoadRunner and I really wanted to to create things that were like LoadRunner. So I asked my grandmother to get me a book about computer programming, but I didn't know anything about computer programming. my grandmother didn't know anything about computer programming. So, she went to a computer store in uh Fort Worth, Texas, and the guy gave her a book which was uh machine language for the Commodore 64. So, I was like, "Wow, programming is really hard, but yet that's I kind kind of got started that way." And it was the first time I was like, "Oh, there's a thing that people will pay me lots of money for." And I was like, "I have no other thing that people would pay me lots of money for. I should get really good at this.
</details>

### 学习 C++ 与加入 Antithesis

>> 那么，你后来是怎么在编程上变得非常厉害的？比如，你之后在不同的公司工作，对吧？

<details><summary>Original English</summary>
>> And then so how did you get really good at at programming? Like you you then worked at different companies, right?
</details>

>> 我花了非常多的业余时间，就只是努力去提高水平。我觉得我突飞猛进是因为我对 BeOS 产生了兴趣……对，我当时对 BeOS 非常着迷，那个社区里有一些非常有趣且乐于助人的人。当时有个人……BeOS 的所有编译器工具都是一家叫 Metrowerks 的公司制作的，该公司当时也为 Mac OS 制作编译器。不知出于什么原因，负责他们编译器团队的主管在邮件列表上很有兴趣指导我学习 C++。

而且邮件列表上还有一位懂 C++ 并且非常友善的人。我对科幻小说基本上可以说是一无所知，所以当时这对我来说并没有什么特别的意义——那个人后来被发现是尼尔·斯蒂芬森，他……

<details><summary>Original English</summary>
>> I spent an awful lot of my free time um just trying to get better at it. I think I I leaps and bounds I got interested in uh BOS uh in the Yes. I was really into BOS and um there were some very interesting and helpful people in that community. There was a guy uh all the compiler tools for BOS were made by this company called MetroWorks that also made uh compilers for Mac OS at that time. And for some reason the guy who was the head of their uh their compiler group took an interest on mailing list in helping me learn C++. And there was a there was somebody who was uh knew C++ and was really nice on the mailing list as well who um I know I know basically nothing about sci-fi at all. So it didn't mean anything to me that that person turned out to be Neil Stevenson who
</details>

>> 不会吧。

<details><summary>Original English</summary>
>> No way.
</details>

>> 是的。他……

<details><summary>Original English</summary>
>> Yes. Who um
</details>

>> 世界著名的科幻作家。

<details><summary>Original English</summary>
>> world famous sci-fi author.
</details>

>> 是的。他基本上就是会和我互相通邮件，在学习 C++ 编程方面给我提出建议，这对我来说发生得非常早。我的意思是，当时还有其他人，但这两人对我来说确实格外突出。比如，我到现在都还没读过尼尔·斯蒂芬森的任何一部作品。我想我读过几页《雪崩》，但这向来是一个讲给别人听很有趣的故事。

<details><summary>Original English</summary>
>> Yes. Who basically was just like would exchange like emails with me and advice on on learning like C++ programming which was really early on for me. I mean, there were other people as well, but those were two who really like stood out to me. Like, I've still never read a Neil Stevenson thing. I think I read a couple pages of Snow Crash, but it's it's always a fun story to tell people.
</details>

>> 是啊。那你后来是怎么加入 Antithesis 的？

简短的版本是，CEO 威尔·威尔逊（Will Wilson）在去年 12 月我找新工作时给我发了条消息，那只是一条链接，指向他们在 Hacker News 的“谁在招人”板块发布的帖子，并问我：“你对这个会有兴趣吗？”基本上就像在问：“你想做 Jepsen 风格的事情吗？”我的回复是：“听起来可能会很有意思。”

<details><summary>Original English</summary>
>> Yeah. And how did you end up at antithesis?

Well, the the short version would be is that Will Wilson, the CEO, sent me a message while I was looking for a new job in December, which was just a link to a thing that they posted on the who's hiring for uh on Hackers Nukes and said, "Would you be interested in this?" It was basically like, "Do you want to do Jeepson style things?" And my response was, "That sounds like it could be fun."
</details>

### 红队的工作与函数式语言

>> 那你现在在 Antithesis 做什么？

<details><summary>Original English</summary>
>> And what do you do at Anticist? Now,
</details>

>> 我在一个叫作红队的团队里。我想如果你去问公司里的每一个人红队是做什么的，你从几乎每个人那里得到的答案大概都会不一样。我会这么表述：威尔把一群非常聪明的人聚集在一起，并表示：“我希望你们能像客户使用我们产品那样去使用我们的产品。”作为其中的一部分，我做过的一件事就是特意从不使用我们内部可用的工具来配合该产品工作，仅仅是为了保证我只能使用客户自己所拥有的完全相同的工具来配合它工作。

<details><summary>Original English</summary>
>> I'm on a team called the Red Team. And I think if you asked everybody at the company what the red team does, you'd get probably different answers from almost everyone. Um, I would I would put it as Will collected a bunch of really smart people together and was like, I want you to use our product the way that customers would use our product. One of the things I've done as part of that is I've intentionally never used the tools which are available to us internally to work with the the product and just done it so that I can only work with it with the exact same tools that uh that customers would have for themselves.
</details>

>> 设立一个扮演客户团队的内部团队，这个概念挺巧妙的，而且你知道你可以找他们交流，他们会同你论理，他们会解释客户是怎么想的。

<details><summary>Original English</summary>
>> That's kind of a neat concept having an internal team who is a customer team except you know you can talk to them, they will reason with you, they'll they'll explain how the customer thinks.
</details>

>> 是的。所以我们都很有经验，并且得到了很大的自主权去从事任何事情，只要别人看了觉得“噢，这对公司很有价值”。因此我花了很多精力在让智能体更好地与 Antithesis 协作的技能上。不过话说回来，我觉得我最喜欢的，就只是做一些向客户传授、同时也向内部员工传授知识的事情，传授我多年来学到的关于如何确保软件良好运行的许多知识。对我来说，这在软件栈的非常底层就开始了，远在任何被人们称为测试或诸如此类的事情之前。是的，就是跟人们聊这个。我喜欢结识别人。我喜欢和人交流。这是我非常热爱的一个主题。我不知道，这算是一种理想的工作。

说到理想的工作，有一件事是你一直深入钻研的，就是不同的语言，我称之为稍微有点小众奇特的语言。我说的不是像 TypeScript 或者可能是 Rust、Go 等主流语言，而是其他几种语言。我们能具体聊聊 OCaml 吗？什么是 OCaml，为什么所有的对冲基金和金融公司都对它如此青睐？

OCaml 是一种最初主要源自法国学术背景的语言。它诞生于人们试图将函数式编程与面向对象特性相结合的时期。在当时，尤其是在 90 年代，这是人们极力尝试去做的一件非常重要的大事。在那时，就是往一切东西上硬套对象。对象非常被看作是未来的方向等等。有趣的是，在像简街（Jane Street）以及其他大量使用它的地方真正流行起来的 OCaml 版本，却是其中任何 OCaml 的面向对象特性都没有真正得到使用的版本。

<details><summary>Original English</summary>
>> Yeah. And so we all have a lot of experience and we've been given a lot of free reign to do anything as long as it as long as people were looking at it going, "Oh, that's valuable to the company." So I worked a lot on on skills for helping agents work better with antithesis. But I mean, I think the stuff that I like the most um is just doing stuff to teach customers and teach people internally as well. a lot of the stuff that I've learned over the years for how to how to be sure that your software works well. Um, and that, you know, for me that starts way down the stack, way before anything that anybody calls testing or whatnot. Yeah. And just talking to people about that. I love meeting people. I love talking to people. And it's a subject that I that I really love. I don't know. It's kind of a dream job.

And speaking of dream job, one thing that you've been really going deep into is just different languages which I would call a little bit of exotic languages. Not I'm not talking about the mainstream TypeScript or maybe roster go etc but a few other languages. Can we talk about Okamel specifically? What is Okamel and why are all the hedge funds and finance companies in love with it?

So, Oak camel is a language that came from an academic background primarily uh in France originally. Um and it was it came out at the time when people were trying to combine functional programming with objectoriented stuff. This was a really big deal that people like tried to do particularly in the '9s. At that point, it was bolting objects onto everything. Objects were very much seen as the future etc. And it's interesting because the version of O camel that's actually caught on at places like Jane Street and and other places where it get used a lot is one where none of the O features in O camel really get used.
</details>

>> 这个 O 是什么？

<details><summary>Original English</summary>
>> What is the O?
</details>

>> O 就是面向对象的部分。

<details><summary>Original English</summary>
>> The O is the object part.
</details>

>> 噢。

<details><summary>Original English</summary>
>> Oh.
</details>

>> 而且它确实有一整套非常面向对象的特性。但我所认识的写 OCaml 的人里，我想不出有谁是真正会去用任何……

<details><summary>Original English</summary>
>> And and there's there is a whole series of features which are very object-oriented about it. But I can't think of anyone I know who does O camel who actually really uses any
</details>

<!-- chunk 2/11 -->

### ML 语言家族与 Rust 的渊源

……的面向对象特性。但它是一门源自 ML 的语言，而 ML 是一个与 ALGOL 等语言完全不同的语言家族。像 Python、Perl，以及很大程度上的 Ruby、C、C++，这些都属于 ALGOL 语言家族。然后还有 ML 家族，OCaml 是其中之一，里面还有很多其他语言。取决于你问谁，有些人会说 Haskell 也算在其中，有些人则认为不算。所有 ML 语言通常都会为人们提供一套不同的功能与特性。我认为目前受 ML 影响最著名的语言应该是 Rust，Rust 中有非常多 ML 风格的特性，比如和类型（sum types）、模式匹配等等，所有这些都是源自 ML 的东西。

<details><summary>Original English</summary>
 of

 the





object-oriented

 features.

 But

 it's

 it's





a

 language

 um

 which

 is

 descended

 from

 ML





which

 is

 a

 entirely

 different

 languages





of

 families

 from

 like

 algo

 languages





where

 where

 like

 Python

 and

 Pearl

 and





for

 the

 most

 part

 Ruby,

 C,

 C++

 these

 are





these

 are

 all

 ALGO

 languages

 and

 then





there's

 a

 an

 the

 ML

 family

 of

 which

 uh





Okamel

 is

 is

 one

 there

 there

 are

 a





number

 of

 others

 in

 there.

 uh

 depending





on

 who

 you

 ask

 some

 people

 will

 say





hasll

 is

 kind

 of

 in

 there

 kind

 of

 not





and

 um

 all

 the

 ML

 languages

 generally





provide

 a

 a

 different

 set

 of

 uh





functionality

 and

 capabilities

 to

 people





the

 most

 famous

 I

 think

 at

 this

 point

 ML





uh

 influenced

 language

 would

 be

 Rust





there's

 an

 awful

 lot

 of

 ML

 type

 stuff

 in





Rust

 the

 the

 sum

 types

 the

 pattern





matching

 etc

 all

 of

 this

 is

 stuff

 that





came

 from
</details>

>> ML 听起来有点像更偏声明式的语言，或者说你会怎么描述 ML？

<details><summary>Original English</summary>
>> ML

 this

 sounds

 like

 a

 bit

 like

 more

 of

 a





declar

 erative

 language

 or

 what

 is

 the





ML

 how

 would

 you

 describe

 it
</details>

>> ML 语言通常是围绕强类型系统构建的，对吧，就像 Rust 也是围绕强类型系统构建的一样。在那里你使用和类型，基本上就是说它可以是这三种情况之一。它们有点像 Java 里的枚举，大家可能比较熟悉；或者现在 Rust 流行多了，有些人可能对 Rust 里的形式更熟悉。你可以把和类型与模式匹配结合起来，如果你还能进一步将它与穷尽匹配（exhaustive matching）结合在一起——意思是假设我有一个可能代表五种不同情况的和类型，对吧，我对它进行处理的方式不是用 if 语句，而是做模式匹配，匹配的是这个东西所属的类型。

[clears throat]

<details><summary>Original English</summary>
>> the

 ML

 languages

 are

 generally

 uh





they're

 built

 around

 strong

 type

 systems





right

 in

 the

 same

 way

 that

 that

 Rust

 is





built

 around

 a

 strong

 type

 system

 where





you

 take

 some

 types

 which

 is

 basically





saying

 it

 could

 be

 one

 of

 these

 three





things

 they're

 kind

 of

 like

 enumerations





uh

 from

 something

 like

 Java

 that

 that





people

 might

 be

 familiar

 with

 or

 hey





Rust

 is

 a

 lot

 more

 popular

 now

 so

 some





people

 might

 be

 familiar

 with

 it

 from





there

 and

 you

 can

 combine

 that

 together





with

 uh

 pattern

 matching

 and

 and

 if

 you





can

 then

 also

 combine

 that

 together

 with





exhaustive

 matching

 um

 where

 what

 it





means

 is

 that

 I

 have

 this

 sum

 type

 which





could

 be

 say

 five

 different

 things

 right





and

 the

 way

 that

 the

 way

 that

 I

 will





work

 on

 it

 is

 instead

 of

 an

 if

 statement





I

 do

 pattern

 matching

 but

 I'm

 matching





on

 the

 type

 that

 the

 thing

 is





[clears throat]
</details>

>> 然后你把这个与穷尽匹配结合起来，最终就能得到这样一个代码库：你只要做一个修改，比如宣布现在它有六种可能而不是五种，编译器就会指出代码库中所有你没有处理……

<details><summary>Original English</summary>
>> um

 and

 then

 you

 can

 combine

 that

 with





exhaustive

 matching

 what

 you

 can

 end

 up





with

 is

 a

 code

 base

 where

 you

 can

 make





one

 change

 and

 say

 actually

 now

 I

 have





six

 different

 things

 of

 this

 instead

 of





five

 and

 the

 compiler

 will

 tell

 you





every

 single

 place

 in

 your

 codebase





where

 you're

 not

 handling
</details>

>> ……那第六种类型的地方。这真是一种无比美妙的体验。听起来编译器为你提供了额外的测试保障，而这种保障在像 C 或 TypeScript 这样的语言编译器中是得不到的。那里的编译器会告诉你类型，但如果我没理解错的话，这里的核心关键在于穷尽匹配。而且模式匹配的存在，会去检查各种条件或者假设，而像 TypeScript 这类语言——我就拿它举个例子——基本上是如果出了问题，你在运行时才会发现；而在编译期，这里有大量的结构规则，当然也有逻辑检查贯穿其中。所以你相当于把大量的验证工作都前置了。

<details><summary>Original English</summary>
>> that

 six

 type

 and

 it

 it

 is

 a

 gloriously





wonderful

 uh

 experience.

 It

 it

 it

 sounds





like

 the

 compiler

 gives

 you

 additional





testing

 that

 you

 might

 not

 get

 from

 a





compiler

 in

 let's

 say

 a

 language

 like

 C





or

 or

 TypeScript

 whatnot.

 The

 compiler





there

 will

 tell

 you

 the

 types

 but

 if

 I





understand

 correctly

 the

 exhaustive





matching

 is

 the

 key

 here.

 And

 the

 fact





that

 there's

 matching

 it

 goes

 and

 checks





kind

 of

 maybe

 conditions

 or

 or





assumptions

 that

 are

 in

 these

 languages





like

 TypeScript.

 I'll

 just

 use

 it

 as

 an





example.

 It's

 kind

 of

 you

 know

 you'll





figure

 it

 out

 runtime

 if

 something





breaks

 and

 here

 in

 compile

 time

 there's





a

 lot

 of

 structure

 rules

 and

 there's

 of





course

 like

 logic

 it

 goes

 through

 there.





So

 you

 kind

 of

 frontload

 a

 lot

 of

 that





validation

 if

 you

 will.
</details>

>> 是的。所有具有某种 ML 风格或属于该大类的语言，都非常倾向于这种理念：“我想把尽可能多的东西放进编译器的静态检查中，让编译器帮我干活。”好，我现在明白为什么有些喜欢 Rust 的人会说，Rust 能帮你减少线上 bug 了，因为它是 ML 风格的语言，编译器会承担更多工作，并且有严格得多的规则需要你去适应，但作为回报，编译器就像……很多问题它直接给你报编译错误。

<details><summary>Original English</summary>
>> Yeah.

 All

 all

 of

 the

 languages

 which

 are





MLike

 in

 some

 type

 of

 way

 or

 are

 in

 that





general

 family

 are

 very

 much

 languages





where

 it's

 like

 I

 want

 to

 put

 as

 much

 as





possible

 into

 static

 checking

 in

 the





compiler

 and

 have

 the

 compiler

 do

 work





for

 me.

 Okay,

 so

 now

 I

 understand

 why





some

 people

 say

 who

 are

 into

 Rust

 that





Rust

 helps

 you

 ship

 fewer

 bugs

 because





it's

 an

 ML

 it's

 type

 language

 which

 the





compiler

 will

 do

 a

 lot

 more

 work

 and

 it





will

 have

 a

 lot

 you

 stricter

 rules

 that





you

 need

 to

 become

 familiar

 with

 but





then

 in

 return

 the

 compiler

 just

 like

 it





a

 lot

 of

 things

 and

 it'll

 give

 you

 a





compile

 error.
</details>

### 从 C 到 Ada 的工程取舍

>> 没错。早年我刚学编程的时候，非常痴迷于各种不同的编程语言，去了解各种可能性。后来很早我就决定选定一门语言，专注投入一段时间。我最终敲定的两种语言是 C 和 Ada，不过主要是 C。选择 C 是因为当时我在为 Mac OS 做大量开发，大概是 System 6 或 7，我想当时应该是 6；而苹果在那时正把大量代码从 Pascal 转到 C，所以我觉得 C 应该会挺有意思。而 Ada 则完全是另一套体系……

<details><summary>Original English</summary>
>> Yeah.

 Early

 on

 when

 I

 was

 learning

 to





program,

 um

 I

 was

 really

 into

 like





different

 programming

 languages

 and

 just





learning

 like

 different

 things

 that

 were





possible.

 And

 uh

 fairly

 early

 on

 I





decided

 I

 was

 going

 to

 pick

 one

 thing





and

 I

 was

 going

 to

 dedicate

 myself

 to





that

 for

 a

 while.

 And

 uh

 the

 two





languages

 I

 ended

 up

 settling

 on

 were

 uh





C

 and

 ADA

 And

 it

 was

 mostly

 it

 was

 C.





the

 the

 choice

 of

 C

 came

 because

 I

 was





doing

 a

 lot

 of

 programming

 for

 I

 think





it

 was

 Mac

 OS

 it

 was

 either

 six

 or

 seven





I

 think

 it

 was

 six

 at

 that

 point

 and





Apple

 was

 converting

 an

 awful

 lot

 of





their

 stuff

 from

 Pascal

 to

 C

 at

 that





time

 so

 I

 was

 like

 oh

 okay

 well

 C

 could





be

 one

 that

 could

 be

 interesting

 and





then

 ADA

 was

 just

 entirely

 different

 and
</details>

>> 对我们这些不了解 Ada 的人来说，Ada 究竟是什么样的？

<details><summary>Original English</summary>
>> what

 what

 is

 ADA

 like

 for

 those

 of

 us





like

 myself

 who

 don't

 know
</details>

>> Ada 更偏向于那种极其严格的静态检查。

[clears throat]

Ada 这门语言在很大程度上是由国防部的需求和意愿推动的，他们希望确保不会出现 bug；它是一门规范极为详尽、绝不允许你写出错误程序的语言。

<details><summary>Original English</summary>
>> ADA

 is

 much

 more

 in

 that

 very

 very





strict

 static

 checking

 thing





[clears throat]

 um

 ADA

 is

 a

 language





that

 in

 a

 lot

 of

 ways

 was

 driven

 by

 the





needs

 and

 desires

 of

 like

 what

 the





defense

 department

 wanted

 to

 have

 for

 um





for

 knowing

 that

 there

 were

 not

 going

 to





be

 bugs

 of

 of

 a

 language

 which

 is

 very





deeply

 specified

 and

 will

 not

 let

 you





write

 incorrect

 programs.
</details>

>> 是的，我们说的可是真正字面意义上的关键任务（mission critical）领域。

<details><summary>Original English</summary>
>> Yeah.

 We're

 talking

 like

 literal

 mission





critical

 stuff.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 没错，关键任务系统。NASA、国防部等等，Ada 针对的就是这类用户。Ada 现在依然存在，拥有一块小而坚挺的市场。那些做 Ada 的公司主打的卖点就是：“听说你喜欢 Rust？想不想要更多保证？”

[laughter]

Ada 就是处于那样的生态位。而这也是我当年的巨大遗憾之一：当时我对编程懂之甚少，对编程语言也了解不多，我根本没法让代码在 Ada 里编译通过……

<details><summary>Original English</summary>
>> Yes.

 Mission

 critical

 stuff.

 NASA,

 the





defense

 department,

 etc.

 These

 these





were

 types

 of

 people

 who

 ADA

 was

 was





aimed

 at.

 ADA

 still

 exists.

 It

 has

 a





small

 but

 robust

 market

 for

 people.

 And





the

 number

 one

 thing

 that

 the

 ADA





companies

 really

 go

 after

 is,

 "Oh,

 so





you

 like

 Rust.

 How

 would

 you

 like

 to





have

 some

 more

 guarantees?"

 Like





[laughter]

 that's

 that's

 that's

 where





that's

 where

 the

 ADA

 stuff

 is.

 And

 this





is

 this

 is

 one

 of

 my

 great

 regrets

 was





that

 um

 I

 didn't

 really

 know

 much

 about





programming

 and

 I

 didn't

 really

 know





much

 about

 programming

 languages

 and

 I





could

 not

 get

 programs

 to

 compile

 in

 ADA
</details>

>> 在 Ada 里编译不过，是因为它实在太严格了，对吧？

<details><summary>Original English</summary>
>> in

 ADA

 because

 it's

 so

 damn

 strict,





right?
</details>

>> 真的很让人抓狂。而在 C 语言里我就能编译通过。我当时根本没意识到我的 C 程序老是发生段错误（segfault），根本跑不了多久；但那时候只要编译过了，就像拿到了奖赏一样，“好了，我现在可以做别的事了”。但我后来花了好多年去建立直觉，摸索如何在 C 语言中写代码才能让程序不崩溃瓦解。现在我满脑子想的都是——我意识到自己为了写并发 C 和 C++ 以及防止程序出现段错误，给自己立了那么多规矩；尽管我后来变得非常严谨，但我终究是人，总会把事情搞砸。我宁愿让编译器来帮我把关。所以像 OCaml 以及其他类似语言里有很多这方面的东西。呃，F#……

<details><summary>Original English</summary>
>> And

 it

 was

 so

 frustrating

 and

 and

 I





could

 get

 C

 programs

 to

 compile.

 It





didn't

 really

 dawn

 on

 me

 the

 fact

 that





my

 C

 programs

 were

 seging

 all

 the

 time





and

 didn't

 really

 run

 for

 very

 long,

 but





it

 was

 like

 thank

 you

 for

 the

 cookie





that

 it

 compiled.

 you

 know,

 now

 I

 can





move

 on

 to

 the

 other

 thing.

 But

 I

 spent





years

 developing

 an

 intuition

 of

 how

 I





could

 do

 stuff

 in

 C

 so

 that

 my

 programs





didn't

 die

 and

 collapse.

 And

 and

 now

 all





I

 want

 is

 I

 like

 I

 recognize

 like

 I

 had





all

 these

 rules

 for

 myself

 of

 writing





concurrent

 C

 and

 C++

 and

 to

 keep

 myself





from

 uh

 seging

 programs.

 And

 even

 even





though

 I

 became

 really

 rigorous

 with





that,

 I'm

 a

 human

 and

 I

 screw

 stuff

 up





all

 the

 time.

 And

 I

 would

 much

 rather





have

 a

 compiler

 help

 me

 with

 that.

 And





so

 there's

 a

 lot

 of

 stuff

 in

 like

 O'





camel

 and

 other

 languages

 like

 it.

 Uh

 F.
</details>

### F# 与 .NET 的诞生背景

>> 我们能聊聊 F# 吗？

<details><summary>Original English</summary>
>> Can

 can

 we

 talk

 can

 we

 talk

 a

 little

 bit





about

 F?
</details>

>> 可以。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 对于没用过 F#、但可能用过 C# 或 TypeScript 的人，你会怎么描述 F#，它为什么与众不同？它也是微软创造或倡导的一门语言，我不确定到底是不是他们创造的。

<details><summary>Original English</summary>
>> For

 folks

 who

 have

 not

 used

 F

 uh

 but





they

 might

 have

 used

 C#

 or

 TypeScript.





How

 would

 you

 describe

 F

 on

 why

 is





different?

 And

 right

 it's

 it's

 a





language

 that

 Microsoft

 created

 or

 or





they

 championed.

 And

 I'm

 not

 sure

 if





they

 created

 it.
</details>

>> 它出自微软研究院。有位叫 Don Syme 的人，F# 的一切基本上都是由他开创的。它最初其实就是面向 .NET 的 OCaml；而当时的 .NET 只有 C# 以及 .NET 运行时……

<details><summary>Original English</summary>
>> It

 so

 it

 came

 out

 of

 Microsoft

 research.





Um

 there's

 a

 fellow

 Don

 Sim

 who

 is





really

 responsible

 for

 everything

 F

 and





it

 basically

 started

 as

 uh

 O

 camel





fornet

 wheren

 net

 at

 the

 time

 was

 just





car

 and

 then the

 net

 runtime
</details>

>> 而 .NET 是微软的框架，在上面访问 Windows API 非常方便，它有很多实用函数。那是他们的通用框架，基本上就是他们版本的 JVM。

<details><summary>Original English</summary>
>> and

 and

 net

 is

 Microsoft's

 framework





where

 it

 was

 really

 easy

 to

 access.

 I





remember

 Windows

 APIs.

 It

 had

 a

 lot

 of





utility

 functions.

 It

 was

 their





everything

 framework.

 it

 basically

 their





version

 of

 the

 JVM.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 也就是 Java 虚拟机。

<details><summary>Original English</summary>
>> Right.

 The

 Java

 virtual

 machine.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我并没有什么内幕消息，但作为亲历过那个时代的人，当时发生了一大堆法律纠纷：微软在他们的 Java 版本里加入了 Windows 特有的 API，而 Sun 公司威胁要起诉他们。

<details><summary>Original English</summary>
>> And

 I

 have

 no

 special

 insight

 into

 it,





but

 from

 somebody

 who

 was

 around

 when





all

 those

 things

 happened,

 there

 was

 a





whole

 bunch

 of

 legal

 kurfuffle

 with





Microsoft

 adding

 Windows

 specific

 APIs





to

 their

 version

 of

 Java

 and

 Sun





threatening

 to

 sue

 them.
</details>

>> 确实发生了一场官司。我想 Anders Hejlsberg 在这个播客里也分享过这个细节：由于当时悬而未决或正在进行的 Sun 诉讼，他们不得不开发 C#，我想还有 .NET；他们即便想用 Java 也不能再用了，这基本上促成了后来的局面。所以他们打造了 .NET。

<details><summary>Original English</summary>
>> There

 was

 a

 lawsuit

 and

 so

 I

 think





Anders

 Hayesburg

 on

 this

 podcast

 shared





the

 detail

 that

 they

 needed

 to

 develop

 C





and

 I

 guess.NET

 net

 as

 well

 because

 of

 a





pending

 or

 or

 active

 sun

 lawsuit

 and

 so





they

 could

 no

 longer

 use

 Java

 even





though

 they

 wanted

 to

 use

 it

 and

 that





kind

 of

 settled

 it.

 So

 they

 built

 .NET.
</details>

>> 确实是这样。.NET 做得非常出色，因为他们几乎吸收了从 JVM 学到的一切经验，并且针对 JVM 中已经固化、在那时很难改动的理念，做出了不同的设计。这些在当时看来是好得多的构想，现在人们还会争论到底好不好，但这并不重要。.NET 确实是一个非常出色的全方位平台等等。当时上面基本上只有一门语言，那就是 C#，它非常像 Java；两者存在差异，但从根本上说，该语言的基本语义是一样的。是的。

<details><summary>Original English</summary>
>> It

 did

 and

 andnet

 was

 was

 great

 because





they

 took

 like

 pretty

 much

 everything





they

 learned

 from

 the

 JVM

 and

 things





where

 ideas

 have

 been

 baked

 into

 the

 JVM





that

 would

 be

 kind

 of

 hard

 to

 change

 at





that

 point.

 And

 they

 did

 different





things

 which

 at

 the

 time

 seemed

 like





much

 better

 ideas.

 People

 argue

 about





whether

 they

 are

 or

 not

 at

 this

 point





but

 doesn't

 really

 matter.

 But

 you

 know





net

 was

 a

 very

 nice

 platform

 um

 etc

 for





everything

 and

 they

 had

 one

 language





basically

 that

 was

 on

 it

 which

 was

 C





which

 is

 an

 awful

 lot

 like

 Java.

 It

 has





differences

 but

 fundamentally

 the

 basic





semantics

 of

 the

 language

 are

 the

 same.





Yeah.
</details>

>> 所以 F# 当时就是本着“让我们引入一些不同的语义、引入一些不同的东西”的想法而生的，它最初……

<details><summary>Original English</summary>
>> Um

 and

 so

 F

 was

 a

 hey

 let's

 bring

 some





different

 semantics

 let's

 bring

 some





different

 stuff

 to

 this

 which

 was





originally
</details>

<!-- chunk 3/11 -->

### F# 与 .NET 平台的融合

比如，我们试着引入 OCaml。我觉得 F# 真正令人惊叹的地方，其实并不在于它具体的某些语言特性。嗯，因为它确实拥有 OCaml 的绝大部分特性，不过也缺少了一部分。而一些身为 OCaml 死忠粉的人，就特别喜欢抓着它缺少的那部分东西去抱怨。但 F# 带来的、以一种我此前在其他任何事物上都未曾真正见识过的方式展现出来的，是它与 .NET 平台的契合度如此之高，契合得天衣无缝。这是我见过的类似事物中最无缝的体验了——比如我在 JVM 上用 Scala 和其他语言做过很多事情，在与 Java 进行交互时会有很多摩擦和不顺畅的地方，而 F# 则没有这些问题。

<details>
<summary>Original English</summary>
like let's try to bring o camel. And I think the thing that's amazing about F is is not really specifically any language features from it. Um because it it has an awful lot of the things that O camel has, but then it doesn't have some. And some people really like to complain about the stuff that it doesn't have who are big O camel fans or whatever. But the thing that F brought in a way that I've never really seen for anything else is it is it fits so well onto net as a platform and it fits so well. It's really the most seamless experience I've ever seen for something like I I did a lot of stuff with Scola and other languages on the JVM. And there are lots of rough edges with with interacting with um Java where F doesn't have that.
</details>

而且 F# 在很多方面的推进步伐要慢得多。你可以看到 Don 在这方面做得非常出色，他没有让 F# 盲目向前冲，没有把它做成一种在集成上面临困难、充满棱角的语言。他们的做法就像是：我们要把这门语言往前推进一点点，然后等待 .NET 运行时赶上我们，以此确保一切都能持续正常运行；接着，哦，现在 .NET 运行时已经添加了一些新东西，你就会看到这样一种景象——F# 稍稍往前推进一步，然后显然这又在某种程度上启发了 .NET 团队，两者之间就形成了一种共生关系。而且多年来，F# 中大量非常有趣且酷炫的特性都逐步融入到了 C# 中。在语义层面，真正遗漏的大概就只有带有穷尽性匹配的和类型（sum types）了。根据过去几年 C# 发生的变化来看，最终甚至连这项特性大概也会被纳入到 C# 中。

<details>
<summary>Original English</summary>
And F developed in a lot of ways a lot more slowly. And you can see how Dawn did this beautiful job of not running ahead with F and and making a language which would be hard on the integration and having lots of rough edges and they would be like we're going to push this a little bit forward and we're going to wait for the net runtime to catch up to us so that everything continues to work and oh now the net runtime has added some stuff and it's you can see this thing where it's like ah F pushes forward a little and then oh clearly this inspired like the net team some and there's like a symbiotic relationship who's there and over the years an awful lot of the really interesting and cool features from F have made their way into uh C and about the only thing that's really missing at a semantic level is actually the uh the some types with exhaustive matching and based on the changes that have happened in the last few years with C it really looks like eventually even that would probably be incorporated into C
</details>

### Pony 语言的渊源与低延迟需求

>> 还有一门我想向你了解的语言，那就是 Pony。

<details>
<summary>Original English</summary>
>> and then one language which I wanted to ask you about is Pony.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yes.
</details>

>> 什么是 Pony？

<details>
<summary>Original English</summary>
>> What is Pony?
</details>

>> Pony 是一门我参与维护的开源语言。它最初是由我的一位朋友创建的。我们俩当年都上过一所专门招收高中阶段表现不是特别好的学生的大学。是的，招收那些面临挂科甚至高中辍学风险的人，那是一所会接收这类在高中表现不好的学生的早期大学（early college），我的朋友 Sylvan 和我都是这种情况。实际上是 Sylvan 当时对我说：“嘿，如果你去学 Perl……”

<details>
<summary>Original English</summary>
>> Pony is a uh is an open-source uh language that I work on. It was originally created by uh a friend of mine who uh uh we both went to a uh a college for people who had not done particularly well in high school. Yep. and were in danger of say failing out and being high school dropouts where it was a it was an early college that would take people in like that who were not good in high school of which both my friend Silvin and I were like that and Silvin was actually the one who was like hey if you learn Pearl
</details>

>> “……你就可以来波士顿，我们能一起做所有这些事情。”

<details>
<summary>Original English</summary>
>> you can come to Boston we can work on all of this stuff.
</details>

>> 哦，是的。后来我去了另一家机构工作，我们当时试图为银行构建高速数据处理系统。我们一开始是通过为纽约市的一家大银行提供咨询服务来开展这项工作的，当时我们接手不同的咨询项目，并调研各种技术方案。在我们做这些事情的那段时间，我一直在思考这样一个系统应该长成什么样，我想如何去构建它等等。其中一个关键点就在于，它必须非常快，对吧？这样一来就排除了一整类语言。它不仅需要快，还需要具备确定性的延迟保证，而这在 JVM 本身上是极难实现的。在银行内部，这种要求通常只能依赖特殊手段，要么使用 C++，要么使用 Azul……

<details>
<summary>Original English</summary>
>> Oh yeah. So I had gone off to work at a uh a place that was uh we were trying to build a high-speed data processing stuff for banks and we started off by doing that for doing consulting with one of the big banks in New York City and we were just doing different consulting jobs and we were looking at stuff and around the time we were doing that I was thinking about what a system like this would look like and how I'd want to build it etc and everything and a big part of it was it was like it needs to be really fast, right? So this rules out a whole class of languages and it needed to be fast and have latency guarantees in a way that uh the JVM itself made really difficult and was for and for inside of banks was reserved for specialized things of either using C++ or um the Azul
</details>

>> 当你提到 JVM 导致实现困难时，是因为垃圾回收吗？是因为……

<details>
<summary>Original English</summary>
>> when when you're saying the JVM made it difficult was it because of garbage collection was because of
</details>

>> 垃圾回收、延迟问题等等。围绕垃圾回收已经有许多改进工作。但这就像你的延迟偶尔会出现尖刺，比如一个原本应该耗时若干毫秒的普通函数，可能会耗费长得多的时间，因为垃圾回收并非完全随机地触发了。

<details>
<summary>Original English</summary>
>> garbage collection latency issues etc there's been a lot of work on garbage collection It's like sometimes your latency will spike like a normal function that should I don't know take this many milliseconds. It could take way longer cuz garbage collection just kicked off not randomly
</details>

>> 尤其在那个时期，在面向所有人提供的标准 JVM 版本中，所有的垃圾回收都是“全停顿”（stop the world）机制，从字面意思上讲，就是为了回收垃圾，所有进程都必须停下来。因此，当一个请求刚进来时，你的延迟就会从几毫秒飙升到巨大的尖刺峰值。这在交易系统等场景中会带来极其糟糕的后果。哦，是的。所以 JVM 主要是被用于运行在交易系统周边的系统，也就是……但即使在那种情况下，它依然会引发问题。比如你有一个风险控制系统，它本该实时评估是否应该叫停某些特定标的的交易，一旦它出现那样的延迟尖刺，代价依然可能极为昂贵等等。当时有一家公司，他们开发过——现在也依然在做——Azul Systems，他们做了一款无停顿（pauseless）的 JVM，但它的费用非常昂贵，所以大多数项目实际上并不会使用它等等。

<details>
<summary>Original English</summary>
>> particularly at that time on the standard of uh available to everyone uh JVM versions uh all the garbage collection was stop the world which literally means in order to collect garbage everything has to stop and so you have a request that's just come in and your latency is going to go from yeah milliseconds to huge spikes. This would be very bad in like trading systems etc. Oh yeah. So like the JVM was used primarily for systems that ran alongside trading systems which were you know where but even even then it could still cause problems. You have you have a risk system which is supposed to be evaluating uh whether you should shut down trading on particular things or not. Um and it has a spike like that that can still be hugely expensive and whatnot. So there was a company uh they made a uh they still do um uh Zuul Systems and they made a JVM which was pauseless um but it cost a lot of money so most projects didn't actually use it etc and whatnot
</details>

### Pony 的诞生与 Wallaroo 的采用

所以我们当时在考虑，好的，我们要为那些不愿意为这类方案付费的场景寻找替代 JVM 类系统的方案。我们需要某种速度非常快的东西，同时我们必须向客户做出的保证是：我们绝不会丢失你的任何数据，也不会把任何数据搞乱。这意味着需要利用并发来实现速度，在某种程度上要贴近底层硬件（close to the metal）——无论这意味着在数据局部性等方面拥有某种程度的控制，以及所有有助于实现高性能的因素。如果大家对此感兴趣，去了解一下“机械同理心”（mechanical sympathy），Martin Thompson 在这方面做的大量工作可能会非常有启发性。但我们当时就是在寻找这样一组特质：我们需要确保系统能稳定工作，而且对我们而言，确保不搞乱你的数据这一保证至关重要。

<details>
<summary>Original English</summary>
and so we we're looking at okay we're trying to replace the JVM type systems for stuff where people don't want to pay for a and we need something which will be really fast and we also need something where the the guarantee that we had to make for people was we're not going to lose any of your data and we're not going to mess any of it up which is concurrency for speed close to the metal for whatever that means in terms of having some level of control over data locality etc and all of the things that go into being fast um if folks are interested in it looking looking into mechanical sympathy a lot of the stuff that Martin Thompson has done there um can be really interesting but we were looking for this collection of characteristics where we need to know it's working and we and like our guarantees around not messing up your data were incredibly important to us.
</details>

我当时心想：我懂 C。我很擅长 C。嗯，我写 C++ 的风格还停留在 1998 年。所以我不确定自己算不算精通 C++，大体上我写 C++ 依然停留在 1998 年的水平。我当时觉得，我们恐怕无法达成所有这些保障要求；而且我坚信，在初创公司的薪资预算下，我绝对招不到能够凭借那样的工具把这套系统做出来的人才。我当时心想，真不知道该怎么办才好，但我们依然继续做着咨询和这些事情。后来发生了一件可以说是领英（LinkedIn）带给我的为数不多的有用事情之一：我有几年没联系过的 Sylvan 给我发了条消息，说：“嘿，看看我做的这个东西。”那是 Pony 的一个早期版本，当时他一直在摩根士丹利（Morgan Stanley）工作。

<details>
<summary>Original English</summary>
And I was like, I know C. I'm good at C. Um I write C++ like it's still 1998. So I don't know if I would call myself good at C++. I still write C++ like it's 1998 for the most part. And I was like, I don't think that we can meet all of these guarantees and I certainly don't think that I can hire people to work on a startup salary who would be able to pull this off with something like that. And I was like, I don't know what we're going to do for this, but we continue to do consulting and this. And for one of the few useful things that's ever happened to me with LinkedIn, um, Silvin, who I hadn't talked to in a few years, sent me a message and said, "Hey, look at this thing that I made." And it was a it was an early version of Pony where he'd been working at uh Morgan Stanley. Y
</details>

>> 他构建了一个看起来像是……基本上就是 C 语言的东西，对吧？

<details>
<summary>Original English</summary>
>> and he had built a thing that looked like a it was it was basically C, right?
</details>

>> 嗯，它是一个 Actor 模型风格的东西，稍后我们可以深入聊聊 Actor 模型。但它全是用……人们必须在上面用 C 来编写代码。

<details>
<summary>Original English</summary>
>> Um and it was an actor model type thing which we could go into the actor model in a bit, but uh it was all written in people had to write stuff in C.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yep.
</details>

>> 在其之上开发，而且它附带了 C 语言在并发、段错误（segfault）等方面的所有遗留问题——就像当年我选择它而不是 Ada 时它所带有的那些问题一样。运行时本身运转得非常出色，但在其之上编写 C 语言代码的人必须极其专业，必须把每件事都处理得分毫不差，否则就会把运行时赋予他们的所有优良特性给毁掉。于是 Sylvan 决定：“我要离开去深入学习大量的数学知识，这样我就能在类型系统领域变得非常厉害，然后我要去创造属于我自己的编程语言。”为了完成所有这些，他在英国帝国理工学院（Imperial）攻读了博士学位。那段经历最终结出的果实就是 Pony。他给我发了消息说“嘿，看看我做出来的东西”，那正是 Pony。结合我们在 Wallaroo 想要实现的目标，我审视了它，当时觉得这其实有点……

<details>
<summary>Original English</summary>
uh on top of it and it came with all of the problems that C still had in terms of concurrency and seg faulting and everything that it had way back when I picked it instead of ADA and the runtime worked really well, but the people who were writing the C on top of it had to be really expert and had to do things just right or they would mess up all of the great things that the runtime could give them. And so Silvin decided, I'm going to go off. I'm going to learn a whole bunch of math so I can get really good at type system stuff and I'm going to go off and I'm going to make my own programming language. And he did a PhD at Imperial in the UK to do all of that. And the thing that popped out of the end of that was Pony. And he sent me the thing of hey look what I made and it it was Pony and I looked at it for what we were trying to do at Walaroo and I was like this is actually kind of
</details>

>> Wallaroo 是那家初创公司，也就是那家 AI 公司的前身，对吧？

<details>
<summary>Original English</summary>
>> Walu was a startup where it worked at an AI company, right?
</details>

>> 是的。Wallaroo 最终发展成了一家 AI 公司。在那个时间节点上，它是一家……我们正试图向银行等机构销售高速数据处理技术等等。至于 Pony，当时根本没有任何人用过它。我们在决定采用它时，所能拿出的最好说辞——当人们问起“那是什么？”时，我们就会说：“噢，其实它最初是摩根士丹利内部的一个构想，这在试图向银行推销时往往能为你争取到极大的回旋空间。”再加上简街资本（Jane Street）当时基本上是全世界 OCaml 的主要使用者，而且在那个时期 OCaml 已经完全与简街资本绑定在一起了。人们就会说：“噢，那你们是不是……”

<details>
<summary>Original English</summary>
>> Yeah. Walloo eventually became an AI company. At that point in time, it was a we're trying to sell high-speed data processing to banks, etc. and whatnot. Pony, nobody nobody had used it at all whatsoever. Um, there were like the best that we could say when we decided to adopt it and people would be like, "What's that?" We'd be like, "Oh, well, it started as an idea at Morgan Stanley, which can actually buy you an awful lot of uh awful lot of room when you're trying to sell to banks." and the fact that Jane Street was basically the primary user of uh of Oakl anywhere in the world and Oakl had become completely associated with Jane Street at that point. People are like, "Oh, so are
</details>

<!-- chunk 4/11 -->

“你们会像 Jane Street 之于 OCaml 那样，成为 Pony 的代表吗？”我们回答说：“嗯，如果我们足够成功的话，是的，这确实有点像我们的想法。”所以，这可以说是回答这个问题的一大段背景。

Pony 是一门绝对在某种程度上脱胎于 ML 家族的语言。它和 OCaml 有很多共同点。它和 F# 也有一些共同点。因此，它和 Rust 也有一些共通之处。它的定位非常明确：旨在让编写高度异步的快速并发程序变得轻松，并让我为了防止段错误（segfault）而学到的所有规则，都由编译器为你强制执行，而不是像我那样——我做的话总是免不了把事情搞砸……

<details><summary>Original English</summary>
 you going to are you going to be like to pony what Jane Street is to Oak camel?" And we're like, "Well, if we're successful enough, yes, that that's kind of the idea." So, and that's a lot of backstory to to answer the question. Pony is a a language which is absolutely in some way descended from the ML family of stuff. It has some it has a lot of stuff in common with O'Amel. Um it has some stuff in common with F. Um it has some stuff in common with Rust because of that. um where it's very much aimed at making it easy to write fast concurrent programs which are highly asynchronous and make it so that all of the rules that I learned uh to keep stuff from seg faulting are things that the compiler will enforce for you instead of well instead of instead of you doing which what I what I would do which is invariably screw something up
</details>

>> ……然后导致程序崩溃。

<details><summary>Original English</summary>
>> um and and have it crash on you.
</details>

>> 对，我想你之前描述过，Pony 让非法状态变得无法表示。

<details><summary>Original English</summary>
>> Yeah, I think you described pulling makes illegal states unre unrepresentable.
</details>

>> 绝大多数非法状态是这样的，是的。在这一点上它和 Rust 有很多共同点，比如其中之一。但是在并发处理的模型上，两者非常不同。我认为 Actor 模型让并发推理变得容易得多——现在大家了解它大概主要是通过 Elixir，以前你可能会说是 Erlang，但现在多半真的是通过 Elixir 了。而且 Pony 为你提供了一个内置的并发模型，就像 Elixir 和 Erlang 一样，而这是你在 Rust 这类语言中得不到的。它的类型系统以及所有一切，都非常注重让异步编程变得极其简单。

我觉得在结合这些特性的体验上，它是最出色的语言之一。相比之下，其他像 Rust 这样的语言虽然非常擅长为你提供保证等等，但并不一定具备这种完整的、类似包办一切（omccas u sort of thing）的机制来告诉你：“其实无畏并发（fearless concurrency）该这么做”。你不需要自己去挑选搭配一堆东西。我们已经挑选好了一组方案，并为你整合在一起。

<details><summary>Original English</summary>
>> A large majority of them. Yes. Which and in that way it has a lot in common with rust like one of the but the uh the model for how it does that in terms of concurrency is very different. I find the actor model which where um which is probably at this point most popular from elixir and maybe that used to be you could say that it was it was Erlang but now it's probably really elixir on that that the actor model makes it uh much easier to reason about uh concurrency and um uh Pony gives you a built-in concurrency model the same way that Elixir and Erlang do in a way that you don't get with uh something like Rust and is very much the type system and everything is very much built around making it really easy to do asynchronous programming. Um, and I think it has just one of the best experiences for doing that combination of things where there are other languages like Rust which are very good at providing you with um uh guarantees and whatnot but aren't necessarily this full kind of uh uh omccas u sort of thing for no actually here's how you do fearless concurrency. You're you're not picking and choosing a bunch of things. We've picked a bunch of things and we put them together for for you.
</details>

### 垃圾回收与延迟

我们能聊聊垃圾回收吗？我们刚才提到它很慢，但我想引用你在之前写的一篇博文或者演讲里说的话。上面写道：“大多数工程师认为垃圾回收很慢。根据他们的经验，他们并没有错。全停顿（Stop-the-world）回收器确实会摧毁你的所有尾部延迟。但是‘垃圾回收很慢’是把症状与原因混为一谈了。”那原因是什么呢？我的意思是，症状有时就是整个系统停顿下来，对吧？

<details><summary>Original English</summary>
And can we talk a little bit of garbage collection? And we just mentioned how it's slow, but I'll quote you in a blog post you previously wrote or this I think this was a talk. It says most engineers thinks garbage collection is slow. They're not wrong about their experience. Stop the world collectors really do destroy all your tail latencies. But garbage collection is slow confuses the symptom with the cause. What is the cause? And I mean the symptom is that sometimes the world stops, right?
</details>

>> 是的。首先我想说的是，大多数人一想到垃圾回收，就会联想到 JVM 的做法。而在我看来，垃圾回收是另一回事：垃圾回收是程序释放其不再需要的内存的一种机制。因为确实存在这样一种现象，有时人们认为一边是自己在做 malloc 和 free 等操作，另一边则是垃圾回收。但如果你想要追求高性能，你不会一直频繁地调用 malloc 和 free，因为那样非常慢，那些都是系统调用。

人们采取的第一步通常是一次性分配大量内存，然后开始像使用 slab 分配器那样切分小块给自己。他们可能会采用 arena 内存分配。有整整一套内存分配器可用。然后问题就变成了：“我现在在管理这块内存。我怎么知道它什么时候是空闲的，什么时候可以释放它等等？”到那个地步，你其实已经走完大多数人所认为的垃圾回收的一半路程了。

这就变成了一个关于“我该如何做这些事、它们又伴随着哪些权衡”的问题。就 JVM 而言，基本上所有内存都可以从任何线程的任何地方访问到，因此很难在不引发全停顿的情况下释放内存。像 Java 的 Shenandoah 收集器、Azul 的收集器这些并发收集器所做的工作，在实现所谓的并发垃圾回收方面，确实是非常令人钦佩的工程成就。

Pony 拥有一个垃圾回收器，为了不过度深入而讲清本质，这里稍微做一点简化：你可以理解为每个 actor 都有自己的堆，这也是人们描述 Erlang VM（BEAM）时常用的说法——虽然在那里严格来说也不完全是这样，但这么理解会更轻松。每个 actor 负责释放自己使用过的内存。所以你不需要进行全局垃圾回收并让整个程序停下来。取而代之的是，当一个 actor 完成某项工作后，它可以通过某种启发式机制来检查：“我是否有可以释放的内存？”

<details><summary>Original English</summary>
>> Yeah. So well the first thing I would say is that most people when they think of garbage collection they think of like what the JVM does. Um I think of garbage collection as a different thing which is that garbage collection is a mechanism by which your program frees memory that it no longer needs because um there is there is definitely this thing where sometimes people think about you on one side you're doing like malach and free and whatnot and on the other side you have garbage collection but if you want to go fast you you don't malo and free all the time because this is really slow. These are system calls. The first step that people do is they they allocate a whole bunch of memory at once and then they start like slicing off little bits to themselves using like there are things called like slab allocators. They might do arena allocation. There's a whole whole set of memory allocators and then it becomes well I am now managing this memory. How do I know when it's free and when I can you when I can when I can free it etc and whatnot? You're already halfway to what most people think of as garbage collection at that point. And it becomes it becomes a a story of how am I doing these things and what is the what are the trade-offs that these things come with and in terms of the JVM uh all of the memory is basically reachable from anywhere from any thread and the and so it's very hard to be able to free memory in a way that doesn't cause you to have to do a stop the world and the stuff [clears throat] that concurrent collectors like uh Java has the Shenandoa collector Azul has theirs do is actually really impressive engineering for how they managed to do what's called concurrent garbage collection. Pony has a garbage collector, which is instead of having to stop the world, what you have instead is that this is this is a bit of a lie in order to get to the truth without going too deep. But each actor has its own heap is the way that somebody could think about it, which is also how people describe stuff for the Erlang VM Beam, which is also not technically true there, but it makes it easier to think about. and that each actor is responsible for freeing memory that it's used. So you do not you do not garbage collect and stop the entire thing. What you do is instead is that when an actor is done doing some work, it can check to see through some heruristic do I have memory that I can that I can
</details>

>> 对于 actor，我们可以将其理解为类似于线程的东西，可能比线程更轻量一些，但它有点像是你自己的独立世界，与其他 actor 相互隔离？

<details><summary>Original English</summary>
>> and with an actor we can think of like as a something like a thread maybe a bit more lightweight than that but it's kind of your own kind of like world that's kind of separate from other actors or
</details>

>> 没错。因此，这不再是“我要停止整个程序以便释放内存”，而是类似于“哦，我执行了 10 次应用操作，现在我要执行一次内存释放操作”。

使用像 Pony 这样的机制，以及其他类似的、各部分可以彼此独立运行的并发内存释放机制，最终带来的结果是：如果人们在标准的 JVM 配置上运行 Cassandra 之类的程序，通常会看到非常陡峭的延迟尖刺，经常惊呼“哎呀，我的尾部延迟太糟糕了”；而在这里，你得到的基本上绝大部分都是平缓的延迟，或者只是一点微小的起伏。

你所牺牲的一点是：在峰值极限状态下，你的吞吐量可能会比其他方式略低一些。这依然是垃圾回收，只是一种对垃圾回收完全不同的理解方式。

这与很多人在为自己编写复杂的内存分配器时所做的事情，真正的区别在于：到了这一步，他们基本上已经完全把作为程序员的自己从这个过程中解放出来了。他们已经提出了一种用于决定何时释放内存的算法或机制，而不再需要自己去尝试用代码硬编码具体的释放规则。

<details><summary>Original English</summary>
>> Yep. And so instead of instead of I'm going to stop my entire program in order to free memory, it's like oh hey well I did 10 application operations and now I'm going to do one memory freeing operation. And what you what you end up with with with like pony and with other concurrent memory freeing things that are like that where the things can operate independent of one another is you end up with these things where instead of having these really spiky latency things like people are used to seeing if they run things like Cassandra or whatnot on a standard JVM setup where it's just like whoop my tail latencies are really bad is that you just get basically blat latencies for the most part or or a tiny little bridge. And the thing that you give up on that is that at your fastest moment, you have a little bit less throughput than you might otherwise. And this is still garbage collection, but it's just it's it's an entirely different like take on garbage collection. And and it's it's a really the difference between that and what a lot of people end up doing in sophisticated, you know, memory allocators that they write for themselves and whatnot is that at this point they've completely basically taken themselves as a programmer out of the equation. They've come up with an algorithm or something for deciding when memory should be freed instead of them having to try and code in what the particular rules for it would be.
</details>

### 软件正确性与测试的价值

那么我们来谈谈软件正确性。你如何定义软件正确性？

<details><summary>Original English</summary>
So let's talk about software correctness. How do you define software correctness?
</details>

>> 在非常宽泛的层面上，我会将软件正确性定义为：我的程序执行了预期它做的事情。我倾向于用不变量（invariants）来讨论问题，对吧？这是一个更偏向形式化规格说明的术语，但归根结底，不变量就是一种保证，再往宽泛了说，就是我的软件正在执行我期望它做的事情。

但在很多情况下，软件在无法正常工作时，人们并不一定清楚自己期望它做什么，而在它正常工作时，大家也未必清楚。但软件正确性实际上是一种对待软件的态度和思考方式，去了解并确信它正在维系其应当做的事情。它是指——你知道的——能够达成其业务目标或编写初衷，并且不会在凌晨 2 点把任何人吵醒的软件。那就是正确的软件。

<details><summary>Original English</summary>
>> I would define software correctness as my program does what I expected it to do at at a at a really loose level. I tend to talk about things in terms of invariance, right? which is a more formal specification term but in in the end invariant or it's it's a guarantee of which even more loosely is my my software is doing what I expect it to do but in a lot of cases people don't necessarily know what they expect their software to do when it's not working but they don't necessarily know when it's working but software correctness is really about like it is a way of approaching software and a way of thinking about it of being like of of knowing knowing that it is it is upholding what it is supposed to do. It is software which is you know which is going to do its business purpose or whatever it was written for and it's not going to wake anybody up at 2:00 in the morning. That that is correct software.
</details>

对于正确的软件，显然你会想要进行一些测试。但你写过一篇非常有趣的博文，我要引用一下你的原话：“没有人真正在乎测试。”这会伤害到那些确实在乎测试的人的感情。但我坚持这个说法。从一个以热衷谈论测试而闻名的人嘴里说出这种话，可能听起来很奇怪，但我并不看重测试本身。测试只是达成目标的手段。手段并不重要，目标才是一切重要的所在。我写了……

<details><summary>Original English</summary>
Now for correct software clearly you want to you know do some testing but you wrote a very interesting blog post which I'm going to quote you. No one cares about testing. That's going to hurt the feelings of the people who do care about testing. But I'm going to stand by the statement. That might sound all coming from someone who has a reputation for talking about testing, but I don't value tests. Tests are a means to an end. The means are unimportant. The end is all that is important. I wrote that
</details>

<!-- chunk 5/11 -->

### 软件验证与类型系统

因为我当时正在思考自己在 Antithesis 的工作，而人们通常把 Antithesis 看作一家测试公司，但我并不这么认为。我认为它是一家软件验证公司，一家确保正确性的公司。嗯，这对我来说截然不同。测试是你为了验证事物是否按预期运转而采取的手段，是在你没有更好的方法时才使用的手段。比如测试里最糟糕的情况，就是人们经常做的大量手工测试。如果从这一点往回推，你可能会想“也许我可以把它自动化”，然后你的测试就可以做得越来越复杂。用这种测试确实可以做出非常惊人的成果。但归根结底，你依然是在整个开发周期的很晚阶段才去做这件事，对吧？

<details><summary>Original English</summary>
because I was thinking about stuff where I'm at antithesis and people think of antithesis as a testing company and I don't think of it that way. I think of it as a software verification company and a correctness company. Um, which is very different to me. Tests are things that you put in uh in order to verify things are working the way that you can for things that you had no better way to do it. Like the worst case for a test is manual testing that people do a lot of times. And if you walk backwards from that, you can maybe I can automate this and you can get more and more sophisticated with the testing that you're doing. And there is absolutely amazing stuff that you can do with that testing. But in the end, you are still you are still doing something at the late stages in the game, right?
</details>

然而，如果再次回到 C 语言和 Ada 的对比上，比如回到我很久以前做的一个决定，C 语言在正确性方面几乎没有给我提供任何帮助。它就像一把对准我自己脚面的巨大枪支，一次又一次地把我的脚给轰掉。而 Ada 则会为我从一开始就构建正确的软件提供极大的支持，它根本不允许我去写注定不正确的东西。我的 Ada 程序之所以编译不通过，根本原因就在于我想做的事情在本质上是内存不安全的，它们会导致某种内存损坏、崩溃、数据竞争之类的任何问题。

<details><summary>Original English</summary>
Whereas if you go back again to the the C C and ADA thing that like for a decision I made really early on, C gave me almost nothing in terms of correctness. It was just a big giant gun that I was pointed at my own foot and shot my foot off with over and over again. And ADA would give me an awful lot of support for actually constructing correct software from the beginning of not allowing me to do things that were going to be incorrect. The whole reason why my ADA programs wouldn't compile was because they were fundamentally memory unsafe was what I was trying to do and they were going to lead to some sort of memory corruption, a crash, a data data race, any anything like that.
</details>

而且，你知道，我非常坚信在真正进入测试之前，你应该尽可能多地做完这些准备。你应该做到让大家不再需要通过测试来确保“我的东西永远只处于这三种状态之一”。如果你使用某种语言——ML 系语言在这类事情上尤其擅长——你通常可以在类型系统内部去表达这些状态到底是什么、允许的状态转换是什么等等，从而确保事物绝不可能转换到一个你未曾预料到的状态。这意义极其巨大，因为当你思考“我的系统到底能不能正常工作”时，你就不需要从头到脚通盘去想整套系统了。你只需要思考类型系统无法替你表达的那一层内容就行了。

<details><summary>Original English</summary>
And uh you know I I believe very much that you should be you should be doing as much as possible before you ever get to testing that you should you should make it so that these things where people are testing to make sure my thing is only is only ever in one of these three states. If you have a if you have a language and ML languages are particularly good um at this sort of thing. you can usually represent within the type system like what the states are, what the allowable transitions are, etc., and make sure that things can't ever transition to a state that you weren't expecting. This is just it's huge because when you're trying to think about does my system work, you're not thinking about the entire thing all the way down. You're just thinking about the layer of stuff that your type system won't allow you to express.
</details>

我理解 ML 系语言的这一特性，它们确实允许你做更多这方面的事。但我们能不能唱个反调：如果你做测试……测试驱动开发，你先写测试然后再去开发，你是不是也能达到类似的效果？

<details><summary>Original English</summary>
So I understand this with ML languages that they allow you to do a lot more of this. But could we not play devil's advocate that if you do test different testdriven development, you write the tests first and then you develop, you might do something similar.
</details>

### TDD、Kata 与基于属性的测试

\>\> 我非常喜欢 TDD。嗯，我认为 TDD 是写出供人使用的优秀 API 的最佳机制之一，因为你是在切身观察自己究竟该如何与这个具体的东西交互。TDD 生态圈……嗯，非常热衷于被称为 kata 的东西，这些是你去练习的编程小题目……

<details><summary>Original English</summary>
>> So I I love TDD. Um, I think TDD is one of the best mechanisms for writing great APIs that people are going to work with because you're actively looking at how do I actually work with this particular thing. The TDD ecosystem um is very much in love with these things that are called katchas and these are little uh programming exercises that you do and
</details>

\>\> 比如每日一练那种。

<details><summary>Original English</summary>
>> the daily ones.
</details>

\>\> 是的。而且其中有一个经常以不同形式出现的 kata，它始终是一个结对编程题目：其中一个人的职责是编写测试，另一个人的职责则是编写实现来让测试通过。而且作为负责实现的那个人，你应该做的是写出尽可能最简单的代码来让它通过。当别人跟我一起做这个练习时，他们很快就会发现我对这条规则理解得极其死板。我会一次又一次地在实现里硬编码，只是为了让他们特定的基于示例的测试通过——而这正是大多数人在 TDD 和单元测试中所做的，对吧？所以如果题目问的是“嘿，2 加 2 等于几？”，而且他们只有这一个测试，我就直接让它返回 4，对吧？如果他们测 2 + 3，我可以稍微写一小段逻辑说：“噢，好吧。其中一个是 2，另一个是 3。我甚至不去算加法，直接返回 5。”按照 kata 的规则，直到写测试的人对实现感到满意，练习才能停止。而要击败一个极其、极其死板执行规则的人，唯一的办法就是你必须开始随机化输入。一旦你开始随机化输入，太棒了，你现在就进入了人们通常所说的“基于属性的测试”的领域，对吧？完全没错。因为你是在自动生成结果，以便让测试覆盖比你单靠想例子所能覆盖的更广阔的空间。

<details><summary>Original English</summary>
>> Yes. And with there's and there's there's there's one kata that usually comes in different forms uh which is which is always a pair programming one and it is it is one person's job to write the test and it's the other person's job to implement the thing which will make the test pass. And and the thing that you're supposed to do as the person who's doing the implementing is you're supposed to do the simplest thing possible in order to make it pass. And the thing that people when people would do this with me, they quickly discover is I took that very literally. And I would I would just hardcode things over and over and over again into the implementation to make their particular examplebased test, which is what most people do with with TDD and unit tests pass. Right? So if it's like, hey, what's 2 plus 2? And that's the only test they have, I'm just going to have it return four, right? And if they do 2 + three, I can do a little thing that says, "Oh, okay. One of them was two, one of them was three. I'm not even going to do this. I'm just going to return five." The kochi is not supposed to stop until the person who has the test is happy with the implementation, the person who's writing the test. And the only way to defeat somebody who's being very, very, very little at it is that you have to start randomizing the inputs. And the moment that you start randomizing the inputs, great. You're now into the land of what normally what people call property based testing, right? Absolutely. Because you're generating results in order to get it to cover more space than you might come up with for examples.
</details>

\>\> 我的意思是，如果我是坐在你对面的那个人，我大概会想：好吧，肖恩这家伙真是有点混蛋啊。[笑声]

<details><summary>Original English</summary>
>> I mean, if if I was on the other side of that, I I' I'd probably be thinking of like, all right, Sean's being a bit of a jerk here. [laughter]
</details>

\>\> 如果你把这个说法换成更粗鲁一点的脏话，那就是大家平时经常对我说的原话了。是的。

<details><summary>Original English</summary>
>> If you take that and and you make it a bit more profane, that was what people would say to me on a regular basis. Yes.
</details>

因为……本质上你的意思就是，你会特意做到这种地步：比如说加法，对吧，比如有个问题像……好吧，比如求和，你输入数字它吐出结果，这实现起来非常简单对吧？如果我开始写测试，你来写实现，你……你甚至可能真的就是开始针对边界情况写代码，比如“噢，如果是这个就返回那个，如果是那个就返回这个”；而且我写的测试越多，你就会觉得“我可以一直这么干，我只要在里面加更多的 if 语句就行了”。而你的意思是，打败你唯一的办法要么是让测试做随机的事情，要么就是发明或者接触到基于属性的测试这个领域，在这里你可以针对某条属性直接运行所有的输入。[笑声]

<details><summary>Original English</summary>
be because like basically you're saying that you would go to the efforts of like let's say if I you know like addition right like there's a question of like all right like a sum like you put in numbers and it spits it out very simple to implement right if I start writing the tests and you write the implementation you you you might just literally like start like write edge cases for like oh if this return that if that return this and just just the more tests you write you'll be like I I can keep doing this I'll just add more if statements in there and you're saying the only way to beat you was to either have your tests do random things or invent or come across the the area of property based testing where you can say for this property just run every single one of them. [laughter]
</details>

\>\> 差不多就是那样。而且……是的，大家在那件事上确实会被我搞得很抓狂。但是等我们做完这个练习，在我们……我工作过的其中一家公司，我们定期会做这个练习，所有的工程师都会参与。无论谁跟我分到一组，出来的时候都会说“我是唯一一个没做完练习的人”，但他们同时也会说“噢天呐，我觉得我现在写测试的能力肯定比以前强多了”。

<details><summary>Original English</summary>
>> Yeah. Yes. Some something like that. And and yeah, people would get frustrated with me with that. But by the time we were done with the exercise, you we we the one place I worked with we we periodically would do this. would like all the engineers would do this and whoever it was who got paired with me would come out and be like I'm the only one who didn't finish the exercise but they would be like also oh my god I think I'm going to be much better at writing tests now
</details>

### 编译器与复杂系统的演进

\>\> 这很棒，这确实能带来更好的测试，但归根结底，被测试的大量内容，如果你有一个更强大的编译器，其实完全没有必要去测。

<details><summary>Original English</summary>
>> and it's great and this is this is this is a thing that can lead to much better tests but in the end like awful lot of the things that were being tested were things that you wouldn't necessarily have to test if you had a stronger compiler
</details>

\>\> 而且你知道，那家特定的公司是一家用 Java 的公司。Java 确实有它的类型系统，能够防止很多事情发生，但它依然允许极大的自由度，就像 C 语言允许极大的自由度一样。多年以来，嗯，我一直是个热爱动态编程语言的人。Smalltalk 至今依然是我最喜欢的编程语言之一，我极其喜欢它。我写过很多 Ruby，写过很多 Perl，也写过很多 Python。我过去总觉得“写这些我根本不需要编译器的帮助，对吧”。后来我终于意识到：好吧，确实如此，但那是因为我以前主要是在小型系统上工作……

<details><summary>Original English</summary>
>> and you know that particular place was a Java a place and there there's a type system for Java which can prevent a number of things but still allows an awful lot of freedom in the same way that uh the same way that C allows an awful lot of freedom for years um I was I was I was a person who loved like uh dynamic programming languages small talk is still one of my favorite programming languages I absolutely love it I wrote a lot of Ruby I wrote a lot of Pearl I wrote a lot of Python and I was always like I don't really need the compiler's help for this right and I eventually realized it was well yeah but that's cuz I primarily worked on small systems
</details>

\>\> 在那里我可以把所有的东西都装在自己的脑子里。

<details><summary>Original English</summary>
>> where I could hold everything in my head
</details>

\>\> 而且我当时只做一个系统，所有的东西在脑子里都随时保持清晰。而当我开始在更大的系统以及更大的公司里工作时，需要打交道的东西变得更多了，与我共事的人也更多了，更多我不真正了解细节的东西进入了系统。这时我开始真正看重编译器的价值，哪怕是在 Java 里面，你也可以像这样：好吧，既然我应该替换这个类，我就直接把这个类删掉，编译器至少能告诉我每一个被破坏的地方，这样我就能对需要在代码库的哪些地方进行探索有个底了。

你写过的另一件事是这个被称为“负载”（workloads）的东西，你其实还就此做过一次演讲，嗯，你写道“你的测试策略里很可能漏掉了一个重要的东西——负载”。什么是负载？

<details><summary>Original English</summary>
>> and I only worked with one system and it was just always fresh of mind and when I started working on bigger systems and at bigger companies where there were more things that I had to work with and there were more people who I was working with more things entered the system where I didn't really know what it because I started to really value like things even even with with Java you could just be like okay well I'm supposed to be replacing this class I'm just going to delete this class and the compiler at least tell me every single place that breaks and I can start to have an idea of where do I need to explore the codebase one thing you wrote about is this thing called workloads and you actually did a talk on this uh and you wrote you're likely missing an important thing in your testing strategy workloads. What are workloads?
</details>

\>\> 那么，嗯，对于像基于属性的测试这样的东西，或者……

<details><summary>Original English</summary>
>> So, um, with things like property based testing or
</details>

\>\> 而且基于属性的测试是指，你说“我的函数，这里是可以传给它的一个属性，比方说这是一个整数”，然后你的测试装置就可以直接……

<details><summary>Original English</summary>
>> and property based testing meaning that you you say my function here's a property that can be passed. Let's say this is an integer and then your test hardness can like just
</details>

\>\> 如果它是一个 int32，它真的可以直接遍历所有的整数，或者它可以……

<details><summary>Original English</summary>
>> if it's an in32, it could literally go through all the integers or it can
</details>

<!-- chunk 6/11 -->

做随机操作，或者可以做一千次这类操作，等等。是的。但是，一旦你越过了大多数人用于基于属性的测试（property-based testing）的那些简单情况——比如，“这是一个属性，用来展示你可以反转一个列表，然后再反转一次，你就会得到开始时的同一个东西”，这非常简单——但如果你想开始把它应用到“我想对我的分布式系统或我的数据库进行基于属性的测试”，例如……
<details><summary>Original English</summary>
do random or it can do a thousand of them, etc. Yeah. And but once you get past the the simple cases that most people use for property based testing which is like here's a property for showing that that you know you can reverse a list and then you can reverse it again and you have the same thing you started with which is really simplistic but if you want to start applying this to I want to do property based testing on my distributed system or on my database for example
</details>

>> 工作负载（workload）就是无论你用来验证该事物是否真正在工作的任何东西，并结合你为了驱动代码、为了测试它而将要创建的输入，对吧？举个简单的例子，如果你想测试一个键值存储（key-value store），对吧？
<details><summary>Original English</summary>
>> the the workload is whatever it is that you're going to use to validate that the thing is actually working combined with the inputs that you're going to create in order to drive your code in order to in in order to test it, right? As as a simple example, if if you wanted to test a key value store, right?
</details>

>> 那么……
<details><summary>Original English</summary>
>> Then
</details>

>> 比如 Redis 或你自己的键值存储，
<details><summary>Original English</summary>
>> like Reddus or your own key value store,
</details>

>> 你有一个键值存储。它有三个操作：get、put 和 delete。嗯，那些都是将要输入到系统中的东西，并且是你工作负载的一部分。但作为工作负载的附加部分，你将必须决定：我打算拥有多少个键？我要查找的键范围是什么样的？键有多大？我打算放进去的值有多大？而你的工作负载就是所有这些东西的结合。它是你的系统，它是你用来判定它是否在工作的东西，它同样也是进入系统的输入。

人们在阅读有关基于属性的测试时，看到这些比如“噢，反转一个列表”的简单例子，就很容易觉得：“噢，好的，太棒了。这是随机性。随机性会帮我实现这一点。”因此，某人可能会做的一个简化版本就是：“好的，我有三个操作，一个 get、put 和一个 delete，我要选择其中一个操作来做。”在忽略可能拥有不同键等事实的这种简化方式下讨论：如果你那样做，你实际上不会触发代码中太多有趣的地方。因为你有均等的机会，你做了一个 put，然后你可能很快就会在附近某个点做一个 delete。而你连续做比如 10,000 次 put、并可能推进到你的系统可能需要开始将内容换出到磁盘或进行某种垃圾回收的区域的几率……
<details><summary>Original English</summary>
>> you have a key value store. It has three operations, get, put, and delete. Um those are those are all things which are going to be input into the system and are part of your workload. But as an additional part of your workload, you're going to have to decide how many keys am I going to have? What is the range of keys I'm going to look like? How big are the keys? How big are the values that I'm going to put in there? And your workload is this combination of all the stuff. It's your system. It's your things that you're going to use to decide whether it's working. And it's the inputs into the system as well. And it's very easy for people when they read about property based testing and they see these simple examples of like, oh, reverse a list to be like, oh, okay, great. It's randomness. Randomness is going to get this for me. And so a a simplified version of what somebody might do is be like, okay, I have three I have three operations, a get, put, and a delete, and I'm going to pick one of those operations to do. Talking about it in the simplified manner where we're ignoring the fact that you could have different keys and whatnot. If you do that, you're not actually going to trigger too many interesting places in your code because you have an equal chance of you do you do you do a put and then you're probably going to do a delete at some point nearby. And the odds of you doing say 10,000 puts in a row and potentially pushing into areas where your thing might need to start swapping stuff out to disk or or do some type of garbage collection or
</details>

>> 或者重新分片（resharding）等等。
<details><summary>Original English</summary>
>> or resharding etc
</details>

>> 或者重新分片，其中任何一种。它们根本就不会发生，因为你就只是在这个小范围周围移动……
<details><summary>Original English</summary>
>> or resharding any of those. They're simply never going to happen because you're just moving right around this little
</details>

>> 是的。就是针对一两个元素上下波动，这……
<details><summary>Original English</summary>
>> Yeah. just up and down for like one or two elements which is
</details>

>> 这是一个醉汉漫步（drunken walk），而醉汉漫步永远不会离起点太远。所以，是的，工作负载很大程度上在某种程度上就是——很大一部分就是：哪些输入能够在这里驱动出有趣的行为？有时对于像键值存储这样的东西，它可能意味着，“嗯，我需要把它推进到非常有趣的地方。”但另外有时，工作负载可能看似非常简单，却能为简单的一面验证非常、非常、非常强大的东西。嗯，因为如果我们要讨论输入那一面，我们需要一块白板。嗯，对于简单的那一面，有一种工作负载通常用于测试 ACID 数据库中的隔离性保证，这……
<details><summary>Original English</summary>
>> it's it's a it's a drunken walk and drunken walks never get very far from where they start. So yeah, the the the workload is very much in in part about like a big part of it is just what are the inputs that can that can drive interesting behavior here. And sometimes for something like the key value one, it might mean well I I need to drive it to really interesting places. But also other other times uh workloads can be deceptively simple and and validate really really really powerful things for the simple side. um because we need a whiteboard if we're going to do the the input side. Um for for the simple side, there's there's there's a there's a workload which is commonly used for testing uh isolation guarantees in asset databases which
</details>

>> 我不知道，我认为这可能是你想用 ACID 数据库保证的单一最重要的事情。它被称为银行测试（bank test），它几乎就是你能想到的最简单的东西，非常神奇。你在一个表中设置若干个全部存在的账户，对吧？然后你说在这个系统中有 10,000 美元，我们要把这些钱分配给我们拥有的无论多少个账户。假设 10 个账户，每个账户初始都有 1,000 美元。如果在系统中有 10,000 美元，而对于这个工作负载我们要做的全部事情就是：我们仅在一个事务内部，把钱从一个账户转到另一个账户，这仅仅意味着把它从一列移动到另一列。我们还要有另一个东西在同一时间运行，并且只是不断地查询：系统中存在的总金额是多少？如果隔离性保证成立，那么它应该看到的唯一值就是 10,000。
<details><summary>Original English</summary>
>> I don't know I think is probably the single most important thing that you want to guarantee with a with an asset database and it's called the bank test and it is just about the simplest thing you could possibly it's amazing. So you set up some number of accounts that all exist in a table, right? And you say in this system there's $10,000 and we're going to divide this up amongst these what however many accounts we have. So we say 10 accounts. Each one of them starts with $1,000. And if there's $10,000 in the system and all we're going to do for this workload is we're going to just inside of a transaction, we're going to transfer money from one account to another, which just means moving it from one column to another. And we're going to have another thing that runs at the same time and is just constantly querying what is the total amount of money that's in the system. And if the isolation guarantees hold, then the only value it should ever see is 10,000.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 这是一项非常简单的测试。
<details><summary>Original English</summary>
>> And this is a very simple test
</details>

>> 因为你一直在彼此之间转账。
<details><summary>Original English</summary>
>> because you keep transferring between one another.
</details>

>> 是的。并且你运行许多不同的事务。很有可能，如果在……我是说如果数据库很优秀，那么在只在笔记本电脑上运行它的正常情况下，你应该永远看不到任何奇怪的故障。然而，你把这作为一个比如分布式数据库，并把它放入一个你开始向其中引入故障的环境中，比如引入节点之间的网络故障、杀掉节点等等。嗯，Kyle Kingsbury 凭借他的 Jepsen 相关工作让这变得名声大噪，经常登上 Hacker News 榜首之类的。这与我们在 Antithesis 所做的属于同一类，各种有趣的 bug 开始从这个非常简单的工作负载中冒出来。这是因为，它正在考验系统的一个非常核心的约束、一个不变量，即我永远不应该能够读取另一个事务内部正在发生的事情。

但工作负载本身是——工作负载是你描述系统：“这是 10,000 美元，这是账户，这是你可以在它们之间转移的方式”；还是说工作负载是像其中一件事，比如在账户之间转移资金，然后你就像“让我们把这个重复很多很多次”？这取决于你想采取多大程度的极大主义视角，对吧？你可以在某种意义上谈论它：工作负载也是你在整个过程中测试的特定数据库，因为 Postgres 做那些事情的方式可能与 MySQL 或其他某个数据库略有不同，因此你可以把它称为一个不同的工作负载；或者你也可以仅在概念层面上把银行测试作为一个工作负载来谈论，这时你甚至没有考虑其中的数据库或任何特定的实现细节。人们经常从这两个极端来谈论工作负载：既可以把纯粹柏拉图式意义上的银行测试本身看作一个工作负载，对吧；但随后也存在它的非理想化版本，其中存在一个特定的实现存在于这里。
<details><summary>Original English</summary>
>> Yep. And and you and you run many different transactions. And the odds are if if I mean if the database is good then in a normal situation where you just run this on your laptop you should never see any any any weird failures. However you take this as like a distributed database and you put it into an environment where you start in introducing faults into it like say introducing network faults in between nodes killing nodes off etc. Um Kyle Kingsbury with his Jeepson stuff made this hugely famous regularly going to you know like the top of hacker news and everything. It's in the same vein of what we do at antithesis as well and all sorts of interesting bugs start popping out from this really simple workload. And it's because it's exercising like a really core constraint there of of the system an invariant which is that I should never be able to read something that's happening in inside another transaction. But the workload itself is is the workload you describing the system. Here's the $10,000. Here's the accounts. Here's how you can move between them or is the workload like one one of these things like moving moving money between accounts and you're like let's repeat this like many many times depending on on how maximalist of a view you want to take, right? You could you could you could be talking about it in a sense where the workload is also the particular database that you're testing in this entire thing because Postgress has a slightly different way of doing those things perhaps than like my SQL than some other than some other database and therefore you could talk about that as a different workload or you could just talk about at a conceptual level the bank test as a workload where you're not even considering the database that's in it or any of the particular implementation details and people regularly talk about workloads from both of those ends from just the the bank test in in in a platonic sense right is a workload right but then there's also the you know the non idealized version of it where there's a particular implementation you know that that exists here
</details>

>> 那么在我脑海的模型中，我能否把“工作负载”替换为一个复杂的测试用例，或者一系列复杂的测试用例，就像我们用来测试的这个东西，对吧？就像工作负载旨在测试某些东西，或者重演一个场景之类的，对吧？
<details><summary>Original English</summary>
>> so could I substitute in my mental model workload as a complex test case or a complex series of test cases and like this thing that we're we're using to test right like a workload is is is meant to test something or or or play or replay a scenario or something like that, right?
</details>

>> 通常不是重演一个场景。那会是……
<details><summary>Original English</summary>
>> Usually not replay a scenario. That would be
</details>

>> 不是重演。是的。但比如构建一个场景。
<details><summary>Original English</summary>
>> not replay. Yeah. But like construct a scenario.
</details>

>> 所以我会避免使用“构建”这个词，因为现在当我们谈论构建时，我们又回到了看起来像我们在单元测试中所做的那种基于示例的事情。
<details><summary>Original English</summary>
>> So I would avoid the word construct because now when we're we're talking about construct, we're we're getting back in towards a thing that looks like the example based stuff that we're doing with unit test.
</details>

>> 是的。当你编写具体的东西时。所以，所以它更像是：工作负载的要点在于你设定规则，然后它在某种程度上自行演进。就像在这个银行转账的例子中，我们从不说我们究竟应该如何转账。我们只是想要随机地、非随机地来回转账，理想情况下命中边缘情况，发挥创意，对吧？而那就是工作负载。
<details><summary>Original English</summary>
>> Yeah. When you write the specific thing. So, so it's more like the point of the workload is that you set the rules and then it kind of works itself out. Like in in this case with the bank transfer stuff, we never say exactly how we should transfer. We just kind of want transfers back and forth randomly, non-randomly, ideally hit interesting edge cases, you know, just just get creative with it, right? And that is the workload.
</details>

>> 是的。并且如果是……如果是像大多数已经存在了一段时间并且经历过某种严格测试的软件那样，那么像银行测试这样的工作负载不应该暴露出任何 bug。它们不应该出现，对吧？也许更复杂的工作负载可能会暴露出来。但这完全取决于具体情况。但对于像银行测试这样的东西，它不应该。但是，当你开始让它承受像 Jepsen 或 Antithesis 类型的体验时——这也是生产环境中一直发生的那种体验，而且就像 Lorin Hochstein 一直非常出色地撰文记录的那样……
<details><summary>Original English</summary>
>> Yeah. And and if it's and if it's like if it's like most software that's been around for a while and is and has gone through some sort of rigorous testing, then no bug should pop out of a workload like the bank test. They they shouldn't, right? Perhaps more complicated workload stuff might pop out. But it really depends. But for something like the bank test, it shouldn't. But bugs will start popping out like crazy from something like the bang test when you start subjecting it to like a Jeepson or an antithesis type experience which is also the type of experience that happens all the time in production environments and that like uh Lauren Hawkstein does a incredible job all the time writing up for
</details>

<!-- chunk 7/11 -->

“嘿，这次事件里发生了什么，这次事件里到底发生了什么。让我作为一个长期深谙此道的人，试着来为你拆解一下。”你谈到质量时说过一件很有意思的事——我再引用一下你的话——就是关于质量并不是一道关卡。你写道：“质量并不是关卡。整个‘关卡’的概念建立在我们正拉入阳光下的某种信念之上。这种信念认为，质量是你通过把坏东西挡在门外来维持的。在门口就抓住 Bug。这是一幅令人安慰的图景，但这不是优秀的团队保持优秀的方式。”所以这在很多层面上正是为什么我不喜欢把“测试”作为一个概念来谈，而更喜欢谈“正确性”，因为……

<details><summary>Original English</summary>
hey

 here's

 what

 happened

 in

 this





incident

 here's

 what

 happened

 in

 this





incident

 let

 me

 let

 me

 as

 somebody

 who's





like

 been

 versed

 in

 this

 stuff

 for

 a





long

 time

 try

 to

 break

 it

 down

 for

 you





and

 One

 interesting

 thing

 you

 said

 about





quality

 and

 I'll

 quote

 you

 again

 is

 is





uh

 on

 how

 quality

 is

 not

 a

 gate.

 And

 so





you

 wrote

 quality

 is

 not

 a

 gate.

 The





whole

 gate

 idea

 rests

 on

 a

 belief

 we're





dragging

 into

 the

 light.

 The

 belief

 is





that

 quality

 is

 something

 you

 hold

 by





keeping

 the

 bad

 out.

 Catch

 the

 bug

 right





at

 the

 door.

 It's

 a

 comforting

 picture,





but

 it

 isn't

 how

 good

 good

 teams

 stay





good.

 So

 this

 is

 this

 is

 this

 is

 really





in

 a

 lot

 of

 ways

 why

 I

 don't

 like





talking

 about

 testing

 as

 a

 thing

 and

 I





like

 talking

 about

 correctness

 because





like
</details>

### 正确性与构造即正确

>> 尽可能地，你的系统无论是什么，从你编写软件的方式以及能够获得的静态检查起，就根本不应该允许坏事发生。就像在理想世界中，你应该能够用类似 TLA+ 或 Alloy 之类的语言编写规约，并将其作为实现进行完美呈现，或者理想情况下直接采用该规约，神奇地将其转化为实现，同时不知何故还具备你所有的性能要求等等。我们离那个世界还差得很远，但那会是一个理想的世界。你只需知道绝不可能发生坏事，因为你已经使用模型检查器证明了这一点。它们能为你做到令人难以置信的事情。而我们其实并没有那种条件。

<details><summary>Original English</summary>
>> for

 as

 much

 as

 possible

 your

 system

 for





whatever

 it

 is

 should

 not

 allow

 bad





things

 to

 happen

 period

 from

 just

 how





you

 can

 write

 the

 software

 and

 static





checks

 that

 you

 should

 be

 able

 to

 get





like

 in

 an

 ideal

 world

 you

 should

 be





able

 to

 write

 a

 specification

 in

 like

 a





language

 like

 TA+

 plus

 or

 or

 alloy

 or





something

 like

 that

 and

 have

 a

 perfect





representation

 of

 that

 as

 an





implementation

 or

 ideally

 just

 take

 that





and

 and

 put

 it

 like

 be

 able

 to

 magically





go

 from

 that

 into

 an

 implementation





which

 somehow

 also

 has

 all

 of

 your





performance

 stuff

 etc.

 We're

 nowhere





near

 close

 to

 that

 world,

 but

 that

 would





be

 an

 ideal

 world.

 And

 you

 just

 simply





know

 that

 no

 bad

 thing

 can

 happen





because

 you've

 you've

 used

 a

 model





checker

 to

 prove

 this.

 And

 they

 can

 do





incredible

 things

 for

 you.

 And

 we

 don't





really

 have

 that.
</details>

嗯，所以我们能达到的另一个层次，就是在类型系统内部进行静态检查，就像 Pony 所做的，像 Rust 所做的，像 OCaml 所做的那样。以一种有趣的方式，Erlang 同样做了很多这类事情，但它是在没有类型系统的情况下完成的，而是通过 Actor 模型来实现：我们将限制你在操作上实际能做的事情，你必须通过消息发送所有内容，而且在每一条消息中，一个 Actor 拥有的数据都会被复制并发送给另一个 Actor，从而由于内存从未真正共享而不可能出现共享内存的数据竞争。它只是被复制了。通过这种方式，我们也做到了一种“构造即正确”的事情，这种效果你同样可以从类型系统或其他机制中获得。

<details><summary>Original English</summary>
Um,

 and

 so

 another





level

 that

 we

 can

 go

 to

 is

 just

 static





checking

 inside

 of

 type

 systems

 for





things

 for

 for

 the

 stuff

 that

 like

 Pony





does,

 for

 the

 stuff

 that

 like

 Rust

 does,





for

 the

 stuff

 that

 Okamel

 does.

 Um,

 in





an

 interesting

 way,

 Erlang

 does

 a

 lot

 of





this

 type

 of

 stuff

 as

 well,

 but

 it

 does





it

 without

 a

 type

 system,

 but

 it

 does

 it





with

 the

 actor

 model

 for

 we're

 going

 to





limit

 what

 you

 can

 actually

 do

 in

 terms





of

 stuff

 where

 you

 have

 to

 send





everything

 by

 messages

 and

 every

 single





message

 the

 data

 that

 one

 actor

 has

 is





copied

 uh

 and

 sent

 to

 another

 actor

 such





that

 there

 can't

 be

 any

 data

 races

 with





the

 sharing

 of

 this

 memory

 because

 it's





never

 actually

 shared.

 It's

 just

 copied.





And

 in

 this

 way,

 we've

 also

 done

 a





correct

 by

 construction

 sort

 of

 thing





that

 you

 could

 also

 get

 from

 a

 type





system

 or

 whatnot.
</details>

我们希望以此为基础进行构建。而测试层面应该针对的是那些无论我们可用的静态手段是什么都无法强制执行的事情，因为归根结底我们只有编程语言，而编程语言都伴随着权衡。某种或许拥有完美类型系统来表达你需要做的一切的编程语言，首先它大概率不存在；其次即使存在，它可能在性能或其他方面也不具备你同样需要的某些特性。因此你必须做出一些妥协，挑选一门具有更好性能保证或其他特性的语言。到了那个阶段，剩下的就只有测试和验证了。

<details><summary>Original English</summary>
And

 we

 want

 to

 have





this

 foundation

 to

 build

 upon.

 And

 the





the

 testing

 aspect

 should

 be

 for

 the





things

 that

 whatever

 our

 static

 means





that

 we

 have

 available

 to

 us

 just

 can't





enforce

 because

 in

 the

 end

 we

 only

 have





we

 have

 programming

 languages

 and

 the





programming

 languages

 all

 come

 with





tradeoffs.

 and





like

 um

 the

 programming

 language

 that





maybe

 has

 the

 perfect

 type

 system

 to





represent

 everything

 that

 you

 need

 to





do.

 Well,

 one,

 it

 probably

 doesn't





exist.

 And

 then

 two,

 even

 if

 it

 did





exist,

 it

 probably

 would

 not

 have

 some





characteristic

 that

 you

 also

 needed

 as





well

 in

 terms

 of

 performance

 or





something

 else.

 So,

 you

 need

 to

 settle





some

 and

 pick

 a

 language

 that

 has

 better





performance

 guarantees

 or

 or

 what





whatever

 it

 is.

 And

 then

 at

 that

 point





what

 you're

 left

 with

 is

 testing

 and

 and





verification.
</details>

### 质量关卡与漏斗模型

>> 是的。但我有点想反驳这种关于质量关卡的看法，因为质量关卡的想法是这样的：好吧，你构建了代码，你有编译器，它会做一些事情，出于现实原因我们使用的语言在应用层会出现一堆 Bug，哪怕编译器是完美的。它无法测试业务逻辑是否正确。然后我们过去的思维方式，或者我认为很多人现在的思维方式是：好，你写出了这个东西，你设置了质量关卡，比如有代码审查、CI/CD、静态分析，我想在生产环境中你还有可观测性；存在着这些关卡，有点像有时你会看到的瑞士奶酪模型，每一层都会拦截一些东西。比如代码审查有时可能会捕获 Bug，尽管我们知道这不是做这件事的好地方，尤其是现在我们不确定代码审查正在发生什么变化，但它可能会捕获 Bug 或可读性问题；在 Google 内部他们有可读性审查，在他们那种情况下会捕获合理性问题；然后 CI/CD 会通过测试捕获一些 Bug，或者我们见过并为此编写了代码的一些回归问题等等。你却说质量关卡是……质量并不是关卡。那这是意味着你不赞成在发布流程中设置这些——我想我们就叫它们关卡吧——还是你只是说换个角度思考，比如从一开始就考虑它？感觉你像是把质量的概念拉回到了最开始，对吧？

<details><summary>Original English</summary>
>> Yeah.

 But

 I

 kind

 of

 want

 to

 push

 back

 on





this

 like

 the

 quality

 gates

 because

 the





idea

 of

 quality

 gates

 is

 like

 okay

 you





build

 a

 code

 you

 have

 a

 compiler

 it

 does





some

 stuff

 the

 languages

 we

 use

 for





practical

 reasons

 will

 there

 be

 a

 bunch





bunch

 of

 bugs

 for

 application

 level

 bugs





even

 if

 the

 compiler

 was

 perfect.

 It





couldn't

 test

 for

 the

 the

 business

 logic





being

 correct.

 And

 then

 the

 the

 way

 we





used

 to

 think

 about

 it

 or

 or

 I

 think

 a





lot

 of

 people

 still

 think

 about

 it

 is





okay

 you

 write

 this

 thing

 and

 you

 have





quality

 gates

 you

 have

 like

 code

 review





CI/CD

 static

 analysis

 I

 guess

 in





production

 you

 have

 observability

 and





there's

 these

 gates

 where

 like

 it's

 a





little

 bit

 like

 sometimes

 you'll

 see

 the





Swiss

 cheese

 model

 like

 each

 layer

 will





catch

 some

 stuff

 like

 code

 review





sometimes

 it

 might

 catch

 bugs

 although





we

 know

 it's

 not

 a

 great

 place

 to

 do

 it





but

 especially

 now

 we're

 not

 sure

 what





happening

 with

 code

 review

 but

 it

 could





catch

 bugs

 or

 or

 readability

 inside

 of





Google

 they

 have

 readability





review

 like

 it

 will

 catch

 reasonability





issues

 in

 in

 their

 case

 and

 then

 CI

 CD





will

 catch

 some

 some

 bugs

 with

 the

 test





or

 some

 some

 regressions

 that

 we've

 seen





and

 we've

 coded

 things

 for

 them

 and

 so





on.

 You're

 saying

 that

 quality

 gates

 is





is

 that

 quality

 is

 not

 a

 gate.

 So

 does





that

 mean

 that

 you

 don't

 believe

 in





having

 these

 I

 guess

 let's

 just

 call





them

 gates

 in

 your

 release

 process

 or





you're

 just

 saying

 just

 think

 about

 it





differently

 like

 think

 about

 it

 from

 the





beginning

 you're

 it

 feels

 like

 you're





taking

 back

 the

 idea

 of

 quality

 to

 the





to

 the

 very

 beginning

 right
</details>

>> 很大程度上就在那里。而且我还想说，我不同意你关于业务逻辑不能被静态强制执行等等的说法，不过我们先把那个兔子洞搁在一边。但除此之外，比如……

<details><summary>Original English</summary>
>> it

 very

 much

 there

 and

 also

 I

 would

 say





I

 I

 disagree

 with

 your

 statement

 that

 uh





business

 logic

 can't

 be

 statically

 uh





enforced

 and

 whatnot

 um

 um

 but

 let's





let's

 leave

 that

 let's

 leave

 that

 rabbit





hole

 aside

 for

 now

 but

 uh

 additionally





like
</details>

>> 测试，特别是在 Jepsen 和 Antithesis 这类风格之外通常所采用的方式。

<details><summary>Original English</summary>
>> testing

 particularly

 in

 the

 way

 that





it's

 it's

 normally





done

 outside

 of

 the

 Jeepson

 and





antithesis

 type

 style.

 Um
</details>

>> 单元测试以及在 CI/CD 中运行的测试。Honeycomb 有很棒的 T 恤，对吧？“我在生产环境中测试”，那是……

<details><summary>Original English</summary>
>> the

 unit

 testing

 and

 testing

 when





they're

 run

 CIC

 is

 the

 um

 honeycomb





has

 awesome

 shirts,

 right?

 I

 test

 in





prod

 which

 is
</details>

>> 可观测性平台。对。

<details><summary>Original English</summary>
>> observ

 platform.

 Yeah.
</details>

### 生产环境与质量假象

>> 是的。而且事实确实是，最终每个人在某种程度上，不管承认与否，都在生产环境中测试。我们拥有的所有工具都无法完全保证任何东西。即便你借助类似 Antithesis、Jepsen 这样的工具做得极其出色，设想出了所有这些绝妙且有趣的输入，依然会有某些在某个时间点损坏的数据存在于你的生产系统中，而你并未随机触发它。你的生成器根本无法生成在生产环境中即将发生的事情，而我们根本不知道它潜伏在那里，我们正在对此进行测试。这种认为我们有所谓关卡、觉得“只要通过了这一关，它就代表质量达标，就可以发布出去”的想法，其实某种程度上就是一个谎言，对吧？随着流程推进，我们抱有的希望是信心程度不断提高，但我们实际上并没有一个能借此确知它符合质量的关卡。

<details><summary>Original English</summary>
>> Yeah.

 And

 and

 and

 it

 it's

 true

 that

 like





everybody

 in

 the

 end

 in

 some

 way,





whether

 they

 admit

 it

 or

 not,

 is

 testing





and

 prod.

 None

 of

 the

 tools

 that

 we

 have





are

 good

 enough

 to

 guarantee

 whatever

 it





is.

 Like

 even

 if

 you're

 doing

 an





incredible

 job

 with

 like

 an

 antithesis





Jeepson

 type

 tool

 and

 you're

 thinking

 up





all

 these

 great

 and

 interesting

 inputs,





there

 going

 to

 be

 some

 data

 which

 got





corrupted

 at

 some

 point

 in

 time

 which





exists

 in

 your

 production

 system

 which





you

 haven't

 randomly

 hit.

 your

 generator





simply

 can't

 generate

 whatever

 it

 might





be

 that

 is

 going

 to

 happen

 in

 production





and

 we

 do

 not

 know

 it's

 out

 there

 and

 we





are

 we

 are

 testing

 it

 and

 the

 idea

 that





somehow

 we

 have

 this

 this

 gate

 where





it's

 like

 oh

 if

 it's

 gone

 through

 this





it's

 quality

 it

 can

 go

 out

 is

 just

 it's





it's

 kind

 of

 a

 lie

 right

 like

 we

 have





hopefully

 increasing

 levels

 of

 assurance





as

 we

 go

 along

 but

 we

 don't

 actually





have

 a

 gate

 where

 we

 know

 it's

 quality
</details>

>> 所以，但你的意思是，这些手段能有所帮助，只是要清楚一定会有漏洞。比如……

<details><summary>Original English</summary>
>> so

 but

 you're

 you're

 saying

 like

 these





things

 can

 help.

 It's

 just

 like

 know





that

 there

 will

 be

 holes.

 Like
</details>

>> 是的，一定会存在漏洞。我们没有、我们没有……

<details><summary>Original English</summary>
>> yes,

 there

 going

 to

 be

 holes.

 We

 have

 We





have

 no
</details>

>> 东西会漏过去，而再加一道关卡……你的意思是并没有哪一道关卡是你加上之后就能表示“好了，这下彻底堵住了所有剩下的漏洞”。只要、只要我们还把目光放在这类关卡上——比如再多加一个，你知道的，就如同如果你再多加一个测试、两个测试或三个测试，当你硬编码那些值的时候，它们确实会让情况变好，当然，但它们不会、它们不能保证质量。

所以我去过的大多数地方，那些我认为属于我称之为运转低效的团队——也就是那些往往行动缓慢、交付产出不多，或者交付很频繁但经常需要紧急发布来修复问题的团队——他们是一群围着传统 CI/CD 搞某种把戏的人，至少现在是传统的了，也就是围绕 Pull Request 或者 Staging 环境构建，在发布到生产环境之前运行一些测试，他们通常是这样看待它的，觉得“哦，这里就是我设置这些质量关卡的地方”。

而那些行动迅速、充满信心，系统确实稳固可靠，而且他们不会整天收到告警的人，是那些从最开始坐下来就考虑质量的人。他们会想：“哦，嘿，我应该做验证”，比方说，如果我正在做一个分布式数据库，尤其是这个，我应该使用类似 TLA+ 的工具来确保我的共识算法切实可行等等一切，并确保我在其中没有 Bug；或者采用 Jepsen、Antithesis 这类工具，在把东西发布到生产环境之前，就把最原始的版本放进去检验：“那么，它的行为符合我的预期吗？”因为在早期修复问题真的很简单，当你……

<details><summary>Original English</summary>
>> things

 will

 sink

 through

 and

 adding





another

 gate.

 You're

 saying

 there's

 no





one

 gate

 that

 you

 could

 add

 that

 will

 be





like,

 "All

 right,

 this

 now

 seals

 off

 all





the

 remaining

 holes."

 As

 long

 as as

 long





as

 we're

 looking

 at

 these

 kind

 of

 gates





of

 like

 one

 more,

 you

 know,

 like

 the





same

 the

 same

 as

 if

 if

 you

 add

 one

 more





test

 or

 two

 more

 tests

 or

 three

 more





tests,

 when

 you

 like

 hardcode

 the





values,

 those

 will

 they'll

 make

 it





better,

 sure,

 but

 they

 will

 they

 will





not

 guarantee

 quality.

 So

 most

 of

 the





places

 I've

 been

 where

 there

 are

 teams





which

 I

 think

 are

 what

 I

 would

 call

 low





functioning

 which

 are

 ones

 where

 they





tend

 to

 move

 slowly,

 they

 don't

 deliver





stuff

 a

 lot

 or

 they

 deliver

 stuff





quickly

 but

 like

 they

 regularly

 have

 to





do

 emergency

 releases

 to

 fix

 stuff

 etc.





are

 people

 who

 think

 about

 like

 some





sort

 of

 thing

 around

 traditional

 CI/CD





stuff

 now

 at

 least

 traditional

 now





that's

 built

 around

 like

 pull

 requests





or

 or

 or

 a

 staging

 environment

 where





they

 run

 some

 tests

 before

 it

 goes

 out





to

 prod

 that's

 generally

 how

 they

 think





about

 it

 is

 like

 oh

 this

 is

 this

 is





where

 I

 have

 these

 quality

 gates

 and

 and





the

 people

 who

 move

 quickly

 and

 with





confidence

 and

 then

 it

 actually

 holds

 up





and

 they

 you

 know

 they're

 not

 getting





alerted

 all

 the

 time

 are

 people

 who





think

 about

 quality





from

 the

 very

 beginning

 of

 sitting

 down





and

 being

 like

 oh

 hey

 I

 should

 validate





for

 example

 uh

 if

 I'm

 doing

 a

 thing





which

 is

 a

 distributed

 database

 which

 is





particularly

 one

 I

 should

 be

 using





something

 like

 a

 TA

 plus

 to

 make

 sure





that

 my

 consensus

 algorithm

 actually





works

 etc

 and

 everything

 and

 to

 make





sure

 that

 I

 don't

 have

 bugs

 in

 that

 or





to

 take

 a

 Jeepson

 antithesis

 type

 tool





and

 put

 the

 very

 first

 version

 of

 your





stuff

 before

 you

 ever

 ship

 it

 to





production

 in

 there

 and

 So,

 does

 it





behave

 like

 I

 expect

 it

 to?

 Because

 it's





really

 easy

 to

 fix

 stuff

 early

 on

 when





you
</details>

<!-- chunk 8/11 -->

### 复杂系统的测试与不变式

首先创建这个东西。如果你像我见过的很多地方那样去做，那就会非常艰难——他们会说：“噢，这是我们的新系统。”然后他们直到很久之后才真正去对它做任何测试，没人知道它到底是不是正常工作，甚至也不一定知道“正常工作”究竟意味着什么。就像他们从一开始就没有问过自己：我怎么知道这东西在正常工作？

<details><summary>Original English</summary>
first

create

the

thing.

And

it's

really

hard

if

you

go

like

which

I've

seen

many

places

do

where

it's

like,

"Oh,

here's

our

new

system."

And

they

don't

really

do

any

testing

on

it

until

like

somewhere

way

down

the

line

and

nobody

has

any

idea

whether

it's

like

actually

working

or

not

or

even

necessarily

any

idea

to

know

what

does

working

really

mean.

like

they

haven't

asked

themselves

from

the

beginning

how

will

I

know

this

thing

is

working
</details>

>> 但我想反驳一下，比如你说只要它在正常工作你就可以写一个测试。我给你举个例子，说明有些情况下可能真的很难通过写测试来证明它正常工作。比如谷歌搜索，我输入“世界上最好的测试工具”，对吧？

<details><summary>Original English</summary>
>> but

uh

I

want

to

push

back

on

like

you

know

that

you

can

just

write

a

test

if

it's

working

I'll

give

you

an

example

where

it

might

be

really

hard

to

write

test

that

it's

working

a

Google

search

I

type

in

the

best

testing

tool

in

the

world

right
</details>

>> 是的。

<details><summary>Original English</summary>
>> y
</details>

>> 如果我问10个人，其中有5个人在厂商工作，他们都会说排在第一位的应该不一样，对吧？在厂商工作的人会说，我的厂商应该排在第一位，显然我就在这里工作，我们在测试领域做着了不起的事情。有些人会觉得，噢，他们可能会喜欢维基百科的那篇文章。有些人会说，我觉得应该出现这个。

<details><summary>Original English</summary>
>> and

if

I

ask

10

people

and

five

of

those

work

at

vendors

they

all

say

something

different

should

be

the

number

one

right

the

people

 who

work

at

vendors

they

will

say

my

vendor

should

be

Number

one,

obviously

I'm

working

here.

We're

doing

amazing

stuff

in

in

testing.

Some

people

will

think,

oh,

like

they'd

like

the

Wikipedia

article.

Some

people

will

say

like

I

think

this

this

should

happen
</details>

>> 当然，当我自己日复一日地运行相同的谷歌搜索时，那些结果会稍微发生一点变化，比如搜索结果会变，我们可以假设谷歌知道自己在做什么，而且这是正确的。但现在如果我想为一个复杂的系统哪怕只是写一个测试——当然我们知道它发生变化的原因，是因为谷歌会计算 PageRank，他们会获取大量的信号，他们也会考虑像实时性这样的因素，所以新闻会更新鲜。但现在我们有了这样一个非常复杂的系统，如果给我的任务很简单，比如：写一些测试，以便我们能够判断谷歌搜索的这一小部分在内部是否运行良好，比如在谷歌内部，那我就会感到很为难，因为我会觉得，好吧，哪怕你说“行，你可以使用任何形式化语言或者 TLA+”——

<details><summary>Original English</summary>
>> and

and

of

course

when

I

run

the

same

Google

search

day

after

day,

those

things

will

change

a

little

bit

like

the

the

results

will

change

and

we

can

assume

that

Google

is

is

knows

what

they're

doing

and

and

it's

correct.

But

now

if

I

wanted

to

just

even

write

a

test

for

for

a

complex

system

and

of

course

we

know

the

reason

it

changes

because

Google

calculates

the

page

rank

and

they

take

a

bunch

of

signals

and

they

also

take

things

like

real

time

so

like

news

will

be

fresher

but

now

we

have

this

really

complex

system

and

if

I'm

I

would

be

given

the

simple

task

of

like

well

write

some

tests

so

that

we

can

tell

if

this

small

segment

of

Google

search

works

fine

let's

say

inside

of

Google

I

would

now

struggle

because

I'm

like

well

you

know

if

we

went

like

all

right

you

can

use

any

any

formal

language

or

or

TLA

plus
</details>

>> 我会很难通过编码表达我究竟期望得到什么。尽管当你看着它的时候，你可以眯起眼睛看一看说“这看起来已经足够好了”，或者如果你有足够多的数据的话。

<details><summary>Original English</summary>
>> I

would

struggle

to

code

like

what

am

I

expecting

even

though

when

you

look

at

it

you

can

kind

of

squint

and

say

like

this

looks

good

enough

or

if

you

have

enough

data
</details>

>> 但是，有一些东西是我们能够测试的。例如，我们可以做一些不变式测试，比如：我在搜索框里放了一个东西并提交了，我期望能够拿回结果。

<details><summary>Original English</summary>
>> but

but

there

are

some

things

that

we

that

we

we

we

can

test

for

example

there's

some

invariance

we

can

do

which

like

for

example

I

put

a

thing

in

the

box

that

I

submitted

I

expect

to

get

results

back
</details>

>> 这是一个，这是一个不变式的例子。

<details><summary>Original English</summary>
>> that's

one

so

that's

one

one

invariant

for

example
</details>

>> 那里确实存在一个不变式。然后我们开始深入下去，你知道我做过一段时间的机器学习，实际上是在推荐系统方面，这就会涉及到那个有趣的事情：“噢，那排在第一位的应该是什么？”对吧？那是一件、那是一件与“它是否在工作”截然不同的事情。这非常不同。“它是否在工作”是指我往输入框里放了一个东西，我拿回了某种结果；“它是否相关”则是完全另一回事了，比如——

<details><summary>Original English</summary>
>> there

is

there

is

an

invariant

there

and

then

we

start

getting

into

things

and

you

know

I

did

the

machine

learning

stuff

for

a

while

which

was

actually

in

recommendation

systems

and

that

gets

that

gets

into

the

interesting

thing

of

you

like

oh

well

what

should

the

number

one

ranking

be

right

and

that

is

that

is

a

that

is

a

very

different

thing

than

is

it

working

right

like

that's

very

different

is

it

working

is

that

I

put

a

thing

into

the

box

and

I

got

something

back

the

the

is

it

relevant

is

an

entirely

different

thing

like
</details>

>> 噢，然后对于“它是否在工作”，我们现在可以问这样的问题：如果我一秒钟提交一千个请求，它还在工作吗？如果并发请求不断涌入，它在工作吗？如果在一个请求提交的过程中，我又提交了第二个或者直接跳离了页面等等。所以你现在说的是，我们可以把这个问题分解成不同的部分。

<details><summary>Original English</summary>
>> oh

and

then

with

the

is

it

working

we

can

now

ask

questions

like

if

if

if

I

submit

like

a

thousand

requests

in

a

second

like

is

it

still

working

if

if

if

we

have

concurrent

requests

coming

is

is

it

working?

If

in

the

middle

of

submitting

a

request,

I

submit

a

second

or

navigate

away

and

so

on.

So

like

so

now

you're

saying

we

can

decompose

this

into

different

parts

of

the

problem.
</details>

>> 而且我拿到的结果，是不是针对我实际查询的结果？

<details><summary>Original English</summary>
>> And

are

the

results

that

I'm

getting

results

that

are

for

my

actual

query
</details>

>> 在这种情况下，里面的内容可能并不重要，但我们可以建立测试，让每个查询都带上某种标记。我们确保那些结果确实返回了，并且服务器没有搞混而把你的结果给了我——好吧，也许对于搜索来说我不知道，我不知道有谁能知道发生了什么，但我相信大家都听说过那些事故，比如某某服务开始把别人的账户展示给用户等等。那是非常糟糕的情况。作为一个曾三次遭遇身份被盗的人，我真的希望没有人会意外把我的个人身份信息展示给别人。

<details><summary>Original English</summary>
>> where

where

what's

in

it

might

not

matter,

but

we

we

can

we

can

set

up

tests

so

that

each

query

gets

some

type

of

marker

that

goes

along

with

it.

And

we

make

sure

that

those

actually

came

back

and

that

the

server

didn't

get

confused

and

give

me

your

results,

which

okay,

maybe

for

search

I

don't

know.

I

don't

know

how

any

would

ever

know

what

happened,

but

I

think

everybody's

heard

about

the

incidents

where

uh

like,

you

know,

the

ex

service

started

showing,

you

know,

somebody

else's

account

to

people

and

whatnot.

That's

a

really

bad

one

there.

You

know,

as

somebody

who's

had

their

identity

stolen

three

times,

I

really

hope

that

that,

you

know,

nobody's

showing

my

PII

to

uh

somebody

else

accidentally.
</details>

### 供应链安全与防御措施

>> 那么，我想聊一聊行业里的一些有趣的收获，我知道你对这些内容充满热情。其中之一是供应链安全。

<details><summary>Original English</summary>
>> So,

I

I

want

to

talk

about

some

stuff

that

are

interesting

learnings

in

the

industry,

and

I

know

you're

passionate

about

them.

One

is

supply

chain

security.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 什么是供应链安全？我的意思是，我觉得我们听到的越来越多了，不幸的是，尤其是在开源领域，对吧？

<details><summary>Original English</summary>
>> What

what

is

supply

chain

security?

I

mean

I

I

think

we're

hear

hearing

it

a

lot

more

unfortunately

especially

in

open

source,

right?
</details>

>> 对。所以基本上供应链安全谈论的是，如果你有一个很受欢迎的东西，对吧？那么攻破那个东西最简单的方法——我们这里谈论的是软件、开源软件——

<details><summary>Original English</summary>
>> Yep.

So

basically

supply

chain

security

is

talking

about

if

if

you

have

something

which

is

popular,

right?

Then

the

easiest

way

to

compromise

that

thing.

We're

talking

software

open

source

software
</details>

>> 软件软件——

<details><summary>Original English</summary>
>> software

software
</details>

>> 就是找到它最薄弱的一环，然后去攻击那一环，对吧？这适用于软件，但也同样适用于硬件，比如说。

<details><summary>Original English</summary>
>> is

to

find

the

weakest

link

for

it

and

to

attack

that

right

which

and

this

this

applies

to

software

but

this

also

applies

to

hardware

for

example.
</details>

>> 噢。

<details><summary>Original English</summary>
>> Oh
</details>

>> 对，比如像 AMD 会做出各种安全保障，他们在里面有可信计算模块，Intel 也会做这种模块。但如果你真想攻击那些系统，你想要的是有个人在组装时能把恶意固件植入到那些机器上。你怎么知道、你怎么知道那确实是原本应该有的固件？而且我也有一点安全背景，这会被称为可信计算基。但人们现在谈论供应链安全时，通常谈论的都是软件方面的事情，比如多年前的 leftpad 是不是算供应链安全事件？有人、就像那是 npm 上的一个小模块，用来做某件事，然后有人往里面放了个加密货币挖矿程序之类的东西。

<details><summary>Original English</summary>
>> right

where

there

can

be

all

sorts

of

security

guarantees

that

like

um

AMD

makes

where

they

have

uh

trusted

uh

computing

modules

which

are

in

there

which

Intel

makes.

But

if

you

if

you

really

want

to

attack

those

systems,

what

you

want

to

have

is

somebody

who

when

they're

putting

this

together

can

put

a

malicious

firmware

onto

those

machines.

How

do

you

know

how

do

you

know

that

that

is

actually

like

the

firmware

that

is

supposed

to

be

and

you

know

I

I

have

I

have

a

security

background

as

well

and

this

this

gets

talked

about

as

like

the

trusting

computing

base.

But

people

usually

talk

about

this

um

when

they

talk

about

supply

chain

security

at

this

point

now

usually

about

software

and

things

like

wasn't

left

was

leftpad

a

supply

chain

security

one

years

ago

where

somebody

was

like

it

was

like

this

little

module

that

was

on

mpm

that

did

something

and

somebody

put

like

a

crypto

miner

or

something

in

it.
</details>

>> 它通常就像——我不太确定它有多微不足道，但这就像替换了一个被广泛使用的软件包。当时是一个非常简单的软件包在做一些微不足道的事情。

<details><summary>Original English</summary>
>> It

was

typically

like

I'm

not

sure

how

trivial

it

is

but

like

it's

replacing

a

package

that

is

widely

used.

There

was

some

very

simple

package

that

was

doing

some

trivial

stuff.
</details>

>> 但是比如，这种情况发生的一个极好途径是：如果你能去针对人们使用但不太去多想的东西，尤其比如在 CI/CD 系统中，并且你能让你的代码在 CI/CD 系统内部运行。你现在就可以访问在该 CI/CD 系统内运行的所有机密信息，这意味着你可以开始发布可能包含恶意软件的软件，谁知道还有什么等等。好，那是其一。但更甚的是，现在几乎现存的每一种编程语言基本上就像是说：给你，这里有个东西，我是从互联网上下载的，也许我检查了它的哈希值什么的，而它简直可以做任何事情。我下载了一个本该用来填充某些文本的东西，但实际上却被允许——我不知道——运行加密货币挖矿程序、建立网络连接等等各种事情。所有这些都是供应链攻击，它们会带来真正毁灭性的影响。

<details><summary>Original English</summary>
>> But

like

so

a

a

great

way

that

this

could

happen

for

example

if

you

can

go

after

something

which

people

use

and

they

don't

think

about

too

much

particularly

say

in

like

a

CI/CD

system

and

you

can

get

your

code

running

inside

of

the

CI/CD

system.

You

now

have

access

to

all

of

the

secrets

that

are

running

inside

that

CI/CD

system

which

means

that

you

can

start

publishing

software

which

might

have

malware

in

it.

who

knows

what

else

and

whatnot.

Great.

That's

that's

one.

But

even

more

so

like

almost

every

single

programming

language

that

exists

right

now.

Just

it's

basically

it's

basically

like

here

you

go.

There's

something

I

downloaded

it

off

the

internet.

Maybe

I

maybe

I

checked

its

hash

or

whatnot

and

it

can

do

literally

anything.

I

downloaded

a

thing

which

is

supposed

to

pad

out

some

text,

but

it's

actually

allowed

to

I

don't

know

run

a

crypto

miner,

make

make

network

connections,

etc.

and

everything

and

and

all

of

these

these

are

these

are

supply

chain

attacks

and

they

can

have

really

devastating

effects
</details>

>> 而且它们正在发生。我们在 npm 中看到了，我想我们、我想我们在 Python 社区也看到了。现在有一个非常好的问题：什么是有效的防御手段？因为你看，有几种幼稚的防御方式。一种是：“噢，我们就设一个冷静期吧。至少一周内不要获取任何新的软件包，我们指望如果有供应链攻击，它的规模会足够大以至于会被曝光并得到解决。”当然，坏处是如果有一个热修复补丁，确实存在一个安全漏洞，那我们现在就把自己暴露在外整整一周。但这算是一种幼稚的做法。另一种非常幼稚的做法是：“让我们去掉我们的依赖吧，直接把它完全搬到内部来做。”然后第三种是：“让我们 fork 它吧，弄这样一个分支，也许我们可以有一个安全团队来决定是否更新、合并或者保留在内部。”但这些做法都属于——所有这些都非常幼稚，并且——

<details><summary>Original English</summary>
>> and

they're

happening.

We

saw

it

in

mpm.

I

think

we

we're

I

think

we're

seeing

it

in

the

Python

community

as

well.

There's

a

quite

good

question

of

what

are

efficient

defenses

because

you

know

like

there's

a

couple

of

naive

defenses.

One

is

oh

let's

just

have

a

cool

down

period.

Let's

not

get

any

new

new

packages

for

at

least

a

week

and

we're

hoping

that

if

there's

a

supply

chain

attack

it

will

be

big

enough

that

it'll

be

published

and

it'll

be

resolved.

Of

course

the

downside

is

that

if

there's

a

hot

hot

fix,

there's

literally

a

security

vulnerability.

We're

now

leaving

ourselves

open

for

a

week.

But

that's

kind

of

one

naive.

The

other

very

naive

is

let's

get

rid

of

our

dependencies.

Let's

just

bring

it

in

a

house

or

let's

and

then

the

third

one

is

let's

fork

it.

Let's

have

this

this

fork

and

maybe

we

can

have

a

security

team

who

can

decide

to

like

update

or

merge

or

keep

it

in

house.

But

these

are

the

kind

of

like

very

all

of

them

are

very

naive

and
</details>

>> 我想知道你看到哪些方法有效且切合实际？因为看起来你是在用能够获取新软件包的低延迟（这些新包通常要么带有关键修复，要么带有极好的功能）去权衡对那个东西万一被投毒的恐惧——

<details><summary>Original English</summary>
>> and

I'm

I'm

wondering

what

are

you

seeing

work

and

being

practical

cuz

you

it

seems

you're

trading

off

kind

of

latency

of

being

able

to

get

fresh

packages

which

often

have

either

critical

fixes

or

really

good

functionality

for

being

afraid

that

what

if

that

thing

is

poisoned
</details>

>> 而且如果每个人都决定实行冷静期，那谁去发现问题呢？

<details><summary>Original English</summary>
>> and

and

and

if

everybody

decides

to

do

the

cool

down

period

who's

going

to

notice?
</details>

>> 确实如此。我们甚至还没谈到——

<details><summary>Original English</summary>
>> Exactly.

We

haven't

even

talked

about
</details>

<!-- chunk 9/11 -->

对吧？

<details><summary>Original English</summary>
that,

 right?
</details>

>> 对。呃，所以我觉得这当中的部分原因在于，几乎现存的每一种编程语言都没有很好的解决办法；而那些可能对此有较好解法的语言，呃，又根本没有人去用，因为它在很长一段时间里确实就不是大家关心的问题。几乎所有包管理以及几乎所有开源软件的运作方式，都可以追溯到当年 Perl 与 CPAN 的模式，那是一种极度开放和互信的东西，就像几乎所有早期的互联网事物一样——在那个时期，伪造发件人去发封邮件是轻而易举的事，诸如此类。那是一个默认每个人都是善意参与者的网络。

<details><summary>Original English</summary>
>> Yes.

 Um,

 so

 I

 think

 part

 of

 this

 is

 is





that

 there

 is

 no

 good

 answer

 for

 almost





every

 single

 programming

 language

 that





exists

 and

 any

 of

 the

 ones

 where

 they





might

 have

 a

 good

 uh

 answer

 to

 this

 um





are

 ones

 that

 nobody

 uses

 because

 it

 it





it

 really

 has

 not

 been

 a

 concern

 for

 a





long

 time.

 the

 way

 that

 pretty

 much





almost

 all

 package

 management

 and

 almost





all

 open

 source

 does

 dates

 back

 to

 like





the

 way

 that

 Pearl

 did

 with

 CPAN

 and





which

 was

 a

 which

 is

 an

 incredibly

 open





and

 trusting

 thing

 in

 the

 same

 way

 that





almost

 all

 early

 internet

 stuff

 was





where

 it's

 really

 easy

 to

 spoof

 somebody





sending

 an

 email

 all

 of

 this.

 It

 was

 it





was

 a

 network

 that

 just

 assumed





everybody

 was

 a

 good

 actor.
</details>

>> 没错。而且我猜在那个时候，准入门槛也更高。比如如果你是个恶意分子，你至少得学会写代码，或者你得雇个人；而现在雇人又稍微棘手了点，因为一旦他们知道我们在干什么，门槛就更高了。但这已经变了，对吧？连准入门槛都变了。

<details><summary>Original English</summary>
>> Yeah.

 And

 I

 guess

 back

 then

 there

 was

 a





higher

 bar

 for

 entry

 as

 well.

 Like

 if





you're

 a

 malicious

 actor,

 you

 at

 least





needed

 to

 learn

 to

 code

 or

 you

 need

 to





hire

 someone,

 which

 again

 is

 now

 a





little

 bit

 trickier

 because

 once

 they





know

 what

 we're

 doing,

 it's

 a

 higher





barrier

 to

 entry.

 But

 but

 that's





changed,

 right?

 Even

 the

 barrier

 to





entry

 has

 changed.
</details>

### 对象能力与语言层面的安全局限

>> 但即便在那个时候，情况也并非如此。和我读过同一所大学的一个高中劣迹生，就是个曾被美国政府逮捕过的人——因为他在十几岁的时候，向一大批他黑进去的政府计算机释放了一个蠕虫病毒。那件事后来甚至扩散得更广，成了当时的一起大事件。所以说，这种事那时候就依然在发生，只是规模更小，而且在当时那个特定的时间点，也并不是每个人都在依赖这些东西。而根本性的问题在于，几乎对于任何语言——不管是 JavaScript、Ruby、Rust，还是任何引入的依赖——在绝大多数情况下，你写的代码所拥有的实际能力，基本上与你碰巧从互联网上引入的代码一模一样；你的代码大概可以为所欲为，而那段第三方代码同样也可以为所欲为。那么，如果你要引入所有这些依赖，你到底该如何去审查这一切代码呢？这就又回到了那个问题上。归根结底，靠我们现有的这套东西，谁也解决不了这个问题。

人们可能会尝试做沙箱之类的事情，但归根结底，任何沙箱都是可以被逃逸的，这通常并没有那么难等等。这方面有一个完整的研究领域，有一位叫 Mark Miller 的人开发了一种叫做 E 的语言，里面有一些被称为“对象能力”（object capabilities）的东西，有很多非常有趣的研究。我们现在正在哥本哈根参加 Bug Bash，当天的第一场演讲是帝国理工学院的 Sophia 教授带来的，其实讲的就是他们所做的一些对象能力的研究等。不过对象能力的基本思想是：为了在系统内采取任何行动，你必须以某种方式被授予执行该行动的能力。因此，举例来说，除非你拥有相应的能力，否则系统不允许你打开网络连接；而初始程序——也就是你写的代码——必须把这种能力赋予其他组件。你知道，没有流行的语言这样做。虽然最初由 Silvin 编写、现在由我共同参与的 Pony 语言内置了对象能力，这是一种能够让人更加信任代码的手段。

但你还需要走得更远，因为如果你的编程语言允许某种类型的外部函数接口（FFI）——几乎所有的语言都支持，以便你可以利用通过 C ABI 调用的 C/C++ 代码或 Rust 代码等——如果你没有某种方式能彻底控制这一点，那么拥有对象能力也无济于事，因为有人可以直接通过 FFI 溜出去。所有这些都是需要解决的问题，而且仅靠在我们现有的系统内做些修修补补，是绝不可能解决这些问题的。

<details><summary>Original English</summary>
>> But

 e

 even

 back

 then

 it

 wasn't

 true.

 One





of

 the

 one

 of

 the

 people

 who

 was

 a

 high





school

 messup

 who

 I

 went

 to

 college

 with





was

 somebody

 who'

 been

 arrested

 by

 the





US

 government

 for

 unleashing

 when

 he

 was





a

 teenager

 a

 worm

 like

 across

 a

 whole





bunch

 of

 government

 computers

 that

 he'd





gotten

 into.

 and

 and

 and

 that

 actually





got

 further

 out

 and

 was

 one

 of

 the

 one





of

 the

 big

 incidents

 at

 at

 that

 time.

 So





like

 I

 mean

 it

 was

 still

 happening

 then





it

 was

 just

 it

 was

 at

 a

 smaller

 scale





and

 not

 everybody

 was

 depending

 on

 these





things

 at

 the

 this

 particular

 point

 in





time

 and

 and

 the

 fundamental

 thing

 is





that

 for

 any

 dependency

 pretty

 much

 for





any

 language

 like

 JavaScript

 or

 Ruby

 or





or

 or

 Rust

 or

 anything

 that

 that

 comes





in

 for

 the

 most

 part

 basically

 the

 code





that

 you

 wrote

 has

 the

 exact

 same





capabilities

 for

 what

 it

 can

 do

 as

 the





code

 that

 you

 happen

 to

 bring

 in

 from





the

 internet

 and

 your

 code

 can

 do





absolutely

 anything

 probably

 and

 that





other

 code

 could

 do

 absolutely

 anything





as

 well.

 And

 so

 how

 are

 you

 possibly





going

 to

 vet

 all

 of

 this

 code

 if

 you're





going

 to

 have

 all

 of

 these

 dependencies





which

 gets

 back

 to

 the

 to

 that

 problem





and

 in

 the

 end

 nobody

 is

 going

 to

 solve





this

 using

 the

 existing

 stuff

 we

 have.





people

 might

 try

 to

 do

 sandboxing

 or





whatnot,

 but

 that's

 just

 in

 the

 end

 like





every

 sandbox

 can

 be

 escaped

 from.

 It's





usually

 not

 that

 hard

 and

 whatnot.

 And





there's

 a

 whole

 area

 of

 uh

 study

 which





which

 is

 in

 these

 areas.

 Uh

 uh

 there's

 a





guy

 named

 Mark

 Miller

 who

 developed

 a





language

 called

 E

 which

 has

 some

 stuff





called

 object

 capabilities.

 Um

 where





there's

 a

 lot

 of

 interesting

 research.





We're

 we're

 here

 right

 now

 as

 as

 part

 of





bug

 bash

 in

 in

 Copenhagen

 and

 the

 first





talk

 of

 the

 day

 was

 uh

 from

 Sophia.





She's

 a

 professor

 at

 uh

 Imperial

 which





was

 actually

 talking

 about

 like

 some





object

 capability

 work

 etc

 they've

 done





but

 the

 basic

 idea

 of

 object

 capability





is

 that

 in

 order

 to

 take

 any

 action





within

 the

 system

 you

 have

 to

 be

 given





the

 capability

 in

 some

 fashion

 to

 do

 it.





So

 that

 the

 system

 would

 not

 allow

 you





for

 example

 to

 open

 uh

 a

 network





connection

 unless

 you

 have

 the





capability

 to

 do

 that

 and

 the





originating

 program

 your

 code

 that

 is





written

 uh

 has

 to

 give

 that

 capability





to

 other

 stuff

 and

 there

 there

 you

 know





there's

 no

 popular

 languages

 that

 do





this

 um

 because

 you

 know

 because

 pony

 is





written

 by

 like

 Silvin

 initially

 and





myself

 now

 the

 object

 capabilities

 are





built

 in

 but

 this

 is

 this

 is

 a

 this

 is





one

 means

 to

 like

 to

 be

 able

 to

 have

 it





be

 like

 I

 can

 trust

 this

 code

 more.

 But





but

 you

 you

 need

 to

 go

 you

 need

 to

 go





further

 than

 that

 because

 if

 your

 if





your

 programming

 language

 allows

 for





some

 type

 of

 foreign

 function

 interface





which

 almost

 all

 of

 them

 do

 so

 that

 you





can

 utilize

 like

 CC

 code

 or

 or

 rust

 code





or

 anything

 using

 a

 Cabi

 um

 if

 you

 don't





have

 some

 way

 to

 control

 that

 completely





then

 it

 doesn't

 matter

 if

 you

 have





object

 capabilities

 because

 somebody

 can





just

 go

 out

 the

 uh

 the

 FFI

 door

 and

 all





of

 these

 are

 things

 which

 need

 to

 be





addressed

 and

 there's

 no

 way

 that

 these





things

 will

 be

 addressed

 by

 just





incrementally

 doing

 stuff

 within

 the





system

 that

 we

 currently

 have.
</details>

>> 这么听来，软件安全变得愈发重要确实是有原因的，而且这是个复杂的话题。我们之前录过一期关于软件安全的播客，但感觉我们当时只是触及了皮毛，因为就像对待任何事情一样，对吧，这全在于细微差别，正是在这些细节处事情变得复杂起来。而且我相信存在着许许多多的策略，每个公司和团队都会决定采取什么策略：从极度简单的开始——当你只是一家小型初创公司，或者说一开始你纯粹是放飞自我凭运气，然后你开始采用的做法同样很简单，就是设置一个冷却期，指望并不是所有人都会同时冷却，这样就没事了；接着事情会变得精细得多，比如扫描依赖项、对它们进行评估、缩减不必要的依赖、扫描依赖链等等。你可以走得非常深，甚至可以一路走到设立一个安全团队的地步，由他们来审查或者尝试验证依赖，甚至可能去联系并了解是谁在构建它，如此等等。

<details><summary>Original English</summary>
>> Well,

 it

 sounds

 like

 there's

 a

 reason





that

 software

 security

 is

 getting

 more





important

 and

 it's

 a

 complex

 topic.

 I

 we





did

 a

 podcast

 episode

 on

 software





security,

 but

 it

 felt

 we

 were

 just





scratching

 the

 surface

 cuz

 as

 with





anything,

 right,

 it's

 it's

 a

 nuance.





It's

 it's

 a

 detail

 where

 it

 gets





complicated

 and

 and

 I'm

 sure

 there's

 so





many

 strategies.

 every

 every

 company

 and





team

 decides

 on

 what

 strategies

 to

 do





from

 the

 very

 simple

 when

 you're

 a

 small





startup

 and

 or

 well

 you're

 just

 yolo

 at





first

 and

 then

 and

 then

 you

 start

 to

 do





again

 a

 simple

 thing

 is

 just

 a

 cool

 down





hoping

 that

 not

 everyone

 cools

 down

 and





it'll

 be

 okay

 and

 then

 it

 gets

 a

 lot





more

 nuance

 scanning

 for

 dependencies





evaluating

 them

 reducing

 unnecessary





ones

 scanning

 dependency

 chains

 and

 so





on

 like

 you

 can

 go

 really

 deep

 you

 can





go

 to

 go

 all

 to

 point

 to

 have have

 a





security

 team

 who

 will

 vet

 them

 or

 try





to

 verify

 them

 or

 or

 even

 maybe

 have





contact

 with

 the

 know

 who's

 building

 it





and

 so

 on

 and

 so

 forth.
</details>

### 投机执行、侧信道攻击与机密计算

>> 而整件事中真正令人毛骨悚然的部分在于：我们即使把所有这些事情都做了——包括我提到的那些甚至更多——最终这一切也都不构成真正可靠的防御。因为多年前为了让我们的 CPU 运行得更快，我们做了一项权衡，那就是引入了投机执行（speculative execution）。投机执行之所以能起作用，是因为其逻辑就像是：“嘿，我有空闲的时钟周期，而程序可能会走这个分支，也可能会走那个分支，那我就同时把两个分支都执行了。”这为我们带来了在过去

<details><summary>Original English</summary>
>> And

 the

 the

 really

 horrifying

 part

 of





all

 of

 this

 is

 we

 could

 do

 all

 of

 these





all

 of

 these

 things,

 the

 ones

 I've





mentioned

 and

 even

 more

 and

 none

 of

 it





in

 the

 end

 would

 be

 a

 really

 good





defense

 because

 we

 made

 a

 we

 made

 a





tradeoff

 years

 ago

 in

 order

 to

 go

 faster





with

 our

 CPUs,

 which

 is

 we

 introduce





speculative

 execution.

 And

 speculative





execution

 works

 because

 it's

 like,

 hey,





I

 have

 extra

 cycles

 and

 this

 thing

 could





go

 down

 this

 branch

 or

 it

 could

 go

 down





this

 branch

 and

 I'm

 going

 to

 execute





both

 at

 the

 same

 time,

 which

 has

 given





us

 the

 vast

 majority

 of

 the

 speed

 ups





that

 we've

 gotten

 for

 like

 the

 last
</details>

>> 截至目前已经超过 20 年里所获得的大部分提速。

<details><summary>Original English</summary>
>> over

 20

 years

 at

 this

 point.
</details>

>> 嗯，大家可能见过这类东西，通常被称作侧信道攻击（side channel attacks）。这当中有各种各样的攻击形式，因为核心问题在于，那些投机执行的分支必须在内存中真实存在。因此，如果我作为攻击者水平足够高，你刚才执行了一个分支来处理我获得授权时的情况，以及另一个分支来处理我未获得授权时的情况；而事实证明，对于一个掌握了足够知识的人——要达到这种水平其实并不需要那么多知识——即使他们实际上并没有该系统的访问权限，也可以利用侧信道攻击去读取为“实际权限到底是什么”而在内存中生成的内容；或者更甚，他们可以找到并从内存中提取用于安全验证的密钥等诸多内容。

所以哪怕我们把其他所有环节都做好了，对吧？只要……就像我曾在微软研究院的机密计算组工作过，我们在微软构建了一款机密容器产品，这个产品现在依然在微软运作。关于我们的安全保证，当时我们总是说的一点是——虽然保证非常棒，但我们在末尾加上了一句——“除非受到侧信道攻击”；也就是说，我们无法保护你免受侧信道攻击。我们所做出的每一项保证，都会被侧信道所攻破。

那么，什么是机密计算呢？

<details><summary>Original English</summary>
>> Um,

 and

 and

 people

 have

 probably

 seen





stuff

 for

 like

 side

 channel

 attacks

 is





generally

 what

 they're

 called.

 And





there's

 a

 whole

 variety

 of

 these

 because





the

 thing

 is

 is

 that

 those

 speculative





branches

 have

 to

 actually

 exist

 in





memory.

 And

 so

 if

 I

 am

 good

 enough

 as

 an





attacker,

 I

 might

 you

 you

 executed

 a





branch

 for

 what

 happens

 if

 I'm





authorized

 and

 what

 happens

 if

 I'm

 not





authorized.

 And

 it

 turns

 out

 for

 a





sufficiently

 like

 knowledgeable

 person





which

 doesn't

 actually

 take

 that

 much





knowledge

 to

 get

 even

 if

 they

 don't





actually

 have

 the

 access

 to

 the

 system





can

 use

 a

 side

 channel

 attack

 to

 read





the

 memory

 that

 was

 created

 for

 this

 is





what

 the

 access

 actually

 is

 or

 even





better

 they

 can

 find

 like

 they

 can

 they





can

 get

 the

 the

 keys

 out

 of

 out

 of





memory

 that

 are

 used

 for

 security

 etc





and

 whatnot.

 So

 we

 could

 do

 everything





else,

 right?

 And

 as

 long

 as

 like

 I





worked

 at

 I

 worked

 at

 Microsoft

 research





on

 the

 confidential

 computing

 group

 and





we

 built

 uh

 a

 confidential

 container





offering

 which

 is

 which

 is

 still

 there





at

 Microsoft

 and

 the

 thing

 that

 we





always

 said

 about

 our

 security





guarantees

 which

 were

 great

 was

 we





tacked

 on

 at

 the

 tail

 end

 modulo

 side





channel

 attacks

 which

 is

 we

 can't





protect

 you

 against

 side

 channel





attacks.

 Every

 single

 guarantee

 that

 we





have

 is

 violated

 by

 side

 channel.

 And





what

 is

 confidential

 computing?
</details>

>> 机密计算这种计算模式，其终极目标基本上是让软件能够在运行环境的操作人员不被信任的环境中运行。

<details><summary>Original English</summary>
>> Confidential

 computing

 is

 computing





where

 basically

 the

 end

 goal

 is

 that

 the





software

 can

 be

 run

 in

 an

 environment





where

 the

 operators

 of

 the

 environment





are

 not

 trusted
</details>

>> 因为在……你在云端部署了某些东西，而你并不确定是谁在运行那个云。多年前曾发生过这么一件事：最后发现，呃，几名 Twitter 员工实际上在充当沙特阿拉伯政府的特工，通过私信等手段刺探沙特异见人士的活动。可能是这类事情；也可能是这种情况：你知道，噢，你或许信任微软或亚马逊，你认为他们不会窃取你的数据，但实际上你信任的是每一个拥有对应访问权限的人，这意味着你是在信任每一名员工都不会遭遇网络钓鱼，或者你在信任每一名员工都不会遇到可能导致受贿的财务问题等等。因此，机密计算就是一种尝试，试图让你不必去信任那些人；因为在安全领域，你信任的东西越多，

<details><summary>Original English</summary>
>> because

 in

 in





you

 play

 something

 on

 the

 cloud

 and





you're

 not

 sure

 who's

 running

 that





cloud.

 years

 ago,

 there

 was

 a

 thing

 that





that

 happened

 where

 it

 turned

 out

 uh





some

 Twitter

 employees

 were

 actually

 uh





working

 as

 agents

 for

 the

 Saudi

 Arabian





government

 and

 were

 spying

 on

 the





activities

 through

 DMs,

 etc.

 and

 stuff





that

 uh

 that

 Saudi

 dissident

 were

 doing.





it

 it's

 it

 could

 be

 this

 sort

 of

 thing





or

 it

 could

 be

 the

 thing

 where

 you

 know





oh

 you

 might

 trust

 Microsoft

 or

 Amazon





and

 you

 don't

 think

 they're

 going

 to





steal

 your

 data

 but

 actually

 you're





trusting

 everybody

 who

 has

 their

 access





which

 means

 that

 you

're

 trusting

 every





employee

 not

 to

 get

 fished

 or

 you're





entrusting

 every

 employee

 not

 to

 have

 a





money

 problem

 where

 they

 could

 be

 bribed





etc

 or

 whatnot

 and

 so

 confidential





computing

 is

 an

 attempt

 to

 make

 it

 so





that

 you

 don't

 have

 to

 trust

 those





people

 because

 in

 security

 the

 more





things

 you

 trust,

 the
</details>

<!-- chunk 10/11 -->

……你的系统就越不安全。是的。没错。所以，在机密计算那些方面，除了侧信道攻击之外，我们本可以为人们提供这些极好的保证，

<details><summary>Original English</summary>
less secure that your system is. Yeah. Right. And so, yeah, in the confidential computing stuff, we could provide these great guarantees for people except for side channel attacks,
</details>

>> 侧信道攻击可能会打破所有这些保证。在那个关头，唯一可能彻底封死它的方法，就是宣布要把推测执行从系统中彻底移除。我不……而且当第一批推测执行攻击开始出现时，比如他们打了 Linux 内核补丁去应对仅仅一个单独的案例，我不记得具体数字了，但大致就像是，我想他们做的第一个补丁导致了大约 50% 的性能下降，然后他们试图从中把性能找补回来。但接着又像这样：“噢不，这里又出现了一种攻击，这里又有一种，这里还有一种。”在某个节点上，我想人们大概就意识到：“好吧，我们只能玩打地鼠了，因为我们不想放弃从中能获得的性能。”我也非常关注安全，但在我自己写的开源代码里，我也绝对会利用推测执行来做事情。而我内心想要追求极致速度的那一面非常喜欢它，因为我可以直接这样想：“噢对，依赖这个机制工作并且知道平时通常会走这条路径的分支预测器，会把这个曾经开销极其巨大的分支变得开销极其低廉，这就意味着我现在可以去做那些原本很难跑快的事情，并且让它飞快运行。”我们大家其实都做了类似那样的交易：我们愿意追求快速，但是，噢，它在根本上就是不安全的。

<details><summary>Original English</summary>
>> which could which can violate all of the guarantees like the only the only way to possibly to fully lock it down at that point would be is to say that speculative execution is going to be removed from the system. I don't and when the first speculative execution attacks started coming out like they patched the Linux kernel to handle just one individual case and I don't remember the exact numbers but it was like oh like here's a I think the first one they did was like a 50% performance drop and they tried to like claw back performance from that and then but it was like oh and no here's another attack and here's another attack and here's another attack and at a certain point I think people just kind of realized well where we're just going to play whack-a-ole because we don't we don't want to give up on the um on the performance we can get from that. And I'm very concerned about security, but I also in open- source stuff I write, I absolutely do things where I'm taking advantage of speculative execution. And the side of me that wants to make stuff go fast loves it because I can just be like, "Oh yeah, the branch predictor, which works off of this and knows that normally it goes down this path, will make these this branch, which used to be really expensive, really cheap to do, and this means I can do things that would be really hard to make go fast now and make go fast." And we've all kind of made that like that deal of we're willing to go fast, but oh, it's just fundamentally insecure.
</details>

### 技术债与软件可塑性

我想问问你关于技术债的问题。大约十年前，你写过一段话，我念给你听听，我很好奇你的想法可能发生了怎样的转变。你当时写的是关于某家公司里的恐怖故事，或者你听说过的一些恐怖故事：

“但事情的关键在于：即使发生着这类恐怖故事，我们依然在赚钱。我们在增长，在维持自身运营。我们不断在为公司创造价值。是的，我们有很多技术债，但我们不断发现、发明各种办法去绕开偿还债务的必要。我们所采纳的‘债务’这一隐喻是具有误导性的。你并不总是非得去偿还自己欠下的债务。你可以绕过它，彻底避免去还清它。技术债只有在你必须偿还时才会造成伤害。”

<details><summary>Original English</summary>
I wanted to ask you about tech depth. Uh 10 years ago, you wrote something and I'll read it back to you and I I want to I'm curious how your thinking might have changed. You you wrote this about a horror story at a at a company or horror stories that you've heard.

Here's the thing, though. We were making money even though these kind of horror stories were happening. We were growing and supporting ourselves. We were continually creating value for the company. Yeah, we had a lot of technical debt, but we kept finding inventing ways to sidestep having to pay it. The debt metaphor we've adopted is misleading. You don't always have to pay off the debt you created. You can work around it and avoid ever having to pay it off. Technical debt only hurts if you have to pay it back.
</details>

>> 是的，我，我百分之百……

<details><summary>Original English</summary>
>> Yes, I I I 100%.
</details>

>> 依然坚持这个观点。

<details><summary>Original English</summary>
>> Still stand by it.
</details>

>> 依然……依然……

<details><summary>Original English</summary>
>> Still still
</details>

>> 我的意思是，我非常倾向于去构建具有可塑性的软件等等之类的东西。可塑性指的是……

<details><summary>Original English</summary>
>> I mean I am very much a person who wants to build malleable software etc and whatnot. Malleable as in
</details>

>> 可塑性指的是那些能够适应新情况的东西，因为构建软件时所处的环境，绝不会是一年、两年、三年之后所处的环境等等。因此，它必须是能够被改变的东西，而这并不一定意味着修改代码，而是指能够让它去契合它所需要身处的新环境，其中通常的应对方案之一往往就是直接把那东西扔掉。我写那段话特别针对的情况，我认为是由于当时在 MySQL 数据库的搭建方式以及分片极限上堆积了大量的债务，而且情况变得越来越棘手。而这最终通过砸钱买了一个分布式数据库给彻底绕过去了，那个分布式数据库对外展现的形式依然像是一个单一数据库。这里面的权衡，一是你们付给了他们相当一笔钱；二则是存在一些古怪的边界情况，就你在单节点 MySQL 系统上所期望获得的实际保证而言，你并不总能真正得到，但它们极其罕见，以至于就像是——这家公司又不是在用 Ada 之类的语言开发关键系统……

<details><summary>Original English</summary>
>> malleable as in stuff which will can adapt to like the new situation because the situation within which software was built is not going to be the situation that's going to be in a year in two years in 3 years etc. And so it needs to be stuff which can be made to change and that doesn't necessarily mean change the code but can be made to fit like the new environment that it needs to be in where one of the answers to that is often times just throw the thing away. That particular one I believe was motivated by one where um there was an awful lot of debt that was stacked around how the database was set up and a limit to sharding that could happen from my SQL and it getting harder and harder. And that ended up being completely sidestepped by throwing money at a uh a distributed uh a distributed database which still made it look like a single database. The trade-off there was one you pay we paid them a decent amount of money and two there were weird edge cases in terms of like the actual like guarantees that you would expect from like a single node my SQL system you wouldn't actually always get but they were so very rare that it's like this is not a company which is using ADA um
</details>

>> 等等。所以这种我偶尔会去排查追踪的极其罕见的问题，其实并没有那么重要。而且在很多情况下，你完全可以直接绕开它。你知道，情况也可能是：嘿，业务变了，那个系统不再被需要了。比如它运行了 3 年，现在不再被需要了，它消失了。你根本不需要去偿还你欠下的任何债务。

<details><summary>Original English</summary>
>> etc. So this incredibly rare thing which I would occasionally track like things down to like is is not that important. And you could just completely sidestep it in a lot of cases. You know, it could be, hey, the business has changed and that system is no longer needed. Like it ran for 3 years, it's not needed anymore. It's gone. You never had to pay off any debt that you you had.
</details>

所以，所以你的意思是，也许我们很多人对技术债的思考方式并不符合它的实际情况。实际情况往往是你创造了技术债，就像是你直接做了一堆拼凑代码，或者只是一些你知道如果在大型生产型企业里就行不通的做法；但也许你是一家初创公司或处于早期阶段，之后你可能根本就不需要偿还它，因为你要么直接重写新软件，要么干脆引入一项新技术直接让它彻底失效……

<details><summary>Original English</summary>
So, so you're you're you're saying that maybe a lot of us are not thinking about tech depth the way that actually happens, which is you often create it like you just do a bunch of hacks or or just like stuff that, you know, would not make sense, let's say, at a massive production company, but maybe you're a startup or early stage and then later on you might never have to pay it because you might just either write new software or just introduce a new piece of technology that just invalidates it
</details>

>> 要么就是没能找到产品与市场的契合点（PMF）……

<details><summary>Original English</summary>
>> or not find product market fit
</details>

>> 然后……

<details><summary>Original English</summary>
>> and
</details>

>> 跑光了启动资金。到了那时，这又有什么所谓呢？

<details><summary>Original English</summary>
>> run out of runway. And then why did it matter?
</details>

>> 是的。对。

<details><summary>Original English</summary>
>> Yeah. Yes.
</details>

>> 是的。我依然记得我在 Uber 工作时，我当时在一个乘车团队，或者说我们在构建乘车产品，那是 Uber 成熟的产品。它已经存在多年了，在赚大钱。而 Uber Eats 团队才刚刚起步，其中一名工程师进到我们的代码库里，提交了一次改动，因为他们需要共享的功能，他们需要用到那个平台的一部分。他们进来之后，删掉了一个在他们改动之后失败的测试，接着他们退出来并完成了更改。我们当时就像是：“你在干什么？你不能删测试啊。”我们陷入了僵局。他们当时就像是：“呃，你看，我只是需要把事情做完。”或者那甚至不是 Uber Eats，而是 JUMP 共享单车。在某个时刻，我开始理解到，实际上这些人，他们真的只考虑明天，因为他们不确定下周自己还会不会存在。果然，Uber 在 6 个月后把整个部门都卖掉了，我想它在 Uber 内部并没有找到产品与市场的契合点，它变成了一家独立的公司。但我当时的感觉就是：“噢，好吧。我想当你带着那种思维思考时，你实际上就会用那种‘能跑通就行，我们发布吧’的思路去删测试。来看看他们甚至不在乎它是否对 100% 的客户都有效，他们只在乎它在那一刻能否基本满足他们的目的。”

<details><summary>Original English</summary>
>> Yeah. I I still remember when I worked at Uber, I was on a rides team or like our we were building a rides product which was Uber's mature product. It's been around for years. It was making serious money and the Uber Eats team was just starting out and one of the engineers came into our codebase and like committed a change cuz they needed the shared functionality. they needed to use some of that platform and they came in uh they deleted a test that was failing after they made the change and they went out and they made the change and we're like what are you doing like you cannot delete the test and we got into the standoff they were like well look I just need to just need to get it done or it wasn't even neat it was it was jump jump bikes and at some point I started to understand that actually like these people like they they really are thinking only about tomorrow cuz they're not sure if they're going to be around the week after and sure enough Uber sold up that whole division 6 months later and it didn't find I guess product market fit inside of Uber. It became its own company. But I was like, "Oh, okay. I guess when you're thinking like that, you actually use one of the lead test like you're like works. Let's roll it out. Let's see if they didn't even care if it worked for 100% of customers. They cared if it kind of worked for their purposes for at that point."
</details>

>> 是的。而且，你知道，有时候你确实是要付出代价的，对吧？确实如此。而且通常你付出代价是因为你成功了。然而，你也可能……我的意思是，也可能会发生这种情况：人们既不关注债务，也没有带着这种思考方式去想——做这件特定事情的最具可塑性的方式是什么，从而让我能迅速把它做出来以便去验证事情？因为“我就在这里胡乱拼凑一番把东西塞进去”，与“我构想出一个方案，在非全功能的情况下尽可能快地实现它”之间，有着非常大的区别。它也许只适用于某个极微小的细分场景，而且有各种各样它无法处理的边缘用例，但它对我来说很容易移除；如果我们在接下来的 3 个月里基于它再构建五个功能，它也不会拖慢我们的步伐，因为归根结底，比如我们是一家初创公司，只是在试图尽快弄清楚我们到底在做什么。是的，你非常有可能陷入这样一种处境：不幸的是，甚至在找到部分产品与市场的契合点之前，你就可能因为欠债过多而走投无路。但是，存在于大量讨论中的那种观点——即“噢不，每一丁点债务都是有害的，它总是必须被还清”——我的意思是，这根本不符合实际情况。

<details><summary>Original English</summary>
>> Yeah. And and you know, sometimes you really do pay the cost, right? You do. And usually you're paying the cost because you were successful. However, you could also I mean it could also happen that people are not paying attention to they're not paying attention to debt, but they're also not thinking about it in a way of of what is the most malleable way to do this particular thing which I can so that I can do it quickly in order to validate things because it's very different between I'm just going to hack this thing in here versus a I'm going to come up with a thing where I'm going to do it quickly as possible when it's not the full thing. It fits some tiny little sliver perhaps and there's all sorts of edge cases that it won't handle, but it's easy for me to remove and if we build five more things on it like in the next 3 months, it's not going to slow us down because ultimately we are we are a startup for example that is just trying to figure out what we're doing as quickly as possible. And yes, you can very much get yourself into a position where unfortunately before you even found part of market fit, you might have debted yourself into a corner. But the idea that that exists in a lot of stuff where it's like, oh no, every single bit of debt is bad. It always has to be paid off is just I mean it it's not borne out in reality.
</details>

### 以慢为快

>> 所以，无论是我们现在所讨论的，还是早先谈论你的职业生涯以及你如何构建软件，其中的一个主题就是你是多么喜欢追求速度。

<details><summary>Original English</summary>
>> So one one theme of both what we're talking about, but as we're talking earlier about your career and how you built software is how you love to go fast.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 而且你已经学会了要跑得快，有时你需要慢下来。关于这一点你也写过文章，所以我就在此引用你的原话：“以慢为快。这意味着在任何人触碰代码之前，先撰写一份规划文档并就我们要做的事情达成一致。这意味着在开始构建之前，先清楚我们将如何测试这个东西。这意味着花上几个小时或几天时间，针对我们尚不理解的部分做探索性的废弃原型。这意味着当……”

<details><summary>Original English</summary>
>> and that you've learned to go fast. Sometimes you need to go slow. And you you write about this as well, so I'll quote you on this. Go slow to go fast. It means writing a planning document and coming to agreement on what we're doing before anyone touches code. It means knowing how we'll test the thing before we start building it. It means taking a few hours or a couple of days to throw away spike on the parts we don't understand yet. It means stopping when
</details>

<!-- chunk 11/11 -->

生产环境在凌晨两点出问题。其中有些理念太反直觉了，对吧？

<details><summary>Original English</summary>production is on fire at 2 a.m. Some of these are are so counterintuitive, right?</details>

>> 对我来说倒不是。

<details><summary>Original English</summary>>> Not to me.</details>

>> 对你不是。

<details><summary>Original English</summary>>> Not to you.</details>

>> 对我不是。我是说，我想它们在……在我职业生涯早期的时候，绝对很可能也是反直觉的。那时候就纯粹是：“哦，不行，得把那件事做完。”但后来就像是……最终你会意识到，其实每周工作80个小时并不能让我做得更快。那只会导致我犯更多错误，因为我整天都处于疲惫状态，而且我现在总得把时间花在排查bug上，而不是开发新功能上。其实当我累了的时候，我就应该离开电脑。这就是所谓的“以慢求快”。我要确保自己休息好，确保自己健康，确保我的大脑——这是这一切的关键部分——实际上在正常运转。

在我职业生涯中见过的最浪费时间的事情之一，就是大家在交谈以及使用词汇时，没有花时间去确保彼此表达的实际上是同一个意思。

<details><summary>Original English</summary>>> Not to me. I mean, I think they absolutely probably were counterintuitive like earlier in my career and everything where it was just like, "Oh, no. Need to get that thing done." But it it's kind of like the thing where where eventually you realize actually working 80 hours every week is not resulting in me going faster. It's just resulting in me making more mistakes because I'm tired all the time and I'm constantly now spending my time tracking down bugs instead of working on new functionality. That really when I get tired I should just step away from the computer. That is a I'm going to go slow to go fast. I'm going to make sure that I'm rested, that I'm healthy, that my my brain, which is a key part of all of this, is actually functioning correctly. One of the worst time wasters that I' I've seen in my career is people not spending time to make sure that when they're talking to each other and using words that they actually mean the same thing.</details>

>> 然后差不多三周后，东西在另一端做出来了，有人看了一眼就说——

<details><summary>Original English</summary>>> And like 3 weeks later the thing pops out the other end and somebody looks at it and goes</details>

>> 那根本不是我想要的。就像是……这就是为什么敏捷开发中像Sprint这样的理念本应融入这一点：我们不会隔很长时间都不去审视它，以确保我们在前进方向上达成一致。如果你打算构建一个庞大而复杂的东西，你应该花上几天时间，所有人——开发的最初阶段并不是编写代码，而仅仅是写下这东西将如何工作、它应该实现什么，并确保大家在所有这些事情上确实达成一致，因为在那个阶段调整东西是非常容易的。你还没有在编写代码等方面投入大量时间，你所做的只是确保：我们所有人讨论的到底是不是同一件事。

多年前，互联网上分布式系统社区的人们曾有过一场非常精彩的争论，双方各执一词、互不相让。他们之所以争得不可开交，是因为他们在讨论消息传递语境下的“恰好一次”（exactly once）究竟意味着什么。

<details><summary>Original English</summary>>> that's not what I wanted. Like this is this is why like with agile that this idea of sprints was supposed to bake in this we do not go very long without looking at it to make sure that we are in agreement for the direction that we're going in. If you're going to build a big complicated thing, it behooves you to spend a few days where everybody just the first part of development is not writing code, but it's just writing down how the thing is going to work, what it's supposed to do, and making sure everybody actually agrees on all of these things because it's very easy to change things there. You haven't invested a lot of time in coding the thing, etc. you're just working to make sure are we all actually talking about the same thing. Years ago, there was a a wonderful argument from people on the internet in the distributed systems community where the two sides were just going back and forth at each other and they were going back and forth at each other because they were talking about what exactly once means in terms of like delivering messages.</details>

>> 恰好一次投递。是的。

<details><summary>Original English</summary>>> Exactly once delivery. Yeah.</details>

>> 是的。其中一组人指的是“恰好一次处理”，他们谈论的是幂等性，以及某件事实际上只产生一次影响；而另一组人谈论的则是消息从字面意义上只到达计算机一次。这边的人就说：“你们在撒谎，你们不可能做到恰好一次……”他们就这么一直互相嚷嚷，耗费了所有这些时间，因为根本没有人真正愿意坐下来明确说：“我说的‘恰好一次’是指这个意思。”

类似的情况随时都可能发生。你派某个人去干活，就像是：“哦，嘿，我在卡片上记了这么点东西”——我猜大家现在可能用Linear，大概也还在用Jira，不管现在用什么吧——“我记下了这么点东西，你去把这事领了，把它做出来。”然后这个人花了不知道是一小时、一天还是五天时间把这东西做出来了，结果却是：“哦，对，不，那不是我……那不是我们所期望的。”你跑得很快，但一无所获，对吧？

所以，你应该花时间为不管那是什么事情打好基础。确保每个人的方向一致。而且作为其中的一部分，比方说，如果你以后想跑得快，你在设计一个系统时，从一开始就应该考虑日后如何知道它确实在正常运行。因为在构建系统时，有些做法会让你几乎不可能知道它是否在正常运转；或者你也可以这样构建：让你很容易知道它是否正常工作，这可以包括我谈到过的一些静态检查相关的内容。甚至仅仅是做到对系统具备良好的可观测性，对吧？

<details><summary>Original English</summary>>> Yes. and and like one group of people meant exactly once processing and they were talking about Iden potence and a thing only actually having an impact one time and the other group was talking about the message literally arriving at a computer only once and these people over here are like you're liars you can't do exactly once like and the and they just spent all of this time yelling at each other because nobody actually bothered to sit down and go this is what I mean by exactly once and the same sort of thing like can come up like all the time you send somebody off it's like oh hey I jotted down this little thing on a card I guess people use like linear they probably still use Jira whatever it is now and I jotted down this little thing you go pick up the thing you do it and then like this person spent I don't know an hour a day 5 days building this thing and it's like oh yeah no I that's not what I that's not what we were expecting and you went fast and you got nowhere, right? Like you spend the time to establish the foundation for whatever that is. Make sure everybody's pointed in the same direction. And as part of it, like for example, if you want to go fast later on, you should be thinking when you're designing a thing for how you're going to know that it's actually working right from the beginning. Because there are ways you can build a system where it's almost impossible to know whether it's working. Or you can build it where it's easy to know that it's working, which can include some of the stuff I've talked about from static stuff. But even just making it so that you have good observability into the system, right?</details>

>> 就像我们要构建一个准备投入到生产环境中的系统。我们将如何知道它是否宕机了？我们如何……我们如何知道它是否出现了灰色故障（gray failures）——一大批用户的体验极其糟糕，但它在负载均衡器或其他地方依然处于运行状态且能正常ping通？

就只是坐下来思考这些问题，确保这些事情在后续容易处理，且以后不会拖你的后腿。这样你前期花一点时间，让所有人步调一致，弄清楚你要做什么，然后在那之后你就可以真正飞速前进了。

太棒了。Sean，这期聊得太棒了。感谢参与这次对话。

<details><summary>Original English</summary>>> Like we're building a system that we're going to put out there in production. How are we going to know whether it's down? How are we how are we going to know whether it's got gray failures where a whole bunch of people are getting a really bad experience, but it's still up and pinging in the load balancer or whatnot? just sitting down and thinking about these things and making sure that they're things that will be easy to do and are not going to drag you down later on so that you spend a little bit of time up front, get everybody on the same page, figure out what you're going to do, and then you can just go really fast after that. Awesome. Well, well, Sean, this was awesome. Thanks for having this conversation.</details>

>> 是的，这次聊得非常愉快。

<details><summary>Original English</summary>>> Yes, this this was wonderful.</details>