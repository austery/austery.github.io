---
author: Latent Space
date: '2026-11-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dpY7YzZo4kE
speaker: Latent Space
tags:
  - ai-native-development
  - coding-agents
  - context-engineering
  - software-development
  - ai-practice
title: 斯坦福CS146S课程与Monaco AI实践：AI原生开发趋势
summary: 斯坦福大学Mihail Eric在AI Engineer频道访谈中，介绍了其CS146S《现代软件开发者》课程的更新背景，以及作为Monaco AI负责人的实践经验。文章探讨了AI编程代理的发展、上下文工程的重要性，以及AI原生开发对初级开发者的影响。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mihail Eric
companies_orgs:
  - Stanford University
  - Monaco
products_models:
  - CS146S
  - Monocoder
  - HAL
media_books: []
status: evergreen
---
<!-- chunk 1/18 -->

### 庆祝百万订阅与嘉宾介绍

好的，这是一期非常特别的节目，因为我们正在庆祝 AI Engineer 的 YouTube 频道达到 100 万订阅。所以，如果你还没听说过，赶紧去那里订阅吧。我们的嘉宾是 Mihail Eric，他不仅在斯坦福大学教授《现代软件开发者》课程——这门课目前正在走红，基本上涵盖了所有 AI 原生开发实践——同时他也是 Monaco 的 AI 负责人。因此他不仅是一位教师，更是一位从业者。下周来参加 AI Code Summit 的朋友们，这将会是对过去一年中大家在编程领域所目睹的所有巨大进展的一次庆祝。对于对抗烂代码（fighting slop）、System 1 模型以及提升对几乎所有代码进行大规模重写的抱负等主题，我都感到非常兴奋。现在成为一名 AI 工程师是最令人激动的时刻。拥有 100 万名 AI 工程师，我认为这一切才刚刚开始。那么，让我们进入采访。好的，现在我们与斯坦福大学兼职教授兼 Monaco AI 负责人 Mihail Eric 一起在演播室。欢迎你。

<details><summary>Original English</summary>
Okay, this is a pretty special episode because we're celebrating 1 million subscribers on the AI code uh AI engineer YouTube channel. So, go over there and subscribe if you haven't heard about it. Our guest is Mihil Eric who is not only teaching the modern software developer at Stanford which is going viral right now for basically covering all the AI native development practices. Uh but also he is head of AI in Monaco. So he's not only a teacher but he's a practitioner. Um, and those of you coming to AI code summit next week, um, it's going to be the celebration of all the extreme progress that you've seen in coding in the last year. I'm excited about all the themes of fighting slob, of system one models, and of increasing your ambition for major rewrites of basically everything that you've seen in code. U, there's never been an more exciting time to be an AI engineer. And with 1 million AI engineers, I think it's just getting started. So, let's get into the interview. Okay, we're in the studio with Mihal Eric, adjunct professor at Stanford and head of AI at Monaco. Welcome.
</details>

>> 谢谢，很高兴来到这里。

<details><summary>Original English</summary>
>> Thank you. I'm glad to be here.
</details>

>> 你引起我们的关注，是因为你正在第三次——第三次，还是第二次更新你的课程。

<details><summary>Original English</summary>
>> You caught our attention because of your course that you are refreshing for the third time, third time, second time.
</details>

>> 是斯坦福的 CS146S，《现代软件开发者》。

<details><summary>Original English</summary>
>> The CS46 146s, the modern software developer at Stanford.
</details>

>> 这一代初级开发者、初级工程师，以及现在正在进入职场的人们，我认为将成为这种新转变的第一代人。我看了一下课程大纲，感觉这涵盖了我们讲到的所有内容。所以每隔一段时间，我都喜欢邀请像你这样的人，你们涵盖了广泛的话题，然后我们可以按主题逐步展开，

<details><summary>Original English</summary>
>> This particular generation of junior developers of junior engineers of people that are now entering the workforce will I think be the first kind of generation of that new shift. And I looked at the syllabus and I was like, this is everything we cover. So every now and then I like to invite people like yourself who like you cover a broad range of topics and then we can sort of go topic by topic
</details>

>> 并向大家介绍每一项技术的最前沿状态，我想你平时和所有嘉宾也都是这么做的。当然。

<details><summary>Original English</summary>
>> and give people the state of the art of each of these things which I I assume you're doing with all your guests anyway. For sure.
</details>

### CS146 课程的创立与背景

>> 告诉我们这门课的历史吧。是什么让你想要开设 CS146 的？

<details><summary>Original English</summary>
>> Tell us the history of the course. What made you want to spring out CS146?
</details>

>> 是的，这是第二次开课，我第一次讲授是在去年秋季，也就是 2024 年秋季。这还是在 Opus 45 546 之前，但甚至在 2024 年秋季之前，这门课就已经筹备了大约一年。这门课的发端大约是在 2023 年 11 月，我当时就有了这种想法：我们看到编程智能体领域发生了所有这些事情，尽管它们当时只是较早期的编程智能体版本，但已经让人觉得开发者工作的方式、我们完成工作的速度等等所有这些有趣的事情，正在发生巨大的变化。所以在那个时候，如果你想真正深入研究如何做这些事情的方法论，能找到的都只是一些零散的博文和散落在线上的内容。于是我有了这样一个想法：有没有一种方法可以围绕这个建立一个稍微更正式一点的课程体系？有了这个想法后，你知道我的母校是斯坦福，我一直有一个梦想就是回去教书并回馈学校。我一直对教育有很深的投入。我和 Chip 聊过，她也是我的好朋友之一，在斯坦福教过一门课。是的，正是 Chip。我跟她聊了聊，她之前讲授过——我想应该是《机器学习系统设计》——所以我向她请教了整个流程是怎样的，在很大程度上借鉴了她设计课程体系以及考虑如何让课程通过学院审批的思路。我把课程整合起来，花了大概 9 到 10 个月的时间，也就是从 2023 年秋季一直到 2024 年中后期，通过了委员会的评审。我阐述了开设这门课的理由，提交了开课提案以及所有相关材料，这就到了 2024 年秋季，我第一次讲授了这门课。反响非常热烈，学生们对它非常感兴趣。去年甚至好像还有一篇关于这门课的《商业内幕》文章。然后到了今年，发生了很多变化，我想说编程智能体、自主编程智能体的发展势头确实达到了我们以往未曾见过的程度。所以，感觉是时候重新开课、把内容刷新一下了，于是我们就到了现在这里。

<details><summary>Original English</summary>
>> Yes, this is the second time it's being taught and I taught it for the first time last fall. So fall 2020. uh this was pre like opus 45546 days but the even before fall 2025 the course had been about like a year in the making the genesis of the class like November of 2024 and I had sort of had this idea that we're seeing all this stuff happening in coding agents and yes they were an earlier version of the coding agents but already it felt like there was something drastically changing in terms of how developers were doing their work how quickly we were getting work done all that fun stuff and so at the time I it was all just scattered blog posts scattered like things you could find online if you were trying to really get into the methodology of how to do these things. And so I I had this idea like, hey, well, is there a way to kind of structure a curriculum around this? It's a little bit more formal. Had the idea and you know I my own matter is Stanford and I always had this dream to go back and teach something and and kind of pay it forward. I've always been very deep into education. I talked to Chip who also taught a class uh one of my good friends. Yeah. Chip. Exactly. uh spoke to her who she had taught her I guess designing machine learning systems and so like asked her what that process was like and sort of you know took a lot of inspiration for how from how she designed the curriculum and and thought about you know getting some through this through the school put it together spent about 9 to 10 months this was now fall of 2024 through to like you know mid to late of 2025 got it through the committee uh made a case for the class to exist you know I had to put together a proposal and everything uh and that took me to fall 2025 when I taught it for the first time which was very well received achieved you know students were really interested in it. Uh there was even I guess like a business inside article that was written about the class last year and then yeah this year a lot of things changed I would say really coding agents autonomous coding agents really picked up in a way that that we had not seen before. Um so it felt like it was time to do this again uh refresh things uh and then here we are.
</details>

>> 与此同时，你还是 Monaco 的 AI 负责人，那也是一家备受瞩目的初创公司。

<details><summary>Original English</summary>
>> Meanwhile you're also head of AI at Monaco which is also a very buzzy startup.
</details>

>> 是的，确实如此。我们现在正受到广泛关注，而且在其中乐在其中。是的。

<details><summary>Original English</summary>
>> Yes. Yes we are. We are we we're in the airwaves right now and and having a fun time doing it. Yeah.
</details>

>> 是的。所以我很喜欢你同时也是一位从业者这一点。你们在 Monaco 显然正在把所有这些东西落地实施。

<details><summary>Original English</summary>
>> Yeah. So like I I do like that you're also I guess a practitioner. You guys are obviously implementing all these stuff at Monaco.
</details>

>> 在高层面上，对于从去年到今年所发生的变化，你有什么

<details><summary>Original English</summary>
>> Any I guess
</details>

>> 原则或观察吗？

<details><summary>Original English</summary>
>> principles or observations about just what you have changed from last year to this year at high level?
</details>

### 从工具概览到架构原则的演进

>> 是的，太多了。回想去年的课程版本，编程智能体虽然已经存在，但我们仍处于那样一个阶段：涌现出各种公司，分别针对软件开发生命周期（SDLC）的每一个环节。比如有针对代码审查的编程智能体，有针对规范设计的编程智能体，有针对站点可靠性工程（SRE）的编程智能体。当然，其中一些公司现在仍然存在，但去年感觉更多的是在做一个宽泛的导览，展示所有可以使用编程智能体的地方。在某种程度上，去年的很多课程体系都是为了让大家接触并对这方面进行概览，就像是一次探索之旅，告诉你：看，因为 AI，你所了解的关于 SDLC 的一切现在都在发生变化。而今年，我认为有一些原则正在变得更加明确和扎实。比如非常严谨的上下文工程（context engineering）理念，以及通过真正透彻地思考设计与架构来处理高度复杂任务的理念。所以我的课程性质并不是面向初学编程的人，它不能也不打算替代传统计算机科学——比如算法那样的课程；事实上很多那类课程都是我这门课的先修要求。但我知道的是，如果你有了良好的基础，现在要将它付诸应用并在生产环境、在真实世界中运用这些原则，我认为现在已经到了这样一个阶段：在 Monaco 我们要应对庞大的代码库，我也帮助很多公司梳理他们超大规模代码库的设计等等，因此这更像是一门面向从业者的课程，旨在让学生毕业或步入职场后，成为职场中最高效的一员。是的。

<details><summary>Original English</summary>
>> Yeah. Yeah. I mean a ton. I think that when I reflect on what last year's version of the class was, I mean, coding agents had been around, but we were still in kind of that phase where companies were emerging that were tackling every single part of like the ASDLC. There was like a coding agent for code review, there was a coding agent for, you know, spec design, there was a coding agent for SR, and you know, some of those, of course, some of those companies still exist, but it felt like last year it was a lot more about a broad tour of here's everywhere you can use coding agents. And in a way, a lot of the curriculum last year was was geared toward exposure and this this kind of survey, this kind of like odyssey of sorts through, hey, everything that you knew about the SDLC is now changing because of AI. Um, this year, I think there's some principles that are solidifying, right? The idea of like very careful context engineering, the idea of like really thinking through sort of like design and architecture as a way of handling really complex tasks. And so the nature of my class is it's not intended for the like beginner programmer. that is not it is not a replacement for like traditional computer science in the sense of like algorithms and if in fact a lot of those classes are prerex to what I'm what I'm doing here but I do know that you if you have a good foundation going now toward applying that and and and sort of using those principles in in production environments in like real world that's something that I think is is now at a place where you know at Monaco we deal with massive code bases you know I help a lot of companies also with thinking through their massive codebase uh designs and things like that and so really it's more of a practitioners course for once the students have graduated or now entering the workforce, how to be the most productive members of of the workforce. Yeah.
</details>

### AI 时代下的计算机教育与核心价值

>> 你提到你对教育充满热情。我觉得处于大学阶段的学生处在一个非常微妙和关键的节点。你有什么建议或看法吗？大家现在还应该学习计算机科学吗？Claude Code 和 Codex 已经足够满足我们需要的一切了吗？我想听听你的想法。

<details><summary>Original English</summary>
>> You said you're passionate about education. I feel like students in that phase of being in college are in a pretty interesting spot. Any advice and any take? Should people study computer science right now? Is cloud code and codeex all we need? Like I I want to, you know, hear your thoughts.
</details>

>> 是的，正如你可能想象的那样，学生们有很多焦虑。我认为我这次想要传达的很大一部分内容是：这种焦虑确实大部分依然存在，去年也同样存在焦虑，但我想说明的是，一名训练有素的 AI 原生工程师——我知道这是个热门词汇，但我们稍后可以深入探讨其中最有趣的一些方面——一名训练有素的原生工程师可以成为任何公司中最有价值的财富之一。实际上本周是开学第一周，第一周的第一堂课上我就讲了：我坚信每家公司都需要你们，但门槛已经高得多了。你虽然刚走出校门进入第一份工作，但如果用 Google 那套职级体系来说，仅仅达到 L3 的水平已经不够了；进入职场时，你大体上需要比那更强，几乎要达到 Senior（资深）级别的水平。那么我们怎样才能更快地达到那个水平呢？所以我试图阐明的是，拥有扎实的软件工程基础核心依然非常重要，包括理解软件系统是如何构建的，以及这些系统的权衡取舍等核心价值观。但在那之外，我们还会深入

<details><summary>Original English</summary>
>> Yeah, I uh you know there's a lot of anxiety from students as you can probably imagine and uh and I I think a lot of what I'm trying to communicate this time around is that the anxiety a lot of it still is here and there was anxiety last year as well but I want to make the case that a well-trained AI native engineer and I know that's like a buzzy word but let's say we we'll we'll we'll we'll dive into maybe what aspects of that that are most interesting a like well-trained native engineer can be some of the most you know the most useful asset to like any company around and so and you know this is the first week of class actually and like week one you know first lecture hey I really believe that every company needs you but the floor is much higher right so you're entering as like your first job out of school but it's not sufficient to just be like a you know an L3 and like a Google term if you're going to use like that that kind of leveling system there it's like you have to generally be better than you know almost at the senior level going to this so like what what can we how do we get there more quickly right and so I'm trying to say that there is still a core bit of like foundational software engineering that is important to have some of these core values of of sort of how software systems are built and the trade-offs of those systems. But then beyond that we go and
</details>

<!-- chunk 2/18 -->

你看，我认为作为人类，价值恰恰应当体现在这里，而不是去纠结其余的实现细节，那些东西大多可以放手交给工具。

嗯，对，这是我之前表达过的一个观点，听起来可能有点争议。说出来像是为了博人眼球，但我心里其实多半真是这么认为的：绝大多数学生都要完蛋了（most students are cooked）。当然其中一部分人依然会极具价值。我知道这个观点不太中听。斯坦福的学生肯定没问题，对吧，毕竟他们来自斯坦福；但美国其他地方的学生会怎么样呢？

<details><summary>Original English</summary>
you know that's where I think you as the humans should still be valuable rather than and the rest of the implementation details you can kind of defer more often. M yeah this is something I've said before which is almost like the controvers I it's like the kind of thing you say to be spicy but I almost like I I do genuinely kind of believe it which is most students are cooked some of them are going to be super valuable I I don't think it's a very popular thing Stanford kids are going to be fine right they're from Stanford but like what happens to like the rest of America
</details>

>> 对，对，这确实是一个悬而未决的问题。

<details><summary>Original English</summary>
>> right right that is an open question
</details>

>> 这种处境很诡异……

<details><summary>Original English</summary>
>> weird
</details>

>> ……因为我觉得很多教育体系动作都很慢。我甚至很好奇……

<details><summary>Original English</summary>
>> situation cuz I feel like a lot of education is slow to move like I'm even curious in how
</details>

>> 你怎么确定这门课的内容该截止到哪里？你在斯坦福教的是现代软件开发，而这个领域眼下正天翻地覆。

<details><summary>Original English</summary>
>> how do you determine where do you put the end date to curriculum in a course on you're teaching a Stanford modern software like that's changing everything
</details>

>> 走个捷径呗：直接把做编程智能体（coding agents）的那帮人请来讲座不就行了。

<details><summary>Original English</summary>
>> you cheat you just get the people from the the coding agents to come and speak right
</details>

>> 哈哈对，请他们来当……对，这客座嘉宾挺有意思。

<details><summary>Original English</summary>
>> oh yeah like yeah have them be the yeah that's a funny guest
</details>

### 课程设计与行业一线认知

>> 确实挺有意思。不过，关于请客座嘉宾这点，其实去年也是这么做的。这是有意设计的，因为你看，我来教这门课，正如 Swix 你刚才提到的，我是一个一线从业者。我日常工作就在做这些，在 Monaco 设计这类系统，类似的事情我见过很多次了。

话虽如此，我绝不敢声称自己掌握了当下的所有答案，真要那么说就太狂妄自大了。因此这门课的架构一直是：先由我这个从业者，带来在行业一线实战以及与圈内大量同行交流沉淀下来的整合洞见；但同时，还有一些人真正处于前沿，洞察着更远处的动态，于是把他们请过来提出自己的主张，展现他们的前沿视角。这就是为什么会有客座嘉宾……

<details><summary>Original English</summary>
>> it's a funny well yeah I mean you know that was uh okay so so on on the guest lectures point I think that was um I mean that was also last year um that was also the case so so that was by design because I look I I came in right and I'm saying I'm a practitioner as as you point out Swix like I'm a practitioner I do this thing on my you know my day-to-day I design these systems you know we we build these things at Monaco and have seen that many times before and so that that being said I don't want to claim that I have all the answers today and that would be that would be like very you' be a lot of hubris to to make that claim. So the structure of the class was always here's one practitioner's sort of aggregated set of insights from working in the field from like talking to a lot of people in the field but then there's people that are like literally on the frontier you know seeing things even beyond that and invite them to sort of put their their their proposals forward their view of the the world forward and that's why the guest
</details>

>> 我觉得让学生见到行业大咖非常有意义——看那些真正身体力行的人，直接听他们分享，还能向他们提问。当然，学生们也想去实习、找工作，有客座讲座挺好的。

<details><summary>Original English</summary>
>> I think it's really impactful for students to see big names uh people actually doing it like hear from them directly be able to like ask them of course you know they want to intern they want to get jobs it's it's good to have guest lectures
</details>

>> 不，我觉得他的意思是——好吧，我来换个方式表述。我们之前也采访过一位……

<details><summary>Original English</summary>
>> no I think what he's saying so okay I I'll sort of rephrase and uh no so okay there you know we've also interviewed an
</details>

>> 教 Coachella 那门课的，对吧？

<details><summary>Original English</summary>
>> uh who teaches the Coachella course right
</details>

>> 对，那种课就像是把所有大腕全拉过来，光有名头；而他不仅请人，还真的手把手教，比如“用 200 行代码写出 Claude Code”。这可没人会主动教你，请来的嘉宾也不会专门跟你讲这个。但如果你想传授底层原理、给学生一套能用起来的框架和真正融会贯通的理解，你就得做这类事情。

<details><summary>Original English</summary>
>> right which is like here's all the names like it's only the names right whereas like he's actually also producing you know here's cloud code in 200 lines of code right and which is no one's telling you to do that no one no one's going to come speak to you do do that but like yeah that when you want to teach fundamentals in a framework that you can use and a working understanding. This is the kind of thing you do.
</details>

>> 没错，完全正确。而且我认为这类教学内容确实需要平衡。正如你所说，这不可能做到百分之百固化。从设计上来说，这既是特色，可能也在某种程度上算是个缺陷，但相比去年，今年的课程大纲确实有很大一部分换掉了，整个大纲的开发一直保持着一种动态演进。

但我至少想指出，有些底层的东西我认为是会留存下来的。诚然，智能体提示词编写方面，编程智能体确实变得更聪明了，面对这些新的交互方式到底意味着什么？但与此同时，Boris 肯定也掌握着一些我所不知的见解，对吧？那就把他请到桌前，让他也来分享他的收获。

<details><summary>Original English</summary>
>> That's right. That's right. Yeah. Yeah. Exactly. And and I but I do think there's a balance for for this kind of material to to your point is there is a you can't it's not 100% solidified. I mean by by design by design it's a feature and maybe a bug of some some kind but a big portion of the curriculum did change from last year right and so that the there's like a dynamism to the whole development of the curriculum. But I'm trying to at least put forth that there are some things that I believe are kind of sticking around and yes prompting coding agents they've gotten smarter. What does that mean in terms of the new ways of dealing with them? But then still Boris is also going to know something that I don't know, right? So let's let's have let's have him also come to the table and share his learnings.
</details>

### 开源实战与导师制

>> 我注意到这次一个挺有意思的亮点，就是有相当一部分比重放在了开源项目的贡献上。

<details><summary>Original English</summary>
>> Um one of the fun things I noticed this time around is a good bit of the portion is on open source contributions.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这背后的考量是什么？你们让大家……

<details><summary>Original English</summary>
>> Uh what's the thinking behind that? You have people
</details>

>> 是的，这正是我个人深感自豪也最为兴奋的事情之一。这门课马上要进入第二周了。这要归功于那些非常慷慨的开源合作伙伴，整个夏天的大部分时间我基本上都在跟他们沟通，让他们对这种合作模式产生兴趣并感到兴奋。

大致思路是这样的：去年我教这门课时，我们布置了大概 9 次作业，最后加一个开放式的大作业（capstone）。那 9 次作业基本都是我设计的一些教学练习，比如“这里有个代码库，用 AI 代码审查工具去提一份 review，然后分析它为什么好、为什么不好”。相对而言偏教学化，坦白讲对很多人来说相当简单，几乎一把就能跑通。后来我觉得这样下去不行，目前这个阶段智能体已经普及了。周二我做过问卷调查，没有一个学生还在纯手写代码了，大家都在用编程智能体，一个手打的都没有。要知道，这帮学生可全都是斯坦福的大二、大三学生。

<details><summary>Original English</summary>
>> Yeah. Yeah. This is um this is one of the things that I'm honestly kind of most proud of and and most excited about. Uh I mean this about to be week two of the class. Yeah. So this is this is the very gracious open source partners that I spent the greater part of this summer just kind of talking to and and getting them kind of excited about and and and interested in in sort of this offering. Basically the idea was so last year when I taught the class we had like nine assignments and then we had like a capstone open-ended project, right? The nine assignments were basically me sort of like coming up with these pedagogical exercises like oh here's a repo like use an AI code review tool to to you know post a code review and then see what why is it good why is it not good so relatively pedagogical honestly pretty easy I think for a lot of folks they could have just like one-shot it and I thought okay this is not that helpful at this point agents are around I mean they they have every student that I surveyed you know on Tuesday not a single person really types by by hand anymore they're like everyone's using coding agents there's no there's and this is you know like All sophomores, juniors at at Stanford.
</details>

>> 你有做过调查吗？各工具的市场份额是怎样的？

<details><summary>Original English</summary>
>> Do you do you survey them? What's the market share?
</details>

>> 调查他们具体用什么工具吗？目前还没有，但这个建议不错，我会去做的。

<details><summary>Original English</summary>
>> Was that like what what tools they use? Okay. I haven't yet, but that's a good call. Yeah. Yeah. I I will
</details>

>> 搞个尖锐点的：看斯坦福的学生到底更喜欢谁。

<details><summary>Original English</summary>
>> be spicy. Stanford prefers.
</details>

>> 哈哈不会。我觉得通过学校渠道，大部分供应商应该都提供教育计划吧？所以……

<details><summary>Original English</summary>
>> No. No. Well, I think through like the the university, I think they have some the educ like most of the the the providers have like an educational program, right? So,
</details>

>> 确实，他们面向学生的方案给得非常大方。

<details><summary>Original English</summary>
>> I mean, yeah, they're they're very generous on plans for students,
</details>

>> 对吧？所以即便在开课之前，我想他们默认就配了 Claude 的授权，可能还有 Cursor 的授权，大概也有 Cognition 的授权吧。我不太确定，这点你们可能比我更清楚。但我在此基础上额外争取到的是：我不希望学生受限于每月 20 美元的订阅额度，如果大家想拉满 Token 测出极限、看看究竟能做到什么程度，那就应该尽管去试。

关于合作伙伴的事我稍后再细说，但我通过四处联络额外争取到的，就是给学生提供更多的额度。比如 Factory 也参与进来了，Cognition 的团队也加入了，还有 OpenAI。

不过言归正传，关于开源合作伙伴，我当时的想法是：在培养下一代学生时，我最担忧的问题之一，正如 Swix 所言，如果大家都在说“他们要完蛋了”，未来会怎样？大家几乎有一种要被时代抛下的焦虑感。而我认为导师制是一个极其重要的环节，能够带动所有人成长，确保在两拨人之间不至于产生巨大的断层——一拨是在编程智能体出现前就已经在行业里的资深人员，他们门儿清，引入编程智能体后变得极强；而另一拨则是初出茅庐的新人，只能原地发懵：“我们现在该怎么办？”

因此，某种程度上的目标就是：既然编程智能体这么强，那我希望把大家置于真实的复杂环境之中，去处理大规模的复杂代码库。我们将与一些在我看来最顶尖的 AI 原生代码库合作，它们都专注于 AI 领域，要么本身就是编程智能体，要么是在现代体系下为智能体打造周边工具。我希望学生们深入参与到这些项目中去，要求平时作业的一部分就是切实为这些项目贡献代码。在参与这些项目的过程中，学生会真正与项目维护者直接交流，维护者会审查他们的代码，帮助他们建立起关于优秀软件架构的心智模型。通过这种方式，优秀软件设计的接力棒得以切实传递下去，而据我所知，绝大多数学生是很难获得这种机会的。

当然，附带的好处就是，我确信他们当中的一部分人会被顺手挖走并录用……

<details><summary>Original English</summary>
>> right? Right. So I think by default even before the class there's like you know claude license I imagine cursor license there's like probably a cognition license as well. I don't know you might know that better than I do but what I was able to also just acrewue on top of that was hey like if I don't want people to be bottlenecked by like the $20 a month subscription like I want you guys to go if you want to like token max something just to see what's possible then then you should and so and I'll come back to the the partners but the the additional thing I was able to to crew through instead of talking to folks was like additional credits for students. So like factory is also getting involved. The recognition folks are getting involved in open as well. But anyway, so so so for the the open source partners, I I sort of like was like, okay, one of the things I'm most concerned about when it comes to educating the next kind of generation of of students is that if everyone is saying kind of to Six's point, like they're cooked like you know what's going to happen to them there. There there's almost like this sense of like them being left behind. And I think that mentorship is like a really important kind of piece of just upleveling everyone and making sure that there isn't this like massive gap that folds that that occurs between you know the senior people that have already been in the industry before coding agents and know what's up and they adopt coding agents and they become amazing and then the juniors that are just like okay now what do we do? So in a sense one of the the kind of goals was hey coding agents are really good. I want to put you guys in situations where you're dealing with complex code bases large code bases at scale. We're going to work with some of like what I think are among the best like AI native repos, you know, that all do AI focused things or either coding agents themselves or building tools in the service of agents, you know, in the modern world. I want you guys to get involved with these projects. I want part of your assignments to be actually contributing to these projects. In the course of being involved with those projects, you will actually be talking to the maintainers. They will be reviewing your code. They will be helping you build mental models of like good software. In that way, there's effectively this like passing on of like the guard of true good software design in a way that you know I don't think most students get the opportunity to do. And then there's the benefit of course that like I'm sure some of them will get you know poached and picked up
</details>

<!-- chunk 3/18 -->

作为做好那些作业的一部分。

<details><summary>Original English</summary>
as part of the doing well in those assignments.
</details>

>> 是的。其中一件有意思的事，你知道，不管怎么说，如果我不说这句我可能会挨不少骂。我觉得你用“完蛋”（cooked）对应“极强”（cracked）是为了戏剧效果，但你知道，把极端情况摆出来确实挺好。嗯，当然。当然。

<details><summary>Original English</summary>
>> Yeah. One of the interesting things you know for for what it's worth get a bunch of hate if I don't say this. I think you say cooked and versus cracked for dramatic effect but you know like it's just nice to to state extremes. Um, sure. Sure.
</details>

>> 是的。所以，所以也许我们应该深入讨论一下课程大纲的细节，或者在顶层设计上你还有其他想探讨的吗？

<details><summary>Original English</summary>
>> Yeah. So, so maybe we should go into the sort of detail of the curriculum or is there anything else you want to explore at a top level?
</details>

>> 哦，没有了。我是说，那……非常有帮助。是的，全都在那儿了。

<details><summary>Original English</summary>
>> Oh, no. I mean like that that's uh very help. Yeah. All that's there.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 我能……我有一些高层面的问题，关于学生使用工具、最佳实践，你是支持它充当个人导师之类的角色吗？嗯，我猜学生也会接触到这个。所以在我们直接深入课程之前，你在这方面有什么指导建议吗，关于……

<details><summary>Original English</summary>
>> Can I I have high level questions about students using tools, best practices, are you pro it like individual tutors? Um I'm assuming this will also be picked up by students. So you know before we dive straight into the course just anything you have guidance on there for
</details>

>> 比如具体指的是哪方面？

<details><summary>Original English</summary>
>> like in terms of what
</details>

>> 对，你说过你对教育充满热情，对吧，这方面也存在一种偏见：一方面是教师、教授该如何使用它，另一方面是学生怎样才能最好地利用这些工具，而不是仅仅……

<details><summary>Original English</summary>
>> yeah you said you're passionate about education right like there's also a stigma of one side is how how do teachers professors use it and then how can students best use these tools that's not just
</details>

>> 把你的作业扔进去……

<details><summary>Original English</summary>
>> throw your assignments in
</details>

>> 它差不多就能一步搞定。如果你在这方面有什么想法的话，要怎样才能依然学到东西？

<details><summary>Original English</summary>
>> it can kind of oneshot it. How do you still learn like if you have anything there?
</details>

>> 对。对。我觉得我在里面还是布置了一些作业，这些作业的目的并不是要成为世界上最难的东西，而是更多地关注概念层面的东西，比如概念——比如更偏概念性的内容，比如你懂的，一个 skill 到底意味着什么，或者类似这些工具更偏战术层面的技巧，比如面向 Agent 的代码库（agent ready code bases），像 AGENTS.md 这类东西。所以会有一定量的基础普及：嘿，如果你还没听说过这些术语，那就把它们了解起来。不过我确实认为，在检验这些工具方面的绝大部分学习，都将发生在开源项目（OSS）以及期末大作业中；期末项目是非常开放的，他们必须去探索一些有意思的东西。

<details><summary>Original English</summary>
>> Yeah. Yeah. And I think that there's I still have some assignments thrown in there which I think are not intended to be the hardest things in the world but are meant to be more about like concept concepts like more conceptual things like you know what does a skill mean sort of like the maybe more of the the tactical of some of these tools skills like you know agent ready code bases like agents MDs things like this. So there's a certain amount of just hey if you haven't heard these terms kind of get up to speed on them. I do think most of the learning though in terms of the kind of putting the tools to the test will happen both in in the OSS and then also in the like the final project where it's like very open-ended and they'll have to just kind of explore something interesting.
</details>

>> 太酷了。好的。

<details><summary>Original English</summary>
>> Cool. Okay.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以，所以也许……对。我就是想聊聊，让我们先过一遍第 1、2、3、4 到 10 周……

<details><summary>Original English</summary>
>> So, so maybe Yeah. I just want to talk about let's go through 1 2 3 4 10
</details>

>> 呃，然后我们再深入探究。基本上就是先广度优先。

<details><summary>Original English</summary>
>> uh and then we'll dive in deeper. So like breath first basically.
</details>

>> 当然。当然。可以。

<details><summary>Original English</summary>
>> Sure. Sure. Yeah.
</details>

>> 所以我们从内部机制和编程 Agent 开始。你教大家如何编写自己的 Claude Code 克隆版。现在它开源了，这一点非常有帮助，然后……

<details><summary>Original English</summary>
>> So we start with internals and coding agents. You teach people how to write their own cloud code clone. It's very helpful that it's now open source and then
</details>

### 十周课程体系概览

