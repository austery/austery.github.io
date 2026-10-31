---
author: The Pragmatic Engineer
date: '2026-04-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3jjRNVfm3V4
speaker: The Pragmatic Engineer
tags:
  - microservices
  - scaling
  - startup-growth
  - career-development
  - ai-engineering
  - leadership
title: Uber首任CTO Thuan Pham：从越南难民到科技巨头，Uber高速增长背后的技术挑战与领导力
summary: 本期访谈深入探讨了Uber首任CTO Thuan Pham的非凡职业生涯。他从越南战争难民的艰苦童年起步，讲述了如何进入科技行业，并在惠普实验室、Silicon Graphics、NetGravity和VMware等公司积累经验。访谈重点关注Thuan在Uber早期面临的巨大挑战，包括应对系统崩溃、在五个月内在中国上线、以及主导Project Helix项目。他分享了Uber如何通过微服务架构和大量内部工具应对超高速增长，以及他关于人才培养、团队文化和领导力的深刻见解。最后，Thuan还讨论了AI对软件工程的颠覆性影响，以及他目前在Fair和Nubank的工作。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Thuan Pham
  - Travis Kalanick
  - Bill Gurley
  - Yuki
  - Max
companies_orgs:
  - Uber
  - VMware
  - HP Labs
  - Silicon Graphics
  - NetGravity
  - Fair
  - Nubank
  - Coupang
products_models:
  - Project Helix
  - Sonar Cube
  - ESX
  - Virtual Center
  - NodeJS
  - PostgreSQL
  - MySQL
  - M3
  - Jager
  - Schemaless
  - T-channel
  - Ringpop
  - g-spatial
  - Clay
  - Darwin
  - ARC
media_books: []
status: evergreen
---
### 引言：Uber的挑战与Thuan Pham的加入

**主持人**: **Uber**大概有5000个微服务。我们谁都不想经历那种极端情况。但在很多时候，当你面临巨大压力，除了应对不断涌来的规模挑战别无选择时，你就必须去做了。**Travis**告诉你，你有两个月时间在中国上线。那确实是我们做过的最疯狂的事情之一，但也是最了不起的事情之一，我现在来解释一下原因。

<details>
<summary>Original English</summary>

**主持人**: **Uber** had about 5,000 microservices. None of us wanted to go through that extreme. But lots of time when you are under a lot of pressure and no time to react other than to survive that scale that keep on coming at you. **Travis** told you you have 2 months to launch in China. That was one of the craziest thing we've ever done, but it's also one of the most amazing thing we've ever done and now explain why.

</details>

**主持人**: 那么，我们来谈谈**Uber**是如何以及为何构建了如此多的内部工具。我不能说所有这些工具都是绝对必要的，但所有重要的工具都是绝对必要的。我记得早期我们面临一个非常痛苦的例子，那就是**Thuan Pham**在2013年加入**Uber**，担任公司首任首席运营官时。当时公司有40名工程师，每天处理3万次乘车请求，系统每周崩溃多次。他有5个月的时间来解决这个问题，否则**Uber**的调度系统就会彻底崩溃，无路可走。7年后，他离开时已是CTO，领导着有史以来最复杂的工程组织之一。

在今天的对话中，我们讨论了**Thuan**与**Travis Kalanick**长达两周、超过30小时的CTO职位面试，以及如何在混乱中实现规模化、在系统崩溃前重写调度系统、在五个月内在中国上线，以及内部称为**Project Helix**的全面重写项目。为什么**Uber**最终拥有数千个微服务和数百个内部工具，因为当时现有的解决方案无法处理**Uber**的规模，还有更多原因。如果你曾好奇一家公司在系统无法承受的超高速增长中，内部是如何运作的，以及如何控制局面，那么本期节目就是为你准备的。顺便提一下，我很幸运能在**Thuan**担任CTO期间在**Uber**工作。**Thuan**是真正的实干家。

本期节目由**Statsig**赞助，它是一个集功能标志、分析、实验等功能于一体的统一平台。请查看节目说明，了解更多关于他们以及我们其他赞助商**Sonar**和**Work OS**的信息。**Thuan**，很高兴能在这里见到你本人。

<details>
<summary>Original English</summary>

**主持人**: So let's talk about how and why **Uber** built so much internal tools. I can't claim that every single one of those thing were absolutely necessary but all the important one were absolutely necessary. So I remember a very painful example of that we had to face early on was when **Tuan Pam** joined **Uber** as the company's first CO in 2013. The company had 40 engineers did 30,000 rides per day and the system crashed multiple times per week. He had 5 months before **Uber's** dispatch system would hit a brick wall with no way out. 7 years later, he left the CTO of one of the most complex engineering organizations ever built.

In today's conversation, we discuss **Tuan's** interview with **Travis Kellik** for the CTO role, which lasted 30 hours, spread over 2 weeks, scaling through chaos, rewriting dispatch before it collapsed, launching China in 5 months, and the full appreite known internally as **Project Helix**. Why **Uber** ended up with thousands of microservices and hundreds of internal tools because existing solutions could not handle **Uber** scale at the time, and many more. If you've ever wondered what it's like inside the room when a company is growing faster than it systems can handle and what are ways to get things under control, this episode is for you. As a side note, I've been lucky enough to work at **Uber** while **Tuan** was a CTO. And **Tuan** is the real deal.

This episode is presented by **Statsig**, the unified platform for flags, analytics, experiments, and more. Check out the show notes to learn more about them and our other season sponsors, **Sonar** and **Work OS**. **Tuan**, it is so good to have you here in person.

</details>

**Thuan Pham**: 很高兴。这么多年后能再次与你联系，真是太好了。我们曾在**Uber**共事近四年。可能在我入职的第一个月，我就在一些非常有趣又充满压力的**Project Helix**——**Uber**应用重写项目——中遇到了你，那真是一个疯狂的项目。

<details>
<summary>Original English</summary>

**Thuan Pham**: It's my pleasure. It's so good to connect with you again after all these years. And it's so good to reconnect. We we worked together for almost four years at at **Uber**. Probably my first month I already met you in like some really like fun slashstressful circumstances during **Helix** the **Uber** app rewrite which was a crazy project.

</details>

### Thuan Pham的早年经历与科技之路

**主持人**: 那么，在我们深入探讨这些之前，你是如何开始接触科技，甚至是开始你的人生旅程的？你有一个相当艰难的开端。

<details>
<summary>Original English</summary>

**主持人**: Well, before we get into any of that, how did you get started not just in tech but but in life? You had a pretty rough start.

</details>

**Thuan Pham**: 是的，我出生在越南，可以说是越南战争的孩子。1975年，我来自越南南方，我的父亲与南方军队有关联。当国家统一时，南方战败，北方获胜，随之而来的是相当多的影响。与南方政权有关联的人在成长过程中没有太多机会，教育机会等都受到了限制。当时的情况就是这样，现在不一定如此。

我的母亲做了一个非常大胆的决定，她不希望她的两个儿子在没有机会的环境中长大。所以我们不得不逃离这个国家。当时有一股大规模的移民潮，被称为“船民”，人们乘坐破旧的渔船或任何能找到的船只，在深夜逃离国家。当时人们并不知道，也没人去想，生存的机会不到50%。大约有200万人离开，大约100万人成功渡海，因为这些船只根本不适合航海。我们横渡了海洋，是的，我们是幸运的一半。但如果人们想得太多，他们可能就不会去做。每个人都觉得，我们需要逃离，我们需要给自己一个更好生活的机会，所以我们做了。

我们离开了越南。我们尝试了很多次，耗尽了我父母所有的积蓄，因为那是个骗局。人们会说，现在付一半，以后付一半，然后船就再也没出现。最终，在第四次尝试时，我们成功了。我们很幸运，有一个非常好的船长，他带领我们穿越了风暴，我们甚至从泰国海盗手中幸存下来。我当时大概11、12岁。我们穿越了南海，经历了三天四夜的航程，到达马来西亚。我们以为一切都结束了，但一周后，我们又被拖回海上，几天后被扔到了印度尼西亚。那里的政府接纳了我们，把我们安置在一个荒岛上，我们在那里建立了一个难民营。

然后我们等待处理。我们接受了不同国家的面试，美国给了我们难民安置，因为我们与美国支持的旧政权有关联。所以，我们非常非常感谢能来到这个充满机会的国度。我们当时一句英语都不会，身无分文。我们由一个教堂资助，我们得到的第一批衣服来自教堂的捐赠衣柜。所以，我们不得不从零开始建设。这就是我的成长经历，也是我来到这里的方式。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, I I I grew up in I was born in Vietnam and I was a child I would say of the Vietnam War. So in 1975 when the south of I was from the south of Vietnam, my father was tied to the military of the south of the south and when the when the country was unified, right? The the south has lost and north is one and there were a fair amount of repercussion, right? People who are associated with the southern regime would not have much of an opportunity growing up. the education opportunity, all these other that was again the the the way it was at the time. That's not necessarily true right now. But that was and my mother then made a very bold decision that she wouldn't want her two son growing up with no opportunity. And so we had to flee the country. And at the time there was a massive wave of exodus called the boat people where people just get onto rinky boat fishing boat or whatever thing they can get their their their place in and escape the country in the middle of the night. People did not know at the time and nobody thought about it that but the chance of survival was about less than 50%. that about two million people left, about million people survived the crossing because this these boats are not sea worthy and we crossed the ocean and yeah, but we were the lucky we were lucky half really. But no one thought about if people think too much about it, they probably wouldn't do it. But everyone just like well we need to escape we need to you know give ourselves a shot of a better life and so we did. So we we left Vietnam. It took many try and took it depleted the entire you know saving of my parent because it was a scam. People were say you know pay up half now half later and then the boat never shows up and finally on the fourth try we actually made it and then we were lucky that we have a really good captain who actually navigate through storms and and all that and we survived even pirate from from Thai. I was around I think 11 12 somewhere and so we crossed that and we survived three three day four nights of the crossing of the South China Sea to Malaysia then we went into Malaysia we thought we were done a week later we got tow back out and dump it in Indonesia a few days later and that's where the government there accepted us in and put it on a deserted island at the time and we formed a refugee camp there. So, and then we were waiting to be processed. We got interviewed by all the different countries and the the US gave us a refugee settlement because we were tied to the old regime that were supported by the Americans. So, we were very very thankful to to get here the land of opportunity and we didn't know any English. We didn't have any penny to our name. We were sponsored by a church. the first set of clothing we got was from the donation closet at the church. And so and so but we had to build from the ground up and so that that was how I grew up and that's how I got here.

</details>

**主持人**: 从这样一个不仅非传统，而且极其艰难的开端，你是如何最终对计算机和科技产生兴趣的？

<details>
<summary>Original English</summary>

**主持人**: And then from this like absolutely not just unconventional but just extremely hard start. How did you eventually get your interest into computers into tech?

</details>

**Thuan Pham**: 就像生活中大多数事情一样，都是偶然或运气。我在数学和科学方面相当不错，就像大多数亚洲孩子一样，我们从小就学习这些。当我们来到这里后，我在高中时有一个朋友，他收到了他父亲送的一份礼物——一台**IBM PC**。那是最早的电脑之一，带着两个软盘驱动器。

<details>
<summary>Original English</summary>

**Thuan Pham**: Just like most in life is by happen or luck. I I was pretty good in math and science as most kids in in Asia. We were growing up. We learned that. And when we got here I had a friend in high school who had received a gift from his dad an **IBM PC**. That was when one of the very first one the one with like two floppy disc.

</details>

**主持人**: 这是在80年代还是70年代？

<details>
<summary>Original English</summary>

**主持人**: Was this in ' 80s or '7s?

</details>

**Thuan Pham**: 这是在80年代，1982年。是的，我读高一时。放学后我就会去他家玩，他有新玩具，所以我们就会写一些**BASIC**小程序，玩游戏等等。我们学会了使用文字处理软件、**Lotus**和**WordStar**等等，我开始用**BASIC**编程，然后我发现这对我来说非常自然，我能以算法的方式思考。

还有一件奇怪的事情，我有时会告诉别人，我通常是个拖延症患者，我不喜欢做两次同样的事情，所以计算机编程对我来说是完美的，对吧？你解决问题一次，那是创造性的部分。之后，我就感到无聊了，我得去做下一个问题。所以，编写程序对我来说是完美的契合。

<details>
<summary>Original English</summary>

**Thuan Pham**: This was in the 80. This was in 1982. Yeah. So freshman year. So after school I would hang out at his place and he's got a new toy and so we were you know writing little basic program and playing game and all that stuff and we learned how to use word processors and **lotus** and **word stars** and all that and I started coding in basics and then I just realized that oh it come very natural to me I can think very algorithmically and then there's another weird thing I I sometimes tell people I am generally a procrastinator I don't like to do the same thing twice so computer programming is perfect for me, right? You solve the problem once that's a creative part. After that, I get bored. I got to do the next problem. And so, writing program was like the perfect fit for me.

</details>

**主持人**: 你不会复制你的代码。

<details>
<summary>Original English</summary>

**主持人**: You do not duplicate your code.

</details>

**Thuan Pham**: 是的，我不喜欢复制代码。我不喜欢做两次同样的事情。所以，当你编写它，它执行的速度比你手动操作快得多。那真是太棒了。我就是自学成才的。然后我放学后在一个政府机构做志愿者，为他们编写代码。我去了那里，基本上把**Lotus**和**DBA3**与所有脚本语言结合起来，自动化了整个财务会计流程，减少了工作量。当时，两个会计师每季度要花大约三周时间来核对所有事情。我用一个按钮就完成了所有这些工作，整个批处理运行大约需要三个小时。所以他们在我高中毕业时非常高兴。我想他们给我写了一封非常好的推荐信。

加上其他事情，以及好成绩等等，我被**MIT**录取了。我到了那里，才真正学习了计算机科学，比如计算机科学的基础知识。在那之前，我只是一个会写程序的孩子。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. I don't like duplicate the code. I don't like to do the same thing twice. And so, yeah, when you write it and then it execute way faster than you can do it by hand. So, that was really wonderful. I just taught myself that. And then I volunteer at a government agency to write code for them after school. And so I did that and I went in there and I basically stitched together **Lotus** **DBA3** with all the scripting languages and automate the entire financial accounting and reduce the the the workload. At the time the two accountant had to spend about 3 weeks or so every quarter reconciling everything. I did all that stuff with a purchase button and took about three hour for the whole batch to run. And so they were so happy when I graduated high school. I think they they wrote me a really good recommendation letter. And with other things that were going on and the good grades and everything else, I I got accepted **MIT** and then I got there and I really learned computer science like the fundamental of computer science. Back then I was just like a kid who just, you know, write programs. So,

</details>

**主持人**: 那么在**MIT**期间或之后，你的第一份专业工作是什么？你在哪里获得了报酬，并全职从事科技工作？

<details>
<summary>Original English</summary>

**主持人**: And then during or after **MIT**, what was your first professional job where where you got paid and you worked full-time on on techn with technology?

</details>

**Thuan Pham**: 一切都是水到渠成。我在**MIT**的时候，有一个为期多年的合作项目，与当时世界上一些最好的科技公司合作，比如**AT&T**、**贝尔实验室**、**施乐帕洛阿尔托研究中心**、**惠普实验室**等等，这些公司遍布全国。我们申请了这个项目，成绩最好的学生会优先获得机会。然后公司会进行筛选，他们对所有学生进行排名，学生也对他们被排名的公司进行排名，然后进行匹配。我最终来到了**惠普实验室**，当时**惠普**是一家很棒的公司。

<details>
<summary>Original English</summary>

**Thuan Pham**: One thing lead to another. I was when I was at **MIT**, there was a multi-year co-op program with some of the best company tech company in the world at the time. **AT&T**, **Bell Labs**, **Xerox Park**, **HP Labs**, and all these company Bor all over the country actually. And so we applied for it and and then the best the the kids with the best grade got prioritized. Then the company had to go through a selection process. They rank all the kids and then the kids all ranked the company that they got ranked and then there was a matching process and I end up coming to **Hill Packard Laboratories** and **AP** was one of an awesome company at the time.

</details>

**主持人**: 那时他们规模庞大，而且非常……

<details>
<summary>Original English</summary>

**主持人**: Back then they were massive and like very

</details>

**Thuan Pham**: 非常创新，激光打印机、工作站、计算机系统等等。我在**惠普实验室**工作，那是研究实验室，很多真正创新的东西都在那里发生，所以那是一份梦想中的工作。作为一名学生，我能与周围所有其他博士一起从事前沿研究。我可以在那里完成我的学士和硕士联合论文，那是协议的一部分。当我毕业时，**惠普**直接把我招进了那个研究实验室，所以我成为了一名研究员，尽管我没有博士学位。

几年后，我进入了工业界，编写人们实际使用的代码。我非常享受在**惠普实验室**的时光，因为你可以做前沿的事情。我们当时正在研究**医疗信息学**，现在你去每个医生那里，你的所有记录都会跟着你。那时，我们实际上有一个网络分布式系统架构，你去的每个医生工作站，都有你的X光片和所有信息跟着你，然后你还有知识库来查找药物相互作用。哦，我们实际上在80年代中后期就做了这项研究。所以这些都是前沿的东西。

但当时让我感到不满意的是，我们发表了很棒的论文，但它们都没有投入实际应用，没有产品化。我就想，这太酷了，为什么我们不能把它带给用户？但这不是当时的设定。当时的设定是研究实验室只负责研究，然后我们每年都会举办一次技术展，每个产品部门的总经理会过来，决定他们想挑选什么并将其产品化。所以，我感觉在研究阶段之后，我没有被赋予更多的权力。所以我不得不去寻找一个我可以编写代码，并且人们实际使用我的代码的地方。

<details>
<summary>Original English</summary>

**Thuan Pham**: Very innovative laser printers you know workstation computer systems all of that stuff. I was in the **HP lab** which is the research lab where a lot of the really innovative stuff happened and so it was a dream job. as a student I get to work on cutting edge research with all the other PhDs around I get to write the joint thesis for my bachelors and my masters with the work there that was part of the arrangement and when I graduated **HP** just hired me straight into that research lab so I became one of the researcher although I didn't have a PhD and after that that were a few years of that then I went into the industry and write code that people would actually use I really enjoy my time at **HP lab** because you get to do cutting edge stuff. We were working on **medical informatics** at the time where right now you go to every doctors all your recctors following you. Back then we actually have a network distributed system architecture where every physician workstation that you go to right had your your X-ray and everything follow and then you have like knowledge base that actually look at for drug interaction. Oh, we actually did that research back in the mid late 80s actually. And so like these are cutting edge stuff. But then the the thing that I find unsatisfied unsatisfactory at the time for me was we published great paper and then didn't go anywhere. It was not productionized and I'm just like I want this is so cool. Why can't we bring it to the user? But that wasn't the setup. The setup was research lab worry about research and then we would have like a tech fair every year and the general manager of every product division swing by and then decide what they want to pick up and productize. And so I didn't feel empowering beyond the research phase. So I just had to go find a place where I can write code and people actually use my code.

</details>

**主持人**: 于是我去了**Silicon Graphics**。当时我们也试图发明未来，并且我们确实做了一个原型。那时有互动电视，现在我们认为流媒体视频、视频点播、在线游戏、合作游戏都是理所当然的。但在那时，我们还没有手机互联网，我们能够将4000户家庭连接到一个有线电视的18个月试用项目中，然后我们发明了网络协议和所有这些东西。我们实际上制作了一个机顶盒，它连接到显像管电视（甚至不是平板电视），机顶盒是一个**Silicon Graphics**的盒子，我们可以实现网上购物、视频点播。你在没有任何这些东西的情况下构建了所有这些。像**Michael Jackson**这样的名人也来参观演示，我们看到了**Spielberg**，我们看到了所有人。我们真的相信那就是未来，而且它确实是未来。问题是，它远远超前于时代。然后我学到了一个重要的教训：这不仅仅是技术问题，还在于世界是否为此做好了准备，以及它在经济上是否可行。

<details>
<summary>Original English</summary>

**主持人**: So I went to **Silicon Graphics**. At the time we were also trying to invent the future and we actually did a prototype of that. There was interactive TV where back then now we could take for granted a streaming video video on demand online game right cooperative game. Back then we didn't have cell phone internet yet and we can cobble 4,000 um homes together in an 18 trial that has cable and then we invent like network protocols and all these things and we actually formed a set top which is like tube TV not even a flat screen TV with a set top box on top which is a **silicon graphics** box and we can implement online shopping video on video on demand and you're building all of that without having any of this stuff right here like we and and celebrity like **Michael Jackson** came by and saw demos and we saw **Spielberg**, we saw everybody. We thought really believe that was the future and it was the future. The problem was it's way we way way ahead of the time. Right. Then I learned a big hard lesson. It's not about just a technology. It's about whether the world is ready for it, whether it's economically feasible.

</details>

**主持人**: 那么当时你是在什么时候意识到这行不通的，即使我们正在做这些很棒的事情？

<details>
<summary>Original English</summary>

**主持人**: And and back then what was the point where you realized like this is not going to work even though we're doing this awesome stuff

</details>

**Thuan Pham**: 大约一年后，对吧？因为在1994年，仅仅为了配置前端就花费了大约1亿美元。**Silicon Graphics**很喜欢，因为他们卖出了所有这些大型服务器来传输视频，而机顶盒本身就是一个**Silicon Graphics**工作站，成本高达45000美元。人们是不会买那种东西的。

<details>
<summary>Original English</summary>

**Thuan Pham**: After a year, right? because it took like $100 million back in 1994 just to provision the head end. **Silicon Graphics** love it because they sell all these massive server to pump out video and then the settop itself is a **silicon graphics** workstation that cost $45,000 right people would not buy that right

</details>

**主持人**: 尤其像以今天的钱来看，那会是1万到2万美元。

<details>
<summary>Original English</summary>

**主持人**: especially like like in today's money that would be like 10 $20,000

</details>

**Thuan Pham**: 人们是不会买的。早期的尝鲜者和爱好者可能会买，但对于大众市场来说不行。所以当我们进行了那次试验，它非常成功，我们都看到了未来。然后我们又在日本为**NTT**（日本电话电报公司）进行了类似的试验，使用我们编写的不同软件。我们去了日本部署，非常酷，玩得很开心，但后来它也无疾而终，因为它在商业上不可行。所以那是我学到的第一个人生教训，不仅仅是技术问题，你必须在正确的时间、正确的地点，以正确的价格点出现。

