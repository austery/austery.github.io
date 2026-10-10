---
author: The Pragmatic Engineer
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UlXpOGIpITM
speaker: The Pragmatic Engineer
tags:
  - containerization
  - career-development
  - infrastructure
  - generative-ai
title: Kelsey Hightower 专访：从高中辍学到谷歌杰出工程师的非传统职业道路
summary: "在这场深度访谈中，Kelsey Hightower 分享了他从高中辍学、考取 A+ 认证开启 IT 职业生涯，到最终成为 Google 杰出工程师并功成身退的非凡历程。讨论涵盖了 Kubernetes 与 Docker 的容器化变革、自动化运维的演进、拒绝微软 CEO 邀约的幕后故事，以及他对生成式 AI 时代软件工程师职业发展的务实建议。"
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Kelsey Hightower
  - Satya Nadella
companies_orgs:
  - Google
  - Microsoft
  - Docker
products_models:
  - Kubernetes
  - Terraform
media_books: []
status: evergreen
---

### Kubernetes 的突破与访谈开场

**主持人**: 你认为到底是什么让 **Kubernetes** 取得了突破性进展？

<details>
<summary>Original English</summary>

**Host**: What do you think really made Kubernetes breakthrough?

</details>

**Kelsey Hightower**: 排名第一的成功因素是 **Docker**。现在，我们不需要再争论 Java、Python 还是 Ruby，你只需要讨论如何调度 Docker 容器。我们已经赢在了起跑线上，因为你可以直接复用相同的 Docker 容器。我还记得我收到了**微软** CEO **Satya Nadella**（萨提亚·纳德拉）发来的一封很棒的邮件。我点开附件的 PDF，发现薪酬等式里多加了一个零。你看着它会想，我都不知道他们还能开出这种条件。我们知道这种事会发生，但在 1999 年高中毕业、选择去考 A+ 认证的那个人，并不知道自己还能有这种机会。所以，我当时是真的认真考虑过去微软的。我并不是一个纯粹的“生成式 AI 黑子”。我只是不喜欢那种天真盲目的推广和采用。我认为它的应用应该更具战略性。既然我把生成式 AI 看作一种工具，而不是人类的完美替代品，那我就能以更加务实的方式来使用它。当涉及 AI 时，我在会议开始前要做的第一件事就是：不要说“AI”。因为 Kelsey Hightower 作为 Kubernetes 社区最具影响力的声音之一而闻名，但你绝对猜不到他的职业生涯是如何起步的。19 岁时，他从大学辍学，成了一名 DSL 调制解调器安装工，之后自学成为开发者，并最终晋升为 **Google** 的杰出工程师。在 43 岁时，他在行业的巅峰期选择了退休。今天，我们将探讨 Kelsey 进军科技界的不寻常之路，以及他如何常常在不经意间为自己创造新机会。我们还会聊聊容器战争的内幕：**Puppet**、Docker、**Terraform**、**CoreOS**，以及 Kubernetes 是如何最终胜出的。探讨他如何从一名 Google 独立贡献者（IC）成长为高管级别，如何拒绝了萨提亚·纳德拉亲自发出的微软 Offer 却依然实现了薪酬翻倍。他还为那些担心被 AI 商品化的软件工程师提供了务实且接地气的建议。如果你是一名正在思考长期职业发展轨迹的工程师——无论是想要晋升到 Staff 以上级别、成为独立顾问，还是在悄悄计划离开这个行业，这期播客都非常适合你。坦白说，这期节目比平常的节目要长，因为我整个人都被死死地钉在了椅子上，完全沉浸在 Kelsey 的故事和思考中。本期节目由 **Antithesis** 赞助播出。无需人工审查或传统的集成测试，即可验证系统正确性，避免 Bug 或停机。在我们开始之前，我想提一下我们的赞助商 Antithesis，顺便给大家上点历史课。在过去的二十年里，软件开发经历了一场从“命令式”到“声明式”的思维转变。基础设施就是一个完美的例子。想想像 Puppet 和 Ansible 这样的工具是如何允许我们声明单个服务器应如何配置的。接着 Terraform 出现了，它让我们能够声明整个基础设施的期望最终状态：服务器、网络、数据库及其相互关系。然后是 Kubernetes，我们不再需要编写容器生命周期的脚本。相反，我们编写清单，声明类似“我希望这个应用程序的副本暴露在具有这么多 CPU 和内存的服务后面”这样的内容。一旦我们不再需要指定基础设施的每一个小细节，部署软件的速度就变得快得多。但随之而来的瓶颈变成了：我们能多快地测试和验证要部署的代码？测试仍然是命令式的。我们必须为每一个小细节编写测试。而现在，随着大语言模型（LLMs）的出现，我们在代码编写方式上也处于声明式转变的边缘。只需告诉模型你想要什么，让它自己算出细节。但这会让“验证瓶颈”恶化一百万倍。Antithesis 是一款声明式测试工具，能够跟上你的 AI 编码 Agent 的步伐。你声明你希望软件具备的属性，Antithesis 会自己找出如何为你检查它们。用 Agent 编写代码的速度来验证你的代码，并带着满满的信心发布。访问 antithesis.com/pragmatic。Kelsey，欢迎来到播客。很高兴能见到你本人。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: The number one success criteria was Docker. Now instead of talking about Java versus Python versus Ruby, you only have to talk about scheduling Docker containers. We were already off to a running start because you could just reuse the same Docker containers. And I remember I get this email from Satia, the CEO of Microsoft, and I'm like, man, he wrote this nice email and I open a PDF and there's a zero get added to the equation. And so you're looking at this like, I didn't even know that they do that. We know that it happens, but the person that graduated from high school in 1999 that chose the A+ certification didn't know that was available. So, I was serious about going to Microsoft. I'm not just like a Genai hater. I just don't like the naive promotion and adoption of it. I think it should be way strategic. And since I think about Genai as a tool versus the great human replacement, then I can use it in way more primatic ways. And when AI is involved, the one thing I just do before the thing kicks off in this meeting, do not say AI because Kelsey High Tower is known as one of the most influential voices in the Kubernetes community, but you wouldn't guess from how his career started. At 19, he dropped out of college to be a DSL model installer, became a self-taught developer, and still went on to become a distinguished engineer at Google. At age 43, he then retired at the very top of the industry. Today we cover Kelsey's unconventional path into tech and how he kept creating new opportunities for himself often unknowingly. The inside story of the container wars, puppet, Docker, Terraform, Coros and how Kubernetes eventually won. Going from a Google IC to executive level and how he rejected a Microsoft offer from Sachio Nadella himself and still doubled his compensation. His grounded on pragmatic advice for software engineers worried about being commoditized by AI and so much more. If you're an engineer thinking about your long-term career trajectory, whether that's getting into a staff plus level, going independent, or even quietly planning to leave the industry, this episode is for you. This episode is longer than a normal episode, frankly, because I was so glued to my chair, mostly listening to Kelsey's stories and thinking. This episode is presented by Anticys. Verify your systems correctness without human review or traditional integration tests and avoid bugs or outages. Before we start, I'd like to mention our presenting sponsor, Antithesis, and maybe offer a little history lesson. Over the last two decades, software development has gone through a mindset shift from an imperative approach to declarative one. Infrastructure is a perfect example. Think about how tools like Puppet and Ansible allow declaring how individual servers should be configured. Then came Terraform, the ability to declare the desired end state of your whole infrastructure, servers, networks, databases, and their relationships. And then with Kubernetes, we stop scripting container life cycles. Instead, we write manifests that say things like, I want the replicas of this application exposed behind a surface with this much CPU and memory. Once we didn't have to specify every little detail of our infrastructure anymore, deploying software became much faster. But then the bottleneck became how quickly we could test and verify the code to be deployed. Testing remained imperative. We had to write tests for every little detail. And now with LLMs, we're on the verge of a declarative shift in the way code is written as well. Just tell the model what you want and let it figure out the details, and it's going to make the verification bottleneck a million times worse. Anthesis is a declarative testing tool that can keep up with your AI coding agents. You state the properties you want your software to have, and antithesis figures out how to check them for you. Verify your code as fast as agents can write it and ship with Growlin confidence. Head to insys.com/pragmatic. Kelsey, welcome to the podcast. It's so nice to see you in person.

</details>

**Kelsey Hightower**: 是的，我其实很高兴来到这里，主要是因为这些年我一直在关注你的内容。所以，能在阿姆斯特丹这里也是我的荣幸。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah, I'm actually happy to be here mainly because I kind of look at your stuff over the years. So, it's honor to be here in Amsterdam as well.

</details>

### 赚取人生第一桶金

**主持人**: 你在工作中赚到的第一块钱是怎么来的？

<details>
<summary>Original English</summary>

**Host**: How did you make your first dollar at a job?

</details>

**Kelsey Hightower**: 哦，工作中的第一块钱是在麦当劳赚的，对吧？那个也算。在高中时，你通常会找离自己最近的工作。那家店离我家只有步行距离。我一到法定年龄，也就是 14 岁，就拿到了工作许可证。我去了那里，那是那种你可以当天填申请表、当天拿到信息、通常当天就能被雇佣的工作。他们问我：“你什么时候能开始？”我说：“就现在。”他们就去后台给我找了一件衬衫。他们问：“你穿多大码？”我说：“男士大码。”我喜欢那份工作的一点是，你在与真正赶时间的人打交道。不过这份工作也有个不好的地方，很多人不尊重做这种工作的人。他们往往只把你当作他们和他们想要的东西之间的一个中间人。但要运营那样一家餐厅，背后其实有很多东西。它非常高效，大家都有很高的期望。我学会了如何运营整家店。所以到我 15 岁时，我已经是一名助理经理了。在晚上和周末，其他经理离开后，他们会把钥匙交给这个 15 岁的孩子。我懂得在那里做所有事情，包括关店打烊。你必须清点所有的钱，每天晚上你必须把这张巨大的电子表格传真给总部。然后我妈妈会来接我。所以，在那个年纪学会如何真正承担责任（甚至是对成年人的责任），这真的很好。这就是我赚到第一块钱的方式。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Oh, my first dollar at a job McDonald's, right? That counts. So, in high school, you get the job that's closest to you. So, it was in walking distance of my house. As soon as I turned legal age, uh 14, get a work permit. And I went there and it was one of those jobs where, you know, you go, you fill out the application the same day. You typically get your information or you're going to get hired the same day. When can you start? I'm like, right now. They go get a shirt for you in the back. You What size do you wear? Uh, men's large. And the one thing I liked about that job is you're dealing with real people that are in a hurry. I guess one bad part about the job, you know, a lot of people don't respect people who have that job. So, they kind of look at you as just like this intermediary thing between them and what they want. But there's so many things that go into a restaurant like that. It's very efficient. Um, you know, people have expectations. And I learned how to run the whole store. So, by the time I turned 15, I was a assistant manager. So, nights and weekends, you know, other managers would leave. They would give this 15-year-old the keys. And I knew how to do everything there, including close out the store, right? So, you have to count all the money. You have to fax this huge spreadsheet to corporate every night. And then my mom would pick me up. And so it was really good learning how to really be responsible even for adults at that age. So that's how I got my first dollar.

</details>

### 初探技术与编程世界

**主持人**: 你是怎么进入科技行业的？你是怎么开始接触编程的？

<details>
<summary>Original English</summary>

**Host**: How did you get into tech? How did you get into programming

</details>

**Kelsey Hightower**: 是在高中时，因为我从加州搬到了亚特兰大。从国家的一端横跨到另一端。我可能错过了 3 到 6 个月的课程，为了能按时毕业，我必须多修几门课。作为一个玩体育、练田径、打橄榄球和篮球的人，我当时觉得，“电脑编程这类东西，那是给书呆子准备的”，你懂的，我当时还想装酷。但我做了一件事，我真的很喜欢它，那就是 **AutoCAD**。我甚至在州一级参加了 AutoCAD 比赛。我们开车过去比赛，他们给你一个任务，你坐在电脑前。那是我第一年做这个，但我真的很喜欢这种接受规范并将其设计出来的想法。如果我当时能让产品成功运行，我可能就能拿第一名了。因为你还得把它打印出来，以便评委审查你的工作。虽然我没成功打印，但我还是拿了第二名。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: in high school since I moved from California to Atlanta? So right, you're going from one side of the country to another side of the country. And uh I missed maybe 3 to 6 months of school and in order to graduate on time, I had to take some extra classes. And so as someone who played sports, ran track, uh played football, played basketball, and it's like, you know, there's this computer programming not, you know, computer club, technology student association. There was a class component and then there was after school component. And I was like, I don't know, man. This computer stuff that's for the, you know, you know, I'm trying to be a cool kid. But the one thing I did, I really enjoyed it, right? So I I had a liking to AutoCAD. I even competed at the state level in AutoCAD. So we we drove down and you compete. They give you a task and you sit in front of the computer. It was my first year doing it, but I really like the idea of like taking a specification, designing it, and I probably would have gotten first place if I would have got the product to work because you also have to print it out so that the judges can review your work. So I got second place even though I didn't.

</details>

**主持人**: 那是 3D 建模。

<details>
<summary>Original English</summary>

**Host**: This is the 3D modeling.

</details>

**Kelsey Hightower**: 是的。AutoCAD，就是普通的 AutoCAD。所以课程的一部分就是建桥梁之类的。我们还做了一些与分会团队合作的项目，比如制作盾徽，有点像辩论一样。你学到了很多与业务相关的知识，但 CAD 是我最喜欢的东西之一。同样在那门课上，我的一位同学教我用 TI Basic。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. AutoCAD, you know, just AutoCAD. Yeah. So part of the curriculum was, you know, you build bridges. We did this thing with um chapter team where you know you have a code of arms and you're kind of doing like a debate. Do you kind of learn all of these things uh related to business but CAD was one of the things I like most? Also in that class one of the classmates taught me TI basic.

</details>

**主持人**: 那是 BASIC 语言的一个版本吗？

<details>
<summary>Original English</summary>

**Host**: Is that a version of of basic?

</details>

**Kelsey Hightower**: 嗯，是的，TI Basic。你知道那种图形计算器吗？就像 TI-86。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Well so TI basic so you know the graphing calculator it's like a TI86. Oh yeah.

</details>

**主持人**: 哦，是的，你是可以对它编程的。

<details>
<summary>Original English</summary>

**Host**: You can program it.

</details>

**Kelsey Hightower**: 对。所以在课堂上他们会说，“嘿，这不仅仅是一个图形计算器，你实际上可以对它进行编程。”我当时就问：“那是什么？”他们说：“看，在这个时候，你可以编写贪吃蛇游戏。”基本上就是拿一本杂志，复制粘贴上面的代码，然后运行，你就可以玩自己写代码的贪吃蛇了。你会开始尝试这个概念。所以那可能是我对编程的第一次接触， literalmente 就是给我的 TI-86 计算器编程。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: right. So in class they're like hey you know it's not just a graphing calculator you can actually program it. And I was like what's that? And it's like look we can you know every at that one at that time you would create the snake game right so it's basically get a magazine copy and paste the code and then you run it and now you're playing snake uh based on the code you wrote and so you would toy around with this concept so that was probably the first introduction to programming was literally programming my my TI86 calculator

</details>

### 绕过大学：A+ 认证与入行

**主持人**: 高中毕业后，你上大学了吗？或者你考虑过上大学吗？

<details>
<summary>Original English</summary>

**Host**: and after high school did you go to college or you considered college right

</details>

**Kelsey Hightower**: 我考虑过上大学，因为当时在乔治亚州（现在也是如此）有一个叫做 HOPE 计划的项目。如果你的平均成绩达到 B 或以上，你就可以免费去任何一所公立学校。乔治亚州的公立学校包括佐治亚理工学院、佐治亚州立大学等。这些都是非常好的大学。

所以我决定去我家附近的一所。但头两周我就觉得：“嗯，这太慢了。这不是我想要的发展节奏。”而且要记住，我毕业的那年是 1999 年。当你打开电视，人们正排队购买新版本的 Windows。市场充满了一种狂热情绪。AOL 开始逐渐淘汰，我们开始接触高速互联网。我当时就觉得：“哟，看看这发展的速度。”而且你也听到了各种说法，比如比尔·盖茨从大学辍学。人们已经不再像以前那样神化文凭了，一切都看重技能。然而不幸的是，我当时并不认识任何程序员，也不认识任何系统管理员，因为在那个时候，所有的系统都像 Sun Microsystems 或者 IBM 大型机，这些东西还在企业里使用。所以当我查看招聘信息时，我看到的是一堆我甚至不知道该如何获得的技能。

因此，我没有上大学，而是继续做快餐，当时在必胜客送披萨。我记得有一次去书店，他们那里有 **A+ 认证**指南。我看了看，有些招聘启事上写着：“嘿，你需要有 A+ 认证才能申请这个支持职位。”我当时就想：“你知道吗？这不需要上大学，而且这本书只要 35 美元。”我记得我买了那本书，这是一个官方认证过程。看起来它是就业市场的一部分。我买下那本书后，一遍又一遍地从头读到尾。你学习了所有的基础知识，对吧？你了解了主板、内存以及所有这些东西是如何工作的，还有关于操作系统的部分，书后还有一个小练习测试。对于像我这样的人来说，有这种快速的反馈循环很好：把 CD 放进去，参加考试，尽管是选择题，但如果你做错了，你就可以回到书本，确保自己理解了书上的内容，然后再考一次。它有一定的随机性，所以你不能只靠死记硬背。

我记得去考试中心参加考试，你在那个小房间里，他们为了确保你不作弊，还会用摄像头对着你。那种考试的好处在于，没有陷阱题。你要么知道，要么不知道。我记得他们可能给了你一个半小时。但我大概 10 分钟就做完了。当我走下来时，拨号连接的声音响起，他们计算了你的分数并说：“嘿，你通过了。”然后你走出来，你就是 A+ 认证专家了。那是我职业生涯中第一次觉得，哦，只要你付出努力，你就能获得证书。当我拿到那个证书后，我记得有一个招聘会，上面写着：“嘿，任何拥有 A+ 和 Network+ 认证的人，都可以加入当时把人们的拨号上网更换为 DSL 的承包商团队。”就这样，我算是正式进入了科技行业。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I considered college because in Georgia at the time and still today there's a thing we're called the hope program. So if you have a B average or above, you can go to any public school for free. And public schools in Georgia include Georgia Tech, Georgia State. These are pretty good universities. They're really good.
And so I decided to go to one that was near me. The first two weeks I was like, um, this is too slow. This is not
this is not the pace that I want to move at. And also remember it's 1999 when I'm graduating. And so when you turn on the TV, people are standing in line for the next version of Windows. There's a lot of euphoria. AOL is starting to phase out and we're starting to touch on highspeed internet and and I was like, yo, look at look at the pace this is moving, but also you're hearing the narratives. Bill Gates drops out of college. These people are not necessarily glorifying the degree anymore. It's all about the skill. Now, unfortunately for me, I didn't know anyone that was a programmer. I didn't know anyone that was like a system administrator because at that time all the systems with like Sun Micros systemystems or IBM mainframe those are still the things that are in the enterprise. So when I looked at the job openings I'm seeing a bunch of skills that I don't even know how to acquire. And so instead of going to college you know I'm still doing fast food delivering pizzas at this time at Pizza Hut. And I remember going to a bookstore and they had the A+ certification guide and I looked and some of the job postings said, "Hey, you need to be A+ certified to take this support role or whatever it was." And I was like, "You know what? That doesn't require college. The book is only $35." And I remember buying the book and it is an official certification process. It looks like it was part of the job market. And so I remember buying that book and reading it cover to cover over and over again. and you're learning all the fundamentals, right? You're learning about, you know, how motherboards and how memory and all these things work and there's an OS component and then there's a little practice exam in the back. And so for someone like me, having that fast feedback loop of like you put the CD in, you take the exam and even though it was multiple choice, you kind of felt like if I got anything wrong, I would just go back to the book and make sure that I understood what was written there and then you go take the test again. and it had a little randomization to it so you couldn't just rely on absolute remembering everything. And I remember going to the facility to take the test and you know you're in that little room and they want to make sure you don't cheat. So there's a camera pointed at you and you're just going through it. And so the nice thing about those tests, there's no trick questions. Either you know it or you don't. And I think they maybe give you an hour, hour and a half. And I remember finishing that thing in like 10 minutes. And when I walk down, you know, you wait, the dialup goes and they calculate your score and say, "Hey, you passed." And then you walk out and you're like A+ certified. And that was like the first time in my career that I felt like, oh, so if you put the effort in, you can gain the certificate. And when I got that certificate, I remember there was like a job fair where, hey, anyone that has A+ and network plus certification, you can be part of the contractors that were replacing people's dialup with DSL at the time.
Okay. And so that's how I I guess officially got into tech.

</details>

**主持人**: 可以说你当时认为这是当时进入科技行业最有效的方式吗？

<details>
<summary>Original English</summary>

**Host**: Is it fair to say that you saw that this could be the most efficient way to get into tech at the time?

</details>

**Kelsey Hightower**: 我觉得我当时把它看作是唯一的方式。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I think I said I saw it as the only way.

</details>

**主持人**: 为什么大学从来没有被你视为一条可能的出路？是因为你没有看到先例吗？

<details>
<summary>Original English</summary>

**Host**: Why was college never like telling you like, okay, that could be a way. Was it just you didn't see examples or

</details>

**Kelsey Hightower**: 是的，我从没见过这种先例。我从未见过它的最终结果。他们教授的许多课程内容，让我觉得花那么多钱是不合理的。听着，也许那不是一所好学校，也许我选错了课，有很多因素可能导致这种情况。但当我审视这一切时，我当时仰慕的那些人，似乎都没有走这条路。我对学校已经受够了。如果你当时 18 岁，你会觉得，够了。因为当时我觉得学校，其实对我来说太简单了。拿全 A 很容易，我没觉得有什么实质性的挑战。所以我心里想，我还想去接受四年这样的教育吗？我后来才了解到，其实学士学位很大程度上只是 K-12（中小学）教育的延续，你记忆东西，听课；但是到了硕士阶段，你开始挑战知识；当然，如果你能读到博士，理想情况下你要为这个领域增添新的东西。但我从来没有见过任何走得那么远的人。所以我从未把它纳入我的考量中。但通过获得这个 A+ 认证所带来的即时反馈循环，让我觉得，哦，我已经准备好参与到实际的经济和生态系统中了。所以对我来说，这似乎是一条更好的路，而且感觉是一条我自己能掌控的路。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I Yeah, I never saw the examples. I never saw the endgame. A lot of the stuff that they were teaching the curriculum, it didn't make sense that you would pay all that money. You know, look, maybe it wasn't a good school. Maybe it was the wrong class that I took. There's so many factors that could have went into this. But when I looked at it, none of the people that at the time that I was looking up to, this is not the path that they seem to be taking. And so I had enough of school, right? If you're 18 at that time, you're like, look, that that's enough of this. Because at the time, I kind of felt school was this because it was so easy for me actually. You know, it's like it was easy to get straight A's. I didn't feel like there was a serious challenge. So it's like, hey, I want to go and do four more years of this. And I would later learn that look bachelors is a lot of the similar that you go through through K through 12, you kind of remember stuff, you listen to the lessons, but then masters you challenge the material and of course if you make it to PhD ideally you're adding something new to the field and I never saw anyone that has made it that far. So I never put that in part of my calculus. So, but just having that immediate feedback loop of like getting this A+ certification and feeling like, oh, I'm ready to participate in the actual economy, the ecosystem. So, to me, I was like, this seems like a better path. And it felt like a path that I would control.

</details>

### 初入职场与首次创业

**主持人**: 那么你拿这个 CompTIA 认证找到的第一份工作是什么？

<details>
<summary>Original English</summary>

**Host**: Yeah. And then what was your first job that you could get with with the certification? This was the comta, right?

</details>

**Kelsey Hightower**: 是的。那时 Bell South 可能是美国最大的电信公司。他们当时已经从早期的 AT&T 中拆分出来了。那时负责电话线的人，也就是正式的 Bell South 技术人员，开着漂亮的卡车，拥有所有设备。但当他们转向高速互联网时，意味着你必须接触电脑。我想作为一个工会，他们会说：“听着，我们不碰电脑，我们甚至不进客户的房子，我们到了分界点就停下来。”所以他们请了承包商进来。承包商的工作就是进来，做一些布线工作。如果你需要拉网线，你就去做；制作 Cat 5 网线，你也做。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. So, at that time, Bell South was, you know, the biggest telco uh probably in America. you know they had been broken up by that time from the AT&T days at that time the people who did phone lines right so those are the official Bell South technicians they drive the fancy trucks they have all the equipment and when they made the shift to highspeed internet that means you had to actually touch the computer and I think as a union they're like look we don't touch the computer we don't even go into the house we we get to you know the demark and we stop and so they had contractors come in and the contractor's job were to come in, have to do a little bit of wiring. So, if you had to run some cable, you did that. Create Cat 5 cables, you did that.