>> 对，对，对。所以，第一周全是 harness 的内部机制，你知道，就是从头构建一个克隆版 Agent；第二周更多是，好的，现在假设有了这个，我们该如何开始思考大规模的上下文工程（context engineering at scale），超出基础的常规提示词；然后我认为与此相关的是，在这个过程中思考工具设计、MCP。大家有一段时间对 MCP 有很多批评，但我依然支持 MCP，我时常能见到它，所以我认为目前它是一个已经存在的标准，而且我认为它会继续存在下去。所以，讨论有效的工具设计，那是第二周的内容。第三周我想更多是关于 skill，以及从简单的单一用途工具扩展到更像流程（procedures）的东西意味着什么，在那里我们将讨论 skill，你知道，那开始引入 Agent 的自动化。第四周很大程度上更多是关于一些基础模块，即你如何定制一个 Agent？这些包括像 Agent 配置文件（诸如 AGENTS.md、CLAUDE.md）、hooks，你知道，还有 subagents。现代 harness 中存在很多不同的机制，你可以用于不同的目的，所以我想让学生接触这些。面向 Agent 的代码库，这大概是我最喜欢的话题之一，尤其是对于那些准备进入工业界并思考大规模代码的人来说非常相关，本质上就是：拥有一个能够被 Agent 高效摄入和理解的代码仓库到底意味着什么？因此会深入思考服务级边界的设计权衡，还有文档、可验证性以及诸如此类的事情。嗯，这就是第五周。对，第六周大概是 Agent 化代码审查（agentic code review）。在这部分我认为有趣的是，顺着第五周面向 Agent 的代码库继续延伸，进入第六周更多是关于：好的，为了……代码审查现在正成为一个瓶颈；我不确定学生们是否……除非他们做过很多，他们中有些是硕士生，在工业界待过，但很多人并没有见过这种情况；但对今天大多数使用代码 Agent 的人来说，我们都正在经历代码审查中出现的一种新瓶颈，那么我们该如何疏通它，或者稍微缓解一下这个瓶颈？那里有哪些机制？比如可验证性及诸如此类的事情，以及我们如何将其延伸到代码审查过程中。第七周，安全。显然，我认为当时有这么一点——去年课程里也有这部分，而我这次想强化它。我是说，对于任何执行大量操作的自主系统，我们看到今年尤其有很多东西被黑客攻击，不仅包括一些核心软件，从 Vercel 到大模型网关（LLM gateways）。所以我想花些时间讨论一下安全领域存在哪些新的攻击途径，以及我们可以如何缓解其中的一部分。第八周是后台 Agent（background agents）。这里我想开始触及的是，你知道，你基本上如何在许多不同的产品和服务领域运行 Agent。不仅是在传统意义上的 IDE 里，而且还包括在你的代码库、你的代码仓库中，在 CI/CD 期间基于触发器运行的东西；甚至在基于事件时触发的东西，比如 SRE 风格的机器人。你甚至要如何构建这样一个系统？我认为在过去这一年里，很多公司开始发布他们的技术博客，比如 Ramp 的 Inspect，Spotify 有他们自己的版本，还有 Stripe 的 Minions，所有这些团队都在撰写非常酷的文章，介绍他们为了实现这一点而构建的内部基础设施。我想涉及这部分内容，让大家了解那是什么。是的，这一周……对，这一周更多是关于当你在现代团队中时会发生什么，以及团队级基础设施的核心部分。涵盖从大模型网关，到 MCP 门户（即大规模 MCP），然后还有如何看待正在演变的角色。这可能有点偏软性。现在的情况是……那种常见且可能不算非常细致的说法是“每个人都是建造者”，但我希望能稍微更深入一些，看看究竟什么东西正在被真正纳入吸收，究竟有哪些过去不存在的角色正在演变或涌现。在可防御的技能体系（defensible skill set）方面，学生们应该考虑哪些过去可能并不成立的事情？所以会有很多更多偏向团队协作动态的考量。然后，是的，所有这些都朝着“软件工厂”逐步构建，我认为这正是当今很多人最关注的事情。一旦我们开始建造工厂，在这一切之中人类依然存在于哪里？围绕人类参与而有意设置的全新关卡又在哪里——比如意图（intent），比如构建可验证的系统？当极端情况下可能 80%、90% 的代码都完全由 Agent 驱动时，会发生什么？我们在这一切之中又处于什么位置？所以，是的。

<details><summary>Original English</summary>
>> yeah yeah yeah so uh week one it's all internals of harnesses you know kind of build a cone agent from scratch uh week two is more okay now assume that there's how do we start thinking about like context engineering at scale u so beyond just vanilla prompting uh and then I think coupled with that is just um in in doing that thinking about like tool design MCP you know people I think for a while MC was getting a lot of hate I'm still pro MCP I see it all the time and so I think that there's At this point it's a standard that's existed and I think it will continue to exist. So you know talking about that effective tool design uh that's week two. Uh week three I would say is more about just like skills and like what does it mean to like extend beyond simple single purpose tools to more like procedures and that's where we'll talk about skills and you know that kind of starts leading into like the automation of agents. Um week four is is a lot of just more of like the foundational pieces of how can you customize an agent? Um this is things like agent config files alla agents MD cloud MD hooks um you know kind of sub aents like there's a lot of different mechanisms that exist in modern harnesses uh which you can use for different purposes so I want to expose students to that agent ready code bases this is probably one of my favorite topics it's like and this is especially relevant for folks that are going into like industry and thinking about code at scale is you know essentially what does it mean to have a repo that's ready to be ingested consumed effectively by an agent and so thinking a lot about you know the trade-offs of designing of kind of service level boundaries but also docs and and verifiability and things of that nature. Um so that's week five. Uh yeah week six sort of agentic code review. Um and here I think what is interesting is thinking also kind of extending from week five week five around codebase like agent ready code bases going to week six is more about like okay in order to like code review is now becoming a bottleneck which I don't know that students unless they you know have done a lot of some of them are master students so they've been in the industry but a lot of them have not seen this but for most people that are using code agents today we're all experiencing something of a new bottleneck in code review so how do we unblock that or sort of unbottle the the bottleneck a little bit um what mechanisms are there there and so verifiability and you know things of that nature and how we can extend that into the code review process week seven uh security I mean obviously I think there was a point so this was in last year's class as well and this this I wanted to reinforce I mean with any autonomous system taking a lot of actions we're seeing a lot of this year especially a lot of things getting hacked um you know not least of which are just some of the the core pieces of software from from versell to you know uh gateways LM gateways entirely so I want to spend some time just like talking about what new attack vectors exist exist in security and and you know how we can mitigate some of them. Uh week eight is background agents. So this is uh what I want to start touching on here is you know how do you like basically run agents in many different like product service areas. Uh not just in what was traditionally an IDE but also having things that are like based on triggers in your codebase in your repo at you know during CI/CD. uh things that get triggered even when you know based on events things like you know S sur style bots. Um how do you even build a system like uh I think this past year was when a lot of companies started releasing their posts like ramp inspect um there was Spotify has their own version of this you know I think Stripe Minions so all these folks were doing really cool write-ups of like their internal info they were building to do this I wanted to touch on that uh get people exposed to what that is. Yeah, this is um yeah, this one is uh more on like what happens when you're in in a team in in the modern world and sort of like the core pieces of of team level infrastructure. So everything from uh LM gateways to you know MCP portals which is like MCP at scale and then just also how to think about the evolving roles I would say. So this is maybe a little bit like a soft thing. It's like what what what is now, you know, and the and the the vanilla maybe like not super nuance thing to say is like everyone's a builder, but I want to like go a little bit deeper beyond that and like sort of like what thing is actually getting subsumed, what what roles are actually um either evolving or emerging that didn't once exist. Um what should students think about in terms of defensible skill set that's maybe wasn't true before? Um and so a lot of more like team dynamic type type considerations. And then yeah, this is uh it all kind of builds up toward the toward the factory which I think is top of mind for now um for a lot of folks today. Once we're we're building factories, where do humans still exist in all that? What is the you know where are the new choke points that that are intentionally there around around human involvement things like intent things like uh setting up a verifiable systems and what happens in the limit when maybe 80 90% of code is fully driven by just agents uh where we we kind of filled into all that. So yeah,
</details>

>> 很扎实的十周内容。呃，我本来想说，你知道，其中一些相比其他部分是更为成熟的模式，而且我觉得大家需要明白，并非所有这些都是已经定论的科学。

<details><summary>Original English</summary>
>> nice solid 10 weeks. Uh I was going to say like you know some of these are more established patterns than others and I I think people need to know that like not all of this is settled science.
</details>

>> 当然。

<details><summary>Original English</summary>
>> Sure.
</details>

>> 呃，你知道，但这些全部——我会认可所有这些都是大家在讨论且你应该知道的事情，只是我们知道了这些开放性问题，但我们可能还不知道答案。

<details><summary>Original English</summary>
>> Uh you know but it is everything I'll endorse everything as like things that people talk about and you should know you just we know the open problems we may not know the answers.
</details>

>> 完全正确。是的。是的。而且我是说，想想看甚至……我是说你大概……

<details><summary>Original English</summary>
>> That's absolutely right. Yeah. Yeah. And I mean think even um I mean you probably
</details>

<!-- chunk 4/18 -->

### 软件工厂与持续实验

你对此有自己的版本。我很想听听你认为哪些地方仍然不那么站得住脚，或者说并非不可动摇，而是还没完全定型。但你看，即使像软件工厂，我们谈论的是黑灯工厂，还是这种半开灯的工厂？我觉得这里面甚至存在一个光谱。是的。你看，还有那些处于最前沿的人，比如 Warp 和 Factory 这类正在建造工厂并将其作为服务出售的公司。你看，即使是他们，也只声称有百分之三十几是完全由生成式驱动的贡献。那么在极限情况下这意味着什么？这很难说。

<details><summary>Original English</summary>
have your own version of this. I'd be curious to hear what you think is is still not as defensible but or not defensible but not as set in stone but you know even like the the software factory are we talking about like dark factories are we talking about like these sort of half lights on factories like I think even there's a spectrum there. Yeah. And there you know there's the people that are on the on the very frontier like like the warps and the factories that are that are like building factories and selling them as services and you know even they only claim like 30 some% of even that of of like fully you know genetically driven contributions. So what does that mean in the limit? It's it is hard to say and
</details>

>> 而且有些人走到了非常非常极端的黑灯工厂路线，然后出来说“大家，我错了”。对吧，所以我们在……讨论过这个。

<details><summary>Original English</summary>
>> and there's people who went very very far dark factory and then came out saying I was wrong guys right so like uh we covered that on the um
</details>

>> 只要意识到，并不是所有人……他们当时可能确实相信自己说的话，但他们有权改变想法，而且他们确实会改变。

<details><summary>Original English</summary>
>> just be aware that you know not everyone they they probably believe the things they saying at the time but they have the right to change their mind and they do
</details>

>> 甚至 Boris 最近发推特说，是的，我经常犯错。

<details><summary>Original English</summary>
>> and even Boris recently tweeted that like yeah I am often wrong
</details>

>> 而且大家因为他创建了 Claude Code，就把他的话奉为圭臬。而我觉得，不，有时他自己都不认同自己。

<details><summary>Original English</summary>
>> like and like everyone is like because he created clock code is like treating his word as gospel and I'm like no well sometimes he disagrees himself
</details>

>> 是的。

<details><summary>Original English</summary>
>> yeah
</details>

这没关系。我的意思是，这又不是政治，对吧？我们仍然是科学家，是工程师。我们受制于……我并不自诩为教条主义者，但你看，我只是希望人们去实验。我认为这也算是一条原则。你之前必须有原则，就像实验一样。我的意思是，你只需要准备好去尝试。很多时候，当我做这类讲座或与人们讨论这些事情时，他们会问，有这么多新东西出现，我该怎么跟上步伐？其实就像每天实验十分钟这么简单。就是花大约十分钟去做一些你以前没做过的事。如果你以前用传统方式解决某个问题，现在出现了一个你想尝试的新工具，或者一个新的框架之类的，仅仅花时间——甚至可能只是用那种新事物去解决完全相同的问题——单凭这一点就能弥补大部分差距。

<details><summary>Original English</summary>
And and that's okay. I mean, like this isn't politics, right? This is we're we're still scientists. We're engineers. We're we're subject to I don't claim to be dogmatic, but you know, I just want people to experiment. I think that's like a principle as well. You have to have principles earlier. Just like experimentation. I mean, like you just have to be ready to and often times when I sort of like give sort of these lectures or or talk to people about this stuff, they're like, how do I there's so much going on. How do I stay on top of this? And it's like, you know, there's something as simple as just like experimenting for 10 minutes a day. Like just spending some 10 minutes doing something that you didn't do before. If that's a traditional way that you were solving a problem, there's now a new tool you want to try or a new like framework or something and just spending maybe even doing the exact same problem just with that new kind of thing is is is alone will cover most of the gap.
</details>

### 代码审查与 Agent 就绪度

>> 是的。我想提一下，比如在你说到代码审查的那周，你列出了 Cognition。

<details><summary>Original English</summary>
>> Yeah. Uh I will call out so some of your uh for example you have cognition on the week that you're talking about code review.
</details>

>> 我实际上和 Silas 在 Devon review 上合作过。

<details><summary>Original English</summary>
>> Uh I actually did work with silus on devon review.
</details>

>> 确实。对。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 相当不错，我想说，这类东西很难做基准测试。虽然有一个 review bench，但没人用它。不过定性来看，Devon review 确实相当不错。

<details><summary>Original English</summary>
>> Pretty good I would say like you know it's hard to benchmark these things. There is a review bench. No one uses it. Um, but like qualitatively Devon review is pretty good.
</details>

>> 我们也在用你们的产品。那也是，对。所以 Monaco 确实在使用 Devon。而且 Silas 去年做过演讲，Silas 非常优秀。

<details><summary>Original English</summary>
>> Well, we use you guys. That's also Yeah. So, so Monaco does use Devon. Oh, and that's that's I mean and Sus actually spoke last year and so I mean Sus is great.
</details>

>> 就是超级超级聪明。不过，是的，我们在用你们的产品。所以我想，在我们采样的众多代码审查工具提供商中，我们确实在很多用例上收敛到了 Devon。

<details><summary>Original English</summary>
>> It's just super super smart. But um yeah, we we use you guys and so I was like okay among among the providers of of kind of code review tools that we and we sampled a lot of them. Um we actually did kind of converge on Devon for a lot of use cases.
</details>

>> Silas 这些天其实更多在模型端，实际负责的是 Walden。

<details><summary>Original English</summary>
>> Besides actually more model side these days and then actually it's Walden that you want.
</details>

>> 对，对，对。我也在和 Walden 交流。我也想顺便提一下 Factory，因为谈到 Agent 就绪度，他们一直非常关注这个，他们围绕这一点构建了 signals 工具。你们在用吗？有什么看法？

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. I Yeah, I was talking to Walden as well. I will also shout out you know from factory because uh you know talking about agent readiness they've been all about that they build signals tooling on that do you guys use that opinions?
</details>

>> 是的。我们确实在使用我们自己的一套 Agent 就绪度方案。Eno 也很出色。我觉得他们在这条赛道上走得非常早。他在演讲中把这点系统化了，我记得是在 AIE，什么时候来着，去年……我忘了具体时间，但他其中的一场……是的，在欧洲，非常棒的演讲。在某种程度上，我认为那是超前于时代的。所以我觉得只有一个人最适合谈论这个，我非常希望能给他们聚光灯，他们也非常兴奋。

<details><summary>Original English</summary>
>> Yeah. So so we do use agent readiness of our own of our own kind. I mean, Eno is is awesome as well. Like I I think they were super early on this on this train and I think when he codified that in his talk, I guess at AIE, what was that like last I forget when it was, but one of his Yeah. Europer um just fantastic talk and I think it was kind of in a way ahead of its time and so I was like there's only one person that I could see being like the most most appropriate person to talk about this where I like really want to give them the spotlight and they're super excited.
</details>

>> 是的，这很有意思。当时我在 COG，我们在讨论这些内容，觉得我们需要形成一些观点。结果 Factory 就在我们讨论的那周推出了一个完整的产品。我当时就想，好吧，你们赢了。

<details><summary>Original English</summary>
>> Yeah, it was funny. I was at COG. we were talking about this stuff and like we're like okay we need to form some opinions about it and then like factory like shipped a full product on it that week that we were talking about it I was like okay you won
</details>

>> 大家都认同同样的事情。

<details><summary>Original English</summary>
>> like I mean like everyone kind of agrees on the same things
</details>

>> 剩下的只是要不要把它做成仪表盘的问题。

<details><summary>Original English</summary>
>> and it's just a question of like do you want to turn it into a dashboard
</details>

>> 是的，对，对。

<details><summary>Original English</summary>
>> yeah yeah yeah
</details>

>> 因为它就是一个仪表盘。

<details><summary>Original English</summary>
>> because it's a dashboard
</details>

>> 没错，没错。但你看，这其中是有价值的。我觉得从营销的角度来看，他们抓住就绪度报告这一点做得很成功。我确实和别人聊过，我会经常向其他人推荐这个，说你们应该运行自己的报告。当然，现在大家都有了开源版本，但我认为这些原则极其重要。

<details><summary>Original English</summary>
>> right right but you know there's there's value and like I think they did well from a marketing perspective jumping on like the the radius report and I've definitely spoken to you know I I will regularly kind of pitch that to other people and and say like yeah you should run reports of your own ind and um you know of course now people have open source versions of it but but I think the the principles are super important.
</details>

### Claude Code 与 Coding Harness 的本质

>> 是的。你想逐条过一遍，还是有其他内容？我可以逐条过。

<details><summary>Original English</summary>
>> Yeah. Uh do you want to go piece by piece or do you have any other things? I I can go piece by piece.
</details>

>> 好的。第一个，对，你重点关注了 Claude Code，但同时也有作为开源赞助者的 PI。这是怎么回事？好吧，这个可能稍微偏营销一点，但有一点我想强调，去年我也明确表达过，我并没有为任何工具代言。我不认为这是对待这类事物的正确方式。工具总是来来去去的。坦率地说，去年开课的时候，Claude Code 并没有那么火爆，也没有被广泛接受。Boris 当时只有 4000 个 Twitter 粉丝，现在已经有不知多少万了，我甚至不知道具体数字，但他的粉丝非常多。所以 Claude Code 确实横空出世了。我觉得……

<details><summary>Original English</summary>
>> Yeah. Okay. So the first one right uh you focus on cloud code but then you also have pi as open source sponsor. What's up? Okay. So so okay this one is maybe a little bit more marketing but but okay um the one thing I do want to highlight and I've made that I also made that clear last year but I'm not a I'm not endorsing any tool. Okay. like like I I don't I I I think that is uh the wrong way to approach something like this. Um there are tools that come and go and when you know transparently when when the class was taught last year cla code was not as popular. It wasn't as like rarely accepted. Boris was only at 4,000 Twitter followers and now he's at you know whatever million. I don't even know if he is but you know like he's at a lot of followers. Um so so Cloud Code has really like emerged on the scene. Um I think
</details>

>> 我觉得，是的，我们在播客里请来 Boris 和 Cat 时也低估了 Claude Code。当时它才推出两个月左右。我其实没怎么用过，用过一次，一次查询花了我 50 美分。我就想，谁会用这个？

<details><summary>Original English</summary>
>> I think yeah I think we we also underestimated Cloud Code when we had Boris and Cat on the podcast. It was like 2 months old. I hadn't really like I used it once. A query cost me 50 cents. I was like, who's going to use this
</details>

>> 完全是。它还在测试版阶段持续了一阵子。但我觉得他们在模型还没准备好时就把它构建出来了，这很值得称赞。就像你经常听到的那样：为模型未来的发展方向而构建。

<details><summary>Original English</summary>
Totally. It was still in beta for a while. But I think it's good on them for how they built it before the model was ready. Like you hear so much build for where the model will go.
</details>

>> 完全正确。

<details><summary>Original English</summary>
>> Totally.
</details>

>> 极其有野心。当时模型还没那么好，你感觉不到。然后，我们看到了它的发展成果……

<details><summary>Original English</summary>
>> Super ambitious. Like models were not that good. You couldn't feel it. And then ah we see we see that it's where it came
</details>

>> 很有意思，因为去年他做演讲时，我记得那是一套非常高层概括的幻灯片，但我记得其中一张幻灯片写的就是“为模型 6 个月后的水平而构建”。那是去年的 10 月左右。我完全能理解他为什么提出这个观点，如果他提前知道 6 个月后 Opus 会达到什么水平的话。因为我认为那也是一次巨大的突破，可以说也是课程发生如此大变化的原因之一，对吧？在这些 Agent 中，在长时间运行的 Agent 式编程任务中，围绕真正的自主性展开了一场巨大的军备竞赛。但回到你的问题，我并不是在为 Claude 代言。当然我用 Claude Code，也用其他工具。但在这里，我更关注的是现代 coding harness 应该是什么样子的。我写过一篇博文，实际上……是的，就是这篇，今年早些时候写的，我在里面拆解了一些类似的原则。长话短说，凭借几乎只需初级算法水平的理解，你就能定义出一个 Agent 式循环，完成所谓的编码 Agent 的大部分核心功能。当然还有各种花哨的功能，这里没有子 Agent，没有 MCP，也没有那些花样。但如果你想要一个能与你对话、能够切实编辑你的文件并且可以用它来做相当复杂任务的东西，它不需要超过 200 行代码。所以，在教育中我尝试做的大量工作，就是剥离掉那些所谓的秘诀，展示其真正的核心。毕竟面对的还是学生，你要教的是……

<details><summary>Original English</summary>
>> that it's Yeah. It's funny because when he gave his talk last year, I remember um you know it was like a very high level sort of set of slides but I remember one of the slides was literally like built for where the model is going to be 6 months from now. And this was like October of last year. And I can see why he would have made that point if if he knew in 6 months where like Opus was going to be cuz that was also what I think was a huge unlock where I would argue was one of the reasons why the curriculum changed as much as it did, right? Where there was certainly this huge arms race around true like autonomy in these agents like longunning agentic coding agent tasks. But yeah, so so you know back to your points like less on I'm not endorsing cloud. I mean you know cloud code I of course I use it and and use other things as well but but here I was more about like the what does a modern coding harness look like. I wrote a blog post that actually uh yeah this one where this was yeah earlier this year where I sort of broke down some of some similarish principles. The TLDDR was that you know you could sort of through like pretty much introductory algorithms level understanding you could just define like essentially a gentic loop that does the bulk of what you would call a coding agent. Um, and of course there's like bells and whistles. There's no sub agents, there's an MCP and none of that stuff. But if you want to see something that you talk to and then it literally will edit your file and you can do pretty sophisticated things with it. You, it doesn't require more than 200 lines. So I, you know, a lot of what I try to do in education is to try to like peel away the stuff that's like the secret sauce and show that like really at its core. I mean, these are still students and you want to teach
</details>

<!-- chunk 5/18 -->

概念性原则。这里面并没有比斯坦福一门叫 106B 的课程更深的内容。那门课就像是算法的入门介绍。构建类似这样的东西，你根本不需要超过 106B 水平的知识。所以，就是这样了。全都在这里了。

<details><summary>Original English</summary>
conceptual principles. There's nothing more to this than in Stanford there's this class called 106b. It's like the introductory introduction algorithms. You don't need more than one 6B to build something like this. And so there you go. There it is.
</details>

>> 考虑到你已经讲过这门课了，学生们有什么反对意见、问题，或者你观察到他们有什么困惑吗？

<details><summary>Original English</summary>
>> Given that you already taught this class, any push back, any questions, any weirdness that you observe from the students
</details>

>> 关于——

<details><summary>Original English</summary>
>> on
</details>

>> 他们有什么不懂的？他们的问题似乎集中在哪些方面？

<details><summary>Original English</summary>
>> what do they not get? What do they ask seem to cluster questions around?
</details>

>> 嗯，你是说针对现在这个特定概念，还是笼统来说？

<details><summary>Original English</summary>
>> H you mean like now that this like this particular concept or just in general?
</details>

>> 呃，这个概念——

<details><summary>Original English</summary>
>> Uh this concept
</details>

>> 关于——关于——

<details><summary>Original English</summary>
>> of of like
</details>

>> 像是从零开始构建它，然后像你那样去做，因为这基本上就是你针对 pi 所需要做的。

<details><summary>Original English</summary>
>> of like of like building it from scratch and then like doing doing what you did because this is basically what you needed for pi.
</details>

>> 对，对，对。完全正确。是的，对，其实并没有，我想他们……关于这个想法本身，我完全没有收到任何反对意见。我认为他们实际上更多只是……他们大多数人都是使用者，对吧？大多数学生最终只是使用这些工具。我认为他们在课程学习中即便有接触，也接触不到多少关于剥开洋葱看本质的内容，对吧？而且我认为……所以这周是讲 Harness（测试/运行框架）。周二的第一堂课，你知道的，讲讲考勤安排等等所有那些琐碎事情。但接下来的前半部分，你知道，第一部分真正的课程内容，就是那 200 行的一个框架；然后昨天我们进行后续跟进时，就是我们实际拿了 Claude Code，然后你知道有这些代理工具，就是你可以用来拦截请求的代理工具——

<details><summary>Original English</summary>
>> Right. Right. Right. Exactly. Right. Yeah. Yeah. Right. So, yeah, it's uh it not really I think they're I haven't received any like push back on on like this idea at all. I think they're actually more just most of them are consumers, right? Most of most of the students do just like end up using the tools. I don't think that they get a lot of exposure um if any certainly in the course work around peeling that onion back, right? And I think um so this was the week of the harness. So, so Tuesday first lecture, you know, logistics, blah blah blah, all that stuff. But then first half is you know the first true like bit of curriculum is the 200 lines of of of like a of a harness and then yesterday when I had sort of the follow-up to that is like we actually took cloud code and then you know you have these like proxy things these like proxy tools where you can intercept the request
</details>

>> 代理。

<details><summary>Original English</summary>
>> proxy.
</details>

>> 是的。没错。确实如此。对，使用那个工具去拦截请求和响应，查看底层细节，看看那里到底发生了什么，然后就像是：好的，我之前确实说过你们可以用 200 行写出 Claude Code，但说真的，好，这里是真正的 Claude Code。所以我实际做的就是，我拿了 Opus 55——就是那个你知道的刚发布 2 天的模型——我说：这就是我拦截到的那些请求，这里清清楚楚展示了到底在发生什么，这是 Prompt，这是 System Prompt，这是 Plan Prompt，这是 Compaction Prompt。然后我们就那么全部过了一遍，展示给学生们看，所以现在他们切切实实拥有了一个自己能够理解的业界顶尖的 Harness。

<details><summary>Original English</summary>
>> Yes. Exactly. Exactly. Right. to use that uh use that tool intercept requests and responses look under the hood see what's happening there and then then like okay I did say you have clawed code in 200 lines but really okay here's like actual clawed code and so what I literally did is I took Opus 55 so this like you know model 2 days old and was like this is I intercepted those requests here's exactly what's going on here's the prompt here's the system prompt here's the plan prompt here's the compaction prompt and then we just like went through all of that and sort of showed it to students so now they really really have like a state-of-the-art harness that they can understand Yeah,
</details>

>> 能获得这三个层次真好，就像学生很大程度上是使用者；然后这是循环中的基线 Agent；接着是真实投入使用的那一个。我也很喜欢你在博客文章里附带的视频演练。你有没有发现学生们处于两极分化状态：有些人是重度用户，使用得非常多；而对某些人来说，如果你了解 Agent 的工作机制，可能会觉得这相当简单明了，对吧？

<details><summary>Original English</summary>
>> it's nice to get those three levels like students are very much consumers. Here's the baseline agent in a loop and then the real one. I like how you have a video walk through of your blog post as well. Do you see students are on like extremes of some people are power users. They consume a lot. For some people, you could assume that this is kind of very straightforward if you know how agents work, right?
</details>

>> 你在课堂环境中如何去平衡这一点？比如你会倾向于迁就平均水平吗？

<details><summary>Original English</summary>
>> How do you kind of balance that in the classroom setting? like do you tailor towards the average?
</details>

### 学生构成与课程受众

>> 是的，我认为这有点自我筛选的性质，因为全部课程大纲都在这里，对吧？课程大纲早就公开了，我的意思是，至少有几周了，我想虽然我是几周前宣布的，但实际上筹备可能至少有一到两个月了。所以如果你去找，大概是能找到的。额，我觉得现实情况是，如果学生对此不感兴趣，他们就不会……他们就根本不会来，他们会选择不来上课。我发现很有意思的一点是，虽然确实仍有学生来上课，但同时也有很多来自斯坦福其他院系的博士后；有很多人表现出了跨学科的兴趣，比如来自病理学、医学类领域，甚至是其他非纯计算机科学的随意某个工科领域的学者，他们都过来听课，也很有兴趣接触这些内容。还有很多商学院（GSB）的学生、MBA 们，他们大概也是想学习如何不再依赖技术联合创始人，不管他们的动机究竟是什么。但是——

<details><summary>Original English</summary>
>> Yeah, I think it's a bit self- selecting because the curriculum is all here, right? So, the curriculum has been available since I mean, you know, at least it's like a few weeks and and I guess I announced it a few weeks ago, but it had kind of been in the works for like probably at least one to two months. So, if you looked for it, you could probably find it. Um, and I feel like the reality is if students are not interested in this, then they won't like they'll they just won't show up and you they will they will choose not to show up. What I'm finding that is interesting is there are still definitely students that show up but then there's also just a lot of folks from you know broader Stanford postocs at other departments there's a lot of like interdisiplinary sort of interests where folks that are in you know somewhere in pathology or like you know like medicinal sort of fields or or even like random other engineering fields that aren't pure CS that are coming in and also interested in in kind of getting exposed to this. also a lot of uh GSP students, MBAs um that also uh want to I guess learn how to not have a technical co-founder or whatever the motivation there is. But
</details>

>> 是的，所以顺便说一句，如果有人还没做过 MITM 代理这个练习，你真的应该去做一下。

<details><summary>Original English</summary>
>> yeah, so I I think by the way if anyone hasn't done the MITM proxy exercise, you should do it.
</details>

>> 是的，你会感到震惊的。额，Claude Code 拥有所有代码 Agent 中最长的 System Prompt，大约有 20,000 个 token。

<details><summary>Original English</summary>
>> Yes, you'll be shocked. Uh cloud code has the longest system prompt of all the coding agents. Something like 20,000 tokens.
</details>

>> 对，对。尽管……对，确实是那样。确实如此。是的。不过他们也把体积缩减了 80%。

<details><summary>Original English</summary>
>> Yeah. Yeah. Although uh yeah, that is true. That is true. Yeah. Yeah. Yeah. Although they've also reduced the size by 80%.
</details>

>> 是的，我知道。但随后它们又会增长，然后他们再删减，接着又再次增长。

<details><summary>Original English</summary>
>> Yeah, I know. But then they grow again and then they cut and they grow again.
</details>

>> 就像个跷跷板一样。

<details><summary>Original English</summary>
>> It's it's a seesaw.
</details>

>> 是的，没错。不，我觉得这很有意思。你会惊讶于里面塞进去的那些东西，有些东西实际上你有时根本用不上。

<details><summary>Original English</summary>
>> Yeah. Yeah. No, I think it's interesting. You'll be surprised like what goes in there that actually sometimes you don't use.
</details>

>> 有时它实际上暗示了某些工具的内部工作机制。

<details><summary>Original English</summary>
>> Sometimes it actually hints at the internal workings of some of the tools.
</details>

>> 额，你在那里有发现什么值得拿出来聊聊的酷炫东西吗？

<details><summary>Original English</summary>
>> Um anything that you found there that could be cool to talk about?
</details>

### 提示词与模型权重的演进权衡

>> 有啊。其实昨天我在讨论这个的时候就提到了这一点：我认为 Claude Code 当年最有趣的一点——而且我认为这也是它在受欢迎程度上一炮走红的部分原因——就是他们对极简主义的专注，对吧？所以在早期，他们是最早真正践行“用更少的工具做更多的事”这一理念的团队之一，对吧？倾向于利用 SQL，倾向于利用 Bash，倾向于利用那些功能强大如瑞士军刀般的工具，并让它成为驱动能力的核心部分。额，我认为他们在这方面的践行做得很棒。我认为这就是为什么他们能像当初那样大受欢迎的原因。我觉得当我在展示类似 System Prompt 的时候，情况就像是：大约两个月前还有一个不同的 System Prompt，现在他们的复杂性已经降低了，事实证明，曾经属于 System Prompt 的那些内容，比如甚至是如何使用 git，对吧？或者如何设置任务以及诸如此类的事情，现在都不再属于 System Prompt 的一部分了。人们实际上更期望这些内容被模型本身——比如模型权重——吸收。额，所以他们有点把许多此类学习经验更多地固化在了模型层面上。这恰好引发了一些有趣的思考，你知道，关于模型与 Harness 之间的对比，对吧？你该如何去权衡这种取舍？各家公司应该投资什么？你又应该投资什么，来真正突破自身能力的前沿？所以，我认为即使作为一个社区，我们也常常在这两者之间摇摆不定。额——

<details><summary>Original English</summary>
>> Yeah. No, I mean in fact yesterday when I was talking about this, it was a little bit of this like one of the things that I thought was most interesting about Claude Code back in the day and I think part of why it really blew up in terms of popularity was their focus on simplicity, right? So in the early days they're among the first to really lean into this let's fewer tools do more, right? Lean into SQL, lean into Bash, lean into like the things that are that are powerful like Swiss Army knife tools and have that be a lot of the driver of capability. Um I think they did a fantastic job leaning to that. I think that's why they they were as popular as they did. I think that when I presented something like the system prompt, it was like well there was a different system prompt about 2 months ago. It is now they have reduced in complexity and it turns out that now what was once part of the system prompt things like how to use even git, right? Or how to like set up tasks or things of that nature are no longer part of the system prompt. It's actually expected to be more kind of captured in the models like the model weights itself. Um so they've kind of baked in a lot of those learnings more at the model level. And that just raises interesting questions around, you know, the model versus the harness, right? And how do you kind of think through that trade-off? What do companies invest in? What should you invest in to really push the the the frontier of your own capabilities? And so I I think we still even as a as a community, we seesaw between the two a lot. Um
</details>

>> 我觉得你不能因为他们先扩充 System Prompt 然后又删减去责备他们。在某种程度上，这也是由于模型当时的状态所致，对吧？额，较弱的、较老的模型，你需要给它们提供“这是好的，这是坏的”这类的示例。然后很显然，到了某个阶段你就会把这些示例砍掉，对吧？这本身就是摸索已有经验的一部分，对吧？如果你使用的是一个搭配了非最强模型的本地代码 Agent，你也可以把同样的思路应用过去——