之后，我加入了一家由我在**SGI**的前同事创办的初创公司，我们当时在做互联网广告。互联网即将腾飞，**Mosaic**浏览器和搜索出现了，**Netscape**正在组建。是的，在**Netscape**的早期，我们非常清楚地看到，电视的广告模式是有效的，所以它也必须适用于互联网，对吧？因为所有这些内容，如果免费，人们就会使用，但谁来为此付费呢？广告。所以，我加入了一家公司，最初我们称自己为**Netvertiser**，然后很快改名为**NetGravity**。它是一个企业软件，用于在**CNN**和**Netscape**网站上放置动态广告横幅。我是最早的工程师之一，我相信我是第四位工程师。是的。

人们可能不知道，我和我的一个朋友是第一批在**Yahoo**页面上投放第一个动态定向广告的工程师。

<details>
<summary>Original English</summary>

**Thuan Pham**: People would not buy that the early adopter enthusiastic maybe right but not for the mass market and so when we and we we did that trial incredibly successful we definitely all saw the future and then we did the same trial a similar trial with a different set of software that we wrote for **NT nippon telephone** in Japan. We went to Japan deploy that very cool had a really great time but then it fizzled out because it would not be commercially viable and so that was a really first life lesson that I learned it's not just a technology right you got to be at the right place at the right time and the right price point and then after that I went to a startup founded by a former office mate at **SGI** so we were doing internet advertising the internet was about to take off then **mosaic browser** search came out **Netscape** was being form and yeah in the early days of **Netscape** and so we saw very clearly that the the advertising model worked for TV so it has to work for the internet right because all these content people would use it if it's free but then who has to pay for it the advertising so we we I joined a company initially we call ourselves **netvertiser** which is like you know very and then ch it changed it name quickly to **net gravity** and then it's so enterprise software to put ad banners dynamic ad banners ers on **CNN** on **Netscape** site and all that. I was one of the very early engineer there. I was the fourth engineer I believe. Yeah. And so people don't know this but a buddy of mine we were the first pup engineer to put the first dynamically targeted ad on the on the **Yahoo** page on the internet.

</details>

**主持人**: 动态定向是指它根据不同的...或者类似的东西显示不同的广告？

<details>
<summary>Original English</summary>

**主持人**: And dynamically targeted meaning that it showed different ads based on different or or like whatever.

</details>

**Thuan Pham**: 是的。在我来之前的版本是一个脚本，它会抓取内容，然后每小时轮播一个静态横幅广告。但后来我们觉得需要进行定向，然后我们开始使用**cookie**。最初是根据页面的内容和用户，然后我们实际上用它来定向不同的广告，然后我们有了广告序列等等。那是最早的尝试之一。当然，我们取得了一些成功，那家公司上市了。

但我学到的另一件事是，有时你必须抓住市场。有一家公司比我们晚得多成立，但他们做了一个广告服务局，并取得了成功，因为它对人们来说投资少得多，你只需在**HTML**页面上贴一个广告标签，然后收入就会源源不断地到来，对吧？因为服务局会动态地在那里放置广告。我们公司也想做这个，但我们的一位董事会成员说不，你应该先专注于盈利，然后再扩张。哦，我们走了盈利的道路，然后我们变成了一个更大、更强大的企业解决方案，而另一家公司则是在努力实现盈利，并通过互联网扩张，就像筹集**Wi-Fi**一样，几年后被**Google**收购了。所以这就是那段旅程。关于如何构建事物，有很多教训。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. The version before I came in was a script that crawl through and just put a stick static banner ad and rotate it through every hour. But then we it's like we got to target it and then we started using **cookie** we started you at first it was a content of the the page and and the person and then we actually use that to actually target different ad and then we have ad sequence and all that stuff and that was the very first one of course we had some success there that company went public but another thing that I learned was sometime you got to seize the market right there's a company that formed right much later than us but did an ad service bureau And that took off because it take a lot less investment for people to you just stick a banner a tag on your **HTML** page and then revenue just come your way, right? Because the the the service bureau kind of stick the app there dynamically or that kind of stuff. We had wanted to do that in our company but then one of our board members said no you should focus on get to profit first before you expand. Oh, and we went down the profitability path and we then becomes like you know a bigger robust enterprise solution where the other one is and try to get profitable and the other one is just expand through the internet like raising **Wi-Fi** then after that years later got bought by **Google**. So that was the journey there. There's a lot of lesson there about how to build things.

</details>

**主持人**: 那么，我是否理解你的意思是，你看到了当市场巨大时，如果你专注于盈利，这本应是合理的，但如果一个参与者专注于增长，即使不盈利，最终也可能把你吞噬？

<details>
<summary>Original English</summary>

**主持人**: So, so this was do I understand that you you you saw that what happens when there's a big market and you you focus on profitability which which should make sense but a player focuses on growth even at being nonprofitable. It might be able to swallow you in the end.

</details>

**Thuan Pham**: 完全正确。看看**Uber**发生了什么，对吧？我们没有做出正确的举动。

<details>
<summary>Original English</summary>

**Thuan Pham**: That's right. Look at what happened to at **Uber**, right? We did not the right move.

</details>

**主持人**: 我开始明白这些事情是如何联系在一起的。所以现在你在那家差点起飞但没有完全成功的初创公司。那么你的下一站是哪里？那家公司上市后被收购了。在那里工作了大约七年后，我晋升到了副总裁级别。我最初是以个人贡献者身份加入的。在此过程中，我从**Silicon Graphics**的日子里得到了启发，我知道如果你想做真正大的事情，你需要借助他人的力量。你不能只靠自己的双手完成。所以我转到了管理岗位，磨练了技能，一路晋升到总监、高级总监，最终成为副总裁。

<details>
<summary>Original English</summary>

**主持人**: I'm starting to see how these things are coming together. So now you're at the startup which almost took off but not quite. And then what was your next stop? That company went public and then got absorbed and after about seven years there I had made it to the VP level. I joined as an IC. Along the way I knew that from my inspiration at the **Silicon Graphics** day that if you want to do something really big you need to leverage other people. You can't do it with your bare two hands. So then I switched over to the management track and I honed the skill and I got up to directors and senior directors and then ultimately got the VP and then

</details>

### 互联网泡沫与职业发展

**Thuan Pham**: 大约八年，七八年后，互联网泡沫破裂了。然后我说，也许是时候证明自己了，看看我是否只是昙花一现，或者我是否真的拥有可转移的技能。

<details>
<summary>Original English</summary>

**Thuan Pham**: After about eight years, seven year, eight year there, the com bust happened right of that time and then I said well maybe it's time to prove to myself whether or not I'm just a one hit wonder or I actually have skill that are transferable.

</details>

**主持人**: 只是关于互联网泡沫的一点，因为你有点一笔带过了，你现在已经经历了很多起起伏伏，但你能带我们回顾一下互联网泡沫到底发生了什么吗？因为我采访过的人，尤其是新毕业生，都觉得那听起来非常非常可怕。你当时感觉如何？你周围的专业人士、工程师们感觉如何？

<details>
<summary>Original English</summary>

**主持人**: Just just one thing on the **dotcom bus** because you kind of swept over it because you you've now seen a lot of like ups and downs but can you take us a little bit back what actually happened with comb bus because the people I talked to especially were new grads it sounded very very scary what what did you feel like and what did people professionals engineers all around you feel like

</details>

**Thuan Pham**: 互联网泡沫破裂时确实有点可怕，但在此之前，有一种过度狂热，认为一切都是**.com**，比如**pest.com**、**fubar.com**，一切都是**.com**，**Webvan**。是的，所有这些东西。我车库里实际上还有**Webvan**的垃圾桶。

所以，是的，但最终还是经历了一次洗牌。最终必须要有健全的商业模式，能够持续盈利，对吧？增长和利润。仅仅增长最终会烧钱，那是不好的。你可以快速增长，但最终你必须将其转化为利润，才能成为一家持久的公司。所以在那个互联网浪潮中，涌现了许多大型公司，比如**Yahoo**、**Google**、**Amazon**，所有这些公司。也有许多其他公司，比如**Webvan**等等，它们会倒闭，因为它们没有经受住时间考验的强大价值主张，对吧？所以，是的，这一切都关乎你提供什么价值，以及它是否对客户有益和有价值，以至于他们愿意为此付费，对吧？

我认为这是我们学到的一件事。哪些是真正基础强大的业务，即使最初可能不盈利，但哪些只是跟风，对吧？只是在某个东西上加上一个**.com**，然后它就很热门。现在可能有很多**AI**相关的事情正在发生，对吧？最终，其中一些会整合，一些会倒闭，一些会成为非常棒的解决方案等等。所以，但市场会解决这个问题。最终，客户会投票决定他们想把钱花在哪里。

说到构建持久的东西和不持久的东西，始终将两者区分开来的一点是代码质量。这正是我们本季赞助商**Sonar**所关注的。**Sonar**是**Sonar Cube**的制造商，他们坚信代码质量和代码安全是内在关联的。高质量的代码自然更具弹性，随着代理开始大规模编写代码，验证层就成为你最重要的安全边界。这就是像**Sonar Cube**高级安全这样的解决方案的价值所在。凭借这种新的恶意软件包检测功能，高级安全提供了实时断路器，自动阻止代理在它们进入你的管道之前拉取未经验证或有风险的第三方库。其影响也是可衡量的。根据**Sonar**的2026年代码开发人员调查报告，使用**Sonar**验证代码的开发人员因**AI**导致停机的可能性降低了44%。这确实是为了弥合**AI**速度与生产安全现实之间的差距。**Sonar**还在做些什么来帮助减少停机、提高安全性和降低与**AI**和代理编码相关的风险？请访问sonarsource.com/pragmatic了解更多信息。

<details>
<summary>Original English</summary>

**Thuan Pham**: The com bus was was kind of scary when the correction happened right but before that there was this exuberance that everything is.com right pest.com fubar.com everything is a.com **webban**. Yeah, all of that stuff. I still have the **webb van bin** in my garage actually. And so, yeah, but then there there was a shake out eventually. There has to be sound business model that makes sustained profit, right? Growth and profit. Growth alone eventually burn, you know, money and that's not good. You can grow fast, but eventually you have to turn that into profit to be a durable company. And so in that dot wave there were massive company that emerged, right? There was **Yahoo**, there's **Google**, there's **Amazon**, all of those company. There's also a bunch of other company, **web van** and others, whatever that would go under because they didn't have like a strong value proposition that last the the test of of time, right? So, yeah, it's all about the what value you deliver and whether or not it's beneficial and valuable to the customer that they're willing to pay, right? And I think that's one thing that we learned. Which one is like a real fundamental strong business even though it might not be a profit initially, but which one are just a me too, right? Just put a.com on something and and it's hot there. There may be a lot of **AI** things that's going on right now, right? Eventually some of these things will consolidate, some will go under, some will become really awesome solutions and all that stuff. And so, but the the market will sort it out. In the end, the the customer will vote on what they want to spend the money on. Speaking of building things that last versus things that don't, one thing that always separates the two is cold quality. And that's what our season sponsor **Sonar** is all about. **Sonar**, the makers of **Sonar Cube**, is deeply rooted in the core belief that code quality and code security are inherently linked. Highquality code is naturally more resilient, and as agents start to write code at a massive scale, that verification layer becomes your most important security parimeter. This is where solutions like **Sonar Cube** advanced security are valuable. With this new malicious package detection, advanced security provides a real-time circuit breaker, automatically stopping agents from pulling in unverified or risky thirdparty libraries before they ever hit your pipeline. The impact is measurable, too. Developers who verify their code with **Sonar** are 44% less likely to report experimenting outages due to **AI**. As per **Sonar** states of code developer survey 2026 report, it's really about closing the gap between the speed of **AI** and the reality of production security. What else is **Sonar** doing to help reduce outages, improve security, and lower risks associated with **AI** and agenda coding? Head to sonarsource.com/pragmatic to find out.

</details>

**主持人**: 带着这个，我们回到**Thuan**在互联网繁荣与萧条之后做了什么。当时有很多裁员，公司破产。这让你周围的人担心吗？这让你担心你的工作可能面临危险，或者你换工作会更困难吗？还是说这只是一个非常短暂的时期？

<details>
<summary>Original English</summary>

**主持人**: With this, let's get back on what **Swan** did after the com boom and bust. And there was a lot of layoffs, companies going bankrupt. Did that worry people around you? Did that worry you that, you know, your your job could be in danger or you might have a harder time switching jobs or did you not did was was it a very short-lived?

</details>

**Thuan Pham**: 持续了几年。我记得在那段时间，找工作确实很难。尤其是对于应届毕业生来说，当一切都紧缩时，他们总是最先受到冲击的群体。人们想要更有经验的人，人们想要留住现有员工，而不是继续招聘需要持续投入的初级员工。所以，这只是当时的经济状况，它会一波又一波地来去。是的，那肯定是一个非常可怕的时期。但当然，从更长的历史范围来看，事情通常会恢复。但这确实导致了重组。是的，所以在那段时间，确实很艰难。

然而，我看待这件事的方式是，人才永远是人才，对吧？所以真正有才华、真正渴望成功、总是努力超越自己能力的人，永远都会有市场。

<details>
<summary>Original English</summary>

**Thuan Pham**: It lasted a couple years. I remember and during that time it was definitely hard to to get a job. especially for new college grad that's always the the the first layer that get hit right when everything retrenchs people want more experienced people people want to stress existing folks rather than keep on you know hiring entry- level so that you have to you know continue to invest in right so it's just the economy of time it it comes and go in wave um yeah so that's always a certainly a very scary time u but of course you know in the longer range of history things generally tend to recover But it it caused a rearrangement and yeah so during that time it was it was certainly tough. However I the way I look at this thing is like yeah talents are always talent right so people really strong talents and who's really hungry is always um try to punch above their weight will always be marketable right yeah

</details>

**主持人**: 即使在经济低迷时期？

<details>
<summary>Original English</summary>

**主持人**: even in a downturn

</details>

**Thuan Pham**: 即使在经济低迷时期。所以我认为关键在于人们即使在和平时期也应该投资于自己的技能，永不自满，不断努力变得更好。然后在战时或困难时期，这些技能会拯救你。如果人们只是非常自满，随着时间而退化，那么当困难时期来临时，就很难从中恢复过来。

<details>
<summary>Original English</summary>

**Thuan Pham**: Even in a downturn so I think the key thing is how people should even in peace time invest in that skill never be complacent constantly try to be better and then in wartime or in rough time those will save you right if people just be very complacent atrophy with the time and then when rough time hit it's very very hard to recover from that

</details>

**主持人**: 然后你去了**VMware**。

<details>
<summary>Original English</summary>

**主持人**: and then you went to **VMware** at this time.

</details>

**Thuan Pham**: 嗯，是的。所以，我从**DoubleClick**去了那里，然后我跳槽到了一家只有四人的公司，屋顶漏水，一切都像经典的初创公司一样，但那家公司没有成功。大约三年左右，公司发展到四五十人，然后资金耗尽，被另一家公司收购了。那家公司构建了一个安全设备产品，试图解决网络服务流量中介的问题。那是一个非常有趣的安全利基市场，但它不是大众市场产品，所以公司很难突破。是的，但最终它还是消失了。但即使如此，那三年也教会了我很多。好吧，即使你从零开始做，你也能生存下来。然后你仍然可以学习到技能，尽管那段旅程可能不会以商业成功告终。但是你的技能仍然会变得更好。

<details>
<summary>Original English</summary>

**Thuan Pham**: Mhm. Yeah. So um let's see after I went from **double click** to that and then I jumped into a fourperson company again leaky roof and everything classic startup that business did not succeed. Uh it took about 3 years or so, got to about 40 50 people in size and then kind of ran out of money and then got acquired by another entity that was built with a security appliance product with try to solve the problem of you know intermediation of web services traffic going through and it was a very interesting security niche but it's not a mass market thing and so it's hard for a company to kind of break through like that right and um but eventually it it uh it went away but even then you Those three years taught me a lot. Um, okay. That you can survive even when you do it from the ground up. Uh, then you still have skill that you can pick up despite the fact that that journey might not end in like a commercial success. Uh, but your skills still get better.

</details>

**主持人**: 所以即使公司没有成功，你作为专业人士也在变得更好。

<details>
<summary>Original English</summary>

**主持人**: So you are getting better as a professional even though

</details>

**Thuan Pham**: 这就是我们必须相信的。我们投资自己，当然也投资我们所参与的公司或载体。理想情况下，双方都能成功，但如果另一方成功了，至少如果你真的努力工作，你就会获得一些技能。然后在此基础上，你就可以利用你迄今为止学到的一切，以及你犯过的所有错误，所有这些都会让你变得更聪明、更好、更有智慧，去寻找下一个机会。

所以，在那家公司被收购后，我立即寻找了其他机会，然后我去了**VMware**。同样，当时**VMware**还是一家相当小的公司，并不为人所知。所以它是一个40人的组织，构建软件来整合。

<details>
<summary>Original English</summary>

**Thuan Pham**: And that's something we have to trust. We invest in oursel but of course we invest in the company or vehicle that we are part of and ideal case both side succeed but if the other succeed at least if you work really hard you will gain some skill and then based on that uh then you can then leverage all the thing that you learned so far and all the mistake that you've made all it got you smarter and better and wiser to look for the next opportunity. So right after that I look at a bunch of other thing when that company was acquired and then I I went into **VMware** um again when **VMware** was a pretty small not very well known yet um so it was um 40 person organization and so that build software to stitch together

</details>

**主持人**: 所以**VMware**当时还处于早期阶段。

<details>
<summary>Original English</summary>

**主持人**: so so **VMware** was still early

</details>

**Thuan Pham**: **VMware**当时还处于早期阶段，是的。它有三个部门。一个部门负责工作站桌面应用程序，另一个部门负责**hypervisor**，也就是操作系统之下的操作系统。然后是我的部门，负责构建企业软件，将所有**hypervisor**整合到一个云平台和管理平台中。所以我是其中一员。我们有40人，我们构建了**VMware**的第一个产品套件，叫做**Virtual Center**，它与**ESX**绑定。所以那是一个非常非常有趣的项目。

<details>
<summary>Original English</summary>

**Thuan Pham**: **VMware** was it's still early yeah there was two there was three division um one division that did the the workstation desktop app and then there was the division that does the **hypervisor** which is the OS underneath the OS. And then there was my division that was building enterprise software that stitched together all of the **hypervisor** into like a a cloud platform and management platform. Right? So I was one for that. It was our 40 people and we kind of built the very first product suite for **VMware** called **virtual center** that tied to **ESX**. So that was um that was a really really fun right people

</details>

**主持人**: 然后**VMware**真正腾飞了。虚拟化作为一个整体也腾飞了。在2000年代早期，**VMware**是其中的核心部分，是主要推动者之一。所以那是一种像曲棍球棒一样的增长体验吗？

<details>
<summary>Original English</summary>

**主持人**: and and then and then **VMware** really took off. virtualization as a whole took off. In the early 2000s, **VMware** was was core part of it. It was one of the main things. So it was just uh was it a kind of hockey stickish experience?

</details>

**Thuan Pham**: 它的增长没有**Uber**那么极端。但是，它确实是，因为它是一项改变行业的技术。它是一个游戏规则的改变者。在那之前，没有类似的东西。起初人们认为，“哦，这只是一个有趣的桌面工具，你可以在一台PC上运行几个Mac和PC操作系统”，但真正的力量在于**ESX**，对吧？是的。然后那就是你为数据中心提供动力的方式。当然，那是**hypervisor**，但我认为让**VMware**如此有用的关键特性是整个**vMotion**功能，当你将一个虚拟机从一个硬件迁移到另一个硬件时，应用程序几乎没有可感知的停机时间。有了这个能力，就解锁了整个云的概念，对吧？因为你有一千台机器，但它看起来像一台。它看起来像一台C机器，所以你机器内部的应用程序会自行扩展，它会自行移动，它可以做任何你需要做的事情，对吧？你可以做灾难恢复（DR），你可以做各种各样的事情。所以这实际上让它非常像一个云操作系统。

<details>
<summary>Original English</summary>

**Thuan Pham**: It was um not to the extreme of **Uber**. Um but it certainly was because it was a industry changing technology. It was a game changer. Right? Before that there wasn't anything like that. At first people thought, "Oh, this is kind of interesting tool on the desktop for you to run a couple of, you know, Mac and PC OS on top in on a PC, but the true power was the **ESX**, right? The Yeah. And then that's what you power data center. And then of course that's the the **hypervisor** but the the I think the key feature that made **VMware** so useful was the whole **votion** thing when you take a virtual machine and you can migrate it from hardware to hardware without any perceivable downtime of the application run on top with that capability. unlock the whole cloud thing, right? Because you have a thousand machine, it can look like one. It can look like a C machine and so application inside of your machine will just scale and it will just move itself and it can do whatever you need to do, right? You can do **DR**, you can do, you know, uh yeah all kinds of things with it, right? So that's actually make it very much like a cloud operating system.

</details>

**主持人**: 然后在**VMware**，你也随着公司一起成长，对吧？所以，你似乎有这样的经历：你先在一家初创公司担任工程副总裁，然后降职到一家小型初创公司，接着加入**VMware**，最终也成为了**VMware**的工程副总裁，对吧？

<details>
<summary>Original English</summary>

**主持人**: And then at **VM** where we also grew with the company, right? So, so again I it seems you have this history of you were VP of engineering at the startup, you stepped down to a small startup, you then joined **VMware** and eventually you became VP of engineering at **VMware** as well, right?

</details>

**Thuan Pham**: 嗯，是的。我有一个奇怪的习惯，当事情变得很大，我开始感到太舒服时，我就会紧张。

<details>
<summary>Original English</summary>

**Thuan Pham**: Mhm. Yeah. Yeah. I have this weird thing where when I get when the thing get large um and I start to feel too comfortable, I get nervous

</details>

**主持人**: 真的吗？

<details>
<summary>Original English</summary>

**主持人**: really.

</details>