</details>

**主持人**: 哦，是的。我最早的一份工作也是布线。我现在还忘了确切的颜色代码。

<details>
<summary>Original English</summary>

**Host**: Ooh, yeah. You you I one of my first jobs was actually cabling. So, I still I forgot the exact color code.

</details>

**Kelsey Hightower**: 橙、绿、白、绿、蓝、白、蓝，大概是那样。现在深深印在你的脑海里了。你该做什么就做什么。你必须做的另一件事是打开电脑。你必须做出决定。如果他们的电脑足够新，他们可以使用 USB 调制解调器。那些东西很糟糕，经常坏，你总是要出去维修。但对于一个新的安装，如果你真的想做好，你就在他们电脑后面安装一个网卡（NIC），一个 Cat 5 端口。在那个时候，我们谈论的是 Windows 98。所以通常在 20% 的情况下，当你安装驱动程序时，电脑会崩溃。现在你就面临了一个全新的情况。你必须排除故障让它恢复在线或正常运行。但如果一切顺利，他们就有了网卡，然后你再接上一个外置调制解调器，连接到电话线上，他们就有了高速互联网连接，然后你插上网线。我做这个做了一年左右，然后开始接企业的活。之前你就像挨家挨户去人们的家里，但你去一个企业时，你连接了一台电脑，但那里显然有八台电脑，却只有一台能上网。我记得当时的企业主，比如一个小保险公司，他们会问：“我们怎样让其他的电脑也上网？”第一次有人问我这个问题时，我说：“我不知道。这超出了我的职责范围（pay grade）。”

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Orange, green, white, green, blue, white, blue, something like that.
It's burning in your head now.
And you know, so you did whatever it took. And the other thing you had to do was you have to open the computer. You have to make a decision, right? If they had a new enough computer, they can use a USB modem. Those were terrible. They always broke and you would always come out for a repair. Uh but for a new install, if you really wanted to do a good job, you install a a nick, right? Uh Cat 5 port on the back of their computer. And at that time, like we're talking Windows 98. And so usually, I don't know, 20% of the time as you're installing the drivers, the computer would crash. And now you have a whole another situation. You have to now troubleshoot getting this thing back online or back operational. But if everything went smoothly, they now had a network card and then you had an external modem that then you connected to, you know, the phone line and they had this high-speed internet connection and then you connected the network cable. And I did that for about let's say a year and then I started doing the businesses. So you go into people's homes like you're going door todoor and then when you go to a business you would hook up one computer but there's obviously eight computers there and only one of them has internet access. And I remember at the time, you know, the business owner, it could be like a small insurance company and they would say like, "Hey, how do we get all the other ones online?" And the first time someone asked me that, I'm like, "I I don't know, man. I don't." We put it on one computer like pay grade, right?

</details>

**主持人**: 是的。我们只确保这台能工作。

<details>
<summary>Original English</summary>

**Host**: Yeah. We make sure it works. But then I decided like, "Well, let me go learn." And that's when I remember like going to like Office Depot, right? They sell computer equipment and things like this. And I went in the store and I asked him, I was like, "Oh, you can get one of these Lynxys routers, right? infamous blue spaceship looking Lynxis router.

</details>

**Kelsey Hightower**: 后来我决定：“好吧，让我去学学看。”我记得那时去了像 Office Depot 这样的商店，他们卖电脑设备之类的地方。我走进店里问他们：“哦，你可以买一个这种 **Linksys 路由器**，对吧？”那个臭名昭著的、看起来像蓝色宇宙飞船的 Linksys 路由器。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I still remember them.

</details>

**主持人**: 我现在还记得它们。

<details>
<summary>Original English</summary>

**Host**: And those things were probably like 50 bucks. And I remember just buying one and figuring out how to get multiple computers to to use one connection. And so eventually I was like, look, I can't do it as part of the job because we we have to do this and we have to leave, but here's my carp. And then they will call you. And I remember one of the first installations that I did on my own. Uh they wrote me a check and I was like, "Yep, you could just write it out to Kelsey High Tower." He was like, "No, we don't we don't write checks to people. We write checks to companies." And I remember right there on the spot, I'm like, "Oh man, I need a company name." And I just made one up digital gateways. And they wrote that on the check and I'm sitting there like, "So, how do you cash this?" So, I went to the bank and they're like, "Sir, you have to get a business license. The business license, you could just do business ads. You have to do this." So, I'm figuring out now I'm 19 years old. Like, okay, I got to go get a business license. Have to figure all this stuff out. So, I do everything. I open a business account just so I can cash the check. But at that point, I'm like, "Oh, this pays more than this does." And so, I got really good at doing those network installs. I really got good at troubleshooting cuz sometimes someone gave them a USB modem, lightning comes, the USB modem is fried, and then you would swap them out for a network card. And eventually, I decided like, I can probably do my own business. And I decided to get some office space. So, I opened a small computer store right outside of Atlanta. I would buy parts from the distributors. I was just like 19, 20 years old. And I wasn't buying enough to really qualify for an account. But luckily, one of the smaller computer stores I used to buy parts from gave a recommendation to the distributor. It's like, hey, this is our guy. He's just getting started. And they gave me an account. And I was able to buy motherboards and GPUs. And people would come over and like they bring their kid and they would have a parts list. I want a computer with all these things and we would assemble machines and you know sell them but also it was the headquarters for all the other service calls. So I did that for like three, four years, you know, that ended up evolving into at the same time or now were talking like 2000, 2001, a lot of the music studios were moving from analog gear and the large mixing boards to ProTools, right? The little rack mount unit. And they all needed max. They all need these conversions. So I added that to my uh abilities. And then I had a small setup in the store and artists and musicians would come in and say, "Hey, we want exactly that in our studio and I would get the order and I added it to the list of things I could do."

</details>

**Kelsey Hightower**: 那些东西当时大概卖 50 块钱。我记得我买了一个，然后摸索出如何让多台电脑共用一个连接。最终我决定，看，我不能把这个作为我原本工作的一部分，因为我们原先的工作有规定的流程，做完就得走。但是我会给他们留张名片。然后他们就会给我打电话。我记得我独立接的第一个安装活儿，他们给我写了一张支票。我说：“好嘞，你直接写 Kelsey Hightower 就行。”对方说：“不行，我们不能把支票开给个人，我们只能开给公司。”我记得当时在现场我就想：“天哪，我需要一个公司名。”我就随口编了一个：“Digital Gateways”。他们在支票上写了这个名字，然后我坐在那儿想：“那这要怎么兑现呢？”于是我去了银行，他们说：“先生，您必须取得营业执照。你可以用‘DBA’（以某名义营业）来做，但你必须完成这些手续。”那时候我才 19 岁，我得去弄懂怎么办营业执照，搞清楚所有这些东西。所以，我搞定了一切，开了一个商业账户，就为了能兑现那张支票。但到了那个时候，我心想：“哦，干这个比我原本的工作赚得还多。”所以，我非常擅长做那些网络安装。我也非常擅长排除故障，因为有时候别人给他们装了 USB 调制解调器，一打雷，USB 调制解调器就烧了，然后你就会去给他们换上网卡。最后，我决定，我大概可以自己做生意了。我决定弄点办公空间。所以，我在亚特兰大市郊开了一家小电脑店。我会从分销商那里进购零件。那时我才 19、20 岁。我进的货还不足以真正获得一个大客户账户资格。但幸运的是，一家我常去买零件的小电脑店向分销商推荐了我。他们说：“嘿，这是我们的人。他刚起步。”于是他们给了我一个账户。我就能买到主板和显卡了。人们会过来，比如带着他们的孩子，拿着一张零件清单。“我想要一台有这些配置的电脑”，我们组装好机器并卖给他们。同时，这里也是所有其他上门服务呼叫的总部。我做这个做了大概三四年。当时大概是 2000 年、2001 年，很多音乐工作室正在从模拟设备和大型混音台转向 Pro Tools，就是那种小型的机架式设备。他们都需要 Mac 电脑。他们都需要这些转换。所以，我把这个也加入到了我的业务能力中。我在店里弄了一个小型的展示区，艺术家和音乐人们会走进来，说：“嘿，我们的工作室里想要一模一样的这套设备。”然后我就会接下订单。就这样，我把它也加入了我能提供的服务清单里。

### 喜剧演员经纪人与加入 Google

**主持人**: 也就是说，这个时候你已经有一家小企业了。听起来发展得不错。然后你突然在 Google 接受了一份员工的工作。现在回想起来，那是怎么发生的？正常来说这更像是一个故事的延续：你成为一名企业家，壮大你的业务，然后顺理成章地发展下去。

<details>
<summary>Original English</summary>

**Host**: I mean, at this point, you now have a small business. Sounds like it's it's going well. And suddenly you take a job at an employee job at Google when I look back, how did that come up up to now? It's it's almost like this is like, you know, the story often times will continue. You become an entrepreneur, you grow your business, you you know, you just take it from there. Even during that time as that store owner, I managed a comedian and we went on the road. And

</details>

**Kelsey Hightower**: 甚至在做店主的那段时间里，我还担任过一位喜剧演员的经纪人，我们还一起去巡演。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: so you were you were helping out your your managing

</details>

**主持人**: 所以你当时在帮忙打理，做经纪人工作。

<details>
<summary>Original English</summary>

**Host**: I had a buddy from high school. He was a comedian. Turns out he was actually really good at it. We even I went to go see him at a club. He's like, "Hey, I need a manager." I was like, "Are you even funny? Like I know you from high school, but I don't remember you being like funny enough that I would pay to see you tell jokes." And um he was like, "I have a show tonight." And so I gave him a ride on the north side of town. And the interesting part, it was a predominantly black audience in Atlanta. Okay, makes sense. And he did these jokes and they laughed and it was one of these comedy clubs where if you're not funny, you have like 3 seconds and they would just boo you off the stage and that's the end of it. And he held it. I was like, "Wow, you survived that. That's um that's incredible. And you were pretty funny." And then we drove about an hour north and the audience is predominantly white. And so on the drive there, I'm like, there is no way you can do those jokes in this room. I got to see how this is going to go. And at the time, they're only paying the comedians like $50. So, you don't make a lot in the early days. And he totally pivoted the set and he held that audience, too. And I was like, "All right, I can be your manager. I know business. I know kind of logistics. I know how to, you know, make a plan together." And I did that for a number of years. and you know he won some televised competitions. We went on the road bands like Earthwind and Fire and some large comedians from Kings of Comedy and Queens of Comedy and I actually picked up some IT work with the company behind it called Letham Entertainment. they had been doing movies at this time. And so now I'm like, you know, doing it for them and I got the small business. I got the comedian. And so, look, I was able to save a lot of money, but man, luckily I was 20 years old cuz I had all this energy, but I was working quite a bit. Eventually, you settle down, you get a family, and you do the math, and it turns out people kind of over glorify entrepreneurship. I think a lot of people believe there is tremendous upside, right? the type of entrepreneurship we talk about with software companies, the the upside is crazy. But when you're doing like selling parts or service business, unless you plan to open lots of stores and you know grow a larger employee base, it's not the same growth trajectory as software companies. And so I kind of did the math after four years of doing that. I said look, I want to settle down. And if you've been an entrepreneur before, you know employees get paid first, the owner gets paid last. And there are months where you get paid less or you don't get paid at all and now you're kind of drawing from savings because it's not their problem. But I did well overall like I did very successful. But I remember it's like you know what I think I'm ready. And so I looked around and Google had data centers nearby and I felt like I had a great combination of skills. I understood you know the racking stack part of the world. I understood the physical part of the networking stack. I understood everything from Linux to Windows. I had an entrepreneur mindset. I didn't think there was nothing I could not do. And I remember going to that interview and they were hiring like data center technicians. What it paid? And in my mind, I'm like that you only have to work for 8 hours. You don't have to issue any invoices and you get paid every 2 weeks no matter what. No inventory. This is crazy. No way they're doing this. And so I go and I remember doing that interview and I didn't know Linux that well. And luckily for me, I knew FreeBSD well. And as I'm answering the questions, I'm like, look, I am not an expert on Linux, not the way Google was asking these questions. And it's like three people on the other side of this table just rapper firing. And I remember I was like, I know FreeBSD. I swear I got lucky. This one of the interview, I think they had a FreeBSD tattoo on their leg, the little beasty logo. And I saw this logo. I'm like, "Oh, I'm saved." And so we started going down the FreeBSD questions and I pass and I get this job in this data center. And it was good because it's like, hey, I'm I'm working with my colleagues, but it felt a bit slow because you only get one job. You come in, you do this thing. And I got really good at it cuz to me, I kind of saw it as like a bit of a competition. Who is the best data center tech here? What are their metrics look like? How do I exceed their metrics? I want to learn how to do every particular thing in this data center because previously as a business owner, the more skills you have, more money you can make. And then I just started switching jobs every 3 to 6 months because I just wanted to explore everything to just amass my abilities. And doing the math, I think every jump was like a 25% pay raise. I mean, coming from a small base, it wasn't it didn't feel big at the time, but after a few jumps, my salary doubled. puppet was uh was a a bit of an inflection point in your career.

</details>

**Kelsey Hightower**: 我有一个高中时的哥们，他是个喜剧演员。结果证明他在这方面非常有天赋。我甚至去过俱乐部看他的表演。他说：“嘿，我需要一个经纪人。”我当时说：“你真的搞笑吗？虽然咱们高中就认识，但我不记得你有搞笑到让我愿意花钱听你说笑话的地步。”他说：“我今晚有场演出。”所以我开车带他去了城市北边。有意思的是，在亚特兰大，那里的观众主要都是黑人。好吧，这很合理。他讲了那些笑话，大家笑了。那是一家要求很高的喜剧俱乐部，如果你不搞笑，你大概只有 3 秒钟的时间，他们就会把你嘘下台，你就完了。但他稳住了局面。我当时觉得：“哇，你挺过了那一关。这真是不可思议。你确实挺搞笑的。”然后我们开车向北走了一个小时，那一带的观众主要都是白人。在开车的路上，我心想，你绝对不能在这个场子里讲刚才那些笑话。我倒要看看接下来会怎样。当时，他们付给喜剧演员的钱可能只有 50 美元。所以在早期你赚不了多少钱。结果他完全调整了他的表演内容，并且成功控住了那群白人观众。我当时就说：“好吧，我可以做你的经纪人。我懂商业，懂后勤规划，我知道如何一起制定计划。”

我做这个做了好几年，你知道，他赢得了一些电视转播的比赛。我们和 Earth, Wind & Fire 这样的乐队，还有一些来自《喜剧之王》和《喜剧女王》的大牌喜剧演员一起去巡演。在此期间，我还顺便从这背后的一家名为 Letham Entertainment 的公司接到了一些 IT 方面的工作。他们当时正在拍电影。所以那时候我就是在为他们做 IT 服务，同时经营我的小生意，还做喜剧演员经纪人。看，我确实攒了不少钱，但也幸亏我当时才 20 岁，因为我精力充沛，但工作量确实非常大。最终，你安顿下来，有了家庭，你算了一笔账，发现人们其实有点过度神化了创业。我认为很多人相信创业有着巨大的上升空间，对吧？当我们谈论软件公司的创业时，那种上升空间确实很疯狂。但如果你做的是像销售零件或服务类业务，除非你计划开很多家分店并大幅扩充员工规模，否则它的增长轨迹与软件公司是不可同日而语的。所以我做了四年的老板之后算了一笔账。我说：“听着，我想安顿下来。”如果你曾经创过业，你就会知道，员工总是最先拿到钱，老板是最后拿到钱的。甚至有些月份，你拿的钱很少，或者根本拿不到钱。这时你就得动用储蓄，因为这是你自己的问题，而不是员工的问题。不过总体来说，我做得很好，我非常成功。但我记得当时我心想：“你知道吗，我想我准备好了。”

于是我看了看周围的机会，Google 在附近有数据中心。我觉得我具备非常棒的技能组合。我懂服务器上架和堆叠（racking and stacking）那一套。我懂网络栈的物理层部分。从 Linux 到 Windows 我都懂。我拥有企业家的思维。我觉得没有什么是我做不到的。我记得去参加那个面试，他们当时在招数据中心技术员。我一看薪水？在我的脑海里，我想：“你只要工作 8 个小时，不用开任何发票，不管怎样每两周就能领到工资。没有库存压力。这太疯狂了。他们怎么可能开出这种条件？”所以我去了，我记得参加那个面试时，我对 Linux 了解得并不是很深。幸好，我非常精通 FreeBSD。在回答问题时，我心想：“听着，我不是 Linux 专家，至少达不到 Google 问这些问题的深度。”桌子对面坐着三个人，像机关枪一样快速提问。我记得我说过：“我懂 FreeBSD。”我发誓我真是走运了。其中一个面试官，我想他的腿上有一个 FreeBSD 的纹身，就是那个小野兽（beastie）的标志。我看到了这个标志。我想：“哦，我得救了。”于是我们开始围绕 FreeBSD 提问，我通过了，拿到了数据中心这份工作。这很不错，因为嘿，我和同事们一起工作，但感觉节奏有点慢，因为你每次只能接到一个任务。你走进来，就做这一件事。我在这方面变得非常精通，因为对我来说，我有点把它看作是一场比赛。这里谁是最好的数据中心技术员？他们的指标是什么样的？我该如何超越他们的指标？我想学习如何在这个数据中心做所有特定的事情，因为以前做老板时，你掌握的技能越多，赚的钱就越多。然后我开始每 3 到 6 个月就换一次工作，因为我只想探索一切，积累我的能力。算下来，我认为每次跳槽大约都有 25% 的加薪。当然，因为基数比较低，当时感觉可能没那么明显，但跳了几次之后，我的薪水就翻倍了。

### Google 数据中心的岁月与指标管理

**主持人**: Puppet 算是你职业生涯中的一个转折点。

<details>
<summary>Original English</summary>

**Host**: You know what and I would say the biggest inflection point in my career was there were two of them before I get into Puppet Labs.

</details>

**Kelsey Hightower**: 你知道吗，我会说我职业生涯中最大的转折点，在进入 Puppet Labs 之前有两个。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Okay.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: So you come from Google, you see this huge operations. There's hundreds of thousands of servers. The cables are perfect. They're immaculate.
Oh, by the way, can you help us imagine like what a data center back then looked like at Google and and what what did you do as as part of the job?

</details>

**Kelsey Hightower**: 从 Google 出来，你会看到这种庞大的运营规模。有成千上万台服务器。线缆布置得完美无瑕，一尘不染。

**主持人**: 哦，顺便问一下，你能帮我们想象一下当时 Google 的数据中心是什么样子的吗？你在工作中主要负责什么？

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. So in 200 maybe four maybe 2005 that data center is like a warehouse. I mean it's huge. So think about a place where and I'm pretty sure they always exaggerated the numbers. So exaggerated number to think about is like think about 200,000 servers in one place. Everything is immaculate. So a lot of people have worked in data centers and it's a mess. Wires are all over the place. You know you're ad hoc adding and removing servers. But Google was systematic. Those machines came off a truck. They were wrapped perfectly. When you wheeled them into their spot, you connected the network cables, they would pixie boot. They would burn in. So part of the job was, you know, you walked around with a crash cart. So depending on what your abilities were, some people had pretty straightforward jobs. You had a crash cart, had all your tools on it, and you would walk around and you would find machines that were needing of repair. So if you have 200,000 machines, it's okay if like 300 of them are broken, right? the system can route around that. And but if they were broken, they needed to be repaired. So you would go to rack a server 7, you will pull it out and you will look at it and oh yeah, the SATA card is on fire. Like it's literally burned. It's burning. It was burnt. And so he's like, I can diagnose this one with my eyes. It needs to replace the SATA card. But the thing is, you would go into the system and you would say, this SATA controller needs to be replaced. So you would be making your prediction and then you would replace it and you would go through its burn-in process. It would join back to the fleet and then the way you were measured was how good were your predictions.

</details>

**Kelsey Hightower**: 大概在 2004 或是 2005 年的时候，那个数据中心就像一个巨大的仓库。太大了。想象一下一个拥有比如 20 万台服务器（他们可能夸大了这个数字，但想象一下 20 万台）的地方。一切都完美无缺。许多人都在数据中心工作过，那里往往一团糟。线缆到处都是，你是临时在添加和移除服务器。但 Google 是系统化的。那些机器从卡车上卸下来时，包装得完美无瑕。当你把它们推到指定位置，接上网线，它们就会进行 PXE 网络引导（PXE boot），然后进行烤机测试（burn-in）。所以部分工作是推着一辆应急小车（crash cart）四处走动。根据你的能力，有些人的工作相当直接。你的推车上装有所有工具，你四处走动，找出需要维修的机器。如果有 20 万台机器，坏了 300 台没关系，系统可以绕过它们。但如果它们坏了，就需要修好。所以你会走到机架 7 的服务器前，把它拉出来看。哦，SATA 控制卡着火了，真的是烧焦了。你能用肉眼直接诊断：需要更换 SATA 卡。但问题是，你必须在系统里记录：“这个 SATA 控制器需要更换。”你做出判断，然后更换它，它会经历烤机测试流程，重新加入集群。而考核你的标准是：你的诊断判断有多准确。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Oh,
right. So you said it's a SATA controller and to me moving fast you look as if I think that SATA controller I'm not going to waste any more time on this one because I'm trying to get my numbers up. So I just swap the SATA controller. You bring in all the cables, you slide it back, it goes through his process, and you move on to the next machine

</details>

**主持人**: 哦！

**Kelsey Hightower**: 对。你说是 SATA 控制器，对于想要追求速度的我来说，既然我认定是 SATA 控制器，我就不想在这台机器上浪费更多时间了，因为我要提高我的维修数量指标。所以我就直接把 SATA 控制器换了，接好所有的线，把它推回去，让它走自己的流程，然后我立刻转向下一台机器。

<details>
<summary>Original English</summary>

**Host**: before you get the feedback.

</details>

**主持人**: 在你收到测试反馈之前。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. And fun fact, there's a guy named Tim Hawk is very popular in the Kubernetes community. He's like the network lead. So back then, Tim Hawkins is working at the other side of Google, like the bigger side of Google. And one of his first projects was built a little tool that you would put on the motherboard. It had about nine lights on it, and the lights would flash back and forth, and it would tell you what dim slots were potentially bad. The technicians that were fast, they didn't waste time like running a program to do a extensive test of the memory. You learn how to use this little device and you would walk up to the motherboard. So the thing I would do is like before I do anything, put this on the motherboard, get the reading, and I learned to trust it over time, dim one, dim two are bad. And the goal would be all right, I have all this memory on my cart. You swatch those two dim slots. Make sure that that's done first. Reboot the machine. And you might be like, I think that's the only thing wrong. And again, you were put in the system. I believe I only need to do DIM one and two. And then the way you were measured is how long before that machine gets kicked back to repair. So if it doesn't get kicked back within, I don't know, 30, 60 days, you did a good job. If you didn't, your scores would be low. So for the technicians that were just reckless, right? They wouldn't even try and you're just swapping the wrong part. You're swapping the wrong hard drive. And so your stuff is always coming back for repair. You were not efficient. So I got to the point where I can maintain high 90s but also repair let's call it three times more machines than other people. So lots of machines rate of return. And then I learned how to do the network switches. And then there's power audits where you're lifting up tiles from the floor and you're making sure that everything looks good. You got to be careful not to touch them because you could die. And so you learn everything about a data center like the service loop. You know you're running all this cat 5 cable and it has to have a perfect service loop. fiber runs on a different part of the rack, right? So you don't ever mix these things. So as a person still like I'm in my early 20s. I'm thinking this is how all data centers look. It's not the case. But it's it's crazy because just as I think back, you know, I was a manager before as well and of course a software engineer for a long time, but the way your performance was continuously measured and fed back to you and you were evaluated based on it. It feels way more strict, should I say, than you know like folks who work as software engineers including at Google. I mean the frequency, the expectations.

</details>