<details><summary>Original English</summary>
>> I think you don't want to fault them for growing a system prompt and then cutting it. At some level, it's also how the model was, right? Uh weaker older models, you need to give them examples of this is good, this is bad. And then obviously you cut that away at some point, right? And that's just part of learning what has been done, right? You can apply the same towards if you're using a local coding agent with not the strongest model,
</details>

>> 你可能就需要添加这些示例，对吧？

<details><summary>Original English</summary>
>> you might need to add these examples, right?
</details>

>> 没错。正是这样。对。对。而且当然，从中也会沉淀出有趣的 AI 认知，也就是你知道的，随着模型变得越来越好，你在什么时候添加这些示例反而会对它产生过度约束，对吧？以及你之后如何去除这种过度约束，额，我认为这同样也是认知的一部分。好的，第二周，你要讲上下文工程（Context Engineering）。Replit 我还没怎么看过，额，但是关于规范驱动开发（Spec-driven Development）有很多版本。额——

<details><summary>Original English</summary>
>> That's right. That's correct. Yeah. Yeah. And then and then of course there's interesting AI learnings to fall out of that which is why you know as the models get better when are you over constraining it by adding those examples, right? And then how you pull away the over constraining uh and that's I think part of the learning as well. Okay, week two, you are going to talk about context engineering. Repit I haven't seen uh but there's many versions of spectriven development. Um
</details>

>> 针对你在这里放入的内容，有什么是你想要向更广泛的受众强调、让大家了解的吗？

<details><summary>Original English</summary>
>> what do you would you highlight to a broader audience about uh what you're putting in here that people should know.
</details>

>> 是的，这就像是你知道的——

<details><summary>Original English</summary>
>> Yeah, this is like the you know
</details>

>> 这门课的一小时浓缩版。

<details><summary>Original English</summary>
>> one hour version of the course.
</details>

>> 是的，没错。就像是“请浓缩一切”。这就是现在这个话题的方向——

<details><summary>Original English</summary>
>> Yeah, exactly. Like please condense everything. That's where this is going this
</details>

>> 这很合理。对，这是——

<details><summary>Original English</summary>
>> that's fair. Yeah, that's
</details>

>> 嗯，不，这其实也像个预告片，对吧？就像是：嗯，如果你想要更多内容，就报名明年或明年秋季的课程，你知道，这是属于你的一小时。

<details><summary>Original English</summary>
>> Well, no, it's it's also a trailer, right? It's like, well, if you want more sign up next next year or next fall for courses, you know, this is your 1 hour.
</details>

>> 这就像……这简直就像是这门课的 Quibi（超短视频）。你懂我的意思吗？不管是……它作为预告片太长了，作为一门课又太短了。这就是……我猜大家会各取所需吧，如果这只是个预告片，等到你下次开讲的时候，内容就又会发生变化了。

<details><summary>Original English</summary>
>> This is like this is like almost like the quibby of the class. You know what I mean? Whether it's it's it's too long to be a trailer. It's too short to be the class. Is this like what what I guess people will part if it's a trailer by the next time you teach it, it'll change again.
</details>

>> 确实是这样。确实。确实如此。完全没错。是的。嗯，对。所以，好。提得好，这很有意思。额，我认为我在这里真正想要强调的核心事情是，额，而且我——

<details><summary>Original English</summary>
>> That's true. That's true. That's true. That's true. Yeah. Well, yeah. So, okay. So, good call it. It's funny. Um the I think that that the main thing that I just want to reinforce here is uh and I
</details>

<!-- chunk 6/18 -->

### 超越基础提示与处理大型代码库

我甚至在面试候选人时都能看到这种情况——业内极少有人能走出仅仅使用基础提示（vanilla prompting）的阶段。大家往往就是一种“发泄式”的用法，比如“嘿，帮我把这事做了”，对吧？就像“去做这个事，做这个事”。当然，随着模型越来越强，这确实能带你走过一段距离。但不可避免地，你知道，而且任何我和那些来自谷歌或者其他拥有海量代码库地方的人交流时，现实都是你必须更加深思熟虑地考虑如何将内容摄入到上下文当中，对吧？

<details><summary>Original English</summary>
see this even when I'm like interviewing folks uh the very few people in industry even progress beyond like just vanilla prompting right there's like a vent form like hey do me the thing right like do do the thing and and that certainly as the models get good that can carry you a certain distance but inevitably you know and any folks folks I speak to that are come out of like a Google or some place where there's a massive like code base the reality is you have to be a lot more thoughtful about how you're like ingesting in context, right?
</details>

因此，要去思考围绕如何定位等问题的一些原则和技术。你知道，我在这里描述的 RAPID 框架，在功能上类似于 Dex 的 RPI，对吧？或者诸如此类的机制：首先进行调研（research），然后提出某种提议（proposal），接着形成类似规格说明（spec）的内容，随后进行实现（implementation），最后再结合一些测试等等把它们串联起来。

<details><summary>Original English</summary>
And so thinking through what are some of those principles and those techniques around how to like point, you know, and I sort of like, you know, the rapid framework that I'm sort of describing here is is functionally similar to like Dex's RPI, right? Or something of that nature where you have this like research, you kind of have a proposal, you sort of a spec and then and then you do like your implementation and then you kind of tie it together with some testing and whatnot.
</details>

所以我在这里只想强调的是，大家应该有这么一个步骤，尤其是当进入不熟悉的代码库，或者试图向上下文中注入智能体在理解超大型代码库时所需的信息时。调研阶段是非常有价值的；而且就我提出的这个特定框架而言，在完成调研后，还会建议提出一些包含若干种替代解决路径的提议。

<details><summary>Original English</summary>
So what I just wanted to reinforce here is that like you should have this step especially when you're entering unfamiliar code bases when you're trying to uh sort of infuse into the context something that an agent needs to understand about a very large codebase. There's value in something that is a research phase and then in the case of this particular sort of framework that I'm putting forward it's like also then suggest some proposal where there's a few alternative ways of solving a problem once you've done the research.
</details>

正是在这里，我也会引入人机协同（human-in-the-loop），让人来作为权衡决策者，决定选择哪一种方案。之后再进入计划阶段，也就是类似规格说明的内容。总而言之，简要概括（TL;DR）就是：确实存在这样一种方法，能够真正扩展并适配多达数百万行代码的代码库。而且它绝不仅仅是基础提示。我认为这是我想强调的：如果你要去这些大型代码库中工作，就应该使用更复杂深入一些的方法。

<details><summary>Original English</summary>
And so this is where I sort of also invite the human in the loop to sort of be the decision maker on one appro one approach versus the other. And then you enter the plan which is kind of the spec. All to say the the the TLDDR is like there is a way to do this that actually does scale out to code bases that are you know millions of lines long. Um and it's not just the vanilla prompt. And I think that's what I want to highlight. If you're going to go work in these big code bases you should use something a little bit more a little bit more involved.
</details>

### 上下文工程与多智能体上下文管理

>> 关于上下文工程，有什么要补充的吗？

<details><summary>Original English</summary>
>> Anything to add on context engineering?
</details>

我认为目前关于我对上下文的思考，最古怪的地方可能在于当你拆分出子智能体的时候——

<details><summary>Original English</summary>
I think that the probably the weirdest thing about how I think about context right now is when you split out to a sub aent
</details>

>> 因为子智能体有时能从继承主线程的完整上下文中获益，有时又不能。对此经常存在分歧。有时候你又想把子智能体所做的工作精简压缩，让研究智能体再把它放回主线程，这非常临时拼凑（hacky）。我对自己正在做的这些都不太满意，所以我并没有确切的答案。我只知道——

<details><summary>Original English</summary>
>> because sub aents can benefit from inheriting your entire context of the main thread or not. Uh sometimes there's a regular disagreement on on that and then sometimes you want to condense what the sub agent does and researchers put it back onto the main thread and it's very hacky. I don't like anything I'm doing. So I don't have any answers. All I know is like
</details>

>> 当你想做任务扇出（fan out）时，这不仅仅关乎你手头有一个大规格说明，然后去执行 RPI 或者 RAPID 什么的。它已经不再是单个智能体在运作了。它关乎将工作分派扇出，并确保它们都拥有正确的上下文和正确的指导。如果你安排了一个评审智能体去审查所有其他智能体的工作，你必须确保它掌握所有信息。而且你总是会经历这种上下文契约不断膨胀的阶段：“天呐，这些人手头上下文不够，我得给他们更多上下文。”好的，太棒了；接着它们就会因为过度拟合你之前随口做出的一句孤立评论，而犯下极其愚蠢的错误，因为你本意并非如此，但它却奉若圣旨。

<details><summary>Original English</summary>
>> uh when you want to fan out work. It is not just about you have a big spec and you you you know you do RPI you do R repit whatever. It is not one agent anymore. It is about fanning out work and make sure they all have the right context and they all have the right guidance. If you have a review agent reviewing all the other works, you have make that guy have have everything and you always go through this phase of expanding contracts like, "Oh my god, these guys don't have enough context. I'm going to give them more context." Okay, great. And then they're going to overtune to some random one-off comment that you made a while ago and then make some really stupid mistakes cuz you didn't mean it that way, but like took it as the law,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 大概是这样。我不知道该用什么词来形容我说的这些，对吧？这就是多智能体上下文管理。

<details><summary>Original English</summary>
>> Something like that. So, I don't know what the word is I'm saying, right? This is like multi-agent management for context.
</details>

>> 是的，确实如此。这其中有某些方面……可能正是相比于科学更偏向艺术的部分，对吧？它正如你指出的那些点的某种结合：用于探索的扇出、用于子任务的扇出，随后是合并、压缩，不管你想怎么称呼它。我认为需要深思熟虑去刷新上下文，理解何时内容开始变得过于臃肿。Dex 之前提出过“迟钝区”（dumb zone）的概念，也就是要对迟钝区有更多的思考。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. Yeah, that that's absolutely right. There there's like some aspect of uh this is maybe the part that's more maybe among the most art than science, right? It's like some combination I think to your points. Yes, the fan out for the exploration, the fan out for like the subtasks and then and then the consolidation, compaction, whatever you know you might want to call it. I think being thoughtful about refreshing of the context, understanding when things are getting a little bit too bloated. I think you know Dex had this concept of like the dumb zone and sort of like being a little bit more thoughtful about the dum zone.
</details>

>> 他很擅长把这些概念公式化。

<details><summary>Original English</summary>
>> He's good at these equating things.
</details>

>> 哦对，还有那些小图表。

<details><summary>Original English</summary>
>> Oh yeah, I think little diagrams.
</details>

>> 那些小图，是的。为什么当时邀请他来着？

<details><summary>Original English</summary>
>> The little Yeah. Oh yeah. Why did you have him on?
</details>

>> 嗯，对，我想是因为……我的意思是，他确实极大地启发并充实了这里的很多课程内容，所以我觉得他是一位非常棒的思想者。图表的作用确实巨大。

<details><summary>Original English</summary>
>> Uh yeah, well I think he's I mean he helped definitely informed a lot of the the curriculum here and so he's just fantastic I think thinker and all this. Um no I think the diagrams are huge.
</details>

>> 这很有用。

<details><summary>Original English</summary>
>> That's useful.
</details>

### 上下文工程的演进与研究

>> 我想为正在尝试研究这个领域的人补充一些线索。观察关于子智能体继承的最佳上下文工程实践是很有益的，比如 Claude 托管智能体有一个会话各自独立、不进行继承的版本。在推理模型出现之前，在智能体运行时间没那么长的时候，这曾是一个热门话题。那时我们拥有的上下文窗口更短，每个人都非常非常精细地管理着那宝贵的上下文窗口，对吧？LangChain 过去经常就此和良好的上下文工程写大量博文。了解所有这些内容对大家都是有好处的。我认为在学生的语境下也是一样，你可以预料到普通学生选修你的课——因为这是一门很棒的课——他们会了解所有这些知识，所以你也应该比他们掌握得更透彻。

<details><summary>Original English</summary>
>> I would add um breadcrumbs for people that are trying to look into this. It's good to see best context engineering preferences like on your sub agent inheriting cloud managed agents has a version where sessions are separate and it's not inherited. This used to be a big talk topic before reasoning models when agents didn't run as long. Um we had shorter context windows. Everyone was very very managing that precious context window, right? Uh Lingchain used to write a lot of blogs about this and good context engineering. All this stuff is good for people to know. I think in the student context as well, you can expect the average student to take your class cuz it's a great class and they'll know all these things. So you should know them know them better as well.
</details>

这也是一个很有意思的研究领域。在 AIE 上展示的其中一篇研究论文中，他们观察了 Claude Code 系统提示词的变化差量（delta）。哪些内容发生了改变，然后他们绘制了一整套性能变化的图表，试图对其进行逆向工程。这就是大家可以做的优质研究。还有另一篇论文也探讨了上下文窗口管理及其对下游性能的影响。它们虽然不算顶尖的论文，但门槛不高，而且能产出优质的博客文章。所以对于想要从事该领域研究的人，我非常推荐，这是一个可以轻松切入的好方向。

<details><summary>Original English</summary>
Um this is a fun space for research as well. One of the papers research papers presented at AIE. They looked at the delta in the cloud code system prompt. What got changed and they like um they they plotted a whole bunch of changes in performance. They tried to reverse engineer it. It's just good research that you can do. There was another one that also looked at context window management and how it affects performance downstream. They weren't the best papers, but like it's quite accessible and it puts out good blog posts, so people that are trying to work on it, you know, I just recommend it's a it's a good area you can easily poke into.
</details>

>> 是的，提得很好。

<details><summary>Original English</summary>
>> Yeah, it's a good shout out
</details>

### 智能体技能与保持人类参与

>> 智能体技能，Claude。

<details><summary>Original English</summary>
>> agent skills CLA.
</details>

>> 是的，是的。我认为所有这些……都在单次所谓函数工具调用（例如 MCP）的基础上做了一点延伸，对吧？从与第三方外部服务交互，延伸到了大家所谓的程序规程（procedures），对吧？比如你如何自动化一系列反复执行的操作，然后以类似 `SKILL.md` 之类的形式将其规范化。所以，我认为就是让这一点更加……让大家在把这些规程代码化方面多做练习。

<details><summary>Original English</summary>
>> Yeah. Yeah. I think all this is uh so a little bit of an extension from single single kind of quote function tool calling like MCP, right? Using interacting with like third party external services and then extending into like what you would call like procedures, right? like how do you automate some set of actions over and over again that you then formalize in the form of like a skill MD or something like that. So I think just making that a little bit more uh giving people exercise in in codifying some of those procedures.
</details>

我想我在这里也会列入一些有趣的技能，我认为它们很值得使用。比如我认为 Matt Pocock 的 grill-me 就很不错。此外，从教学角度来看我也很喜欢一些技能，比如 Jeffrey Litt 制作的 explain-diff。我认为一旦开始谈论代码审查，它就会变得格外有趣，因为众所周知，整个核心在于——

<details><summary>Original English</summary>
I think what I'll also sort of like include here is is a few few kind of fun skills that that I think are are good to use like I think Matt Matt Pox like grill knee is like a good one. Uh and then I there's ones that I also like from more from the educational perspective like Jeffrey Litz uh he has like explained diff which I think becomes especially interesting once you start talking about code review because you know the whole
</details>

>> 理解代码。

<details><summary>Original English</summary>
>> understand the code
</details>

>> 理解代码。正是如此。是的，你必须去理解代码。我不知道你们有没有用过那个工具，但实际上的流程是：你运行它，放入你在代码中所做的变更差异（diff），接着运行该技能；在结束时，你不仅能得到一份展示发生了什么的直观可视化呈现，以便浏览并理解其最核心的变动；而且我真正喜欢的是，在最后它几乎会提供一个小测验，你可以通过它来真正强化确认自己是否理解了发生了什么。我认为那种程度的交互式来回反馈是非常好的。

<details><summary>Original English</summary>
>> understand the code. Exactly. Yeah. you got to have to understand the code and and I don't know if you guys have used that but effectively like you run you know you have your your your kind of the the the diff you've put in your code and then you run the skill and at the end of it you have this not only like kind of a visual representation of what's happened so you can you know kind of skim it and understand what's what's actually at the core of it but then what I really liked was this almost like quiz at the end of uh at the end of it where you go through and sort of like really reinforce whether you understand what's happening and I think that that level of interactive sort of back and forth I think is is quite nice.
</details>

是的，在这个领域有几篇博文我非常喜欢拿出来讨论。最近有一篇大概是说：在任何情况下，不动脑子（turning your brain off）都不是个好主意。我认为这些技能实际上是在强迫你开动大脑。而当所有人都想使用编程智能体来偷懒不用脑子时，他们只是想着“帮我做个应用，读懂我的心思，在我什么都不用说明的情况下把一切都猜对并做好”。

<details><summary>Original English</summary>
Yeah, there's there's a couple blog posts in this domain that I really like to bring up. Uh there's one I think recently which is like kind of there's no situation in which turning your brain off is a good idea like you know and and I think these skills actually force you to turn brain on and when everyone wants to use coding agents turn your brain off. They're just like make me an app and get read my mind and guess get everything correct without me telling you about it.
</details>

>> 没错。但很多这类技能主要属于这种类型：

<details><summary>Original English</summary>
>> That's right. But like a lot of these skills are mostly in the genre of like
</details>

<!-- chunk 7/18 -->

不，不，就像，请多问我一些问题。

像……

<details><summary>Original English</summary>
no
 no
 like
 ask
 me
 more
 questions
 please.


Like
</details>

>> 我觉得现在的产出比人们习惯的要多得多。比如我输入一行提示词，就能得到数万行代码，而且结构完整，

<details><summary>Original English</summary>
>> I
 think
 there's
 a
 lot
 more
 output
 than


people
 are
 used
 to.
 Like
 I
 can
 type
 in
 a


oneline
 prompt
 and
 get
 tens
 of
 thousands


of
 lines
 of
 code
 and
 all
 structure
 and
</details>

>> 然后就像“大家看我的生产力多高”。

<details><summary>Original English</summary>
>> like
 look
 at
 my
 productivity
 guys.
</details>

>> 嗯，但你知道，更有效率的做法是，你应该清楚自己在做什么。

<details><summary>Original English</summary>
>> Um
 but
 you
 know
 more
 effectively
 you


should
 know
 what
 you're
 working
 on.
</details>

>> 你真的可能会脱节、脱离掌控。你应该花更多时间思考自己真正在做什么。呃，做具体工作和把代码写出来比以前容易多了。

<details><summary>Original English</summary>
>> You
 can
 really
 be
 put
 out
 of
 touch
 out


of
 the
 loop.
 You
 should
 spend
 more
 time


thinking
 about
 what
 you're
 actually


doing.
 Uh
 doing
 the
 work
 and
 getting
 the


code
 written
 is
 much
 easier
 than
 it
 was.
</details>

>> 是的。是的。至于理解层面，确实没有任何借口了。

<details><summary>Original English</summary>
>> Yeah.
 Yeah.
 The
 understanding
 there's
 no


no
 excuse
 for
 for
 sure.
</details>

### Web skills 与技能编写

>> 不好意思。什么是 web skill？

<details><summary>Original English</summary>
>> Sorry.
 What
 is
 a
 web
 skill?
</details>

>> 好的。我意思是，实际上就是与网络本身进行交互的技能。Computer use……

<details><summary>Original English</summary>
>> Yeah.
 So
 I
 mean
 effectively
 like
 skills


that
 interact
 with
 with
 like
 the
 web


itself.
 Computer
 use
</details>

>> computer use。是的。诸如此类的东西。

<details><summary>Original English</summary>
>> computer
 use.
 Yeah.
 Things
 like
 this.
</details>

>> 还有别的吗？

<details><summary>Original English</summary>
>> Anything
 else?
</details>

>> 呃，主要是涉及从网络拉取信息的事情。我觉得是……

<details><summary>Original English</summary>
>> Uh
 I
 mean
 mainly
 things
 that
 involve


like
 pulling
 pulling
 information
 from


the
 web.
 I
 think
 it's
</details>

>> 关于与网络交互的技能，是否有最佳实践，相比……

<details><summary>Original English</summary>
>> Are
 there
 best
 practices
 on
 skills
 that


will
 interact
 with
 the
 web
 versus
</details>

>> 我……

<details><summary>Original English</summary>
>> I
</details>

>> 我觉得这更像是我找到的一些挺有意思的东西的概览或某种演示。我想可能是出自……是像 Versel 吗？我现在正努力回想。我得回头查查完整的阅读材料，但有那么一个网站，我记得他们……也许实际上是基于浏览器的。他们可能做过……

<details><summary>Original English</summary>
>> I
 think
 this
 is
 more
 of
 like
 a
 a
 bit
 of


a
 a
 survey
 or
 kind
 of
 a
 demo
 of
 stuff


that
 I
 found
 that
 was
 kind
 of


interesting.
 I
 think
 it
 was
 it
 might


have
 been
 out
 of
 was
 it
 like
 a
 Versel?


I'm
 trying
 to
 remember
 now.
 I'd
 have
 to


look
 back
 at
 the
 the
 full
 like
 reading


materials,
 but
 there
 was
 like
 one
 site


that
 I
 found
 where
 I
 think
 they
 maybe
 it


was
 it
 might
 have
 been
 browser
 based


actually.
 They
 might
 have
 like
 done
</details>

>> 你记得这个吗？

<details><summary>Original English</summary>
>> do
 you
 remember
 this?
</details>

>> 记得。呃，对他们来说大概就是这个东西。只是我当时在想，我是漏掉了什么吗？我觉得这在技能社区里算是一个大块。很好。他正在了解这方面。

<details><summary>Original English</summary>
>> Yeah.
 Uh
 well,
 it
 would
 be
 them
 that


this
 thing.
 It's
 just
 I
 was
 like
 did
 I


miss
 something?
 I
 think
 this
 is
 like
 a


big
 part
 of
 the
 skills
 community.
 Good.


He's
 being
 educated.
</details>

>> 是的，我觉得他们做出了某种……因为我猜他们……是的，我的意思是 browser base 显然很喜欢……

<details><summary>Original English</summary>
>> Yeah,
 I
 think
 I
 they
 like
 made
 some
 sort


of
 because
 I
 guess
 they
 were
 Yeah,
 I


mean
 browser
 base
 obviously
 like
</details>

>> 他们喜欢浏览器。

<details><summary>Original English</summary>
>> they
 like
 browsers.
</details>

>> 他们喜欢浏览器，而且，嗯，但是是的，他们有一个不错的网站，我觉得他们在上面展示了其中一些有趣的能力。

<details><summary>Original English</summary>
>> They
 like
 browsers
 and
 um
 but
 yeah,
 they


they
 had
 like
 a
 good
 I
 think
 website


where
 they
 showed
 some
 of
 these


interesting
 capabilities.
</details>

>> 看起来挺靠谱。CLI 是个挺好玩的方向。你的学生里是有很多人是第一次接触终端和 CLI，还是说这现在已经成常态了？

<details><summary>Original English</summary>
>> Seems
 legit.
 CLI
 is
 a
 fun
 one.
 Do
 you


have
 a
 lot
 of
 students
 or
 this
 is
 their


first
 time
 in
 a
 terminal
 in
 a
 CLI
 or
 is


it
 kind
 of
 the
 norm
 now?
</details>

>> 呃，不，我不这么认为。呃，我觉得鉴于他们大多数人……同样，呃，去年我会说他们中有些人可能还记得手指在键盘上敲打的日子，呃，大多数学生到目前为止我觉得都接触过 cloud code 了。

<details><summary>Original English</summary>
>> Uh
 no,
 I
 don't
 I
 don't
 think
 so.
 Uh
 I


think
 that
 given
 that
 most
 of
 them
 again


uh
 last
 year
 I
 would
 say
 that
 some
 of


them
 had
 probably
 still
 remember
 the


days
 of
 of
 finger
 on
 keyboard
 uh
 typing


uh
 the
 this
 is
 um
 most
 I
 think
 students


have
 like
 interacted
 with
 cloud
 code
 at


this
 point.
</details>

>> 我的意思是，我挺好奇现在只用客户端应用的人群比例。cloud code 也有桌面客户端，codeex 也是。Codex 现在主要就是个应用。你有点不在 CLI 里，不在终端里了。这让很多普通人望而却步。不过……

<details><summary>Original English</summary>
>> I
 mean
 I
 I'm
 curious
 the
 split
 of
 people


that
 are
 now
 just
 using
 the
 apps
 right


cloud
 code
 also
 has
 a
 desktop
 app
 so


does
 codeex.
 Codex
 is
 primarily
 an
 app


now.
 You're
 kind
 of
 not
 in
 the
 CLI
 not


in
 the
 terminal.
 It's
 a
 thing
 that
 puts


off
 a
 lot
 of
 average
 people.
 But
</details>

>> 我只是顺便提一句。

<details><summary>Original English</summary>
>> I'm
 just
 random
 note.
</details>

>> 是的。呃，我想说，关于技能，我觉得还有一点，就是有些技能是技能的组合包，它们彼此交叉引用。

<details><summary>Original English</summary>
>> Yeah.
 U
 I
 would
 say,
 you
 know,
 I
 think


there's
 also
 another
 thing
 about
 skill


that
 are
 skills
 that
 are
 bundles
 of


skills
 where
 they
 they
 sort
 of
 cross


reference
 each
 other.
</details>

>> 对。就像插件一样，对吧？

<details><summary>Original English</summary>
>> Yeah.
 Like
 the
 plugins,
 right?
</details>

>> 呃，像插件一样。然后还有，我想，编写技能的艺术，这也是我为 AIE 一直重点关注的事情。

<details><summary>Original English</summary>
>> Uh
 like
 plugins.
 And
 then
 there's
 also
 I


guess
 the
 art
 of
 writing
 a
 skill,
 which


is
 a
 thing
 that
 I've
 also
 focused
 on
 for


AIE.
</details>

>> 我觉得很多这类东西都集中在消费技能上。嗯，还有各种网红，比如 Matt Pog 等等人，他们就像是说：“对，这个技能能拯救……能解决你所有的问题。”但其实不对，你应该自己写技能。

<details><summary>Original English</summary>
>> I
 think
 a
 lot
 of
 these
 uh
 are
 focusing


on
 skill
 consuming.
 Um,
 and
 you
 have
 all


these
 influencers
 like
 Matt
 Pog
 and
 what


have
 you,
 they're
 like,
 "Yeah,
 this


skill
 will
 save
 it
 will
 solve
 all
 your


problems."
 But
 no,
 you
 should
 write
 your


skills
 yourself.
</details>

>> 实际上，当你试图凭直觉去写它们时，通常写得很糟糕。实际上，编写一个技能也是需要一点技巧的。

<details><summary>Original English</summary>
>> And
 actually,
 when
 you
 try
 to
 write
 them


naively,
 they're
 usually
 bad.
 And


actually,
 it
 takes
 a
 little
 bit
 of
 skill


to
 write
 a
 skill.
</details>

>> 完全没错。完全没错。

<details><summary>Original English</summary>
>> That's
 absolutely
 right.
 That's


absolutely
 right.
</details>

>> Swix 在编写技能方面有什么独家秘诀？

<details><summary>Original English</summary>
>> What
 are
 Swix's
 best
 tips
 on
 writing


skills?
</details>

>> 我有一个技能。我有一个公开的技能仓库。我确实经历过一段“把所有东西都做成技能”的狂热期。

<details><summary>Original English</summary>
>> I
 have
 a
 skill.
 I
 have
 a
 public
 skills


repo.
 I
 went
 through
 definitely
 a
 phase


of
 psychosis
 of
 like
 skill
 everything.
</details>

>> 不，不，不，别给我们扔技能。怎么才能写出好技能？

<details><summary>Original English</summary>
>> No,
 no,
 no,
 don't
 give
 us
 skills.
 How
 do


you
 write
 good
 skills?
</details>

>> 是的。确实。确实。我有用来精简技能的技能。

所以我有……比如像 cloud code 和 codecs，它们都有创建技能的技能，对吧。所以我有一个技能精简技能来做删减，因为它们……它记录了那些默认创建出来的技能存在糟糕问题的各种表现。

<details><summary>Original English</summary>
>> Yeah.
 Exactly.
 Exactly.
 So,
 I
 have
 a


skill
 for
 cutting
 skills.


So
 I
 I
 I
 like
 there
 so
 every
 like
 uh


cloud
 code
 and
 codecs
 they
 all
 have


skill
 creation
 skills
 right.
 So
 then


there's
 I
 have
 a
 skill
 cutter
 skill
 that


cuts
 it
 down
 because
 they
 they're
 all
 it


just
 documents
 every
 way
 in
 which
 those


default
 skills
 that
 are
 created
 are
 bad.
</details>

>> 所以任何技能创建之后，你总是会运行这个来裁剪它。

<details><summary>Original English</summary>
>> So
 you
 always
 run
 this
 after
 any
 skills


created
 to
 cut
 it
 down.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Right.
</details>

>> 嗯，所以……

<details><summary>Original English</summary>
>> Um
 so
</details>

>> 像这样。

<details><summary>Original English</summary>
>> like
 this.
</details>

>> 是的。这真的很烦人，因为有时会有废话水货，但水货里也有好东西，然后你就得去粗取精，把他们……把他们……

<details><summary>Original English</summary>
>> Yeah.
 It's
 really
 annoying
 because


sometimes
 there
 is
 slop
 and
 like
 but


there's
 good
 in
 the
 slop
 and
 then
 you


have
 to
 like
 sort
 of
 whittle
 down
 what


they're
 what
 they're
</details>

>> 对。对。噢，有意思。正如你所说，即使是废话水货，它也依然是用智能体的语言写成的。所以这些废话是有其含义的。就像……是的。好的。好的。懂了。懂了。

<details><summary>Original English</summary>
>> right.
 Right.
 Oh,
 interesting.
 As
 you're


saying
 like
 even
 the
 slop
 is
 it's
 still


in
 the
 language
 of
 the
 agent.
 So
 that


the
 slop
 means
 something.
 It's
 like
 it's


like
 a
 it's
 Yeah.
 Okay.
 Okay.
 Got
 it.


Got
 it.
</details>

>> 没关系。每个人都有自己的版本。我一开始习惯……对技能进行感觉检查是非常容易的，对吧？你只要调用它，运行几次，然后我把这些偏好提炼成一个技能，说明“这就是我喜欢的模式，不喜欢的模式”，它会随着时间不断调整，然后就可以自动化了。

<details><summary>Original English</summary>
>> It's
 fine.
 Everyone
 has
 their
 own


version.
 I
 used
 first
 there's
 very
 easy


to
 like
 vibe
 check
 a
 skill,
 right?
 You


just
 call
 it
 run
 it
 a
 few
 times
 and
 then


I
 distill
 these
 preferences
 into
 a
 skill


that's
 like
 this
 is
 what
 I
 like
 this


way.
 doesn't
 like
 and
 it
 it
 adjusts
 over


time
 and
 then
 you
 know
 it
 get
 automated.
</details>

>> 问题在于，是的，你调用了它，但实际最糟糕的部分是，某个技能在你意想不到的时候被触发了。比如你某次写它是为了修复一件事，结果现在你在做一个完全不同的东西，它却触发了。为什么？因为写得太差，因为触发条件写着“噢，无论何时发生某某情况就调用我”，你当时觉得“行，看起来挺好”，然后你换了个不同的项目，它又触发了，你心想“这到底怎么回事？”你知道，有少数几个人就是“好的，我有一堆技能。我有时就一直往上加”，而我认识的一些人，比如 Eugene Yan，他们对自己拥有的技能数量相当讲究。他们会修剪技能。如果不常用，他们每隔几周就会清理一次。

<details><summary>Original English</summary>
>> The
 problem
 is
 that
 yeah
 you're
 calling


it
 but
 the
 the
 actual
 the
 worst
 part
 is


when
 a
 skill
 triggers
 when
 you're
 not


expecting
 it
 to
 like
 you
 wrote
 it
 one


time
 to
 fix
 a
 thing
 and
 then
 like
 now


you're
 working
 on
 a
 completely
 different


thing
 and
 it
 triggers.
 Why?
 Cuz
 it's


badly
 written
 because
 the
 trigger
 says


like
 oh
 call
 me
 whenever
 blah
 blah
 blah


happens
 and
 you're
 like
 okay
 read's
 good


and
 then
 you
 do
 a
 different
 project
 and


it
 and
 it
 triggers
 and
 you're
 like
 what


the
 hell's
 happening?
 You
 know,
 there's


a
 there's
 like
 a
 few
 people
 that
 are


just
 like,
 "Okay,
 I
 have
 a
 bunch
 of


skills.
 I
 keep
 adding
 on
 sometimes
 when


I
 know
 some
 people
 like
 Eugene
 Yen,
 they


are
 pretty
 particular
 about
 how
 many


skills
 they
 have.
 They
 prune
 them.
 If


not
 used,
 they
 clean
 them
 every
 few


weeks."
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。所以，呃，如果你是在这个技能圈子里，这确实是个大问题。我觉得这其实就是为什么我怀疑……他们是优秀的，Anthropic 那边有些非常聪明的人希望技能彻底消亡。

<details><summary>Original English</summary>
>> Yes.
 So,
 uh,
 so
 yeah,
 this
 is
 like
 a
 a


huge
 problem
 if
 you're
 if
 you're
 sort
 of


in
 that
 skills
 world.
 I
 think
 this
 is


actually
 why
 I
 suspect,
 uh,
 they're


good.
 There
 are
 very
 smart
 people
 at


over
 in
 anthropic
 that
 want
 skills
 to


die.
</details>

>> 呃，这可不是句受欢迎的话。不，不，他们不会公开这么说的，

