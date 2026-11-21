---
author: AI Engineer
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1et3Lb_KLQo
speaker: AI Engineer
tags:
  - content-creation
  - workflow-automation
  - human-in-the-loop
  - generative-ai
title: 我不怕 AI 垃圾内容，我怕未被讲述的故事：为你在乎的人打造内容工厂
summary: WorkOS 应用 AI 工程师 Zack Proser 分享了他如何将个人长期的写作与手艺经验封装为自动化“工厂”。他先后构建了帮助同事撰写技术博客的 Blog Bot，以及用家庭照片为两个幼儿生成睡前故事的专属应用。他认为比起 AI 垃圾内容，更值得担忧的是那些因恐惧或自我怀疑而未能面世的故事；通过将专业审美与流程封装为工具并由人类把关，能赋予他人非对称杠杆，让更多人有效分享自己的经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Zack Proser
  - Michael Grinich
companies_orgs:
  - WorkOS
  - Cloudflare
products_models:
  - Slack
  - Granola
media_books: []
status: evergreen
---
### 为什么应该为你关心的人打造一座“工厂”

非常感谢各位的到来。在这次演讲中，我打算尝试说服大家：如果你在乎某个人，无论你是否经常与他们共事，你都应该为那个人打造一座工厂。接下来我们会探讨这究竟意味着什么，以及为什么要这样做。

<details>
<summary>Original English</summary>
[music]

>> Thank you all so much for being here. In this talk, I'm going to try to convince you that if you care about somebody and if you work with them regularly, even if you don't work with them regularly, you should build that person a factory. And we're going to talk about what that means and why.
</details>

那么首先，我为什么会这么说呢？我是一名开源开发者，已经做了 15 年了。

<details>
<summary>Original English</summary>
So, first, why do I say this? Um so, I'm an open-source developer, have been for 15 years now.
</details>

但从十几岁初开始，我就在极其狂热且持续不断地写作。最初是用铅笔、纸、钢笔和笔记本。大概 16 岁左右，我开始使用文字处理软件。在过去 15 年的职业生涯中，我在许多初创公司工作过，作为工程师在那些公司任职期间，我会在他们的博客上发表文章。

<details>
<summary>Original English</summary>
But since my early teens, I was writing uh voraciously and constantly. It started off with pencil paper, pen, and notebooks. And then around 16, I was onto word processors. And in the course of my career in the last 15 years, I've worked at a bunch of startups and I've published stuff on on their blogs as an engineer while working there.
</details>

之后我一直持续在自己的个人网站上发布内容。因此，我写了大量的随笔、教程以及各种我觉得有趣的东西，以此来满足自己的探究欲。在这个循环中，一旦我解决了自己的痛点，我就喜欢把它发布出来，与全世界分享。

<details>
<summary>Original English</summary>
And then I've constantly been publishing on my own site. So, I have a ton of essays and tutorials and things that I find interesting to kind of scratch my own itch. And then as part of that cycle, as soon as I scratch that itch, I like to just publish it and kind of share it with the world.
</details>

说这些只是想表明，我写起东西来可以说是带有某种执念、甚至有点狂热，而且这种情况已经持续相当长一段时间了。稍后我们会谈到我写过的一篇文章，那是我所有文章中表现最好的一篇，而我只用了 23 分钟就写完了。我们也会聊聊我是怎么做到的。

<details>
<summary>Original English</summary>
And so, that is all just to say that I write sort of obsessively, kind of fanatically, and have been doing so for for quite some time. And we'll get into one of the posts that I I wrote here that has done consistently the best and that I wrote in 23 minutes. And we'll talk about uh how I did that, too.
</details>

不过我相信你们当中有些人已经在想：这又不是 AI 大会，也不是关于 AI 的演讲；这里面肯定充斥着粗制滥造的垃圾内容（slop）。但我打算告诉大家，有一件事远比所谓的“AI 垃圾内容”更让我担忧。

<details>
<summary>Original English</summary>
But I'm sure that some of you are already thinking uh this isn't, you know, this isn't an AI conference, isn't an AI talk. Uh certainly there is slop involved here. And uh I'm going to tell you that there is something that I'm far more concerned about than AI slop in particular.
</details>

我相信，只要我们带着正确的初衷去塑造作品，去审视产出的结果，并对自己和彼此负责，我们实际上完全有可能利用 AI 创作出比没有它时更好的故事，同时改进流程，让更多人能够更有效、更持续地讲述自己的故事。