**Kelsey Hightower**: 是的。一件有趣的事，有一个叫 Tim Hockin 的人在 Kubernetes 社区非常受欢迎，他像是网络负责人。那时 Tim 在 Google 的另一侧工作（更大的那一侧）。他最早的项目之一是做了一个插在主板上的小工具，上面大约有 9 盏灯，灯会来回闪烁，告诉你哪些内存插槽（DIMM slots）可能有问题。追求速度的技术员不会浪费时间运行程序去进行彻底的内存测试。你学会了如何使用这个小设备，走到主板前插上。我通常会这么做：在做任何事之前，把它插在主板上，获取读数。随着时间的推移，我学会了信任它：“插槽 1 和插槽 2 坏了。”你的目标就是利用推车上的内存，迅速替换掉这两个插槽的内存，确保首先完成这一步，然后重启机器。你可能认为这就是唯一的问题了。同样，你在系统中记录：“我认为只需要处理 DIMM 1 和 2。”考核你的方式是：这台机器要过多久才会被再次打回维修。如果它在比如 30 天或 60 天内没有被打回，你就做得很棒。如果打回了，你的分数就会很低。所以，对于那些行事鲁莽的技术员来说，他们都不怎么去仔细测，换错零件，换错硬盘。他们的机器总是被打回维修，这样效率就不高。我后来达到了这样的水平：不仅能保持在 90 分以上的高分，而且修理的机器数量大概是其他人的三倍。也就是说，高产出、低返修率。后来我又学会了处理网络交换机。还有电力审计，你要掀开地板瓷砖，确保一切正常。你还得小心不要碰到某些东西，不然可能会触电身亡。所以你学到了关于数据中心的一切，比如维护环路（service loop）。你铺设所有的 Cat 5 网线，它必须有完美的维护环路。光纤走机架的另一部分，你永远不能把它们混在一起。所以，作为一个二十岁出头的年轻人，我当时以为所有的数据中心都是这样的。但其实并不是。不过这很疯狂，因为我现在回想起来，我以前也做过经理，当然做软件工程师的时间更长，但你当时的工作表现被持续衡量、反馈，并据此对你进行评估的方式。我得说，它感觉比作为软件工程师（包括在 Google）工作要严格得多。我的意思是那种评估频率和期望值。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: The reason why I didn't feel as bad as some of the metrics people are using now is because I felt like I can control the outcome. It didn't feel like it was a thing that was just a metric that didn't do anything. If I felt like my score was taking a hit and I was like, you know what, I am being a bit sloppy and how I'm diagnosing these machines. And I remember one time where I almost had my score dip below 90. I started writing additional shell scripts to starting combining different functions together. It's like, you know what? Can't be moving this fast. There's a way for me to diagnose multiple things of the machine at one time. And so, I would diagnose the Saturn array, all the hard drives while I'm doing the memory component. And then when it rebooted, I would just run the script one more time as I'm putting my cart back together to catch that one more thing. And once I started doing that, I can move as fast as I want it and the scores are right. So to me, when the scores actually match the things that you're doing, then it's a healthy feedback. And again, no one really talked about it unless you needed to talk about it. And so I kind of leveraged it for a personal thing. I pulled it up in the morning. I kind of looked at my performance metrics and in many ways I calibrated my strategy based on this detailed feedback that I was getting. So, I think I appreciated that level, that granularity back then because it felt like it was uh something that was helpful for me, not just my manager.

</details>

**Kelsey Hightower**: 我之所以不像现在很多人面对各种考核指标时感觉那么糟糕，是因为我觉得我能控制结果。它感觉不像是那种毫无意义的空洞指标。如果我觉得我的分数受到了影响，我会想，“你知道吗，我在诊断这些机器时有点马虎了。”我记得有一次我的分数差点跌破 90，我开始编写额外的 Shell 脚本，把不同的功能组合在一起。我想：“不能只追求快，我得有办法一次诊断出机器的多个问题。”所以，我在处理内存组件的同时，也会诊断 SATA 阵列和所有硬盘。然后当它重启时，在我整理手推车的时候，我只需再运行一次脚本来捕获可能的最后一个问题。一旦我开始这样做，我就可以随心所欲地快，而且分数也能保持住。所以对我来说，当分数真正反映了你所做的事情时，这就是一种健康的反馈。而且，除非有必要，没人会真的拿这事儿来找你谈话。所以我某种程度上把它变成了我个人的工具。我早上打开系统，看看我的绩效指标，在很多方面，我根据我得到的这种详细反馈来校准我的策略。所以，我想我当时很欣赏那种粒度的反馈水平，因为感觉它是对我有帮助的东西，而不仅仅是为了方便经理。

### 走向自动化：Peer 1 托管与金融服务公司

**主持人**: 你提到过你有两个可以说是非常大的转折点。其中一个是...

<details>
<summary>Original English</summary>

**Host**: And you said you had two two kind of big big inflection points. One of them was

</details>

**Kelsey Hightower**: Google 是一个很大的转折点。当然，这要归功于我的创业经历。当我进入虚拟主机（Web Hosting）行业时，我去了一家名叫 Peer 1 的公司。他们是 Rackspace 的一家衍生公司，他们的核心理念就是全自动化自托管。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Google was a big one. Like that was definitely one of course my entrepreneurship. And when I got to web hosting, I went to a company called Pier 1. They're a spin-off of Rackspace and they were all about fully automated self-hosting, right? So,

</details>

**主持人**: 这是在大概 2005、06、07 年左右吗？

<details>
<summary>Original English</summary>

**Host**: this was back in like what 2005 67?

</details>

**Kelsey Hightower**: 是的，大概是 2005 年、2006 年。哦，那已经是他们主打的方向了。他们的口号是“延迟致命”（Latency Kills）。所以在那个时候你上网，许多客户群体都是自己托管游戏服务器的人。如果你想玩游戏，一种方式是托管一个游戏服务器，但你需要一个多人能访问的服务器。你就会去 Server Beach，它是 Rackspace 剥离出来的业务。Rackspace 更像是：“我们买台服务器，给你之后需要很多手动步骤。”而 Server Beach 的理念是：“让我们把一切都自动化。”机器会 PXE 启动，一些 PHP 脚本会运行。如果你订购了 RAID 配置，我们会在机器网络启动时配置 RAID，然后把你放在所属的 VLAN 上。我们会根据你的订单安装合适的操作系统，而我们只是通过一个表单走完所有这些步骤。整个过程大概需要一个小时。完成后，你就有了一个 IP 地址、登录凭据，如果你还需要电子邮件加上网站管理等所有这些东西，你都能拥有。当你用完后退还回来，我们再把它放回资源池，为下一个客户做好准备。所以当我看到我们是如何做到这一点时，我惊叹道：“哟，这也行！你可以端到端地自动化一切。”这里还有一点很重要，我们甚至在为 RAID 控制器更新固件。因为一旦你对一台服务器进行了 PXE 启动，你就在内存中了，你可以访问所有的硬件。你还没有提交给操作系统，但你有足够的能力做任何你想做的事。如果你想配置 RAID 控制器（那时还没有清晰的 API），我们真的是在运行 Curl 脚本和命令行工具试图让这台机器达到正确的状态，完成后我们再把它放入机群。所以在那个年纪，我就觉得：“哦，没有什么自动化是你做不到的。”当我们当时必须自动化 Windows 2000 服务器时，我们只是构建了能够抓取屏幕、登录到 Active Directory 的工具，然后抓取鼠标移动的动作，这样我们就能在那些 Windows 服务器上给软件打补丁。所以像“我需要一个特定工具来做这件事”的概念是不存在的，当时的想法就是：“你需要用尽一切必要手段。”因为这些人每个月只付 99 美元。当某个随机客户打电话来时，我没有时间让你花整整一个星期去弄。你不知道他们的设置，不知道他们的基础设施架构，你只有几分钟时间让他们重新上线。所以每个人都学会了快速行动。没有抱怨，拿到那个工单，解决它就是你的责任。也许你会向队友寻求帮助。所以我学会了如何快速行动。但真正的转折点来源于我是从技术支持开始那份工作的。人们会打电话说我的 SQL 无法工作，DNS 无法工作。他们有时甚至无法描述到底什么无法工作。我发现我们都在电话队列里。电话一响，它就会在大家之间轮流分配。然后如果你不能够快速解决，或者根本解决不了，你就建一个工单。工单就停留在那里，理想情况下你稍后会去处理它，但工单队列变得越来越长。当交接班发生时，我们只是积压了所有这些工单。当然，客户现在很生气，因为三天都没有回复。所以有一天我说，听着，我不准备登录到电话队列里去了。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah, this is like Yeah. 2005, 2006. Oh, they were already about that was their thing. Their tagline was latency kills. And so back then you would go online. A lot of the customer base was like um people hosting their own game servers, right? So if you wanted to play a game, one thing you could do back then is host a game server, but you needed a game server that multiple people could hit. And so you would go along to server beach. So this is a spin out of Rackspace. So Rackspace is more like, you know, we'll buy a server and once you get it and it's a lot of manual steps. Rackspace was more of a let's automated everything. So the machine would pixie some PHP scripts would run. If you ordered a RAID setup, then we would configure the RAID while the machine was net booted and then we would put you on the VLAN that you belonged on. We would install the right operating system based on what you've ordered and we just took a form. We just went through all of these steps and then when we were done, and it took maybe about an hour. When we were done, you had an IP address, login credentials, and if you wanted email and plus, you know, website management, all these things, you got it. And when you were done, you gave it back and then we put it back into the pool ready for the next customer. And so when I saw how we were doing that, I was like, yo, this is okay. You can automate things end to end. And the other thing that was important here, we were doing things like updating the firmware for RAID controllers because once you pixie a server, now you're in memory and you have access to all the hardware. You haven't committed to an operating system yet, but you have enough to do whatever you want. So if you want to configure the RAID controller and back then there wasn't like clean APIs. We were literally running curl scripts and command line utilities trying to get this machine into the right shape and then when we were done we would put it into the fleet. So at that early age I'm like oh there is nothing you cannot do. When we had to automate the Windows 2000 servers back then we would just build tools that would literally screen scrape log in to active directory and then we would screen scrape mouse movements so that way we can patch software on those Windows servers. So the concept of like I need a specific tool to do it's like no. Back then it was like you do whatever is necessary because these people are only paying like $99 a month. I don't have time for you to spend a whole week when they call random customer. You don't know their setup. You don't know their infrastructure. You have minutes to get them back online. So everybody learned to move quickly. No complaining. When you get that ticket it's on you to figure it out. Maybe you lean to your teammates for help. So I kind of learned how to move fast. But the the inflection point came from I started that job in tech support. So people would call my SQL isn't working, DNS isn't working. They can't even describe what isn't working sometimes. And so I realized that we were all in the phone queue. When the phone would ring, it would just round robin between everyone. Then if you couldn't solve it fast enough or you couldn't solve it at all, you created a ticket. And the ticket sat there and then ideally you get to it later, but the ticket queue was just getting long. And when a shift change happened, we just had all these tickets piling up. And of course, customers are now mad, 3 days, no response. So one day I said, look, I'm just not going to log in the queue.

</details>

**Kelsey Hightower**: 我打算只解决工单。我重新回到了那种企业家的思维状态，编写了一些小脚本来处理工单。我看到了问题：这是个 SQL 问题，我们需要清理数据库。这很简单，运行这个脚本。工单关闭。嘿，先生，一切都搞定了，请再试一次。关闭。这根本不是个问题。关闭。哦，我们需要升级 PHP。关闭。然后整天的工单队列都保持为零，空空如也。然后有人说：“嘿，Kelsey 没登录电话队列。他根本没在接电话。”我的经理把我叫到办公室，说：“嘿，Kelsey，你为什么没在电话队列里？”我说：“因为我们不需要所有人都接电话。我们只需一个人就能让工单队列保持为零。”然后我告诉同事们：“听着，如果你们不能快速解决问题，直接快速开个工单就好，我会处理的。”有些人专门搞 Windows，他们接到一个 Linux 问题的电话，不知道该怎么办。我说：“别担心，赶紧把它扔到队列里，继续接下一个电话。有我呢。”所以我变得超级高效。我把这个流程解释给经理听，他思考了一下。他叫 Mike，他说：“嗯，我喜欢这个主意。我们要改变流程。我们会让几个人不接电话，但前提是工单队列必须保持为零。”那是我第一次学到“活动”（Activity）和“影响”（Impact）的区别。活动是你在疯狂接电话，做个“全明星”，但团队的工单队列依然很长。你做出这种跳跃，说“听着，我也许不去接电话，但我对同事的承诺是‘影响’”，工单队列保持为零。所以在周三我们进行团队交接时，我们移交的是一个空的队列。当然，我没有把这套方法教给下一班的人，因为我没想那么多。所以当我们回来时，队列又爆满了。你会觉得：“哇，你们这些人又把一堆包袱甩给我们团队了。”当然，我们会把它清理干净，但后来管理团队说：“哟，每个人都要这么做。”然后我感叹：“天哪，你真的可以改变流程。”所以那是一个巨大的转折点。我认为下一个转折点更多的是关于成为一个成熟的人。不要再那么频繁地跳槽了，因为，经过几次晋升和产生一些影响后，我又准备去下一个地方了。很多时候我不需要与那些决策带来的后果长期共存，也没有待足够长的时间去真正影响更多文化。所以当我进入金融服务行业时，那是我第一次受到各种限制。因为在这些（互联网）公司里，一切都是为了快速行动。在 Google，我们必须快速行动，我们必须与大公司竞争，我们将用便宜的硬件、聪明的人才、任何必要的手段来做到这一点。Web 托管业务利润微薄，你必须快。但在金融服务公司，规矩是：“不，我们是在这里赚钱的。”

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I'm just going to resolve the tickets. And I'm back in that entrepreneurial mindset. I'm building little scripts to take a ticket. I see the issue. This is my SQL issue. We need to vacuum the database. This is easy. Run that one. Ticket close. Hey sir, everything is good to go. Please try again. Close. This is not even an issue. Close. Plus, oh, we got upgrade PHP. close and then the ticket queue is zero. It's just empty all day. And so someone's like, "Hey, Kelsey's not logged into the phone queue. He's not even on the phone. He's not taking calls." My manager pulls me in the office like, "Hey, Kelsey, why are you not on the phone queue?" I said, "Because we don't all need to be on the phone queue. We can just have one person making the ticket queue stay at zero." And then I would tell my colleagues, "Hey, look, if you can't figure it out fast, just open a ticket super quickly. I will take care of it." So some people specialize in Windows. They got a Linus call. They didn't know what to do. I said, "Don't worry about it. Just put it in the queue quickly. Move on to the next call. I got you." And so I became super efficient. So I explained this process to the manager and he thought about it. His name is Mike. And Mike was like, "Yeah, I like that. We're going to change it. We're going to have a couple people stay out of the queue, but the promise is that queue has to stay zero." And it's the first time I learned the difference between activities and impact. activity is you being an all-star answering a bunch of calls, but the ticket queue for the team is still high. You making this jump and saying, "Look, maybe I stay out of the queue and my promise to my colleagues is impact." The ticket queue is zero. So on Wednesday when we do the team turnover, we're handing off a empty queue. Now, of course, I didn't teach them that because I didn't think about it. And when we would come in, the queue would be high again. And it's like, yo, whoa, this is not you guys keep handing off a bunch of burden to our team. And of course, we would clean it up, but then the management team was like, yo, everybody's going to do it. And then I was like, man, you can change the process. So that was like the huge inflection point. I think the next one was more about being a mature person. Stop job hopping so much because again, after maybe a few promotions and some impact, I'm now off to the next thing. and I didn't have to necessarily live a long time with some of those decisions or you know stay long enough to really impact more of the culture. So when I got to financial services, it was the first time I got restrictions put on me, right? Because in these companies, everything is about moving fast. Google, we got to move fast. We have to compete with the big guys. We're going to do with cheap hardware, smart people, any means necessary. Web hosting, we're not charging a lot. Margins are thin. You got to move quick. Financial service like, no, we making money over here.

</details>

**主持人**: 所以你加入了一家金融服务公司。

<details>
<summary>Original English</summary>

**Host**: You joined the financial services company.

</details>

**Kelsey Hightower**: 是的。那也是我薪水第一次翻倍的时候。我是趁着午休时间去面试的。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. So that was the first time my my salary doubled. So I went on my lunch break for a job interview.

</details>

**主持人**: 那感觉一定很棒。

<details>
<summary>Original English</summary>

**Host**: That must have felt awesome.

</details>

**Kelsey Hightower**: 哦天哪，我不记得了。我的经理当时非常生气，因为我是午休时间溜出去的。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Oh my god. I don't remember. My manager was so upset. I went on a lunch break.

</details>

**主持人**: 你是说前任经理，那个你...

<details>
<summary>Original English</summary>

**Host**: The previous manager, the one you

</details>

**Kelsey Hightower**: 我是在 Peer 1 遇到他的。他是我很好的朋友，名叫 Joe Rodriguez。他是第一个让我成为软件开发人员的人。所以，我给他展示了一些我关于基础设施虚拟化现代化、优化 PXE 启动过程的想法。他说：“伙计，你有很多好主意。”所以在面试中（这里指的是早些时候在 Peer 1 内部的面试），他说：“展示给我看你都建了些什么。”我当时太兴奋了，我仍然带着企业家的思维，所以我拿到了那份工作。现在，我是一名从事自动化堆栈开发的软件工程师了。我记得后来我看到了一些 5 年前让我感到害怕的职位招聘，那些甚至让我只想去拿个 A+ 认证、开个电脑店而不是尝试去应聘的职位。我再次查看了那些职位描述，上面写着你需要 Linux。我当时想，我在那份工作期间甚至拿到了红帽认证（Red Hat certified），对吧？所以我心想我现在已经具备了所有的资格。我记得那个（金融公司的）职位，在去之前我并不知道薪水是多少，但你必须穿衬衫和打领带。那是我这辈子第一次需要穿衬衫打领带。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I met Pier One. He was a good friend of mine named Joe Rodriguez. He's the first person that made me a software developer. So, I showed him some ideas I had on like modernizing our virtualization, uh, optimizing our Pixie Boot process. And he was like, "Man, you have a lot of good ideas." So, in the interview, he's like, "Show me what you built." And I'm so excited. I'm still that entrepreneur thinking, and I got the job. So now I'm a software engineer working on this automation stack. And uh I remember seeing jobs that I used to be afraid of 5 years ago. The same jobs that made me want to just go get an A+ certification and open a computer store instead of even trying. And so I looked at those job descriptions again and it was like you need Linux. So like I got that even at that job I got Red Hat certified, right? So I was like I got all the qualifications now. And I remember the job. I didn't know how much it paid before I went, but you had to wear a shirt and tie. It was the first time in my whole life had to wear a shirt and tie.

</details>

**主持人**: 哦，所以你还专门去买了一条领带。

<details>
<summary>Original English</summary>

**Host**: Oh, so you had to go and buy one.

</details>

**Kelsey Hightower**: 是的。我记得我的家庭老师，她帮我改了裤子边。我说：“嘿，我有个面试，我知道，这身看起来合适吗？”我趁着午休时间开车过去，到了那里，你知道，这是大企业环境。我心想：“哇，这才是这才是大联盟。”我以前甚至没觉得 Google 是大联盟。我认为金融服务才是大联盟。显然，如果你的工作需要打领带，那你一定在做一件非常严肃的事情，以至于需要穿衬衫和领带。所以，我开始面试，紧张得直冒汗，想着“他们会问我一些我可能从未听说过或见过的东西吗？”他们开始问 Linux 方面的问题。我心里嘀咕：“不对，你得用这个标志。那不是正确的标志。不，查一下。那不是正确的标志。你不能用 grep 这么干。不，你必须这样通过管道。那个版本 Linux 里的 PS 表不显示那个。那个 curl 命令不行。”我觉得这太简单了。我的一部分内心在想，要么我是真的很厉害，要么就是有别的原因。所以我心想，这可能还有下一轮面试。所以我在开车回家的路上，松开领带，给我妻子打电话说：“嘿，我觉得我表现得非常棒。”这已经成为一种模式了：我在某方面变强了，然后我找到一份更好的工作。我在某方面变强了，我找到一份更好的工作。但现在，感觉这像是一份真正的“职业”。然后我正和妻子通电话，我说：“嘿，我得先挂了。”是招聘人员打来的。“嘿，你有空吗？100% 有空。他们想给你发 Offer。”我当时想，给我发 Offer？这可不太一样，通常他们只会告诉你这个职位薪水是多少。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. And I remember my home teacher, she him my pants for me, right? I was like, "Hey, I got a job interview. I know. Does this look right?" I'm driving up on my lunch break and I get there and you know, this is enterprise. I'm like, "Wow, this is this is the big league." I didn't even think Google was big league. I thought financial services big league. Obviously, if you have to wear a tie to do your job, you must be doing something so serious that you need a shirt and tie to do it. And so, I get to the interview and I'm sweating like, "What? They're going to ask me stuff that I've probably never heard of or seen before." And they started asking Linux questions. I'm like, "No, you got to use this flag. That's not the right flag." No, look it up. That is not the right flag. You can't do that with Grip. Nope. You got to pipe it this way. That the PS table doesn't show you that. Not on that version of Linux. not with that curl. And I'm like, it's too easy. And part of me is like, either I'm really good or something else. And so I'm thinking like, yo, that was maybe there's another round. And so I'm driving home and I'm loosening up the tie and I'm calling my wife like, "Hey, I I think I did a really great job." Like, you know, I think and and this has been a pattern, you know, I get good at something and I find a better job. I got good at something, I find a better job. But now it's like this is like a career. And so I'm talking to my wife and I was like, "Hey, I got to call you back." And it's the recruiter calling. Hey, you have a second? It's like 100%. Uh they want to make you an offer. I'm like, you know, make you an offer is different. Like it's usually this is how much the job pays.

</details>

**主持人**: 在那之前一直是那样。你当时赚多少钱？

<details>
<summary>Original English</summary>

**Host**: That's how it was until then. How much were you making?

</details>

**Kelsey Hightower**: 4万5千美元。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: 45K.

</details>

**主持人**: 所以你当时赚 4.5 万。

<details>
<summary>Original English</summary>

**Host**: So you were making 45K at that point.

</details>

**Kelsey Hightower**: （新 Offer 是）9万美元。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: $90,000.

</details>

**主持人**: 哇。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kelsey Hightower**: 我激动得差点把车开出公路。像……双倍。这太疯狂了。我在想 9 万，你开始算退休账了，我们可以买套房了，你想着所有这些你能做的事情。我在回去上班的路上，我记得他们问：“那你什么时候能开始？”今天是周四，我告诉他们我们周一就能开始。根本不管什么两周离职通知。我当时想我可管不了那么多，这可是翻倍啊！所以我记得我给 Joe 打了电话。Joe 在圣安东尼奥，那里是 Rackspace 的总部。我说：“嘿，Joe 哥们。我得辞职了。”他说：“什么？你团队干得这么好，你怎么能辞掉我？我可是把赌注押在你身上了。”我说：“嘿，Joe，冷静点兄弟。他们给 9 万。”他立刻说：“什么？他们还招人吗？”后来我去了那家公司，Total Systems, TSYS。最初感觉确实有点慢，他们有运行手册，有变更窗口，一切都受到监管。这是一家金融机构，我们在处理信用卡支付，我们在为政府做工作。我记得当时团队里每个人的节奏都是这样慢。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I almost drove off the rope. like n like double. This is insane. I'm thinking 90 and you're doing the you know retirement calculations. We can buy a house. You you're thinking of all of these things that you could do. And so I'm on the way back to the job and I remember and they were like then when can you start? It's like Thursday. I'm telling them we can start Monday. Like uh two week notice. I'm like I don't know man. Like it's devil
for this.
I have to. So, I remember I called Joe and Joe's based in San Antonio where the headquarters of Rackspace was. I was like, "Hey, Joe, man. Hey, man. I got to I got to I got to quit." He was like, "What, man? You just, you know what I'm saying? You're doing so well on the team. How you going to quit on me? I made a bet on you." You know? I said, "Hey, Joe, calm down, bro. They pay 90K." He's like, "What? Are they hiring?" And so, I got to I got to that company, Total Systems, Tus. And um it did feel a bit slow. They had run books, change windows, everything was regulated. This is a financial institution. We're processing credit card payments. We're doing work for the government. We're doing all of these things. And I remember the team was just everybody just moving at this pace.

</details>

**主持人**: 但是当你真正进入那里时，这种感觉难道不疯狂吗？当我搬到伦敦时，我有过类似的经历，我的薪水比在爱丁堡时翻了一倍多，在那里因为拿了这么多钱，别人对你有很多期望；还有打领带的经历也一样。然后稍微有些失望。当时你有没有稍微觉得：“我是不是漏掉了什么？这工作应该更高级才对，面试的时候可能不那么难，但是……”

<details>
<summary>Original English</summary>