<details><summary>Original English</summary>
>> Uh,
 which
 is
 not
 a
 popular
 statement.


No,
 no,
 they
 they
 won't
 say
 this


publicly,
</details>

>> 但它就是让人感觉很杂乱。这感觉很杂乱。而且我知道，我能看到我自己的技能，大家做的都很杂乱。这感觉不像是……

<details><summary>Original English</summary>
>> but
 it
 just
 feels
 sloppy.
 This
 feels


sloppy.
 And
 I
 know
 it's
 I
 I
 can
 see
 my


own
 skills
 people
 being
 sloppy.
 It


doesn't
 feel
</details>

>> 呃，AIA pill，

<details><summary>Original English</summary>
>> uh
 AIA
 pill,
</details>

>> 对吧？你懂我的意思吧？

<details><summary>Original English</summary>
>> right?
 You
 know what
 I
 mean?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这根本不是 AGI 该有的样子。就好像每个人都揣着一大堆 markdown 文件。

<details><summary>Original English</summary>
>> It's
 it's
 not
 it's
 not
 what
 AGI
 was


supposed
 to
 look
 like.
 It's
 like


everyone
 having
 a
 giant
 bunch
 of


markdown
 files.
</details>

>> 我觉得一定程度上这是个园艺修剪维护的问题。某种意义上是的。

<details><summary>Original English</summary>
>> I
 mean,
 I
 think
 part
 of
 it
 is
 there's
 a


gardening
 problem.
 Yeah.
 some
 sense.
</details>

>> 很多人其实根本不看自己的 markdown 文件，对吧？就像那种用户体验：直接通过对话输入你想要的，在聊天中创建一个技能，使用它，查看输出。

<details><summary>Original English</summary>
>> A
 lot
 of
 people
 actually
 don't
 look
 at


their
 markdown
 files,
 right?
 Like
 the


the
 UX
 of
 it
 of
 just
 chatting
 what
 you


want,
 creating
 a
 skill
 and
 chat,
 using


it,
 seeing
 output.
</details>

>> 你不需要查看 markdown 就能获得很多价值。在某种程度上不要把它给自己弄得太复杂。呃，如果你重复做某些事情，就能获得很大的价值。只要跟它说：“看下我们前五次是怎么做这个的，给我做个技能。”然后你就可以通过对话不断迭代它。它也有好的一面，对吧？

<details><summary>Original English</summary>
>> There's
 a
 lot
 you
 can
 there's
 a
 lot
 of


value
 you
 can
 get
 without
 ever
 looking


at
 your
 markdown.
 Don't
 don't
 over


complicate
 it
 at
 some
 level
 for


yourself.
 Uh
 you
 can
 get
 a
 lot
 of
 value


if
 you
 do
 stuff
 repeatedly.
 Just
 be


like,
 look
 at
 the
 last
 five
 times
 we
 did


this.
 Make
 me
 a
 skill.
 And
 you
 can


iterate
 it
 with
 chat.
 There's
 a
 good


side
 of
 it
 as
 well,
 right?
</details>

### 技能的组织级定位与 Monaco 域名

>> 还有一件事。嗯，我想还有另一种看待它的方式，因为有一种用法是只把技能当成智能体随时运行的流程步骤，你知道，去跑个代码审查之类的。但在像 Devon 这样的情况下，对吧，我们把技能沉淀下来，作为呈现我们最佳实践的一种方式，对吧，然后把它提供暴露给智能体和代码审查系统，以便按照我们喜欢的方式去建立 API，按照我们定义的方式去建立服务层面的边界。这就像是呈现组织级知识的另一种途径，也许不完全是那种“你为了省去每次写提示词的麻烦而让智能体去执行的随意事情”。所以我也挺喜欢……我觉得那种定位、那种用途可能会比你所知道的这些随机流程存在得更久。

<details><summary>Original English</summary>
>> There's
 another
 thing.
 Um
 there's
 I


guess
 another
 way
 to
 look
 at
 it
 as
 well


cuz
 there's
 a
 there's
 the
 use
 of
 the


skill
 as
 just
 this
 procedure
 that
 the


agent
 kind
 of
 runs
 whenever
 to
 you
 know


do
 like
 a
 code
 review
 or
 whatever.
 But


then
 in
 the
 case
 of
 something
 like


Devon,
 right,
 where
 we've
 codified


skills
 as
 a
 way
 of
 of
 sort
 of


representing
 our
 best
 practices,
 right,


and
 then
 making
 and
 exposing
 that
 to
 the


agent,
 the
 code
 review
 system
 to
 then,


you
 know,
 institute
 the
 APIs
 the
 way


that
 we
 like
 to
 define
 them.
 Institute


kind
 of the
 service
 level
 boundaries
 the


way
 we
 define
 them.
 That's
 like
 an


alternative
 way
 of
 sort
 of
 representing


like
 org
 level
 knowledge
 and
 maybe
 not


so
 much
 this
 like
 arbitrary
 thing
 you


want
 the
 agent
 to
 do
 so
 you
 don't
 have


to
 write
 the
 prompt
 each
 time.
 And
 so
 I


like
 I
 like
 that.
 I
 feel
 like
 that


positioning
 might
 that
 that
 purpose


might
 exist
 longer
 than
 just
 u
 you
 know


these
 kind
 of
 random
 procedures.
</details>

>> 我刚才 Google 搜了一下 Monaco AI skills，结果出来的全都是摩纳哥这个国家。

<details><summary>Original English</summary>
>> I
 just
 Googled
 Monaco
 AI
 skills
 and
 it's


giving
 me
 the
 the
 the
 country.
</details>

>> 嘿，这个国家……

<details><summary>Original English</summary>
>> Hey
 the
 country
</details>

>> 总有一天。总有一天。好吧，我们在 AEO 上肯定会赢过他们的。这是肯定的。

<details><summary>Original English</summary>
>> one
 day.
 One
 day.
 Well,
 we're
 going to


beat
 them
 on
 AEO.
 That's
 for
 sure.
</details>

>> 你们能不能直接把那个国家买下来？

<details><summary>Original English</summary>
>> Can
 you
 just
 buy
 the
 country?
</details>

>> 嗯，情况是这样的。好的。关于这个，我们……我们正打算买……不，我们不是要买下那个国家。但是，但是，但是，嗯，你知道，当买下 monaco.com 域名时，我们确实……确实遭到了不少非议抨击。这点我得承认。

<details><summary>Original English</summary>
>> Well,
 here's
 the
 thing.
 Okay.
 On
 this
 we


we
 uh
 we're
 about
 to
 buy
 No,
 we're
 not


about
 to
 buy
 the
 country.
 But
 but
 but
 um


you
 know
 we
 we
 did
 uh
 we
 did
 get into
 a


little
 bit
 of
 flack
 when
 we
 uh
 bought


the
 monaco.com
 domain.
 I
 will
 say
 that
</details>

<!-- chunk 8/18 -->

### 诉讼与飞机广告营销

额，我们确实被他们起诉了。所以……

<details><summary>Original English</summary>
uh we did get uh sued by them. So
</details>

>> 怎么说？

<details><summary>Original English</summary>
>> what
</details>

>> 对，这件事闹得人尽皆知，网上全公开了。对，他们很不高兴，但事实是我们现在好好的，而且我们打赢了。我们赢了官司。所以……

<details><summary>Original English</summary>
>> yeah there's there's like a whole public there's a whole public thing about this where yeah so they didn't like that but but here we are and uh we won. We won. So
</details>

>> 好吧，那我们把这段留着。我本来还想说这话题太劲爆了，不过既然你们赢了。

<details><summary>Original English</summary>
>> okay then we're keeping it in. I was about to say this is spicy but you won.
</details>

>> 是的。没错。不，不，没事的。

<details><summary>Original English</summary>
>> Yeah. Yeah. No no it's
</details>

>> 这就是为什么我们能看到那些旗子到处飞吗？

<details><summary>Original English</summary>
>> Is that why we is that why we see the flags flying around?
</details>

>> 因为这就像一场胜利。这是一种胜利。这是我们的胜利。挺逗的。

<details><summary>Original English</summary>
>> Because it's like a victory. It's It's a victory. It's our victory. That's funny.
</details>

>> 对于在旧金山的人来说，抬头看就能看到。顺便提一下，对于听音频的听众，我们在 YouTube 上展示了这个画面。你们雇了一架飞机到处飞。我觉得你们仍是少数几家真正经常这么做的公司之一。Sam Blonde 想出来的点子。一天六千美元。额，我倒不觉得这能直接促使我去谷歌搜 Monaco 是什么，但是 Monaco 的所有广告基本上就只有“Monaco”加上美元符号，

<details><summary>Original English</summary>
>> For for those that are in SF, just look up and, you know, so for for those who are on audio, we're showing this on YouTube. Uh it's you fly a plane around. I think you're still one of the few that actually do this on a regular basis. Sam Blonde came up with it. $6,000 a day. Uh, I don't necessarily think it directly causes me to Google what Monaco is, but that all of Monaco's ads are just Monaco dollar sign,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 就像美元符号，后面跟着一个 X 数字。

<details><summary>Original English</summary>
>> Like dollar sign and then X number.
</details>

>> 这就开启了话题，对吧？整个广告的目的就是让人好奇 Monaco 到底是个什么鬼？

<details><summary>Original English</summary>
>> It starts the conversation, right? All the the whole point of the ad is what the hell is Monaco?
</details>

>> 是的。而且你知道，这确实可以讨论，但从某种意义上说，营销的目的不就是吸引眼球吗，对吧？而且，也许还有更深一层的作用，那就是如果有人……比如我去参加活动，人们会说：“哦，你们就是搞飞机巡游的那帮人。你们就是看板上写着大数字的那帮人，什么 1.93 亿之类的。”然后他们会问：“但你们究竟是做什么的？”但这可能恰恰就是全部目的所在，对吧？我只是需要有人把它当作一个破冰话题。

<details><summary>Original English</summary>
>> Yeah. And and you know, you could you could like that's a debate to be had, but but in some sense like what is the purpose of marketing if not to like get attention, right? And and yes, maybe there's one level beyond this, which is if somebody So, you know, I'll go to events and people like, "Oh, you guys are the ones with the planes. You guys are the ones with like the big number on the billboard, blah blah blah, 193, you know, million, whatever it is." Um, and and that but they're like, "But what do you do?" And then but that's that's but that's but maybe that's the whole point, right? Is that I just needed someone to come and use it as an icebreaker.
</details>

>> 我得说，你刚才走进来的时候我说的也是这句。我就说：“啊，那架飞机。”

<details><summary>Original English</summary>
>> I will say it's what I said as you walked in as well. I was like, "Ah, the planes."
</details>

>> 可不是嘛。然后就会问：你们是做什么的？那好，让我来告诉你我们是做什么的。所以，作为一个参与过决定 Devon 广告牌文案会议的人，我们花了大量时间琢磨措辞，也许我们直接写个“Devon”就行了，虽然看起来蠢蠢的。但是……

<details><summary>Original English</summary>
>> There you go. And now, what do you guys do? Well, well, let me tell you about what we do. So, so you know, as someone who's been in those meetings deciding what we do on the the Devon billboards, we spend so much time on the words and maybe we should just be like Devon, which is so dumb. But like,
</details>

>> 行吧，你看，我觉得 Sam 上周还发了个帖子，他就在讲……Sam 实际上就像是我们这儿的营销军师。飞机背后也有一点故事，但长话短说就是……

<details><summary>Original English</summary>
>> okay, you know, look, look, I I think Sam had another post uh this past week where he was just talking about like, you know, I mean, Sam is effectively like our our, you know, marketing sort of mastermind here. And uh yeah, I think there's a little bit of history behind behind the planes as well, but but the TLDDR is that
</details>

>> 他的招牌风格就是“我没有所有答案，你必须亲自去试”。我觉得很多时候我们就是去尝试各种东西，如果见效了，那太棒了。我们预料到这会引起这么大反响吗？其实并没有。但既然成了，这就是个好点子。

<details><summary>Original English</summary>
>> his whole shtick is like I don't have all the answers. You just got to try things. And I think a lot of this is we just try things and and if it sticks, great. If it like did we know this was going to blow up as much as it did? I mean, not really. But but now that it did, it's an idea.
</details>

>> 是的，没错。

<details><summary>Original English</summary>
>> Yeah. Exactly.
</details>

>> 而且极简主义，从小起步再做大，而不是搞大排场再缩水。

<details><summary>Original English</summary>
>> And minimalism, start small, go high instead of start big, go small.
</details>

>> 从小起步再做大要容易得多。

<details><summary>Original English</summary>
>> Uh way easier to start small, go big.
</details>

>> 是的，完全正确。

<details><summary>Original English</summary>
>> Yeah. Exactly. This
</details>

>> 另外，每天花费六千美元。这完全就是抱着试试看的心态。我觉得大家……

<details><summary>Original English</summary>
>> also, you know, it's 6K a day. Like it's it's very much just try things. I think I think people
</details>

>> 比广告牌便宜。肯定比广告牌划算。

<details><summary>Original English</summary>
>> cheaper than billboard. Cheaper than a billboard for sure.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且挺好玩的。

<details><summary>Original English</summary>
>> And it's fun.
</details>

>> 是啊。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 也没什么害处。

<details><summary>Original English</summary>
>> Not not much harm done.
</details>

>> 但你知道这……值得一提的是这种简单粗暴的逻辑：当我们想更进一步、超越一架飞机的效果时，我们的想法是，知道什么比一架飞机更牛吗？两架飞机。

<details><summary>Original English</summary>
>> But you know it does it's um but you know the kind of simplicity here that that's worth mentioning is then when we're trying to like one up the plane we're like you know what's better than one plane? Two planes.
</details>

>> 两架飞机，三架。

<details><summary>Original English</summary>
>> Two planes. Three.
</details>

>> 我觉得下一步该上火箭了。

<details><summary>Original English</summary>
>> My way to rocket.
</details>

>> 好吧，我也想说我见过……

<details><summary>Original English</summary>
>> Well okay I also say I've seen
</details>

>> 我有过这个想法。我希望未来某个时候能实现，不过走着瞧吧。下一次 SpaceX 发射，我们直接看到 Monaco……

<details><summary>Original English</summary>
>> I had that idea. Uh I I would like for for that to happen as well at some point but uh we'll see. This is the next SpaceX launch. We just see Monaco
</details>

>> 印在星舰上准备升空。

<details><summary>Original English</summary>
>> for the ship to start.
</details>

>> 没错，没错。得先去和我们的 SpaceX 朋友搞好关系。

<details><summary>Original English</summary>
>> There you go. There you go. Got to got to warm up to our our SpaceX friends.
</details>

>> 行，这我就满意了。

<details><summary>Original English</summary>
>> Okay. I'm happy.
</details>

>> 你不想……

<details><summary>Original English</summary>
>> You don't want to
</details>

### Monaco 的产品定位与市场策略

>> 既然我们聊到了 Monaco，值得稍微展开介绍一下 Monaco 吗？还是留到最后？

<details><summary>Original English</summary>
>> Well, I mean, we're we're on Monaco. Is it worth talking a little bit about Monaco? Do you leave it to the end?
</details>

>> 好啊，好啊。额……

<details><summary>Original English</summary>
>> Yeah. Yeah. Um
</details>

>> 因为这就像是话题间的一个中场休息。

<details><summary>Original English</summary>
>> because this is like an intermission between the the topics.
</details>

>> 你来定。

<details><summary>Original English</summary>
>> You decide.
</details>

>> 行。我们提到了 Monaco，对吧？我觉得如果勾起了大家的好奇心、提到 Monaco 到底是个什么鬼，结果却不作回答，那未免有点吊人胃口。当然可以，你能解答一下吗？当然，我希望我能讲清楚。好的。所以……

<details><summary>Original English</summary>
>> Okay. We're We mentioned Monaco, right? Like let's let's give I I I think it's I think it's a little bit annoying to like mention what the hell is Monaco and then not answer it. Sure. Can you answer it? Sure. Well, I hope so. Yeah. So, um
</details>

>> 这是个国家。所以，它是一个小小的……

<details><summary>Original English</summary>
>> this is the country. So, it's a small little uh
</details>

>> 没毛病，对头。好吧，这就是摩纳哥公国，这就是我所知道和喜爱的那个摩纳哥。是的。我们是一家位于旧金山的 B 轮公司。我们实际上正在打造一个一体化的销售平台。完全由原生智能体处理所有好玩的事情，或者至少是人类不乐意做的事情，但智能体很乐意做，因为它们没有情绪主见，而且它们出错率更低，这样销售人员和销售团队就能集中精力去做人类擅长的事情，也就是促成交易。

<details><summary>Original English</summary>
>> There you go. There you go. Okay. That this is Monaco. This is the Monaco that that I know and love. Uh yeah. So, we are uh you know, we're we're series B company uh here at Basin SF. We are are building effectively like an all-in-one sales platform. Uh fully native agents doing all the fun stuff. uh or at least the stuff that humans don't like to do but but that agents are do like to do because they don't really have opinions but do in a less airprone fashion so the sales people and sales teams can focus on doing what humans are good at which is you know closing deals
</details>

>> 这么说来，马克·贝尼奥夫（Mark Benioff）大概不会喜欢你们。

<details><summary>Original English</summary>
>> so presumably Mark Beni off doesn't like you guys
</details>

>> 大概率不喜欢。

<details><summary>Original English</summary>
>> probably not
</details>

>> 但说实话，他本人也是个非常 AI 原生派的人，非常激进，搞了 Agentforce 等一整套东西。

<details><summary>Original English</summary>
>> but he's like also honestly a very AI native person very aggressive and agent force and everything
</details>

>> 你们在做什么是他不做或者做不了的？

<details><summary>Original English</summary>
>> what are you doing that he he doesn't do or he cannot do
</details>

>> 好吧，这么说吧，我们目前或者说创办这家公司时瞄准的市场，从一开始就不是大企业客户，对吧？我们的想法是，如果我们的目标是打造一体化产品，那么我们就需要与一批种子客户一起进行迭代打磨，我们需要与他们共同成长。相比之下，要把客户从 Salesforce 手里硬抢过来要困难得多；但如果我们能在你还只用谷歌表格跟进销售管线的时候切入，向你展示一种更具 AI 赋能的解决方案，我们就能陪着你一起成长。在某种程度上，这遵循了 YC 等公司的模式：先把产品卖给同期的同班同学公司，陪他们一起壮大，然后再走向高端市场。所以我认为，可以说我们是面向初创公司最优秀、即便不是唯一最顶尖的销售平台之一。我们目前所有的客户都是早期初创公司，大致处于种子轮到 A 轮阶段，这就是我们过去主要深耕的区间，种子轮到 A 轮，而现在我们正向更高端的市场迈进。在过去一年半的实践中，我们对一体化平台积累了大量的认知。

<details><summary>Original English</summary>
>> well okay so so right now we or uh we started the the company in a sort of like the the market that we went after was not enterprise from the get- go, right? We sort of said like we're going to start by like if our goal is to build the all-in-one, then we need to kind of build this in an iterative fashion with with a group of customers and we need to like grow with them into this. It's much harder to pull someone away from from Salesforce than to say like hey if we meet you at the point when you are still just a Google spreadsheet tracking pipeline and we sort of show you a you know more AI pill sort of answer to the problem then we can grow with you and in a way it kind of follows the same the same uh model of like you know BS or all the like YC companies where you kind of sell to your batch mates you kind of grow with them and and you then you go up up up market and so we I would argue are the you know the the I would I would claim the among the best if not the best sort of like startup focused uh sales platform and so all of our customers are like early stage startups at this point probably through to like series A is is kind of where where we've primarily been focused kind of seed to series A and then now we're going more up market and we've kind of learned a lot about the all-in-one in the last year and a half of doing that
</details>

>> 而你是 AI 负责人。

<details><summary>Original English</summary>
>> and you are the head of AI.
</details>

>> 是的，没错。

<details><summary>Original English</summary>
>> Yeah, that's right.
</details>

>> 你们构建了哪些很酷的 AI 成果？

<details><summary>Original English</summary>
>> What's some cool AI stuff you guys have built?
</details>

>> 好的，我们针对销售应用场景搭建了自己的智能体运行框架。回溯一下编程框架的逻辑，我们从业界的 Codex、Claude 等系统中汲取了大量灵感，构建了专门面向销售的定制化工具，以及专门针对 GTM（走向市场）场景的定制化工作流。我们构建了自己的这套框架，驱动着 Monaco 平台上几乎所有的业务。从潜在市场规模（TAM）的评分、理想客户画像（ICP）的打分与定义，到销售管线的演进推进，再到销售人员不乐意做的一切琐碎杂务——比如更新会前备忘、更新总结纪要等所有这些事情，我们都有智能体在后台驱动所有这些工作流。所以我们做到了这一点，它开箱即用。不仅有长周期智能体，也有针对某些 GTM 场景的短周期智能体。

<details><summary>Original English</summary>
>> Yeah, I mean uh we have built our own agent harness for for sales use cases. So all this I mean to call back to the to the coding harnesses uh taking a lot of inspiration from from the systems like the codexes in the clouds of the world and sort of building bespoke tools that are very sales focused bespoke workflows that are all kind of geared toward GTM use cases. Um so we built our own version of that that powers pretty much every single thing that that powers the Monaco platform. So from you know uh scoring of scoring of TAMs uh scoring of ICPS and and develop defining of ICPS uh through to pipeline evolution through to like all the mundane kind of things that maybe a salesperson doesn't want to do which is like oh update my meeting you know premeating notes update my summaries like all these things. Um you know we have agents powered powering all those workflows. So we we've done that. It it's it's kind of comes comes out of the box. Um and uh yeah, so long long agents long horizon agents for long horizon agents and short horizon agents some cases for for for GTM use cases
</details>

>> 而且它是高度领域专精的，构建在基座模型之上。针对这些业务，你们会训练自己的专属模型吗？

<details><summary>Original English</summary>
>> and it's pretty domain specific built on foundation models. Would you do any of your own models for this?
</details>

>> 问得好。因为到目前为止，我认为很多垂直领域 AI 公司普遍都是如此：起步时把前沿大模型当作第三方服务来用，探索技术边界，因为它们代表了最顶尖的水平。接着，我想我们在过去一周的 Harvey 事件中也看到了这一点，他们面临着毛利率在正 50% 到负 50% 之间波动的质疑。不论……

<details><summary>Original English</summary>
>> Yeah, it's a good call out. Uh because so far I mean I think this is generally true of a lot of like vertical AI companies is like you kind of start where you sort of use the frontier models like as third party services to see what's possible cuz they are like the very frontier and then I think we've seen this I guess in the past week with the whole like Harvey sort of where they like the plus 50% to minus 50% margin kind of question. I mean know I think irrespective of the
</details>

<!-- chunk 9/18 -->

数据。我认为有趣的是，在某个节点上，从成本角度来看事情确实变得很有意思，你开始琢磨能不能在开源权重模型上跑得更快。然后很大一部分工作——我认为很多 AI 模块的用途——就是对这些模型进行后训练，构建类似通过强化学习进行后期调整的环境之类的。所以，嗯，我们现在正处于这个阶段。

<details><summary>Original English</summary>
numbers I think what is interesting is like at a certain point things do become interesting from a cost perspective you you start to wonder can you do it faster on you know open weight models and then that a lot of that then a lot of what I think the the purpose of of the AI pieces are is just to post train those models build environments for you know kind of to post using RL and things of that nature so um we're kind of in that phase right now
</details>

>> 挺有意思。对，我一直把这种策略称为“Agent 实验室打法”（agent lab playbook），不过这是我自己的叫法。就是说，Agent 先从用户端切入，然后使用构建产品所需的任何模型；一旦拥有了用户群体，就可以反过来补充模型端能力。而模型实验室走的往往是相反的路线：他们先从大规模预训练做起，然后努力去寻找用户。

<details><summary>Original English</summary>
>> fun yeah I've been calling this uh playbook the agent lab playbook but that is kind of my coining of like you know like agents start from the user first and then they uh they they use whatever models you need to to build products but then you can backfill the the model side once you have the user base and then the model labs go kind of go the other way they they start with the big pre-trains and then they try to find users
</details>

>> 嗯，这种模式有望形成一种分工。Monaco 应该属于偏向营收与 GTM（Go-To-Market）的一方。

<details><summary>Original English</summary>
>> um and it's like very you know it's hopefully working as a as a as a split and Monaco would be on the sort of revenue GTM side
</details>

>> 没错，是的。

<details><summary>Original English</summary>
>> that's right yeah
</details>

>> 嗯，我觉得挺有意思的一点是，他们既想为你们提供服务，同时又试图与……竞争。

<details><summary>Original English</summary>
>> um and I think it's interesting uh they would want to serve you while also trying to compete with
</details>

嗯。

<details><summary>Original English</summary>
Mhm.
</details>

>> 作为模型实验室。

<details><summary>Original English</summary>
>> Uh as as model labs,
</details>

>> 确实是这样。

<details><summary>Original English</summary>
>> that is correct.
</details>

### 数据丰富与获客

>> 我一直在琢磨的一些事情中——我也涉足过其中一部分——我认为真正难解决的问题之一其实是数据丰富（enrichment）。

<details><summary>Original English</summary>
>> One of the things that I've been I've been I I dabble in in in some of this. I think one of the hard problems is actually enrichment.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我自己花了很多时间在这上面，基本上是为了 SEO 和调研之类的。我想对你们来说，这实际上也是非常核心的一部分。

<details><summary>Original English</summary>
>> Uh I would say I spent a lot of my time doing that for for basically SEO and like uh research and what have you. And I imagine for you it's actually like a core part of that.
</details>

>> 没错。

<details><summary>Original English</summary>
>> That's right.
</details>

>> 你觉得模型擅长做这个吗？你们有喜欢合作的供应商吗？想给他们公开点名推荐一下或者怎样的吗？

<details><summary>Original English</summary>
>> Do you find that models are good at it? Uh do you have any vendors that like you like working with? You want to give them a shout out? Whatever.
</details>

>> 有，当然有。我们用过……我们是 Parallel 的早期使用者，我认为他们非常出色。

<details><summary>Original English</summary>
>> Yeah. Yeah. Absolutely. Yeah. So we we have used we were early adopters of Parallel and then I think they're very strong.
</details>

>> 好，那就是通用搜索类的。

<details><summary>Original English</summary>
>> Okay. So just general search.
</details>

>> 对，我是说……

<details><summary>Original English</summary>
>> Yeah. I mean
</details>

>> 不是 ZoomInfo 或那类厂商。

<details><summary>Original English</summary>
>> not like Zoom info or one of those guys.
</details>

>> 不是，不是，不是。嗯，不过对，我们用 Parallel，也用 Exa。所以给这两家都点名推荐一下。

<details><summary>Original English</summary>
>> No. No. No. Um but yeah, we use Parallel. We also use Exa. Um so we'll give give a shout to both of those folks.
</details>

>> 你能对比一下它们吗？

<details><summary>Original English</summary>
>> Can you compare them?
</details>

>> 都是朋友。

<details><summary>Original English</summary>
>> They're both friends.
</details>

>> 都是朋友，都是朋友。都是我们挺喜欢的人。

<details><summary>Original English</summary>
>> They're both friends. They're both friends. They're both folks that uh that we like.
</details>

>> 如果你更偏向其中一家，他们会非常感兴趣的。

<details><summary>Original English</summary>
>> They'll be very interested if you like one of the
</details>

>> 哈哈，我保持中立，今天在这事上我保持像瑞士一样的中立。不过，当然，我们也会做自己那套数据丰富。我们大多数的数据系统——我的意思是，我认为我们构建的最有价值的软件模块或最有价值的系统之一，就是目前我们的“全域数据库”（world database），比如包含丰富企业信息、丰富客户机构信息以及丰富联系人信息的数据库。这样每当我们为客户构建理想客户画像（ICP）时，都能掌握最新鲜的信息，明确在此时此刻你应该联系哪家公司的哪个人。我认为毫无疑问我们达到世界级水准的领域之一，就是获客需求（demand）。我们是一家非常出色的需求挖掘公司，能切实帮助企业提升预约会议数量。

<details><summary>Original English</summary>
>> Yeah. I'll keep it I'll keep it neutral. I'll stay I'll stay Switzerland in this today. But yeah know so so and then of course we do our own version of enrichment as well. So we it's it's like a most of our data systems I mean part of like one of one of I think the most valuable piece of software that we build or most valuable systems is current like our world database like the database of companies enriched companies enriched accounts uh enriched contacts. So like that whenever we are constructing ICPS for folks, we have the most up-to-date information about who you should reach out to at which company at this point in time. Like I would say that one of our like I think where we are like world class hands down is just demand. Like we are very good demand company. Like we help companies increase their meetings booked in a way that actually
</details>

>> 在合适的时机找到买家……

<details><summary>Original English</summary>
>> find buyer at
</details>

>> 在合适的时机找到买家，对吧？而且是多重时机因素的结合。比如有这样一种情况：假设你的目标销售对象是销售副总裁（VP of Sales）。联系他们的合适时机，并不是在他们……比如过去 5 年都在同一个地方任职的稳定期。如果他们刚刚换了工作——一个很好的信号是，一旦他们从上一份工作跳槽到新岗位，他们就进入了一个新环境，此时更有可能购买或乐意考虑购买新的销售平台，因为他们正处在职位转换期。所以……

<details><summary>Original English</summary>
>> find buyer at the right time, right? And it's kind of like combination at the right time. Like there's there's times when like here's an example like if you are um if you are targeting someone that just you are selling to um VPs of sales let's say okay like the the right time to to reach out to them is not when they are like sort of in the middle of some like they've been at the same place for the last like 5 years. if they are now in the middle of like a job like a good signal is like once if they've gone from one job to a new job they're now like entering a new place where they're more likely to be to purchase or be open to a purchase of a new sales platform because they're in the middle of the job transition. So
</details>

>> 从 A 公司跳到 B 公司，对于销售来说是一个很好的信号，比如“在这个时间点该不该联系他们，你是否察觉到了他们的 LinkedIn 动态变化”之类的。这其中有多少是你们倾注到模型和测试框架中的专业能力，又有多少是模型本身的能力加上通用的行业最佳实践？显然这两者都有其价值。

<details><summary>Original English</summary>
>> going from company A to company B for like sales a good signal of like hey should you reach out to them at this point in time is did you detect that their LinkedIn changed or something like that. How much of this is your expertise put into model and harness versus models are good there's generic best practices like is there there's obviously some value in both
</details>

>> 这里的核心是整合各部分的黏合层、提升可靠性、全部在一个平台内做好……

<details><summary>Original English</summary>
>> um is it just the glue getting it reliable doing it all in one platform doing it well
</details>

>> 看起来似乎还包含……

<details><summary>Original English</summary>
>> it seems like there's also
</details>

>> 融入了我们所不知道的、你们团队擅长的领域专业知识。

<details><summary>Original English</summary>
>> stuff that we wouldn't know that you guys are also domain experts in that's baked in
</details>

>> 对，我认为如果没有前者，它就会完全沦为大路货。我的意思是不完全是这样，因为一体化（all-in-one）本身依然有很大价值。我认为这绝对是我们开创的模式：销售领域的大多数公司最初做的只是单点解决方案，他们更倾向于尝试类似 YC 那种“先立足再扩张”（land and expand）的做法，先选一个小切口切入，然后再向外扩展。而我们从一开始——这也是我们在一年零几个月的大部分时间里一直保持隐身模式（stealth mode）的原因，纯粹就是在打磨产品，因为我们从一开始就清楚自己想做一体化平台。但这本身虽然强大且意义重大，我认为真正的力量在于：今天的 Monaco 拥有世界级的市场拓展（GTM）团队，一支真正世界级的销售 Monaco 自身产品的团队。而且不仅如此，负责销售 Monaco 的这批 GTM 人员，就是我们所谓的“前沿部署客户经理”（forward deploy account executives），也就是 FDA。他们本质上就像……我称之为人类销售员，类似顾问角色，帮助我们所有的客户上手、引导他们构建基于 Agent 的工作流，并在整个销售 GTM 生命周期的每一个环节为客户提供引导。所以回答你的问题：一体化平台确实是一方面，但另一方面还在于我们拥有这批人才。比如 Sam，我们引进了不少前 Sam 团队的成员，他们是此前在 Brex 等公司最优秀的 GTM 人才，我们正在把所有这些沉淀并固化到平台中。

<details><summary>Original English</summary>
>> yeah I think without the former it would it would be like a fully commoditized I mean not fully I mean because there's still a lot of value in the all-in-one. I think like that is something that we definitely pioneered like most companies in the sales space started as just like point solutions and I think they're they tried more of like the YC approach of you kind of land and expand. You kind of pick a niche and then you expand from there. Uh, and we from the get-go, I mean, that's why we stayed in stealth for the greater part of a year and some months, was just building because we knew we want to be the all-in-one from the start. But, you know, that alone is is powerful. It's meaningful. But, I think the real power is the fact that today Monaco as Monaco has like a world-class go to market team, like a truly like world-class go to market team selling Monaco, of course. But we also have the same go to market people that sell Monaco are the ones that are like what we call for deploy account executives. They're FDA. They're effectively like well I say human human sales people that are like the consultants of sorts that help onboard all of our customers get them like building agentic workflows and are effectively there to like help guide them through every part of their own sales go to market life cycle and so to your question it's the all-in-one yes but it's also the fact that we have these like you know SAM and and you we we have brought on a lot of like former Sam Sam's team members and stuff like that who were like the best people in GTM at Brex and other places so um we're codifying all of that in the platform
</details>