**Thuan Pham**: 是的。所以在**DoubleClick**，当我成为副总裁并管理数百人时，我就会想，这只是侥幸还是真的有实力？所以我不得不回到一家四人公司，试图看看这是否真实。那次尝试不是很成功，但引擎是健康的，是好的。然后当**VMware**再次从小公司发展壮大，当它变得非常大时，当你达到一个只是管理事务而不是开辟新天地、努力学习的阶段时，你就必须做一些不同的事情，对吧？所以我不断回到小公司，当我变大时，我可能会再次回到小公司。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. And so that's where when at **double click** when I got to VP and I managed hundreds of people, I like is this a fluke or is it real? So I had to go back to a fourperson company and try to see if it's real or not. That didn't succeed really well, but the engine was healthy. It was good. And then when a **VMware** again is a smaller company and go big and when it get really big again when you get to a point where you're just running things rather than breaking ground and doing this thing or how hard learning then you got to do something different, right? So I keep on going back small and when I get big I might go back small again and

</details>

**主持人**: 是的，我看到了这个模式。你在**VMware**取得了很大的成就，**VMware**当时表现出色。是什么让你四处寻找，你是如何找到当时这家非常小的公司**Uber**的？或者它当时可能叫**UberCab**，我甚至不确定它叫什么。

<details>
<summary>Original English</summary>

**主持人**: yeah so I'm seeing the pattern. So you you got big at **VMware** and **VMware** was doing amazing. What made you um look around and how did you find this very small company at the time called **Uber** or it might have been **Uber Cab** I'm not even sure how it was called.

</details>

**Thuan Pham**: 当时已经是**Uber**了，那是在那之前很久了。是的。嗯。是的。那是在**VMware**工作了8年之后。有时人会变，有时公司会变，有时双方都会变。所以，对我个人而言，变化是我觉得在那里已经无法再做更多事情了。对。我管理着一个800人的工程团队。我们正在构建这个那个软件，这已经是那个软件的第三代了。我们在调整，在增加更多功能。我爱我的团队，但你知道，这更多的是保持稳定，保持增长，增加更多功能。然后公司也随之发生了变化。你知道，最初的创始人离开了，新的团队进来了，有很多变化和个性。一段时间后，就觉得是时候离开了。

<details>
<summary>Original English</summary>

**Thuan Pham**: It was **Uber** at the time already was way before that. Yeah. Mhm. Yeah. It was when after 8 years at **VMware** um and sometime people change sometime company change uh sometime both side change and so um yeah for me what changed personally for me was I reached to the point where I didn't feel I could do much more there. Right. I'm running 800% engineing team. We're building this that this software and and it's been like the third generation of that software already. We're tweaking, we're adding more feature to it. I love my team and all that. But you know, it's just more of like keep it steady, keep it growing and add more feature. And then the company has also changed along the way. you know, the the original founder left, new crew came in, and there's a fair amount of changes and personalities and all that. And after a while, it just felt like it's time.

</details>

**主持人**: 那么，以你现在的背景，你拥有了令人印象深刻的履历。你可能可以去任何地方，无论是大公司还是小公司。你的求职过程是怎样的？你是如何再次遇到**Uber**的？因为当时**Uber**还相当默默无闻。

<details>
<summary>Original English</summary>

**主持人**: So, so now with your background, like you now have a super impressive background. You probably could have gone anywhere large or small. What was your search process look like? And and then how did you come across again? Cuz **Uber** was still pretty obscure.

</details>

**Thuan Pham**: 是的。这里有一个非常有趣的事情。人们确实问我求职过程是怎样的。你是如何建立这样一番事业的？我的诚实回答是，我什么都没做。这也不是你偶然发现一个又一个机会的运气。实际上是另一回事。那就是如果你在每家公司都努力做好工作，与所有同事，包括你自己的团队、你的同事等等，都合作良好。随着时间的推移，非常缓慢地，你会在人们心中积累起一个不错的声誉。人们在行业中来来往往。但如果你对他们好，他们往往会记住这一点。然后当你变得有空时，人们就会来找你。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Uh here's a really interesting thing. People do ask me about what the search process look like. How did you sit together a career like that? My honest answer is I didn't do any of that. And um and it wasn't luck that you that you bumble around and you find one thing after another. It's actually something different. It's that if you try to do a really good job at every company you've been working well with all the people that you work with, including your own team, your peer, whatever it is. Over time, very slowly, you accumulate a decent reputation in people's mind. And people always come and go throughout the industry. But if you're good with them, to them, whatever, they tend to remember that. And then when you become available, then people come to you.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Thuan Pham**: 就像这样，“这个怎么样？那个怎么样？这个又怎么样？”然后你实际上会审视所有这些事情。然后你就可以深入挖掘并做出决定。所以，这在硅谷多次发生在我身上。尤其我认为最大的突破是**Uber**。同样，当我离开**VMware**时，我没有计划做任何事情，对吧？我说，“好吧，让我们坐下来看看发生了什么。”然后，**Benchmark Capital**的**Bill Gurley**，他是**Uber**的早期投资者，你猜他与我的联系是什么？他从十年前的**NetGravity**那家初创公司认识我。所以我们算是认识，但当然，当我们认识一个人时，你会关注他们的声誉。是**Bill**来找我，在他知道我离开**VMware**后，他说：“嘿，你能看看这个吗？我正在投资它，可能会非常有趣。”所以我去了他在**Sand Hill**的办公室，他与我分享了董事会演示文稿，以及公司是如何增长的。然后我理解了它的商业模式。对，当时我试图招聘一些人时，他们都会问：“为什么**Thuan**，你为什么要加入一家出租车公司？”

<details>
<summary>Original English</summary>

**Thuan Pham**: Like this, how about this? How about this? How about this? And then you actually look at all those thing. And then you can dig in and you can decide. And so that played out multiple time for me in the in the valley. And especially I think the biggest breakthrough was **Uber**. Again, when I left **VMware**, I didn't plan to do anything, right? I'm said well let's sit back and take a look see what's going on and then **Bill Gurley** from **Benchmark Capital** who invests in early investor in **Uber** and guess what his tie was he knew me from that **net gravity** startup a decade before and so he we kind of knew each other and then but of course when we know someone you follow their reputation and it was **Bill** who come to me after he knew that I'm leaving **VMware** hey can you take a look at this one I'm investing it could be really interesting so I went up to his his um office in um **San Hill** and he shared with me the board deck and how the company is growing and then I understood the the business model right to all of you back then when I trying to recruit some people it was like why Don why you joining a taxi company right

</details>

**主持人**: 是的，我记得每个人都在问这个问题。

<details>
<summary>Original English</summary>

**主持人**: yep I remember everyone's asking that question

</details>

**Thuan Pham**: 完全正确。所以，但我知道这一点。当然，我们必须经历与**Travis**的相当严格的面试过程。是的，但最终，是这种联系促成了正确的事情，但这种联系和机会基本上都与你的声誉息息相关。

<details>
<summary>Original English</summary>

**Thuan Pham**: exactly and so but I I knew that and of course then we have to go through like a pretty rigorous interview process with **Travis** and uh yeah, but ultimately it's about the connection that lead to the the right thing, but that connection and the opportunity is basically tied to your reputation.

</details>

### Uber CTO面试：30小时的深度交流

**主持人**: 然后那时，我查了一下，你也帮我查了，**Uber**刚刚完成了B轮融资，获得了3000万美元，估值3亿美元，这在当时规模不小，但远不及后来成为的巨头公司。我读到一个有趣的事实是，你和**Travis**有一个非常严格的面试过程，持续了几十个小时。你能谈谈那是怎么回事吗？

<details>
<summary>Original English</summary>

**主持人**: And then back then as I I I looked it up and you also helped me with this, **Uber** just raised it series B which was $30 million is value at $300 million which was sizable but still not nearly the the gigantic company that it later became. And one fun fact that I I read about is you had this very rigorous interview traveler process which was tens of hours or or something like that. Can you can you talk about how that went?

</details>

**Thuan Pham**: 他能做到这一点，令人印象深刻。他投入了超过30小时一对一地面试我。

<details>
<summary>Original English</summary>

**Thuan Pham**: It was impressive on that he did that. It was he committed over 30 hours interviewing me oneon-one.

</details>

**主持人**: 哇。

<details>
<summary>Original English</summary>

**主持人**: Wow.

</details>

**Thuan Pham**: 是的。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah.

</details>

**主持人**: 那就像好几天的长时间……

<details>
<summary>Original English</summary>

**主持人**: That's like several days of like long

</details>

**Thuan Pham**: 两周的面试，每天至少几个小时。

<details>
<summary>Original English</summary>

**Thuan Pham**: Two weeks worth of interviewing every single day. A couple hours each day minimum.

</details>

**Thuan Pham**: 是的。带着激情，带着好奇心，一段时间后，我甚至忘了我正在被面试。那就像人们分享想法，交流想法，有时意见不合，然后一起解决问题。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. with passion, with intrigue and we end up after a while I kind of forgot that I was being interviewed. It was like through people kind of sharing ideas like exchanging idea and sometime disagree something and then kind of work it out

</details>

**主持人**: 然后你给我看了一张照片，上面列出了你们讨论的一些话题。你能总结一下那些话题是什么吗？

<details>
<summary>Original English</summary>

**主持人**: and then you you showed me you took a photo of like some topics that you talked about like can you like summarize what what those were?

</details>

**Thuan Pham**: 是的。我第一次会议时，我开车去了旧金山，在办公室见到了**Travis**。我们立刻去了白板，他写下了他想和我讨论的所有话题，那是一个很长的清单。有一个关于招聘、解雇、沟通以及设计等一般性话题的长清单，然后有一个关于工程特定内容的短清单，比如代码质量、质量保证、设计等等。然后还有一个更短的清单，列出了他希望在一个工程团队中看到的五件事以及工程团队的文化。是的，那就是清单。所以我们写完清单后，就开始讨论，从清单上挑一些项目来谈。当然，我本应该和他开一个小时的会，结果持续了两个小时，这实际上很好，因为我们完全投入其中，时间就这么过去了。然后，我一开车离开办公室，刚到出口，就接到了招聘人员的电话，说：“**Travis**想再见你，再多聊聊。”所以我们照做了。当然，他非常忙。他四处奔波于所有区域办公室，管理业务。所以我们每天都安排了**Skype**会议，每天两个小时，我们会选择一个话题。这就是为什么我拍下了那个白板的照片，他也做了同样的事情，列出了要讨论的话题清单，我至今手机里还存着。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. uh my very first meeting I drove up to San Francisco and saw **Travis** in uh in the office and we immediately went to the whiteboard and he wrote down all the topic on his head that you know he want to talk about with me that was a really long list there's a big long list of general topics about you know hiring and firing and communications and all of that stuff or design everything else and then there's a shorter list of very engineering specific stuff what about code quality what about QA what about design um all that and then there is also a list of shorter list of the five things that he want to see in an engineering team and and the culture of the engineing team and yeah and so that was the list and so after we wrote the list um we start talking picking up some item off the list and talk of course you know in two hours I was supposed to meet him for an hour it last two which is actually good because we got totally into it time ran out and then as soon as I drove drove out of the office. I barely get to the exit. I got a call from the the recruiter say, "Go **Travis**, we want to see you again and talk talk some more." And so we did that. And of course, he's very busy. He's traveling around the all the regional offices um to run the business. And so we set up a **Skype** session every single day for two hours each day and we will pick one of the topic. That's why I took a picture a photo of that whiteboard and he did the same thing as a as a list of topic to talk about and I still have it on my phone today.

</details>

**主持人**: 这对我来说太令人印象深刻了，因为我们会在这期节目中分享那张截图，但事实是CEO会深入到代码审查这样的事情，招聘话题我理解，但他对工程如此关注，或者说你是否感觉到他有这样的愿景，即技术和工程对**Uber**至关重要？

<details>
<summary>Original English</summary>

**主持人**: It's it's so impressive to me that cuz we'll we'll share that list in this episode as well that screenshot but that the fact that the that the CEO would go into things like code review like it's the hiring topics I understand but but that he was so engineering minded or did you get a sense that he had the vision that technology and engineering would be just key to **Uber**?

</details>

**Thuan Pham**: 哦，绝对是。我的意思是，他知道这一点，从一开始就非常清楚，他认为业务有两个主要的引擎来驱动。一个是运营，你知道，比特和原子，对吧？你必须有车轮，有实物在世界各地移动，然后是技术，而技术是其中的关键部分，对吧？没有哪一方比另一方更重要，但它需要两者兼备。是的，所以那是非常关键的，我认为他也知道自己想要什么，以及他希望在任何人身上看到什么。所以我想这个清单和这一系列对话是为了让他验证这一点。是的，后来，我想他要么说了什么，要么我明白了，那实际上是在模拟与另一个人一起工作的感觉。

<details>
<summary>Original English</summary>

**Thuan Pham**: Oh absolutely. I mean he he knew that and it was very clear from the very beginning that he viewed the business has two major engine that powers it. One is the operation you know bits and atom right you got to have wheels physical thing moving around the world and then there's technology and technology is a key part of that right no one side is super appeal to the other but it require both of those yeah and so that was very key and I think he also knew what he wants also and what he want in whoever it is and so I think this list and this this this series conversation was for him to to vest that yeah Later on, I I I think either he said something or I figured out that it was actually a simulation of what it's like to work with another person

</details>

**主持人**: 在那种能力下。最终，当我们身处其中时，我们所有人都在一直互相合作，我们能对某些事情意见不合吗？我们能解决问题吗？我们是否普遍拥有相似的理念和原则？他亲自做到了。是的。所以，是的，他所展现出的激情和投入程度令人印象深刻。从我这边我可以告诉你，比如有些时候，我们完全投入其中，两个小时过去了，他不得不停下来赶飞机去其他地方，他真的停下来告诉我等一下，然后拿起电话打给他的行政助理，说能不能改签我的航班，继续对话。谁会有这种程度的投入和激情呢？当你看到这些时，它真的会吸引你。

<details>
<summary>Original English</summary>

**主持人**: in that capacity. In the end, when we inside, we all working with each other all the time and can we disagree on something? Can we work things out? Do we have generally similar philosophy and principle? And he did it himself. Yeah. And so that Yeah. and and the the level of passion and commitment he showed was just really impressive from from this side I can tell you for example there's some session when we totally you know in the middle of that and two hours gone by and he had to like stop and catch a flight to go somewhere else he literally stopped and told me just wait and he'd pick up his phone call his EA and say can you move my flight and continue the conversation who had that level of commitment right and passion and stuff like that and when you see that it actually draws you in.

</details>

**主持人**: 是的。所以我想你加入已经不是问题了，但你能回忆一下从内部看，尤其是从工程和系统角度看，当时的情况是怎样的吗？

<details>
<summary>Original English</summary>

**主持人**: Yeah. So I guess it was not a question that you joined but can you recall what was it like from the inside especially from an engineering point of view from a systems point of view from like what was going on?

</details>

### Uber早期：在混乱中求生与调度系统重写

**Thuan Pham**: 当时规模还很小。我调取数据时，每天大约有3万次乘车请求，周末总是最繁忙的时候，人们四处出行。是的，那个周末，也就是我周一入职前的周六或周日，每天大约有3万次乘车请求。当时**Uber**在全球大约有二三十个城市，所以规模非常适中。当时已经有一些有利的因素。工程团队非常年轻，但非常精干，非常投入且有才华，无论需要做什么，他们都能齐心协力完成。因此，服务非常出色。当时我们只有豪华轿车服务，但对于所有乘坐的人来说，体验非常棒，这就是为什么口碑传播如此之快。

是的，所以那是真正好的部分。现在，**Travis**可能预见到的，或者其他什么，是下一个阶段，即随着公司越来越快地增长，会发生什么。顺便说一句，那40名工程师都非常年轻，我想他们都在20多岁，而且系统并不是为了规模化而构建的，对吧？它是为了功能性而构建的。它实际上是……

<details>
<summary>Original English</summary>

**Thuan Pham**: So it was still pretty small. It was um about 30,000 rides a day when I pulled the data the the the weekend which is always the busiest time when people move around. Yeah. That weekend the the day the the Saturday or Sunday before I join I joiner Monday. um was about 30,000 rides a day. Uh and **Uber** was I don't know 20 something cities around the world at that point uh 2030 and so it was very modest. The there's certain things that were going for it already. The the engineing team was very young but uh pretty scrappy and uh pretty committed and talented where whatever need to get done by hook by group they co together right and so and as a result though the the the service was beautiful. anybody who ride we only had black car service at the time but the XP was beautiful when for all the people who ride it that's why word of mouth is you know raging around and uh yeah and so that was the really good part now the thing that maybe **Travis** had foreseen or whatever it is was the next phase which as the company grow faster and faster what happened right and by the way the the the 40 engineer were very very young I think in the 20s all of them and um the system was built not to scale, right? It was built for functionality. It's actually

</details>

**主持人**: 整合在一起，而且它奏效了。

<details>
<summary>Original English</summary>

**主持人**: together and it worked.

</details>

**Thuan Pham**: 是的。它奏效了，而且运作得非常好，对吧？但它无法扩展，而且会一直崩溃，每周多次。那就是我们在战壕里的生活。曲棍球棒式的增长确实发生了。是的，一切都崩溃了。我们基本上必须与时间赛跑，才能弄清楚下一个最关键的崩溃点是什么，以及如何提前解决。司机们甚至在面试时就一直告诉我的一件事是，你必须“看到拐角处”。所以我尽力去“看到拐角处”。

我入职后的头几周，除了认识工程师、建立关系和信任之外，我做的第一件事就是开始审视我们目前拥有的和我们需要的东西，而调度系统是第一件事。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. And it worked and it worked beautifully, right? But it wouldn't scale and it would crash and burn all the time, multiple times a week. And that was our lives in the trenches. The hockey stick actually happened. Um yeah, everything breaks. Uh and um and we have to basically race against time to actually figure out what would be the next most critical thing that would break and how to get ahead of it. And one of the thing that drivers always tell me even from the interview days is you got to see around corner. So I try my very best to see around corner this that's and one of the first thing I I did when the first couple weeks were beyond getting the getting to know the engineer and build relationship and build trust was to start examine what we currently have and what we need and dispatch was the first thing

</details>

**主持人**: 没有调度系统，就没有一切，对吧？那是你匹配乘客和司机的地方。

<details>
<summary>Original English</summary>

**主持人**: without dispatch there is nothing right that's where you match the writers and and drive

</details>

**Thuan Pham**: 是的，那是我们的匹配服务，对吧？当它有司机、乘客并进行匹配时。

<details>
<summary>Original English</summary>

**Thuan Pham**: yeah it's it's our matching service right when when it has the drivers the writers and does the match

</details>

**主持人**: 完全正确，没有它就没有业务，对吧？

<details>
<summary>Original English</summary>

**主持人**: that's right and without that there's no business right there's

</details>

**Thuan Pham**: 是的，我开始着手，那是我看的第一个系统。我问了一些问题，我审查了架构，我审查了实施计划。很明显，它无法扩展。它是一个**JavaScript**，是**NodeJS**，而且是单线程的。当时的工程师在城市变得越来越大时，他们需要那段代码来支持城市，他们就会把那段代码移到一个更大的、处理器更快的机器上。

<details>
<summary>Original English</summary>

**Thuan Pham**: And so yeah and I I start that was the first system I looked at and I asked some I I reviewed the architectures I reviewed the implementation plan and um it was very obvious that wasn't going to get scale uh it was a **JavaScript** it's **NodeJS** and it was a single threaded thing and the engineer at the time where when the city get larger and larger uh they need more out of that piece of code to power that city they would move that piece of code into a larger machine with a faster processor.

</details>

**主持人**: 垂直扩展只能让你走到这一步。

<details>
<summary>Original English</summary>

**主持人**: Vertical skilling only gets you exactly so far.

</details>

**Thuan Pham**: 所以我的职责也是做事，但也要在过程中教导人们。所以我只会向团队提出引导性问题，当时团队只有三四个人。所以我问工程师，“好吧，如果城市变得更大，你必须支持它，因为每个城市都在变大，乘车量越来越大，会发生什么？”然后他们说，“哦，是的，我们只是把它移到一个更强大的处理器上。”我说，“如果你能得到最快的处理器，会发生什么？”“哦，有多处理器，然后你可以得到一个四路盒子，然后你可以在上面放置多个这样的进程。”然后你说，“好吧，你有三四个这样的东西在服务同一个。它们会互相通信吗？它们共享相同的状态吗？”不完全是，对吧？所以它变得非常分区。

所以很快，通过提出这些引导性问题，工程师们就发现了这个东西无法扩展的缺陷，对吧？然后我必须确定“死胡同”的极限在哪里。我基本上问，“我们目前拥有乘车量最大的城市是哪个？”他们说是**纽约市**。我说，“好吧，**纽约市**什么时候会达到我们即使使用我们能找到的最大盒子也无法处理的容量？”大约是十月，而当时是五月。好吧，所以就像，“好吧，我们必须重写它，不是吗？”我们必须以一种真正可扩展的方式来编写它。我只有两个要求，我只需要这些。一是一个城市必须由多个盒子提供动力。

<details>
<summary>Original English</summary>

**Thuan Pham**: So my role also is to do thing but also to teach people along the way and so I would just asking leading question to the team and the team only have three people three or four people at a time and uh so I asked the engineer um okay what would happen if the city get larger and you have to support that because every city is getting larger the ride volume is getting larger and larger. Uh then entry base said, "Oh, yeah, we just we just move it to um a more powerful processor and say what happened if you get to the fastest process you can." Oh, there are multiprocessors and then you can get a four-way box and then you can put multiple of these processes on them and then you say, "Well, you got three or four of these things servicing same. Do they talk to each other? Do they share the same state?" Not really, right? So it become very partition. So pretty soon by asking those leading question, the engineer now discovered a flaw that this thing would not scale, right? And then and then I had to establish the limit of where is the brick wall and I basically said what's the biggest city uh do we currently have in terms of right volume and uh they say **New York City** and I said okay when is **New York City** is going to we can run our capacity even handle **New York City** even on the biggest box that we can get our hands on it's about October and this was around May okay and so it's like well we have to rewrite it don't we and we have to write it in a really scalable way And and I only have two requirement that I all I need. One is a city has to be powered by multiple boxes.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yes.

</details>

**Thuan Pham**: 一个盒子必须能支持多个城市。就是这样。所以你可以有N乘M。

<details>
<summary>Original English</summary>

**Thuan Pham**: And a box has to power multiple cities. That's it. So you can have N byM.

</details>

**主持人**: 你给了他们这两个限制。