**Host**: But isn't it crazy when you get in there? I I had something similar when I moved into London and my salary more than doubled going for Edinburgh where you have all these expectations because you're being paid so much more. the tie. Same thing for me for the tie and then it's a bit disappointing and I think did you not not feel a little bit like am I missing something like this should be you know higher this should be you know the interview was okay maybe not as hard but it it was something I mean I did because I was naive because I didn't understand the consequences of a mistake and so yeah I was like oh these people are just moving slow and I looked at what they were doing and everything was like a risk if you made a mistake you remember you only get seven milliseconds, 7 seconds to give Visa a response. If you don't, then it's a default decline. Now everybody's losing money. And so the cost of getting a good change, it was just worth waiting. So I didn't know that in the beginning. So I'm just like, oh, everybody's moving a little too slow. I was seeing how they were doing deployments. I'm watching how they're provisioning servers. I'm like, you know, you can automate this whole thing cuz I've done it multiple times. And then I learned to be a little bit patient. All right, hold on. I learned how to deal with the nose. I learned how to deal with the executives. I learned how to talk not just to engineers with the senior leaders and get their trust. And I won't talk about everything that I did there, but I was there for about three years. So the job hopping stops and I remember there was a task where we were using Apache and some Java plugin to talk to our J Boss instances. And so they were using a lot of memory per connection on the load balancer. And so we got a new we're moving off the main frame. We're moving into this new, you know, Java world and the servers just kept falling over. We couldn't handle all the transactions and I'm just watching the team go into these change windows and then we fail. We would fail. We would fail. And the CTO at the time was like, you know, this is costing us money. These we're getting chargebacks. We're having to pay out penalties. And I was like, I had a dev environment when I was using EngineX. I got rid of all this Java stuff. Like it's it's just HTTP. You don't need a Java connector thing. I'm reading the spec. You don't need it. And my memory usage is a fraction

</details>

**Kelsey Hightower**: 我的确有过这种想法，因为我很天真，不了解犯错的后果。所以我当时觉得：“哦，这些人只是动作太慢了。”我看着他们在做的事情，每一个操作都充满了风险。如果你犯了错，要记住，你只有 7 毫秒（或者 7 秒）的时间给 Visa 一个响应。如果没做到，就是默认拒绝交易。那所有人都在亏钱。所以进行一次高质量变更所付出的代价，是值得等待的。一开始我并不知道这些。我只是觉得：“哦，大家动作都有点太慢了。”我看着他们是如何部署的，看着他们是如何配置服务器的。我心里想：“你知道，你可以把这整个过程自动化，因为我已经做过很多次了。”但后来我学会了多一点耐心。好了，等一下。我学会了如何处理别人的拒绝（No）。我学会了如何与高管打交道。我学会了如何不仅仅和工程师沟通，而是和高级领导沟通并赢得他们的信任。我不会详谈我在那里做的所有事，但我在那儿待了大概三年。频繁跳槽的日子结束了。我记得有一项任务，我们正在使用 Apache 和一些 Java 插件来与我们的 JBoss 实例通信。他们在负载均衡器上每个连接消耗了大量内存。当时我们正在从大型机迁移到这个新的 Java 世界，但服务器总是崩溃倒下。我们无法处理所有的交易。我看着团队进入这些变更窗口，然后失败，一次又一次地失败。当时的 CTO 说：“你知道，这在让我们亏钱。我们遭遇了拒付，我们必须支付罚金。”我说：“我在使用 **Nginx** 时有一个开发环境，我摆脱了所有这些 Java 相关的配置。那只是 HTTP，你不需要什么 Java 连接器之类的东西，我读过规范，根本不需要。”而我的内存使用率只有原来的一小部分。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: by getting rid of it.

</details>

**主持人**: 通过去掉它做到的。

<details>
<summary>Original English</summary>

**Host**: Yeah, you don't need it. And engineext had a better threading model, all these things. And I was like, I got a perfect config. I've ported the Apache config to this one. I even handle all of our redirects, all of our routes, all the legacy crust. This thing will work. It's like, I don't know, Kel, this is not certified stuff. It's like, no, no, no. I got it from Red Hat. RPM install engine X. It's in it's in Red Hat. And they're like, okay, it's in Red Hat. Okay, sure. gave me one chance.

</details>

**Kelsey Hightower**: 是的，你不需要它。而且 Nginx 有更好的线程模型之类的优势。我说：“我有一套完美的配置。我已经把 Apache 的配置移植过来了。我甚至处理了我们所有的重定向、所有的路由，还有所有残留的历史包袱。这东西绝对能行。”他们说：“我不知道啊，Kel，这不是经过（官方架构）认证的东西。”我说：“不不不，我从红帽（Red Hat）那里弄来的。RPM 安装 Nginx。它就在红帽官方库里。”他们说：“好吧，既然在红帽里，那就行。”他们给了我一次机会。大概过了一周，他们让我试一把，允许我在变更窗口里操作。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah.
And about after a week, they gave me a shot and they let me be in the change window. And

</details>

**主持人**: 变更窗口具体是什么？

<details>
<summary>Original English</summary>

**Host**: what what is the change window?

</details>

**Kelsey Hightower**: 在金融机构里，变更窗口通常意味着我们可以在午夜开始变更，并且必须在凌晨 6 点前完成。你必须通知每一个客户。我们要在环境中改变一些东西，事情可能会变得有点奇怪，我们希望得到您的许可。如果这是对您的业务可能造成不利影响的操作，现在就请提出来。在我们获得许可后，我们就有了一个时间窗口。那是你唯一的机会。如果你不能按时完成，你就必须关闭它，把系统恢复到原来的状态。你可以向前推进，如果不行就回滚。我记得当时我把 Nginx 部署上去了。到了这个时候，全靠你自己了，这家公司里没有人有 Nginx 的经验。而且，大多数人都不想做这个。他们觉得：“我们认为这是个坏主意。”所以现在你的声誉悬于一线，你不能躲在团队背后，所有人都在看着你：“看你的了。”幸运的是，领导层当时表态：“我们支持你，我们把自己的职业生涯也押在上面了。”虽说他们可能不会有事，但在大概两小时后，我让一切都运转起来了。我们眼看着内存压力直线下降。如果说之前（32G内存）占用率一直在 90%，每次都堆栈溢出导致一切崩溃，那么现在这个东西的内存占用稳定在 2G 左右。每个人都在问：“哟，我们现在有峰值负载吗？这是真的吗？”我们都坐在那儿，不太确定。以前我们测试平台的方法是，让人开车去加油站，拿张信用卡买点油，然后看看这笔交易是否落到了 Oracle 数据库里。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: So change window typically in the financial institution is like we can start changes at midnight and we have to be finished by 6:00 a.m. and you have to notify every customer. We're going to change something in the environment. Things may get a little weird. We would like your permission. And if if it's something that can be detrimental to your business, now's your time to speak up. So once we got permission, we had a window. That's the only window you got. And if you can't finish it on time, you got to shut it down and get us back to where we were.
Yeah. Roll back.
Roll back. Roll forward or if you could roll back. And I remember I put engine X in place. So at this point, it's all you. No one at this company has EngineX experience. Also, most people don't want to do this. They're like, "Hey, we think this is a bad idea." And so now it's your reputation on the line. There is no hiding behind the team. It's almost like everyone's sitting back like you got it. Now luckily the leadership was like we are supporting you and we're putting our careers on the line as well. I mean they probably would have been safe but after about 2 hours I got everything working and we just watched your memory pressure just drop. So if we were at 90% on utilize I don't let's call it 32 gigs and we're just blowing stack every time everything's crashing. this thing is hovering at like two gigs of RAM. And everyone's like, yo, like are we getting peak load? Is this legit? And we're all just sitting there like not sure. And the way we used to test the platform is we would someone would drive to the gas station, get a credit card, buy some gas, and we wanted to see the transaction land in the Oracle database.

</details>

**主持人**: 是的，你们可以追踪它。

<details>
<summary>Original English</summary>

**Host**: Yeah, you could track it.

</details>

**Kelsey Hightower**: 所以我们可以追踪整个流程。我们说：“天哪，成功了。”但问题是，直到第二天早上 10 点，你才能真正放心。那时已经是凌晨 3 点了。大家各回各家，但我没睡觉。我想：“我们在生产环境中改变了很大一部分基础设施，让我们看看情况。”早上 10 点过去了，我们四处查看，Nagios 警报没有响起。我说：“哥们，我们可能真的稳了。”你知道我的，我把 `top` 命令开着，看着内存使用量保持稳定。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: So we can track the whole thing. We're like, yo, it works. And so the thing is, you can't really be comfortable until about 10:00 the next day. So now it's 3:00 a.m. We all go home. I don't go to sleep. I'm like, "Yo, we've changed a big part of the infrastructure in production. Let's see." So 10:00 goes by and we looking around and there's no naggios alerts going off. I'm like, man, we might be we might be good. You know me, I got my I got top going. I'm looking like memory usage is holding steady.

</details>

**主持人**: 对于那些不知道的人来说，当你运行 `top` 命令时，它会在一个循环中显示 CPU 树。就像你运行 `ps aux` 命令一样，你能看到所有正在运行的进程。

<details>
<summary>Original English</summary>

**Host**: Yeah, top is uh for those who don't know that that's when you uh it shows it show the CPU PS tree in a loop, right? So just like if you ran the PS aux command, you see all the processes running processes.

</details>

**Kelsey Hightower**: 是的，你运行 `top`，它基本上就会根据你设定的时间（比如每秒）刷新一次。但我之前打过一个赌：如果我把这事搞定，你得请整个楼层吃一周的披萨，每天都要点新的。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: And so you just run top and then it's basically that every second being refreshed or whatever timer you give it. But one of the bets I made was if I get this to work, you have to buy pizza for the whole floor for a week. Every day we get a new order.

</details>

**主持人**: 因为他之前答应过：“Kelsey，如果你搞定这个，我请你吃牛排大餐。”

<details>
<summary>Original English</summary>

**Host**: And cuz he promised like Kelsey, if you get this to work, I'll buy you a steak dinner. And at the time I still am. I was vegetarian. I don't eat steak. But here's here's what I would like instead. you got to buy pizza for the whole floor. Now, I don't know how strategic I was thinking, but I figured that I could score some points with the whole team from turning it into a I succeeded to a we succeeded

</details>

**Kelsey Hightower**: 当时我还是素食主义者，我不吃牛排。但“我想要的是，你要给整个楼层买披萨。”我当时可能也没想多深远，但我觉得，通过把“我成功了”变成“我们成功了”，我能在整个团队那里赢得一些好感。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: and then people eating together was one good way of doing it. And I remember after it worked, he was like, "What's the order?"

</details>

**主持人**: 大家一起吃东西是个好方法。

<details>
<summary>Original English</summary>

**Host**: And I just ordered, you know, pizza from one place and we just put it in the middle. Everyone was like, "What's the pizza for?" Right? Cuz usually you only get this for special events, like for the thing we did. And the next day some more pizza and some more pizza. And so when I got that accomplishment, I was like, "Okay, this is what maturity looks like. It's not about just having the right solution. You literally have to get consensus, buy in, make sure and then your reputation's on the line." And I got that change in. It just kind of changed the way I thought about what success looked like. And so that was the inflection point. And then of course I brought puppet into that organization repeated a similar process of automating everything with this tool.

</details>

**Kelsey Hightower**: 事情成功后，他问：“要点什么？”我就点了一家店的披萨，然后把它放在中间。大家都问：“这披萨是庆祝什么的？”对吧？因为通常只有我们做了些特殊的项目才会有这种待遇。然后第二天又有披萨，后天还有。所以当我取得那个成就时，我心想：“好吧，这就是成熟的表现。这不仅仅是拥有正确的解决方案，你确实需要获得共识、获得认可，然后再把你的声誉押在上面。”我推行了那项变更。这在某种程度上改变了我对“什么是成功”的看法。所以那是一个转折点。当然，后来我把 Puppet 引入了那个组织，重复了类似的流程，用这个工具自动化了一切。

### 赞助商播报 (Buildkite & Sentry)
*注：因要求高保真翻译，以下保留原字幕中的播报内容。*

**主持人**: Kelsey 刚才谈到了 2010 年代 CI/CD 的面貌，以及当时向生产环境部署有多么困难，这正好自然过渡到我们本期节目的赞助商 Buildkite。那种手动部署的时代正是 **Buildkite** 创立的时期。工程组织当时都在努力想办法如何提高发布频率（超过每周一次），那些四处碰壁的人首先转向了 Buildkite。Shopify 在 2015 年开始使用 Buildkite。Airbnb、Canva、Uber 和 OpenAI 使用 Buildkite 都长达 7 到 12 年。在整个 2010 年代，全球软件领导者在行业内遇到的最棘手的 CI 问题，都在 Buildkite 流水线上得到了解决。这也正是 Buildkite 成为最能适应当前趋势的 CI 平台的原因。生成式 AI 的高吞吐量正在将每个人的构建队列推向极限。编码 Agents 正在以你默认配置所能承受的 5 倍、10 倍甚至 50 倍的数量提交代码。那个在 5 到 10 年前能支撑 Shopify 流量的同一套架构，现在正在处理来自 Anthropic、Cursor、Meta、Mistral、Cohere、VLM、xAI、Lambda 等等的一波又一波提交，他们都是 Buildkite 的客户。当其他 CI 工具在重压下崩溃时，Buildkite 每周运行着约 14 亿分钟的任务。Agent 可以运行在你的基础设施上，也可以运行在 Buildkite 上。每一个工件和日志都会被捕获，如果出了问题，你能立刻看到原因。如果你的现有 CI 达到了瓶颈，或者宕机问题越来越影响你的交付，请访问 buildkite.com/pragmatic 获取 30 天全功能试用，无需信用卡，还有一位名叫 Ola 的真实人类工程师随时待命，他非常乐于助人。

我还要提一下我们的季度赞助商 **Sentry**。AI Agent 并没有来自生产环境可观察性日志的反馈循环，但它们需要吗？我的意思是，我们肯定不想构建这样一个系统：每次生产环境报错后，AI Agent 就在无人监督的情况下自动向生产环境推送修复补丁。那将是引发灾难的配方。但是，如果我们做得更保守一点呢？当生产环境报错时，一个 Agent 结合来自 Sentry 的上下文来调查问题。毕竟 Sentry 已经包含了错误的所有上下文。Sentry 的 MCP（Model Context Protocol） 就是将 Sentry 接入支持 MCP 的 Agent 的一种方式。Claude Code、Cursor、Codex、VS Code、Copilot 它们都支持。一旦你连上 MCP 服务器，你就能做一些非常有用的事情。例如，当一个已解决的 Sentry 问题再次出现时，你可以触发 Cursor Agent 去调查回归原因，阅读相关代码，并打开一个包含建议修复的 PR。要让这一切跑起来需要一些工作：你需要将 Sentry 连接到你的代码库，向 Cursor 添加 Sentry MCP，为 Cursor 定义调查指令，配置触发自动化的条件，并测试一切正常。但一旦你配置好并运行起来，你就能更快地修复回归问题，同时你依然在审查每一项修复。对我来说，这似乎是对 AI、MCP 和 Sentry 非常合理且有用的使用方式。访问 sentry.io/pragmatic 了解 Sentry，今天就开始监控并修复回归问题。好，说到这里，让我们回到 Kelsey 的故事，听听他是如何将 Puppet 引入他的组织并自动化 DevOps 流程的。

<details>
<summary>Original English</summary>

**Host**: Kelsey just talked about what CI/CD looked like in the 2010s and how difficult deploying to prod was which leads us nicely to our episode sponsor build kite. This type of manual deploy era was a time of build kite was created. Injuring orgs were trying to figure out how to ship more frequently more than once a week and those running into wall first turned to build kite. Shopify started running on build kite in 2015. Airbnb, Canva, Uber, and OpenAI have all been using Built Kite for 7 to 12 years. Throughout the 2010s, the hardest CI problems in the industry for global software leaders were getting solved on Builk Kite pipelines. That's exactly what makes Built Kite the CI platform most in tune with what's happening right now. Genai throughut is pushing everyone's build queue to its limits. Coding agents are pushing commits 5, 10, 50 times volume that your defaults were built for. The same architecture that absorbed Shopify's traffic at scale five to 10 years ago now absorbs a shared push from Entropic, Cursor, Meta, Mistral, Coher, VLM, XAI, Lambda and more who are all Buildcad customers. Where other CIS are cracking under the weight, Builkcite is running about 1.4 billion job minutes a week. Agents run on your infrastructure or on build kites. Every artifact and log is captured and when something fails, you see the why immediately. If you're hitting ceilings on your existing CI or downtime is becoming more problematic for your delivery, head to builkite.com/pragmatic 30-day all access trial, no credit card, and an actual human engineer on the standby. His name is Ola, and he is very helpful. I'd also like to mention our season sponsor, Sentry. AI agents don't have a feedback loop from production observability logs, but should they have it? I mean, we probably don't want to build a system where after each production error, AI agents automatically push out a fix into production without supervision. That would be a recipe for disaster. But what if we did something more modest? When a production error fires, an agent investigates this with context from Sentry. Sentry already has all the context in the error. After all, Sentry MCP is one way to plug in Sentry to agents that support the model context protocol. Cloud Code, Cursor, Codeex, VS Code, Copilot, they all do. After you hook up the MCP server, you can do some very useful things. For example, you could do this when an already resolved century issue resurfaces. You can kick off a cursor agent to investigate the regression, read the relevant code, and open a PR with a suggested fix. There's a little work involved to get all of this going. You need to connect Sentry to your code repository, add Sentry MCP to Cursor, define the instructions for Cursor's agent to investigate, configure the trigger that launches the automation, and test that it all works. But once you have it up and running, you can get regressions fixed faster whilst you're reviewing every and all fixes. This feels like a sensible and helpful use of AI and CP and Sentry to me. Check out Sentry at centry.io/pragmatic and start monitoring and fixing regressions today. And with this, let's get back to Kelsey and when he introduced Puppet into his organization and automated DevOps processes.

</details>

### 拥抱自动化：从 Jira 驱动 Puppet 到加入 Puppet Labs

**Kelsey Hightower**: 我记得有个人从 Puppet 过来拜访……

<details>
<summary>Original English</summary>

**Kelsey Hightower**: And I remember we had someone from Puppet come by

</details>

**主持人**: 为了给不了解的人解释一下，Puppet 是一个配置管理工具，对吗？

<details>
<summary>Original English</summary>

**Host**: and and just for again those who don't know Puppet, Puppet is this
configuration management tool.

</details>

**Kelsey Hightower**: Puppet 是这样一种存在：过去我们有大量随机运行的 Shell 脚本，做着一些“伪自动化”，但大多数时候你还是得手动操作。来了一个工单，有人想要在服务器上配置一个新的 SSH 密钥，有人想要安装软件，你就手动去做，然后把输出结果复制粘贴到工单里，关掉工单，第二天再重复同样的动作。这就是为什么我会说：“有些做 IT 的人不是有 20 年经验，而是把 1 年经验用了 20 年。”他们从未实现向自动化跨越，也没有学习新工具或新技能。所以当时我看到了改变的契机：“天哪，我可以引入一个工具。”我引入了 Puppet，当时版本是 0.24.8。那时 DevOps 甚至还没成为一个专有名词。我开始学习像给 Java 生产环境写代码那样写代码，用 Puppet 的 DSL 编写 Puppet 清单文件，有时还需要写点 Ruby 代码来构建新的资源类型。我也开始接触开源，比如“嘿，上游有个东西坏了，我要给上游贡献代码。”我一直在幕后做所有这些工作，为我的“第二幕”做准备。

有一天，我的经理去参加了一个会议，回来后他说：“嘿，Kelsey，我终于知道你在搞什么了。”我问：“是什么？”他说：“你在做 DevOps。”我心里其实有点不爽：“凭什么别人来定义我在做的事？”然后大家都开始谈论 DevOps，他说：“我遇到了一个叫 James Turnbull 的人。”James 是个澳大利亚人，在 Puppet Labs 工作，他写了第一本关于 Puppet 的书，那本书我不仅买了而且读过。我惊呼：“James Turnbull？这名字听起来好耳熟。哦！”我看了看桌上的书，是他是他。原来 James 那个时候写了很多技术书籍。经理说他要来我们办公室。我心想：“哇，世界级的专家要来了。”那时候，我已经把 Puppet 隐藏在了 Jira 工单后面。你可以直接开一个 Jira 工单，我为所有东西都制作了 RPM 包。你从下拉菜单里选择你想要的 RPM，选择你所在的环境。然后魔法发生，结果就出来了。大多数人甚至不知道 Puppet 的存在，他们从来不需要碰它，他们只知道他们可以按需获取任何东西。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: So puppet is we went from you know lots of shell scripts you know doing random things and pseudo automation but most of the time you just did a manual thing you had a ticket come in someone wanted a new SSH key on a server someone want something installed you did it manually copied and paste the output in the ticket and you closed it and you did that every day over and over again and that's where the saying that I I say sometimes some people have 20 years of one year experience some people in it have been doing that 20 years on the row they never the leap to automation or learning new tools or skills. And so I saw like man I can bring in a tool and I brought the tool called puppet at the time 0248 and this is right before DevOps becomes a word but it's like all right I'm starting to learn how to write code like the for the Java production stuff. I'm writing puppet, you know, manifest using the puppet DSL. Sometimes you have to write a little bit of Ruby to build a new resource type and I'm contributing and also I get introduced to open source like, hey, there's something there that doesn't work. I'm going to contributed upstream. So, I'm doing all this behind the scenes getting ready for act two. And I remember my manager went to a conference and he came back and like, "Hey, Kelsey, I finally know what you're doing." I was like, "What's that?" He was like, "Uh, you're doing DevOps." And I part of me was like upset. how do you get to name what I'm doing? And so, you know, everyone's talking about DevOps and he's like, I met a guy named James Turnball. And James is an Australian dude. He worked at Puppet Labs and he wrote the first puppet book that I bought and read. And so I'm like, James Turnpaul? That name sounds familiar. Oh, I'm looking at my desk, James Turn. So, he's one of the co-authors of this book. And it turns out James wrote a lot of tech books back then. And he's coming to the office. And my manager wanted him to check out how we were using puppet. I was like, "Okay, so you know, this is world-class expert." And by that time, I had puppet hidden behind Jurro tickets. And so you could just open a Jurro ticket. I had RPMs for everything. You picked the RPM you wanted from a drop down. You picked your environment from a drop down. And magic happened and you got results. Most people didn't even know Puppet existed. Most people never touched it. They just knew they can get anything on demand.

</details>

**主持人**: 你可以直接去 Jira，然后它就自动执行了。比如，你可以配置一台新机器？

<details>
<summary>Original English</summary>

**Host**: You could go to Jira and it does it. So, so for example, you could like provision a new machine or

</details>

**Kelsey Hightower**: 甚至是一整个环境。“我要数据库，我要 IBM MQ 消息服务器，我要这三个应用，我还需这套防火墙配置。”没问题，开正确的 Jira 工单。等它们被批准后，我们有一个我叫它“Mr. Resetti”（来自某个游戏的梗）的程序。一旦获批，这个程序就会接手这个工单，提取出所有自定义字段的内容，去调用相应的 Puppet 清单，把结果抓取回来更新到工单里。产品经理、开发人员，他们几乎是瞬间就能得到他们想要的。所以我们构建了整套系统，而他们并不知道，在那些夜晚和周末，我还在给 Puppet 提交开源代码。因为当时公司不允许工作时间做这个，那是 2007 年、2008 年。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: whole environment. I want database. I want IBM MQ series message server. I want these three apps and I need this firewall setup. No problem. Open the right jar tickets. Get them approved. When they're approved, we had this little I I called it Mr. Receti. All right. One of my buddies gave me a name from some video game. Once it got approved, Mr. city would own the ticket and we would just extract the custom fields and we would just call the right puppet manifest and we would take the output and update the ticket and so PMs developers they just got what they want damn near instantaneously so we built all the systems they didn't know nights and weekends I'm contributing to puppet because you know wasn't allowed at work at the time this is 2007 2008

</details>

**主持人**: 他们当时可能根本不懂什么是开源。

<details>
<summary>Original English</summary>

**Host**: they probably didn't even really understand what open source was anyway

</details>