>> 听你聊这些非常有意思，表达方式与一般的 AI 负责人大不相同。这或许也因为你曾是一名创业创始人，对吧？你习惯了用这种视角来思考这些问题，在你的岗位上具备这种思维非常重要。

<details><summary>Original English</summary>
Yeah, interesting to have you talk very differently than a normal head of AI might also talk to because you're also a former founder, right? And like you're you're also think used to thinking about these things in this way and it's like interesting to it's important to have that in your role.
</details>

### Monaco 内部的 Agent 原生编程

>> 是的，太酷了。我想关于 Monaco 的情况你已经介绍得够充分了，随着 Monaco 后续故事的展开，我们之后还可以再聊。

<details><summary>Original English</summary>
>> Yeah. Cool. Uh I I I I think you you've introduced Monaco enough there and and obviously I think as the Monaco the story develops we can revisit.
</details>

>> 没问题，当然可以。

<details><summary>Original English</summary>
>> Sure. For sure.
</details>

>> 或许可以顺势切回另一个话题：Monaco 内部的编程、Agent 原生编程或者现代软件开发是什么样的？你在对外授课时，或许只是尽量给出全局概览；但在 Monaco 内部，你们是不是在路线选择上更有倾向性？

<details><summary>Original English</summary>
>> Um maybe the bridge back is also what is coding uh or agent native coding or modern software development like inside of Monaco. Um you know I think you're when you're teaching you're maybe trying to be here's a lay of the land but maybe inside of Monaco you guys are more opinionated on one thing versus the other.
</details>

>> 是的，没错。我们在编程 Agent 上的投入基本上是从第一天就开始了，而且积累了非常多的经验教训。我们走过弯路、踩过坑，获得了不少心得，现在也开始更深入地对外分享其中的一些经验。比如在我们的博客上——可能值得在这里分享一下——我们越来越多地发布一些……可能不是最顶部那篇，那篇偏产品介绍，而是像下面这些内容：比如当 AI 普及开来、规模化代码贡献、自研与外购抉择等。我们花了很多时间调研不同的供应商和服务商，最终选择在内部自研了很多系统。以我们所用的后台 Agent 平台为例，我们有自己版本的类似 ramp inspect 机制，名为 monocoder。它是基于 Coder 平台构建的，也是我们用来从工程维度实现产品扩产的核心工具。

<details><summary>Original English</summary>
>> Yeah. Yeah. No I mean we have so we we made investments in coding agents from basically like day one and we've like learned a lot. we have our own like scars that we've sort of like picked up and and learnings and I think we've now been getting much deeper into sort of sharing some of our learnings. So like in our blog which might be worth sharing here we've been increasingly posting some of what uh maybe not that so that one is more of like a product the one at the very top but this stuff I would say like yeah when AI gets that spread in before like scaling contributions builder buy S. So you know we spent a lot of time looking at different providers looking at vendors and ended up building a lot of things in house. So for us something like a background agent platform we have our own version of like a ramp inspect um that we call monocoder um which is is built on the coder platform um but it is what we use to essentially scale up our engineing product
</details>

>> 类似 coder.com 吗？

<details><summary>Original English</summary>
>> like coder.com
</details>

>> 对，coder.com。

<details><summary>Original English</summary>
>> coder.com yeah
</details>

>> 噢。

<details><summary>Original English</summary>
>> oh
</details>

>> 是的，我们确实根据自己的业务场景对它做了一些改造。我们的很多 Agent 开发工作都是在上面进行的。它是一款设计非常出色的软件，非常适合用于隔离开发环境、扩展到多 Agent 架构，以及运行这些耗时很长的长流程编程 Agent 任务。所以……

<details><summary>Original English</summary>
>> yeah we actually yeah have sort of adapted it to some of our use cases and yeah it's where a lot of our agent development happens it's just this really well-designed piece of software for essentially isolating of of sort of like um development environments scaling out to multi- aents um you know being able to run these long long horizon agentic coding agent tasks. So
</details>

<!-- chunk 10/18 -->

### 自研工具与 HAL 机器人

Monicoder，向 John Tracy 还有 Co 致敬，感谢他们构建了那个工具。从那之后，我们也搭建了自己的版本，比如一个叫 HAL 的 Slack 机器人。实际上，HAL 有点像结合了一部分应用信息安全（AIS）、一部分客户成功（CS）以及一部分质量保证（QA）工程师的职能。因为它常驻在我们的 Slack 里，既能帮助我们排查调试问题，并在出故障时提 PR，同时我们的销售人员也会用它来了解产品如何运作、探究某件事情的究竟。所以，针对 HAL 在面对销售人员与面对开发者时表现出的不同性格，我们不得不解决一些有趣的问题。类似这样的系统，在过去大概一年左右的时间里，我们陆续搭建了很多。向负责 HAL 的 Yuna 以及 John Tracy 致敬。

<details><summary>Original English</summary>
Monicoder, shout out to John Tracy and and and Co for for building that out and and then yeah like from there we've also built our own versions of like a you know like like a slack bot which is call but um you know effectively how is like this part AIS part like customer success part like uh kind of QA engineer because it it it lives in our Slack but it serves all the purposes of helping us debug things and put up PRs when things are broken but also used by our own sales people to find out how the product works, find out like how to get to the bottom of something. And so there's like interesting questions we've had to answer around the different personalities that HAL has u depending on whether it's talking to like a saleserson versus like a develop developer. And so systems like this that we built out over time a lot in the last like year or so. Uh shout out to Yuna for for Hal and and John Tracy as well.
</details>

>> 所以你们自己内部自研了很多工具。

<details><summary>Original English</summary>
>> So uh you're building a lot in house.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你们也使用其他工具吗？

<details><summary>Original English</summary>
>> Uh you also use other tools.
</details>

>> 我们确实会用其他工具。是的。

<details><summary>Original English</summary>
>> We do use other tools. Yeah.
</details>

>> 那么界限在哪里？

<details><summary>Original English</summary>
>> So what is the line?
</details>

>> 是的。所以——

<details><summary>Original English</summary>
>> Yeah. So
</details>

>> 买——

<details><summary>Original English</summary>
>> by
</details>

>> 是自研还是购买。这是个好问题。而且我们——

<details><summary>Original English</summary>
>> was that Yeah, the builders by it. It's a good question. Uh and we
</details>

### 自研与采购的考量：以代码审查工具为例

>> 我觉得有一个通用原则，我通常认为的原则是：你为了学习而自研，为了长期持有而购买……抱歉，反过来了。是你为了学习而购买，为了长期持有而自研。对，是反过来的。所以，你为了学习而购买，为了长期持有而自研。我觉得在这里大体上也是如此。在早期，当我们还在摸索起步阶段时，代码审查就是其中一个例子，我们当时花了很多时间考察各种代码审查平台。事实证明，我们今天仍然在使用 Devin，因为我们确实仍然发现它构建系统的方式具有很大价值。所以，要向 Cognition 团队致敬。但在此过程中，我们也确实尝试过一些 SRE 工具，也尝试过一些现成的、可能更偏向后台 Agent 的平台，后来判定鉴于我们的基础设施以及我们搭建私有云平台的方式，内部自行构建这些系统会更合理。当然我们并不固执，如果有新产品出来，我们也乐意重新审视它们。但在这里我觉得，通常只有在我们觉得市面上没有成熟产品时，我们最终才会选择自研。

所以代码审查可能是一个有趣的例子，因为大概一年多前，我们确实对代码审查工具做过一次全面的调研，当时——

<details><summary>Original English</summary>
>> I think there's this um uh like a thing a general principle that that I generally which is like you build to learn and you buy to keep or sorry you buy to learn and you build to keep. Yeah. The other way around there. Yeah. So so you you buy to learn and you build to keep. And I think that's generally true here where in the early days when we were still trying to figure out like you know get our feet under us a little bit we were you know code review is an example one of them where we spent a lot of time looking at different code review platforms. It turns out today we still use Devon because we've actually still find a lot of value in how the systems been built. So you know shout out to the cognition team. Um but then along the way we did try out some like S sur tools and you know we tried some sort of like offtheshelf maybe more like background agent platforms decided that it was just given our infrastructure given how we had set up our own cloud platform it just made more sense to kind of build this out internally of course we're not dogmatic we we are open to revisiting them if if something comes out but here I felt I think usually we ended up building in house when we felt that there was no like mature offering out there so

code review is maybe an interesting example because we did do a whole survey of code review tools like maybe over a year ago and at the time
</details>

>> 你可以提一下像 CodeRabbit，对吧？

<details><summary>Original English</summary>
>> you can shout out like code rabbit right
</details>

>> 是的，CodeRabbit 以及他们这类产品。而且当时还有 Graphite，在他们被收购之前叫 Code Graphite，持续了一段时间；还有 Ellipsis，那是之前的 YC 公司。但其实有一大批，对吧？我是说，我们确实尝试过很多人做的工具，它们还可以，但我认为它们当时还没有越过“立刻发挥实用价值”的门槛。于是我们稍微把这件事搁置了一阵子，我说的是一年多以前的事了。后来我们又回到了这个方向，很自然地——再次向 Devin 团队和 Cognition 的朋友们致敬——我们又尝试了一次它。我想，当时好像有人跟我说过类似“嘿，你该试试这个，它看起来已经变好很多了”。可能正好是在去年 Silas 在课堂上做分享的时候，效果确实很好，而且它在团队里自然而然地传播开了——

<details><summary>Original English</summary>
>> yeah code rabbit and and them and you know that there was also like code graphite graphite graphite for a while before they got acquired um like ellipsus and which like a y company before the fact so but there's a bunch right I mean so so there were a lot of folks that we did try and they were okay but I don't think they had like crossed the threshold of like they're immediately useful yet and so then we kind of like we sort of like put it aside a little bit this was you know I'm saying like well over a year ago then we kind of went back to this and sort of organically I mean, again, shout out to to the to the Devon team and and cognition folks where we tried it again. I think um I had sort of like gotten that somebody had told me like, "Hey, you should try this and it seems like it's gotten a lot better." It might have been actually during Silus's talk during the class last year and it was just good and it it was organically like like
</details>

>> 纯凭感觉，对吧？你不可能有别的——

<details><summary>Original English</summary>
>> purely vibes, right? Like this is there's no way that you
</details>

>> 是有——对。这……我的意思是，好吧，我是这么看的。当我们第一次做评估的时候，我们并没有真正挑选任何供应商，当时觉得没有哪家供应商能让我们非常满意。我当时确实做了一次分析，审查了我们的 PR，基本上做了一组饼图，说明它解决了什么问题。我们权衡了它的冗长程度、发帖频率以及实用性，看看是否对这种平衡感到满意。所以第一次更多是由统计数据驱动的，不仅仅凭感觉。第二次评估时我没打算硬推。第一次的时候我有点像是“嘿，我们应该引入一个 AI 代码工具”，第二次的时候我就想“算了，我不打算再去推了”。但随后团队里的人自发地说：“嘿，Devin 挺好用的。你能把我也加进去吗？”于是到了今天，大家就开始自发地被添加进来了。所以这是一个我们目前仍然倾向于使用供应商的案例。长期来看会是怎样我们拭目以待，但在那之外的其他方面，我们只是觉得市面上产品的成熟度还没达到要求。

<details><summary>Original English</summary>
>> there was Yeah. This this was like I mean Okay. Okay. Here here's what I'll say. When we did that first evaluation the first time around where we didn't really pick any vendor um and we were like there's no vendor that we're super happy with. I did do like an analysis where I looked at our PRs basically did sort of like a you know set of pie diagrams like here's what this is solving. Are we are we happy with the kind of the trade-off of verbosity and how often it's posting with utility. Um and so there was it was more statistically driven than just vibes. The second time around I wasn't going to push hard on it. The first time I was kind of like hey we should adopt an AI code tool. Second time I was like no I'm not going to do that again. Um but then organically people were just like, "Hey, Devon is like good. Like can can you like add me to this?" And so today people started just like getting organically added. So this is a vendor where you know one of the cases where we're still leaning to the vendor. You know we'll see in the long term what that looks like but um everything outside of that we just didn't feel like maturity was there.
</details>

>> 是的，而且这种痛点还没强烈到让你想要把 Devin 拔掉然后自己写一个的地步。

<details><summary>Original English</summary>
>> Yeah. And it's not painful enough that you would like rip out Devon and write your own.
</details>

>> 没错。

<details><summary>Original English</summary>
>> That's right.
</details>

>> 挺有意思的。是的。

<details><summary>Original English</summary>
>> That's interesting. Yeah.
</details>

>> 这对 Devin 来说算是很好的宣传了，我都没想到。顺便澄清一下，我只是个顾问，现在参与没那么深了。但能从外部听到这些反馈很有意思，因为在内部——这么说吧——存在一定程度的“信息茧房”，在 Slack 上你只能听到正面的声音，因为大家只想传播好消息。但你在这件事上没有偏向，只是单纯选择最好的工具。

<details><summary>Original English</summary>
>> So good good talk for Devon who I didn't even know. Uh you know for the record I'm only an adviser. I'm not that involved anymore. But like it's interesting to to hear about it externally because internally uh there is a certain amount of let's call it um the the bubble where like on Slack you're you're like you only hear positive things cuz people only want to circulate positive things. Uh but like you have no dog in the fight like you just choose the best tool.
</details>

>> 如果能拿到 Slack 免费额度，那当然也挺好的，没有人会拒绝这个。

<details><summary>Original English</summary>
>> I mean if you want to get a Slack free credit that's totally that'd be cool too like that. Wouldn't I would say no one would say no to that.
</details>

>> 我想 Silas 会帮你搞定的。

<details><summary>Original English</summary>
>> I think Silus I think Silus will hook you up.
</details>

### Agent-ready 代码库与后续课程结构

>> 好，情况就是这样，对吧？然后这些经验融入到了你所有的教学工作中，我觉得这非常好，随着讨论深入我们可以再多讲讲这些，因为这种亲身实践的经历非常宝贵。

<details><summary>Original English</summary>
>> Okay. So, so, so there's that, right? Um, and then, uh, and that informs all your teaching work and, you know, I think that's that's really good and we can bring in more of this as, as you like, uh, because I think this is this lived experience is very good.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我很乐意回到 Agent-ready 代码库或者更广泛的讨论……比如第四周和第五周——

<details><summary>Original English</summary>
>> Um, uh, I'm happy to go back to agent ready code bases or board like so so week four and five
</details>

>> 某种程度上是契合的。

<details><summary>Original English</summary>
>> kind of uh, you know, matching.
</details>

>> 是的，它们有一点重合。是的。

<details><summary>Original English</summary>
>> Yeah, they they blend a little bit. Yeah,
</details>

>> 有一点重合，没错。无论你想引入你在 Monaco 建立的任何坚定信念，以及建议大家从什么开始。

<details><summary>Original English</summary>
>> blend a little bit. That's right. whatever you want to whatever strong beliefs you have introduced in Monaco. Yeah. Uh and recommend people to start with.
</details>

>> 确实是这样。第四周和第五周，我认为第四周可能更多偏向概念基础和实现路径，因为定制 Agent 的方法有很多；而第五周是我真正倾向于“好了，让我们开始思考并在真正的代码库上付诸实践”的阶段。所以在这里我一定要向 Factory 团队致敬，并强调类似“就绪度报告（readiness report）”这类事物的价值。我认为我想要强调的核心点是，对我而言，类似 Agent-ready 代码库这样的东西是一个前置条件，也是通往后续一切的基础模块。当我提到“后续的一切”时，指的是人们曾经有一阵子——而且我认为现在依然如此——对多 Agent 架构极度狂热，比如并行化 Agent、几十个 Agent 去做各种各样的事情。但你实际上需要打好基础才能把那件事做好。而基础就在于：你的代码库可验证性如何？你的代码库结构有多好？它对 Agent 而言有多容易理解？所以我觉得对我来说，Agent 就绪度几乎可以说是接下来四到五周里的第一块拼图，大概一直延续到第八周或第九周，届时我会花更多时间广泛探讨 AI 软件团队以及整体组织架构，但当下绝对是在为后台 Agent 和软件工厂构筑基石。我认为从这个视角来看，所有事情就是从这里开始变得有趣起来的。

<details><summary>Original English</summary>
>> Yeah. No, for sure. Yeah. Week four and five I would say they they are a little bit um four is maybe a little bit more like uh conceptual foundations and ways to do this cuz there are a lot of ways to customize agents. And then I would say week five is where I really kind of like lean into all right let's think about this and apply this in practice on like a true codebase. And so here I will definitely, you know, give a shout out to to the factory team and and uh and want to just highlight the value of something like a readiness report. I I think that the main piece that I want to uh reinforce something like agent ready code bases is to me like a precursor and a bit of a building block toward everything to come afterwards. When I say everything to come afterwards, I mean like people always got, you know, for a while and I think people still are like super hyped on like multi- aents like paralyzing agents, like tens of agents doing all kinds of things. It's like you actually need to set a foundation in order to do that well. And the foundation is how verifiable is your codebase? How like well structured is your codebase? How understandable is it by an agent? And so I think like agent readiness to me is like almost almost like piece one of the next four to five weeks where maybe until like week eight or nine where where I spend more time talking about like broadly uh you know AI software teams and like kind of or global structure but definitely building up the the building blocks for for uh background agents the software factory. I think this is where it all kind of gets interesting from from that perspective.
</details>

>> 是的。有一点我注意到你在谈论 Monaco 时提到了，但在这里没有列出来，那就是 SRE 这一侧。当你完成闭环时，你实际上希望让 Agent 去读取你的构建日志，然后理想情况下再去读取线上生产环境的分析数据。

<details><summary>Original English</summary>
>> Yeah. One thing that I observed you talking about for Monaco, but it's not here is the S sur side. When you close the loop, um you actually want to have the agent read your logs for builds and then put ideally read your analytics for live production.
</details>

>> 没错，确实是这样。是的，虽然没有明确列出，但这是一个很好的提及。所以我——

<details><summary>Original English</summary>
>> That's right. That's right. Yeah. Um not as not explicitly, but it's a really good shout out. So, I
</details>

<!-- chunk 11/18 -->

我想我会把这点穿插在大概两个地方：一个是后台智能体（background agents）那一周，另一个是软件工厂（software factory）那一周。所以说得完全没错。确实，提出这种“基于触发器/事件来完成闭环”的想法非常好。如你所知，现在当人们谈论在软件工厂中由智能体触发任务时，这大概是两三个切入点之一。完全正确，那部分内容会放在那里讲。

<details><summary>Original English</summary>
think that I'm going to weave that in in like two places. One is in the background agents uh week and then also in the software factory week. So absolutely right. Um I do it's a really good call out this idea of like trigger/eventbased closing of the loop. Um which you know now is one of the one of the probably two or three entry points when people talk about agents kicking off tasks in a software factory. Uh that's absolutely right. That'll come in there.
</details>

>> 挺有意思的是，大家都称之为基于触发器或基于事件，我猜这确实是它的实际技术实现。

<details><summary>Original English</summary>
>> Yeah it's interesting that people call it trigger or event based which I guess that is the actual technical implementation of it.
</details>

>> 感觉这听起来几乎太底层了。嗯。

<details><summary>Original English</summary>
>> It just seems too lowle almost. Mhm.
</details>

>> 但所谓的触发器通常就是一个 cron 任务，对吧？实话实说。

<details><summary>Original English</summary>
>> Uh but so so the trigger is usually a chron job, right? Like let's be real.
</details>

>> 确实。确实。确实。

<details><summary>Original English</summary>
>> Sure. Sure. Sure.
</details>

>> 基于事件的通常也是一个浮现出事件的 cron 任务，然后就变成基于事件了。但归根结底全是 cron。

<details><summary>Original English</summary>
>> Uh event based is usually a chron job that like surfaces an event and then it's event based. But it's it's all crons.
</details>

>> 对。对。没错。没错。对。对。对。或者是 web host 之类的东西。不过是的，完全没错。是的。而且你知道，这当然是技术术语，因为说到底，作为计算机科班出身的人，是的，我们以前就这么叫它们。所以我想我还是习惯用这些术语。是的。那么，有没有哪家 AI SRE 公司给你留下了深刻印象？

<details><summary>Original English</summary>
>> Yeah. Yeah. That's right. That's right. Yeah. Yeah. Yeah. Or like web host or something like that. But yeah, that's absolutely right. Um yes. And and you know the technical term of course because at the end of the day Yeah. Uh being sort of like a CS person by by by trade and and yeah, we we called it those things. And so I guess that's I fall back on that terminology. Yeah. And have any AI sur companies made an impression on you?
</details>

### AI SRE 与企业级基础设施挑战

>> 好吧。我是觉得 Resolve 他们做得挺不错。Resolve 做得很好。从泛后台智能体的角度来看，我觉得 Night Shift 也做得相当相当不错。我是他们的忠实粉丝，他们是 Greylock 投资的。我觉得他们在这个领域也做得很好。是的。我想说的是，SRE 是一个很有意思的用例，这可能又回到了自研还是采购的问题上。我觉得有意思的地方在于，SRE 到底在什么时候、在什么场景下才能真正体现出最大的价值？通常是在你有极其庞大的服务依赖关系、存在这种体量巨大的系统，以及大量的 Kubernetes 和 Helm 文件的时候——就像那种随处散落、规模极大的 Kubernetes 基础设施和 Helm 文件。我觉得这就是为什么 Resolve 在企业级市场上做得非常出色，对吧？你去向福特销售，去向沃尔玛销售，你对他们说：“你们的服务级依赖关系太疯狂了。”你会看到这些展示系统架构的图表，然后他们介入进来，表示：“好吧，我们会尽力去梳理理清这一切。”我觉得在较小的规模下，通常还是可控的，你完全可以自己搞定。但是，对于大企业来说，我觉得他们确实做得很棒。

<details><summary>Original English</summary>
>> So, okay. I mean, like I think the Resolve folks are doing well there. The Resolve is doing well. I would say Night Shift is also doing quite quite a good job there in terms of broadly like background agents. I'm a big fan of kind of like they're greylock backed. I think they're doing doing well in this area as well. Yeah. I I would say that where I think SR is an interesting use case and this might back to the build versus buy question. I think what's interesting about it is like where do when does it become like where does where does an S sur an as like really see the most value? It's typically when you have like a tremendous number of like service dependencies and these like massive sort of like systems and tons of Kubernetes and Helm files like you know just like tremendously large Kubernetes infrastructure Helm that's like files kind of strewn everywhere around. I think that's why um resolve has done really well in like the enterprise, right? Where you go and you sell to Ford, you go and sell to like a Walmart and you kind of say, "Hey, you have your service level dependencies are crazy." Um and you see these these like, you know, these diagrams of how things are set up and then they kind of go in and they're like, "Well, we we'll we'll try and make sense of all this." I think that like at at smaller scales, it's usually still manageable that you can kind of roll your own. But, you know, I will say that for the enterprise, I think they've done a good job.
</details>

>> 是的。对于从未在这种规模下工作过的人来说——因为我当初也是花了一段时间才见识到这种场面——它的量级大概是几万个代码仓库，仓库数量比开发人员还要多。在这些情况下，你根本不知道公司里任何地方运行的到底是什么代码，

<details><summary>Original English</summary>
>> Yeah. for for people who have never worked at this scale because it took me a while to uh to to to to see this it is on the order of let's let's call it tens of thousands of repos more repos than developers. These are the situations where like you don't know what code is running
</details>

>> 因为写那段代码的人大概率早就已经离职了，

<details><summary>Original English</summary>
>> any anywhere in the company cuz probably the guy who wrote is no longer here
</details>

>> 对，离谱的是，顺便说一句，它居然还是核心承重代码。

<details><summary>Original English</summary>
>> right absurd and like by the way it's still low bearing.
</details>

>> 太离谱了。是的，那才是最可怕的地方，完全没错。然后你是那个在值班的人，你面对着一个崩溃的系统，而当年写代码的人早已不在了，只有一些过时陈旧的运行手册（runbooks），你心里直犯嘀咕：“这里到底怎么回事？”这真是一件非常可怕的事情。是的，在企业级规模下，那完全是另外一种截然不同的巨兽。是的。所以对于那种学校里的黑客型开发者，一个人管一个仓库，他们完全无法体会这种处境。但我觉得，如果给他们这种概念，比如把他们丢进一个模拟环境里：你在新工作入职第一天就发生了这种情况，现在你该怎么办？

<details><summary>Original English</summary>
>> That's absurd. That's yeah that's that's the scariest thing that that's absolutely right. It's it's like it's and and then you're you're the person, you know, you're the person who's on call and you're interacting with a system that goes down where that person still isn't there and there's like old out of date runbooks and you're like, "What the hell is going on here?" It's a scary scary thing. And yes, you're at the at the enterprise level, it's like it's a whole whole different beast. Yeah. So, so like the the the kind of like college hacker, they you know, one person per repo, they've never totally no appreciation. But like I think I think if you just give that idea like you drop them in like a simulation of like okay like day one on your job this happens what now?
</details>

>> 是的。是的。这里我还要顺便提一下。Resolve 的团队去年其实为课程设计了一个作业，他们实际上创建了一个沙盒供学生去操作。沙盒内部散布着很多很多正在执行各种任务的服务，甚至沙盒里的那些服务本身还带有 bug。作为作业的一部分，学生们必须实际使用 Resolve 智能体，扮演值班人员的角色去探测系统、排查到底发生了什么。不过，

<details><summary>Original English</summary>
>> Yeah. Yeah. So so another shout out I'll I'll give here. So the resolve folks they actually last year they they made an assignment for the class where they effectively created like a sandbox for students to go and then the sandbox was like strewn I mean the within the sandbox there was like many many services that were doing their various things and there was even like bugs in the services uh within that sandbox and then as part of the assignment the students had to like go and actually uh like use the resolve agent and kind of like probe and play the the human on call person probing the system discovering what's happening Um, but
</details>

>> 他们的网站挺有意思的。

<details><summary>Original English</summary>
>> they've got an interesting interesting website.
</details>

>> 我还没看，我已经有一阵子没看过这个了。

<details><summary>Original English</summary>
>> I do not It's been a while since I've seen this.
</details>

>> 是的，交互性非常强。

<details><summary>Original English</summary>
>> Yeah, this is very interactive.
</details>

>> 好的。他们现在在做类似 PagerDuty 的事情。

<details><summary>Original English</summary>
>> Okay. They're they're being a pager duty now.
</details>

>> 是的。是的。看看这个。对。不过这个视频我当时也在……

<details><summary>Original English</summary>
>> Yeah. Yeah. Check this out. Yeah. But also this like this this uh video I was uh
</details>

>> 你之前提到的，挺有意思，挺有意思，好吧。

<details><summary>Original English</summary>
>> you know you were shouting out interesting interesting but okay.
</details>

>> 好的。除了像这样的交流，我们平时很少有机会去探讨这方面的领域。还有其他细分赛道吗？因为我觉得“AI SRE”这个说法可能太宽泛了，或者根据看待角度的不同，也可能太狭隘了。说它太宽泛，是因为 AI SRE 下面其实有几个子方向挺有意思的；

<details><summary>Original English</summary>
>> Yeah. So okay you know we never get a chance to talk about this side of the world except for conversations like this. any other segments because I think AI SR is maybe too broad or even too narrow uh depending on how you look at it right like too broad meaning well there's several subdivisions of AI sorry that's interesting
</details>

>> 说它太狭隘，是因为那甚至都不是我们面临的最大难题。

<details><summary>Original English</summary>
>> um or too narrow being like well actually that's not even the biggest problem that we have
</details>

>> 所以你怎么看都行。

<details><summary>Original English</summary>
>> so take it however you like
</details>

>> 好的，你是特指针对 Monaco 而言，还是泛指那些正在考虑这套体系的企业机构？

<details><summary>Original English</summary>
>> yeah uh you mean like specifically for for like Monaco or just like broadly for like organizations thinking about this
</details>

>> 泛指，因为那才是我们的受众。

<details><summary>Original English</summary>
>> broadly because that is our audience
</details>

>> 明白了。

<details><summary>Original English</summary>
>> take it
</details>

### 代码审查瓶颈与合并队列

>> 是的，我认为这同样取决于你的规模大小，对吧。我觉得对于企业来说，存在很多并不总是——我甚至觉得答案往往不只是引入更多智能体那么简单。而且既然我们实际上还在讨论第五周的“智能体就绪代码库”，每当我与达到特定规模的公司交流时，真正拖慢他们脚步的反倒更多是一些底层的 DevOps、CI/CD 之类的问题，对吧？他们的合并队列（merge queues）积压了，启动部署一个应用耗时太长。因为实际上存在更多更基础的问题，与丢进去一个 SRE 机器人（或者类似别的机器人）几乎毫无关系，加机器人根本解决不了问题，因为他们必须先解决更多系统性的问题，所以……

<details><summary>Original English</summary>
>> yeah I I think that it again it's it's a function of how your scale Right. And I think that for for the enterprise, they there are a number of issues that aren't always I almost feel like the answer is not even always just more agents. Uh and and since we're still actually on the week five agent ready code bases, like when I talk to companies of like a certain scale, the the things that are holding them back are really more just like low-level like DevOps CI/CD stuff, right? They're like their their merge cues are getting backed up. They it takes too long to like stand up an app. because there's like actually more foundational things that have almost nothing to do with that like throwing in one more S bot or Allah you know a bot wouldn't be the answer to the problem because there's like more systemic things that they need to figure out and so uh
</details>

>> 这就引出了我们……

<details><summary>Original English</summary>
>> so that brings us to we
</details>

>> 是的，完全没错。所以这就让我们进入了，对，完全没错，这就来到了合并队列及更深层的探讨。是的，这可以说是写给现代智能体代码审查的一封“情书”。是的，我认为去年和今年之间发生的最大变化，或许就是大家突然非常清楚地意识到代码审查成了一个瓶颈。尤其是一旦人们彻底拥抱了 AI（AI-pilled），生成代码的速度变得如此之快，理论上一天可以提 30 多个 PR。然后呢？在什么节点上，你决定是要么把自己放在中间，作为一种门禁，按传统方式去审查代码，但那样你实际上就成了约束条件，成了研发速度的咽喉卡点，这显然不好，对吧？那规模化生成的意义又在哪里？要么你就会想，我们怎样才能两全其美：既能充分介入以保证对合并内容抱有信心，同时又能实现规模化合并，并且不至于完全放任自流、不管不顾？所以，我觉得我在这里主要想探讨的就是这种中间地带，对吧？也就是说，存在一类问题，如果你在智能体就绪度上做了周密的设计，在可验证性上做了周密的设计，那么有很大一类问题，你在一定比例的时间里是能够放心地基本直接自动批准的。从设计和架构的角度来看，必须满足什么条件才能做到直接自动批准？又在什么时候你必须介入并表明“其实在这里我仍然希望……”

<details><summary>Original English</summary>
>> yeah exactly right so that's that's where we get into yeah exactly right yeah there we go to the merge Q and beyond um yeah this is a yeah a love letter of sorts to to modern gentic code review um yeah I think that the the the biggest thing that maybe happened between last year and this year was it suddenly became very clear that code review is a bottleneck especially once you people got really really AI pill and and there's the velocity on generation became so high that you know you could in theory like put up 30 plus PRs a day uh and then what like what's at what point do you decide that you either have to institute yourself and put yourself in the middle as some way to to gate and review things in the traditional way but then you're you're literally the constraint you're the choke point of the velocity and that's not good right And then what was the point of generating at scale? Or you say, well, how do we maybe get the best of both worlds where we're instituting ourselves enough that we have trust in what's getting merged, but we're also uh able to kind of like merge at scale, but we're also not kind of like free freewheing it here and anything goes. So a lot of I think what I want to touch on here is just that that middle ground, right? which is like there are there is a class of problems that if you've put in thoughtful design into your agent readiness, you put in thoughtful design around your verifiability. there's a class of problems that you can feel comfortable you know some percentage of the time essentially like auto approving and what has to be true from a kind of a design perspective from like an architecture perspective to just auto approve and when do you have to insert yourself and say actually here I still want
</details>

<!-- chunk 12/18 -->

### 代码审查与规范维护的瓶颈

仔细审查这一点，即使你确实在仔细审查，你仍然是在逐行审查，还是在做别的事情，对吧？

<details><summary>Original English</summary>
to review this carefully and even if you do review it carefully are you still doing line by line review or you doing something else right
</details>

>> 所以对，这里面的一些内容……

<details><summary>Original English</summary>
>> so yeah some of this
</details>

>> 我们今年最热门的话题之一，呃，我们在 Latent Space 有一个特约作者计划，呃，这是来自 Aviator 的 Ankit 写的，他专门写了一篇关于消灭代码审查的长文，因为我觉得你懂的，那可能就像是最终的大 Boss。

<details><summary>Original English</summary>
>> we one of our hottest topics of this year uh we have a guest writer program for latent space uh this is from Ankit from Aviator and he has a whole thing on killing the a review because I you know that that that is like maybe the final boss
</details>

>> 呃，那个瓶颈所在。他提到了几个……

<details><summary>Original English</summary>
>> uh of of that's that's a bottleneck. He has a few
</details>

>> 呃，他借以实现这一目标的关卡。我不知道你有没有跟 Ankit 聊过，或者……

<details><summary>Original English</summary>
>> uh gates by which he does this. I don't know if you you've talked to Vankit or
</details>

>> 聊过。没，我读过这篇文章。是的，是的，是的。我没跟他本人聊过，但我绝对读过。