<details>
<summary>Original English</summary>

**主持人**: You gave them these two constraints.

</details>

**Thuan Pham**: 不需要新功能。只需确保我们能做到这一点。然后这就能让业务、公司投入大量硬件，它就能扩展。从技术上讲，它会无限扩展。所以工程师们做到了。因为要求非常简单，我们必须在时间耗尽、生存空间耗尽之前，非常非常快地完成。所以他们做到了，我们实际上在八九月左右就部署了它，就在它真正发生之前。

<details>
<summary>Original English</summary>

**Thuan Pham**: No new feature necessary. Just make sure that we can do that. And then that allow the business the company to just pour a whole bunch of hardware behind that and it will scale. Technically it will scale infinitely right. And so the engineer did that and because the requirement is very simple we have to do it really really quickly before we run out of time uh run out of runway to survive and uh so they did that and we actually deployed that right around August September right before it actually

</details>

**主持人**: 然后下一个问题是数据库将成为下一个瓶颈，对吧？然后API单体将成为下一个瓶颈。我们不断识别所有这些问题。所以有所有这些威胁向我们袭来，我们必须确定我们还有多少时间，直到我们真正陷入严重的“星球大战”局面，无路可走，然后提前解决。

<details>
<summary>Original English</summary>

**主持人**: and then on to the next problem database going to be the next choke point right and then the API monolith is going to be the next choke point and we keep on identifying all these things uh so there's all these threat coming at us and we have to establish like how much runway we have until we like really getting serious Star War there's no way out and then get ahead of it

</details>

**主持人**: 所以这就是我们进行了多次重写的原因，我后来才加入，但重写仍在持续发生。我想当你加入时，你会问，为什么他们不能第一次就写好呢？但我想我是否理解正确，那是因为：a) 有时你只是为了解决你的问题而构建一个系统；b) 你并不总是知道它会发展到多大。一个很好的例子就是**纽约**问题。然后你接受这些限制，然后你构建一个系统，如果这些事情后来发生了变化，你可能需要构建一个不同的系统。

<details>
<summary>Original English</summary>

**主持人**: and so this was then the reason that we had so many rewrites I I joined later but rewrites were still continuously happening and I think when you come in you ask like why could have they not written it properly the first time or like but but I I guess do I understand correctly that it was because a sometimes you just build a system to solve your problem and and and b you don't always know how big this will say a good example is the the **New York** problem And then you take those constraints and then you build a system and then if those things change later you might need to build a different system.

</details>

**Thuan Pham**: 是的。这还取决于你增长的速度，这决定了你如何决策。因为你增长得越快，你生存的时间就越短，考虑到你目前拥有的架构和系统。是的，关于它可能增长到多大的问题，没有人真正知道。但对此进行推测实际上是没有意义的。是的，这一切都关乎我们还有多少时间可以活。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Um it also depends on how fast you're growing that dictate how you make and because the faster you grow the shorter runway you have to survive right given whatever architecture and system that you currently have. And yeah the the the question about how big it can possibly grow nobody knows really. But it's actually not fruitful to pontificate on that. Yeah. It was all about um how much time we have to live.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Thuan Pham**: 对。

<details>
<summary>Original English</summary>

**Thuan Pham**: Right.

</details>

**Thuan Pham**: 我们不能撞上死胡同，无路可走。对。所以，是的，如果时间真的很少，那就不要想太多。只要活下来，给自己足够的空间，然后活到再战一天，这就是我想说的。

<details>
<summary>Original English</summary>

**Thuan Pham**: We don't we hit the brick wall and it's no way out. Right. So yeah, and and if that time is really short, then don't overthink it. Just survive that and give yourself enough runway to then live to fight another day is what I like to say.

</details>

**主持人**: 像**Uber**那样快速增长对初创公司来说是个好问题，直到它不再是。快速增长带来的痛点是提及我们本季赞助商**Work OS**的好时机。如果你正在构建任何SaaS，尤其是**AI**产品，你会惊讶地发现你需要快速构建企业级功能，比如**SAML**边缘案例、目录同步、审计日志以及企业客户期望的所有功能。自己构建这些基础设施需要数月时间。**Work OS**提供API，让你在几天内就能交付。认证、SSO、SCIM、Arback、审计日志等等。所有这些都旨在直接集成到你的产品中。这就是为什么像**Anthropic**、**OpenAI**和**Cursor**这样的公司已经在**Work OS**上运行。跳过重复构建，继续交付。访问workhaw.com。

有了这个，我们回到**Thuan**的团队重写调度系统，以及这次首次重写给他们带来的短暂喘息空间。所以这就是调度系统，我们知道我们必须非常快地完成它，也许能为我们争取12个月。当我们度过那个阶段后，我们还有另外12个月来思考那个团队的下一个生存阶段。这就是为什么系统需要多次重写。假设我对工程师的要求是构建一个能够无限扩展、经受时间考验的系统，那可能需要一年时间。我们永远也达不到，在那之前我们就会死掉。

<details>
<summary>Original English</summary>

**主持人**: Growing fast like **Uber** did is a good problem to have for startups until it's not. And the pain points that come with fast growth is a good time to mention our season sponsor, **Work OS**. If you're building any **SAS**, especially an **AI** product, surprisingly, you reach the need to build enterprise features like **SAML** edge cases, directory sync, audit logs, and all the things enterprise customers expect quickly. Building that infrastructure yourself takes months. **Work OS** gives you APIs to ship it in days. Authentication, **SSO**, **SCIM**, **Arback**, audit logs, and more. All designed to integrate directly into your product. That's why companies like **Entrophic**, **OpenAI**, and **Cursor** already run on **work OS**. Skip the rebuild. keep shipping. Visit workhaw.com. With this, let's get back to **Tuan's** team rewriting the dispatch system and the short breeding space that this first rewrite gave them. So that's what with dispatch, we knew we had to do it very quickly, maybe by ourself another 12 months. And after we get through that point, then we have another 12 months to think about the next phase of survival for that team. That's why the system need to be rewritten several time. Let's say if my requirement for the engineer was build a system that will scale infinitely to the test of time, it might take a year. We never get there. We'll die before then.

</details>

### 中国市场：不可能的任务

**主持人**: 是的。说到在之前就“死掉”，你在2014年被赋予了一项看似不可能完成的任务。**Travis**告诉你，你有两个月的时间在中国上线。显然，在中国上线并不像简单地开放你的API和允许防火墙那么简单。那个项目是怎样的？我听说那是一个绝对疯狂的项目。你能带我们回顾一下当时的情况吗？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Speaking of of dying before, you were given in 2014 a seemingly impossible task. **Travis** told you you have two months to launch in China. And apparently launching in China was not as simple as just like opening your API and allowing the firewall. What was that project like? I heard it was an absolutely manic and crazy project. Can you take us back what it was like?

</details>

**Thuan Pham**: 是的，那确实是我们做过的最疯狂的事情之一，但也是最了不起的事情之一。我现在来解释一下原因。我记得非常清楚，大约在2014年圣诞节前后。我们都在1455号大房间里闲聊，**Travis**宣布：“好吧，新年一到，我就会点亮它，我们就要进入中国市场。”好的。然后他转向我，说：“我想要……”，当时的要求之一是，我们必须在中国本土运行我们的服务，对吧？数据中心必须实际在那里。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, that that was one of the craziest thing we've ever done, but it's also one of the most amazing thing we've ever done. Um, and now explain why so that that is so so I remember very very clearly right around Christmas time 2020 14. Uh we were all hanging out in the the the the the big room in uh 1455 and **Travis** made a declaration that okay come the new year I'm going to light it up and we're going to go into China. Okay. And then he turned over to me. It's like I want the uh and one of the requirement at the time was that we have to run our services on China soil, right? And data center physically there

</details>

**主持人**: 物理数据中心必须在那里。

<details>
<summary>Original English</summary>

**主持人**: physical data center needs to be there

</details>

**Thuan Pham**: 在那之前，我们有点像在浑水摸鱼，通过从美国提供动力来运行。好的。我们有时间限制来做这件事，但他就是要点亮它。我们就要做这件事。我说，他说：“两个月。”我说：“那真的很难。”他说：“为什么呢？我可以去机架上安装所有机器，然后复制软件过去，应该用不了两个月。”然后我不得不解释，这没那么容易，因为当你那样做时，它第一天能工作，然后两者就会漂移，你将如何维护它？我们没有两倍的工程团队来管理两个不同的、会偏离的系统。

<details>
<summary>Original English</summary>

**Thuan Pham**: Until then we kind of dabble in dirt water by powering it from from the US. Okay. And we have a limit of time um to do that but he's going to light it up. We're going to do that. And I said he's like two months. And I said well that's really tough. And he's like why is that? because I can go rack all the machine and copy the software over and shouldn't take more than two months and then I have to like explain that it it's not that easy because when you do that then it work on day one and then the two drift and how you going to maintain that right we don't have twice the engineering team to actually manage two different system that deviate

</details>

**主持人**: 所以正确的做法是，你需要构建、重新架构任何你需要做的事情，来构建一个可以分区的系统。我想这里存在巨大的安全问题，因为在那里运行的任何东西都不能假定拥有任何级别的隐私。但在我们这里，我们必须保护一切。所以我们必须构建一个具有完全数据和控制分区的相同系统，这样就不会有任何信息泄露。但每次你部署代码时，你都必须在所有地方都部署。所以你必须重建很多东西。

<details>
<summary>Original English</summary>

**主持人**: so the right way to do that is you build rearchitects whatever you need to do to kind of build one system that that can be partitioned right so I think there's a huge security concern right because there are anything that runs over there cannot presume to have any level of privacies or anything like that. Uh but over here we have to protect everything right. So we have to build that same system that has completely partition of data and controls and everything else so that yeah nothing bleed across but it has to be every time you deploy code you have to close everywhere right so you have to re rebuild a lot of things and

</details>

**Thuan Pham**: 所以我去了**TPM**团队，要求他们实际评估范围。我想……

<details>
<summary>Original English</summary>

**Thuan Pham**: uh so I went to the **TPM** team and asked uh the team to actually scope it out and I think

</details>

**主持人**: **TPM**，技术项目经理。

<details>
<summary>Original English</summary>

**主持人**: **TPM** technical program manager

</details>

**Thuan Pham**: 技术项目经理。我想对我们来说最好的方案是大约六个月，那已经是我们能想象到的最快速度了。我向业内的一些朋友征求意见，他们都嘲笑我，说至少需要18个月。但你知道，那是**Uber**，所以我们只是觉得，我们没想太多。我们想，好吧，那就做吧。然后**Travis**不喜欢六个月这个时间，所以我们折中了一下，定在了四个月。

<details>
<summary>Original English</summary>

**Thuan Pham**: Technical program manager and um I think the best path for us was about six months and that was the fastest we can even imagine I benchmarked with a few of my friends in the industry and they kind of laugh at me and it's like 18 months minimum thing. Uh but you know that was **Uber** so we just like we didn't think too much about it. was like well that that um let's do that and then driver didn't like the the six months so we kind of settle around four months right so and so

</details>

**主持人**: 因为他不喜欢…

<details>
<summary>Original English</summary>

**主持人**: because he didn't like

</details>

**Thuan Pham**: 我们只是折中了一下，我们什么都不知道，但我们只是想埋头苦干。所以我们看看，鉴于这是最终目标和要求，需要改变什么。然后每个人都开始非常忙碌，加班加点地进行这些修改。四个月过去了，我们仍然还差一个月左右，所以我们错过了冬季高峰，他对此不太高兴，但这没关系，对吧？然后五个月过去了，我们非常接近了，但还没到，我们又要延期了。所以，他当时肯定不高兴，但我们实际上谈了谈。我说团队非常有信心在一个月内可以上线，但他必须给我们一些东西，这意味着给我们一个增量上线的机会，而不是一次性点亮中国所有城市，让我们分阶段进行，对吧？每周我们上线一些城市，然后我们将在几周内完成，然后就结束了。他说：“好吧，这很合理，但他想要最大的城市先上线。”那就是**成都**。

<details>
<summary>Original English</summary>

**Thuan Pham**: We just split the difference we didn't know anything but we just want to heads down and start getting to it and so we look at oh what need to change given like this is the end u uh goal and the requirement and then with everybody start getting really busy uh working a lot of hours to stop making these changes and four months come and we are still a month or so short so we slip the winter trappers and he's not too happy about that but it's fine right and then uh five months comes around and we're very close but we're not there we're about to slip again and so uh it was not h definitely not happy then but we actually talk it out and I said the team feel very confident that within a month we can launch but he had to give us something that mean give us a ability to incrementally launch instead of lighting all the city in China oper once let let us do it in phase right every single week we'll launch a number of cities and then we're going to do it in a process of like a few weeks and then we're done with that and he said okay that's reasonable but he want the the biggest city first and that's **Chungdu**

</details>

**主持人**: 所以他同意增量上线，但你必须从最大的城市开始。

<details>
<summary>Original English</summary>

**主持人**: so he he agrees to the incremental launch but you need to start with the biggest

</details>

**Thuan Pham**: 从最大的开始，是的，完全正确。但那真是太棒了，你仔细想想。我后来想了很多，那真是最棒的事情，因为先做最难的事情，一旦你上线了，其他一切都迎刃而解了。团队有了这种自信，团队知道他们会带着信心进入下一批城市。如果我们按照传统方式，先从最安全的、最小的城市开始，然后逐步升级，表面上看起来是很好的风险控制措施，但我们每周都会提心吊胆，直到完成。但这次我们做了所有事情，先做最难的事情，之后就只是例行公事了。结果也确实如此。所以，是的，我们完成了，很多人都筋疲力尽，然后他们休息了一个月，去海滩，除了看海什么都没做。我知道有些人就是这样做的。但那之后，我们就不再害怕任何事情了，我们做到了看似不可能的事情。

<details>
<summary>Original English</summary>

**Thuan Pham**: Start with the biggest first yeah exactly but it it is brilliant though you think about it uh I I I thought a lot about that you know over time and that was the most brilliant thing because by doing the hardest thing first once you launch that everything else is downhill from there the team has this swag the team know would go into the next set of city with confident had we done the traditional way let's start with the safest one the smallest one first and next one we step it up on the surface it seemed like oh it's a very good risk control measure but every single week we'll be holding our breath until it's done it's not done right but this time we we did everything we and to do the hardest thing first and after that it just the routine process throughout the rest and that it worked out exactly like that and so yeah we got it done and a bunch of people were really burnt and then they took like a month off go to the beach and did nothing except stare at the water I know some other did that uh but after that though we're not fearful of anything we did like kind of the impossible and

</details>

**主持人**: 我和一个当时在IT团队工作的朋友聊过，他的工作就是物理地设置服务器。他说时间表太不可能了。我想他们从开始到结束只有两周时间。他们有一点时间计划，但他们当时就在现场。他们只是……当我收集那些参与其中的软件工程师的故事时，每个人都有自己不可能完成的任务和项目，他们都认为不可能完成，但不知何故，一切都成功了。

<details>
<summary>Original English</summary>

**主持人**: I I I I talked with a friend at who worked at the IT team at the time and his job was just to get the servers physically set up and he said that the timeline was so impossible. I think they had two weeks from start to finish. They had a little bit of time to plan but they were on the site. They were just and and when I gather the stories from the software engineers who worked on it, everyone had their own impossible task and project and they all thought it couldn't not be done and then somehow it all came together.

</details>

**Thuan Pham**: 完全正确。我们谁都不认为整个事情能完成，但我们只是埋头苦干，把它拆解开来，一步一步地完成。

<details>
<summary>Original English</summary>

**Thuan Pham**: That's right. None of us thought the whole thing that could be done, but we just got our head down and we just, you know, break it apart and just do it one step at a time.

</details>

**主持人**: 然后我想不用说，中国的上线取得了巨大的成功。**Uber**开始与领先的中国供应商**滴滴**正面竞争。他们几乎是正面交锋，竞争非常激烈，同时还在与世界其他地区竞争。

<details>
<summary>Original English</summary>

**主持人**: And then I think needless to say, but the China launch was a massive success. **Uber** started to compete head-on head with the leading Chinese provider **DD**. And they were is pretty much head-on head uh very intense competition all the while competing with the rest of the world as well.

</details>

**Thuan Pham**: 完全正确。是的。

<details>
<summary>Original English</summary>

**Thuan Pham**: That's right. Yeah.

</details>

**主持人**: 所以那真是不可思议。那真是不可思议。我想，仅仅是经历过这一切，做到了最初认为不可能的事情，就增加了每个人的信心和能力范围，这就是“拉伸”的意义。我想**Travis**喜欢说一句话，有时你必须愿意稍微“红线”一下自己，对吧？这就是你证明自己能做更多事情的方式，那就是他最初在公司中培养的无畏和冒险文化。

<details>
<summary>Original English</summary>

**主持人**: So that that was something incredible. That was something incredible and I think just the experience having gone through that and doing thing that initially you didn't think was possible just increases everyone's confidence and range and and that's what stretching all about and I think that there's a saying that **Travis** like to say that sometime you have to be willing to redline yourself a little bit right and that's how you you you prove that you can actually do a lot more than you can that was the fearlessness of the and the risk-taking culture that he won in the company in the first place

</details>

### 微服务与内部工具的演进

**主持人**: **Uber**从外部来看，非常出名的一点是微服务，而从内部来看，非常受关注的一点是“程序与平台分离”。你能告诉我们哪个先出现，以及我们是如何发展到拥有如此多微服务的？

<details>
<summary>Original English</summary>

**主持人**: one thing that **Uber** has been very very well known about from the outside is microservices and from the inside one thing that has been very talked about is a program and platform split. Can you tell us which one came first and and how do we get to as many microservices as we did?

</details>

**Thuan Pham**: “程序与平台分离”先出现。是的。微服务后来才出现。嗯，平台和程序平台作为一种组织结构，是出于必要性而首先出现的。当我2013年4月加入时，我们有40名工程师和3名产品经理。

<details>
<summary>Original English</summary>

**Thuan Pham**: The program and platform came first. Yeah. And microservices came later. Um and the platform and and uh program platform as an organizing structure came first out of necessity. When I came in April of uh 2013 uh we had 40 engineer and three product manager.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Thuan Pham**: 到那年年底，我们大约有100名工程师和十几个产品经理。即使在那样小的规模下，我们以职能型组织结构也陷入了停滞。想象一下，有大约八到十名移动开发人员，一些基础设施工程师，以及一群后端工程师等等。现在调度团队有五到八个人，但我们想要推出的每个功能都必须排队等待移动开发带宽和调度带宽，这使得权衡变得不可能，因为你想要做的每个功能都必须与这么多团队协商。所以团队想要快速行动，并立即感受到摩擦并抱怨。这很好，对吧？我们提出了担忧。

我记得**Travis**、**Jeff Holden**和我看到了这一点，我们实际上在一起待了几天。我记得我们有不同颜色的便利贴，每种颜色代表不同的职能：工程、产品、设计。我们把每个人的名字写在便利贴上，然后**Travis**谈论了他认为业务中最重要的领域。当时他能想到**Uber**世界可以涵盖的17个领域，结果远不止这些，但当时是17个。我们没有足够的资金来支持17个，我们有足够的资金来支持7个，外加几个，仅此而已。其余的可以空着，直到我们招聘更多的人并为其提供资金。所以这就是当时的情况。但在那个过程中，我们把便利贴贴到这些领域上，每个领域都必须是一个跨职能团队，因为我们不能再以职能团队的方式运作了。

<details>
<summary>Original English</summary>

**Thuan Pham**: By the end of that year um we had about a 100 engineer and a dozen or so product manager. Even at that really small size we ground ourselves to a halt with a functional or structure. Uh imagine a low tone engineer there about up to eight or 10 mobile developers uh a number of infrastructure engineer and a bunch of backend engineer etc etc and um five eight people or so at dispatch now but every feature that we want to put out has to be queued up on mobile development bandwidth dispatch bandwidth and it become impossible to navigate tradeoff because every feature you want to do you have to go negotiate with so many team right and so then the team want to move fast and start to feel that friction and complain right away. And that's a good thing, right? You know, we raised a concern. And so I remember **Travis** and **Jeff Holden** and I saw that and we got together for a couple days actually and I remember we had sticky note all the different colors each color represent a different function engineering product designer um and uh we put one person name to each of the sticky note and then **Travis** gave a talk about what are the most important area of the business that he think right and at the time they were like 17 area that he can think of the the world of **Uber** can cover 17 area turned out to be a lot more than that but at the time it was 17 we didn't have enough to fund 17 we had enough to fund seven plus a few more right so we fund seven uh with partially the next four and that's it and the rest can remain empty until we hire more people and we fund it and so that was the the the the thing but then as part of that process we then put sticky note onto each of these area has to be a cross functional team because we can no longer afford to run in no uh yeah cross function rather than a functional team.

</details>

**主持人**: 是的，这意味着有一个后端、一个移动端，以及他们需要的任何其他东西，比如设计等等。

<details>
<summary>Original English</summary>

**主持人**: Yeah, which means that there's like a back end, a mobile and whatever else they need like a design if they need to etc.

</details>

**Thuan Pham**: 概念是那个团队必须拥有所有必要的技能，才能完成任务。无论他们必须做什么，他们就去做。对吧？所以这就是那个决定背后的原则。然后我们把其中一些称为“程序”，另一些称为“平台”。所以“程序”是构建最终用户实际使用的东西的团队，而“平台”是构建其他程序团队使用的工具和层的团队。这就是所谓的横向与纵向。所以就是这样。然后我们定义了这些之后，就开始把正确的便利贴贴到那个盒子里，这就是第一版程序和平台的诞生方式。

<details>
<summary>Original English</summary>

**Thuan Pham**: That the the concept is that team has to have all the skill set necessary to just get it done. Whatever they have to do, they just go off and they do that. Right? So that was the the principle behind that decision and then we call some of those program and some of them platform. So programs are the team that build thing that the end user actually use and the platform are the thing that build tools and layer that other program team use and that was it sort of horizontal versus vertical kind of thing. So and that's that and and then after we define that then we start putting the right sticky note onto that box and then that's how the first version of programming and platform came about.

</details>

**主持人**: 那么微服务是如何开始的，它们又是如何发展到如此之多的呢？

<details>
<summary>Original English</summary>

**主持人**: And then how did microservices start and how did they blossom as much as they did?