<details>
<summary>Original English</summary>
And I believe that if we uh bring the right intention to shaping the work and we judge the result and we hold ourselves and each other accountable, that it is actually possible to use AI to produce better stories than we can without it and to improve processes so that more of us can tell stories more effectively and more consistently.
</details>

### 23 分钟写出的文章与内容工厂的雏形

回到我刚才提到的那篇文章，那是我根据自己在过去十来年运营和自主发布技术博客的经历写成的。我在文中分享了那是一种怎样的体验，以及长期运营并保持持续输出究竟是怎样的过程。这篇文章从完全不存在到写进 Markdown 并彻底发布，我全程只花了 23 分钟——那是在大语言模型出现之前。而且那还是在经历了一场特别折磨人的哄睡、把我的两个幼儿安顿睡下之后写出来的。

<details>
<summary>Original English</summary>
So, to get back to that post I was talking about, uh this is a post that I wrote about my own experience over the course of, you know, decade and a half running and self-publishing a tech blog. And I made some, you know, shared kind of what the experience was like and what it what it's like running that and keeping up the consistency. And I published this in I wrote the entire thing from didn't exist to written into markdown and and fully published in 23 minutes before LLMs. And it was after a particularly brutal bedtime routine putting down my two toddlers.
</details>

因此，我的同事和一些朋友难免会不停地问我：你怎么能写得这么快？你到底是怎么做到的？这怎么可能？你一天的时间又没有比我多。

<details>
<summary>Original English</summary>
And so inevitably what my colleagues and some of my friends would would constantly ask me is how do you write so fast? Like what are you doing and how how is this possible? You don't have more time in the day than I do.
</details>

当我思考这个问题时，我意识到答案就在于我一直在构思写作。在某种程度上，我总是在强迫症般地推敲新的标题、想法、句子，或者思考我能讲什么样的故事，以及如何把那个故事展开，让它尽可能地引人入胜、极具感染力。

<details>
<summary>Original English</summary>
And when I thought about this, I realized that the answer is that I am always writing. And so to some degree, I'm kind of obsessively trying out new titles or ideas or sentences or how what stories might I tell or how might I develop that story so that it is the most compelling and impactful that it could possibly be.
</details>

结果就是，我曾经基本上成了我个人认识的唯一一座“内容工厂”。就像那样，做着自己的事情，在初创公司工作，当一名开发者，但同时又在源源不断地发表内容。

<details>
<summary>Original English</summary>
And as a result, I was essentially the once the only content factory that I knew personally. You know, just kind of, you know, doing my thing, working at in startups, being a developer, but then constantly publishing.
</details>

### 比 AI 垃圾内容更可怕的是未被讲述的故事

正因如此，我个人并不那么担心 AI 垃圾内容，因为我认为我们可以应用非常多的技术来纠正它，而且我认为有办法解决那个问题。我真正担忧得多的，是所有那些从未被讲述出来的故事。

<details>
<summary>Original English</summary>
And so I personally am not as worried about AI slop because I think there's a tremendous number of techniques that we can apply to to fix that and I think there's ways to solve that problem. I'm I'm significantly more concerned about all the stories that go untold.
</details>

在我的职业生涯中，通过与一大批优秀且才华横溢的人共事，我注意到很多人常常对自己说：“噢，我不是个写作者，我干不了那个。”许多人因为各种原因感到恐惧和羞怯，无论是因为他们过去的经历，还是他们的自我认知限制了他们，导致他们无法把自己最有影响力的工作分享出来，无法以一种对他们自身和未来的职业发展最具价值的方式进行分享。

<details>
<summary>Original English</summary>
And so what I've noticed over the course of my career and working with a bunch of excellent and talented folks is that a lot of folks tell themselves, oh, I'm not a writer, I can't do that. A lot of folks feel fear and shame for various reasons, whatever the their experience might be or or their self-concept limits them from actually sharing the most impactful work and sharing it in a way that would be most impactful to them and their their future career.
</details>

这就是为什么我说，现在是时候考虑去打造充满关爱与宽容的工厂，并把它们赠予他人了。接下来我们将深入阐述这究竟意味着什么。

<details>
<summary>Original English</summary>
And so this is why I say that it's it's time to consider building factories of love and grace and to give them away. So we're going to develop what that actually means.
</details>

### WorkOS 的 Blog Bot 与非对称杠杆

我是 WorkOS 应用 AI 团队的一名工程师，在那里工作了两年。

<details>
<summary>Original English</summary>
So I am a engineer on the Applied AI team at WorkOS. I've been there for 2 years.
</details>