<details><summary>Original English</summary>
>> Yeah. No, I've read this post. Yeah. Yeah. Yeah. I haven't spoken to him personally, but I' i've definitely read
</details>

>> 大体正确，有什么批评意见吗？

<details><summary>Original English</summary>
>> mostly right any criticisms?
</details>

>> 没有，我觉得这是对的。我的意思是，大体上是对的。嗯，我猜你提到了一个词，比如最终 Boss。嗯，也许并不是，我认为有两个卡点。一个是审查，另一个大概就是顶层的意图或诸如此类的东西，对吧？比如这……

<details><summary>Original English</summary>
>> No, I think this is right. I mean like broadly right. Um I guess you mentioned one thing like the last boss. Um maybe not I think there's two choke points. There's the review and there's probably like the intent or kind of the thing at the top, right? like this is
</details>

>> 而且还有一些统计数据，我也喜欢拿出来看。你知道，每个人的数据肯定都不一样。这是肯定的。

<details><summary>Original English</summary>
>> and there's some there's some stats as well that that I like to pull up. You know, everyone's stats is different for sure. For sure.
</details>

>> 但显而易见，合并代码的人更多了。显而易见，审查的数量并没有随着……

<details><summary>Original English</summary>
>> But like clearly more people are merging. Clearly the number of reviews are not increasing in line with
</details>

>> 呃，没有随着合并的增加而同步增加。

<details><summary>Original English</summary>
>> uh with merge.
</details>

>> 没错。没错。如果你看看任何一家现代公司，那种真正投入其中并仔细思考过这个问题的公司，有些人已经发表了关于这方面的文章，我相信你们肯定也会写这方面的文章。嗯，但我认为最近像 Amplitude，还有嗯，我觉得 Cloudflare 也写了一篇很不错的。我认为 Augment 也写了一篇很棒的文章，讨论了他们 AI 代码审查系统的设计。嗯，这些都是非常棒的，如果你想分享其中一些链接的话。我觉得他们写得非常精彩。嗯，对，所以顺便向……我其实嗯，向 Cloudflare 致敬，因为我觉得像……呃，某种意义上有点像传统公司，或者说是规模比较大的公司，但我认为他们在围绕 AI、围绕 AI SDLC 的内容产出方面做得太出色了。嗯，所以我觉得他们那篇写得很好，但长话短说，嗯，是的，我认为确实如此。我认为我们仍在寻找那个最佳平衡点。什么东西是可以自动批准的？什么东西是不能真正自动批准的？如果它不能自动批准，即使在必须需要一定人工审查的世界里，我们又在审查什么？我们仍然是在逐行看代码，还是在结合规范做某种权衡？而且你知道，我认为这里又是另一个完全独立的问题了。但是大家有没有随时保持……你们大家有没有随时保持规范的最新状态？呃，规范是根本不可能保持最新的，对吧？

<details><summary>Original English</summary>
>> That's right. That's right. And if you look at any modern uh sort of company that's that's that's really invested in this and thought about this carefully and some people have already done posts about this and you I'm sure we'll do posts about this as well. Um but I think recently like the amplitudes and um I think Cloudflare has has done a good one. I think Augment has also done a good one where they talk about the design of their AI code review system. Um these are a bunch of really good if you want to share some of those links. I think they're fantastically written posts. Um yeah, so shout out to I actually um shout out to to Cloudflare because I think like um very like kind of like you know in a sense like legacy company or like you know bigger company but I think they've done a fantastic job in terms of just their their content around the AI the AIS DLC. Um so I think they have a good post there but TLDDR um yes I think this is true. I think that there's we're still fi finding that sweet spot. What is auto approvable? What is not really auto approvable? And if it is not auto approvable is even in that world of something that has to be somewhat human reviewed, what do we review? Are we still doing the line by line or are we doing some some combination of the spec and you know I think this yeah again a whole separate question there as well. But are people keeping uh are you guys keeping the spec up to date at all times? Uh the spec is no way, right?
</details>

>> 是的。没有。额，我的意思是，好吧，规范存在于几个不同的地方，对吧？比如，存在于像 Linear issue 中的规范，也存在于像 PR 描述上下文中的规范，对吧？所以，你可以把 PR 描述作为你以一种更浓缩的形式大致描述整个实现的地方。只要那是代表代码库当前时间点的最新内容，我其实认为这就足够了。所以，我们对 PR 描述非常用心。我们不会只让它写成一段话。它实际上更像是一个说明该 PR 中所发生变更的规范，甚至还包含了文件级别的指针指向那些发生变更的地方。因此你不仅能了解宏观上发生了什么，甚至还能了解文件的构造以及你触及的服务层边界。所以你知道，我认为那是我们投入相当多的地方。因此我对那种说法持保留态度，因为在我看来，最起码的一点，它在内部应当与 PR 规范保持一致。

<details><summary>Original English</summary>
>> Yeah. No. Well, I mean, okay, in a few different places, right? So, like there's a spec that as it exists in like a linear issue and there's a spec as it exists in like the context of a PR description, right? So, you can like you can have your peer description be the place where you like describe more or less the entirety of the implementation in a more condensed format. And as long as that's the most that's the most upto-date thing representing this point in time of the codebase, I think that's sufficient actually. So, we're thoughtful about like our pure descriptions. We make them be not just like, you know, a one paragraph. It's more like it is effectively like a spec of what has happened in the PR and there's even like kind of line um file level pointers to things where things have changed. So you not only get the high level of what's happened but even the kind of the the construction of the files and sort of the service level boundaries that you're touching. So you know I think that's where we we've invested quite a bit. So I push back on that because to me of course it's you know bare minimum it should be internally consistent with the PR spec.
</details>

>> 当然，不是，我的意思是整个功能、整个代码库的规范，因为那是所有 PR 的总和。也就是说，如果你的 PR 规范弄错了或者遗漏了什么，问题就会出现在整个代码库本应实现的功能与你的 PR 试图实现的功能之间的差异上。

<details><summary>Original English</summary>
>> Sure the no what I meant is the spec for the feature the codebase because that is the summation of all PRs that that is like if your if your PR spec got it wrong or missed something it's going to be the delta between what the whole codebase is supposed to do versus what your PR is trying to do.
</details>

>> 嗯。所以，所以我的意思是，我并不指望你会有答案，因为我自己也对这件事情感到非常头疼。我试着指示模型去做这件事，它们做得很差。

<details><summary>Original English</summary>
>> Mhm. So, so I I mean I don't expect you to have an answer because like I really stress about this myself. I try to instruct models to do it. They're bad at it.
</details>

>> 就是这样。

<details><summary>Original English</summary>
>> That's it.
</details>

>> 所以，人类才是规范之神，掌管着诸如“五周前我做了另一件事，现在你们却在推翻它”这样的全局信息。

<details><summary>Original English</summary>
>> So, so the humans are the the spec gods of like well five weeks ago I did this other thing and now you're reversing it.
</details>

### 代码库状态与任务表征的演进

>> 你看过 Basis 发的那篇……他们发的一篇推特、推特短文吗？我觉得他们讲得非常好，讨论了通过 Git 追踪的不同类型的文件产物。其中一些是规范，即预期的意图；另一些则是他们所称的代码规范状态，这可能更接近你刚才描述的，即隐性知识、隐性意图，这也必须在某个地方被形式化沉淀下来，对吧？所以那部分是全部纳入版本控制的，我觉得他们发现这种做法对他们很管用，所以那可能也是值得分享的另一篇内容。

<details><summary>Original English</summary>
>> Have you seen the um the post from Basis? Like they have a they had a tweet tweet little thing uh tweet article. I thought they did a great job talking about um like different sort of file artifacts. they they they track via git and some of them are like the specs the intent of what is to be and the other is like what they call like the canonical state of the code which is like a little bit more maybe what you're describing which is implicit knowledge implicit intent that also has to be codified somewhere right so that part that's all version controlled and I think they found that to work for them so that might be another thing to share as well
</details>

>> 正在试着翻出它，这是 Basis，那家财务会计软件公司？

<details><summary>Original English</summary>
>> is trying to pull it up this is basis the the accounting company
</details>

>> 那家会计公司，完全没错。是的，我们马上要邀请 Mitchell 参加我即将在纽约举办的会议，跟他聊聊这个。我很喜欢他们提出这种方案。我对这个问题的解决方案是……呃，我不知道自己准备好聊这个没有，因为我可能永远不会发布它。呃，它是一种为了捕获所有这些内容而替代 Git 的东西。

<details><summary>Original English</summary>
>> the accounting company exactly right yeah we're um we're having Mitchell at uh my New York conference soon talk to him about that I like that they are coming out with this. My solution for this is um I don't know if like how ready I am to talk about it cuz I may never ship it. Uh is something that is replacing git in order to capture all of this.
</details>

>> 呃，所以我称之为程序数据库（program database），呃，它捕获所有的 trace，并将所有规范具象化为我们既可以忽略又可以保留的东西，呃，并且它还同时控制附加在它之上的各种 skills。因为我认为，基本上 Git 仅仅关注代码，而你只需要一个单一真实来源（source of truth），它不仅包含代码之外的一切，包括所谓的隐性假设，或者说约束、意图以及……

<details><summary>Original English</summary>
>> Uh so I call it a program database uh where it captures all traces and all and and raifies specs to something that that we that we can ignore and keep uh and it also controls the skills that are attached to it uh as well. Because I think like basically what git is only focused on code and then you just need a source of truth that is uh not only uh everything else outside the code including the the implicit what what do you call implicit assumptions or like the constraints the intent the
</details>

>> 其他东西，呃，而且还是高度并发的，因为 Git 在设计上到处引入互斥锁（mutxes），这很糟糕。

<details><summary>Original English</summary>
>> other stuff uh but also multi- like highly concurrent because git is git by intro by design introduces mutxes everywhere which sucks
</details>

>> 呃，所以你需要极高的并发性。你见过 GitButler 吗，是叫这个吗？好像是的。就是那个以前做 CTO 的人。

<details><summary>Original English</summary>
>> uh so so you need like super concurrency. Have you seen um uh it get Butler is it? There's like Yeah. The guy who used to be CTO
</details>

>> 我想他的名字是 Ian。

<details><summary>Original English</summary>
>> Ian I think is his name.
</details>

>> 我忘了他的名字，不过是的。

<details><summary>Original English</summary>
>> I forget his name but yeah
</details>

>> Scott，Scott，Scott，Scott。嗯，所以是的，我认为有很多人……

<details><summary>Original English</summary>
>> Scott. Scott Scott Scott. Um so yeah so I think there's there's a lot of people
</details>

>> 都在朝这个方向努力。嗯，我认为这里存在一个问题，就是究竟什么才是任务的理想表征？是的。

<details><summary>Original English</summary>
>> going after this. Um and I think there's the there's the question of like really what is the ideal representation of tasks? Yeah.
</details>

>> 而且我认为赢家……

<details><summary>Original English</summary>
>> And I think the winner
</details>

>> 可能不是我，是 Linear。

<details><summary>Original English</summary>
>> probably not me linear
</details>

>> 真的吗？

<details><summary>Original English</summary>
>> really
</details>

>> 因为任务就沉淀在他们那里。

<details><summary>Original English</summary>
>> cuz like that's where the the task are.
</details>

>> 是的。呃，而且显然他们已经决定转型成为一家编程智能体公司了，

<details><summary>Original English</summary>
>> Yeah. Uh and like clearly they have decided to become a a coding agent company,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 而且，你看，只要你深度使用 Linear，他们就拥有那里所有的单一真实来源。

<details><summary>Original English</summary>
>> And well, you know that they have all the source of truth there as far as you as long as you buy into linear.
</details>

>> 是的，是的。确实如此。确实如此。我想知道，我心中持有一个类似的观点，我认为很多公司都会演进成某种版本的编程智能体公司，也就是任何与 B2B 软件发生交互、在其中收集有关用户的信息或某种产品洞察的公司。我认为你同样可以形成闭环，因为编程智能体的终极本质，它的目的就是根据用户或客户参与的某些事件采取行动，然后理想情况下用它来修复产品的某个方面，对吧？我觉得 Linear 在做的正是这个。我想象类似的事情 Amplitude 也能做，对吧？因为他们也掌握关于用户分析、用户问题的洞察。我想象甚至如果你把思路再放宽一点，你甚至可以让 Decagon 或 Sierra 类似的产品来做同样的事，明确这里出了什么故障，然后去形成闭环。

<details><summary>Original English</summary>
>> Yeah. Yeah. That that is true. That is true. I I wonder I I have like this somewhat like kind of held belief that I think a lot of companies are going to evolve into some version of a coding agent company which is any company that has like an interaction with B2B software where you're collecting something about the user or some like product insight. I think you can also close the loop because ultimately like what a coding agent is the purpose of coding agent is to act on some adventure thing that's happening where users involved or customers involved and then use that to like fix ideally some aspect of the product right I think what linear is doing I imagine the same thing like an amplitude could do as well right because they're also getting insights about user analytics user problems I imagine even like you want to really stretch it you could even have like a decagon or serum do something similar where you know here's what's broken go close the loop
</details>

>> 好的，所以把所有这些东西都搭建好，打造一个为智能体准备就绪的代码库，并设置好代码审查。安全审查是在第七周做的事，它不是第一周要干的事。

<details><summary>Original English</summary>
>> yeah all right so set all those things up for agent ready codebase and set up code review. Security is week seven. It's not week one.
</details>

>> 同学们，

<details><summary>Original English</summary>
>> Students,
</details>

>> 你说什么叫安全不重要？

<details><summary>Original English</summary>
>> what what do you mean security is not important?
</details>

>> 我是在开玩笑，因为我总是说，呃，你看，在亚马逊，第零号工作永远是安全，他们总是这么说。

<details><summary>Original English</summary>
>> I make fun because I always say like uh you know at Amazon job zero is security and they always say this.
</details>

>> 是的。是的。

<details><summary>Original English</summary>
>> Yes. Yes.
</details>

<!-- chunk 13/18 -->

>> 不管怎样，在最后做安全审查。好的。

<details><summary>Original English</summary>
>> Anyway, but yeah, security review at the end. Okay.
</details>

>> 我之前在亚马逊，我不记得这个了，但我相信——

<details><summary>Original English</summary>
>> I was at Amazon and I don't remember that but I I believe
</details>

>> 这是安迪·贾西（Andy Jassy）常说的话。

<details><summary>Original English</summary>
>> this is the thing Andy Jesse says.
</details>

>> 好，明白。我是在杰夫（Jeff Bezos）时期待过一段时间，后来一部分时间正好赶上过渡到安迪。不过是的，我觉得这个话题去年有人提，今年也是一个焦点。而且 Isaac 去年也发过言。我觉得他是一个非常有深度的人，是这个领域里很有思想的领导者。我认为 Semgrep 是一家很有意思的公司，因为他们在智能体出现之前就已经存在了。开源代码库的存在远早于传统的 SaaS 防御机制。但我认为他们做得很不错，他们调整了方向——或者说不是转型，而是把自身的产品能力扩展增强到了这个领域。当下确实是个有趣的时期，发生了很多事情，这些攻击载体现在都开始浮出水面。现在有越来越多的劣质内容和 AI 生成的代码。我认为在这里我想传达的一个核心观点，就是依赖项追踪和供应链管理。基本上就是供应链方面，你必须谨慎对待依赖项，做好适当的版本锁定，不要随随便便执行 `npm install` 就指望整条链条万无一失。

<details><summary>Original English</summary>
>> Okay. Okay. Okay. I see. I see. And that was I guess he I I was there partly during Jeff's time and then partly when was transitioning to Andy. So, but yes, I I think um this is a thing a topic last year as well and it's it's also one this year and I think that there I um Isaac also spoke last year. I find that he's an incredibly thoughtful thinker uh thoughtful thinker, you know, a thoughtful thoughtful leader in sort of the space. I think Sam Grup is an interesting company because they've been around even before sort of agents, right? I mean, the the OSS repo was exist well before kind of traditional SAS kind of defense mechanisms. Um but I think they've done a good job of pivoting and or not pivoting augmenting their offering into this space. Um you know I think it's it's um it's an interesting time right uh there's just a lot going on where these these attack vectors are now kind of coming to the surface. there's a lot more slop and AI generated code and I think maybe one of the core insights that I want to drive here is just the idea of like dependency kind of dependency tracking and supply management basically like supply chain right um you have to be careful about like your dependencies and and pin things appropriately and don't just arbitrarily hit npm install and expect the chain to go
</details>

>> 对，所以从潜在角度来说，最安全的代码库就是没有任何依赖项的代码库。

<details><summary>Original English</summary>
>> yeah so potentially the most secure codebase is one with no dependencies
</details>

>> 没错，完全正确。你看到某个依赖项会觉得：“这个依赖项很棒，实现得很专业，但我打算自己写一个。”

<details><summary>Original English</summary>
>> yes right that's correct you you look at the dependency you're like cool dep cool implementation pro, but I'm just going to make my own.
</details>

>> 完全正确，确实如此。这也是个很有意思的视角，因为它走向了极致。虽说知易行难，但如果你认为代码如今已经商品化，编写代码既容易又廉价，那为什么不全部自研呢？当然，那样做确实最安全，因为你看过所有代码，掌控一切，而不是依赖 Axios 之类的库。不过，我们拭目以待到底有多少人真会这么做。但这确实是最安全的做法，我赞同你的看法。不，其实这种说法很危险，因为那样你就只会犯自己的错误，而不是依靠大家去发现错误。开源的精髓就在于——怎么说的来着——阳光是最好的消毒剂。

<details><summary>Original English</summary>
>> That's absolutely right. That's absolutely right. And and that's an interesting insight because it's sort of to the limit. And you know, I think it's it's probably easier said than done, but if you believe that with code now being commoditized, code being easy, cheap, why not just build everything in house, right? Like that like of course that's and that would be the safest thing because you've seen everything, you control everything instead of, you know, depending on Axios or whatever. But, you know, we'll see how many people actually act on that. But that is the safest thing. I agree with you. No, I so that statement is dangerous because then you would just make your mistakes instead of making relying on other people to discover mistakes. The whole point of open source is that you know what is it like uh sunlight is the best disinfected.
</details>

>> 这就像林纳斯定律（Linus's Law）。确实，如果你全靠自己的定制软件依赖，发现问题的速度会极慢，因为你只有自己的这批用户，而且他们有了问题也不会向你汇报。但如果一个东西全球有十万名用户，总会有人发现漏洞——

<details><summary>Original English</summary>
>> It's like linville's thing and it's it's like well yeah you will be very slow to discover your own custom software dependencies cuz you only have your users and they won't report it to you. But if this this thing has 100,000 users worldwide, someone will find something
</details>

>> 然后你就可以更加信赖它，对吧？

<details><summary>Original English</summary>
>> and then you can depend on it more, right?
</details>

>> 呃。

<details><summary>Original English</summary>
>> H
</details>

>> 是的，这根本……我其实是想充当理性的声音，你不能在两个极端上走绝对化路线。我刚才算是给你设了个套，把你引到了那种论调里——

<details><summary>Original English</summary>
>> yeah, this is this is there's no basically I I don't I'm trying to be a voice of like reason and you cannot be absolutist in both and uh you I I kind of trapped you there. I tal I talked to you into the talk track of
</details>

>> 把所有东西都自研内置。

<details><summary>Original English</summary>
>> vendor everything.
</details>

>> 没错，对。

<details><summary>Original English</summary>
>> Right. Right.
</details>

>> 那样其实是有隐患的。

<details><summary>Original English</summary>
>> And there is a bug there.
</details>

### 开源软件工厂与 AI 安全前景

>> 是的，这个问题很有意思。我也在想这能在多大程度上……我赞同其中的一部分观点，但这里面又有多少会受到一个事实的影响——我一直有种信念，认为大多数开源项目（即便不是全部）未来都会变成基本上由智能体驱动的软件工厂。如果真变成那样，情况会如何？

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. It's an interesting one. I I wonder how much that that how much is that I I buy some aspect of that but how much of that is impacted by the fact that everything I I have this belief that like most OSS repos if not all of them will just become soft for factories that are effectively agent run in the future. what happens then where like
</details>

>> 哪怕你看像 Warp，Warp 是一个编码智能体，他们当然也在销售软件工厂类的产品，但他们本身也是把开源的 Warp 终端当作软件工厂来运作的。这几乎表明，虽然人类依然参与其中，但参与程度越来越低。肯定不再是每个人都会把合进来的每一行代码都审查到过去那种严苛程度。这会让代码库面对安全漏洞时变得更脆弱还是更坚固？现在很难说。我认为这正是存在细微差别的地方，我们甚至包括我认识的做开源软件的人，都还在努力弄清那个稳定平衡点到底在哪里。

<details><summary>Original English</summary>
>> I mean even um like even if you look at warp right like warp which is a monocoding agent of course they're also you know selling a software factory product but but they are running their warp open source warp terminal as a software factory and that almost suggests that there's a part where yes humans are still involved but increasingly less so certainly not every single person is reviewing every single thing that comes in to the maybe the same exact level that we did in the past does that make this code base more or less vulnerable to securityurities it's a bit hard to say Um, I think that's just where there's a little bit of nuance that I think we're still and even the folks that I know that I that work in OSS are trying to figure out exactly what that stable point is.
</details>

>> 对，这里有几个相关的论点，我也乐意继续聊聊，安全是一个无休止、涉及面极广的领域。Vercel 的 Malte 提出过一个论点，他说：“大家听着，让我们把所有用 C、C++ 写的强依赖核心软件都移植到 Rust 上，我们会更快、更安全，大概花不了 600 万美元就能搞定。”然后还有另一个论点，这与模型实验室在技术前沿推进节奏上的做法相关。他们认为：“我们可以先放慢速度，做 Daybreak，做 Glasswing，确保大家都打好了补丁，然后再全力加速。”所以我觉得大家天然有一种信念，认为模型能解决所有的安全问题。

<details><summary>Original English</summary>
>> Yeah, there there's a couple of related arguments and then I'm I'm happy to to keep going like security is like a non-stop like huge huge huge huge surface area thing. There's one argument from Malta of Verscell who's like okay guys let's take every single like high depend highly dependent on software that's written in C C++ port it to Rust and it's like we'll be faster more secure uh and like it it won't probably take like $6 million and but you you you'll get it done and and then there's there's another argument for this this also links to pacing the frontier from the the open source from the model labs who are like okay let's slow down so that we or like we'll do Daybreak, we'll do what's glass wing, we'll make sure everyone's patched and then we can let loose on rampant acceleration. Uh so I think like there there's there's there's an inherent belief that the models will fix all security
</details>

>> 但在我看来这还没得到证实，因为万一它们引入了新的漏洞呢？

<details><summary>Original English</summary>
>> and I think it's just unproven to me because what if they introduce new bugs
</details>

>> 而且只是不同类型的漏洞？

<details><summary>Original English</summary>
>> and they're just different bugs?
</details>

>> 没错，完全是这样。所以我其实是在等反驳，我等着有人说：“不，你真是个蠢货，显然模型在这方面要强得多。”

<details><summary>Original English</summary>
>> That's right. That's right. That's so so I I mean well I'm looking for push back. I'm looking for like well no you're you're you're an idiot. Like obviously your models are way better at this.
</details>

>> 是的。我猜推到极致的话，问题就变成了：我们是否相信模型能创造出完美的软件？如果模型能创造出完美的软件，那问题就解决了。真的有这种可能吗？如果能，那就皆大欢喜了，那我们干脆什么都不用干了，大家回家去海滩上躺平度过余生算了。

<details><summary>Original English</summary>
>> Yeah. Uh I I guess like that's almost like in the limit there there's the question is like is is a model do we believe a model will create perfect software right? If a model is creating perfect software then then you're done. Is there such a thing then then that's done right? Then then we have then we're done here at all. Like then then we're just going to go home and and and chill on a beach for the rest of our lives.
</details>

>> 我觉得这里还有一个问题：先把它开放用于安全防御，让大家先打补丁，推迟发布，之后再正式发布，这样就足够了吗？还是说存在另一个问题——

<details><summary>Original English</summary>
>> I think there's also the question of is it good enough to first give it for security? to let people patch then just delay the release and do it after or is there a problem of
</details>

>> 觉得它找漏洞的能力要强得多，哪怕你打了补丁，也可以全力以赴测试更久，或者……

<details><summary>Original English</summary>
>> oh no it'll be much better at finding vulnerabilities you can full send test it for longer even if you've patched or like
</details>

>> 能有多久呢？你给 3 个月时间，别人可以用 6 个月来尝试攻破它，问题并没有解决，对吧？

<details><summary>Original English</summary>
>> how long right you can give it for 3 months someone can try to exploit it for 6 months the problem's not solved right
</details>

>> 对，没错。

<details><summary>Original English</summary>
>> right right yeah
</details>

>> 我对这种做法的整个质疑点——这也是一大通话题，我们不必展开讲——就是比如你指定了 100 家受信任的组织，把它们列为优先对象，让它们使用网络安全模型。可你这么做其实是为我创造了 100 个可以去攻破的攻击途径，而且顺便说一句，攻破它们相当容易。

<details><summary>Original English</summary>
>> yeah my whole problem with like and again like this is a whole rant that we don't need to go into but like you know you name 100 bless organizations that like okay these are like priority they they have access to a to a cyber model that uh you've just created 100 attack vectors for me to go compromise and like they're by the way they're pretty easy to compromise.
</details>

>> 是啊，所以我也说不好。总之，这超出了我们的能力范畴。

<details><summary>Original English</summary>
>> Yeah. Yeah. So I don't know anyway um that above our pay grade
</details>

>> 不过聊聊安全领域的热门猛料还是挺有意思的。

<details><summary>Original English</summary>
>> is fun to get juicy in you know security like
</details>

>> 我是说安全现在确实是个非常诱人的热门领域，我觉得安全圈的人其实挺享受现在的状态，因为他们平时通常得不到那么多关注，而现在吸引了海量关注。

<details><summary>Original English</summary>
>> I mean security is right now very juicy right like and like I think actually the security folks love it because they like they usually don't get that much attention and now they have like a ton of attention.
</details>

>> 真的吗？你说他们平时得不到关注？我发现至少从风险投资的角度来看，风投家们非常热衷于投资安全公司，而且回报也相当——

<details><summary>Original English</summary>
>> Is that true? like I I mean and that they don't get attention. I find that um I find that at least from like a VC perspective, people love VCs love investing in security companies and have like pretty good
</details>

>> 像 Wiz 之类的公司做得非常非常成功。

<details><summary>Original English</summary>
>> like a whiz or something like has done very very well.
</details>

>> Wiz，可能还有 Socket。我两天前刚跟一位风投聊过这个。显然在过去 5 年里，真正做成功的安全公司只有 Wiz 和 Socket。

<details><summary>Original English</summary>
>> Whiz is arguably whiz and socket. Uh I literally I had this conversation with VC two days ago. Apparently whiz and socket the only security companies in the last 5 years that have worked.
</details>

>> 那像 Abnormal 呢？

<details><summary>Original English</summary>
>> What about like abnormal?
</details>

>> 我不知道从风投的角度来看它算不算成功——

<details><summary>Original English</summary>
>> I don't know what it worked for a VC point of view of
</details>

>> 我懂了，你指的是从商业回报的角度来看。

<details><summary>Original English</summary>
>> I see from like from like an economics perspective.
</details>

>> 是的，有意思。这轮不到我来评判，显然那个领域有很多优秀的玩家，但我认为那确实是一个非常艰难的行业。所以基本上，虽然这不是什么有争议的观点，但任何安全公司最好的时机，都是在高调重大安全事件刚发生之后。

<details><summary>Original English</summary>
>> Yeah. Interesting. No, not not for me to say, right? Obviously many like great players in in in that field, but it's it's a tough tough industry, I think. And so basically like the best time but I think it's not controversial. Best time for any security company is when an high-profile incident just happened.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对吧，显然到那时候你就能大卖一堆安全产品了。绝对是这样。

<details><summary>Original English</summary>
>> Right. Obviously like then obviously you're going to sell a bunch of security. Totally.
</details>

>> 是的。所以我认为让大家提高警惕是合理的，人们应该了解基本的防范措施。我确实——

<details><summary>Original English</summary>
>> Yeah. So so I I think I think that's a fair thing like people people should be aware. People should know the the basic mitigation mitigations. I do
</details>

<!-- chunk 14/18 -->

我认为代码扫描很重要，但我只是想让大家明白，模型会引入你作为人类不会犯的 bug，如果你不去检查那些 bug……

<details><summary>Original English</summary>
think like code scanning is important, but like I I just want to give people the the idea that like no models introduce bugs that you wouldn't make as a human and like if you're not checking those bugs then
</details>

>> 甚至不仅是它们会制造 bug，而是你对自己正在写出的东西感知变弱了，对吧？比如当……

<details><summary>Original English</summary>
>> it's not even that they make bugs, it's that you have less awareness of what's being written, right? Like when
</details>

>> 是的。全面审查。

<details><summary>Original English</summary>
>> Yeah. reviewing everything.
</details>

>> 是的，是的。先别管 bug 了。模型其实挺厉害的。平均来说，我认为它们的 bug 还会更少一些。问题还在于你甚至不知道自己发布了什么，就像……

<details><summary>Original English</summary>
>> Yeah. Yeah. Forget bugs. Models are pretty good. They'll have on average, I would say, less bugs. The problem is also that you don't even know what you're putting out like
</details>

>> 是的，

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 很多这种情况。

<details><summary>Original English</summary>
>> there's a lot of that.
</details>

>> 是的。所以我想我们必须考虑缓解措施，并且这算是安全与作为代码审查一部分的安全的结合，对吧？我的意思是做这些检查我认为很重要。

<details><summary>Original English</summary>
>> Yeah. And that's I think we have to be thought about mitigations and and like the and there's sort of a combination of security and and security as part of code review as well, right? I mean think this is also like doing those checks I think is important.
</details>

>> 是的。所以我想也许我在这里再多说一点，或者帮我验证一下我在这件事上的直觉，那就是代码库的不同部分并不是完全平等的。代码库中对安全极其重要的部分是数据存储……

<details><summary>Original English</summary>
>> Yeah. So so I think um maybe I would say one more thing here uh or or check your check my intuition on on this thing is that uh not all parts of the codebase are created equal. the parts of the codebase where security is very important is data storage
</details>

>> ……以及计费。所以我们就称之为数据、计费。身份认证（authN）和权限授权（authZ）显然与所有这些东西相关。这些基本上是绝对不可轻率改动的 VIP 代码，至于其他部分，放开去干就好。

<details><summary>Original English</summary>
>> um and uh billing. So let's call it that data billing uh off and off is obviously related to all those things and those are basically don't vip code and then everything else go nuts.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我认为完全正确。完全正确。

<details><summary>Original English</summary>
>> I think that's absolutely right. That's absolutely right.
</details>

>> 而且很有意思的是，如果你不知道 authN 和 authZ 之间的区别，请去搞清楚。然后，如果你从来没有看过 AWS IAM（虽然你看过），也请去弄明白。这些都是需要理解的基本概念，一旦掌握了这些术语，你就可以通过 prompt 去调用；如果没有这些术语，你就……

<details><summary>Original English</summary>
>> And and and it's really funny how like okay well if you don't know what the difference between offend and off Z is please learn it. And then you know if you if you don't know if you have never looked at AWS IM which you have please learn it like this like these are basic like conceptual things to understand that you can prompt for once you have the language you can prompt for it. You don't have the language you're
</details>

完全同意。完全同意。是的。是的。在某种程度上，我甚至会把这一点延伸到某些特定的云平台上，对吧？我记得之前有一家公司遭遇了那起大事件，一次严重的故障，就像仅仅是一个 DNS 问题就导致了宕机，你还记得吗？是不是……

<details><summary>Original English</summary>
Totally. Totally. Yeah. Yeah. To an extent I even extend that to like just general like certain certain cloud platform of things right. I mean there was the I forget which company got had that hu incident huge incident where like it was just like a DNS issue that brought down was it do you remember this? Was it
</details>

>> DNS 问题？你得缩小一下范围。

<details><summary>Original English</summary>
>> DNS issues? You need to narrow it down.
</details>

>> 是的，我知道。我知道。有一个特别著名的。是不是……

<details><summary>Original English</summary>
>> Yeah, I know. I know. There was a particularly prominent one. Was it
</details>

>> 著名的 DNS 问题也有过很多起。

<details><summary>Original English</summary>
>> There have also been many prominent DNS issues.
</details>

>> 好吧。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 但你可以列举一下。

<details><summary>Original English</summary>
>> But list them off.
</details>

>> 永远都是 DNS。总是这样。所以 DNS 更多属于可靠性、正常运行时间的范畴。

<details><summary>Original English</summary>
>> It's always DNS. It's always Yeah. So DNS is more of like a reliability uptime.
</details>

>> 确实。确实。

<details><summary>Original English</summary>
>> Sure. Sure.
</details>

>> 安全方面，大家关注的是：你亏钱了吗？你泄露客户信息了吗？

<details><summary>Original English</summary>
>> Uh you know security I think people like did you lose money? Did you leak customer information?
</details>

>> 是的，是的，是的，是的。我肯定会把那些排在 DNS 前面。提到 DNS 仅仅是因为正常运行时间。是的，总体的正常运行时间。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. Yeah. Yeah. That I would Yeah. Probably put that above that for sure. Only DNS because of uptime. Yeah. General up time.
</details>

### 后台 Agent 与全栈架构

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> SLA 之类的，比如后台 agent。现在你请来了 Coffee 的朋友，但我的意思是，你的嘉宾并不一定和当周的主题绑定，对吧？