**Kelsey Hightower**: 他们的态度是：“嘿，你必须在自己的私人时间做。”所以我只在晚上和周末做。James 来了，我记得我们一起进了电梯，要去三楼。我的经理把 James 介绍给我，以及我们团队。“嘿，这是这位，那是那位，这是 Kelsey。”James 转过头看着我，他说：“Kelsey Hightower？哦，我们知道你。我们非常感谢你贡献的代码。”我的经理当时就在旁边愣住了：“什么贡献代码？我们没做过什么贡献啊。”James 握着我的手，跟我像老朋友一样聊天，因为我一直通过开源社区与 Puppet Labs 的团队合作。到了楼上，经理说：“嘿，我们给他看看我们的架构吧。”我说：“好吧 James，我们这儿用了很多 Puppet 清单，我使用了外部节点分类器，用数据配置逻辑，我们应用了承诺理论（Promise Theory），我们把一切都调整得很好。但是从交互界面上，我不想让所有人都要学现代的 Puppet，所以我们把它挂接在 Jira 上。”我给他展示了整个工作流。他就坐在那里说：“牛，我完全挑不出任何毛病。这简直太棒了。”接下来是改变游戏规则的时刻。他大老远来到亚特兰大，离机场有 45 分钟车程。他花了一天时间和我们团队在一起。一天结束了，他正准备叫出租车去机场。我说：“不行，你在我的地盘，我绝不能让你自己打车去机场，我开车送你。”于是我上了车，他坐在副驾，我同事在后座。他解下领带，卷起袖子，我看到了他身上的纹身。我惊叹道：“哦，所以你是个真正的技术圈里人。”他说：“是啊，我平时不搞这些打扮，这只是为了应付你们这儿的着装要求。”我说：“哦，James 你太酷了。”他说：“伙计，你们做的工作非常出色。”那是我第一次真正和现实中的 James Turnbull 交流。他邀请我去了 PuppetConf 演讲。

我去了那里做我的第一次大型技术会议演讲。我讲了一些 Puppet 底层集成的东西，并在里面加了一点幽默元素。那是我第一次觉得自己能在舞台上做真实的自己。在回家之前，Puppet 的创始人 Luke Kanies 在俄勒冈州波特兰的一家小咖啡馆里和我坐下来，他问我：“你想来这里工作吗？”我立刻回答：“想！当然，百分之百愿意！”当然，薪水也有了不错的涨幅，而且我可以远程办公，不需要马上离开亚特兰大。我记得回到原公司后，我的经理非常赞赏我这些年取得的进展，我给自己打出了一些名气。我记得有一天他突然给我加薪了，他把一个信封滑给我，我打开一看，上面的数字很不错。我说：“哦，太好了。但有个事，我要辞职了。我要去 Puppet 工作了。”然后他说了一句非常酷的话（考虑到我们曾经因为意见不合关系紧张，但总体而言是他帮我走向成熟，这一点我永远感激），他说：“你居然能在这里待这么久，我挺惊讶的。”他把这当成一种最高赞誉，认为我不仅在这里变得更好、产生了影响，而且我确实改变了这家公司的文化。7 年后，Kubernetes 出现时，一切形成了一个完美的闭环。我回到了那个办公室，他们已经在生产环境中运行 CI/CD 和 Kubernetes，甚至我当年留下的一些旧工具还在运行。对我来说，那是极其重要的反馈——有时候，产生持久的影响远比一时的解决方案重要。即使我不在了，他们依然保留了那种文化，知道如何拥抱新技术并把它融入架构中。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: so they was like hey you got to do it on your own time so I would just do it nights and weekends so James shows up and I remember we all get in the elevator. We're going to the third floor. My manager's introducing James to me, to our team, like, "Hey, this is this person. This is this person. This is Kelsey." And James turns to me, he's like, "Kelsey High Tower? Oh, we know you. We love your contributions." And my manager is just like, "What contributions? We're We're not doing contributions." And James is like shaking my hand and he's just talking to me like we're friends because the thing is I have been working with the puppet labs team through like openource open source contributing to puppet
and so we get up there and you know my manager is like hey let's show him our setup I was like all right James we have a lot of puppet manifests over here I'm using external node classifiers I'm setting brightening config from data you know I read my burst is promise theory and we got it all dialed in but from an interface perspective I just didn't want everyone to have to modern puppet. So, we hooked it up to Jer. I'm showing him this entire workflow and he's just sitting there like, "Yeah, I have no recommendations at all. Like, this is this is amazing." And here's the thing that kind of the game changer. So, he came all the way to Atlanta. We're 45 minutes from the airport. He spent time with our team and uh it's the end of the day. And then he's on the way out and he's about to call a cab to go to the airport. I'm like, "No, I you're in my hometown. I cannot let you go to the airport. I will give you a ride to the airport." So, I get in my car and he's in the front seat. My colleague's in the back seat. He takes off his tie and rolls up his sleeves. I can see all the tattoos. I'm like, "Oh, so you're like a legit text like, "Yeah, I don't do all of this. I just did this for you all. This is your dress code." I was like, "Oh, James is cool." He was like, "Man, yeah, you guys are doing great work." And you know, now I'm talking to the real James Turnball. And uh he invited me to give a talk at Puppet Cough. and I went to go give that talk. It was my first like real conference talk and I talked about some low-level kind of puppet integration stuff and I had a little comedy in there. It was like the first time I felt like I could just be myself on stage. Before I came home, Luke Kenise, the founder of Puppet, we sat down in a little coffee shop in Portland, Oregon, and he was like, you know, would you like to work here? I was like, yes, like of course, 100%. And of course there was a nice salary increase and I could work remote. I didn't have to leave Atlanta immediately. And I remember coming back and uh my manager really appreciated all the progress I was making over the years. I kind of made a name for myself. And I remember he gave me a nice little raise just out of the blue. And he slid this envelope to me and I opened it. It was a nice number in there. I was like, "Oh, that's great." I was like, "But here's a thing. I'm resigning. I'm going to go work for Puffet." And then he said something that was dope because we had a kind of, you know, difficult relationship depending on how it went. But overall, he helped me mature. That's one thing I will always say. He helped me really be mature. And uh he was like, "I'm surprised you stayed here this long, right?" As like this ultimate compliment that you stayed here beyond the just getting better or making an impact. You literally changed this culture. And the full circle moment happened like 7 years later when Kubernetes came out. I remember coming back to that office and they had already been running CD in production, Kubernetes in production and even some of the old tooling I had was still running and to me that was like a really important feedback that sometimes if you make an impact lasting impact is way different that even when I wasn't there they still had the culture to say there's new technology and we know how to bring it into the stack.

</details>

### Golang 的觉醒与 Docker 的冲击

**主持人**: 此时容器技术开始崭露头角，对吧。你是如何第一次接触到容器的？你是否在很早期就意识到这将成为一件大事？

<details>
<summary>Original English</summary>

**Host**: So at this point containers were starting to start right. How did you first come across containers and very early on you realize this is going to be big and important?

</details>

**Kelsey Hightower**: 我并没有。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I didn't.

</details>

**主持人**: 哦，你没有？

<details>
<summary>Original English</summary>

**Host**: Oh you didn't?

</details>

**Kelsey Hightower**: 没有，因为我当时在 Puppet Labs。在那之前，我是核心 Python 模块的贡献者，比如 Virtualenv 团队的，当时在试图解决 Python 的包管理问题，Python 即使在那个时候也有很严重的包管理问题。所以我之前完全沉浸在 Python 中，后来学习 Puppet 时，我又完全沉浸在 Ruby 中。我当时认为 DevOps 加上配置管理，就是解决一切问题的终极答案。那个时候，也就是 2011、2012 年，在我心里，市场上唯一的竞争就是 Puppet、Chef 和 Ansible 之间的较量。仅此而已。我完全投入其中，当时我还在 Puppet Labs 工作，感觉我们在主导未来。我们去各大公司让他们了解配置管理，谈论加速交付、合规检查的好处。我们正在推动人们从 Sharepoint 转向执行代码来实现这些目标。我们认为好戏才刚刚开始。谁能想到那个时代并不需要再辉煌 10 年呢？我们甚至从 VMware 那里拿到投资，将 Puppet 集成进去；Chef 也在那时候被集成进了 AWS。所以这感觉就是终点，我们只需要教系统管理员通过 DevOps 成为工程师，并拥抱这些工具。然后，我第一次看到的冲击是 **Golang** 的出现。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: No, because I'm at puppet labs. You know, before that I was contributing to core Python stuff like virtual imp pi on the team that was trying to integrate some of the Python. Python had a package management problem even back then. And so I'm all in on Python and then when I'm learning Puppet, I'm all in on Ruby at that time. I'm thinking DevOps plus configuration management is the end all beall for everything. And really at that time we're talking 2011 2012 in my mind the competition was only between Puppet Chef and Anible. That was it. And so I'm all in and I'm working at Puppet Labs. And so we're kind of in some ways I felt like we were dictating the future. We were going to companies and getting them to understand configuration management. We were talking about the benefits of like speeding everything up and you know doing all these compliance. We were moving people from SharePoint to executable code to implement these things. So we thought we were just getting started. There was no world where we then think that we needed 10 more years of that, right? We even got money from VMware to integrate Puppet into that. Chef was being integrated into AWS at that time. So this was like the thing that finally were finally getting there. We just got to teach system administrators to become engineers via DevOps and started embracing these tools. And then the first thing that I saw come out was Golang.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Mhm. And I remember sitting at my desk and I was like,

</details>

**Kelsey Hightower**: 我记得我坐在办公桌前，心想，那个时候我们在使用 Ruby 时遇到了性能问题。全局锁解释器，你很难轻松地同时做不止一件事。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: you know, at that time we were hitting performance issues with Ruby,
right? The global lock interpreter. You can't do more than one thing at a time, not easily.

</details>

**Kelsey Hightower**: 于是我们转向了像 JRuby 这样的东西。我们甚至为 Puppet 的一部分代码使用了 Clojure。我记得我们还在考虑，是不是应该开始用 C++ 或者 C 语言重写？但问题是那些贡献者怎么办？那些 Ruby 开发者该何去何从？我们严重依赖 Ruby Gems 这样的东西，这将是一次极其艰难的推销。我记得我第一次下载 Go 语言时，它彻底折服了我。我记得我做的原型之一是重写 Facter。Facter 是 Puppet 的一个客户端 Agent 模块，它能提供关于机器的事实信息。比如内核版本是什么，用户分布是什么，它会将这些事实交给 Puppet，这样你的配置代码就有了上下文环境来决定怎么做。那个模块原本是用 Ruby 写的，有时运行得很慢，因为你必须串行读取所有的文件。于是我试着使用 Golang。我记得我在 Mac 上写了代码，编译后，通过 SCP 传到一台 Linux 机器上。我惊呼：“哦，这太疯狂了。”所有事实数据的采集竟然并行运行，仅用原来极小的一小部分时间就返回了。我说：“兄弟们，我们必须得用 Golang 来写点东西了。”我记得团队回答说：“不行，它不支持 Solaris 或者 AIX。”因为那时 Puppet 正在进军传统企业市场。我心想：“这也能作为标准？绝对不行。”但我能理解。接着 Terraform 问世了。在 Docker 之前，Terraform 开始稍微挑战了一下当时的格局。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: And so we moved to things like J Ruby. We even did closure for some part of the puppet stack. And I remember we were thinking about should we start doing stuff in C++?
Mhm.
Should we start doing stuff in C? But the problem is contributors. What would we do with all the Ruby contributors, right? we were relying on things like Ruby gems and it's going to be it was going to be a hard sale and I remember downloading go for the first time and the thing that sold me on it I remember um one of the prototypes that I built was factor so factor is one of the agents in puppet that gives you facts about a machine so this is Red Hat this kernel version this is what the users look like and it would give that to puppet so that your configuration code had context on what to do and that was written in Ruby and sometimes it will run slow because you're reading all these files serly. And so I remember I was like, "All right, let's try this Go Lang out." And I remember I wrote the code on my Mac, compiled it, SCPD it to a Linux box. I was like, "Oh, this is crazy." And I remember running all the facts in parallel, and it came back in a fraction of the time. I was like, "Yo, we got to use Golang for stuff." And I remember the team was like, "No, it doesn't work for Solaris or AIX because Puppet was now moving into the enterprise." I was like, that's the criteria? No way. But I got it, right? I've gone through this maturity thing before. And then Terraform comes out. But before Docker, Terraform is trying is starting to challenge things a little bit, right? And it's starting to use things like Go, at least that was on my radar. So Terraform is like, who cares about the node? It's all about the APIs. And all of us come from the server world and everything's about an agent on a node versus the cloud starting to take over at this point, right? So,

</details>

**主持人**: 所以 Terraform 是以云为核心构建的，对吧？你可以将云环境基础设施配置为代码。

<details>
<summary>Original English</summary>

**Host**: So Terraform was built with the cloud in mind, right? You you could configure your cloud environment infrastructure as a code.

</details>

**Kelsey Hightower**: 对。而我们一直试图从“节点”去操作云。我们试图教 Puppet 通过在一个节点上的代理去配置云端的服务器。这种间接方式非常怪异。但是 Terraform，Mitchell Hashimoto 对吧，他也是早期 DevOps 运动的重要人物。当时他的 Vagrant 是用 Ruby 写的，属于同一个生态圈。然后他分拆出去搞了这么个用 Go 写的工具。我看着它心想：“看，他们已经用 Go 来做这事了。”我记得当 Docker 出现时，Puppet 依然被视为推动创新的人。我们正要求人们以不同的方式思考，走出他们的舒适区。当 Docker 问世时，我们办公室的大多数人都对它嗤之以鼻，觉得：“不，这只是一阵风。这个东西里连配置管理都没有。他们根本不懂企业级。这就跟个玩具一样。”他们倒没有不尊重人，但确实没人把这看成是对我们正在做的事情的挑战。我看了 Docker 之后，起初也没完全搞明白，直到我离开。当我离开 Puppet 时，我打造了一个叫 `confd` 的工具。我去当了工程副总裁，终于可以写 Go 代码了。我们理所当然地审视了那些大量使用 Java 的地方，我赢得了团队的信任，开始用 Go 重写一些微服务，缩小了我们的云足迹，淘汰了旧系统，并把 Go 代码推到了生产环境。我当时想：“我们好像真的不需要 Puppet 了。”我开源了这个叫做 `confd` 的项目，它会从 `etcd` 中提取变量，并仅生成刚好足够的配置——只取了我认为合理的 Puppet 理念的那一部分。然后 Docker 出现了。我恍然大悟：“哇，我们可能不需要再到处搬运 Python 文件了。我们可以把它们打包起来。”

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. And we were trying to do this from a node. We were trying to teach puppet how to talk through by having this indirection where you have to go through a node to configure a server in the cloud. It was so weird. But then Terraform Mitch Hashimoto, right? Like he was a big part of the DevOps movement early too. Then he was like frag Vagrant was written in Ruby. So he was part of that same ecosystem. And then he splits off and there's this going. I'm like, look at that. They're using Go for this. And I remember when Docker came out, Puppet at that time was the one pushing innovation. We're asking people to think a little different,
get out of their comfort zone. And then Docker comes out and most of the office was dismissing this as like, nope, this is a fad. They don't even have config management in this thing. They don't really understand enterprise. This is just kind of not like a toy. They were not being disrespectful, but no one saw this as a challenger. what we were doing and I looked at it and I didn't get it immediately until I left. When I left Puppet, I built this tool called CompD. I went to go be a VP of engineering and I got to write Go code. So, we started rightfully so. We looked at all the Java heavy usage and I earned the trust of the team and we started rewriting some of the microservices in Go, shrinking our cloud footprint and we sunseted it and got it all into production, the Go code. I was like, we don't really need Puppet anymore. And I open sourced this project called CompD and it would pull variables from CD and generate just enough config, just the parts of Puppet that I thought made sense. And then Docker was out. And then I was like, wow, we can probably stop moving Python files around. We can probably package them up. Not in our case.

</details>

**主持人**: Docker 的核心理念是定义一台虚拟机或容器，对吧？

<details>
<summary>Original English</summary>

**Host**: And the idea with Docker was right, that it it would define a virtual machine or a container, right? So to me the big value of docker at the time was previously I had definitely did the work to make RPMs for every app even the custom apps RPMs are the red hat package management y
so if you're on a red hat system you can do yum install engineext yum install postgress but most people
even today don't package their third party apps like the apps that a development team would write you're like no we just put cicd we'll copy them over there maybe put them in a tarball but we usually never went to making official Debian packages or RBM packages But puppet meant you didn't have to go through all of that work and you can still end up with a package something that was repeatable. So all the stuff we used to do with Python and virtual in all the things you used to do with Ruby gems and you know the virtual environments we have for that we got rid of it just squish it all into a docker container and you got rid of a lot of dev tooling. So this is why I think it resonated so much with developers because we cleaned up the mess of working on multiple projects and so I was attracted to that comp was compatible with that and then coro was the thing that I was like you know what I think I know what I want to do but I didn't understand distributed systems not to the degree what coro was doing. So when I moved to the the what was the idea behind coros was like Google's infrastructure for everyone else and so at that time we did there was a tool called MSOS um the board paper had already been published I tried to read it when I was at puppet labs I don't understand any of this stuff is hard to install I couldn't justify it but we would see kind of the rumblings of the Twitter folks talking about the distributed system and all this maybe big data stuff is going around but I was like I just don't understand it seems incompatible with the stuff that I think about even as someone who's worked at Google that had a system like this, right? They had Google cluster file system at this time. It didn't seem as complicated as this MS thing. So I was like, I dismissed it. But what cores did was build on top of Docker. Cor is like, what if we had an operating system that only had Docker on it? Everything is written in Go. We can have a little key value store where you can put your config and we would just synchronize it to all the machines. And that was so compatible with the comp dway way. And so I'm looking at this cores thing. And I'm like, yo, this looks a little bit more like the future because that's what we used to do. You know, I had at this time I was a software developer at Puppet. I was a software developer, VP of engineering at the other company. And I was like, you know what, ops can learn a lot from the uh Docker way of thinking about the world because as a system administrator, we always try to make the OS small, remove things you don't need so it can be secure and repeatable. Docker was like for the things that need to change, just put it here and isolate it. And Cororos is like, "What if you had an operating system designed only to do that?" And I met the Cororo team at Gopher Con, a Go language conference. And they saw me present. And what I learned from the puppet days, every presentation is an interview. I don't think a lot of people think about it that way cuz people are looking at you on stage and they get to see what you're about. And so at Gopher Con, I remember also Rob Pike and the original creators of Goldinger. Oh, this is like the first Gopher Con, right? And so the original creators, Russ Cox, all these people I look up to, Brad Fitzpatrick, and they're all in the audience. And I remember I had a talk, two things. I'm sitting in the audience waiting for my turn. I'm number four on the list or something like this. And the two people who started Gopher Con, they're just from the community, Brian Kettleston and Eric St. Martin. And they're new to this conference scene. Like you could tell, right? You know, they were the best MC's in the world. But they were like, "Hey, welcome to Gopher Con." And at the point in time, Ruby is still dominating. And down the street, there was the Ruby conference going on. And we were just in this building. And I remember the first talk they introduced Rob Pike and he gave this amazing keynote around Hello World. He went up all the way down to the compiler. He went all the way up and he described how the language took shape. It felt simple on the surface, but it went super deep. And it's like Rob Pike had also come full circle from his AT&T days through Unicode through all the stuff that he's ever done. And now we get to see one of his best works, Golang. And my talk was titled Golang for system administrators. I wanted them to see that there's a better way. The way they introduced Rob Pike, though, I was like, "Oh man, this is Rob Pike. You got to you got to have more energy than that for Rob Pike." So, I'm sitting in my chair and I don't know them, but I'm sitting with a buddy of mine from that company where we rewrote everything in Golang, Billy Click. We're sitting next to him. Say, "Hey, Bill, I'm going to go ask them, can I be the MC?" He's like, "What?" Okay. So, I'm whispering. And I walk to the backstage. It's like, "Hey, Eric, uh, Brian, uh, can I try my hand at being the MC?" And they're like, "Sure." Right? And they knew who at least who I was because they accepted the talk. And so I don't know if it was after Rob, but I came out next. So like, "Hey, I'm Kelsey High Tower. You may not know me, but I'm going to be your MC for the rest of the day." And I don't know what happened because it was my first time doing that. I'm cracking jokes. I'm having fun. And I said, "Hey, from here on out, when anyone comes to the stage, it needs to be loud in here to the point where we can get kicked out." And so I was, "All right." Hey, so our next speaker and I think it might have been Derek Coloulston, you know, he's like a Google. He was talking about some ghost stuff and I remember it got really loud and then they come on stage. So if you were a speaker ever before and it's like you walk up to basically a standing ovation, you're energized, everybody is excited. I don't care what you do, the energy level is high. And so he comes out, he's having a good time, the audience is having a good time. And then eventually it was my turn. And I realized like who introduces me. So I go onto stage and I was like I'm next. So we're going to try it like this. I'm going to go back and I'm going to come out and you guys gonna make a lot of noise for my talk. And then I remember just like sliding slowly behind the curtain. So everyone's now laughing. And then the music comes on and I walk out surprised like hey. And everyone's clapping and I do this talk and at that time it's live demo or nothing. And at the time they had this thing called go present. So Rob Pike team, they wanted to make sure they could use Go for everything, even generating a slide deck presentation.

</details>

**Kelsey Hightower**: 对我来说，那时 Docker 的巨大价值在于：以前为了给每个应用制作 RPM 包，我得花不少功夫，即便是自定义应用。RPM 是红帽的包管理器，如果你用红帽系统，你只需 `yum install nginx`。但大多数人甚至到现在都不会把第三方应用——比如开发团队写的应用——打成标准包。你会说：“不用，我们只需用 CI/CD 把代码拷过去，也许打个 Tar 包就行了。”我们通常不会去制作官方的 Debian 包或 RPM 包。但 Puppet 的出现意味着，你不需要经历那些繁琐的工作，你依然能得到某种可重复的“包”。但是有了 Docker，过去我们用 Python 虚拟环境做的那些事，用 Ruby Gems 做的那些事，我们全都扔掉了。只需把它塞进一个 Docker 容器里，你就摆脱了一大堆开发工具。所以这就是我认为它能引起开发者强烈共鸣的原因。因为它清理了多项目开发的烂摊子。于是我也被它吸引了，`confd` 与之完美兼容。然后 CoreOS 出现了，我觉得：“这就是我想做的事。”但当时我并不懂分布式系统，至少达不到 CoreOS 在做的那个深度。CoreOS 的理念是什么？是“为大众提供类似 Google 的基础设施”。在那之前，市面上有一个叫 Mesos 的工具，那篇关于 Borg 的论文已经发表了。在 Puppet 时我试着去读过，我完全看不懂，系统也很难安装，我找不到理由去用它。但我们看到了 Twitter 上的人在讨论分布式系统，大数据也在流行。但我当时觉得：“我不懂这个，这跟我的思路格格不入。”即便是对于我这个曾在 Google 做过类似系统的人来说，它看起来都比那个 Mesos 复杂得多。所以我忽略了它。但 CoreOS 做的，是建立在 Docker 之上。CoreOS 的理念是：“如果有一个只有 Docker 的操作系统会怎样？一切都用 Go 语言写。我们弄一个小小的键值存储系统，你可以把配置放进去，然后我们把它同步到所有的机器上。”这与 `confd` 的做法极其契合！所以我看着 CoreOS 惊叹：“这看起来更像是未来。这正是我们过去想做的。”那时我已经做过软件开发者、工程副总。我心想，运维人员可以从 Docker 的世界观里学到很多东西。作为系统管理员，我们总是试图让操作系统保持精简，删掉你不需要的东西，让它变得安全和可重复。而 Docker 的思路是：“对于需要变动的东西，就把它们隔离放在这里。”而 CoreOS 则进一步提出：“如果我们从设计之初就打造一个只干这件事的操作系统呢？”

后来，我在 GopherCon（Go 语言开发者大会）上遇到了 CoreOS 团队。他们看到了我的演讲。我从 Puppet 时代学到的是：**每一次演讲都是一次面试**。我不认为有很多人会这样想。当人们看着台上的你时，他们能看到你的实力。我记得第一届 GopherCon 的台下，坐着 Go 语言的早期创造者，Rob Pike、Russ Cox、Brad Fitzpatrick 等所有我仰慕的大佬。我在台下等着上场，我排在大概第四个。头两个发言的是那两个社区里创办这场大会的人，Brian Ketelsen 和 Erik St. Martin。你能看出这是他们第一次搞大会，他们不是最专业的 MC（主持人），但他们很热情。那时，Ruby 依然占据统治地位。就在街对面，Ruby 大会正在举行。第一场演讲他们介绍了 Rob Pike，他做了一场关于“Hello World”的精彩主题演讲。他深入到了编译器层面，然后一路向上，描述了 Go 这门语言是如何成型的。表面上看起来简单，但实际上极其深邃。这就像 Rob Pike 的职业生涯走过了一个闭环，从他在 AT&T 的日子，到 Unicode，再到现在，我们看到了他最得意的作品之一：Golang。