大约一年前，我们决定需要提高发布的频次。这同样不是为了向互联网发射垃圾内容炮弹，而是因为我们有多个团队和成员一直在做着非常出色且具创新性的工作，但我们并没有稳定地把所有这些故事讲出来，也没有将我们的洞见以及正在做的事情充分带到市场上。

<details>
<summary>Original English</summary>
About a year or so ago, we decided that we needed to increase publishing velocity again, not to slop cannon in the internet, but because we had multiple teams and folks that were doing excellent and innovative work constantly, and we were not consistently telling all those stories and kind of bringing, you know, our insight and stuff that we were doing to the marketplace.
</details>

于是我构建了最初被我们称为 Blog Bot 的系统。这是一个构建在 Cloudflare 之上的系统，运行在云端。基于我那种近乎强迫症般的写作背景，我能够做到的，是去思考：在这项手艺中，究竟什么才是一份优秀的作品？

<details>
<summary>Original English</summary>
And so I built the initial what we call Blog Bot, right? And this is a system that was built on Cloudflare, and it runs in the cloud, and because of this sort of obsessive writing background that I had, what I was able to do was to think about what do I believe makes a good artifact in in this in this craft, if you will, right?
</details>

也就是随着时间的推移和许许多多次的反复实践，我个人认定的、能够让一篇文章更有趣、更引人入胜、具有更高教学价值的所有要素。我把所有这些理念塞进了一个实现自动化的盒子里，然后把这个盒子交给了我的同事们。

<details>
<summary>Original English</summary>
And so what are all the things that over time and many, many repetitions I have come to believe personally make something more interesting, more engaging, you know, um to have better pedagogical value. And I just kind of stuffed those all into a box that made it automated, and then I handed that box to my colleagues.
</details>

这最终为他们带来了我如今所说的**非对称杠杆**（asymmetric leverage）。同事们可以通过 Slack 中一个非常简单的界面——一个他们早已理解且每天都在使用的工具——发出指令说：“@Blog Bot，我们有这次活动的文字记录，我想让你围绕它生成一篇符合品牌调性、紧扣主题、达到 WorkOS 质量标准的活动回顾博客文章。”

<details>
<summary>Original English</summary>
And what that ended up producing for them was this what I call asymmetric leverage now. So a colleague can come into a very simple interface in Slack, something that they already understand and use every day, and say, "At Blog Bot, we've got this transcript from an event, and I want you to produce an on-brand, you know, on-theme, you know, reaching the quality bar WorkOS blog post about it recapping it."
</details>

他们得到的是一份已经完成了 85% 到 90% 的初稿。这意味着他们不必再耗费精力手动从 Granola 录音、活动图片、大家在 Slack 中准备时的讨论或是我们想要采取的框架中拼凑所有的上下文，所有这些都已自动为他们获取完成。他们拿到的是一篇基本就绪的博文，只需要再进行两三轮迭代，由真人通读一遍、署上自己的名字并发布出去即可。

<details>
<summary>Original English</summary>
And what they get out is, you know, a draft that is 85 to 90% of the way there. It means that they haven't had to manually and tediously assemble all the context from the Granola recordings or the images of the event or what folks said about it in Slack to prepare or the framing that we wanted to use. All of that is automatically sourced for them. And what they arrive at is a blog that is essentially ready to almost ready to go, but needs a couple more iterations and for a human to read all the way through and to put their name on it and to publish it.
</details>

非对称杠杆的精妙之处在于，你可以在一个极其简单的界面背后，隐藏一个非常强大甚至复杂的分布式系统。该系统拥有连接到公司内部你在乎的每一个信息源的数据连接器、定制工具、向人类请求批准以确认事实的能力等。我们甚至还有一个专用的图像生成端点，其产出完全契合我们极其优秀且才华横溢的设计团队的标准。

<details>
<summary>Original English</summary>
And so the nice thing about asymmetric leverage is that you can hide behind a very simple interface an incredibly powerful and even complex, you know, distributed system that has a data connector to every source of information that you care about in your company, custom tools, the ability to ask a human for approval to confirm facts, etc. We even have a special endpoint that has that does image generation that is um the outputs resemble exactly what our excellent and very talented design team would produce.
</details>

通过持续推行这一做法并允许其他人运行它，全公司的发布速度确实得到了提升。

<details>
<summary>Original English</summary>
And so that, you know, consistently doing this and allowing other people to run it does across the org increase publishing velocity.
</details>

仅仅凭借最初的那份草案或最初的提示词——同事只需说：“嘿，我们刚办了一场活动，想写篇回顾文章。我现在手头还有别的事，你先起个草稿吧？”他们所拿回的成果，也就是我所说的非对称杠杆，是一份内容充实的东西。它虽然不能直接一键推到生产环境发布，必须有人承担责任并通读全文，但系统已经帮他们完成了大量前置工作来整合初始素材。