<details><summary>Original English</summary>
>> SLAs and stuff like uh background agents. Uh now you got your buddy from Coffee here, but I mean your guests aren't necessarily correlated with that week, right?
</details>

>> 是的。第九周确实存在一点排期问题，我安排了 Elad，我想我第九周肯定没有……Elad 我原本想把他排在最后，但时间上实在协调不开。所以是的，这稍微有点奇怪，我想第九周我完全不讲课，但我们在第十周会重新回到那些话题。所以安排得有点交错，形式上有点奇怪。是的，第八周。Rajesh 一直在负责 Cloudflare 的云基础设施、开发者体验（DevX）及相关领域的大量基础架构工作。正如我之前所说，我认为他们在这方面做得非常出色，对于他们这种规模的公司、这种体量的上市公司来说，他们的落地应用是非常惊人的，而且我认为他们的技术内容也极好。归根结底，这关乎你使用异步后台 agent 的各种方式。我想我也打算花不少时间讨论，比如 Stripe 的 minions，Spotify 的——我忘了他们那个版本的名称了——以及 Ramp 的 inspects 等类似的东西，我认为所有这些都在展示当你将其向外扩展时会是什么样。

<details><summary>Original English</summary>
>> Yeah. No, I mean like the the nine one was a little bit of a scheduling thing where I've thrown in, you know, Elad and and I guess I'm isn't with definitely week nine. Elad I was trying to get him at the end, but I think it was just timing wise couldn't work it out. Um so yeah, it's it's a bit of a weird one where I don't I guess I'm not lecturing at all week nine, but but we're coming back to those topics in week 10. So it's a little bit staggered in a in a bit of a bizarre way there. Yeah, week eight. Um, Rajesh who has been leading a lot of like the infra stuff at uh Cloud Infra uh DevX and and beyond at Cloudflare which as I earlier said was I think they're doing a great job here and definitely their adoption for a company of their size and a public company of their size is is fantastic and then their content I think is also really good. I mean this is fundamentally about all the ways you can use like asynchronous background agents. Um, I think I'm also going to spend quite a bit of time talking about, you know, the Stripe minions, the Spotify, I forget the name of their version of this. Um, the ramp inspects, the, you know, things of that nature that I think are all kind of showing what does it look like when you scale this out.
</details>

>> Tag Instinct。

<details><summary>Original English</summary>
>> Tag Instinct.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> Muse。Muse。

<details><summary>Original English</summary>
>> Muse. Muse.
</details>

>> 是的。我的意思是，可能少讲面向消费者的，更多关注软件团队如何在大规模下使用它们。

<details><summary>Original English</summary>
>> Yeah. I mean, I guess less on consumer, more on like, you know, software teams using them at scale.
</details>

>> 底层全都是编程 agent。

<details><summary>Original English</summary>
>> They're all coding agents under the hood.
</details>

>> 确实。

<details><summary>Original English</summary>
>> True.
</details>

>> 一切都是编程。

<details><summary>Original English</summary>
>> Everything is a coding.
</details>

>> 是的。比如 Grokbot 就是其中一个有趣的例子，虽然非常偏向消费级定位，但其底层是 Grok，底层其实是 Cursor。

<details><summary>Original English</summary>
>> Yeah. Like Grockbot is one of those interesting things where like very very much presented as consumer e uh it's it's Grock under it's you know it's it's cursor under the hood.
</details>

>> 是 Cursor 团队做的。

<details><summary>Original English</summary>
>> It's the cursor team. It's
</details>

>> 不，确实如此。我见过 Cursor 在那些点点点里运作，但他们并没有整合代码库，对吧？

<details><summary>Original English</summary>
>> no no for sure. Like so I I've seen the like you know cursor working in in the like the dot dot dots but but but they are not they don't have like a codebase integration right.
</details>

>> 他们有。

<details><summary>Original English</summary>
>> They do.
</details>

>> 好吧，我没用过那个功能。

<details><summary>Original English</summary>
>> Okay. I haven't used that.
</details>

>> 我之前只用它来做 OpenTable 预订之类的。

<details><summary>Original English</summary>
>> I've only been using for like open table reservations.
</details>

>> 没错。好的。

<details><summary>Original English</summary>
>> Exactly. Okay.
</details>

>> 我觉得这就是他们想要达到的目的。

<details><summary>Original English</summary>
>> Uh which I think that's the point of what they're trying to do.
</details>

>> 我明白了。是的，也就是说……

<details><summary>Original English</summary>
>> I see. Yeah. as in like
</details>

>> 他们试图表达的是：你可以把它当作消费级工具使用，但如果你善于使用它，这里有更强大的能力，因为它的底层实际上就是 Cursor。

<details><summary>Original English</summary>
>> they're trying to be like uh well you can use it for consumer stuff but here's the extra power if you know how to use it well uh because because it's actually cursor under hood
</details>

>> 我觉得这适用于所有的编程 agent，对吧？比如 Claude Code、Claude Design。人们在使用 Codex 时并不知道自己正在使用 Codex，对吧？弹出一个随机的代码解释器窗口，而你只是在问它一个问题，但在某种层面上，底层就是一个编程 agent，对吧？

<details><summary>Original English</summary>
>> I think this goes to all coding agents right like cloud code cloud design uh people using codecs not knowing they're using codecs right a random code interpreter window pops up and you're just asking jets a question at at some level there's coding agent under the hood right
</details>

>> 是的，我再给你举一个实际的例子。我在 Codex 内部运行我所有的 SEO 和 AEO，它有一个代码库，尽管传统的营销人员可能只是去查看 Ahrefs 之类的工具，但我写了所有这些脚本来完成各种复杂的操作。确实如此。

<details><summary>Original English</summary>
>> yeah so so I'll give you another sort of practical example Uh so I I run all my SEO and AEO inside of codeex and it has a codebase even though like a traditional marketer would just check a address or something because I write all these scripts for doing all the all sorts of crazy stuff. Sure
</details>

>> 而且我还需要存储数据，还需要可视化数据。很快你就会发现，只要你持续在做某件步骤很多或者数据量很大的事情，你就需要一个代码库。嗯，这个观点很有意思。

<details><summary>Original English</summary>
>> and and also I need to store data and also I need to vis visualize data and like pretty soon you go like as long as you're doing anything on a ongoing basis that has like maybe a lot of steps or a lot of data you need a code base. Hm. That is an interesting take.
</details>

>> 我认为模型也喜欢构建代码库。

<details><summary>Original English</summary>
>> I think models also like building code bases.
</details>

>> 不，但这可能只是暂时的现象。

<details><summary>Original English</summary>
>> No, but but that could be a temporary thing.
</details>

>> 我想也许我的重点更多在于界面，对吧？比如你会断言到这种地步吗：Grokbot 会提供一个让高级用户能够查看底层代码的地方？是这样，还是……

<details><summary>Original English</summary>
>> I guess maybe my my point is more around the interface, right? Like will are you going so like are you going to go so far to say that a grobot will have a place where like the power user will be able to see the code under the hood? Is that or is it
</details>

也许他们直接跳去用 Cursor 了？我想你表达的是这个意思吗？

<details><summary>Original English</summary>
maybe they just jump to cursor? I guess is is that what you're saying?
</details>

>> 确实如此。因为我觉得如果不是这样，那你基本上就是在蚕食 Cursor。如果推到极致，按你所说的 Grokbot 就是 Cursor，那么如果底层全都变成了……你就甚至不再需要 Cursor 了。

<details><summary>Original English</summary>
>> Well, exactly. Because I'm like otherwise then then you basically cannibalize cursor. Like if if in the limit what you're saying is Grockpot is the cursor then you don't even need like a cursor if all under the hood is just becoming
</details>

>> 这是同一个团队。所以他们现在并不在乎，但没错，全都变成 Grokbot 了。

<details><summary>Original English</summary>
>> it's the same team. So they right now they don't care but yeah it's all Grockpot.
</details>

>> 是的，是的，是的。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah.
</details>

>> 我认同这一点。我的意思是，我确实接受即便表面上看起来完全是非技术的用例，在底层也都是技术的，都可以通过代码来编写、设计和实现，这一点绝对没错。对。问题更多只是在于：对开发者来说，那是他们的唯一入口吗？

<details><summary>Original English</summary>
>> I I I buy that. I mean I do accept that even things that seem outwardly just like non-technical use cases under the hood are technical can be like written and and designed and implemented in code like that that much which is absolutely true. Right. The question is just more like is a developer is that their single point of entry?
</details>

>> 是的，

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 我觉得甚至都不用是开发者，对吧？比如想象一个做市场营销的普通人，在使用 Claude Code 或者直接在应用中使用 Claude，现在也是在一个他们永远不知道、永远不会触碰的代码库中工作，但是……

<details><summary>Original English</summary>
>> I think it's not even developer, right? Like you think of a regular person doing marketing that is using cloud code or just claude in the app now is working in a codebase that they would never know, never touch, but
</details>

>> 有一个代码库管理器。

<details><summary>Original English</summary>
>> there's a codebase manager.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我认为 Claude 标签页在后台 agent 方面是一个很好的例子。这是 Anthropic 非常重要的工作方式，他们做出来的。你应该去看看他们是怎么运作的。

<details><summary>Original English</summary>
>> I think cloud tag is a good one for uh background agents. It's a big way anthropic works and you know they make it. You should see how they work.
</details>

### AI 原生团队与 MCP

>> 是的，是的。做得很好。好吧，AI 原生团队。我们已经讨论了很多关于网关之类的话题。我们今天刚发布了一期关于路由的节目，还有 MCP 门户。我想说 MCP 门户是最不被……

<details><summary>Original English</summary>
>> Yeah. Yeah. Good job. Uh, okay. AI native team. Uh, we've talked a lot about these topics of like gateway. Uh, we just put a routing episode out today and MCP portal. I would say MCP portal is like the least
</details>

>> 看好 MCP 的。

<details><summary>Original English</summary>
>> bullish on MCPS.
</details>

>> 我看好 MCP。不存在看好看衰，它现在就是整个生态格局的一部分，对吧？

<details><summary>Original English</summary>
>> I'm bullish on MCP. There's not bullish or bearish. It's just is it just is a part of the landscape now, right?
</details>

>> 嗯，

<details><summary>Original English</summary>
>> Um,
</details>

这话挺有分量。之前有一整套“MCP 强势回归”、“MCP 已死”的说法。大家都喜欢走向极端……

<details><summary>Original English</summary>
that's a statement. There was a whole MCP is so back. MCP is dead. People like extreme
</details>

>> MCP 门户是一个未经证实的商业模式。我之前考虑过创办一个，我甚至就可能创立一个 MCP 门户的主题做过引导性提案，后来我就失去兴趣了。我对很多事情都会失去兴趣。但是，里面究竟有什么？好吧，我在这里想的是，如果这是偏向于……这一周的规划设计如果更多面向……

<details><summary>Original English</summary>
>> MCP portals is a unproven business. Uh I I thought about starting one. Uh I actually pitched a guiding topic on on potentially starting one and then I lost interest. I lose interest in a lot a lot of things. But I uh what's what's in there? Uh so okay so what I'm thinking here is if this is um if this is the week design uh more kind of geared toward
</details>

<!-- chunk 15/18 -->

### MCP 门户与网关的统一

把这个扩展开来，比如当采用某些原则时会发生什么——其中很多都来自于我与那些在各自公司领导团队、原生团队的人的交谈。所以在这里，我认为某种 MCP 门户只有在达到一定规模时才会真正变得有意义，在那个规模下，你实际上必须拥有一个单一入口点来进行治理、安全、审计、成本优化等操作。我很想听听你对未来的看法，或者未来是否可能根本不存在这种东西。但对我来说，如果你相信像 OpenRouter 这样的东西，或者某个类似单一入口点的地方，让许多事情在此发生、连接并得到有效治理，我觉得这种东西在未来也有存在的空间。

<details><summary>Original English</summary>
scaling this out to like what happens when you take some principles and a lot of this was informed by like conversations I had with folks that were you know leading and native teams and teams at uh at respective companies and so here uh I think that something MCP portal really only becomes interesting once you're at a certain scale where you effectively have to have a single point of entry to do things like governance security auditing cost optimization I'd be curious to hear what you see as the future or maybe lack thereof. But it to me is if you believe in like an open router or you know some place like a single point of entry for for many things to happen and connect to and be effectively you know governed. I feel like there's a world where this also continues to exist.
</details>

>> 对。我对此唯一的微调是：它会融入到 LLM 网关中。

<details><summary>Original English</summary>
>> Yeah. My my only tweak on this is that this folds into the LM gateway.
</details>

>> 所以它们是完全相同的平台。

<details><summary>Original English</summary>
>> So they are the exact same platform
</details>

>> 这一点我认同。这一点我认同。我可以接受，这个实际上你我能达成共识。是的。

<details><summary>Original English</summary>
>> that I will give you. That I will give you. I can I can accept that that actually you can can agree with. Yeah.
</details>

顺便说一句，它还会融入到另一件事中，我之前说的 authz——也就是权限管理和所有这些东西——以及计费。所以，推向极致的话，所有的基础设施最终都会收敛到完全相同的问题上：中间有一个盒子，然后两边各有一个盒子。你懂的，“万能上帝盒子”（God Box）会解决一切，对吧？只有当你理解了上帝盒子的职责时，这才是真的。因此，把 MCP 门户和网关分开，意味着你还没有完全接受它们处于同一个问题层级。在非常类似的方式下，我也发现人们不理解数据库查询也有很多相似之处，他们会把过滤、排序或者通用推荐割裂开来，而实际上它们是同一个问题。

<details><summary>Original English</summary>
Uh and and then then by the way it also folds into the other thing of um what did I say was was uh offz you know permissioning and all these things and billing so like all to the limit all infra converges to the same exact problems where they have the box in the middle and then you have the box in two sides uh you know god box will solve everything right and it's true only if you take uh if you understand the job of the god box and so separating mcp portals and gateways means you don't fully accept that they are uh you know the the same layer of problem and in a very similar way I also find that people don't understand database querying uh to have a lot of the similar things where they will separate filtering from ranking from uh or or just like general recommendation if they're the same problem.
</details>

>> 于是就像……因为当你把所有这些东西结合在同一层时，你就可以通过有用的方式让它们产生交叉依赖；如果它们处于不同的层级，就无法做到这一点。

<details><summary>Original English</summary>
>> Uh and so like then you just com because like when you take all these things you combine them in the same layer then you can sort of cross depend on on things in useful ways. If there are different layers then they cannot.
</details>

>> 对，我其实并不反对这一点。我认为……可能在教学意义上，把它们拆成独立术语与合为一个是有区别的。我认为底层架构绝对就是这种“上帝盒子”：一端有东西输入，而在上帝盒子的另一端，存在着一堆第三方的、内部的、第一方的各种东西。所以是的，我其实同意这一点。我发过一条……我发过一条挺辛辣的推文。天啊，那条上帝盒子的推文在哪儿？哦对，这就是 $M \times N$ 到 $M + N$ 架构。所以任何从事基础设施工作的人都需要明白——恭喜你，你现在拥有了一份基础设施领域的工作，或者如果你想成为一名基础设施工程师，你就需要明白：你的整份工作就是打造上帝盒子，然后把它们拆散。

<details><summary>Original English</summary>
>> Uh yeah I I I actually will not disagree with this. I think um maybe the yeah so slightly pedagogical I think that the this breaking up of like separate terms versus one. I think I it is absolutely correct that the underlying architecture is the the god box where one thing goes in and there's a bunch of other stuff that is some third party some internal some first party that all kind of exists uh on the other side of the god box. So yes I agree with this actually. I I have a I have a I have a spicy uh spicy tweet. I Oh god, where where is the godbox tweet? Oh yeah. So this is the M MX to M plus architecture. Uh so anyone working in infra needs to understand uh congratulations, you now have a job in infrastructure or you want to be an infra engineer, you need to understand that your entire job is making God boxes and then taking them apart.
</details>

所以你的问题要么是没有一个足够好的上帝盒子，要么是你不喜欢别人的上帝盒子，所以现在你必须把它拆掉，自己做一个。

<details><summary>Original English</summary>
So either your problem is either you don't have enough you don't have a good gut box or your problem is someone else's god box you don't like so now you have to take it apart and make your own.
</details>

>> 太好笑了。非常有意思，我喜欢这个说法。太搞笑了。直到宇宙热寂为止。哇，真有意思。

<details><summary>Original English</summary>
>> That's funny. That's very funny. I like that. That's very funny. Until the heat death of the universe. Wow. That's funny.
</details>

### 捆绑与解绑的循环

>> 这其实是对“做软件只有两种方式：要么捆绑，要么解绑”的重新表述。但问题是，你到底在捆绑什么？但愿捆绑的是本就该在一起的东西。然后随着时间的推移，人们对于什么应该放在一起、什么不该放在一起的看法可能会发生改变。

<details><summary>Original English</summary>
>> Which which is a this is a a restatement of like there's only two ways to make software which is you bundle them, you unbundle them. But like what are you bundling? It is the things that go together hopefully. And then like maybe over time people's opinions shift as what what goes together what should not go together.
</details>

>> 没错。没错。

<details><summary>Original English</summary>
>> Right. Right.
</details>

>> 所以就有了整件事，比如也许 Monaco 应该更偏向单点解决方案，也许 Monaco 应该包揽一切，对吧。这里就存在一个问题：在某种程度上，你是在为你所服务的初创公司客群进行捆绑；在某种程度上，你是在对 Salesforce 进行解绑，因为 Salesforce 是那样，而这正是你从 Salesforce 手中赢得市场份额的方式——你从 Salesforce 中解绑出来。

<details><summary>Original English</summary>
>> So so like you know there there is that that the whole thing you know maybe uh Monaco should be a more of a point solution. Maybe Monaco should own everything. Right. And like there's the question of like in some ways you're bundling for uh the kind of startup segment that you serve. In some ways you're unbundling from Salesforce because Salesforce that and then that's how you win market share from Salesforce. You unbundle from Salesforce.
</details>

嗯，这很有意思。是的，这是一个更宽泛的论述。我是说，把它广泛联系到所有垂直 AI，或者现在的捆绑与解绑——就像整个 Craigslist 和 Airbnb，还有 Tinder 之类的，那些都是独立拆分出来的……

<details><summary>Original English</summary>
M hm that's interesting. Yeah, that's that's an even broader statement. I mean connecting it to broadly all of vertical AI or uh and now like bundling unbundling I mean that's like the whole like Craigslist and Airbnb you know the Tinder and all those are separate
</details>

>> Tinder。

<details><summary>Original English</summary>
>> Tinder
</details>

>> 但你知道，基本上就像是个人分类广告（personals）。

<details><summary>Original English</summary>
>> but you know like personals basically
</details>

>> 从来没这么想过，但确实是。所以我们今天刚刚发布了关于 OpenRouter 的播客，对吧？

<details><summary>Original English</summary>
>> never thought about thought about it that way but yes uh you know one one of those things so we just shipped the open router pod today right
</details>

>> OpenRouter 取得了巨大的成功。很多人都尝试过构建网关，但没有一个人能取得 OpenRouter 这样的成功；OpenRouter 只做网关。所以这就是一个典型的例子：他们不同意我的看法，不认为路由层也应该去做运维……

<details><summary>Original English</summary>
>> and um open router huge success lots of people tried to build gateways none of them had success with open router open router only builds gateways. So there's an example of like this. they disagree with me that the the the router layer should also do ops
</details>

>> 因为 Arize 在做运维和可观测性等等，而像 MCP 网关，他们并没有做。

<details><summary>Original English</summary>
>> because Arise is doing ops um and observability and and what have you and and they and like the MCP gateway they don't have that
</details>

>> 而且他们只处理模型路由。

<details><summary>Original English</summary>
>> and they they just they only handle model routing
</details>

>> 所以我很喜欢被这样打脸，因为他们的态度是：我们就是单点解决方案，我们就把这一件事做到极致，这就是我们的工程重心，这很好；同时这也是市场营销的重心，这很棒。

<details><summary>Original English</summary>
>> and so like I I like I am I love being wrong like that because they're like we are the point solution and we only do this one thing really really well and uh that's our that's our engineering focus which is good. It's also the marketing focus which is nice.
</details>

### 组织边界与平台工程的角色

>> 嗯。我认为你所描述的那种包揽一切的一站式服务，在理念上是合理的；但我认为在实践中最终发生的情况（部分原因可能也是市场营销），特别是当你观察企业级市场时，这大体上都属于基础设施、大体上属于平台，但技术栈的不同部分是由不同团队负责的。我认为在企业规模下进行这种整合，如果要说把 MCP 门户和网关合二为一，必须有人站出来说“现在这两个东西你都要通过同一个端点来调用”，而从根本上说，要让所有人都赞同这一点是非常困难的。所以这通常更像是一个政治问题，甚至是一个人的问题，而不是纯粹从软件设计角度来看——尽管从软件设计角度看这完全说得通。

<details><summary>Original English</summary>
>> Mhm. I I think the um this becomes I think that the what you've described of like the one one-stop shop for all the things is ideologically what makes sense but I think what ends up happening in practice and you know part of it is probably also marketing is that especially when you look at the enterprise is like this is broadly under infra like broadly under under platform but then there's separate teams owning different parts of the stack and I think part of that consolidation at the at the scale of an enterprise if we're going to say MCP portal and gateway someone has to come together and say like now we're there's a single end point that you're hitting both of these things and that fundamentally is like a hard thing to get everyone on board with. Um, so it often times like more like political and and even like people problem rather than like a from a software pure software design perspective this makes a ton of sense.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但现实并非如此，对吧？软件系统有时受到人的问题的瓶颈限制，甚于纯粹的软件问题。

<details><summary>Original English</summary>
>> But that's not it right like software systems sometimes are bottled like by people problems more than than pure software.
</details>

>> 我对此的定式通常是：你懂的，你交付的产品往往映射了你的组织架构——我忘了这个原理叫什么了……康威定律，你交付的是你的组织架构，对吧？

<details><summary>Original English</summary>
>> The way my my framing of this is typically you know how you ship your org chart is well I forget what the the name of this principle is. uh you need Conway's law, you ship your orchart, right?
</details>

>> 你购买的东西也反映了你的组织架构。当你创办一家初创公司或打造一个工具时，你在公司里到底是在为谁服务、把谁当成最好的朋友？

<details><summary>Original English</summary>
>> Uh you buy your org chart like like like who like when you start a startup or you you make a tool, who in the company is your are you best friends for?
</details>

>> 如果它是为了服务所有人，那它就谁都服务不好。

<details><summary>Original English</summary>
>> And if it's for everyone, it's for no one.
</details>

>> 嗯，这很有意思。确实很有意思。

<details><summary>Original English</summary>
>> H that's interesting. That is interesting.
</details>

>> 所以，Latent Space 和 AIE 有一个自觉的考量：既然有这样一类软件工程师，他们非常、非常、非常在乎 AI，并打算以此作为全职工作，那我们就专门为他们服务。

<details><summary>Original English</summary>
>> So so like a conscious part of uh latent space and and AIE is like okay there's this category of software engineer that really really really cares a lot about AI. Is it going to make it their day job? Let's only make it for them.
</details>

>> 对，对，对，对，对。不是工程上的大杂烩捆绑，绝不做给所有人用的开发者工具。

<details><summary>Original English</summary>
>> Right. Right. Right. Right. Right. Not not a bundling of engineering. Never going to be the dev everyone.
</details>

>> 是的。你看，我们聊数据库，聊安全，但都是从 AI 的视角来聊。

<details><summary>Original English</summary>
>> Yeah. Look, we talk about databases, talk about security, but like there's an there's an AI angle to it.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 对，走着瞧吧。这说得通。

<details><summary>Original English</summary>
>> Yeah. We'll see. That makes sense.
</details>

>> 另外我也想顺便提一点，跟这个观点有关：我认为未来有一个角色正变得越来越重要——平台工程师。我认为这是一个非常关键的岗位。

<details><summary>Original English</summary>
>> Uh, one thing I'll just like shout out as well related to the to the point is uh I think role of the future that is increasingly important. U platform engineer. I think this is like a huge one,
</details>

>> 没错。好吧，说点更多背景……在 Temporal 之前，也就是在这一切之前我的上一份工作，我本来想……是的，如果我们想主导平台工程，如果我当时没创业，我就会去做平台工程师。因为那个角色决定了所有这些关乎关键任务（mission-critical）的东西，然后应用层的年轻人们就可以在我们搭建的平台上为所欲为。但你懂的，真正厉害的大佬们都在做平台。

<details><summary>Original English</summary>
>> you know. Okay. more lore uh temporal pre my job before all this I would have uh yeah so we wanted to own platform engineer if I hadn't started yeah I would have done platform engineer uh because that is the role that decide that decides all of this mission critical stuff and then the kids over in applications can do whatever they want on top of our platform but but you know the big boys do platform
</details>

>> 是的，我认为在现代，他们掌控云端、掌控开发者体验（DevX）、掌控安全运维，所以我觉得它是涵盖所有这些东西的。

<details><summary>Original English</summary>
>> yeah and I think in the modern day they own they own cloud they own devx they own security ops so I think it's it's all the things
</details>

>> 比如所有那些真正可能让公司遭受惨重损失、或者决定公司成败的关键环节，都是平台组的人在把关；然后产品组的人就去调调 CSS。

<details><summary>Original English</summary>
>> like everything where you can actually like lose lose the company or like it would make or break like yeah platform guys and then product guys can do you know adjust the CSS that
</details>

>> 你这是在挑起纷争了。我的意思是，虽然我不是调 CSS 的人，但我尊重每一个人。

<details><summary>Original English</summary>
>> that's you're starting to fight here I mean I'm not the CSS adjuster but but I I I appreciate everyone
</details>

<!-- chunk 16/18 -->

### 软件工厂与人机在环

>> 我是说现在挺有意思的。未来会是怎样？我觉得大家可以调整所有的东西，呃……

<details><summary>Original English</summary>

>> I mean it's a fun time what's what's the future I feel like all the guys can adjust all the things um
</details>

>> 对，对对对。所以这里有几个方面。好，所以这里会承接上一周的一些内容，比如编程智能体、大团队、其中的一些概念，但接着我们会聊到软件工厂。呃，我希望大家真正开始思考这样一个世界：这台机器去建造那台机器，以及人在其中是否还处于回路之中、处于哪个位置。你知道，今天我认为答案是某种意图与某种审查的结合，或者可能是这样的环节——意图是你定义规格说明以及需要构建什么，而审查则是你在对系统进行一定程度的自主检查。当然这也会……我认为在意图这一块之前，那个瓶颈就会被打破。但就目前而言，我认为在一个全自动化系统中，这两个就是卡点。呃，所以是的，我只是想让大家接触到这一点，实际上我们的开源合作伙伴之一 Warp，他们正在做这样一件事，作为他们对开源项目贡献的一部分：他们基本上要做一个运行工厂的 Warp 版本，学生们就负责构建工厂、为工厂做贡献并让它保持运转——

<details><summary>Original English</summary>

>> yeah yeah yeah so there's there's a few aspects here okay so so there's a little bit of spillover from from the previous week so yeah coding agents big teams some of the concepts but then you We'll touch on the software factory. Uh I want people to to really start thinking about this this world of of this machine that builds the machine and where if at all are people still in the loop there. You know today I think the answer is some some combination of intent and kind of review or maybe the places like so intent where you're defining the specs and what needs to be built and and review where you're you know doing some amount of your own checking of the system. And of course this also this is I think that bottleneck is going to be loosened up before even the intent piece does. But for now those are the two choke points I think in in a fully automated system. Um so yeah I just want to give people exposure that for one of the OSS partners actually uh warp they're doing this thing as part of their contribution to the OSS program where they're going to essentially make a version of warp that is running the factory and students will just be like building the factory contributing to the factory and keep it running
</details>

>> 就像“来我们的工厂工作”。

<details><summary>Original English</summary>

>> like work in our factory.
</details>

>> “来我们的工厂工作”，完全正确。然后他们会在那里发现有趣的东西并带回来。

<details><summary>Original English</summary>

>> Work in our factory. Exactly. And then they're going to find things that are interesting there and pull it back.
</details>

>> 这就是那种……我不确定，显然 Factory 本身对这个非常非常热衷。

<details><summary>Original English</summary>

>> This is one of those things where like I'm not sure obviously factory itself is very very keen on this.
</details>

>> 我感觉每个人都想打造自己的。

<details><summary>Original English</summary>

>> I feel like everyone wants to build their own.
</details>

>> 是的，我……我认为那确实是一个好问题，而且我认为他们当然有权尝试销售他们所做的产品。我认为这是一个很难全盘掌控的系统。这包含很多东西，确实非常多。

<details><summary>Original English</summary>

>> Yeah, I I think that's that is it is a good question and I think they're, you know, of course entitled to kind of try and sell the products they do. I think it's a hard system to own its entirety. It's a it's a lot. It's it's a lot.
</details>

>> 请帮我决定一切吧。

<details><summary>Original English</summary>

>> Decide everything for me, please.
</details>

>> 是的，内容很多。我正在努力去……你知道，我还没有深入去理解他们在这里的 GTM 策略，但我猜你必须采取零敲碎打的方式，对吧？你必须像这样：“嘿，我们首先是你的编程智能体”，哦，然后还有……你基本上采取先占位后扩张（land and expand）的方式，对吧？我的意思是，我们讨论过这种捆绑与拆分的情况，你一开始不可能说“这是你的整座工厂”，你绝对不可能让像福特这样的客户接受那种方案，你懂我意思吧？直接跑过去把整个东西甩在他们桌上。呃，至少我是这么认为的：你首先成为他们首选的编程智能体，你为他们构建一些后台智能体，你接管他们的一部分安全或运维（SRE/security）环节，然后你再说“好吧，现在如果你们把一切都定义在代码中，或者类似配置之类的东西，我们就可以把它们全部串联起来了”。OpenAI 有一篇关于这个的很有意思的博客文章，我们邀请了——

<details><summary>Original English</summary>

>> Yeah, it is a lot. And I'm I'm trying to you know I haven't like gone too deep in understanding like the how they approach their GTM here but I suspect you would have to do a peace meal right you would have to be like hey we first your coding agent oh then also like you basically land and expand right I mean we talk about this bundling on bundling piece you don't start by saying here's your whole factory there's no way you could get like a Ford on board with that you know what I mean where you're going to go on and just plop the whole thing on on their desk um that's at least how I would think about it is you first be their their coding agent of choice you you you build up some background agent for them you you own some of their S sur pieces and then you're like well now we can just weave it all together if you define everything in code or something like that like you know configs. There was a fun blog post on this from OpenAI. We had
</details>

>> 我们的好友 Ryan。

<details><summary>Original English</summary>

>> our buddy Ryan.
</details>

>> 我们请 Ryan 上了播客。基本上，他们花了五个月时间制作了一个内部工具，手动编写的代码为零行。他们大致梳理了整个过程。这被称为“利用工程”（harness engineering）。所以，你可以去学 harness engineering。但是，你知道，那里的经验是起初会有个低谷期或者比较慢，然后你把工作卸载出去，并且有同行评审。这是……目前来看这是二月份的文章了，但这展现了软件工厂的一种愿景，对吧？就像你全力投入，呃，让智能体完全编写所有内容，以及如何把这件事做好。

<details><summary>Original English</summary>

>> We had Ryan on the podcast. Basically, they spent five months making an internal tool with zero lines of manually written code. They kind of walk through one. It's called harness engineering. So, you can learn harness engineering. But, you know, the learnings of there was kind of a slump or slower at first and then you offload and you had peer review. It's at this point it's from February but it's you know a vision of a software factory right like you are full sending um letting agents fully write everything and how to do that well
</details>

>> 对，完全没错。是的，我是说某种版本的形态肯定会出现。呃，就 SP 的观点而言，我确实对这里的销售环节感到好奇，比如这背后的实际商业模式，那是个有趣的问题。但从原则的角度来看，我认为这是……这是未来的一种可能版本。除此之外，我认为还会涉及到并探讨诸如：好吧，在未来成为一名开发者意味着什么，对吧？我们……人们在谈论品味，人们在谈论，比如对系统和架构的理解，是的，比如软件品味。我想在这里更深入地探讨一下，或许至少开始为围绕这个问题给出一些答案。

<details><summary>Original English</summary>

>> yeah absolutely yeah I mean some version of this is going to exist uh to SP's point I do wonder about the the sales piece here like the actual business of this that's an interesting question but from a principal perspective I think this is the the this is one version of the future and then beyond that I think there's going to be some amount of dabbling into and speaking about like okay what does it mean to yeah what does it mean to be a developer in in the future right like are we people talk about taste people talk about like you know understanding of systems and architecture and yeah like software taste I want to like go a little bit deeper here on maybe starting to like at least put a some answers to the question around this
</details>

>> 是的，呃，所以这就是你对 AI 软件工程下一步走向的回答。

<details><summary>Original English</summary>

>> yeah uh so this is your answer to where where AI software engineering goes next
</details>

### 开发者的角色演变与抽象层级