我的演讲题目是“系统管理员的 Golang”。我想让他们看到有更好的方法。但是他们介绍 Rob Pike 出场的方式，让我觉得：“天哪，这可是 Rob Pike 啊，你们的激情得再高一点。”所以当我在后台看到 Brian 和 Erik 时，我问：“我可以试试当 MC 吗？”他们同意了。于是我走了出去：“嘿，我是 Kelsey Hightower。你们可能不认识我，但接下来今天的时间里，我就是你们的 MC。从现在起，无论是谁上台，我们都要把气氛搞得燃爆，哪怕我们被赶出这个场子！”结果整个场馆沸腾了，每一个上台的演讲者都像迎来了起立鼓掌，每个人都充满了活力。最后轮到我自己的时候，我才意识到，谁来介绍我出场呢？于是我走到台上说：“下一个是我。我们这样来，我先走回后台，然后我走出来的时候，大家要为我的演讲疯狂欢呼。”然后我慢慢退到幕后，全场大笑。音乐响起，我走出来，假装惊喜地挥手，所有人都热烈鼓掌。

在那个年代，演讲如果不是现场演示那就是白搭。Rob Pike 的团队当时为了证明 Go 可以做任何事，开发了一个叫 `go present` 的幻灯片工具，完全是用 Go 写的。它能生成 HTML 幻灯片，还可以在幻灯片里直接运行你的代码片段，让人们看到输出结果。我当时想：“系统管理员能从 Go 里获得什么价值？我该如何向他们证明？”所以我用 Go 写了一个 iPXE 服务器，并在我笔记本的 VMware Fusion 虚拟机里演示，我演示了如何从我笔记本上运行的 Go PXE 服务器同时启动多台虚拟机的系统。当我在幻灯片里点击“运行”，你可以直接在幻灯片里看到 HTTP 下发镜像、分配 IP 的日志，虚拟机当场启动。你甚至能看到台下观众脸上的震惊：“你刚刚用幻灯片完成了整个过程？”然后我启动了下一台机器，并讲解了为什么我认为这对我们的运维领域是个颠覆：终于，我们有了一个工具，既能写出高性能的应用，又拥有命令式编程的简洁，我们可以超越单纯的脚本，真正开始构建系统。观众完全被吸引了。我向后看去，后排站满了人。我认出了一些名字，他们是 Ruby 社区的人，都是写 Ruby 书籍的大佬。中场休息时，他们过来对我说：“我们在 Twitter 上看到你们这儿嗨翻了，就抛下 Ruby 大会跑过来了！”我觉得那一刻，Go 真的登堂入室了。

但猜猜还有谁在那里？CoreOS 团队也在看着我。因为我刚刚是用 PXE 启动的 CoreOS 系统！这就是为什么我说“每一次演讲都是一次面试”。他们说：“行，我们看懂了，你该加入 CoreOS 团队。”所以我加入了 CoreOS。这也是我第一次真正感觉到，容器运动长出了翅膀，它真的有前途了。那大概是在 Kubernetes 出现的一两年前。

### Kubernetes 的发布与爆发

**主持人**: 你当时也在用 Go 演讲。

<details>
<summary>Original English</summary>

**Host**: It was all in Go.

</details>

**Kelsey Hightower**: 都是用 Go 的。你可以有一个很漂亮的 HTML 格式的幻灯片，你只需要在浏览器里打开它。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: It was all in Go. So you had this nice HTML representation of your slides. You just open up your browser.

</details>

**主持人**: 希望它不要崩溃。

<details>
<summary>Original English</summary>

**Host**: Hopefully it won't crash.

</details>

**Kelsey Hightower**: 希望不崩溃。并且你可以在示例中直接执行代码。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Hopefully it doesn't crash. And you can run executable code in your examples.

</details>

**主持人**: 放入任何代码片段，格式都很整齐，而且有一个小运行按钮，让大家看到 Go 代码的输出结果。

<details>
<summary>Original English</summary>

**Host**: So any code snippet you put there, it was formatted nicely. And you had the little run button so people can see the output of the Go code. And so I was like, hm, what would a system administrator value you can get from go? How can I prove it to them? And so I wrote a ipixie server in Go. And I remember in VMware Fusion that runs on your laptop. So if you want virtual machines on your laptop, you can use desktop parallels or VMware Fusion. The thing about VMware Fusion on your Mac, you can create virtual machines, but you can also swap out the network card. And I did one where you can have a network card that talks to IPixie. So, I wanted to show them how it would um boot up multiple machines from a Go Pixie server running on my laptop. So, part of that demo would start the I had this kind of snippet of my Pixie server and I hit the run button. So, now my Pixie server is running in the background. I was like, "So, what can you do with it?" And I remember looking in the front row and Rob Pike and team are just intimately looking at this thing like, "Wow, this he just started a pixie server from his laptop from Go Present the slide deck tool." And so this thing is running and I'm like, "All right, let's bring up VMware. I got to make sure I switch the adapter to the one that supports iPixie. Got to do some firmware thing." And then I remember I booted the VM. You can see the logs in the Go Present of like HTTP handing off the image, giving the IP and the virtual machine is booting up and you can just see the amazement on the audience face like did you just do that? And then I booted another thing in the thing and I'm going through why I think that this is a gamecher for the craft that we have. We finally have a tool where we write high performant things with the simplicity of imperative programming and we can go beyond just scripts. We can actually build systems. The audience was dialed in and it got loud like after you know things were working people were clapping. I look in the back and there's a whole bunch of people now standing and I recognize some of the names because they're from the Ruby community. These are people that are writing the Ruby books. And then, you know, after I'm done, there's a break and I walk back there. They're like, "Hey, we saw on Twitter that you guys are just like going crazy over here. It's out of control is electrifying. We left the Ruby event to come here." And so I felt like, man, it had arrived. But guess who else was there? The Coros team. The Coros team was watching me because I was pixie booting Coros. This is what I mean is every job's an interview. the team was like all right we can see that yeah you should join the core o team so that's how I ended up at coros this is how I really felt like the container movement had legs and this is what maybe a year or two before kubernetes comes out

</details>

**主持人**: 然后 Kubernetes 出来了，你也开始为它做贡献。

<details>
<summary>Original English</summary>

**Host**: and then kubernetes came out u and you were starting to contribute to that as well

</details>

**Kelsey Hightower**: 是的。有很多软件工程师，有时看到台上的演讲者，他们会质疑：“那个人真的懂他在说什么吗？是不是只是个只会念稿的布道师？这个演示是不是别人写好给他直接跑的？”我能理解，因为有时很难去评估你不具备的技能。所以当我们在 CoreOS 时，我们正在打造自己的集群管理系统，叫 Fleet。我们使用 `systemd`，并且试图通过 `etcd` 同步配置。因为在 CoreOS 集群中，所有节点都是通过 `etcd` 通信的。过去你要把 `unit` 配置文件 SCP 到 1000 台机器上，但现在我们说，不用拷贝文件了，直接放在 `etcd` 里，应该运行这些文件的节点会自动去拉取并运行它。我们叫它 Fleet。

大约一年后，Kubernetes 横空出世，所有人都一头雾水：“这是啥？”我们只提前了一天收到消息。Google 团队联系我们说：“嘿，明天我们要发布这个东西，这是 GitHub 仓库，你们得对内容保密，先别往外说。”我心想，这故事里根本没有我们的戏份啊。新闻里只会说是 Google 和 Red Hat。CoreOS 的名字不在里面。那么我们能做什么呢？我记得我整夜没睡。我拿到了 GitHub 仓库的访问权限，拼命阅读所有的 Go 代码，试图搞清楚那些二进制文件是干什么的，因为根本没有文档！

<details>
<summary>Original English</summary>

**Kelsey Hightower**: yes so my core os and I think the thing that's very important a lot of software engineers sometimes they look at the people on stage and they ask questions like does that person know what they're doing is this person just like an evangelist. Uh, did someone write this demo for them? Did they give it to them and they just run the code?
Yeah, we we think that, don't we?
Well, I mean, I can see why because sometimes it's hard to value skills you don't have. So, a lot of software engineers are terrible. If you put a soft some, they can't talk. They can't simplify concepts. Maybe they can write code really well, but this is a set of skills that they may or may not have. And so, when you see someone like that, you're you're you're questioning them. And I remember giving a talk one time at Strange Loop about Cedd and CRO OS and someone was like do you understand uh is isd like a CA system or AP system like the cap theorem and the question was kind of loaded like we don't think you even know what that means. I was like um CD is going to always favor consistency. He was like that's not correct the RAF paper blah blah blah. I said listen you said Etsy D. Let me show you this is the raff log. This is my three nodes. I'm going to turn off two. And you notice I can't write any keys. So availability has been sacrificed. Consistency is being preserved. I'm going to start another node. There's going to be a handshake. There's going to be quorum. I will be able to write keys. Now it works. That's the cap theorem in reality. So it doesn't matter what the rap paper says that you're talking about a raff log on a single implementation. Raph doesn't talk about cluster membership, leader election, how it's implemented, and what you should do in the different modes. That choice is yours. And this is how D is implemented. And I remember he was like, "Oh this guy actually knows what he's talking about." Being at Coros, we were working on our own fleet management system called Fleet. We're using systemd and we're trying to synchronize configs through CD and remember in a core os cluster all the nodes communicate viacd. So imagine using systemd for those that have never used systemd you put a unit file like I want this process to start with these flags you know bind to this port and you put it in a directory and then systemd will start it and if you had a thousand nodes of course you could SCP that file to all 1,000 nodes and then there you have it. So we decided instead of you copying all the files of all the nodes just put the unit file incd and the node that should run those things would then pull from and just run those unit files and we called it fleet. So we had our own vision of giving people a distributed spouse or distributed system. About a year goes by Kubernetes comes out and everyone was like what's that? And we're all we got like a day notice. So the Google team reached out like hey tomorrow we're announcing this thing. Here's the GitHub repository. Here's you guys are under embargo. Don't talk about it. And so I'm thinking we're not part of this story. like our our names are not in here just say as Google and Red Hat and they're going to announce it at Docker Con. There's no core OS in here. So, what can we do? And I remember I stayed up all night. I got access to the GitHub repository. I reading all the Go code trying to figure out what all these binaries mean cuz there's no docs.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kelsey Hightower**: 所以我在 CoreOS 上把所有东西都跑通了。当 Google 正式宣布时（比如那个在 DockerCon 上的著名演讲），他们在 Hacker News 上发了帖子冲到了第一。紧接着我们发了帖子：“嘿，刚刚他们说的那个东西，这里是如何在 CoreOS 上运行它的教程。”我打了一些补丁让它真的跑起来，并编写了一个漂亮的指南。我们把它发布在了 CoreOS 官网上。然后我们的帖子也在 Hacker News 上冲到了第一。所有人都在说：“Google 刚刚宣布了这个东西，我们不知道它到底是个啥；然后 Kelsey 搞出了这篇东西，现在我们懂了，我们知道怎么安装运行它了。”大家疯狂下载 CoreOS 只是为了能跑一跑 Kubernetes。那时我正好接下来一周有个会议主题演讲。我说：“我不管我几个月前提交的演讲主题是什么，我今天就要讲 Kubernetes。”我开始给人们做 Kubernetes 的现场演示，教他们如何在 CoreOS 上玩转它。但当时团队还没有完全买账，因为我们还有自己的产品路线图。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: And so I got everything working on core OS. So when they did the official Google announcement, of course there's a famous Docker keynote where they unveiled it to the surprise of even Docker to some degree. And I remember they post their number one on hacker news and then we post hey what they just said but here's how you run it on core o
and some examples and commands and I had to do a few patches to get it to actually work and I had to build some binaries to get things glued together.
You did that overnight.
Overnight I didn't go to sleep. I'm just like hey guys I finally figured out how to compile everything. I think the kublet does this. You have to put this there. They had like a coup up SSH script, but I had to reverse it because I'm not using Google Cloud. We got core OS. We're on bare metal. So, I have to pixie boot some things. But I think if you put all these things in the right place, there's this CD thing that's ours. We know that. So, we know how to use that. But I think the API server connects to that. There's no volumes. There's no config maps. So, all you can do is get this thing stood up and then you can submit a config and then it will just basically use Docker in the background. Okay, I can document that. So, we get everything to work and I write this nice little guide. Someone in our team, they publish it to the official core west website. So then we launch that on hacker news and then we go to number one and everyone is like Google just announced this thing. We don't know what it is. And then Kelsey launches this thing. We now know what it is. We know how to install it. We know how to run it. So now people are downloading core OS just so they can play with Kubernetes. And I had a keynote probably in a week. I don't know what I submitted to the conference cuz usually you submit like months ahead of time. I was like, "Hey, I know this talk was supposed to be about this, but it's not today. It's going to be about Kubernetes." And people like, "What's that?" It's like, "Yeah, it just got announced. I'm going to show you." And I started giving people live demos of Kubernetes and how to make it work, you know, using Coros and all these things. But the team still wasn't sold because we had our own road map.

</details>

**主持人**: 是的。你们还有自己的 Fleet 管理软件。

<details>
<summary>Original English</summary>

**Host**: Yeah.
and and you had your own fleet management software.

</details>

**Kelsey Hightower**: Kubernetes 成了 Fleet 的直接竞争对手。而且我们也还不确定它是否靠谱。记住，当时的王者是 Docker，他们有 Docker Swarm。Google 几年前推出过一个叫“Let Me Contain That For You (lmctfy)”的东西，那是个用 C++ 写的容器运行时，试图挑战 Docker，结果根本没人理。所以我们当时也在想，可能这个新东西最后也没人理。只有当我下班回家，开始在晚上和周末提交一些小型代码贡献，阅读了所有代码，真正体会到它的精髓时，我才说：“不，这东西是有料的。”大概两三个月后，多亏了 CoreOS 的创始人 Alex Polvi 和 Brandon Philips 人非常好，他们没有生气。我所有的主题演讲越来越像“Kubernetes + CoreOS”。最终，这是不可避免的。我成为了 CoreOS 的产品经理，我们把所有人都叫到了旧金山办公室的地下室。我们宣布：“兄弟们，All in Kubernetes。Fleet 以及我们自己建的相关工具，全部废弃。我们要全面转向这个新方向。”我很高兴我们那么做了。因为 Alex Polvi 后来提出了“Operators”这个名词（Kubernetes 社区的核心概念），我们共同投入了大量的精力，还做出了名为 CNI 的网络标准接口。对我来说，Kubernetes 意味着什么？它将我过去 15 年在数据中心作为一线执行者积累的经验，从学习 Puppet 的优缺点，到摸爬滚打的经验进行了完美的整合。就像是我对这个世界的呼喊：“如果我知道怎么写，我早就造出这个东西了。”这也就是我向全世界解释它的方式。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. We had our own Kubernetes was now competing with it with fleet specifically.
Yeah. And also we didn't know we can trust it, right? Remember Docker is the king. Docker's number one. There's Docker Swarm, right? And we're with Fleet. And right now, we're like, uh, Google also launched years prior a thing called let me contain that for you. It was a container runtime written in C++ to compete with Docker. And no one cared.
Yeah.
And so we didn't know like maybe no one's going to care about this either. It's only when I started going home and starting doing small contributions and starting to read everything and getting a feel for it, I was like, "No, there's something here." And so for maybe two or three months and luckily the founders of course were really nice, Alex Pov and Brandon, they were just like they didn't get mad or anything. I was contributing nights and weekends kind of like I was at that other company. Uh all of my keynotes were more like Kubernetes plus core OS. And I remember at some point it was inevitable. We all got in a room. I became the product manager of core o at the time and Alex is like I think you got the vision here and we got everybody in the basement in San Francisco in the office we were like hey guys all in on Kubernetes fleet deprecated all these things that we're building deprecated we're going to go all in and I'm glad we did because um Alex Py came up with the name operators which is like a core idea in the Kubernetes community we put all this effort in there me and another guy working on a thing called CNI which is the networking layer for Kubernetes And what Kubernetes really meant for me was that previous 15 years of experience as a practitioner in the data center learning promise theory learning Puppet where it works well where it doesn't and then understanding that Puppet wasn't the only way and then making going through all these loops. And so when I ended at Kubernetes it felt like this would be the thing I would build if I only knew how. And that's the way I explained it to the rest of the world. And at that Gopher Con, maybe the next one, there were people from the now early Kubernetes community. It's a small company called Kismatic. They were kind of a cores competitor to some degree, but they came up with the idea like we should have a conference just like GopherCon. We called it KubeCon. Joseph got the logo going and the Kismatic team kind of put up the money for the first event and we really welcomed the entire community and now it's been 12 years later and the CNCF has done a fabulous job of keeping it going. Now there's like what 13,000 people here in Amsterdam keeping that thing going.

</details>

### Kubernetes 制胜的法宝

**主持人**: 我也问过上过播客的 Kat Cosgrove。你认为到底是什么让 Kubernetes 取得了突破并最终成为了编排节点的绝对主流标准？在此之前有 Fleet、Docker Swarm，就像你一开始说的那样，它看起来并没有后来那么大潜力。

<details>
<summary>Original English</summary>

**Host**: So I asked this from Cat Cosgrove as well who was on the podcast. What do you think really made Kubernetes break through and then just just become the de facto way of of orchestrating nodes and and and just winning again? There was at core o you were building fleet docker had swarm like as you said in the beginning it it didn't seem like this this will be this big

</details>

**Kelsey Hightower**: 我认为排名第一的成功标准是 Docker。在那个时代，Mesosphere 有他们自己的运行时，HashiCorp 出了 Nomad 也有自己的运行时，但唯一获得了全球开发者共识的运行时是 Docker。通过采用 Docker，Kubernetes 直接绕过了语言层面的争议。我们不再需要争论 Java、Python 还是 Ruby，你只需要讨论调度 Docker 容器。这就等于站在了巨人的肩膀上。我们已经赢在了起跑线上。相比之下，Docker Swarm 试图将为单机设计的 Docker API 强行扩展到分布式集群上，这在设计上注定会面临灾难。而 Kubernetes 团队非常聪明。他们没有摆出一副“Google 在所有方面都比你们强”的姿态。他们做对了两件事：第一，让我们直接用 `etcd`；第二，让我们直接用 Docker。将这两者结合，再加上那些写过 Omega 论文的人的经验。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I think the number one success criteria was docker so remember there was mos and msosphere and they had their own runtime corp had come out with nomad and they had their own runtime but the biggest runtime that had already got global consensus was docker so by that time there were so many docker containers and docker workflows and docker Swarm maybe the Achilles heel to Docker Swarm was its design. They tried to take the Docker API which worked really well for one node and expand it across multiple systems and it was not the right API to scale to another type of thing that we needed. And so they kept trying. They tried to add storage. They tried to add networking but the Docker API was never meant for that. And so the Kubernetes team was smart. Instead of trying to say Google's better than everyone on everything, they did a couple of things correct. Let's just use CD. Let's just use Docker. So you take those two things and you take the experience of the people who wrote the Omega paper which is kind of thinking about what would come after Borg and at least the things like MSOS.

</details>

**主持人**: Omega 是 Google 设想的在 Borg 之后要构建的系统，但他们从未真正去建它，对吗？

<details>
<summary>Original English</summary>

**Host**: So Omega was a system where what Google would have built after Borg but they never built it, right?

</details>

**Kelsey Hightower**: 是的。它有很多部分影响了后来的 Kubernetes。对于很多人来说，Kubernetes 解决的第一个痛点是：过去如果你的 Ruby 应用依赖 Nginx 和另一个进程，你必须写一个超级复杂的 Shell 脚本（Entrypoint）去模拟 init 系统的行为。Kubernetes 说：“不不不，你不需要这么做，你可以做几个独立的容器（Pod 的概念），我们会像管理进程树一样管理它们。”所以突然之间，应用架构的思路变得无比清晰。

它解决的第二个大问题是，我们从“基础设施即代码”（Infrastructure as Code）跨越到了“基础设施即数据”（Infrastructure as Data）。Kubernetes 说：“不，你只需要指定你确切想要的容器、它们需要的内存，我们有一个 Status 字段会告诉你它们是否在运行。”这就意味着你根本不需要成为编译器专家。不管你用什么语言，你只需要在 IDE 里写几行 YAML，交给 API 服务器。它的控制循环（Control Loops）就会根据这个状态进行自我修正。

最后，要归功于 Brendan Burns，他让 Kubernetes 的首要扩展机制变得无比顺畅。OpenStack 和 Mesos 都没有这种设计。在 Kubernetes 中，他为基础设施引入了“类型系统”。就像在强类型编程语言中一样，“类型”为你省去了大量认知开销。你再也不用担心给一个应该传整数的地方传了字符串。一旦你把数据模型建立好，不管你是用 Python 还是 Bash，你只要能读写这套标准 API，就能扩展功能。Cisco 可以进来做他们想做的，Red Hat 也能进来做 OpenShift。这就是让整个生态彻底爆发的转折点。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. So they had elements of it. So like the omelette, you know, this like agent that would like be more declarative. a lot of hints from the Kubernetes world that will come later
and and then just to be clear Borg was and is still Google's way of managing their back then hundreds of thousands now probably millions or tens of millions of of servers and they were best in the world with this or they still are right so they learn
I think Borg was one of these things where you integrate the hardware the software the package management the configuration management map reduceuce right Borg is this thing that just expands and grows in some ways I guess it's extensible but all that insight and knowledge, but then they get so much experience with that. If you were to do it again, what would you do? And you read the Omega paper and it's like here's how we what we learn from scheduling. It doesn't need to be that complex, especially for certain workloads. You don't need this like high performance overengineer thing. There's a simpler way to do scheduling, especially if you can give the scheduler a bit more metadata about the workload. They're also big game changers. Now instead of talking about Java versus Python versus Ruby, you only have to talk about scheduling Docker containers. And so I think that's the number one success criteria that we were already off to a running start because you could just reuse the same Docker containers. You didn't have to rebuild a new image thing. So given that what they tried to do in the early beginning was just fill in the gaps. And in many ways, yes, it's a new system, but it fills in the gaps. The one gap that they filled in was Docker had an entry point. So if you needed a Ruby app that needed EngineX and your process, you used to have to write a little shell script, the entry point script that would do all this magic almost imitating an init system. Kubernetes is like, no, no, no, you don't need to do that. You can just make separate containers and then Kubernetes would run them as a process tree. And so for many people, it's like finally now we can have a clear way of thinking about application architecture
like blocks. like blocks now instead of like you have to open the entry point to see what we're going to do versus full life cycle management independent. So it solves that number one problem. The other big one that I think that they solve number one we went from infrastructure is code to infrastructure is data and infrastructure is code is like if this do that um bring in this module for loops all this stuff and Kubernetes is like no no no you have to specify exactly the containers you want how much memory that they need and then we have the status field to tell you if they were running or not and you would take this data object that you could write by hand give it to an API and then the control loops would operate on this state so That means it didn't matter if you had Ruby, Python, or anything. You can just take your IDE, write some YAML, give it to another tool, manipulate the YAML, and then pass it down to the API servers. You can build any combination that you want it without having to be a compiler first. That to me was a fundamental game changer that I don't know if a lot of people understood why it felt very easy to onboard to Kubernetes. Cubectl apply object off you go. And the last thing I think credit to Brendan Burns, the ability to extend Kubernetes in a first class way. OpenStack didn't have it. MSOS didn't really have it. In MSOS, you have a scheduler and you built the other part of the scheduleuler. So you can have Spark, Hadoop, Marathon, but you had all these other tools sitting on top of a thing. So an extension in MSOS was heavy almost like a whole another system. The thing that makes Kubernetes powerful, there's a data model. We gave infrastructure a type system. So instead of imperative shell scripts, you finally had types. So if anyone's ever come from like Python to a type language, types do a lot for you in terms of cognitive overhead. Like you really know what goes into this function. If you put the wrong thing into this function, it doesn't even work like you can't pass a string where an integer needs to be. Kubernetes brings the same semantics to infrastructure. And finally, now it's much safer to automate things because you're gluing together things that actually have structure and types. I was about to say the reason we love types and every language is goes towards them is safety and it eliminates a a whole class of errors.
Yeah, you can do things like static analysis. You can have other tools compile different things and ensure that they have the exact same thing and you have this validator tells you that's not the right object, that's not the right field. And so once you have all of those things, you can build a really nice deployment system. So coupl deploy these containers, no problem. But what about everything else? So instead of trying to evolve Kubernetes to do everything, Brendan Burns, I remember sitting next to him, he's like, "Kelsey, let me show you this thing, you can extend Kubernetes just by giving it a description of what you would like your object to be." So if you were thinking about this from the rest world, hey, I need a user, here's the credit operations, and just give it to the thing and it does everything else for you. And so when that came out it's like so if I wanted to manage let's say a firewall like yeah you can describe a firewall and you give that to Kubernetes and all the tooling works you can now say coupl apply a firewall and so now we got tools like search management where if you want a certificate from let's encrypt you can just say what domain you want where it should live give it to it and now you had a first class extension you didn't have to uninstall it you have to make some magical binary and it really didn't matter what what language you on it because once you put the data model in place, you got the machinery and if you care, if you like Python, you can have Python running a loop, grab the data and then make it so if bash was your thing, you can literally pull the config using a bash script and make it so and just update the status field. That opened up the entire ecosystem. So Cisco could come in, do what they wanted to do. Red Hat can come in, open shift and do what they wanted to do. To me that was the gamecher that brought the rest of the community in.