<details>
<summary>Original English</summary>
And so with just that initial draft or just that initial prompt where my colleague said, "Hey, we just had an event. We want to do a recap post about it. I have some other things on my plate right now, so why don't you start the draft, right?" And what they get back, what I mean by asymmetric leverage is this is what they get back, something substantial. It is not ready to one shot all the way to prod. Somebody has to take responsibility for it and read it all, but we have done or the system has done a significant amount of the work for them to assemble the the initial pieces.
</details>

更重要的是，他们完全有权按照自己的喜好进行调整和微调，完全不需要我介入。他们不必来请求我或者其他任何具有写作背景的人做任何事，只需以极其简单的方式做出自己想要的修改，把工作完成。在刚发布之后，看到这些工具开始起作用，同事们开始用它产出成果，感觉非常棒。

<details>
<summary>Original English</summary>
And then it is, more importantly, something that is solely in their power to adjust and tune to their liking without me being involved at all. So they don't need to, you know, ask me to do anything or anyone else that that might have a writing background. They can just make the changes that they want in a very simple way and kind of get their work done. And so, you know, this was fun to initially see after I published that this stuff started working and folks there were producing things.
</details>

### 流水线与手艺：极致速度下的品质坚守

我记得大约在这个时候，我和 WorkOS 的创始人 Michael Grinich 有过一次交流。我们当时正在讨论公共领域中正在发生的激烈争论，即关于向外疯狂倾倒垃圾内容，以及“AI 写作全都是垃圾”等论调。

<details>
<summary>Original English</summary>
And I remember around this time I had a conversation with Michael Grinich, the founder of Work OS. We were talking about, you know, the pretty the debate that was happening kind of in the public square about, you know, slop canonning and and, you know, AI writing is all slop, etc.
</details>

但与此同时，大家又渴望推进得更快；而对于我们这些经验丰富的开发者来说，我们看得很清楚，利用这些强大的工具可以在几天内构建出过去往往要耗费数月的东西。

<details>
<summary>Original English</summary>
And at the same time the desire to move faster and for us as experienced developers, we were seeing it was very obvious that you could use these powerful tools to build things in days that used to take us months at a time.
</details>

Michael 打了一个比方，他给我看了一段 YouTube 视频：一家公司在生产线上批量组装钹（cymbals），产出速度非常快，但他们会对每一个产品进行检验。Michael 试图借此说明，这与我们通过 Blog Bot 及其他工具开始尝试的事情十分相似。

<details>
<summary>Original English</summary>
And so Michael used a metaphor and he showed me a YouTube video where a company was mass assembling symbols on a production line and, you know, producing them very, very rapidly and yet inspecting all of them. And initially, and he was trying to, you know, draw the the parallel to this is kind of what we're starting to experiment with with these this blog bot and other tools as well.
</details>

Michael 说：“在我看来，这完全体现了手艺（craft）。”

<details>
<summary>Original English</summary>
And Michael said, "This screams craft to me."
</details>

我记得刚跟他一起看那段视频时，我心里其实有些畏缩，并不太能坦然接受“是的，我想我确实可以以更快的速度产出文章或内容”这种说法。

<details>
<summary>Original English</summary>
And I remember the initial time that we were kind of looking at that video together, I sort of flinched and didn't fully feel comfortable to accept that, "Yeah, I guess I can produce an articles even faster or content even faster."
</details>

但 Michael 的核心观点在于：手艺贯穿于整条流水线之中。因此，即便机器在许多环节承担了大部分甚至全部的繁重工作，并以人类无法企及的速度生产部件，但那家公司始终保留着的，是对工艺彻头彻尾的深厚专注。每一件乐器都由在公司工作多年、深谙质量标准的音乐家亲自试奏；他敲击试听，从他的口型你可以看出他在说“很完美”，然后转交给下一道工序，这一件就可以出货了，他在上面确认：“我，这个人，对这面钹进行了验收，它可以冠以这个品牌名称推向市场。”

<details>
<summary>Original English</summary>
But Michael's point was that craft runs through the entire line. So, even though machines are often doing must much of the heavy lifting or even all the heavy lifting in some parts and producing units at a speed that humans could not approach, what has not left that company is a complete and profound dedication to craft and inspecting every single device as played by a musician that has been with the company for a long time and understands what the quality bar is and plays and he you can kind of see if you read his lips he's saying it's beautiful and then he hands it off and that one's good to go and he's putting, "I, this person, signed off on this symbol. It is ready to be produced under this brand name."
</details>