</details>

**Thuan Pham**: 是的，同样，我们谁都不想走到那种极端，但在很多时候，当你面临巨大压力，除了生存别无选择，面对不断涌来的规模挑战时，你必须做出能够提高速度和效率的决定，因为速度和效率让我们能够足够快地构建以求生存。所以，我们立刻就知道后端API，也就是那个单体，是阻碍速度实现的东西。所以我们宣布：任何新的东西都必须在它之外构建。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, again um you know none of us wanted to go through that extreme but lots of time when you are under a lot of pressure and no time to react other than just to survive that scale that keep on coming at you, you have to make decision that increase speed and velocity because speed and velocity allow us to build quick enough to survive and so um we knew right away that the the backend API which is a monolith, right, is the thing that will prevent prevent speed from happening, right? So, we made a declaration anything that is new need to be built outside of that. Yeah.

</details>

**主持人**: 作为微服务。好的。然后有一个团队专门负责将那个单体，那个API单体，分解成一堆服务。

<details>
<summary>Original English</summary>

**主持人**: As a microser. Okay. And then there's a team that's dedicated to decompose that that monolith that API monolith into a bunch of services.

</details>

**Thuan Pham**: 是的。我们以前称之为API，对吧？我想……

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. We used to call it API, right? I think

</details>

**主持人**: 那就叫API，对吧？我想那个项目名称叫**Darwin**。

<details>
<summary>Original English</summary>

**主持人**: that's called API, right? And I think that project name is called **Darwin**.

</details>

**Thuan Pham**: 是的，**Darwin**。哦，我记得。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yes, **Darwin**. Oh, I remember.

</details>

**Thuan Pham**: 是的。有趣的是，如果我们冻结时间，那段代码可以在3到6个月内分解。但我们花了两年时间才做到，因为当我们剥离一段代码时，业务仍在不断向前发展，对吧？随着我们推出新城市，这些曲棍球棒式的增长现在相互叠加，而且发生得很快。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. And interestingly, had we freeze time, that piece of code could be decomposed in a matter of 3 to 6 months. But it took us 2 years to do that because as we peel out a piece of code, the business keep on going forward, right? These hockey sticks are laying on top of each other now as we launch new city and happening fast.

</details>

**主持人**: 新城市和新产品**Uber X**。

<details>
<summary>Original English</summary>

**主持人**: New city and new product **Uber X**.

</details>

**Thuan Pham**: 完全正确。功能必须不断添加，对吧？所以我们当时所有人的理念是，没有人应该阻碍其他人。没有人可以阻碍其他人。所以当一个团队需要构建一个功能，而那个功能还没有从单体中剥离出来时，他们就会把它添加到单体中，对吧？然后负责剥离的团队尽力而为，然后我们就像不断追逐自己的尾巴，直到最终，你知道，某个东西被完全剥离出来。结果，单体就像这样膨胀起来，对吧？因为你剥离了一个东西，剩下的东西增长得比你剥离的还要快。所以代码库越来越大，最终达到某个点，然后才开始缩小。这就是为什么花了两年时间，同时，所有新的东西都必须是自动的，因为我们不能继续向单体中添加东西。所以这就是它如何发展到数千个微服务的原因，但这都是出于必要性，这样我们才能分散开来，一次性解决所有问题。然后随着时间的推移，事情稳定下来，业务变得更加成熟，增长不再那么剧烈时，团队，我们实际上有一个叫做**ARC**的项目。我们可以审视这些东西，并思考如何清理它们。所以我们在一堆属于同一领域的微服务之上放置了领域接口。

<details>
<summary>Original English</summary>

**Thuan Pham**: That's right. Feature has to be added on, right? And so the philosophy we all operate at the time was no one should be blocking anybody else. No one can block anybody else. And so when a team that need to build a feature and that thing hasn't been pulled out of monolith, they add to the monolith, right? And then the team that pulls it out do the best that it can and then we kind of keep chasing our own tail until eventually you know something get completely pulled out and as it happened it bulges up like this the monolith right because you pull out one thing the remaining stuff grew even faster than the stuff that you pull out. So the code base get larger and larger eventually reach to a certain point when it start to come down and that's why it took two two years and meanwhile everything that is new must be auto because we don't keep on adding stuff right to to the monolith and so that's how it came up to to like you know thousands of microservices but that was out of necessity so that we can just fan out and solve every problem all at once and then over time after things stabilize and so the business more mature and growth is not as violent like that anymore uh then the team uh we actually have a project called **ARC**. We can look at this stuff and how do we clean it all up. So we put like domain interfaces on top a whole bunch of microservices that are within the same domain.

</details>

**主持人**: 这很有趣，因为我记得大约在2016年左右，**Uber**发布了一篇博客文章，说**Uber**大约有5000个微服务。几个月前我又看到**Uber**发布了另一篇，他们大约有4500个。所以在这十年里，数量缓慢下降了，对吧？

<details>
<summary>Original English</summary>

**主持人**: It's it's funny because I remember that around like 2016 or so there was a published **Uber** blog post that **Uber** had about 5,000 microservices and I just saw about a few months ago **Uber** published another one and they have about 4,500. So in that 10 years the number has gone slowly gone down right to go down but

</details>

**Thuan Pham**: 下降了，但即使如此，现在**Uber**的复杂性也大得多，对吧？是的，这个过程花了一点时间，但当团队必须审视所有事情并思考如何简化时，对吧？然后为了理解这些，我们必须发明新的工具，比如**Jager**（追踪工具）等等。所以那是非常棒的工具，我们将其开源了。

<details>
<summary>Original English</summary>

**Thuan Pham**: To go down but even then right now **Uber** has so much more complexity right yeah it's the process what took a little while but when yeah the team had to look at everything and how do we simplify that right and and then to make sense out of that the new tool has to be invented by us **gagger** the tracing tool all of that stuff and so that be really great tool that we open source to

</details>

**主持人**: 让我们谈谈**Uber**是如何以及为何构建了如此多的内部工具，并且还开源了其中一些。**Jager**就是其中之一，但在内部我们有**Schemaless**（一个旅行数据存储）、**T-channel**（RPC协议）、**Ringpop**（G空间放置）、**Clay**（服务框架）、监控和可观测性工具，还有数百个其他工具，有些是开源的，有些不是。

<details>
<summary>Original English</summary>

**主持人**: and let's talk about h how and why **Uber** built so much internal tools and also open source a bunch of them. **Jaker** was one of them but internally we had **schemaless** a trip data store **T channel** RPC protocol **ring pop** **g spatial** placing **clay** service framework you monitor observability and there's like hundreds of others some of them open some of them not

</details>

**主持人**: 你当时是如何考虑这些的？难道不觉得我们构建这些东西浪费了很多吗？还是说这又是出于必要性？

<details>
<summary>Original English</summary>

**主持人**: how were you thinking about that like does it not seem like a lot of waste for us to build this or was it again necessity

</details>

**Thuan Pham**: 大部分是出于必要性。我不能说所有这些东西都是绝对必要的，但所有重要的东西都是绝对必要的。事实是，当我刚开始在**Uber**工作时，我们几乎使用了所有开源的东西。我们使用**Redis**，我们使用所有东西，对吧？因为那里的工程师只专注于构建一个能移动汽车的服务。但后来随着我们规模化，我们不断推动这些开源工具的能力边界，直到它们达到临界点。在某个时候，如果我们不发明一些东西来满足我们自己的需求，顺便说一句，这是2013、14、15、16年，当时的技术还没有那么成熟。

<details>
<summary>Original English</summary>

**Thuan Pham**: It was mostly necessity I can't claim that every single one of those thing were absolutely necessary but all the important one were absolutely necessary the thing is when when I started **Uber** used pretty much all the open source stuff. We use **Reddis**, we use everything, right? Because those the engineer there just focus on putting together a service that actually move cars. But then as we scale uh we keep on using uh pushing the boundaries of the capability of those um um open source stuff and to the breaking point and at certain point if we don't invent something to power our own need. By the way, this is 2013, 14, 15, 16. It's not as mature as

</details>

**主持人**: 当时我们没有大型科技公司对开源的投入。很少有，而且大多数大型团队，比如**Google**和**Facebook**，都把他们的东西留在内部。

<details>
<summary>Original English</summary>

**主持人**: we did not have the kind of the big tech investment in open source back then. There was very little and and mo most of the big teams like **Google** and **Facebook**, they were keeping their inside.

</details>

**Thuan Pham**: 我记得一个非常痛苦的例子，我们早期不得不面对的，就是我们使用**PostgreSQL**。好的。我们达到了某个规模，**PostgreSQL**会随机崩溃，这会随机导致我们的服务停机，我们不明白为什么，它发生在内核内部。我记得当时我不得不在**LinkedIn**上恳求人们，任何了解**PostgreSQL**的人来做我们的顾问，帮助我们诊断这个问题。我们花了几个星期，在此期间非常可怕，因为我不介意我们认为我们可以解决自己的问题，但当我们遇到一个大问题，却依赖于别人，而且我们不知道，因为它是开源的，没有一个单独的人，没有一家单独的公司，我愿意支付任何费用，如果有人能给我一个答案，但没有人。

所以，那也是促使我们构建自己的数据层等等的动力之一，这样我们就可以使用这种通用数据库。我们最终使用**MySQL**作为表格数据存储，所有上层逻辑都必须为我们自己的用途而构建，对吧？因为那样我们就可以控制自己的状态，我们只构建我们真正需要的功能，对吧？所以那只是众多例子中的一个。

最终我们遇到了其他规模化瓶径。我记得在2015年假期前后，我正在度假旅行。我不得不去机场，我像往常一样乘坐了**Uber**。两天后才收到收据，对吧？为什么会这样？事情都在排队。我们处理事情的速度不够快，对吧？所以，是的，但这对于很多人来说并不是一个决定性的问题，因为他们只是乘车，然后收据晚点到也没关系，只要计费等等都正常，即使你晚点计费，他们也不太介意，对吧？但只要乘车发生了，其余的事情可以稍后处理，但这仍然不好。好的，当我深入研究时，我们的数据处理能力已经达到极限了，对吧？所以我们必须重写很多东西。然后我们的监控能力也达到了临界点，使用了我们使用的开源工具，所以**M3**必须被发明出来，所有这些东西。所以我们允许很多，我们不得不做这些事情，因为我们达到了一个规模，我们使用的所有开源工具都崩溃了。

<details>
<summary>Original English</summary>

**Thuan Pham**: I remember like for example a very painful example of that we had to face early on was we use **Postgress**. All right. and we get to certain scale that **postquest** would randomly fail and that take our services down randomly without we don't understand it's inside the kernel I remember the time where I had to go on **LinkedIn** begging people who anybody on **LinkedIn** that has any knowledge of **postgrad** to be our consultant to help us diagnose this problem and we spent several weeks and during that it was terrifying because I don't mind if we think we can do something of our own problem it's terrifying when we have a major problem and we depend on somebody else and we we don't know because it's open source there's no single person no some single company I'll be willing to pay anything if someone can give me an answer but there was no one right and so that was one of the motivator to kind of build our own you know data layers and all of that stuff as well so that we would use this generic database and we end up using **MySQL** just as table data store all the logic on top we have to build for our own use right because then we control our own state and we only build the feature that we really need, right? And so that was one of many example and eventually we run into other brick wall of scaling. I remember in 2015 right around the holiday I was taking a holiday trip. I had to go to the airport and I I took an **Uber** ride as usual. The receipt didn't come for 2 days after that, right? Why is that? Things were queuing up. We weren't processing things enough, right? And so yeah, but that's not a dealbreaker for many people because they just ride and then receipt come later. is fine as long as the building and all the stuff even when you build people late they don't really mind that either right but as long as the right happened the rest of stuff can be processed later but it's still not great okay when I dug into it like our data processing capability is at capacity right so we have to rewrite a bunch of stuff and then our cap ability to monitor things is reaching a breaking point with the open source tool that we use so the **M3** has to be invented right and all of that stuff so we we allow lot of we had to do thing because we at the scale where we broke all the open source stuff that we use

</details>

### Project Helix：Uber应用重写

**主持人**: 在**Uber**，我们做了一些不寻常的事情，其中最不寻常的项目之一，也是你我相遇的地方，当我加入**Uber**时，它在内部被称为**Helix**。它完全重写了**Uber**的应用。据我所知，当时**Uber**的用户体验开始下降，因为它变得非常混乱。**Travis**对此有点厌倦了。设计团队提出了一个解决方案，一个非常漂亮和干净的UI，工程团队看了之后，发现这将是一个完全的重写。然后我们就真的进行了完全重写。我记得当时我们有一两百万行代码。我们有两三百名移动工程师在做这个。这是一个庞大的业务，而且设定了一个极其紧迫的截止日期。你能带我们回顾一下，我们为什么要做这个？

<details>
<summary>Original English</summary>

**主持人**: At **Uber** we did unusual things one of the most unusual projects which is where you and I met when I joined **Uber** was called internally called **Helix** it was completely writing **Uber's** app and as I understand what happened is **Uber's** user experience was starting to degrade because it was really cluttered got a bit fed up with it the designer team came up with a solution which was a very nice and clean UI which kind of the engineering team looked at it and it would have been a full rewrite And then we just did a full rewrite. Back then I remember we had a million or two million lines of code. We had two or 300 mobile engineers working on this. This was a massive business and there was an extremely tight deadline set. Can you take us back on why did we even do this

</details>

**主持人**: 因为从内部来看，它感觉像是一种生存威胁，但它不像**Google+**与**Facebook**那样的生存威胁。我们是如何决定那个短期限的？

<details>
<summary>Original English</summary>

**主持人**: because from it didn't feel it felt existential threat from the inside but it was not like uh like a plus versus uh versus **Facebook** existential thing. And how did we decide on that short deadline?

</details>

**Thuan Pham**: 是的。嗯，似乎有一个反复出现的主题，就是紧迫的截止日期，对吧？我们做的每件事都有紧迫的截止日期。就是这样，这就是文化运作的方式。我们想做的任何事情都想尽可能快地完成。

但回到为什么要做**Helix**，实际上**Travis**有一个愿景，而且实际上不仅仅是设计师，**Travis**和当时的设计主管**Yuki**，他们合作，他们做了所有的故事板等等。所以他有一个愿景，认为当时现有的应用程序限制太多了。是的，它很好，按一个按钮就能叫到车，所有这些都很好。但如果你想让更多的服务接入其他东西，比如消息功能等等，当人们乘车时，新的架构允许它更加开放，对吧？对所有这些东西。所以这就是那个愿景背后的原因。然后当我们做这个的时候，美学非常重要。图标变化，所有这些东西都变化了。哦，是的。所以，但那确实是，是的，它很漂亮，那实际上是**Travis**和**Yuki**，对吧？他们当时……然后当然，当它具体化到一定程度时，工程团队，移动团队就参与进来了，而且不仅仅是移动工程师，后端也必须全部重写。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Um it seemed like a recurrent theme that keep on coming up was a tight deadline, right? Everything we do had a tight deadline. It's just it's yeah it just that's just how the culture role. Um anything we want to do want to do as fast as we can. Um but going back to uh why **Helix** um actually **Travis** has a vision right and it's actually not just the designer **Travis** and **Yuki** who was the lead designer at the time they pair up and they all the storyboard and everything else. So he has a vision where the current app back then was too limiting. Yeah, it's really good. Push a button, get a ride, all that stuff. But if you want more services to hook in other things, right, messaging and all these other things as people were riding, uh the new architecture allow it was much more open, right, to all those things. Uh and so that was the the vision behind that. And then when we're doing that, the aesthetic is really important. The icon change and all of these things change. Oh, yeah. And so but that but that is yeah it's beautiful right that's actually **Travis** and **Yuki** right they were and then of course when when that fleshed out to a certain amount um then the engineering team the mobile team get involved and it's not just the mobile engineer the back end had to be written to everything

</details>

**主持人**: 我们从每5秒轮询一次的心跳机制，改成了实际的推送通道，这过程相当痛苦。

<details>
<summary>Original English</summary>

**主持人**: we we we changed from uh the heartbeat where every 5 seconds we would pull and it was pretty painful to an actual push uh push channel

</details>

**Thuan Pham**: 是的，这部分，那时它被称为实时系统，对吧？是的，它必须改变后端，必须改变所有东西，以支持新的流程和所有这些东西。所以，是的，我不知道，总共花了六七百名工程师七八个月的时间才完成，然后我们把它推上线，它至今仍在运行，仍然基于相同的架构。它考虑得如此周全，几乎是面向未来的设计，所以至今仍在被使用，至今仍然很漂亮。如果你把它和之前的版本比较，它确实是正确的选择。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah this part with that by by that time it's called real time system now right yeah it has to change back end has to change everything has to change to port the new flows and then all that stuff and so yeah it it took I don't know 6 700 engineer all told 7 8 months to actually do it then we put it off and it still live today it's still on that same architecture it was so far well thought out it's almost like future proof in that design so it's still used today it's still beautiful today and if you compare that with the previous version it actually was definitely the right

</details>

**主持人**: 是的，而且它具有可扩展的用户体验。

<details>
<summary>Original English</summary>

**主持人**: yeah and it was scalable user experience

</details>

**Thuan Pham**: 我对此不居功，这就像是**Travis**和**Yuki**的才华。

<details>
<summary>Original English</summary>

**Thuan Pham**: I take no credit in that it's like the genius of **Travis** and **Yuki**

</details>

### 团队文化与管理哲学

**主持人**: 你时不时会向所有工程师发送关于不同事情的邮件，我记得你发过一封非常非常感性的邮件，是关于命名规范的。

<details>
<summary>Original English</summary>

**主持人**: you every now and then sent emails to all of engineering on different things and I remember this really really emotional email coming from you uh about naming.

</details>

**Thuan Pham**: 我看到了所有这些，我理解年轻工程师想找乐子。

<details>
<summary>Original English</summary>

**Thuan Pham**: I see all this and I understand that young engineer want to have fun.

</details>

**主持人**: 我们当时玩得很开心。

<details>
<summary>Original English</summary>

**主持人**: We were having fun.

</details>

**Thuan Pham**: 是的。用一种滑稽的方式命名事物。我想那封邮件的触发点是一个名为**Mustafa**的服务。我完全不知道那是什么。我看着那些东西，那时我们已经非常复杂了，对吧？我们必须不断地吸纳新工程师。我们希望构建者能快速上手等等。我可以想象一个工程师进来，如果所有这些奇怪的名字都没有上下文，当时我们的工具也不是那么好，对吧？**You blame**还没有出现，对吧？所以没有映射让人们发现这到底意味着什么，然后那些我们重命名方案。所以我到了有点受够了的地步，所以我发了那封邮件。当然，你知道，那些群发邮件有时你发出去后会后悔，因为它产生了一些影响，但它并没有真正解决问题。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. And name things in a goofy way. I think the trigger for that was a service named **Mustafa**. I have no idea what it is. Right. I look at that stuff and and by that time we were already very complicated, right? And we had to onboard new engineer all the time. we want builders to ramp up quickly etc etc and I can imagine an engineer come in here and if all these weird name have no context to it uh at the time our tooling wasn't that great either right you blame didn't come into existence yet right and so there's no mapping for people to discover what this really mean and then those we renaming scheme so I got to the point where I'm kind of fed up so I send that email out of course you know those mass emails sometimes you regret after you send it out because it has some effect but it didn't really solve

</details>

**主持人**: 我想那句话被广泛引用，因为你特别写道：“这不是一个米老鼠商店。”

<details>
<summary>Original English</summary>

**主持人**: and I I think it very quoted because you specifically wrote this is not a **Mickey Mouse** shop.

</details>

**Thuan Pham**: 完全正确。我们不是米老鼠。是的，那是一个成长的阶段，对公司里的每个人都是。但那是我当时的挫败感，就是看看在这个规模下，我们必须认真对待自己。我们必须做得更好、更快，而这并没有帮助。

<details>
<summary>Original English</summary>

**Thuan Pham**: Exactly. We're not **Mickey Mouse**. We and and yeah, it was uh again it was it was a growing up phase for everyone in the company. But it was it was my frustration at the time was look at at this scale inside we got to take ourselves seriously. We got to do thing better faster and this is not helping.

</details>

**主持人**: **Thuan**一直在谈论随着组织规模的扩大而改进事物，例如转向更成熟的命名策略。随着公司的成熟引入新的、更好的方法，这很好地引出了我们的赞助商**Statsig**。**Statsig**构建了一个统一平台，既支持实验又支持持续交付。内置的实验功能意味着每次发布都会自动成为一个学习机会，通过适当的统计分析，准确显示功能如何影响你的指标。功能标志让你能够自信地持续交付，向10%的用户推出，及早发现问题，并在需要时立即回滚。由于它是一个集所有功能于一体的平台，拥有相同的产品数据，你的组织中的团队可以协作并做出数据驱动的决策。他们提供了一个慷慨的免费层级供你开始使用，专业团队的价格每月150美元起。要了解更多信息并获得30天企业试用，请访问stats.com/pragmatic。

有了这个，我们回到**Thuan**。我们开始使用更好的命名。另一件在行业中对**Uber**来说非常独特，并引起外部很多困惑的事情是**Uber**的资深级别。有一段时间，**Uber**有一个常见的资深工程师级别，叫做L5。然后，在某个时候，你和领导团队将其分成了两个：L5A和L5B，即资深一和资深二。你能告诉我们你为什么这样做，以及这个想法是从哪里来的吗？

<details>
<summary>Original English</summary>

**主持人**: **Tuan's** been talking about improving things as the orc scales such as moving to a more mature naming policy. Introducing new and better approaches as the company matures leads us nicely to our presenting sponsor **stats**. **Statseig** built a unified platform that enables both experimentation and continuous shipping. Built-in experimentation means every roll out automatically becomes a learning opportunity with proper statistical analysis showing you exactly how features impact your metrics. Feature flags lets you ship continuously with confidence, roll out to 10% of users, catch issues early, roll back instantly if needed. And because it's allin-one platform with the same product data, teams across your organization can collaborate and make datadriven decisions. They have a generous free tier to get started and pro pricricing for teams starts at $150 per month. To learn more and get a 30-day enterprise trial, go to stats.com/pragmatic. With this, let's get back to **Tuan**. We we started to do better names. One other thing that was very very unique to **Uber** across the industry and it caused a lot of confusion from the outside is **Uber** senior level. For a while **Uber** had a senior engineering level called L5 which is common and then at some point you were the leadership team cut it into two. There was L5A and L5B senior one senior 2. Can you talk us about why you did that and where did you get the idea from?