</details>

### 重返 Google：打造影响力的 DevRel

**主持人**: 然后你加入了 Google，在外人看来这并不意外。但你是怎么加入的？你也为 Kubernetes 做过贡献。你加入了 Kubernetes 团队吗？

<details>
<summary>Original English</summary>

**Host**: And then you joined Google not very surprisingly at this point I guess from the outside of course but but h how did that go? You've been contributing to to Kubernetes as well. The team team was there. Did you join the Kubernetes team?

</details>

**Kelsey Hightower**: 不。那个时候我已经在考虑我的“退出策略”了。在我们的职业生涯中，我们做了很多努力进入这个领域：证书、训练营、学习，甚至上大学。一旦你进来了，你就会思考职业发展：开发者、高级工程师、首席工程师、杰出工程师，我们几乎把一生都耗在这个轨迹上。我们这个行业太年轻了，以至于我们甚至不习惯看到有人“退休”。但当时的我已经站在了巅峰。我已经体验了成名，我在想怎么功成身退。我甚至去 NASA 喷气推进实验室面试并拿到了 Offer。我想去那里为一个更大的愿景（比如送人类上火星）工作，而不是整天跟 Python、Go 这些代码打交道。就在我已经准备签协议去加州 NASA 时，Google 打来了电话。我心想：“去干嘛？我已经见识过你们的机器帝国了。”但他们说：“我们给你一个机会来做开发者关系（DevRel）。”这是我这辈子第一次听到这个职位。它代表着自由——没有死板的代码提交配额，没有 Jira 工单。当时 Google 团队非常聪明，他们让我自己定义我要做什么。

但作为有过创业心态的人，如果我真的用外面那套刻板印象来做 DevRel（比如到处做布道、写教程），我肯定会被开除。对我来说，那只能叫“活动”，我要做的是创造“影响”。所以我到了 Google 做的第一件事是问：客户在哪里？云计算是怎么赚钱的？我跑去找销售代表：“如果你需要任何懂 Kubernetes 的专家，随时打电话给我，我会飞过去，我会在白板前画 6 个小时。”我去了澳大利亚、加拿大做现场交流。因为我知道，要在这个组织里生存，我必须证明我的价值与收入挂钩。我不只把自己局限在 Kubernetes 上，我也在 Serverless、数据库等领域发力。到了最后，我就能够游走在各个工程团队之间，甚至开启了名为“移情工程（Empathetic Engineering）”的内部实践。我让 Google 最顶尖的工程师聚集在一起，要求他们不借助任何脚本手动安装一遍 Kubernetes，看着他们挣扎报错，然后引导他们意识到用户体验有多糟糕。接着促成了 `kubeadm` 这类易用工具的诞生。我还写了著名的《Kubernetes The Hard Way》。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: No. So by that time I'm at Coros Kubernetes has definitely taken off. I'm giving lots of keynotes now. Everyone wants to know my opinion. I'm making all these prototypes. I'm kind of moving things forward. There's a Kubernetes book now, right? I'm a co-author with Brendan Burns, Joe Beta at the time. I'm like, you know what? I am I'm thinking about my exit. So, in our careers, we do a lot of work to get into this field. All the certifications, the boot camps, the studying, some of us college, and then once we get in, we're thinking about career progression. Dev, senior engineer, principal engineer, distinguished engineer, and we spend almost our entire lives on that trajectory. And our field is so young that some of our pioneers are finally like no longer here for the first time. We're not used to that and we're not really used to people retiring. Like Rob Pike just retired. The concept of an exit for individual contributor or a leader in the tech space is we don't we didn't have a lot of those. Lionus is still at it. He's not retired, right? So we don't spend a lot of time thinking about the exit plan in our field. If you're a professional athlete, your body will tell you when it's time to go. And so when at core OS we reached this peak, I felt like I've done everything I've ever wanted to do
in in the tech industry.
In the tech industry from 1999 to being unsure of myself to seeing myself on the side of museum buildings, full landscape view because people are coming to see what I think about where technology is actually going. And so it comes full circle. You get a bit of taste of the fame. You can look at GitHub and you meet people. We use your libraries. We used your command line tools. I started my career like some people were not even born when I graduated high school and they started their careers from those books. And so I felt at the time that I had come full circle and I was starting to think about the exit part of that journey. I remember spending time with Jet Propulsion Lab, JPL, part of NASA. And I remember being there and and I was so excited because the movie The Martian, had just wrapped up filming there, and they gave me a tour of the facility, like the Mars rover, the new one before they launched it to Mars. They were QAing. It was just going in a circle around the track. And I'm like, had a little laser on there so it can split rocks. And they were showing me how they improved the wheels over time. I went to another lab and there were a bunch of scientists working in there and it looked like a fish tank and I described it that way was like yeah we we determined that if you want to replicate parts of Mars surface and I might be getting this wrong that the rocks that you find in like a fish tank we can replicate some of this stuff and maybe slightly different than that. As I'm watching these people work and he showed me like how spacecraft has evolved over the last 20 or 30 years and I'm like wow you all seem to have an actual purpose. For the first time I've seen people using technology not to just make more apps not to add numbers in a database but to actually have humanity do something. And so they were not all about Kubernetes and Docker and Python and Go. They were like we're just trying to get a person to Mars and back again. I remember in part of the interview process that their interview questions are if you had to deflect a meteor, how would you do it? But it has to hit one state. So now you're in the leadership position. What would you do? And you're just explaining the answer like you know I would kind of bring a bunch of experts and then you know you got to think about the ability to evacuate people and you have to explain yourself. And the core part of my answer was you would have to explain yourself almost 24-hour live stream. Here's the trajectory. Giving everyone the countdown. Explain every decision you're making. I chose transparency. I chose truth. I chose like, look, we have to deflect it. There's no way to make it zero. So, we've chosen this state and this is the evacuation plan. And we estimate that this number of people won't make it. We're just being honest with you. No need for conspiracy theories. It's live. And I was like, wow, what an interview. A 20-year career at that point. never had an interview that made me feel that way. And so I actually was going to go to NASA after Coros. I even signed the employment agreement. I was going to move to Pasadena, California and work at NASA on the Mars mission and lead up the infrastructure and the infrastructure teams. And of course Google called. I was like, hey, come to Google. And at that point, I was like, for what? You have hundreds of thousands of employees. I admire Google. I've been there before, but not in that capacity. I was going to go to the headquarters.
Yeah. not not not to the
not to the data center but to the headquarters and I and I've always admired people like Brian Grant, Eric Tune, Don Chin, all of these wonderful people that I got to work with through the Kubernetes community. In many ways, I felt like I was already working on the team because by that time I had commit access to Kubernetes. So, I kind of felt like all the things I wanted to achieve in that regard was there. And so, I was like, why would I come work there? I'm just going to be a cog in the wheel. I'm going to go there. I'm just going to disappear. you're going to just make me work on Google stuff all day long. What's the value in that? I've seen the peak of this. And they were like, we won't do that. I was given the opportunity to do Devril and it's the first time I ever did it. But devro represented freedom. No tickets, no write code measured against squee benchmarks. I was like, I don't want that. I want to be able to make impact. And so the team was smart. They were like, look, we got this area called Devril and we'll let you define what you do.
So you got to write your job description pretty much.
Yeah. But as an entrepreneur, I know how this goes.
How does it go?
If you come in and you really do Devril stuff, in my mind, you're going to get fired because if you limit yourself to the external perception of Devril, you go to conferences and you become more of an evangelist, you do tutorials and guides. For me, those are activities. I'm a person of impact. And so, the first thing I did when I got to Google was like, where's the customers? How do we make money on cloud? So, I need to figure out how to talk to the customers. So, hey, where's the sales rep? If you ever need anyone with Kubernetes expertise, call me. I will fly to Disney. I will go to Walmart on site and I will whiteboard for 6 hours because that's the revenue component. So globally went to Australia, Canada, doesn't matter. We don't even have a region there yet. I'm going to bootstrap it. So now I'm growing my impact on the revenue side.
And and the reason you said if you would have gone as Defo, you would have been fired because you would have not been generating any revenue. I just felt like I was going to be fired.
But but this is just like thinking as an entrepreneur as like you want to make money.
I want I want to make sure that I'm impacting the business. And for most businesses, revenue is the criteria. And no one ever made me do that by the way. It wasn't like Demetri. It's like no no. To me, I understood the value of revenue. So I would go out and I was able to do it in an authentic way. I'm just talking about the same things I was talking about before. And then product impact. This is cloud. Why limit yourself to Kubernetes? There's serverless, there's databases, there's metrics, there's there's so many things here. So now I'm like, I need to learn everything and I want to employ all of my skills. So it turns out my time in financial services means I can be an exec sponsor. I knew how to go from hello world to hello revenue. So if I got into an exec briefing, I didn't waste everyone's time showing them the latest feature of Kubernetes. Doesn't make sense. They want to know how these tools come together to lead to actual app impact and outcomes. And so I matured there and I also got smart. You got to go to other teams and you read the OKRs, right? So another team might say, "Hey, Kelsey, we're really trying to get more adoption on our metric stack." And I remember the first thing that I started implementing at Google was a thing called empathetic engineering. So you have a lot of smart Googlers. These people are brilliant. I mean extremely brilliant to the point where the hardest problem Google had in my opinion was what to build. Not how to build it, what to build.
They could do that.
And in some cases you end up with like five messaging systems and but the thing is what to build seemed to be the most pressing problem. And so the one thing that I tried to do was like how do you convince other engineers, you know, their manager, how do you get them to trust you? And I started these empathetic engineering sessions where the first one was like get the Kubernetes team in one room. All of them engineering off-site. I want you all to install Kubernetes but you can't use any scripts. And remember these some of them are distinguished engineers and principal engineers. Some of them worked on Borg. Some of them are just the original creators of Kubernetes itself. And it was so fun to watch them struggle because it's like do we install Docker first? What version of Docker? Can we put this on your bunt too or does it need to be Red Hat? And so an hour goes by, teams of four are like, "Nah, man. This is doesn't work." I was like, "Great, you all can stop. I'm going to show you how I would do it." And of course, I know how to do this because I get to prepare, right? So, not a knock against them. I'm just like, "All right, Debian, tune the kernel this way. Put Docker on there. Put FCD, put the API server, put all these things. There you go. That's how you do it." And I was like, "Yeah, I mean, of course, you had prepare, of course." And so, the question then was from an engineering perspective, how will we make this better? And then people are like well if we had OS packages this could have been appit install and we could have just used local machinery like that's a good idea. Someone was like we will make that happen. Another person was like even if you had those packages though you still need to know what order and where the config files go. So coupube admin was born which was a command line tool that gave you a procedural thing. But the other thing that I remember from my career was I don't want just a tool that abstracts everything from me. I want to know how it works. So I wrote the guide Kubernetes the hard way. And that guide is what I used to help teach people at GitHub in the early days pre-Microsoft how to like run Kubernetes on bare metal and and walk them through that guide. And so it was that empathetic engineering that helped me make a huge impact on cloud because I can go to every team, every org. And instead of guessing what their road map should be, given someone who had spent time in the field, given someone that had this enterprise background, hands-on experience across lots of tooling, I knew where people were coming from, I would say based on where Google sits in the landscape and in the competitive landscape, given what our abilities are and what our customers need, I think this is it. But I never said it that way. I would get everyone in the room.

</details>

**主持人**: 让人们通过自我探索去领悟。如果我理解得没错，你是不太关注所谓的职级晋升流程，而是只专注于去创造你能创造的最大影响？

<details>
<summary>Original English</summary>

**Host**: You you would have them discover it. have them discover it. So you
and nudge them.
So you you you knew what you think the key the most important problem areas were for example and then you orchestrated a session to help people.
I try to always know the two things in multiple product areas that would make the most impact aka revenue that would get adoption and so and then launches versus landings. You would put all these things in motion. They would land at different times. So launches is we ship the thing, people have a big celebration. I know that doesn't matter as much as the landing. People are actually paying for it. So when I got good at that cycle, the promotions were a little predictable because I would be able to make impact, right? Sometimes you build prototypes and sometimes you would contribute to things like cloud functions. But the overall goal though was to use every skill you had. So working with PMs, we got to add Go support to cloud functions. We're the team that made Go. Amazon has support in Lambda for Go. We need to do this. And also, I have a keynote at the next Gopher Con and I'm talking about serverless. And I have two choices. I have to use Lambda or we can use Go Functions. And so, we sprint. We get it done. We get all the Googlers reality. We get it checked in. It's in alpha. And I tell the PM, "Hey, you want to go to Gopher Con? We'll launch it on stage." We launch it on stage. We tell people how we designed our worker, how the internals work. and then they can just come sign up. That was the trifecta. You do the work, you have the vision, you execute, you launch, and you land.
Land.
And the landings compiled over seven years is how you go from like I think maybe L5 to distinguish engineer
L9. That's like four promotions.
Yeah. Four promotions, seven years. But it's interesting because a lot of times when you ask someone on, you know, how they got promoted, let's say, yeah, four four times in seven years at a place like Google, I would expect just being naive that they will tell you like, okay, this is how I planned or like this is what you need for each level. But sounds like it's it's a very different you just had landings that that created impact like and and you were focusing, do I read it correctly, that you were not focusing on your promotions or the next next level? You you just wanted to, you know, do the best work that you could.

</details>

**Kelsey Hightower**: 不，不，我依然瞄准了下一级的晋升。因为我作为有着企业家思维的人，如果你让我看到了山顶，我就会想尽一切办法爬到山顶去。所以是的，我完全是冲着“我该如何爬到下一级？”去做的。但我不屑于在写晋升材料时玩填字游戏。我会在包裹里写：“嘿，我是 Kelsey，我帮组织解决了这些极其难缠的问题，我帮助了哪些跨团队的伙伴，结果就是这样的收入和落地。”如果你写得足够真实、坦荡且充满了真正的商业影响力，晋升委员长根本无法拒绝。而影响力的本质，并不是你个人写了多少复杂的代码，而是你去赋能了多少人，影响了 Google 内部多少个部门的开发文化。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Oh, no, no. I was focused on your next levels because that was the goal.
Because think about it, if my whole career, I've always tried to acquire the skills and make the impact so I can move to the next level. And so at Google, the levels were expressed as promotions. And there was a point in time in the org that I was in, there was no level seven for an individual contributor. So now we have to make a level seven. And then once you get to a level seven, now you kind of pave the way for the other people that want to come up through that icy path. And then level eight isn't the same as level seven. Level eight isn't the same or level 9 isn't the same as level eight. And yes, there is a formula to some of the promotions early. So from 3 to four, four to five is a little formulaic. You have a ladder. There are things that are expected of you. And the decision making on those type of promotions are localized. Meaning your manager, maybe a director. But then outside of that though, when you start to go higher, it's now expanded where there's now other teams that have to understand your impact in a way that can't be biased by a local team. So if you think you've made a lot of impact and then people across the org do not agree, that allows you to really throttle what impact means, right? Because if it's just your team, I really like this person. Now everyone's a distinguished engineer. And so I think Google did a really good job of saying, look, it was okay to be like L5 or six for your entire career. Yeah, that's their terminal level. I think it used to be L5, now it's L4 actually. Okay. But they moved it back cuz I I think L5 has gotten a bit tricky and they don't want to fire really good L4s.
Exactly. So, and I think for a lot of people, you can follow the formula and get to where you need to be. But I was like, at the time, I think there's like a couple hundred distinguished engineers. So, as an entrepreneur, if you show me the top of the mountain, I want to get there.
So, then you were targeting, you're like, all right, how can I get to the next one? To the next one. and impact was the name of the game, right?
Yeah. And I guess the only thing I would probably add to the moment or to the situation was I wanted to do it authentically. And so there was one part of the time I remember I didn't get one of the promotions, but I was getting promoted pretty fast. So of course people like, "Dude, you need to actually make an impact before you get promoted again. Stop it." And that was good feedback. But I remember I took a chance. So there's a pattern to doing a promotion packet like structure. There's examples and you go through all of this stuff and you get feedback. I remember one year I was like, I'm not doing that. This year I'm just going to talk in like the first person. Hey, I'm Kelsey. I work on these things, not these things. These things are important to Google. So, here's exactly what I did, but more importantly, here's the people I brought along. Here's the teams I've impacted and here's the results of this. So, I did this project and here are the results of that. And I'm talking in this way like I'm ignoring the process. I don't really care about the template. And as someone who at that point in time was on some of the promotion committees where we're looking at the promotion packets and making a decision as a team, I decided to write my packet for those people so that when they got it cuz look, if you're having to do a read a lot of these, it's it's hard. You're like, "Oh man, they're all so dry. Everyone's being very safe. Everyone's only telling me what I want to hear. I don't even know the person from after reading this whole packet." I said, "I'm not going to do that. I want them to see me as if I was in the room advocating for myself. And I remember getting feedback on that package like, Kelsey, this is like, come on, bro. This is, you know, things. I was taking it seriously. It wasn't I wasn't making a mockery of it. I just wanted to make sure that they understood what I was doing and I was aware that I wasn't just trying to play the game. I was trying to approach this process authentically. And I got promoted off of that packet. And look, it could just be sometimes the work sometimes speaks for itself, but a lot of times people can't see the work if it's not presented correctly. And so that kind of slingshot I mean and the reason why I tell that story is that every distinguished engineer doesn't get there the same way. Everyone thinks like, oh, how much code did you write? What complex thing did you build? And for me, I think it was the impact on Google Cloud's culture. The empathetic engineering thing became an official thing that they used to onboard other engineers. It became things that had a whole team behind it. They used to go give them and a product manager that would evolve the program and integrate into HR the philosophy around other engineers saying, "Kelsey, we just did an empathy session. I want to show you the results of it because we're about to ship it." And then engineers started really thinking about the customer. I mean, Amazon was always known for that to some degree, but to help Google get on the same page, I mean, I'm pretty sure other people had an impact, but there was a direct line of impact from those type of programs and also me diversifying, moving away from Kubernetes into the serverless realm, moving to the world where you're helping out the Postgress or the Spanner team, add a Postgress interface, the Go team, getting a little bit better with cloud, just making other people successful around you is one of those things that helps you become distinguished. is the impact, the ability to influence.

</details>

### 拒掉微软 CEO 邀约，成就完美双赢

**主持人**: 在你晋升为杰出工程师之前，你经历过微软给你发 Offer 的事情。能给我们讲讲那段故事吗？

<details>
<summary>Original English</summary>

**Host**: Before you got to the distinguished level, you you shared a story about Microsoft in an offer. Can can you tell us about that?

</details>

**Kelsey Hightower**: 我是那种不喜欢下“最后通牒”（ultimatums）的人。在企业界往往会发生这种情况：假如你赚 10 万美元，然后你出去面试拿到了 12 万美元的 Offer。那么现在你面前有两条路。你可以直接跳槽去赚那 12 万，或者你可以带着这个去跟你现在的雇主下通牒：“你不给我 12 万我就走人。”这种做法常常会让双方关系变得极度紧张。而我并不想这么做。那次微软来挖我。我甚至连一份更新好的简历都没有，我都大概有 15 年没碰过简历这东西了。但是他们的招聘流程截然不同：“抱歉，这是一个特殊的流程，我们只是希望你能见到代表微软的正确的人。”