他们去演奏、倾听并做出决断。产品的生产速度可能极其惊人，但品质从未脱离这个过程。这就是为什么 Michael 会告诉我“这完全体现了手艺”。起初我对此不太习惯，但后来我回头反思了自己在写作方面的历程，我意识到我其实并不反对他的观点。

<details>
<summary>Original English</summary>
So, they play, they listen, and they decide. They might be being produced at extreme speed, but the quality has not left the process. And this is the reason why Michael told me that this screams craft to me. And so, I was initially uncomfortable with that, but I went went back and kind of thought about my own journey in in writing and I I realized that I didn't disagree with him.
</details>

后来，在 Blog Bot 发布了两到三个版本之后，我们在博客上发表了一篇回顾文章。当时我们看到全公司的发文率都在上升；更重要的是，我亲眼看到许多平时做着极其出色的工作却不常向外分享的同事，现在都在定期撰写文章来介绍：“这是我们做的工作，它的运作机制是这样的，它能实现什么功能。”

<details>
<summary>Original English</summary>
And so, we published a recap post after the second or third version of blog posts was out and we had seen publication rates rise across the org and I had anecdotally, more importantly, seen colleagues that were doing excellent work but didn't always share that work were now regularly producing articles to say, "This is what we worked on. This is how it works. This is what it does."
</details>

### 锻造隐喻：火花、风箱与淬火

所以我知道这套机制开始见效了。但我们在网上收到的最早的一条评论却是说：你们做这事挺酷的，但我现在在网上读到的每样东西，读起来都会感到膈应。我心里带着膈应去读，大脑在审问每一句话：“这句是 AI 写的吗？那句是 AI 写的吗？这句是人写的吗？还是那句是？”

<details>
<summary>Original English</summary>
And so, I knew that it was starting to work. But we got one of the the first comments that we got online was from someone saying that this is cool that you did this, but now every single thing I read online, I flinch when I read it. I read it with a flinch. And I'm interrogating in my mind every sentence, "Was this AI? Was that one AI? Was this one human-written? Was that one?"
</details>

在某种层面上，我最初理解这种抱怨。但它也一直困扰着我；结合之前关于流水线与手艺的讨论，我决定必须把自己在这一问题上的思路理清楚。当然，我理清思路的方式就是写作。

<details>
<summary>Original English</summary>
And at a certain level, I understood this complaint initially, but it it also bothered me and and taken in conjunction with the conversation around the assembly line and craft, I decided that I kind of had to get my own thinking on this issue clear and straight. And so, of course the way that I do that is to write.
</details>

于是我决定回顾并思考：我对过去的写作方式有什么看法？作为一个人去写作意味着什么？而如今我能借助大语言模型以 6 倍的速度、经过多得多的迭代达到最终目标，这又意味着什么？

<details>
<summary>Original English</summary>
And so I decided to look back and think about what do I think about the way I used to write and what it means to write as a person and now the fact that I can do it with an LLM and get to the the end goal that I want um you know, 6x faster with many more iterations.
</details>

我决定从铁匠锻造的世界中借用一个延伸隐喻。在这个场景中：
- 我是**火花**（the spark）：依然保有意识，依然在真实世界中与人打交道，体会着摩擦、痛苦、磨难与喜悦。因此，作为一名开发者或一个有品味的人，由我来决定这是好是坏，是我喜欢还是不喜欢，或者这是否是一个值得去讲述和分享的重要且有趣的故事。
- 与此同时，我也是**风箱**（the bellows）：在这个阶段，即便大语言模型或机器可能正在帮我处理具体的繁琐细节，我依然在观察产出的内容，并指明：“这部分还可以；这一段完全不相干，直接删掉；这些内容需要展开，但必须按照这种确切的方式展开；这里写错了。”我不断地打磨作品，让它越来越接近我想要的方向。
- 最后，作品必须打磨到足以正式发布到某个网址上的状态，因此我同样是**淬火水**（the quench）：如果现场有真正的铁匠，还请原谅我滥用这个隐喻。但我就是将烧红的铁块浸入水中的那一刻——将它冷却定型，然后宣布发布。Zack Proser 说了这些话，他为所有这些文字、主张、链接、技术规格和性能数据承担责任并为其背书。