</details>

**Thuan Pham**: 我做了那个。我对此不道歉。我认为当时那是一个好举动。原则是，我们希望人们成长，但我们对**资深工程师**级别有非常明确的定义和期望，因为我们以**Google**、**Facebook**等所有优秀公司为基准。

<details>
<summary>Original English</summary>

**Thuan Pham**: I did that. I'm I'm not apologize for it. I think it was a good move at a time. Um and the the the principle was we want people to grow right but we have a very clear definition and expectation of what it is at the staff engineer level because we benchmark ourselves to all the great company out there **Google**, **Facebook** and all that

</details>

**Thuan Pham**: 然后我意识到，对于许多工程师来说，从初级工程师到资深工程师，再到**高级工程师**，可能需要五年的时间。好吧，那是一段漫长的时间，所以我只是想把它分成两部分，这样人们就能感受到进步，而且也不是每个人都能成为**高级工程师**，对吧？但有些人能成为**资深工程师**就足够了。

<details>
<summary>Original English</summary>

**Thuan Pham**: and then I realized that for many engineer crossing from senior engineer I mean um engineer two pass through the senior engineer to get staff it could be a fiveyear journey. Okay, it's a long time and so I just want to break it in two so that people get that sense of progress and then also not everybody can make it to staff, right? But some people it's good enough to make it to senior

</details>

**主持人**: 资深二。是的。

<details>
<summary>Original English</summary>

**主持人**: senior too. Yeah.

</details>

**Thuan Pham**: 我认为那是有益的。不是说不这样做，然后每个人都迷失在那五年的旅程中。是的，所以这就是背后的动机。所以你看到了一个问题，然后这是一个解决方案，而且它奏效了，我们可以这么说，对吧？

<details>
<summary>Original English</summary>

**Thuan Pham**: And I think that's a benefit. It's not right but versus like not doing it and everybody kind of just get lost in that five year you know journey. Um yeah and so that was the the motivation behind that. So you saw a problem and then this was a solution and it it it worked we can say right

</details>

**Thuan Pham**: 它奏效了一段时间，对吧？然后人们适应了，然后他们开始抱怨，说：“哦，为什么有两个级别？我们需要更快地达到**高级工程师**级别。”然后我在那里的时候，我坚持了这一点，因为我是一个负责人，而**高级工程师**是与行业中最好的公司相比较的。

<details>
<summary>Original English</summary>

**Thuan Pham**: It worked for a while right and then people were acclimatized to that and then they start complaining it's like oh why there's two level we need to get the staff faster and then while I was there I held on to that because I was a principal and staff is staff compared to the best of the industry

</details>

**主持人**: 后来我离开后，我想它……

<details>
<summary>Original English</summary>

**主持人**: u and later on after I left I think it got

</details>

**Thuan Pham**: 他们被降级了，L5B现在是**高级工程师**，所有级别都被降级了。

<details>
<summary>Original English</summary>

**Thuan Pham**: re they got pushed down L5B is now staff everything got pushed down

</details>

**主持人**: 通货膨胀。我不想搞这种职称通货膨胀。

<details>
<summary>Original English</summary>

**主持人**: inflation and I I didn't want to do a cytoin inflation thing.

</details>

**主持人**: 我很欣赏这一点。我记得你发过的另一封邮件是在2016年，你写道你听到了反馈，说工程师们不开心，因为他们的经理不支持他们。然后你写道，我们正在创建一个简单的内部调岗流程。你可以调换团队。这封邮件反响如何？你又是如何决定我们需要这样做的？

<details>
<summary>Original English</summary>

**主持人**: I I I appreciate that. Another email that I I remember from you is in 2016 you sent an email saying you've heard the feedback that NGS are unhappy because their managers not support them and then what you wrote is like we are creating an easy internal transfer process. You can move teams how how was that received and again how did you decide that we need to do this?

</details>

**Thuan Pham**: 我审视了人才库，我认为对我们来说最好的是为人们创造机会，让他们在公司内部通过新的挑战不断成长，因为如果我们不这样做，他们就会离开公司去寻找。然后我想到下一个合乎逻辑的步骤是，如果人们来找我们，只是辞职，他们在面试时没有告诉我们。

<details>
<summary>Original English</summary>

**Thuan Pham**: I look at um the talent base and I think it is best for us to create opportunity for people to keep on growing with fresh new challenges within the company because if we don't do that they would leave the company and seek uh and then I thought about the next logical step which is hey if people come to us and just resign they didn't tell us when they interview.

</details>

**主持人**: 是的。那么我们为什么要搞这些严格的流程，当你必须征求经理的许可才能去另一个团队时？是的。我们为什么要给自己制造麻烦呢？对吧？当我们的工程师从A团队到B团队时，必须征求所有这些许可，而如果他们去外面面试，他们就不必征求许可。是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And so why the heck do we have like these rigorous process when you have to ask your manager for permission to go to another team. Yeah. Why do we make it harder for ourself right when our own engineer go from team A to team B have to ask for all these uh you know permission where they don't have to ask if they interview outside. Yeah.

</details>

**主持人**: 那根本说不通。

<details>
<summary>Original English</summary>

**主持人**: That just doesn't make any sense.

</details>

**Thuan Pham**: 基本上，在外面面试更容易，或者说以前在外面面试更容易。所以那对我来说没有任何意义，所以我说，“好吧，我们不要那样做。”对。那也可能有一个好的副作用，就是经理现在需要被激励去关心员工，好好培养他们，让他们成长，你知道，把最优秀的人放在最适合他们成长的时间点，然后他们就不太可能离开自己的团队，对吧？如果他们继续成长的话。所以所有这些，你知道，那种反向压力可能会让工程师经理们也更负责任一些。所以就是这样，我记得那受到了相当大的阻力，因为它在当时会相当激进，但我们还是做了。所以那结果证明是正确的举动，对吧？我宁愿人们互相信任，当一个工程师想走的时候，他们应该和他们的经理保持非常好的关系，他们只是和经理谈谈，“嘿，你看，我想做这个。”经理应该普遍支持，而不是说“不，你属于我”那种错误的做法。

我有一句话，我总是和你们分享：这不是监狱。我们不能把任何人锁起来，对吧？每个人都有自由意志。如果他们想在某个地方工作，他们就应该有能力去做。而且我们应该创造更多的机会，然后我们也应该支持这一点。我们发布内部招聘板，对吧？外面能看到的，我们在内部也能看到。所以任何人都应该能够在公司内部的所有机会中选择，并留在公司。为什么要把它弄得那么难，最终导致他们离开公司呢？那真是愚蠢。

<details>
<summary>Original English</summary>

**Thuan Pham**: Basically it's easier to interview outside or it was easier to interview outside. So that didn't make any sense to me and so I said well let's not have that. Right. And that also has maybe a good side effect where manager now need to be incentivized to take care of people great develop them grow them you know put position the best people into the best time for them to grow and then they not like to leave their own team right if they continue to grow. So there's all of that you know that back pressure might cause engineer managers to be a little bit more responsible too. So that was that and I remember that get quite a bit of push back because it would be pretty radical at the time you but we just did it anyway and so that that turned out to be the the right thing to move right and I would rather people trust each other and when an engineer want to go they should have a really great relationship with their manager where they just talk to man hey look I'm I'm I want to do this and the manager should be generally supportive instead of like no you belong to me that kind of thing which is the the wrong thing I have a saying that I share with you guys all the time It's not a jail. We can lock anybody down, right? Everybody have free will. If they want to work, you know, somewhere, they should have the ability to do that. And we should create more opportunity and then we also to support that. We publish internal job board, right? Anything on the outside see we see on the inside. So any should be able to shop within all the opportunity have inside the company and stay with the company. And why make it so hard and end up leaving the company? That's just a silly thing.

</details>

**主持人**: 我记得在**Uber**的一些会议上，无论是全体会议还是团队会议，你都会发表一些令人难忘的演讲，其中最令人难忘的，我问过以前的**Uber**员工，**Charles**特别告诉我，他对你最深刻的记忆是关于这个演讲或这个话题，即从死亡的角度看待工作。

<details>
<summary>Original English</summary>

**主持人**: I remember at **Uber** in in some of the the meetings either all hands or team meetings you you gave talks that were memorable and one of the most memorable I I asked around former **Uber** folks and **Charles** specifically he was on the podcast he told me that his most vivid memory of you is this talk or or this topic about behaving work in the perspective of death.

</details>

**Thuan Pham**: 是的，我不记得那个确切的演讲，但我脑子里一直有那种想法，对吧？有时我会根据不同的情境与不同的听众分享，但它归根结底是关于找到自己的目标，而不是把自己看得太重，对吧？如果你看看那些最成功的人，他们并不会把自己看得那么重，对吧？你知道得越多，你就越知道自己不知道什么。而那些傲慢的人往往是知识不足，或者他们必须……所有这些，对吧？所以，是的，我总是抓住机会提醒人们要谦逊，我总是用我自己作为例子，对吧？我说，你看，当你身居要职时，人们对你很好，但不要让这冲昏头脑，那不是你，那是你所处的职位。我记得我说过这样的话，就像我不再是“盐”的那一刻，对吧？而那总是会发生的，对吧？世界会忘记我们，对吧？所以我们真正能做的，就是在我们做的任何工作中，尽力帮助彼此，给彼此留下持久的积极印象。总有一天，一切都会结束，工作会结束，然后我就会想到更多的事情，比如生命本身也会结束。所以那时我衡量自己，我最引以为傲的成就是什么？我说，好吧，当我离开时，我最引以为傲的是有多少人记得我曾经对他们很好，或者帮助过他们，并且持续了几年，对吧？这就是，因为我什么也带不走。所以活在当下，尽力对每个人都好，尽可能地建设性，并且留下一个好的遗产。所以这就是那个演讲的全部要旨。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, I don't remember that exact speech but I I do have that line of thought in my head all the time right and sometimes I would share with different audience with different context but it is um it's all about finding one's you know purpose and not take oneself too seriously right if you look at uh people the most accomplished people don't take themselves that seriously right the more you know the more you know you don't know kind of thing and people who are arrogant tend to like not know enough yet or they have to all that right so um yeah so I always take opportunity to remind people to sort of be humble and the example I use always is use myself right I say look you know when you're in an important position people treat you really well but don't let that get to your head it's not you it's the position you hold and I remember saying this like the moment I stop being salt right And that's always happened, right? The the world forget about us, right? So the only thing we can really do is in any job that we do, do the best that we can to help each other to leave a lasting positive impression in each other. And one day everything ends a job end and then I'll get to the mor stuff like life even end itself. And so then I measure my myself like what is my achievement that I will be most proud of? And I said, well, when I'm gone, the thing I'm most proud of is how many people remember how I was good to them or helpful to them and for some number of years, right? And that is that because I can't take anything with me. And so live in the moment, be as best as you can to everyone and be very as constructive as you can and and and leave a good legacy behind you. So that that that was a whole gist of that.

</details>

**主持人**: 我有时觉得，人们总是在谈论如何更好地拓展人脉，但听起来这几乎不是一种技巧。这只是做好工作，对吧？

<details>
<summary>Original English</summary>

**主持人**: It it feels to me sometimes there's talk about how you can network better and grow your network, but sounds like this is almost like it's it's not a hack. It's just do the work, right?

</details>

**Thuan Pham**: 做好工作，然后正确的事情就会发生，对吧？但你不能为了那个目标而工作，因为那非常做作，对吧？只要真诚，做你自己，乐于助人，建设性地，提升每个人，一路帮助人们，无私地指导你。让我再告诉你一个角度，我个人一次又一次地经历过。不仅仅是行业中的其他人把你拉入好的事情。当你被拉入，却没有支持你成功的人，你也不会成功。

这里有一个**Uber**的例子，当我加入时，工程团队非常年轻，缺乏经验，不知道如何构建可扩展、可靠的系统，所有这些。而我拥有的网络中，真正知道如何做到这一点的人来自**VMware**。他们构建系统软件，我们构建操作系统。对。严格的首席工程师级别，所有……

<details>
<summary>Original English</summary>

**Thuan Pham**: Do the work and then the right thing happen, right? But you can't do the work in service of that goal because that's very artificial, right? Just be genuine, just be yourself, be helpful, be constructive, uplift everybody, help people along the way, coach you being doing it altruistically. And let me tell you another angle too which I personally experienced over and over again. It's not only that other people around the industry pull you into good stuff. When you pull in and you don't have people to support you succeed, you would not you would not succeed also. And here is an example at at **Uber** right when I came in uh again the engine we talk about very very young in experience did not know how to build system at scale reliable all that stuff and the network that I have who really knew how to do that was from **VMware**. You're building system software. We're building operating system. Right. Rigorous principal level engineer all

</details>

**主持人**: 经验。不，就像他们睡着了也能做到一样。对。

<details>
<summary>Original English</summary>

**主持人**: experience. No like in their sleep they can do it. Right.

</details>

**Thuan Pham**: 对。所以当我进来，当我必须与团队合作处理调度系统时，我从**Uber**调来了第一位工程师加入那个团队。对。他叫**George**。所以他在那里，他为其他人工作，或者提升那里的每个人。对。然后……

<details>
<summary>Original English</summary>

**Thuan Pham**: Right. So when I came in and when I have to like um work with the team on dispatch I pull in the first engineer from **Uber** to to lean land on that team. Right. His name is **George**. And so he there and he work for everybody else or uplift everybody there. Right. That and then

</details>

**主持人**: 来自**VMware**。

<details>
<summary>Original English</summary>

**主持人**: from **VMware**.

</details>

**Thuan Pham**: 是的。是的。是的。是的。然后当我构建支付系统时，我们又调来了几个。然后当我们构建**Schemaless**时，那是一个丹麦团队，对吧？我从我的**VMware**团队中调来了四名顶尖工程师，我把他们从丹麦的一层楼搬到了另一层楼。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Yeah. Yeah. Yeah. And then when I build payment system, let's pull in another a few more one. And then when we get to build **schemalas**, it was a Denmark team, right? I pulled the top four engineer from my **VMware** team in that I moved them down from one floor to the next in Denmark.

</details>

**主持人**: 这就是为什么我们有一个丹麦办公室，这是正确的，它是**Uber**最好的基础设施办公室之一。

<details>
<summary>Original English</summary>

**主持人**: This is why we had a Denmark office which was correct which was one of the best infrastructure offices at **Uber**

</details>

**Thuan Pham**: 他们构建了**Schemaless**。

<details>
<summary>Original English</summary>

**Thuan Pham**: and they built **schemalist**.

</details>

**主持人**: 他们构建了**Schemaless**。他们构建了许多其他……

<details>
<summary>Original English</summary>

**主持人**: They built **schemalist**. They they built a lot of other

</details>

**Thuan Pham**: 对。所以现在如果我不是一个好人，没有为他们做好工作，或者和他们一起工作，那他们为什么要来呢？

<details>
<summary>Original English</summary>

**Thuan Pham**: right. And so now if I weren't a good person doing a good job for them with them or what why would they come?

</details>

**主持人**: 是的。他们不会接电话的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. They would they wouldn't answer the phone.

</details>

**Thuan Pham**: 是的。他们不会接电话，对吧？但我打给的每一个人，因为我真的需要帮助，他们都来了。最初他们都问同样的问题：“为什么要做出租车公司？”但当他们理解后，他们就来了，对吧？但他们来是因为他们仍然喜欢和你一起工作。对吧？有些人已经和我一起在五家不同的公司工作了28年。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. They wouldn't answer the phone, right? But every single one that I call because I really needed help, they all came. Initially they all asked the same question. Why taxi company? But when they understand that they came, right? But they came because they still enjoy working with you. Right? There are people who work with me for five different company over 28 years.

</details>

**主持人**: 这总是让我感到惊讶，我认为这是人们在建立办公室时或我与创始人交谈时可能会忽略的一点：一件事是你可以在哪里招聘，另一件事是优秀的人可以在哪里长期留下来，这其中有很多价值。丹麦一直是非常核心的关键基础设施。

<details>
<summary>Original English</summary>

**主持人**: And that always surprised me and I think this is something that people might overlook a little bit as they're building out offices or I'm talking with founders is one thing is where you can hire the other thing is where people where the good people stay for a long time and there's a lot of value in that and Denmark kept being very core critical infrastructure.

</details>

**Thuan Pham**: 是的。核心基础设施软件团队，这也是我们在**Uber**必须构建的东西之一，因为当时我加入时，我们没有构建基础设施软件，对吧？我们只是使用现有的开源工具，对吧？我们构建了那个。我沿途发现的另一件事是，优秀的人才无处不在，但你必须为他们带来机会。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. core infrastructure software team and that's one of the thing we had to build at **Uber** because back then when I came in we didn't build infrastructure software right we just use existing open source stuff right and we built that and another thing that I you know uh discover along the way is great talents are everywhere but you know you have to bring opportunity to them

</details>

**主持人**: 他们不一定会从丹麦搬到旧金山，对吧？所以这就是为什么我们最终在全球有九个工程办公室，因为我们有很多工作需要完成。我们去其他地方不是为了节省成本，而是因为我们有需求，我们有世界级的人才，我们只是挑选世界级的人才，无论规模大小。丹麦团队与印度等地的团队相比规模较小。但你知道，那里有真正优秀的基础设施人才，我们会在那里投资。立陶宛，我们有很棒的**DevOps**团队。所以我们只是去人才所在的地方，然后我们把伟大的工作带给伟大的人才，然后我们建立一个结构来管理，并赋予人们对问题的一流所有权，然后，你知道，每个人都是平等的。

<details>
<summary>Original English</summary>

**主持人**: they don't necessarily relocate from Denmark to San Francisco right and so that's why we end up having nine engine offices around the world y because we have a lot of work need to be We didn't go to other places because of cost savings like that. We go there because we have need and we have world class talent and we just cherry pick the worldass talent doesn't matter what size it is and Denmark team was small compared to team in India etc. But you know there would really great talent infrastructure and we'd invest on that. **Lithuana** we had amazing **DevOp** uh team and so we just go to where the talent uh is and then we bring the great work to the great talent and then then we establish a structure uh to manage and give people first class ownership of the problem and then you know everybody is kind of equal.

</details>

### 三次“服役期”与职业生涯的终结

**主持人**: 在**Uber**，你多次谈到你的“三次服役期”。它们是哪些？

<details>
<summary>Original English</summary>

**主持人**: At **Uber** you you talked about several times of your three tours of duty. Which ones were these?

</details>

**Thuan Pham**: 是的。同样，这又回到了目的。所以当我做某事时，我试图有意识地思考我为什么要做某事？我做这件事的目的是什么？所以当然，我加入**Uber**的目的是，嘿，让我们建立这个业务。我只是构建支持业务的技术。所以最初的几年，18个月，24个月，都在修复很多损坏的东西。系统不可靠，变得更可靠等等。重建事物。基本上只是让事情运作起来，并且运作良好。然后随着时间的推移，你知道，这些事情不会在某个特定的日子结束和开始，它只是逐渐进入和退出。所以第二阶段，我称之为我的第二次服役期，是全球规模化。那是中国，那是各个维度的大规模扩展。所以，是的，在每个阶段结束时，你都会问自己，我还有用吗？我是否想重新投入我的承诺、精力和所有其他东西？所以前两个阶段是毫无疑问的，对吧？我们就是为了做那个。

然后当第二阶段即将结束时，大约在2017年，我们实际上已经稳定下来了。我们现在非常庞大。我当时确实在问自己这个问题，我还需要留在这里吗？我实际上打算在那个夏天结束我的工作，因为，你知道，那时我们还有另一位更高级别的**STP**。我认为他在技术上非常非常出色，我感到非常安心，你知道，有个人能做得更好，因为那个人在**Google**做过更大的事情，对吧？是的，但后来那没有成功，然后**Uber**经历了一个非常艰难的一年。所以那时我不得不让自己投入到第三次服役期，那就是，它的目的是什么？你知道，帮助公司度过动荡的岁月。我当时不知道那个阶段何时会结束，我只是知道它结束的条件，那就是下一任CEO上任时，对吧？然后在那之后，那个人是否喜欢我，我是否喜欢那个人，或者其他什么，那有待决定。但第三阶段我必须坚持下去，因为，你知道，我们欠自己，也欠所有一路走来构建**Uber**的人，度过那个动荡的阶段。所以我们做到了，然后当新的CEO上任时，你知道，我一直留到了2020年。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Again, it it come back down to purpose. Uh so when I do something, I try to be intentional about why am I doing something? What's my purpose of doing that? And so of course my purpose to come into **Uber** was, hey, let's build this business. I just build a tech that support the business. And so the first couple year, 18 months, 24 months were fixing a lot of the broken stuff. Things weren't reliable, become more reliable, etc., etc. Uh rebuild things. um basically just get thing to work and work well and then along the way you know these things don't end and beginning on a particular day it just phase in and out right so the phase two uh that what I call my second tour of duty was scale worldwide scale that was China that was massive scales everywhere in every dimension uh and so yeah so at each of those phase when you're done with that phase you ask yourself am I still useful do I want to re-up right my commitment and energies and everything else. And so the first two phase were no question, right? We're there to do that. And then as phase two were about to wrap up, right, uh about 2017, we actually kind of stabilized. We're really big now. I was actually asking myself that question, do am I need it here anymore? And I was actually about to wrap it up that summer because, you know, at that point, we had also another **STP** that was higher. And I think he's really really great technically and I can like feel very very at peace kind of you know there's there's someone who really take it on even better cuz the person has done even bigger thing at **Google** right yeah and then but that didn't work out and then **Uber** has a really rough year so then I have to like sign myself up to the third tour of duty which is and what is the purpose of that you know help the company get through the turbulent years and I had no idea at the time when that phase would end I just kind of know the condition for that to end which is whenever the next CEO arrive right and then after that whether that person like me I like that person or whatever it is that's to be decided but that third phase I have to stick it through because you know we owe it to oursel and we owe it to everyone along the way who have built **Uber** to that point right to to get through that turbulent phase. So we did that and then uh when the new sale come in and you know I stayed on until 2020

</details>