当我去到那边，见到了很多幕后高管。这更像是一个“反向面试”，是他们在极力向我推销他们自己。之后，我收到了一封来自微软 CEO 萨提亚·纳德拉亲自发的私人邮件，大意是“如果你来，团队会全力支持你”。附件里有一份 PDF。我打开那个 PDF，就像在你的职业生涯中经常会发生的一样，薪酬的数字后面加了一个“零”。我甚至都不知道还能开出这种天文数字！但我没有把这个当作筹码去 Google 那里下最后通牒。我非常真诚地找到了我那相处了六年、极其出色的主管。我说我并未刻意求职，但我必须考虑这个数字，毕竟它在财务上实在是太丰厚了。他看了一眼那个数字，笑着说了一句我永生难忘的话：“我想让你知道，你配得上这里的每一分钱。”短短几小时内，Google 匹配了这份超高薪酬。所以我不仅没有破坏信任关系，反而还得到了我应得的回报。几个月后我见到了萨提亚本人，他对我说了一句充满诗意的话：“我们给你的 Offer 就像是你正在逃离什么地方似的；但我们本来应该给你一个‘值得你奔赴’的理由才对。”

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Yeah. So, I'm one of those people. I don't like ultimatums. That's it's hard for an ultimatum would be you're working at a company for a couple years. You're doing a really good job. And I'm just going to make up numbers here just to protect everybody, but just say you're making $100,000. And for a lot of times, you could be happy with 100,000. And so a company says, "Hey, we're hiring." And you go there, you do an interview, and they say, "Look, we're paying $120,000." At that moment, you are actually worth $120,000. Cuz you now have evidence from the market. The $100,000 you currently make doesn't look so good anymore. You can't unsee a job offer for 120. And so now you have to make a decision. You can commit to that. Leave your job and go make 120 and start over. Or you can do the ultimatum thing. If you don't pay me 120, then I'm leaving. And that puts everybody in a weird predicament because sometimes it doesn't have to be that adversarial. Sometimes it's just this is evidence that, hey, look, I want to advocate for myself. I know we're not in promotion cycle, but I believe I'm worth 120 and I would like to have that conversation. And someone would say, hey, well, you need to go prove it. It's like, well, I have an offer if you want to see it, but I would rather be here. And that can turn into a you went to go look for another job. It's like, oh my god. So I'm stuck.
They can have weird dynamics, right? Especially with your manager or or your management chain.
Exactly. So I was always weary of that, but I also knew that in business, that's just how it goes. And so I'm really at the peak now. I'm thinking like early retirement. I'm probably can get out of here at what 55 60 if I continue on this pace.
Yep. And then Microsoft is like, "Hey, come through." And look, I never had an executive recruitment process. So by this time, I'm probably considered an executive at Google. Once you hit like L7, you're kind of considered like an executive.
What What is an executive?
So an executive just means that you probably have uh an admin to help you with some of the tasks you're doing. You're probably going to be asked to be an executive sponsor of things and programs. So if a team wants to have a program for something and there's going to be a budget for that, you may have to help oversee that program. So they need executive sponsorship. Another engineering team knows that they're going to need budget for something and they need someone that has a little bit of political capital, a little bit of weight in the organization to help endorse them. So that can be executive sponsorship or you might be assigned to one of the largest c customers the company has. But that executive set of duties means that you're going to be making impact above and beyond yourself typically to support other parts of the organization. So I grew into that at Google. Microsoft was like, we want you to start there. And here's the thing, I didn't think about my role that way there. I'm still the old Kelsey from Coro West days, right? I'm just doing well here. And I wasn't going to interview at Microsoft. I'm like, for what? I'm at Google. I mean, I had a lot of freedom at Google. I was making impact at Google. I had a good reputation. And so, I'm like, "No, my trajectory is fine. I'm not doing that." And to be honest, I don't like Windows. I I didn't like Azure. I don't like .NET. I like GitHub. VS Code is nice, but my whole career, the majority of it, has been rooted in authenticity. I've been working on the things I actually like and care about. this would be one of the first times maybe outside of some of the enterprise roles that I'm going to go work on a set of technology that I wouldn't use on purpose. And so I went there and I met the Microsoft team. And the weird thing though is I had a recruiter and they swapped the recruiter out and it's like, "Hey, our mistake." I'm like, "What do you mean mistake? This person was super nice and they asked for a resume and I didn't have a resume cuz it's been seven years
cuz you had to create one."
Well, it's been actually 15 years at that point since I ever had to show someone a resume. So, I'm like, "Reme? Oh, man. I haven't made one of those in a long time. I'm looking online for a template. Like, what's the style of résumés these days?" And so, I'm like trying to figure out a resume. I'm like, "See, this is why I don't waste time interviewing. I don't got time for this anymore." And they swap the recruiter out and it's like, "Hey, sorry about all that. You we don't need no resume. Sorry, that's not this kind of process. What we want to do is make sure that you meet the right people who represent Microsoft." I was like, "Okay, that's different." So, I get on site. I'm like, "Okay, what kind of quiz questions are we going to be prepared for?" You're not doing quiz, bro. You had commit access to Kubernetes. You wrote the book on Kubernetes. You're leading these things. You helped start K. Come on. Like, you have a Wikipedia page. Like, there's We don't need to try to figure out whe you made the impact. We can just look at GitHub. There's evidence there. And so, I'm meeting all these leaders. They're bringing all these people who are behind the scenes. I remember meeting Scott Gunry for the first time. And I didn't really know who he was because I just didn't know how I didn't know the lineage and the history of of Microsoft. And you know, of course, I'm looking up who these people are and and I was like, "Wow, this is they're courting me. Oh, this is what that feels like." I mean, Google did it a little bit too, but not like this was like I'm I'm looking I'm looking at the these are the executive directors of
this is like reverse interview. They're not interviewing you. They're trying to sell themselves.
You know what? And that's the thing that I appreciated a lot because they were like this is your career. You built a fantastic career over there. We can't ask you to throw that away without understanding what you would be doing here. And so it was like you can if you want to understand the business if there's someone you haven't gotten a chance to talk to just give us a name. And I'm talking to them and the one thing that I really respected about Microsoft was I think by that time they had also acquired GitHub. And so they had a big vision for themselves, a lot of diversity. And I was like, "Okay, there's a lot of opportunity here." They're also all in on Kubernetes. They had just acquired people like Das and Brendon Burns is there. So I was like, "All right, Kelsey, you can come and make an impact there. There's room to grow." I'm like, "All right, I might do it." All right. So I'm glad I did the interview. And I get home and it felt like that time I doubled my salary. I told you on the way home and I remember I get this email from Satia, the CEO of Microsoft. And I'm like, man, he wrote this nice email, Kelsey, that I heard you had a good experience with the team. Remember, I did the interview at the Microsoft headquarters, right? So, hey, heard really good things from the team. Just wanted to let you know, you know, you're going to be respected here. We're going to support you as a team. I'm like, damn, support as a team coming from the CEO. And the offer was like a PDF. It's an attachment. So, I read this thing and so number one, what an honor. This is the CEO of Microsoft. Yeah, so many more important things to be doing than to be emailing me about a role. And I open a PDF and as a like very often in your career there's a zero get added to the equation. And so you're looking at this like I didn't even know that they do that. We know that it happens, but the person that graduated from high school in 1999 that chose the A+ certification didn't know that was available even while I was at Google having all this success. And Google paid me pretty well, too. But I know you can add another zero still. And so I'm like, whoa, this is this is crazy. And I'm like, wow. So I um I showed my wife and she was the one that said, "You should just go interview. Like put your ego to the side and let's go see what's out there." So, shout out to my wife. And so, I get the PDF and I'm like, okay, this number is perfect. Honestly, I don't know what to say, but let's just just find out like, is this really the only number? So, I remember given a counter like, you know what, I think it should be this. And the funny thing is Microsoft counter back higher. So, we're not playing around. I'm like, oh, whoa, now I understand that I don't understand this part of the game.
Yep. And so I have this offer and I knew that I wasn't going to go interview there if I wasn't serious about taking it. So I was serious about going to Microsoft been almost 6 years at that time at Google and I went to my manager. I had the same manager which is legendary at Google. I had the same manager for 6 years straight even with all the reorg manager the whole time. He was a director. So even when I got leveled up they allowed at least someone one level above still to report to a director. And I had a such a good relationship with them and I told them what happened. I said I wasn't looking and they asked me to come in. So I went in and I'm going to take it. Number one, it will be financially irresponsible to not do this. So that will be the driving force and also I get to stretch myself in another way and see if I can make an impact again. He's like, "Okay." Um, but it was no ultimatum. I was like, "I'm leaving." And he's like, "I'm just curious what Google would say." I said, "No, not great. I don't want to do Ultimatum."
Yeah. You don't believe in it?
I mean, I do believe in it, but I didn't want to do it.
You don't want to do it? Yes.
I didn't want to do it
cuz you understood the dynamics.
The dynamics, especially I in in many ways, Google had been really, really good to me in every facet. So, it wasn't ultimatum time. It was more like I've earned it. And he said that too. I gave him the PDF and he looked at it. He just started smiling and like, "Oh, wow. Whoa." And then he said something that was really dope. He says, "I want you to know you're worth every penny of this." And I was, "Oh, the whole
That's That's
a game changer because he knows me like no other person I've ever worked with. No one knows me as well as Greg does. He knows my strengths. He knows my weaknesses. He knows my ambitions and my motivations. He knows all of them. For him to say that, it was important." And so I'm thinking if Google wanted me to be at that level, they would have done it already. But also, pragmatically speaking, no one really knows your situation. Like all these people have thousands of people they manage. They're not targeting you or being mean to you. At least in my case. And so maybe they thought I was making that kind of money already. Maybe they thought that I was already a distinguished engineer. That how would everyone in the or know? They got other things to worry about. So he presents the thing to them and I think within hours they're like this is no problem. Like hey here's the you know don't worry about that number. Here's a bunch of stock and all these things and I'm looking like whoa whoa. So now I have the money and I'm at the company I want to be.
And you didn't do an ultimatum.
I didn't do the ultimatum. So I felt good about the relationship. I didn't feel like um there was going to be some retaliation. I had no fear about that. And I continued to be successful. eventually got promoted to distinguished engineer at Google told the Microsoft team no but the one thing that people saw from this I didn't talk about this at that time but I did do a tweet and the tweet was different company same team a lot of people's like what does that even mean different company same team but people were you know retweeting it and they liked it and people oh it's because of the community stuff and how the different people in the community work together and that was part of it but a big part of it was that moment that Microsoft got me the biggest raising my career at Google and about 3 to 6 months later I was in San Jose and Satia was there and his admin is like hey um Sate would like to just you know meet me with you I'm like the CEO of Microsoft got time to do anything so I'm in San Jose and then I go to this hotel and the admin meets me downstairs like hey Santi kind of ready to see you now and I'm going up and now he know I'm coming right like let's just say the meeting is at 1:00 He knows I'm coming for like days and then you go into the hotel room and like the the doors are open overlooking a mountain range and Sati is sitting there overlooking the mountain range like a vanity fair photo shoot and I remember before on on the plane ride there I'm reading his book hit refresh and I remember the opening chapter he talks about starting Microsoft as a developer advocate and now being CEO of Microsoft advocating for the soul of Microsoft because he had been there so long. You saw the birth of cloud and all these things. I was like, "Oh, this and the book was actually a pretty good read about his trajectory in the industry and his time at Microsoft." So, now I'm done with the book and I'm about to meet him. So, I have all this context in my head. So, when I walk through, I felt like I had this rapport with him for some reason because I read the book and then he's looking out over the mountain range and I walk through the door. was like, "Sate, why are you sitting here like this? You knew I was coming, so you're just posing like we're doing a photo shoot." And he just started laughing. And so the tension, at least for me, was way down. And we had a discussion. I won't repeat everything here, but he said something dope. He said, "We were sitting around at the table and we asked ourselves, what executive did we want that got away? That means that you still were in the minds of of at least some people." He's like, "You were on that list." And uh we had a discussion and he was very transparent and he said um we gave you a good offer. We think we gave you a good offer and at that time Thomas Karen had just come from Oracle. My personal opinion I liked his leadership at Google but I can understand why some people were afraid of the Oracle DNA being brought to Google. And I think maybe some people in the industry felt like oh this is a moment to go and maybe poach a few people that didn't want to make that transition. and he said something like, um, we gave you a offer as if you were running away from something and we should have gave you something to run towards. And I was like, damn, that that's poetic. And so we wrapped up that meeting and I really felt like, man, I actually belong to the industry. It wasn't like I'm a Googler or Kubernetes person. I really felt after that moment that I was an industry person. So I was very comfortable at that point retiring within the next year or so.

</details>

### AI 时代与软件工程的未来

**主持人**: 你目前在深入了解生成式 AI。考虑到所有正在发生的快速变化，并且有些经验丰富的开发人员对它可能会商品化他们的工作感到恐慌，你如何看待生成式 AI 以及软件工程的未来？

<details>
<summary>Original English</summary>

**Host**: You talk with Sachio Nadell and about a year later you retired. How how did that thinking come up to because you were mentioning that you kind of had your retirement. You were thinking about your kind of endgame or exit game.
... (Host jumps into the AI query towards the end) ...
One one thing that a lot of experienced software engineers are worried about right now is all the AI we're all using AI agents. They do generate code really quickly. Uh which is something writing code used to take a lot of effort. It took a lot long time to be good at it. Now with code reviews, there's now more tools coming in and some people are like worried like okay like what is happening to my profession like the craft of writing code seems to be something that we can offload and more and more people are offloading including prominent people. What will this do to software engineering and what advice would you give to people who are experienced software engineers? They're a little bit worried because it's it's a big shift. they still want to, you know, like be the whatever great engineer will look like in the future, but what steps might be able to take and especi especially like your your take because you're I think you're pretty grounded in just looking at this from a vantage point that some of us are not.

</details>

**Kelsey Hightower**: 首先，软件开发者需要有点自省精神。在过去的 20 到 30 年间，你亲手通过自动化消灭了许多其他行业。智能手机吞噬了相机、指南针、录音机和地图，报纸也在衰落。你从未对那些被软件颠覆的人表现出太多同理心，那你现在也不应指望别人对你产生同理心。所以你首先要搞清楚这一点，才不会因为整天抱怨而让别人觉得你是个疯子。

其次，问问自己：“我的工作到底是什么？”有些开发者以为自己唯一的工作就是写代码。因为他们是公司里唯一能做这事的人，所以他们觉得自己很安全。他们不去学网络，不学产品，不学与客户沟通。他们唯一的护城河现在被 AI 商品化了，所以他们自然极度恐慌。但如果你是个“全栈”（Full Stack）工程师（不仅仅是前端加后端，而是懂得业务全流程的人），你会松一口气。你会觉得：“太好了，我终于可以把那些繁琐的代码交给 Claude 去写，而我能将注意力集中在架构设计、数据库选型、以及这件事情是否真的值得做上面了。”

你要明白，**编写代码是一种决策行为**。生成代码的速度确实能大幅提升，但这并不代表你不需要停下来思考：“我应该用这套数据结构吗？”或者“即使我能光速写完这个功能，但它以后会不会成为维护的噩梦？”AI 并未改变软件工程的本质，我们的工作从来都不只是写代码，我们的工作是**解决人类的问题**。所以，不要过度依赖 AI 到失去最深层的基本功。你要知道，如果你不懂色彩怎么调和，去买 1600 万种颜色摆在桌上是没用的；但如果你懂得了调色，那每一种新工具对你来说，都只是用来画出更美画作的一支笔。这就是我对这个时代软件开发者的务实建议。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: I think as a software developer, the first step you have to do is have a bit of reflection. For the last 20, 30 years, you have been automating a lot of industries away yourself. all those programs. I remember seeing an maybe it was like a diagram of every device that has been replaced by the iPhone. The radio, the calculator, the compass, all of these tools people used to buy individually. The top 30 of those electronics from the last 40 years are all in your iPhone. All of them. That means some electronic makers have gone out of business. They're gone. You did that. Not in a malicious way, but you were part of that. And so the software developer has been glorified for a very long time. The internet some people would say caused the downfall of magazines and newspapers because of the convenience of having a software approach. And so you have been part of the change to other industries and other people yourself. What did you think about that? Did you even think about it at all? So let's not be surprised if you find no sympathy from all the other professions that you've helped force change upon. So I think that's step one. You have to go do that reflection because if you don't do that reflection, you won't know how to behave now. You're going to be complaining and people are going to look at you crazy because where was this empathy before? You might be very excited about this and not realize you're only excited because you're in position to benefit from this. So if you work at an Anthropic, of course this is the future because it's in your hands. If you're at Nvidia, of course this is the future because you will be selling the picks and shovels. And so you got to ask yourself, why am I excited? Now what I don't want you to do is necessarily feel guilty about it, but I need you to see the big big picture. It's going to help frame everything else. The second thing I want you to do is ask yourself, what was my job? Remember, there was a point in my career where I was lying to myself. I thought my job was to be the less best Linux administrator ever. You as a software developer, you may have thought your job was to be the only person in organization that can write code. And since no one else could do it, you were safe, right? And so you didn't learn any other skills, networking, product management, design, talking to customers. Nope. All you had to do was write code and you were safe. And you probably made more money than everybody and you were fine with that. Now you got caught. The only thing you were good at is now been commoditized. And again, you did this to others. So let's say the vision you have for yourself is only in this very narrow realm. You're going to be very afraid of this trajectory because all you know is software developers write code. That's it. Some software developers still don't write test, still don't know how to deploy anything. And so they are really afraid because they can't see any other way that this plays out. Now if you're a full stack engineer, you're probably like, man, there's so much more than just writing code. You have to do architecture. You have to do design. You have to do so many other things that I love clock because now I can focus on those things and I can use these tools instead. So I can see why that person would have that perspective. Now, I understand why that full stack person has a perspective of watching the same people commentate that the code generation piece replaces everything else. They're going to be like, "No, you don't know what this job is." It's way more than just writing code. Writing code is the last step. If you're a security engineer, you're probably like, "We never figured out security for the pace of the current enterprise."
The one before.
Yeah. like everyone thinks they're moving slow. I remember I took a security um training thing and most of them aren't that good because they can't go super deep. They just tell you, "Hey, here's how to avoid fishing. Here's how to not leak information, adhere to various laws and things like that." And then they said one thing this time that I learned that was pretty good. They're like, "What's the key to protecting yourself?" And they say, "You know what? Just go slow." A lot of attacks are, "I'm about to board a flight and let's say you're an admin or you're a VP and the CEO texts you right now. We need to wire the money to Oracle to pay for the license. They're going to cut it off right now. This needs to be done immediately." You look at your phone, it's definitely from the phone number of the CEO. You have a good relationship. Everything looks right and it's moving fast. So, you're like, "Man, I'm on a 10-hour flight. I need to do this now. Turns out the attacker knows you're about to board this flight. They've seen all your previous text messages. They know how your manager talks to you. They know that you've moved fast in the past. And so they now are primed to get you to do the exact same behavior again. And you could be the VP of security. So you should know better. And sometimes that naive confidence will make you feel like I'm obviously not being fished. I've done this many times. This is definitely the CEO. Who would know how we actually operate? And who would know that I can actually do that? So what do you do? You make the transfer. And just like that, 10 million has been wired to the wrong place because you moved fast. It wasn't because you were not smart. It wasn't because you were not productive because in this case, you were productive, but you did the wrong thing. So when I think about code, there is value in having a healthy pace. Let's say you're an insurance company. You sell insurance. Hey, make model. How old are you? Have you had any accidents? Okay, here is your insurance for the year. Simple, very simple thing. If you're an insurance company, that's all you are. You're kind of close to being done. Now, you could say with JAI, we should get into payments. We should compete with Door Dash, right? We have all these tools. Let's go and
we could build it.
Yeah, we can build it. So, but the thing is, should you just build it? because you can and the answer is typically no. So we usually optimize ourselves as humans around the pace needed for the task and when we don't need to do that work anymore we move on to something else. So now I think what we're going to end up with is people not realizing a lot of this stuff we were doing in software engineering was decision-m what database to use what schema should we really collect someone's social security number or should we avoid it not yeah I can write code to parse a social security number really fast like no no should you even do it and so when you write code it almost makes you slow down again because there's been times where I thought I had a good design that's that phrase writing is thinking So is writing code. So as you're writing the code, you're like, "Hey, wait a minute. This loop is ridiculous, right? Not only is it going to make the computer warm, this is not the right thing to do. There's a better data structure than the algorithm that I'm using." So then you stop and say, "Hey, the data structure is wrong. We need to change the architecture from the top down. So decision making sometimes does benefit from slow. And when I'm saying slow here, we're not talking waterfall 6 months.
Yeah. No,
we're just talking about maybe one more day before you go at it. And I think some of us are going to miss that part because clot spit it out, ship it.
Yeah. And that's also one one thing that you always have the the more experienced generation be worried about the young generation. I remember when I joined the industry, ReSharper had come out. ReSharper uh and the experienced old guard was like, "Nah, you're you're not a real developer if you use ReSharper cuz you know you're not going to learn the library and you need that and and you know, like that's what makes you a real developer." And then I remember when I was now five or plus years of experience and stack overflow started to become big and I was like nah you don't want to go to Stack Overflow because you're not going to you know learn the real thing. So but now what the current old guard is saying which is you know we're I'm I guess I'm part of it is like well if you use AI you're going to miss learning the basics and when you have learned the basics it's so much easier to use AI. And I wonder if we're just repeating the same the same mistake as as the previous ones did which is the new generation usually figures out the tools they understand how to do it or are we rightly concerned that some people who are coming into this AI native they're now learning to code they they can jump through so many layers that they will just not you know see what's under understand or are we just like making assumptions that might not be true.
Here's where I think we can it can be right on both sides. Do you need to learn how to code to make an impact in this industry? The answer is no. You do not have to. There are some people who use these no code platforms where they drag and drop and they produce a really good app. There are some people who have built a consultancy business by just using Wix, right? They go there, their website actually looks pretty good and so they got really far with that. Now, for what they're trying to do and accomplish in life, they'll probably be fine. But let's just say you are a software engineer. And the idea behind software engineer is not limited to just producing apps. Software is the interface between hardware and things people want to do. So there's a whole bunch of things you need to learn. So if you want to be that type of software engineer, you got to learn hardware, too. If you don't understand hardware, you can never work at that level. And look, if that's not your job, then so be it. But you will never have that creativity. I remember seeing someone was like, "Hey, you can do isolation without a VM." I was like, "How would you do that?" He's like, "Oh, because when you boot the kernel, there's a thing you can do before the kernel loads to isolate it in a way that you can lock down processes." The only reason why this person knows is they know the full boot sequence from firmware to switching to the kernel and the tricks you can do in between. Now, for me, that doesn't work at that depth. I'm thinking there's only virtualization, CPU isolation, things like G Visor where you intercept system calls. But never did I think about the boot sequence. And so yes, you can get very far, but as someone like we applaud every version of Opus that's released or chat GBT, but there are versions of yourself that get deeper from these new trainings. So no, you don't have to. But if you ever want to get better at anything, and sometimes that depth, that nuance is the thing that leads to an invention, right? If you know how a compiler works, if you know how memory management works, that might give you enough information to say, "Oh, I can make a new programming language." If only thing you know is the surface, you can't even imagine how you can create another programming language that is better fit for the task at hand because you never gone that deep. I'm not saying everyone wants to do that. So I think it is fair to say all I want to do is come in get a job and if that job can be done by using AI tools I think the side effect of that is then that job will be commoditized. It has to that's just the way it's going to go. But I've always seen myself for my entire career I want to learn more. I want to go deeper. I want to go so deep that I can create. And I think a lot of people who are doing this, the reason why we're having this reaction, some of us, some of us, part of our careers have been the creation part, there is no spec for this. There's no protocol for this, but we're going to make it work. A lot of people that are doing like the reverse engineering, the hacking, there's like there's no framework for what I'm about to do. I just know how memory works and I don't care what your security tool does. I will make it do what I want it to do. You need to go way below the surface. And so for a lot of us that are saying this, we know the value of the fundamentals that lead to the other stuff. And so if you tell a next generation, oh, you don't need to learn these things. It's like that may be right in the short term, but we know for a fact your career will be limited and that may not be a problem and you have to decide. But make no mistake, if we put this much effort in training the model so that it can spit things out, you better make sure that you are willing to train your own model. So my advice to people would be and maybe we should talk about it different. Maybe we shouldn't have so much fear-mongering around it. Maybe we wouldn't should put it a versus this. We should just say great artists tend to know how to mix colors and it isn't your benefit to understand the primary colors so you can mix them to get the other colors. And it's a superpower, right? So you don't have to go buy, you know, imagine an artist trying to go buy 16 million colors and put them on the desk because they don't know how to mix colors. If you teach a person how to mix colors, like you can get any color you want. And I think that's the way we had to approach it. It's just another skill that if you had it, you might just unlock some creativity. So I encourage you to learn it.

</details>

### 总结与尾声

**主持人**: Kelsey，非常感谢你。这是一次极其精彩的对话。

<details>
<summary>Original English</summary>

**Host**: Kelsey, thank you very much. This was just an amazing conversation.

</details>

**Kelsey Hightower**: 太棒了。谢谢你邀请我。

<details>
<summary>Original English</summary>

**Kelsey Hightower**: Awesome. Thanks for having me.

</details>

**主持人**: 我承认整个对话过程中我都紧紧地钉在椅子上。抱歉花的时间比较长，但我希望你们也认同这一期的时间花得非常值得。Kelsey 的过往履历实在是太不可思议了。他由单亲母亲抚养长大，为了去挨家挨户安装 DSL 线路在 19 岁就从大学辍学，最终却成为了 Google Cloud 的杰出工程师——这家公司里只有几百人能拥有这个头衔。3 年前，当他觉得不再需要为别人工作时，他在巅峰时期退休了。这是多大的鼓舞啊。

我做了笔记的一点是，Kelsey 谈到“每一次工作都是一次面试”。当 Kelsey 在 GopherCon 做演讲并从幻灯片通过 PXE 启动 CoreOS 时，他根本不知道 CoreOS 的团队就坐在台下，而他正是那样加入了 CoreOS。当他在晚上和周末为 Puppet 贡献代码时，他不知道有一天 James Turnbull 会走进他的办公室并认出他的名字。他只是不断地出现，并在公开场合做出色的工作。这是一个值得铭记的教训：在工作中尽你所能做到最好，它很可能在你不知不觉中就成为了你职业生涯下一步的敲门砖。我还对微软发 Offer 的故事很着迷。Kelsey 并没有用微软的 Offer 在 Google 下达最后通牒，尽管他完全可以这么做。他只是告诉了经理实情，然后 Google 匹配了那个数字。显然，在这个级别上没有放之四海而皆准的薪资谈判建议，但做一个诚实坦荡、具有极高诚信度的人是值得铭记的原则。

Kelsey 对极简主义的坚持也给了我启发。他把钱看作自由的象征，确保他的生活方式永远不会随着薪水的增长而膨胀，这让“提前退休”成为了一种真实的选项，而非幻想。最后，Kelsey 对 AI 的看法既接地气又务实。AI 并没有改变软件工程存在的初衷。这份工作从来不仅仅是为了写代码，这份工作过去是、现在也是为了“解决人类的问题”。理解了这一点的工程师将会安然无恙。如果你喜欢这期播客，请务必在播客平台和 YouTube 上订阅。再次感谢各位的收听与打分！

<details>
<summary>Original English</summary>

**Host**: I will admit I was glued to my chair for the whole of a conversation. Apologies that it took this long, but I hope you agree that this specific one was worth it. Kelsey's past was just so unlikely. He's someone who was raised by a single mother, dropped out of college in favor of installing DSLines doortodoor at 19, and still ended up as distinguished engineer at Google Cloud. Only a few hundred people who hold a title at the company. And he retired at the top 3 years ago when he decided that he no longer needs to work for others. What an inspiration. One thing I took notes on was when Kelsey said how every job is an interview. When Kelsey was giving the Gercon talk and PXE booting Cor from his slide deck, he had no idea that the Coros team was sitting in the audience and that's how he ended up at Coros. When he was contributing to Puppet at nights and weekends, he didn't know that James Turn would walk into his office one day and recognize his name. He just kept showing up and doing the work in public. It's a lesson worth remembering. Do the best work you can at work. it might unknowingly be your job interview for your next step in your career. I also found the Microsoft offer fascinating. Kelsey did not use the offer from Microsoft as an ultimatum at Google, even though he could have. He just told his manager the truth and then Google matched the offer. Obviously, at this high of a level, there's no universal composition negotiating advice that always works. But being a straight shooter with high integrity is something that is good to keep in mind. I was also inspired by Kelsey's focus on minimalism. He treats money as freedom tokens and made sure that his lifestyle never inflated with his salary so that early retirement was always a real option, not just fantasy. Finally, Kelsey's AI takes his point is grounded and pragmatic. AI does not change what software engineering is actually for. The job was never just to write code. The job was and is to solve human problems. The engineers who understand this are going to be fine. Do check out the show notes below for related the pragmatic engineer deep dives on Kubernetes and other related topics. If you enjoy this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show.

</details>