<details>
<summary>Original English</summary>
And I decided to borrow an extended metaphor from the blacksmithing world and say that in this case I am the spark who is still conscious, who's still dealing with people in the world experiencing friction and pain um and suffering and joy etc. And so I decide as a developer or a person with taste uh that this is something that's good or that I don't it's not good or I like it or I don't like it or actually this is an important and interesting story that is worth telling and sharing. And then I'm simultaneously the bellows. Now even if at this point in the process the LLM or the machinery might be doing the actual tedious um minutia for me I'm still watching what develops and saying this over here is is okay, this section is completely you know, um irrelevant just drop it. Uh all of these need to be developed but they need to be developed in this exact way and this is wrong, right? And so I'm continuously shaping the work closer and closer to where I want it to go. And then finally uh you know, something has to be done enough to at least initially publish it at a URL and so I am also the quench. I am the thing that you you know, drop into I'm so sorry if there's actual blacksmiths in this I'm as I torture this extended metaphor. But I am the thing that you drop your hot iron into the you know, into the water and it and it seals it and stops it and says publish, Zack Proser said this and he stands behind all these words and these claims and these links and these specs and and this performance data.
</details>

因此，最终的成品依然必须配得上署上我的名字。我对这一点思考得越深，就越觉得我有了一套框架，去理解未来即便产出速度不断提高，我们该如何继续前行并依然确保品质。

<details>
<summary>Original English</summary>
And so the finished work still has to earn my name and so the more that I thought about this the more that I felt like now I had a framework for kind of understanding how we're going to move forward and still produce quality in the future even if the velocity is increasing.
</details>

不仅如此，我思考得越深入就越发意识到：由于我有着始终大量产出并不断迭代的背景，我觉得对于最终用户而言，左边是由我纯手工打出文档里的每一个字然后印出来，右边是由我花两小时半或三小时在大语言模型中进行 14 轮迭代——期间不断指出“不，不是那个，改掉这个词，按那种方式改掉那个句子；好，挺接近了”，最后由我自己亲手微调几处并发布——这两者对最终用户而言实际上没有任何区别。用户要么觉得“Zack Proser 写的这篇是垃圾，我再也不读他的东西了”，这没问题；要么会觉得“写得还行，下周我可能还会再读读看这个人的内容”。

<details>
<summary>Original English</summary>
And and furthermore the more I thought about this the more I realized that because of my background in producing a lot all the time and iterating constantly I feel that if the end user can't tell the difference between on the left me writing every single element by hand in the document and then printing it, and on the right me spending two and a half or three hours going through 14 iterations with an LLM and then saying no, not that, change this word, change that sentence like that. Okay, that's pretty close. And then hand editing a few more at the end myself, and then publishing it, there's effectively no no difference for the end user. You know, you either say that that thing that Zack Proser produced is garbage, I'm going to read them again. That's fine. Uh or you say like that's okay and maybe next week I'll come back and give that person another try.
</details>

所以我意识到，我真正在乎的、也是我建议大家去在乎的真正衡量标准在于：
- **它真实吗？**
- **它有用吗？**
- **它优美吗？**
- **它是否对他人有所助益？**

因为如果我们生产的内容归根结底是要让人类来审阅品味的，这才是我们真正追求的目标。

<details>
<summary>Original English</summary>
And so I I realized that what I actually care about and what I think I would suggest we care about is that uh the real the real rubric here is is it true? Is it useful? Is it beautiful? And does it help anybody else? Because that's what we're actually going for if we're producing things that are for humans to review at all.
</details>

### 为极小受众打造工厂：4 小时落地的儿童睡前故事应用

在这个房间里的所有人，无论大家是否意识到、是否这么认为、或者是否以此来定位自己，其实都有类似的能力——对某种作品或工作流有着绝对专业的掌握。它可能是一个内部流程，也可能是某种极其深奥或复杂的事物。无论你在哪里工作、处于什么行业、或者想做什么，通用的理念都是：先把这项专长做成一个工具，让它运转起来，直到你能看到某些符合你标准且能够生产出来的东西。

<details>
<summary>Original English</summary>
And so uh you know, all of us in this room, whether we realize it or think of it or conceive of ourselves in that way or not, have something like this, some artifact or workflow that they are um absolutely an expert in. It could be an internal process, it could be um something extremely arcane or complex. And the the overall concept, regardless of where you work or the field and industry or what you're trying to do, is to create that into a tool initially, kind of get it working where you start to see something that you recognize and can produce.
</details>

然后你让其他人来尝试，并询问：“如果你们尝试把自己的素材放进去跑一遍，能否达到你们想达到的最终目标？你们能否更完整、更有效地完成工作？”我认为这是一个应用广泛的模式，未来我们会越来越多地看到它的身影。