**主持人**: 然后在2017年，我记得那一年非常动荡。**Travis**不得不暂时卸任。一个由14人组成的团队，他们是**Travis**的直接下属，接管了公司的领导权。你就是其中之一。所以这就是你决定，如果一切顺利，你可能就离开了。但你决定留下来帮助公司，帮助团队，帮助我们度过难关。**Uber**是由成千上万的人构建的，对吧？过去和现在。那些在某个地方构建然后离开的人，那很好。他们的工作仍然以某种方式存在，对吧？这导致了我们现在拥有的**Uber**。那是一件非常重要的事情，我们所有人都构建了它，那也是我们许多人的生命。

<details>
<summary>Original English</summary>

**主持人**: and then in in so in 2017 I remember it was really turbulent. **Travis** had to step down for a while. A group of of I think 14 people who were **Travis's** direct reports. They took over steering the company. You you were one of them. So this is the point where you decided that if everything would have gone smooth, you might have actually just left. But you decided to stay on to help the company, help the team to help us get through. **Uber** was built by tens of thousands of people, right? Past and present. The fact that people built somewhere and then left before I that's so fine. They that work was still in there in some way, right? That led to that **Uber** that we have there. And it was a really important thing that we all built that that many of our lives were.

</details>

**主持人**: 然后，为了熬过去，我们上市了，这进展顺利。然后，一切都还不错。然后当然，疫情发生了，这真的打击了**Uber**。疫情爆发几个月后，你就辞职了。你为什么离开**Uber**？为什么选择那个时机？是什么促使你决定：“好吧，是时候离开了”？

<details>
<summary>Original English</summary>

**主持人**: And and then just to suck it up, we went public, which which which went good. And then it it it went okay. And then of course **CO** happened which really hit **Uber** and a few months later in into **CO** uh you did step down. Why did you leave **Uber** and and why why was the timing what it was and what motivated you to say okay this is the time to to go?

</details>

**Thuan Pham**: 是的，那真的与疫情无关。你知道，我很幸运能达到人生的一个阶段，金钱不再重要，对吧？所以那时我问自己，如果我每天醒来都要花X小时做某事，我为什么要这样做而不是做其他事情？所以归结为三件事：第一，我是否真的热爱这项使命和我在做的事情？第二，我是否觉得我的存在正在产生真正大的影响？第三，我是否享受与我共事的人的陪伴？对吧？如果这些维度中有几个缺失，那么在某个时候，整体上就不再令人愉快了，对吧？那么，那时就会想到，好吧，当你醒来，每周花50小时做某事，而金钱不再重要时。我生活非常节俭，所以这不会改变任何事情。所以，那时我为什么要这样做而不是做其他事情呢？所以我想那就是当时我意识到，我更多的是在那里做一份大工作，但或多或少只是在管理事务，而不是像早期那样更有效地建设公司。所以在那时，我认为让其他人来尝试这份工作会更好。你知道，就像一切都会结束一样，对吧？所以你必须自己决定。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, it it didn't have anything to do with co really. it you know I was I'm lucky enough to arrive at a point in life where money doesn't matter right and so then I asked myself why am I doing anything if I wake up every day and spending x number of hours on doing something why would I do that versus something else and so it come down to three things one is do I really love the mission and what I'm doing and the second one is do I feel like my being anywhere there right is making a really big impact. And the third one is am I enjoying the company of people I'm working with? Right? And if several of those dimensions are lacking then at some point is not enjoyable in totality anymore. Right? Then uh then it come down to okay when you wake up and you spend 50 hours a week doing something where money doesn't matter anymore. Uh I live very modestly so it doesn't doesn't change anything. So uh then why would I do that versus doing some other thing? And so I think that was that was the the realization at that point where I'm more like okay I'm there doing a a big job but more or less running things rather than you know being very uh much more effective and building the company like in the early days and so and at that point I think it's actually much better for other people who take a crack at that job again it you know like everything ends right and so you have to decide yourself at

</details>

**主持人**: 而且它确实给了其他人机会，对吧？所以，他们也接手了。现在，离开**Uber**后，我记得你接受了一次采访，你好像说你在考虑退休，或者你会看看情况。但你并没有就此止步。哦，不。你做了其他事情。**Coupang**、**Nubank**、**Fair**。我们能谈谈发生了什么吗？你的想法是什么？你甚至一刻都没有真正离开过。

<details>
<summary>Original English</summary>

**主持人**: and it did give opportunity to other people right so like and and they did pick it up now After **Uber**, I I remember you did an interview uh with a with a publication. I think you said that you're thinking of retiring or you'll see. But then you you were not done. Oh, no. You you did other stuff. **Kong new bank fair**. Can can we talk about what what what happened? What was your thinking? And you never even left for for a moment, honestly.

</details>

**Thuan Pham**: 嗯，我把这归咎于疫情。所以，说真的，疫情与此息息相关。当我离开时，我们计划整个夏天都去旅行，因为我们的女儿正处于八年级和九年级之间，即将进入高中。我们计划了非洲野生动物园之旅，还有所有其他旅行计划。

<details>
<summary>Original English</summary>

**Thuan Pham**: Well, I blame that on **CO**. So, seriously, that one co had everything to do with it. Uh so when I left um we had um a plan to travel the entire summer because my our daughter was between eighth grade and ninth grade when she's about to enter high school. We had African safari plan. We have all the other travel plan.

</details>

**主持人**: 一切都被关闭了。

<details>
<summary>Original English</summary>

**主持人**: Everything got shut down.

</details>

**Thuan Pham**: 一切都被关闭了。所有航班都被取消了，所有国家都关闭了，所以我们被困在家里。是的。

<details>
<summary>Original English</summary>

**Thuan Pham**: Everything got shut down. All the flight get cancelceled all the country clothes and so we stuck at home. Yeah.

</details>

**主持人**: 对。我记得当时我是一个人去超市，然后非常稀疏地快速采购，拿上你需要的东西就出来，戴着所有口罩。

<details>
<summary>Original English</summary>

**主持人**: Right. And I don't remember at the time where I'm the only one who go to supermarket to and then then like very very sparse to kind of race through it, pick up what you need and you get out with all the mass and

</details>

**Thuan Pham**: 是的，所以我们有点无聊。所以我很无聊，我坐在家里，我们都通过视频**Zoom**通话，很多人都想和我聊聊，这并不奇怪。所以我接了很多电话，其中一个就是**Coupang**的创始人。我们聊得很愉快，你知道，他是一个充满干劲的人，想做很多事情，我真的很喜欢这一点。我想，反正我在这里也没事做，不如让自己有用起来，对吧？这又是关于你如何利用时间的问题。所以，是的，我做了，我加入了那里，我提供了一些帮助，但我也学到了很多，因为那也是一个非常有趣的领域，对吧？亚马逊式的物流，而**Coupang**的做法是，你谈论的是五六个小时的配送。

<details>
<summary>Original English</summary>

**Thuan Pham**: yeah and so uh we kind of bored though and so I I'm bored so I sit at home and we all got on video uh **zoom** call and uh lots of people want to kind of chat with me uh to um not surprising and so I took a bunch of call and one of them was the the founder of **coupon** and we had really great chat and you know it's like hard charging person want to get a lot of thing done and I I really like that and I I think well I'm not doing anything here anyway so might as well you know make myself useful right again it's about how you spend your time and so yeah as I did that and I um yeah I I joined there and I helped some but I learned also a ton because that's also a very interesting area right of **Amazon** style logistic and the way **coupon** does it is you talk about 5 hours 6 hours delivery

</details>

**主持人**: 哇。

<details>
<summary>Original English</summary>

**主持人**: Wow.

</details>

**Thuan Pham**: 是的。你在午夜前下单，东西会在早上5点送到你家门口。5点。我在那里的时候，我加入了送货卡车，在凌晨两三点把包裹放在人们家门口，这真是太棒了，对吧？所有这些你学到的东西，你学到了很多很多。所以，是的，在当时的情况下，这真是充分利用了时间。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. You order before midnight and the thing show up in your doorstep 5:00 in the morning. 5 and I when I was there I joined the delivery truck putting packages in front of people's home like 2 3:00 in the morning and it's it's brilliant right and all those thing that you learn and you you you learn a whole bunch of these thing and so yeah it's a really great use of time right given the circumstances.

</details>

**主持人**: 是的。然后你成为了**Nubank**的顾问还是董事会成员？

<details>
<summary>Original English</summary>

**主持人**: Yeah. And then you became was it is it an adviser or a board member at **Newang**?

</details>

**Thuan Pham**: 董事会成员。是的。**Nubank**对于那些不了解它的人来说，在美国或欧洲以外，它是最成功、估值最高的非美国公司，是拉丁美洲增长最快的银行。它非常极端。它的工程文化。我听到了很多关于它的惊人之处。你是第一个我实际谈论它的人。那么，你在那里学到了什么？你现在还在参与，对吧？

<details>
<summary>Original English</summary>

**Thuan Pham**: Uh board member. Yeah. And **New Bank** is for for those that don't know and outside of the US or Europe, it is the most successful and highest valued non US companies, the largest growing bank uh in Latin America. It's it's it's extreme. It's as it's engineering culture. I hear amazing things about you're the first person I'm actually talking about. So, what what did you learn there? And and you're still involved, right?

</details>

**Thuan Pham**: 是的。是的，我仍然参与其中，但以董事会成员的身份。有一段时间，我还承担了更积极的责任，指导了几位CTO。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Yeah, I'm still involved, but as a in a as a board member capacity. Uh and for a while I I also took on a more active responsibility to mentor the Cto right a couple of them.

</details>

**Thuan Pham**: 所以，是的，我再次强调，这一切都关乎有用。我们在旅途中学到了很多，与真正聪明的人、真正有动力的人一起工作，他们更年轻，我们传授知识，分享你所看到的和建议，帮助人们更好更快地前进。我发现这非常充实。所以，就是这样。那里的文化非常活跃。我的意思是，它让我想起了我们**Uber**的早期，每个人都充满干劲，创始人也充满干劲，每个人都充满干劲。当我访问那里时，通常是在董事会会议期间，我们每年都会去巴西一次，我们会与整个公司举行全体会议，有时我也会与工程团队举行全体会议，并进行问答环节，就像我们在**Uber**做的那样。所以它非常充满活力，对吧？他们的非凡成功有很多因素。其中之一就像**Uber**一样，他们实际上在正确的时间解决了正确的问题。

<details>
<summary>Original English</summary>

**Thuan Pham**: And so yeah and so I I again it's all about being useful. Um we all learn a lot in our journey and working with really smart people, really motivated people younger and impart that knowledge and sharing you know what you see and advice help people move forward better faster and and I find that very fulfilling and so so that uh was that and the the culture there is very vibrant. I mean it remind me of our early days **Uber** when everybody is gung-ho hard charging the founders hard charging everybody is when I visit there uh usually during board meetings uh once a year we kind of go down to Brazil uh and we will have all hands with the with the entire company and sometime I also did all hands with the engineing team and do **AMA** style the way we did **Uber** and so it's just very energetic right and and there there many factor to their phenomenal the success one is like like very much like **Uber** they actually solve the right problem at the right time

</details>

**主持人**: 在**Nubank**出现之前，有大量没有银行账户的人口，他们提供了跨越传统银行的在线和应用程序服务，体验非常棒，NPS（净推荐值）得分非常高，最终它为人们的生活增加了大量价值，这就是为什么采用率如此之高，对吧？所以，是的，执行得很好，产品愿景惊人，文化和活力非凡，所有这些因素在伟大的公司中都非常常见，我们在**Uber**早期也经历过类似的事情。所以能成为其中一部分，真的让人重新充满活力。

<details>
<summary>Original English</summary>

**主持人**: there's a whole bunch of unbanked population before **new bank** came along and they deliver like leapfrog of traditional banking just online and the app and the experience is beautiful the **NPS** score is through the roof and it it ultimately it add a lot of value to people right live and that's why the adoption rate is crazy high right and and and so yeah well executed um amazing product vision and phenomenal cultures and energy and all those factors are very common in like great companies and we experienced one of those thing at **Uber** too in early days. So it's really re-energizing being a part of that

</details>

### Fair：B2B市场与AI应用

**主持人**: 然后他们做得很好，现在你是**Fair**的CTO。是什么让你加入了**Fair**？

<details>
<summary>Original English</summary>

**主持人**: and and and they're doing great and now you're the CTO at **fair**. What made you join **fair**?

</details>

**Thuan Pham**: 我休了几年假，当时我女儿正在读高中，因为我觉得她离开后，那段时间就永远回不来了。现在她已经走了。

<details>
<summary>Original English</summary>

**Thuan Pham**: I took a couple years off when my daughter was finishing high school because I figured that time would not ever come back when she's gone and she's gone now.

</details>

**主持人**: 那是正确的选择吗？

<details>
<summary>Original English</summary>

**主持人**: What was it the right choice?

</details>

**Thuan Pham**: 哦，绝对是。我不会后悔那段时间。所以那……

<details>
<summary>Original English</summary>

**Thuan Pham**: Oh, absolutely. I would not take that time back. So that

</details>

**主持人**: 嗯，是的，我很高兴。

<details>
<summary>Original English</summary>

**主持人**: um yeah, I'm so glad.

</details>

**Thuan Pham**: 是的，十年级、十一年级和十二年级，我得以待在家里，送她上学，接她放学，做饭，你知道，一起玩，帮助她申请大学，所有这些。所以我们之间的感情非常好。当我想到她要去上大学时，我在想，“哇，我会有很多空闲时间，我该做什么呢？”

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, 10th, 11th grade, and 12th grade, I get to stay home, drop her off, pick her up, cook, you know, hang out together, help with college application, all of that stuff. And so the the bond we had was really cool. And as I was thinking about her going to college, I was thinking, "Wow, I'm going to have a lot of time on my hand, so what should I do?"

</details>

**主持人**: 又来了。

<details>
<summary>Original English</summary>

**主持人**: Here we go again.

</details>

**Thuan Pham**: 完全正确。所以，我应该加入另一个董事会吗？我当时正准备这样做。然后在最后一刻，**Sequoia**的一些合伙人让我去见**Max**，**Fair**的CEO。我真的很喜欢他，他非常聪明，同样具备所有相同的特质：非常聪明，非常有冲劲，想做所有正确的事情。这个业务是赋能本地企业。

<details>
<summary>Original English</summary>

**Thuan Pham**: Exactly right. And so should I join another board, which I was about to. And then at the last minute some partner **Seoya** asked me to meet **Max** uh the CEO of there and really liked him very smart again all the same characteristic very smart uh very hard charging want to all the right thing the businesses empower you know local you know businesses

</details>

**主持人**: 我们能稍微谈谈这个吗？因为从外部来看，你知道，当你搜索**Fair**，你和我看到它时，它并没有告诉你太多。它感觉像……

<details>
<summary>Original English</summary>

**主持人**: can we talk a little bit about that because from the outside you know when you **Google fair** and you and I look at it it doesn't tell you exactly too much feels a

</details>

**Thuan Pham**: 它是一个B2B市场，连接着大品牌批发商和零售商。所以人们购买商品，然后补充他们的店面。所以，是的，所有传统的双边市场动态都适用。使命与我们的使命非常相似，尽管我们是B2C，而这是B2B，但这一切都是关于我们能做些什么来赋能本地企业蓬勃发展，对吧？所以购买正确的东西，通过销售盈利，发展业务。

<details>
<summary>Original English</summary>

**Thuan Pham**: It is um it is a **B2B marketplace** right between uh big brand wholesalers and retailers up. So people buy that and then uh stock their storefront and and so yeah and so all the traditional two-sided marketplace dynamic apply and the mission is very similar to our mission rub even though we are **B toc** right this is **B2B** but it's all about what can we do to empower local businesses to flourish right so to buy the right thing to sell through make a profit grow that business

</details>

**主持人**: 所以基本上这可以帮助小型和大型企业真正发展他们的业务，无论是……

<details>
<summary>Original English</summary>

**主持人**: so basically this can help small and also large businesses to actually just like grow their business may may that be like

</details>

**Thuan Pham**: 更成功的需求，更多的需求，更多的供应，所有这些，对吧？所以，是的，这就像一个真正的……

<details>
<summary>Original English</summary>

**Thuan Pham**: more successful demand, more demand, more supply, all of that stuff, right? So, yeah, it's like a really

</details>

**主持人**: 市场非常有趣，也非常复杂，所以我真的很喜欢。

<details>
<summary>Original English</summary>

**主持人**: market place is really fun and very complex and so I really like that

</details>

**Thuan Pham**: 我真的，当我深入研究，通过面试过程和所有其他事情时，这家公司再次行动非常快，一周内所有事情都完成了，包括我的家庭作业，对吧？我必须去展示所有东西。所以我真的，这家公司行动非常快，充满活力，文化非常好，非常友善，你知道，没有政治。每个人都专注于做正确的事情，互相合作，互相照顾。所以，这是一个三合一。无论公司是大是小，对吧？但它具备了所有要素。所以我想，好吧，也许那是一个加入并提供帮助的好地方。

<details>
<summary>Original English</summary>

**Thuan Pham**: and I really when I dig in uh through the interview process and everything else and again this company moved really fast within a week everything was finished including my homework assignment, right? I have to go and present and everything else and so I really the company moved really fast. is energizing and the culture is super nice and super kind, you know, like no politics. Everybody's just focused on doing the right thing and working with each other, taking care of one another. So, it's a trifecta. Doesn't matter if the company is really big or really small, right? But it's got all the ingredients. So, I was like, well, maybe that's a good place to jump in and help out help out.

</details>

**主持人**: 你能给我们介绍一下**Fair**的背景吗？包括公司规模、工程团队规模、主要中心在哪里，以及工作方式是怎样的？是现场办公还是混合办公等等？

<details>
<summary>Original English</summary>

**主持人**: And can you give us a little context on **fair** in terms of the size of the company, the size of the engineering team, where the hubs are, what the what the work is like? Is it in person? is is is it hybrid and so on?

</details>

**Thuan Pham**: 是的，公司大约有1000人。工程团队，包括数据科学团队，总共大约300人。我们每周三天在办公室工作，是的，每周三天，另外两天是远程在线工作。是的，如果有人住得离办公室近，他们会来得更多。嗯，是的，工程团队，旧金山这里有一部分，就在这条街的下面，还有很大一部分在加拿大，我们在**Waterloo**有一个大办公室，在多伦多也有一个大办公室。所以我经常去那里出差。每五六周左右我就会去一次。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, the company is about a thousand person. The engineing team including the data science team combined is about 300 people. The work we are in the office three days a week um yeah three days on the week that the other two on um are working remotely online for yeah and some people show up more if they live close to the office. Um yeah uh the engineering team uh there's a a portion here in SF um just down the street from here and uh a large part is in uh Canada uh then we have a big office in water and we have a big office in uh Toronto. So I I make the trip there quite often. Every five six week or so I'm over there.

</details>

**主持人**: 那么你现在正在解决的哪些有趣的工程挑战让你感到兴奋？

<details>
<summary>Original English</summary>

**主持人**: And what are some interesting engineuring challenges that you're excited about right now that you're solving?

</details>

**Thuan Pham**: 哦，现在最令人兴奋的事情显然是**AI**，以及**AI**如何如此迅速地改变一切。告诉我，你看到了什么？在你的团队中，哪些是有效的，哪些是无效的？

<details>
<summary>Original English</summary>

**Thuan Pham**: Oh uh right now clearly the most exciting thing is **AI** and how is **AI** changing everything so quickly. Tell me h how what what are you seeing what's working what's not at you know like in on your teams

</details>

**Thuan Pham**: 在我的团队以及公司内部，我们正在使用**AI**来提升每个人的效率、生产力和产出，对吧？所以这是其中之一。在工程方面，我们特别使用**AI**来改进搜索和推荐，对吧？因为整个工作就是帮助人们发现那些能很好地销售给企业的东西等等。想象一下**AI**作为一个购物顾问，所有这些东西。然后在编码方面，**AI**现在正在做更多的编码工作。嗯，但我们也使用了不同的技术来实际提升工程生产力。你听说过**swarm coding**吗？

<details>
<summary>Original English</summary>

**Thuan Pham**: In my team as well as in the company you know we're using **AI** to boost everyone yeah effectiveness and productivities and output right and so so that's one within the engine specifically we use **AI** to make you know search and recommendation better right because the whole job is to help people discover thing that would sell really well for the business and etc and imagine **AI** as a shopping consultant right and all this stuff and then coding wise you know **AI** is doing a lot more of of the coding now um but we also used uh different technique to actually boost uh engineering productivity um you have you heard like **swarm coding**

</details>

**主持人**: 所以，**swarm coding**是指代理吗？

<details>
<summary>Original English</summary>

**主持人**: so so **swarm coding** as an agents

</details>

**Thuan Pham**: 是的，一大群代理，对吧？

<details>
<summary>Original English</summary>

**Thuan Pham**: yeah a whole bunch of a swarm of agent right

</details>

**主持人**: 它相当新颖，所以你们已经在使用了？

<details>
<summary>Original English</summary>

**主持人**: it's it's pretty new so you're already using it

</details>

**Thuan Pham**: 所以我们已经在使用了，我们正在构建协调器来协调所有这些代理的行动。我们衡量了第一批早期采用者，然后我们构建了更强大的工具后，大部分工程师也跟进了。我们看到了早期采用者在工程产出上的显著提升，那些以这种方式思考效率很高的人，对吧？因为它与线性思维非常不同，当我编写这段代码时，现在它几乎就像多线程编程是单线程的，对吧？你必须考虑所有这些其他事情，你必须提示所有行动，然后所有这些代码都会回到你这里，你必须审查它，你坐在一起。是的。它需要一种不同的思维方式，认知负荷可能会高一点，但产出是巨大的，我们看到我们最优秀的工程师的产出翻了一番。

<details>
<summary>Original English</summary>

**Thuan Pham**: So we already using it and we we building orchestrator to orchestrate the action of all this agent and uh we measure the the first the early adopters um the and then the the the bulk of the engineer follow through after we build the the more robust tooling and we see dramatic lift in engineering output among the early adopter the the one are really efficient at thinking this way right because it's very different from a linear kind of thinking when I write this piece of code right now it's almost like multi-threaded programming was single threaded right you have to think about all these other thing you have to prompt all the action and then you have all this code come back at you and you have to review it you sit together. Yeah. And it it required a different way of thinking and the cognitive load might be a little higher but the output is dramatic and we have seen our best engineer double their output.