>> 是的，所以我是说，工厂是属于战术层面的东西，但我认为在此之外，还有一个围绕角色的问题，对吧？比如这个角色会演变成什么样？呃，如果工厂全速运转，做着它该做的事，传送带源源不断地产出代码，那我们在这一切之中做什么呢？对吧？而且我认为我们……我认为几周前你和我曾跟 Jerry 一起吃晚饭时讨论过这个问题，当时还有 Dex 和 Jerry，讨论的是围绕工厂的话题。但是的，我……我认为当时讨论的内容中有一部分是我非常赞同的，那就是抽象层级不断提高，然后不知何故依然需要有人在——即使是一家公司的 CEO，也必须对各个不同组成部分有足够的全局把控和理解，才能对方向做出判断，对吧？才能纠正航向，才能设定指标之类的事情。我认为有一个可以类推的版本，有一个类比版本可以对应到监管技术的人。我们称之为智能体管理者，我们用不同的术语来称呼，它们都很像行业黑话。但是，呃，在某种程度上，这是一个理解产品需求、约束条件、技术限制，能够把所有这些串联起来，并且知道如何拍板判定的人。

<details><summary>Original English</summary>

>> yeah so I mean the factory is is like the tactical but I think beyond that there's like a there's a question around like the role right? Like what does the role evolve into? Um if if the factory is is running and you know full steam ahead doing its thing, the conveyor belt is is turnurning out code. What what do we do in all this? Right? And I think we I think you and I we had this discussion with Jerry at the dinner once upon a time a few weeks back with Dex and Jerry around around the factory. But yeah, I I I think that there was this part of at least the discussion points there which I I'm pretty much on board with is like increasing levels of abstraction and then somehow there's someone still even a CEO of a company has to have enough oversight understanding of like different constituent parts to be able to make a judgment on direction right to be able to course correct to be able to set metrics and things of of that nature. I think there's a version that translates of that. There's a there's a version that of that analogy that translates to like someone who oversees the technical. We call it a manager of agents. We call it a you know different terms. They're all buzz buzzwordy. But um in some some respect someone who understands product requirements, constraints, technical constraints kind of loops through all of those and and and knows how to adjudicate.
</details>

>> 是的。呃，我想说的是，呃，就在你前面坐在这把椅子上的，我们刚刚迎来了 Anthropic 的平台产品主管和工程主管。呃，我当时问，你们的工作什么时候会合并？他们回答说“还没呢”，你知道吧？呃，所以如果 Anthropic 都还没有做到那一步，你就不应该觉得它已经迫在眉睫了。

<details><summary>Original English</summary>

>> Yeah. Um I I will say that uh in the chair before you, we just had uh anthropics uh head of product and head of engineering uh for the the platform. Uh, and I was like, when are when are your jobs going to combine? And they're like, not yet, you know? Uh, and so if Entropic is not doing not there yet, you should not feel like it's it's imminent.
</details>

>> 挺好，挺好，挺好。呃，他们有说还要多久吗，还是就只说了“还没呢”？

<details><summary>Original English</summary>

>> Good, good, good. Um, do they say how long or are they just not yet?
</details>

>> “还没呢”，但谁知道呢？而且我……肯定有很多人觉得“好吧，是的，我们在……我在做她的工作，她在做我的工作”。就像这样。

<details><summary>Original English</summary>

>> Not yet, but who knows? And I I definitely there was definitely a lot of like, okay, yeah, we're I'm doing her job, she's doing my job. Like, yeah.
</details>

>> 我觉得这对学生来说也是一个有趣的视角，对吧？你说过有很多大二的本科生，比如——

<details><summary>Original English</summary>

>> I think it's also interesting perspective for students, right? you said there's a lot of sophomore undergrads like
</details>

>> 你还有两三年的时间来规划你想做什么。呃——

<details><summary>Original English</summary>

>> you got two three years to go to plan out what you want to be doing. Um
</details>

>> 从那个角度来看有不同的看法，对吧？你又不是直接进入工业界。

<details><summary>Original English</summary>

>> there's different ways to look at it from that, right? You're not straight in industry.
</details>

### 从提示词到系统的自底向上构建与评价指标

>> 我在意的、呃，我思考很多的点是，这场讨论中更能引起我共鸣的一部分是回路那些内容，比如，呃，好吧，你开始写提示词，现在你不再写提示词了。你写的是用来写提示词的提示词。没准就是这样。

<details><summary>Original English</summary>

>> The thing that I care uh I'm thinking a lot about is well so one part of this discussion that resonates more with me is the loop uh stuff where like um okay you you started writing prompts now you no longer write prompts. You write prompts that write prompts. That's right.
</details>

>> 没错。然后你就一直往上走。我认为对我来说，这种递归同心圆的本质，既向外延伸，但也向内深入——

<details><summary>Original English</summary>

>> Right. And then then you just keep going up. And I I think to me the sort of recursive concentric circles nature going outward but also going inward
</details>

>> 构成了打造工厂的过程。我认为你是自底向上构建出工厂，而不是自顶向下构建，但我认为很多人最终会开始自顶向下构建，比如你从最高层面出发，比如我的目标是什么，然后你再把系统摸索出来。呃，目前那样做会产生大量的废料（slop），你不应该那么做，但总有一天你会这样做的。

<details><summary>Original English</summary>

>> is something that builds the factory. I think you build up to the factory not build down but I think a lot of people will eventually start building down like you start from the top level like what is my goal and then you figure out the systems. Um that currently creates a ton of slop and you should not do that but someday you will.
</details>

>> 嗯。

<details><summary>Original English</summary>

>> Mhm.
</details>

>> 嗯。

<details><summary>Original English</summary>

>> Mhm.
</details>

>> 是的。对。

<details><summary>Original English</summary>

>> Yeah. Yeah.
</details>

>> 所以是的。所以，所以……所以你知道，我想向你提出的问题就是，呃，我们……我们是否……人们存在是为了解决的最主要问题是什么？比如那是你的事情，对吧？所以在……比方说今天的工程师，呃，衡量你的标准是你的 PR 合并率、PR 贡献率——

<details><summary>Original English</summary>

>> So yeah. So, so in so instead of so you know that would be my question to to prompt you um is uh do we do we uh what is the sort of prime question that people exist to solve like that is your that is your thing right so in in let's let's say an engineer today um you are measured by your PR merge rate PR contribution rate
</details>

>> 嗯，两年后那就会变得很荒谬了。好吧，那你的核心要务是什么？

<details><summary>Original English</summary>

>> well two years from now that's going to be ridiculous okay well what's your main thing
</details>

>> 对，我不知道。

<details><summary>Original English</summary>

>> right I don't know.
</details>

>> 是的。

<details><summary>Original English</summary>

>> Yeah,
</details>

>> 赚钱。

<details><summary>Original English</summary>

>> money.
</details>

>> 大家总是太快把话题引向钱上。它是介于赚钱和——

<details><summary>Original English</summary>

>> People always go to money too quickly. It's something in between money and
</details>

>> 对，PR 之间，

<details><summary>Original English</summary>

>> right PRs,
</details>

>> 客户满意度，你做的功能带来的 CSAT 分数。

<details><summary>Original English</summary>

>> customer satisfaction, seesat scores from your features.
</details>

>> 连那个都像是一个产品决策，并不真正算是一个代码决策，对吧？就像……我不知道，就像——

<details><summary>Original English</summary>

>> That even that's like a product decision, not really a code decision, right? Like like I don't know like
</details>

>> 但……但如果工程角色正在演变成为类似于 PM 工程师的混合体，也就是产品工程师，你知道，混合型角色，那么他们……那我认为了，你知道，这就是关于以下问题的一个答案：

<details><summary>Original English</summary>

>> but but if the but if the engineering is evolving into like a more of a PM engineer like product engineers, you know, hybrid, then they then I think that's you know that's one answer the question of like
</details>

<!-- chunk 17/18 -->

### 角色演进与学生毕业项目

这个角色会演变成什么样？我认为不言而喻的是，如今我会建议学生花更多时间去思考整体系统，而不仅仅是你所在的工程难题的单一局部，还要考虑它如何与整体关联。在实践中也确实是这样发生的：比如学生的毕业设计项目，我鼓励他们走出去。事实上，我给他们作为期末项目灵感种子的，就是 YC 的创业征集令（Request for Startups）。我差不多就是在跟他们说：“去创办一家公司吧，你懂我意思吧，去做出点有意思的东西来。”

<details><summary>Original English</summary>
what does the role evolve into? I think it it goes without to say that um I would today recommend to students spend more time thinking about holistic systems not just your like single part of the the engineering puzzle but how that ties in with and you know and this is like in practice ends up happening like students for their capstone projects I encourage them to go out and like in fact what I give them as the seed of ideas for final projects is like the the YC request for startups. I'm almost like go build a company like you know what I mean like go go build something interesting.
</details>

>> 去年大家都做了些什么？

<details><summary>Original English</summary>
>> What did people build last year?
</details>

额，我是说，各种各样的东西。比如有人来自电子工程系，在工程学院学电子工程，他们做了一个类似于转换器的东西，用于解析在 C 语言中带有内存地址的用户手册，然后将其转换为他们可以解释甚至可视化的代码。所以都是针对他们特定用例的东西。还有一位是设计师，现在其实在 Vercel 工作，她的项目就像是：“给我的设计笔记本拍张照，根据我拍的照片给我生成一个应用。”对吧。所以真的就是，在她的演示中，她拍了一张自己随手画的草图，然后就得到了一个完整的 Vercel 应用。正因如此，她很可能因此在 Vercel 拿到了一份工作，做着某种类似方向的事情。

<details><summary>Original English</summary>
Uh I mean a variety of things like someone was like um someone came in the E department uh was in the E school and E was studying E and they were like they built effectively a translator for like parsing of u like manuals to that have like um like memory addresses in in C and then converting that into like uh like code that they could then like interpret and even like visualize. So so stuff like specific to their their use case. someone who was like a designer and is now actually at Versel and she like had you know like take a picture of my like design notebook and generate me an app based on what I take a picture of. Right. So literally she was like for her demo I was like here you go snaps a picture of like some random like scribbles that she was doing and she got a fully fleshed out Versell app and from that and I think because of that probably got a job at Versell doing that doing doing some version of this.
</details>

>> 噢，很棒。

<details><summary>Original English</summary>
>> Oh nice.
</details>

>> 那确实要求很高，Vercel 在设计工程师方面非常出名。

<details><summary>Original English</summary>
>> Um that's a high bar actually Versell uh very known for their design engineers.
</details>

>> 是的。是的。我记得她现在好像在做 Eve。啊，不是你们那里的 Eve。

<details><summary>Original English</summary>
>> Yeah. Yeah. And I think she's now working on Eve from I remember. Ah, no Eve in your
</details>

>> EVE。Eve 是一个开源软件，或者说是开源合作伙伴。我是说，他们与我们合作的方式之一就是让学生用 Eve 进行构建。是的。

<details><summary>Original English</summary>
>> EVE. Eve is an OSS or like OSS partner. I mean like like they one of the the ways is partnering with us is that they are having students build with Eve. Yeah.
</details>

>> 是的。这就是元测试框架（meta-harnesses）的概念，对吧？测试框架的测试框架。你总能再深入一层。但我确实觉得，至少对我来说，这在逻辑上是说得通的，就像模型路由器封装模型 API 一样。如果你要在它们之间切换，你也需要封装测试框架。

<details><summary>Original English</summary>
>> Yeah. So the this is the concept of meta harnesses, right? Uh harnesses of harnesses. Uh you can always go one level deeper. Um but I I do think like it makes sense at least for me uh in the same way that model routers wrap model APIs. You you need to wrap harnesses as well if you're going to between them.
</details>

### 前沿探索与落地现实

>> 同意。同意。我认为在某种程度上，学生也应该保持脚踏实地，意识到前沿领域正在发生很多事情，但也有很多公司仍处于在生产环境中使用单一调用进行摸索、甚至还没怎么尝试过的阶段。有很多这样的情况。所以它仍需要时间去发展成熟。不过我觉得你关于品味的观点很好。保持品味，多尝试各种东西；无论每家公司是否都有自己版本的软件工厂，还是你在构建工具帮助公司实现它，紧跟前沿，实际去使用这些工具，去摆弄它们，你在这个过程中就会逐渐搞明白，你懂吧？

<details><summary>Original English</summary>
>> Agree. Agree. I think at some level students should also stay grounded in like there's a lot of stuff happening at the edge. There's also a lot of companies that are still like single call in production playing around haven't tried it. Um you know there there is a lot of that. So there's there's still time for it to work. But I think your point on taste is good. have taste, try stuff like uh whether each company has their own version of a software factory, uh you're building tools to help companies do it, like staying on top of it, actually using the tools, playing with it, like you'll you'll figure it out along the way, you know?
</details>

>> 是的。我百分之百同意这些。我是说，首先正如你所指出的，确实有很多公司仍停留在写 prompt 调用 ChatGPT 或者某种 ChatGPT 版本的阶段，也许他们刚刚拿到了 Cursor 许可证，才刚刚开始让员工上手使用？这比我们这里（硅谷）想象的要普遍得多。我可以百分之百确信地说这一点。但确实，我认为对于学生来说，接触到这些——在某种程度上，他们了解这些并且处于前沿的事实，最终将使他们进入那些在前沿技术方面可能还不够成熟的地方时，能够成为更有趣、更有价值的贡献者。

<details><summary>Original English</summary>
>> Yeah. And I think the the 100% agree with all that. I I mean, first to your point that are a lot of companies still in the prompt chatgbt or some version of, you know, chat GBT maybe do they just got a cursor license and are just now getting people on boarded? um that is way more true than we believe certainly here in the valley. Um that is I can I can say 100% confidence. Um but yes, I think for the students being exposed to this is just at a certain point this the fact that they know this and are on the edge is what will eventually allow them to also be some of the more interesting and more valuable contributors when they go to maybe places where that maybe aren't up to snuff in terms of being on the frontier.
</details>

### “精神错乱”阶段与技术认知演进

>> 是的。这类关于演进历程的讨论……

<details><summary>Original English</summary>
>> Yeah. uh what one of the this this kind of progression type talk
</details>

>> 大约一年前的，依然非常有影响力，Steve Yegge……

<details><summary>Original English</summary>
>> still very influential about a year old Steve Yaggi
</details>

>> 谈到了“精神错乱”（psychosis）的各个层级。他现在一路走到了第 10 级，已经放弃并搬到了一个农场，不过……是的，就像你想……抱歉，我在开他玩笑。他做了 Gas Town。

<details><summary>Original English</summary>
>> talking about the the levels of psychosis uh he's all the way through level 10 now um where he's he's given up and he's moved to a farm but uh yeah like you want sorry I'm making fun of him uh he built Gas Town
</details>

>> 是的，我记得。

<details><summary>Original English</summary>
>> yeah I remember
</details>

>> 搞了这一切，又搬到了 Gas City，现在他把那座城市烧了，说：“我要去开发我的游戏了，不再搞 Gas Town 了。”我觉得……我是说，我记得今年早些时候在工程师展会上和他聊过，他当时不就是那种想法吗——在 Gas Town 唯一有用的产出就是 Gas Town 本身。

<details><summary>Original English</summary>
>> all these things moved to Gas City now he's burned down the city and said I'm building my game and no more Gas Town I thought that I mean I I remember talking to him at at the engineer fair uh earlier this year and uh wasn't he his whole like thing like the only useful thing that was built at Gas Town was Gastown,
</details>

>> 对吧？那是极其彻底的失败。极其惨烈。

<details><summary>Original English</summary>
>> right? That that's a horrible failure. Horrible.
</details>

>> 完全如此。完全如此。

<details><summary>Original English</summary>
>> Totally. Totally.
</details>

>> 所以，人们应该意识到“精神错乱”是真实存在的。如果你不把交付真实产品作为对自己的要求，你不过是在拿着大语言模型瞎胡闹。

<details><summary>Original English</summary>
>> Um and and so like people should be aware that like psychosis is real and if you're not holding yourself accountable to delivering real products, you're just screwing wrong with LMS.
</details>

>> 是的。这可能相关，但我不知道……我是说我也玩过一点 Gas Town，非常复杂的系统，可能有点超前于时代了。但我也好奇他们是否在一定程度上受制于营销方式，因为从术语的角度来看它非常难理解，里面包含的东西太多了。不过我认为 Gas Town 的营销也是推动它传播的因素之一，对吧？比如……

<details><summary>Original English</summary>
>> Yeah. I this is like a maybe I mean relevant to but I wonder how much of I mean I played a little with Gastown very involved system maybe a little ahead of its time um but I'd also wonder if they were like bottleneck a little bit by the by the marketing and that it was a very difficult thing to gro from a terminology perspective like there's just a lot going on I think the Gas Town marketing also is one of the things that propelled it right like
</details>

>> 在 Gas Town 之前紧接着是什么？当时有……

<details><summary>Original English</summary>
>> what was right before Gas Town there were like
</details>

>> 他的……是的，Beats，他做的……除非你在说别人的。不，不，当时有整套 open claw，还有别的什么，然后就是 Gas Town。整篇宣言也真正推动了它在概念层面的传播。那些绝不会使用 Gas Town 的人，也因为可以读到这份宣言而了解了 Gas Town。所以这其中有营销的视角。

<details><summary>Original English</summary>
>> the like his his Yeah Beats he did unless you're talking about someone else's No, no, there were like there was the whole open claw, there was something else, and there was Gas Town. And the whole manifesto also really helped spur it into the conceptual. The people that would never use Gas Town, but learned about Gas Town cuz you can read the manifesto like there there's a marketing angle to it.
</details>

>> 是的。所以……但我确实认为，虽然不必对他字面上的话全盘接受，但大方向是对的。所以我认为他在这点上大方向没错。如果你处于 IDE 阶段，就该进入高阶用户阶段了；如果你处于单智能体阶段，可能该转向多智能体了，等等等等。而且你可能应该尝试构建自己的编排器，对吧？所有这些可以说是……这甚至可以说有点过时了。现在的软件工厂在这些之外还有更多内容。但这篇博文早于软件工厂的概念。我确实觉得，作为雇主，我如今在自己的公司里就面临这个问题：我不想雇用任何没有经历过“精神错乱”并最终走出来的人。

<details><summary>Original English</summary>
>> Yeah. I mean, so so I I but I do so not necessarily someone to take literally, but direct like like directionally correct, you know, and and so I think he's directionally correct on this one. And so if you're at the ID stage, it's time to move into power user stage. If you're a single agent, you probably time to move to multi- aent and blah blah blah. Uh and you probably should try to build your own orchestrator, right? And that's that's all that arguably uh this is not even this is like kind of out of date now. There there is more to the software factory beyond this. Uh but this this article predates the software factory. I I do think you know one of those things where like uh I'm open to as an employer I have this problem in my company today which is I do not want to hire anyone who hasn't been through psychosis and come out the other end
</details>

>> 因为我现在正在出钱资助某个人去经历这种“精神错乱”。

<details><summary>Original English</summary>
>> because I am currently paying for somebody to go through psychosis
</details>

>> 从他的薪水来看代价非常高，从消耗的 token 来看代价也非常高，而我从中什么都没得到。他自己还不理解，我的反馈他根本听不进去。

<details><summary>Original English</summary>
>> and that's very expensive from his salary uh very expensive from tokens and I'm getting nothing out of it and he doesn't get it like my my feedback doesn't get through
</details>

>> 所以我几乎想鼓励你的学生去经历这种“精神错乱”，然后再走出来，心想：“好吧，我当时到底是怎么了？”对吧？因为 Steve 刚刚经历的，就是一场长达两年的、非常公开的这种历程。是的。

<details><summary>Original English</summary>
>> and so like uh it's almost like I would encourage your students to have psychosis and then come out and go like, "Okay, what was wrong with me?" Right? Cuz like that's what Steve just went through like a very public two-year journey of this. Yeah.
</details>

>> 在学生那边情况很奇怪。业界有很多“你以为自己很高效，但其实并没有”的情况，学生版本大概也是这样，对吧？你在 Notion 里做图表，做各种个人优化，然后感觉就像：“糟糕，我经历了这场精神错乱，但没有任何改变。”对吧。对吧。

<details><summary>Original English</summary>
>> It's weird on the student side. There's like a lot of uh industry you think you're being productive. You're not is probably the student version, right? You're notion charting and making all these optimizations personal s and it's like dang I went through the psychosis but nothing has changed. Right. Right.
</details>

>> 所以去经历它吧。去经历一遍。

<details><summary>Original English</summary>
>> So go through it. Go through it.
</details>

### 成熟度模型级别

>> 对。是的。我还没看过这个。我其实看过 Boris 提出的一个版本。显然更侧重于云用例，但我记得他做过一个云端构件之类的东西，展示的我认为更多是在团队层面。不过我记得他有四个阶段，不是八个阶段，但大致遵循了相同的演进过程，比如从没有采纳一直到……

<details><summary>Original English</summary>
>> Right. Yeah. Uh I haven't seen this. I've seen a version of this from Boris actually. obviously more geared toward cloud use cases, but I remember he made like a cloud artifact where it showed I think more at the team level, but I think he had four stages, not eight stages, but it kind of rough roughly followed the same progression of like no adoption to through to you know I guess
</details>

>> 只有四个阶段挺好的。这层级太多了。是的。好吧，看看 V 能不能把它调出来。但除此之外，放眼全局，我们讨论完所有事情了吗？那是其一，噢，那是其一。好了，找到了。它是一个架构师。好的。

<details><summary>Original English</summary>
>> only four is good. This is this is too many levels. Yeah. Well see we'll see if uh V can pull it up but other than that you know zooming out have we you know discussed all the things that's one oh that's one okay there we go. It is an architect. Okay.
</details>

>> 所以，分别是门控式（gated）、辅助式（assisted）、并行式（parallel）。最后一个是什么？

<details><summary>Original English</summary>
>> So, it's gated, assisted, parallel. What's the last one?
</details>

>> 受监督的自主（supervised autonomy）和 AI 原生（AI native）。好的。

<details><summary>Original English</summary>
>> Supervised autonomy and AI native. Okay.
</details>

>> 所以它是从 0 开始索引的。一共是五个层级，对吧？

<details><summary>Original English</summary>
>> So, it's zero index. So, it's five levels, right?
</details>

>> 好的。

<details><summary>Original English</summary>
>> All right.
</details>

>> 从 0 开始。

<details><summary>Original English</summary>
>> Start at zero.
</details>

>> 是的。哇。其实挺不错的。我需要更深入地通读一下这个。

<details><summary>Original English</summary>
>> Yeah. Wow. Actually, it's pretty good. I need to uh read through this in more more depth.
</details>

>> 使用 AI 原生。这就对了。

<details><summary>Original English</summary>
>> Use a native. There you go.
</details>

>> 我要给动态工作流点个赞。这是 open 那帮人正在搞的子智能体模式之一……

<details><summary>Original English</summary>
>> I would give a shout out to dynamic workflows. This is one of those things that is a sub aent pattern that the open guys are
</details>

<!-- chunk 18/18 -->

也在探索。嗯，那显然是契合的，所以基本上就是你在为你正尝试做的事情按需编写测试框架（harness）。

<details><summary>Original English</summary>
also exploring. um that is clearly fitting and uh and so it's basically you're writing a harness on demand for the thing that you're trying to do.
</details>

>> 于是，可能很多子代理（sub agent）对话只是你在复制父代理，

<details><summary>Original English</summary>
>> And so uh this is maybe like a lot of sub agent conversation is just you're copying the the parent agent
</details>

>> 但实际上你应该写多得多的代码，然后把那作为子代理运行，而这就是 Anthropic 那帮人选择称之为动态工作流（dynamic workflows）的东西。

<details><summary>Original English</summary>
>> but you actually should be writing way more code and then like running that as a as a as a sub agent and that is what the enthropic people have chosen to call dynamic workflows.
</details>

>> 好吧。但你知道——

<details><summary>Original English</summary>
>> Okay. Uh but you know
</details>

>> 是的，我们也构建了它的一个版本。是的，这是个好模式——

<details><summary>Original English</summary>
>> yeah we we've built a version of this as well. Yeah, it's it's a good pattern
</details>

>> 针对 Monaco。

<details><summary>Original English</summary>
>> for Monaco.
</details>

>> 嗯。是的。

<details><summary>Original English</summary>
>> Mhm. Yeah.
</details>

>> 它是做什么的？是的。我是指即时构建针对 GTM 的类似 harness 的用例。是的。

<details><summary>Original English</summary>
>> What does it do? Yeah. I mean on the fly sort of like harness sort of use cases for GTM. Yeah.
</details>

>> 哦，那太棒了。

<details><summary>Original English</summary>
>> Oh, that's great.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯

<details><summary>Original English</summary>
>> Um
</details>

>> 我要给听众指出来，当 Boris 写下这个时，是面向团队采纳的。而且他还说，你知道，Anthropic 处于阶段三。我们仍在努力迈向阶段四。

<details><summary>Original English</summary>
>> I will note that when Boris wrote this, it's for team adoption for people that are listening. And also he says, you know, Enthropic is on stage three. We're still trying to get to stage four.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 他就像是，我正处于阶段四。我就是那个人。但是，你知道，它并不像 Steve 的那样简单。像 Steve 是非常棒的个人“做这个做这个做这个”，而这个则更多是如果你在管理一个团队，并且想让你的团队彻底接受 AI（AI pill），而不仅仅是作为其中一个用户，你知道 Anthropic 仍然处于阶段三，别——

<details><summary>Original English</summary>
>> He's like, I am at stage four. I'm the guy. But, you know, it's it's not as simple as Steve's. like Steve is a very good personal do this do this do this uh this is a much more if you're running a team and you want to AI pill your team and not just be a user of one you know anthropic is still at stage three don't
</details>

>> 别像，是的

<details><summary>Original English</summary>
>> don't be like yeah
</details>

>> 好吧，我是说你应该教这个，这太棒了，这包含了我们谈论过的所有内容，这就是我们讨论过的一切

<details><summary>Original English</summary>
>> okay I mean you should teach this this is this is great this is this got all the stuff that this is everything that we talked about
</details>

>> 确实是

<details><summary>Original English</summary>
>> there you go
</details>

>> 我真不敢相信自己以前竟然没碰见过这个

<details><summary>Original English</summary>
>> I I can't believe I haven't come across this
</details>

>> 嗯

<details><summary>Original English</summary>
>> um
</details>

>> 很好的资源，是的

<details><summary>Original English</summary>
>> good resource yeah
</details>

### 斯坦福课程总结与寄语

>> 非常非常棒。好的，那是一趟狂野的旅程，在 1 小时或两小时内讲完了斯坦福一学期的内容。感谢你做这些。最后还有什么想法吗？有什么行动号召（calls to action）吗？

<details><summary>Original English</summary>
>> very very good okay that was a wild tour once one semester of Stanford in 1 hour or two two hours. Thank you for doing this. Any parting thoughts? Any calls to action?
</details>

>> 没有，这次很——我是说，超级有趣。你知道，这经历了九个月的酝酿。我很兴奋。这是第一周的结束。有很多事情要做，有很多东西要学。我很高兴看到接下来的进展，特别是与开源（OSS）伙伴的合作，以及让学生们深入到一些复杂代码库的代码中。嗯，让他们构建一些东西。所以不，这会很有趣。我会随时向你们通报进展。

<details><summary>Original English</summary>
>> No, this was uh thanks for I mean ton of fun. It's it's been a you know nine months in the making. I'm excited. This is end of week one. A lot to do, a lot to learn. I'm excited to see what happens with especially the OSS partners and just getting students like deep in in the code of of some complex code bases. Um having them build some stuff. So no, it'll be fun. Keep you guys posted.
</details>

>> 你们明年还会办另一期。你——你们需要给学生的积分（credits）。如果有开源领域的人想要参与，他们可以联系。

<details><summary>Original English</summary>
>> You're doing another version next year. You you need credits for students. If OSS people want to get involved, they can reach out.
</details>

>> 当然。

<details><summary>Original English</summary>
>> Sure.
</details>

>> 因为积分很重要。他们想要吗？

<details><summary>Original English</summary>
>> Because credits matter. Do they want it?
</details>

>> 什么？

<details><summary>Original English</summary>
>> What?
</details>

>> 他们真的想要积分吗？

<details><summary>Original English</summary>
>> Do they actually want the credit? The
</details>

>> 学生们，或者他们想要——你有信用卡。我觉得很多学生不想花钱。

<details><summary>Original English</summary>
>> students or they want you you have credit card. I don't think a lot of students want to spend.
</details>

>> 我想要——是的，信用卡。但是——

<details><summary>Original English</summary>
>> I want Yeah. credit card. But
</details>

>> 是的。不，我想，听着，我记得，你知道，确实有一定数量的额度（credits），但除此之外他表示，如果他们想在这个方向上放手大干，告诉我，我们会有这些单次实验，他们可以直接扩展到一千个以上的代理。这是来自 Factory 的。

<details><summary>Original English</summary>
>> yeah. No, I I I think look I go like I remember you know it was like you know there's a certain number of credits for sure but then on top of that he's like look if they want to go hog wild with this like let me know and we'll do have these like one-off experiments where they can just like scale up to like a thousand plus agents. This is from factory.
</details>

>> 是的，你知道 Factory。

<details><summary>Original English</summary>
>> Yeah, you know factory.
</details>

>> 不，那种人很有价值。就像 Cursor 的 Wilson，对吧？他说“我要写一个浏览器”，对吧？

<details><summary>Original English</summary>
>> No, those kind of people are valuable. So this is Wilson from cursor, right? Who is like I'm going to write a browser, right?
</details>

>> 那些有野心而且确实能执行的人，是非常有价值的，这基本上就是一个招聘号召。

<details><summary>Original English</summary>
>> Those people who are ambitious and like can actually execute, those are very valuable and that's basically a a recruiting call.
</details>

>> 没错。说得很好。是的，但我确实认为学生们应该懂得如何抱有抱负，因为拍一张照片——恕我直言，拍一张照片然后把它变成一个应用，在这个时代并不算多么有野心。写一个浏览器才算，而且实际上还有很多类似的项目。

<details><summary>Original English</summary>
>> That's right. That's a good point. Yeah, I but I I do think like students should should like understand how to be ambitious because snapping a photo I mean respectfully snapping a photo and turning into an app is not that ambitious in in the this day and age. Uh writing a browser is and there and like there actually is a lot more projects like that.
</details>

>> 是的。是的，我认为没错。是的，关键在于抬高底线。我是指，是的，去年是——你知道，对去年的学生表示赞赏，但是，是的，今年显然我们会有更高的预期，我们更——

<details><summary>Original English</summary>
>> Yeah. Yeah, I think that's right. Yeah, it's all about raising the floor. I mean I think yeah last year it was uh it would you know you know credit to the students of of last year but uh yeah this year I obviously we're going to expect we're more
</details>

>> 那现在就算不合格了。

<details><summary>Original English</summary>
>> that's a fail now.
</details>

>> 我们会有更高的预期。我是说，是的，但那就是整个重点，对吧？比如我们在提升水平，对吧？去年就像是，“嘿，你听说过提示词工程（prompting）吗？这就是它的样子。”我花了一些时间讲像 K-shot 提示作为其中的一节课。而现在，我甚至觉得你们都不会再去琢磨那个了。所以——

<details><summary>Original English</summary>
>> We're going to expect more. I mean, yeah, but that's but that's that's the whole point, right? Like we're leveling up, right? Last year it was like, yeah, hey, have you heard of prompting? Like, here's what it is. And I spent some time talking about like, you know, Kshot prompting as one of the lessons. And like, I don't even think you guys even think about that now. So,
</details>

>> 我觉得有一种情况是认为自己在班级同学中脱颖而出。然后还有另一种情况，就是你也处在行业中一帮人的早期工程角色中，大家仍在努力找工作。拍——拍，你知道，不是为了特意点名某个 demo，但你确实可以通过做很多事来脱颖而出。我给学生们提供一个第 11 周的免费锦囊：做基准测试（benchmarks），做基准测试和评估（evals）。一个好的基准测试会让你敲开每个前沿实验室的大门，敲开每个顶尖代理实验室的大门。

<details><summary>Original English</summary>
>> I think there's a there's a version of thinking you stick out in your cohort of classes. And then there's also a version of you're also in early engineering roles of a bunch of people in industry, people still trying to get jobs. and snap snap uh you know not to call out one demo but you can you can do a lot to stick out for sure. I I'll give uh students a freebie uh of a week 11. Uh make benchmarks, make benchmarks and evals. Uh this will get you uh a good one going to get you in the door of every frontier lab in every front every top agent lab.
</details>

>> 带着严谨态度、针对任何有趣内容写出的优秀工程博客文章。那里有很多基准测试或者触手可及的成果，但工程博客文章的效果确实非常好，对吧？你深入钻研了一件事。

<details><summary>Original English</summary>
>> Good good engineering blog posts with some rigor on anything interesting. There's a lot of benchmarks or low hanging fruit there, but the engineering blog posts do really well, right? You you went deep on one thing.
</details>

>> 是的。嗯，而且可能在里面也能赚很多钱。所以，不仅是敲开大门，如果你把那个做成业务，你真的、真的能从中狠赚一笔。

<details><summary>Original English</summary>
>> Yeah. Um and probably also there's like big a lot of money to be made in that as well. So, not just uh in the doors, but if you make that into businesses, you you can uh you can really really cash in on that.
</details>

>> 是的。大家不知道像 SWE-bench 曾经是本科生项目。

<details><summary>Original English</summary>
>> Yeah. People don't know like Sweetbench was like undergrad project.
</details>

>> 是的。是的。是的。没错。来自——来自普林斯顿，对吧？是的。是的。是的。

<details><summary>Original English</summary>
>> Yes. Yes. Yes. That's right. From from Princeton, right? Yeah. Yeah. Yeah.
</details>

>> 太好了。好的。嗯，太棒了。他已经。

<details><summary>Original English</summary>
>> Great. Okay. Well, fantastic. He has.
</details>