<details>
<summary>Original English</summary>
And then you let other folks try it and say uh if you try this and put your stuff through it, you know, uh are you able to get to the end goal that you're trying to get to? Are you able to get to your work uh your work done more completely and more effectively? And so I think that this is a broadly applicable pattern that we're going to see increasingly more and more.
</details>

在刚才的故事中，我建造的第一座工厂基本上是为我的同事们打造的。通过它，我们能够触达更广泛的人群，让大家更多地去发表自己所做的卓越工作。但是，作为软件开发者，使用大语言模型的经验以及从中获得的效率加速让我不禁思考：在这个新世界里，如果受众规模更小，是否同样值得为他们建一座工厂？如果受众只有两个人，是否足以成为专门打造一座工厂的理由？

<details>
<summary>Original English</summary>
And uh you know, so the first factory that I built in the story essentially is for my colleagues. So more of where we can reach someone, people are publishing more about the excellent work that they're doing. But the experience, of course, with working with LLMs and the acceleration that I get from that as a software developer, then had me questioning uh in this new world, what if an audience that's even smaller is also worth building a factory for. What if uh two people were enough of an audience to build a particular factory?
</details>

于是我再次应用了相同的思路，在 4 个小时内借助高端配置完全跑通了这套方案。但这一次，我的工厂专门是为两个人打造的。

<details>
<summary>Original English</summary>
And so I applied the same idea again and uh got this fully working with uh Opus 55 extra high end in 4 hours. But this time my factory was for specifically two people.
</details>

正如我提到的，我是两个幼儿的父亲，所以我承担了大量的哄睡讲故事职责。我构建了这个应用，让它读取孩子们当天的照片，找出我们当天做过的事情，然后自动将其构思成适合睡前阅读的故事，并且把他们自己也写进故事里。这样一来，他们的一天就变成了一个故事。我们一起学到的道理或一起做过的事情，他们能再次看到并从中看到自己的映射。应用里还配有动画等内容，并会为他们朗读。

<details>
<summary>Original English</summary>
So uh I do a I've as I mentioned I have I'm a father to two toddlers and so I do a ton of bedtime story duties and uh I built this app so that it looks at the photos of their day and kind of finds what we were doing and then automatically sort of suggest them into a story that can be ready for bedtime and that cast them in it as well. And so their day becomes a story. Lessons or things that we did together they see again and can kind of see reflected in them. There's like animations and stuff and it'll kind of narrate to them.
</details>

这是一段非常奇妙的体验，因为我可以自信地说，这是我整个职业生涯中见效最快的一次测试——从零到可用，在 4 个小时内就迎来了孩子们不断喊着“再来一次、再来一次、再来一次”。紧接着我添加的第一项功能就是实时语音控制，这样当他们最后喊“再来一次、再来一次”时，应用就会自动重播。

<details>
<summary>Original English</summary>
And uh this was a pretty trippy experience because I can say with confidence that this is the fastest successful playtest I've ever had in my entire career um from zero to working and again again again in 4 hours. So the first thing I added next was uh real-time voice control. So when they say again again again at the end it just plays it again.
</details>

这依然是同一种模式。这是我构建的另一座完全运作起来的工厂。它将我所认为什么是好睡前故事的理解代码化了——作为一名担任睡前故事主讲人足够久、久到拥有自己审美标准的实践者，我把这些标准编码了进去。产出的完全是取材于他们当天的内容；现在他们甚至可以直接对着它说：“我想听一个关于美国队长的故事，我想听我和美国队长去动物园的故事。”大概一分半钟之内，整个故事就生成完成了。他们读完故事，在其中看到了自己的身影。

<details>
<summary>Original English</summary>
So again this is the same pattern though. This is another factory that I built that's fully working. It's codified with what I believe makes a good bedtime story what I have you know opinions about and have as a practitioner of bedtime stories for having served long enough to have opinions. And what comes out is exactly their content in their day and now they can literally go up to it and say I want a story about Captain America and I want a story about me and Captain America at the zoo and and then there you go and in a minute and a half like you have that full story. They go through it and they see themselves reflected in it.
</details>

### 对冲焦虑的解药：把你的强观点注入工厂并赠予他人

我之所以分享这一切，是因为这是一个充满巨大潜力和进步的时刻，但同时也充斥着焦虑、不安、不确定、恐惧和怀疑。

<details>
<summary>Original English</summary>
And so you know I I share all this because it's a moment of like incredible potential and advancement and anxiety and hand-wringing and uncertainty and fear and doubt.
</details>

作为一名视觉创作者，我自己也经历过这些心路历程：从“我画画、我喜欢画画”到“天哪，我以后为什么还要再画画？”写作是这样，软件开发也是这样，然后再重新跨越到另一面。