</details>

**主持人**: 我知道我们正在谈论这个，但为了明确，我们谈论的不是代码产出，而是实际的业务产出，是他们工作的影响，对吧？

<details>
<summary>Original English</summary>

**主持人**: I I know we're talking about that but just to make it clear we're talking about not the code out but the actual business out but the impact of their work right

</details>

**Thuan Pham**: 是的，影响。现在取决于**AI**的演变，对吧？所以现在最先进的技术是，大规模的改变非常容易，对吧？清理等等，对吧？所以生产力大幅提高。现在我们正在努力突破下一个前沿，那就是如何在这种旧代码库之上构建新功能时，也能达到这种生产力提升和产出水平，对吧？它不像，“哦，你我可以去构建一些全新的、不与任何东西纠缠在一起的东西。”那会非常快。整个东西都会为你生成，对吧？是的。但我们有数百万行代码，你如何处理这些，并在所有这些依赖关系之上构建功能，对吧？**AI**现在是否足够好，可以帮助我们一路解开一些这些东西，构建新的东西？所以我们实际上，你知道，继续在这方面努力，并找出如何继续通过**AI**提升更多的生产力，即使是构建新功能。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah the impact uh now depend on the the evolution of **AI** right so right now the state uh of the art right now is it's very easy to make large scale changes right clean up and everything else right so massive productivity increase now we're trying to crack the next frontier which is how we get that level of productivity increase and output building new features on top of a code base that are older, right? It's not like, oh, you and I can just go build something brand new, not entangled with anything. It's really fast. The whole thing will generate for you, right? Yeah. But we got millions of lines of code and how do you like deal with that and build feature on top with all those, you know, dependencies and all that stuff, right? Can **AI** good enough now to help us untangle some of those thing along the way building new thing and so we actually, you know, continues to work on that and figure out how we can actually continue to boost uh more and more productivity out even building new feature with **AI**.

</details>

**主持人**: 你认为**AI**将如何改变软件工程，以及软件工程师的工作内容和我们重视的技能？

<details>
<summary>Original English</summary>

**主持人**: How do you think **AI** will change software engineering and what a software engineer does and what skills we value?

</details>

**Thuan Pham**: 是的。它已经在改变了。我的意思是，变化非常迅速。这些变化比我见过的任何东西都令人着迷，包括互联网。对。那时我记得当我们第一次学习如何编程时。我们必须了解很多关于机器架构的知识。我们必须了解虚拟内存。我们必须了解，然后我们必须学习语法和编码。所有这些东西现在都被抽象掉了。对。尤其是**AI**。就像我想要X、Y和Z，它应该这样，整个东西都被构建出来了，对吧？所以它提升了竞争环境，让那些甚至不知道如何编程的人现在也能创造出好的，你知道，好的体面的代码和应用程序，或者其他什么，表面上看起来都很好。所以它改变了游戏规则，对吧？它提升了竞争环境。那么在这种抽象的层面上，你如何区分优秀的工程师和普通的工程师呢？

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. Uh it's already changing. I mean very rapidly fast. These changes are fascinating anything I've ever seen including the internet. Right. Back then I remember when we first learned how to um do programming. We have to know a lot about the machine architecture. We have to know about virtual memory. We have to know and then we have to learn how to like syntax and coding. All of that stuff been abstracted away now. Right. Especially **AI**. It's like I want X Y and Z blah and it should be this way and whole thing get constructed right so it elevated level the playing field where people who don't even know how to program can now create good you know good decent code and app or whatever it is that look on the surface are really good. So it is gamechanging right it it um it elevates the playing field. Now then in that level of of abstraction, how do you tell the great engineer from the good engineer?

</details>

**主持人**: 很好的问题。你如何……

<details>
<summary>Original English</summary>

**主持人**: Great question. How do you

</details>

**Thuan Pham**: 嗯，从我们目前看到的情况来看，优秀的工程师仍在寻找方法来利用这一点，并进一步加速产出。然后我们看到优秀的工程师和普通工程师之间的差异仍然是两三倍的能力。他们更爱探索。他们更处于前沿，他们更具创新性，对吧？然后有些人会说，“好吧，这是你给我的工具，我会提高两倍的生产力，对吧？因为我正在使用这个工具。”这很棒。但优秀的工程师会继续突破新的边界。所以我认为这仍然是可行的。你仍然可以观察人们，看到谁是高绩效者，谁是普通人。

<details>
<summary>Original English</summary>

**Thuan Pham**: Well, from what we see so far, the great engineer are still finding way to leverage this and accelerate the output even more. Then we see the difference between the great engineer and an an average engineer is still two 3x in terms of their capability. They're more inquisitive. they're at the bleeding edge more, they're more innovative, right? And then there are people who like, okay, well, here's the tool that you give me, I'm going to be two times more productive, right? Because I'm using this tool. It's great. But the great angel continue to break new boundaries. And so I think that is still available. You can still you can look at people and you can see who are the high performer versus who are average.

</details>

**主持人**: 那么我是否理解正确，你所看到的优秀工程师的特质是，我们没有提到，但它是一种既定的基础，再加上好奇心和创新？

<details>
<summary>Original English</summary>

**主持人**: So do I hear correctly that the with the traits that you're seeing in G engineers is we didn't mention but it's kind of a given the foundations plus curiosity plus innovation

</details>

**Thuan Pham**: 无畏，愿意创新，愿意拓展，愿意尝试新事物，开辟新天地，所有这些特质仍然存在。

<details>
<summary>Original English</summary>

**Thuan Pham**: Fearlessness willing to innovate willing to stretch willing to try new things and break new ground all of those traits that's still exist

</details>

**主持人**: 有趣的是，如果我回想**Uber**时代或你创业的日子，那些特质就是……

<details>
<summary>Original English</summary>

**主持人**: interesting if I think back to like just the **Uber** days or your startup days that those traits were kind of the traits of the

</details>

**Thuan Pham**: 突出的人。完全正确。那些是让一个人出类拔萃而不是平庸的特质。

<details>
<summary>Original English</summary>

**Thuan Pham**: standout that's right those are things that make someone outstanding versus someone the average

</details>

**主持人**: 所以我想也许一个建议是，如果你以前是一个优秀的工程师，就不要自满，继续使用，继续以同样的方式处理问题。对。

<details>
<summary>Original English</summary>

**主持人**: so I guess maybe an advice is like well I mean try not like if if you were a great engineer before just don't be complacent and keep using keep right approaching the same way. Right.

</details>

**Thuan Pham**: 完全正确。是的。自满就是死亡。我的意思是，世界会越来越快地发展，我们停滞不前的那一刻，我们就在落后。

<details>
<summary>Original English</summary>

**Thuan Pham**: Correct. Yeah. Complacency is death. I mean like every the world will move faster and faster and the moment we stand still we are falling behind.

</details>

**主持人**: 听起来如果你以前在一家快节奏的初创公司工作过，**AI**应该会很熟悉。欢迎回到以前的样子。

<details>
<summary>Original English</summary>

**主持人**: It sounds like if you if if you worked at a a fast fast-paced startup before which is this is how it works. **AI** should be familiar. Welcome to how it was before.

</details>

**Thuan Pham**: 对我来说，它是一个极其强大的工具，但归根结底，它仍然是一个工具。如果你能正确地运用这个工具，你就能做出非凡的事情，而如果你只是平庸地使用这个工具，你就不会做出伟大的事情。

<details>
<summary>Original English</summary>

**Thuan Pham**: To me it is a incredibly powerful tool but in the end it's still a tool and you can wield the tool properly. you can do extraordinary thing versus you just merely use a tool in a mundane way. You're not going to be a great stuff.

</details>

### CTO的职责与未来展望

**主持人**: 我们谈论了在这个时代脱颖而出的工程师。我想谈谈我不能和太多人谈论的事情：脱颖而出的CTO。你现在在多家公司担任过CTO。我失去了工程副总裁的职位。你曾在**Uber**和**Fair**担任过一些最高级别的工程领导职位，你作为CTO做得非常出色。CTO最重要的工作是什么？

<details>
<summary>Original English</summary>

**主持人**: So we talked about stand out engineers in this age. I'd like to talk about something that I cannot talk with too many things. Standout CTOs. You have now been CTO at multiple companies. I I lost VP of engineering. You've been at some of those high highest engineering leadership and at **Uber** at **fair**. You've you've done an outstanding job as a CTO. What is the most important job of CTO?

</details>

**Thuan Pham**: 是的，这有几个方面。一是建立一个高绩效团队。好的，人才、文化，所有这些。你知道，无论你需要做什么，建立组织结构，发展人才，淘汰表现不佳的人等等，你需要做的一切，以确保你拥有真正高密度的人才，因为当你有A团队时，A团队只会想招聘更多的A级人才，是的，他们对任何表现不佳的人都无法容忍，对吧？所以当你达到那种集中度时，它就会自我保护，如果你愿意这么说的话，对吧？然后当然，你必须创造一个人们真正互相信任、团结一致、合作良好的环境，对吧？因为你组建了一个全明星团队，并不意味着他们就能很好地合作。如果你没有文化上的契合，对吧？所以我一直深信组织方面的事情，如果你把这一点做好，那么好的结果就会自然而然地发生，对吧？无论你想做什么，对吧？他们都能取得出色的成果，因为我们拥有优秀的人才和强大的动力。

另一方面是，你必须展望未来，看到那个拐角处，对吧？例如，我总是思考两年后的情况。伟大的事物需要是什么样子？好的，我们是否拥有关键的要素，如果你愿意这么说的话，人才和其他方面，来实际实现目标，无论是架构、领导力，还是其他什么，对吧？我们正在努力解决什么问题？业务会是什么样子？所以，你知道，著名的**Wayne Gretzky**的名言是“滑向冰球将要去的地方”。所以你必须预见未来。我会在每个管理层级与每个人分享这一点，无论你在哪个层级，你的工作都是要比你的下属看得更远一点，对吧？因为你的下属正忙于处理近期的事情，对吧？然后你必须看到，因为如果你不这样做，那么没有人会做，那是你的工作，对吧？

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah, there there are a couple of angle to this. One is build a high performance team. All right, talent, culture, all of that. you know, whatever it is that you got to do, put the orc structure, put the, you know, uh, develop the talent, prune, you know, uh, bad folks out or whatever, everything that you need to do to make sure that you have really high talent density because when you have team A, team A will just want to hire more A level players and yeah, they just intolerant of anybody who's not performing, right? So, when you get to but you got to get to that concentration and then it's kind of just self-protecting, if you will, right? And then of course you have to create an environment where people really trust each other and align and work really well together, right? Because you put an all-star team together doesn't mean they work really well. If you don't have like a the cultural alignment, right? So that organizational side of things I've always deeply believe in that if you do that one well then good outcome will just happen, right? It doesn't matter what you want to do, right? They will just uh be able to come out with great result because we have great talent and with great motivation. The other side is you have to look in the future and see around that corner, right? For example, I always think about two years out. What does great need to look like? Okay, do we have the key, you know, uh ingredient if you will, talents and otherwise to actually get there, whether it's architects, the leadership, whatever, right? And what problem are we trying to solve? what would a business look like? So, you know, uh the famous **Wayne Gretzky** quote is skate to where the puck would be. So, you have then to envision that future and I would I would share this with everyone at every management level that when you're in a any level, your job is to see a little bit further out than your folks, right? Because your folks are busy working on the near-term things, right? And then you have to see because if you don't do that, then no one it's your job to actually do that,

</details>

**主持人**: 对吧？好吧，让我们来验证一下，因为现在是许多人，包括我，都认为是一个前所未有的增长时期。

<details>
<summary>Original English</summary>

**主持人**: right? Well, let's put this to the test because right right now is the most so many people including me see it's an unprecedented time with growth.

</details>

**主持人**: 你是如何“看到拐角处”的？你现在在你的拐角处看到了什么？比如，即使不是两年后，而是六个月后，会有什么到来？

<details>
<summary>Original English</summary>

**主持人**: How do you look around the corner? What do you see around your corner right now? Like what will be coming maybe not even in two years but even in six months?

</details>

**Thuan Pham**: 嗯，六个月后，我们知道我们需要做什么。事实上，那太短了，对吧？就像这些事情……

<details>
<summary>Original English</summary>

**Thuan Pham**: Well in 6 months you know we know what we need to do. In fact it's too short right it's like these are the things

</details>

**主持人**: 谈谈两年。我最近问**OpenAI**他们两年后看到了什么，他们说：“哦，那太久了，我们谈谈六个月吧。”

<details>
<summary>Original English</summary>

**主持人**: talk about two years. I I I recently asked **Open AI** on what they see in two years and they're like oh that's too long let's talk six months.

</details>

**Thuan Pham**: 但在上下文中一切都很重要，对吧？对他们来说，他们正在努力重塑未来，有时事情变化太快，从那个角度来看。但从**Fair**的业务来看，我们知道我们想要驱动什么业务成果，我们知道我们需要执行什么项目，对吧？对我来说，那几乎是板上钉钉的，它只需要良好的执行，对吧？以及一路上的良好调整。对我来说，18到24个月是我的工作范围，而我的团队则在处理六个月的问题，对吧？

所以，例如，我们有很多领域需要清理，对吧？有老旧的数据生态系统，你知道，我们在**Uber**也看到了同样的问题，你知道，上游的变化会破坏下游的东西，你如何用所有这些老旧的代码库真正清理它？然后，你知道，下一代由**AI**驱动的搜索和发现会是什么样子？生产力会是什么样子？我们如何利用**AI**来使未来的开发产出翻倍，对吧？所以所有这些事情，未来需要是什么样子？我们是否有足够的动力和能力来实现目标，就专业知识、管理和规划而言，所有这些。然后如果答案是否定的，那么下一个问题就是我们如何实际定位自己，我们招聘谁？所以这就是CTO在非管理方面的工作。

<details>
<summary>Original English</summary>

**Thuan Pham**: But in context is everything right? for them they're trying to reinvent that future and sometimes things are changing too fast there from that context but from **fair** the business we know what business result we want to drive we know what project we need to execute right to me that that's pretty much lock and load it just require good execution right good adjustment along the way to me 18 to 24 months out is my job to look at while my team is worrying about the six-month uh problem right and so for example there are many area that we need to clean up right there's the e data ecosystem that's been old and you know same problem we saw at **Uber** too you know something change upstream break thing downstream and how do you really clean it up with all this you know older you know code base then you know what is the next generation of search and discovery that are **AIdriven** right you know to look like productivity right how can we leverage **AI** to like double output on you know future development right so all of these thing what does that future need to look like and do we have the horsepower and and to get there right in terms of expertise uh management and the planning all that stuff and so and and then if the answer is no then it like the next question how do we actually position oursel there who do we recruit and so that that's the job of the co on on the sort of the the non-management side

</details>

**主持人**: 然后最后，你对一个年轻工程师，比如25岁或刚毕业进入这个行业的人，有什么建议？现在变化很多。

<details>
<summary>Original English</summary>

**主持人**: and then finally um what advice would you give to a young engineer someone let's say 25 years old or a new grad who is entering the industry right Now, lots of change

</details>

**Thuan Pham**: 对于现在进入职场的人。我必须承认这是一个非常可怕的时期，因为它非常坎坷。即使在我们公司，现在我们仍然会招聘应届毕业生，但他们是通过我们的实习合作渠道进来的，对吧？我们不再像过去那样大规模招聘应届大学毕业生了，对吧？但优秀的人仍然能找到机会，对吧？我们每四个月都会有一批健康的实习生，对吧？最优秀的人仍然会收到我们的录用通知，因为如果我们今天不招聘这些人，那么几年后我们还会有哪些资深工程师呢，对吧？你必须培养人才管道，优秀的人才就是优秀的人才。他们会学习和成长。

<details>
<summary>Original English</summary>

**Thuan Pham**: For folks who are entering the the workforce right now. I have to acknowledge it's a very scary time because it's very bumpy. Even at our company right now, we still bring in uh new grad, but it come through our uh intern co-op channel, right? Uh we're not in the world where we just hire massive number of new college grad like the old days anymore, right? But if great people are still finding opportunity, right? That we have a a healthy cohort of co-op every single um four months that come through, right? And the best of the best still get offer from us because if we don't hire those folks today, what senior engineer will we have for yeah years from now, right? You have to feed the talent pipeline and great people are great people. They will learn and grow and

</details>

**主持人**: 是的。所以，是的，机会永远存在于优秀人才。所以投资自己，当学生时，你知道，做志愿者，尽早解决难题。你越早越努力工作，未来就会越好。如果你现在太轻松，那么未来的道路可能会更艰难。所以我认为这是关键。然后当你进入这个行业时，这取决于职业阶段。我想说，最初的五到十年左右，寻找能让你学到最多、最能推动你的机会，因为那是你最有精力发展技能并快速提升的时候。当你达到资深工程师、**高级工程师**的级别时，你就知道足够多的东西，可以产生巨大的影响。那时就寻找能让你产生巨大影响的机会。也许一家小公司会给你一个更大的舞台，让你产生巨大的影响，对吧？承担一些风险并去做。那个阶段应该是关于利用你所知道的知识，尽可能地产生巨大的影响。你也会在过程中学习。然后当你进入下一个阶段，如果你真的很好，你已经达到了，你知道，首席工程师、高级**高级工程师**，或者在管理方面，高级总监、副总裁等等。那时你学会了回馈，对吧？你学会了一路指导和培养人们。你将领导并负责非常重要的事情，你知道，运用这些知识做好工作，同时也教导和带领其他人。所以不同的阶段，你应该稍微改变一下优先级。

<details>
<summary>Original English</summary>

**Thuan Pham**: Yeah. And so so that will always the opportunity will always be there for great talent. So invest in yourself when a student you know volunteer doing solve hard problem early on. The earlier and harder you work early on the better you will have in in the in the in the future. If you take it too easy right now then the road in the future might be a little harder. So I think that's the key. And then when you enter the industry it depend on uh I think career phases. I would say the first five 10 years or so find opportunity where you learn the most that push you the most because those are the time that you you have the most energy to develop your skill and ramp up really fast and when you get to like senior engineer staff engineer range then you know enough to be very dangerous in terms of making a big impact then seek opportunity where you can make a big impact. Maybe a smaller company will allow you like a you know a bigger stage to actually make a huge impact, right? Take some of that risk and do that. And that phase should be about using what you know and make this big impact as you can. And you will learn along the way too. And then when you get to the next phase where hopefully if you're really good, you're already at this, you know, principal engineer, senior staff or on the management side, senior director, VP, whatever it is. And then that point you learn to give back, right? You learn to coach and develop people along the way. you'll be leading and responsible for you know very big things uh you know apply that knowledge to do a really great job but also teach and bring other people along so different phases you should change the priority a little bit

</details>

**主持人**: 非常感谢，这是一次很棒的对话，所以我希望每个人都会觉得这很有用。

<details>
<summary>Original English</summary>

**主持人**: to thank you so much this was a great conversation so I hope that everyone be um will find this useful

</details>

**主持人**: 多么精彩的对话，其中许多故事以前从未被讲述过，我希望你和我一样喜欢它们。微服务的故事非常精彩。**Uber**没有人计划拥有数千个微服务。它之所以发生，是因为每次他们试图分解单体时，业务增长得太快了，以至于其他团队添加新功能的速度比分解团队剥离旧功能的速度还要快。在隔离情况下只需3到6个月就能完成的事情，却花了两年时间。**Uber**经历了异常剧烈的业务增长，导致异常快速的代码增长，而微服务帮助**Uber**驯服了这种增长。但除非你以**Uber**的速度增长，否则你可能不需要数千个微服务。哦，还有一个有趣的事实，在2026年，**Uber**的微服务数量比2016年还要少。

我还发现**Thuan**的整个职业生涯是如何通过简单地做好工作而建立起来的人际关系塑造的，这令人着迷。**Bill Gurley**联系他加入**Uber**，是因为他记得**Thuan**在十年前的**NetGravity**公司，那家公司甚至没有赢得市场。**Thuan**从**VMware**招募到**Uber**的工程师之所以前来，是因为他们真心喜欢和他一起工作。这没有所谓的“人脉策略”，只是多年来对人友善，在幕后悄然积累。

最后，**Thuan**关于**AI**的观点很有趣。自满就是死亡。在这些**AI**工具出现之前，造就优秀工程师的特质：好奇心、无畏、愿意尝试新事物，正是造就**AI**工具时代优秀人才的相同特质。工具变了。但让人出类拔萃的特质没有变。请查看下面的节目说明，了解更多关于**Uber**和**Uber**工程文化的深入探讨，这些内容已在《实用工程》时事通讯和播客中涵盖。如果你喜欢这个播客，请务必在你喜欢的播客平台和**YouTube**上订阅。如果你能给节目留下评分，我们将特别感谢。

<details>
<summary>Original English</summary>

**主持人**: What a conversation so many of these stories have not been told before and I hope you enjoyed them as much as I did the microser story is such a good one nobody at **Uber** planned to have thousands of microservices. It happened because every time they tried to decompose the monolith, the business was growing so fast that other teams were adding to it faster than the decomposition team could pull things out. It took 2 years to do something that in isolation would have taken 3 to 6 months. **Uber** had unusually violent business growth that resulted in unusually fast code growth and microservices helped **Uber** tame its growth. But unless you're growing at the speed of **Uber**, you probably will not need thousands of microservices. Oh, and fun fact, in 2026, **Uber** has fewer microservices than they had in 2016.

I also found it fascinating how **Tuan's** entire career was shaped by relationships he built by simply doing great work. **Bill Gurley** reached out about **Uber** because he remembered **Tuan** from **Netgravity**, a company from a decade earlier that didn't even win his market. The engineers **Tuan** pulled from **VMware** into **Uber** came because they genuinely enjoyed working with him. There was no networking strategy. just years of being good to people compounding quietly in the background.

Finally, **Tuan's** point about **AI** was an interesting one. Complacency is death. The traits that made someone a great engineer before these **AI** tools: curiosity, fearlessness, willingness to try new things are exactly the same traits that make someone great with **AI** tools. The tools changed. What makes people exceptional has not. Do check out the show notes below for more deep dives on **Uber** and **Uber's** engineering culture as covered in the pragmatic engineering newsletter and podcast. If you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on **YouTube**. A special thank you if you also leave a rating on the show.

</details>