<details>
<summary>Original English</summary>
And I've experienced those things as you know as a visual artist going from oh I draw and I like to draw to oh why would I ever draw again um to the same thing for writing, same thing for software and then back to the other side.
</details>

因此我只是想分享，在某种程度上，这正是对抗那种恐惧、不确定与怀疑的解药。因为我知道我喜欢生产这些东西，我也喜欢帮助其他人去产出；当我看到平时工作极为出色、却可能不认为自己是创作者或写作者的同事，如今能够因此获得认可，并与全世界分享他们的成果以及发现的模式时，我体会到了巨大的快乐和满足感。

<details>
<summary>Original English</summary>
And so I just wanted to share that this is now the in some ways an antidote to that kind of fear and certainty doubt because I know that I like to produce these things, and I like to help other people produce those things, and I get immense joy and satisfaction out of seeing my colleagues who are doing excellent work but might not think of themselves as creators or writers now getting credit for and sharing their work with and the patterns that they've discovered with the world.
</details>

看着我的同事们把越来越多的故事、深度技术剖析和项目公告通过第一座工厂发布出来，这令人无比欣慰。看着我的孩子们产出属于他们自己的故事，真实地讲述我们当天做了什么、学到了什么，比如为什么要轻手轻脚、不要打妹妹等等，同样美妙。这是我做过的最成功的试玩测试，每篇故事平均被要求重播三次，最主要的反馈就是“还要、还要、还要”。

<details>
<summary>Original English</summary>
And so, seeing my colleagues put increasingly more and more stories and technical deep dives and announcements through the first factory is incredibly satisfying. You know, seeing my kids produce their own stories that that literally talk through what we did in that day and what we learned, and you know, why we need to have soft hands and not slap our sis you know, sister etc. Um But again, most successful play tests I've ever done uh the the average uh request for book repeat is like three per story, and it's you know, the primary feedback is again again again.
</details>

现在我可以尽情欣赏他们创造出来的内容，而这两座工厂都是如此——无论是我与同事合作的工作工厂，还是在家里的生活工厂。仅仅是因为我长期专注于做某件事并沉淀了这类作品的制作经验，久到足以形成关于什么才算有趣、什么才算优秀的独立见解；而现在，我让我关心的人把他们自己的内容和故事带入其中。从这里我获得了满足感，也从他们那里得到了反馈——比如他们会说：“嘿，如果它还能做到某某功能就更酷了”，而你会发现：“好，你是对的。”

<details>
<summary>Original English</summary>
Uh so, now I get to enjoy what they make, and that's true for for both these factories. So, it's true for the factory that I work with with my colleagues with and then also at home. So, it's just because that I've done this one thing and made this type of artifact long enough to have opinions about what makes it interesting what makes it good, and now I allow the people that I care about to bring their own content and their own stories through it, and then that is where I'm getting my contentment and getting feedback from them about saying like hey, it would be even cooler if it did XYZ, and you're like okay, you're right.
</details>

因此，我想把这个问题抛回给在座的各位：**你们将为谁去打造一座充满关爱与宽容的工厂？** 谁是你关心的人，或者哪个团队是你所珍视的？有什么东西是你真正烂熟于心，或者是同事和朋友经常对你说“天哪，你在某某方面真擅长”或“你对某某事情真有热情”的？

<details>
<summary>Original English</summary>
And so, the question that I would turn back to all of you in this room is who will you build a factory of loving grace for? So, who is somebody that you care about or a team that you care about? What is something that you specifically know by heart or are constantly told by colleagues or friends man, or you are so good at XYZ, or you have a real passion for XYZ.
</details>

你能为它打造一座工厂吗？如果你是开发者，尽管放手去做；如果你不是开发者，可以让智能体（agent）来帮你做。把你从实践和构建中所学到的一切，以及你所有坚定坚持的主张都倾注到那座工厂里，然后把它交给平时通常不产出这类内容的人，看看他们会创造出什么。这就是为什么我希望我已经说服了大家：如果你在乎某个人，你应该为他们打造一座工厂。

非常感谢大家。

<details>
<summary>Original English</summary>
Can you Can you build a factory for it? If you're a developer, you know, go to town, and if if you're not, have an agent help you do it, and uh pour into that factory everything that you've learned uh from doing and from building, all of your strong uh strongly held opinions, and then hand it off to somebody else that doesn't normally produce that kind of stuff, and then see what they create, and uh that is why I hope I've convinced you that if you care about somebody, you should build them a factory.

Thank you very much.

>> [applause]
</details>