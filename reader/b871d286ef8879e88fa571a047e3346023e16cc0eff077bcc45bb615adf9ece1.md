---
author: All-In Podcast
date: '2026-05-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4oq91rzQcO8
speaker: All-In Podcast
tags:
  - ai-regulation
  - job-market
  - open-source
  - prompt-engineering
  - anthropic
title: 'All-In E275: 梵蒂冈的AI通谕、Anthropic的“数字上帝”与就业叙事的逆转'
summary: 本期访谈探讨了教皇关于AI的通谕，剖析了Anthropic创始人的“数字上帝”倾向及其背后的监管捕获策略。嘉宾Bill Gurley分享了AI赋能职业发展的见解。主持人们就AI导致的失业潮是真实存在还是企业的“AI洗白”裁员展开激烈辩论，并深入分析了开源AI与中心化权力之间的博弈。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Bill Gurley
  - Dario Amodei
  - Sam Altman
  - David Solomon
  - Jason Calacanis
  - David Sacks
  - Chamath Palihapitiya
companies_orgs:
  - Anthropic
  - OpenAI
  - Goldman Sachs
  - Apple
  - Meta
  - Amazon
  - Benchmark
products_models:
  - Claude
  - GPT-4o
  - WhisperFlow
media_books:
  - Running Down a Dream
  - Magnifica Humanitas
status: evergreen
---
### 播客幕后与滑铁卢大学的“秘密武器”

**Jason**: 兄弟姐妹们，今天我们神圣地团结在一起，讨论这个最神圣的日子——**All-In** 播客发布的日子。话题很多：AI 数据中心、中国、正义、人类尊严。**Dario**（Anthropic CEO）拆除这些 SPV（特殊目的载体）对梵蒂冈可不是什么好事。我们是在 200 亿估值时入场的，那可是 50 倍的收益。那么，让我们开始吧。

<details>
<summary>Original English</summary>

**Jason**: Okay, we are gathered here today in holy unity, brothers and sisters, to convene and discuss on this most holy day, the day the All-In podcast drops many topics. AI data centers, China, justice, human dignity, Dario unwinding these SPVS hasn't been good for the Vatican. We got in at 20 billion. That was a 50 bagger for us. So, let's get started.

</details>

**Sacks**: Jason，我很确定在教皇通谕发布之前，你就已经认为自己是上帝在人间的副手了。所以这对你来说没什么新鲜的。

<details>
<summary>Original English</summary>

**Sacks**: Jason, I'm pretty sure you believed you were the vicer of God before the encyclical. So, this is nothing new for you.

</details>

**Chamath**: 让赢家继续跑。

<details>
<summary>Original English</summary>

**Chamath**: Let your winners ride.

</details>

**Jason**: 我们向粉丝开放了源码，他们已经为此疯狂了。烟雾从 **Chamath** 的池边小屋和扑克室升起。他过去三天一直住在我的池边小屋。

<details>
<summary>Original English</summary>

**Jason**: We open sourced it to the fans and they've just gone crazy with it. I'm going all in. The smoke has risen from Tratad's pool house and from the poker room. He's staying in my pool house. He's been there for the last 3 days.

</details>

**Chamath**: 感觉太棒了。他甚至都不知道——你知道吗，我现在理解 O.J. Simpson 的处境了，如果你让 Kato Kaelin 在你家里住得足够久，你就会失去理智。在某个时刻，总会有人要被“干掉”。好吧，闲话少说。住在那里真的很棒，但 Chamath 没意识到，厨房里有一个登录了 **Uber Eats**、**DoorDash**、**Instacart**、**Amazon** 的 iPad。

<details>
<summary>Original English</summary>

**Chamath**: It's been magnificent. He didn't know. You know what? I understand where OJ was coming from. You know, you put Ko Kalin in your house for long enough, you just lose your [ __ ] At some at some point, somebody's getting whacked. All right, enough with the shenanigans. Uh, but it's been great staying at the house because there's actually Chimant is not aware of this. There's an iPad in the kitchen and that's logged in to Uber Eats, Door Dash, Instacart, Amazon...

</details>

**Jason**: 等等，别说了。

<details>
<summary>Original English</summary>

**Jason**: Laura Piana. Come on, stop.

</details>

**Chamath**: 不，是真的。上面有每一个服务。我告诉管家：听着，未来 72 小时内进来的任何包裹，如果上面写着 **JCAL**（Jason 的代号），直接送到池边小屋。所以这些包裹一直在进来。然后我重新贴了标签，把它们寄到了他的农场，现在管家正在把那些东西运往农场。

<details>
<summary>Original English</summary>

**Chamath**: No, there is. It's literally every single service. And I told the house manager like, listen, any packages that come in the next 72 hours, right to the pool house, if it says JCAL, right to the pool house. So, all these packages have been coming. Then I relabeled them, gave them back, sent them to the ranch, and now the house manager is sending that stuff to the ranch.

</details>

**Jason**: **Loro Piana** 想知道为什么我的裤子内缝从 36 变成了 12。

<details>
<summary>Original English</summary>

**Jason**: Laura Piana wants to know why my inseam went from 36 to 12.

</details>

**Chamath**: 你的腰围从 32 变成了 36。好了，欢迎大家来到节目。**David Sacks** 也在。David，你怎么样？

<details>
<summary>Original English</summary>

**Chamath**: Your waist size went from 32 to 36. All right, welcome to the program, everybody. David Saxs is here. How you doing, David?

</details>

**Sacks**: 我很好。

<details>
<summary>Original English</summary>

**Sacks**: I'm good.

</details>

**Jason**: **Chamath Palihapitiya** 回到了 8090 办公室。过去两天我也在那里，那里的氛围（vibe）太棒了，有一种很好的文化。如果你是“Bestie”（节目的忠实听众）并出现在那个办公室，那里的人都是这个节目的超级粉丝。在那儿就像皇室成员一样。每个人都跟我打招呼：“嘿，我是这里的开发人员，我是节目的忠实粉丝，谢谢你怼 Chamath。我们不能怼他，因为他付我们的房贷，但每当你怼他，我们就很开心，我们在秘密的 **Slack** 频道里为你欢呼。”

<details>
<summary>Original English</summary>

**Jason**: Chimoth Poly Hopetia is back at the 8090 office. I was at the 8090 office the last couple days and it's a vibe. It's a vibe. There's like a great culture going on. If you're a bestie and you show up at that office though, everybody there is a huge fan of the pod. So I was like it was like being royalty. It's stopped by everybody. Hey, I'm a developer here. I'm a big fan of the show. Thank you for giving it to Chimath. We can't give it to him because he pays our mortgage and everything, but every time you stick it to Chimath, we love it. We're cheering for you in the secret slack room.

</details>

**Chamath**: 竟然还有一个秘密的 Slack 频道？

<details>
<summary>Original English</summary>

**Chamath**: there's a secret slack room.

</details>

**Jason**: 绝对有一个秘密 Slack 频道。氛围真的很棒，你们开发了大量的软件，拥有很多年轻的人才。我不想说出你们的“秘密源泉”在哪里，但你们确实拥有一群非常聪明的孩子。

<details>
<summary>Original English</summary>

**Jason**: There is. There is definitely a secret slack room going on. No, but it was great. The vibes were awesome. You're building a lot of software. A lot of young talent. I don't want to say that where your secret source is, but there's a secret source of talent you have. And uh, man, those were some smart kids.

</details>

**Chamath**: 我很乐意公开：当初我在 **Facebook** 时，我们就成了**滑铁卢大学**（University of Waterloo）实习生最积极的招聘者。所以现在我故技重施。我们每季度招聘的实习生比全职工程师还要多，这是故意的，因为这会给产品带来巨大压力，迫使产品必须足够好。本季度有 400 人申请了实习岗位。

<details>
<summary>Original English</summary>

**Chamath**: I'm happy to say it. Look, when I was at Facebook, we became the most aggressive recruiter of Waterlue co-ops. And so, I went back to the well. Yeah. We recruit more interns every quarter than we have full-time engineers, which we do on purpose because it puts a ton of pressure on the product actually being good. We had 400 people apply this quarter for internships.

</details>

### Bill Gurley：追逐梦想与AI时代的职业心态

**Jason**: 哇，非常有意思。今天顶替 Friedberg 的是唯一的、无与伦比的 **Bill Gurley**。他最近一直忙于《**追逐梦想**》（Running Down a Dream）的工作。如果你还没买这本书，赶紧去买，写得不可思议。你现在结束了新书推广，终于有时间陪我们了。

<details>
<summary>Original English</summary>

**Jason**: Wow. It's very interesting. Uh with us sitting in for Freedberg, who's busy with some potatoes seed this week doing great stuff at Ohio, the one, the only Bill Gurley is here. He's been running down a dream. If you haven't bought the book, get the book. It's incredible. And you're off book tour, so now you have time for us. Yeah.

</details>

**Bill Gurley**: 是的，我告诉过你，如果你谈论教皇，我肯定得参与。

<details>
<summary>Original English</summary>

**Bill Gurley**: Yes. And I, you know, I had told you if you ever talk about the Pope, I'd love to hop on. And so

</details>

**Jason**: Bill 是福音派信徒，我是天主教徒，所以我们确实有一些共同点。Bill，你上次去教堂是什么时候？

<details>
<summary>Original English</summary>

**Jason**: well, you know, he Bill's an evangelical. I'm a Catholic. So, we do have some common ground here. Do you you when's the last time you were at church, Bill?

</details>

**Bill Gurley**: 每当 Jason 开始变得“亵渎神灵”时，我就得上来，确保他不要对教皇失礼。

<details>
<summary>Original English</summary>

**Bill Gurley**: when Jal gets sacriiggious? I got to come on there and make sure JCL doesn't get out of line with the Pope.

</details>

**Jason**: 听着，教皇是上帝在人间的信使，我们应该给予他基本的尊重。顺便说一下，刚才那是在模仿 Bill Gurley，不是真的 Bill。不过大家都知道，你在 **Benchmark** 完成了非常成功的几十年风险投资生涯后交出了接力棒，写了书，现在还成立了一个非营利组织。你创办了自己的“**追逐梦想奖学金**”（Running Down a Dream fellowship），这有点像 Peter Thiel 的 Thiel Fellowship。

<details>
<summary>Original English</summary>

**Jason**: Listen, the Pope is God's messenger on earth. We should give him a base level of respect. By the way, that's us imitating Bill Gurley. This not actually Bill Gurley. But hey, everybody knows you were uh you know, you uh handed the baton over at uh Benchmark after a very successful couple of decades in venture capital. You wrote the book. You've now got a nonprofit. You're doing your own spin, I think, on uh maybe what Peter Teal does with his fellowship. You started your own running down a dream fellowship, I understand.

</details>

**Bill Gurley**: 是的，它的目标人群不同，网站是 **rdad.org**。我们将向那些想要追求梦想但需要帮助的人提供 5000 美元的资助。申请流程和 Thiel Fellows 类似。申请通道上周已经开放了，如果有人读过书并深受启发，那就去申请吧。另外，我做了一个相关的 **TED** 演讲，很快就会发布。迈阿密的一位教授甚至根据这本书开设了一门课程，而且他是以“开源”的方式进行的。

<details>
<summary>Original English</summary>

**Bill Gurley**: Yeah, it's uh it's targeted at a different demographic. It's called uh rdad.org runningdownadream.org. We're going to do $5,000 grants to people who want to chase their dreams but need some help. And so there is an application process like Teal Fellows and other programs and we've been out talking to those people. Um but we're we're we're actually live. We went live last week for the application. So if you know people who have read the book and are inspired and need some help, have them apply.

</details>

**Jason**: 对于现在的“**末日论**”（dumerism）你怎么看？如果你是一个高中或大学的年轻人，在面对这种氛围时，该如何追逐梦想？

<details>
<summary>Original English</summary>

**Jason**: What's your take on all of this dumerism? Like if you're a young person and you're in college or you're in high school, is this is this much to do about nothing or how do you run down a dream in the face of something like that?

</details>

**Bill Gurley**: 我担心很多人在从事他们根本不在乎的工作。盖洛普民意调查支持这一点，他们创造了“**摸鱼式辞职**”（quiet quitters）这个词。59% 的受访者对自己的工作态度模糊。当你态度模糊时，你就没有“**高能动性**”（high agency），就不会全身心投入。

<details>
<summary>Original English</summary>

**Bill Gurley**: I fear that the a lot of people are in jobs they actually don't care about that much. And um there's a Gallup poll that backs this up. They came up put that word quiet quitters. They're like 59% of the people they surveyed are kind of ambivalent about their job. And when you're ambivalent about your job, you're not high agency. And so you don't lean in.

</details>

**Bill Gurley**: 看看 Jason 谈论他们如何实施 AI 时那种热忱和能动性。保护自己免受 AI 冲击的最佳方式，就是成为那个“**AI 赋能版**”的自己。但如果你态度模糊，你可能就是一只待宰的羔羊。问题在于心态。

<details>
<summary>Original English</summary>

**Bill Gurley**: you hear that enthusiasm and that high agency and then you want to go try these things. And I think the best way to protect yourself from AI is to be the most AI enabled version of yourself you can be. But if you're ambivalent about your job, you're probably not doing that and you could be, you know, a sitting duck. So I think it's the mindset that's the problem.

</details>

**Jason**: 我为我的公司创建了一个管培生项目（Associate in Training），收到了四五百份申请，竞争六个名额。我给了他们两个任务选择：一个是写一份投资备选公司的深度报告，另一个是为我们公司开发一个特定的**竞争情报**软件。令我震惊的是，80% 的学生选择了“**氛围编程**”（vibe coding）。

<details>
<summary>Original English</summary>

**Jason**: I created an associate in training program for my firm cuz we want to like help people get into venture capital and we gave them a choice of assignments. One of them was to write coverage of one of our portfolio companies that's breaking out. and then we gave them another option to vibe code a very specific project I've wanted to have for our venture firm for a long time on competitive intelligence and I would say I think like maybe 80% of the students applying and we had four or 500 people apply for six positions 80% of them did the vibe coding and I was shocked I thought it would be the exact opposite.

</details>

**Jason**: 谁都能写字，扔进 ChatGPT 就能出结果。但他们选择了开发软件，这很惊人。我的感知是，5 到 10 年前毕业的那批人感觉很迷茫，没有能动性。但现在的大学生，即使他们可能是通过 ChatGPT “作弊”度过学校生活的，但他们学会了通过“**黑客**”（hacking）手段使用工具，他们非常擅长利用工具解决问题。

<details>
<summary>Original English</summary>

**Jason**: Anybody can write, anybody can throw in JBT and get some output. But they they actually built software and th that's the scary thing. The students who graduated, at least this is my perception, the students who graduated like 5 10 years ago before AI, they're not AI first. They feel lost in a drift. They don't have agency. But the group coming out of college right now that cheated their way through school using Chad GBT, I'm joking, cheating, but I mean hacking. I I agree with that. So they were totally like, I know how to use these tools to get through my finals.

</details>

**Chamath**: Bill 说的非常重要。上周我说过，没人会问亚马逊的仓库工人是否真的想要那份工作。工作满意度不应该由外部人来评判，而应该问工作者本人：你喜欢它吗？你想留住它吗？现在这种 AI 末日论正在土崩瓦解。高盛 CEO 说了，现在各大前沿实验室都在说：“哇，这将带来一场就业大爆发。”

<details>
<summary>Original English</summary>

**Chamath**: Girly, I think you're saying something super important. I said this last week, which is nobody asks the warehouse worker at Amazon whether they actually want that job. And so to your point, job satisfaction isn't some external person judging your job to be valid and saying you must be able to have it. I think it should be asking the person that does the job, do you like it and do you want to keep it? And now this whole lie is kind of getting undone. The Goldman Sachs CEO said it. And now the entire Frontier Labs are all like, "Wow, it's going to be a bonanza of jobs."

</details>

**Bill Gurley**: **Mark Cuban** 有句名言：世界上有两种人，一种是用 AI 比以往更快地学习的人，另一种是用 AI 逃避学习的人。这取决于你是否有高能动性。你是用 AI 让自己变得更强大，还是把它当作一个“作弊码”？如果你属于后者，那你确实面临风险。

<details>
<summary>Original English</summary>

**Bill Gurley**: Mark Cuban had had a great quote. He said there are two types of people in the world. Those that use AI to learn faster than they ever could before and those that use AI to avoid learning altogether. And I I think it's this notion of high agency or not. Are you leaning in and using this stuff to be ever more powerful in what you try and accomplish or are you using it, you know, as a cheat code? And if you're in the latter, yeah, you're probably at risk.

</details>

**Bill Gurley**: 很多孩子感到疲惫，是因为我们将高中和大学变成了一场苦役，让他们以为毕业那天学习就结束了。但我们都知道，各行各业最顶尖的人都处于持续的学习旅程中。如果一个人不是主动自发地学习，那他可能还没找到自己真正热爱和着迷的事物。

<details>
<summary>Original English</summary>

**Bill Gurley**: I do think that a lot of kids get exhausted because we've made high school and college such a grind that they think the learning ends the day they they walk out with their diploma. And as we all know, the best and brightest in all of our fields are on a constant learning journey. And so I I think the real test is if you're not proactively self-learning, then you're probably not tilting against something that you really adore and are fascinated by.

</details>

### 提示词工程：10倍效能的生产力黑客

**Sacks**: 谈到应届生，我认为目前市场上最抢手的技能一定是精通 **Claude**。如果你进入一家公司，而你是唯一懂 Claude 的人，其优势不亚于几十年前唯一懂电子表格或文字处理软件的人。虽然这可能只是短期套利，但作为 AI 原住民，你拥有巨大的领先优势。

<details>
<summary>Original English</summary>

**Sacks**: With respect to new college grads, I was going to say that I think the single most marketable skill in the economy right now has got to be proficiency in Claude. If you're going into a firm right now and you're the only one who knows Claude, it would be like you're the only one who knows how to work a spreadsheet, the advantage would be enormous. Now, I think that that's probably a short-term arbitrage... but as a young college graduate right now, you have such an advantage if you're an AI native just knowing how to use these tools.

</details>

**Sacks**: 我们的制作人 Nick 过去三个月一直在用 Claude 制作每日简报。起初我以为那只是 AI 垃圾信息（AI slop），但实际上它非常令人印象深刻：它根据我之前在播客中的言论预测了我可能感兴趣的话题，并回溯了之前的转录稿来更新这些话题。它是高度**上下文相关**的。我问 Nick 是怎么做到的，他给我看了他为 Claude 设计的**自定义提示词**（Custom Prompt）和**技能文档**（Skills Document）。那些文档非常长且详细，虽然不是代码，但非常具有技术含量。

<details>
<summary>Original English</summary>

**Sacks**: our producer Nick has been doing with using Claude for you know he's been creating this daily briefing document. But actually the thing that was really impressive about it was that it predicted topics that I would specifically be interested in based on my previous comments on the pod and also it went back and looked at previous transcripts and what I had said and then had updates to those topics based on specific things I had said. So again it was highly highly contextual. But then I asked Nick, how did you generate that? and he showed me the the custom prompt that he designed for Claude and then the skills document and they were very long and detailed documents. They weren't written in code but they were very technical and I just realized looking at that that the average person is not going to be able to generate this.

</details>

**Jason**: Sacks，有趣的是，你只需要问你的 AI——问 Claude 或 ChatGPT：“嘿，我要你给我写一个**超级提示词**（Mega Prompt），你现在是一个播客制作人，播客里有四个角色，一个完美的提示词应该是怎样的？”它就会给你建议，然后你再不断优化它。

<details>
<summary>Original English</summary>

**Jason**: the interesting thing uh Sachs is you can you just have to ask your AI you ask claude or chatgpt or whatever you're using hey I want you to make me a mega prompt... and it will actually suggest a prompt and then you can refine the prompt so you actually have a dialogue about a prompt as opposed writing the prompt yourself.

</details>

**Sacks**: 无论你在市场营销、法律还是会计行业，如果你是同龄人中最精通 AI 的那个人，你就是无价之宝，比不懂 AI 的人价值高出 10 倍。

<details>
<summary>Original English</summary>

**Sacks**: by the way David what you said I think is true of almost every single job type like it's not just tech or programming if you're in marketing if you're in legal if you're in accounting... if you're the most AI savvy person of all your peers, you are golden. 10x more valuable than the next person who's not basically.

</details>

**Jason**: 制作人 Nick，解释一下这个过程。

<details>
<summary>Original English</summary>

**Jason**: Producer Nick, explain the process.

</details>

**Producer Nick**: 当我们获得 **Claude Co-work** 访问权限并有了扩展内存后，我开始把每一份转录稿都喂给它，看看它是否能基于你们过去的言论对新新闻进行背景化分析。我先给它一个总目标，然后问它：“你会如何为此编写技能文件或培训规则？”它就为我写好了全部内容。

<details>
<summary>Original English</summary>

**Producer Nick**: Yeah, once we got access to Claude Co-work and it had that like further expanded memory access. I thought it would be interesting to just start feeding every transcript into it and seeing if it could actually contextualize new stories that were coming out based on past things that you guys have said. And I gave it like a general prompt of what I wanted and I said, "How would you write a skills file or some training rules for this?" And it wrote all of it for me.

</details>

**Chamath**: 递归性太惊人了。这就是为什么人们认为 AI 会抹杀所有工作是错误的，仍然需要有人去监督、迭代和验证。

<details>
<summary>Original English</summary>

**Chamath**: The recursiveness of this is incredible. This is why people think, oh, it's just going to wipe out all the jobs. No, someone still has to supervise, iterate, validate, you know, all those kinds of things.

</details>

**Jason**: 如果你觉得自己已经落后太远了，我鼓励你打开 Claude，说：“我能做些什么来提升我的工作表现？”然后开始交谈。你可以使用语音转文字，我用的是 **WhisperFlow**，非常棒。你只需要滔滔不绝地讲，它就能从你的碎碎念中理出结构。这种“**碎碎念式提示词**”（blather-on prompt）能产生难以置信的效果。

<details>
<summary>Original English</summary>

**Jason**: I encourage you to pop up Claude... and say, "What can I do to be better at my job?" and just start talking and literally if the more you talk and you can use voice uh you know text to voice I use whisperflow is a really cool program for this... it will build the structure around the two or three paragraphs that you give it as instructions... It is unbelievable what the blatheron prompt can get in terms of output.

</details>

### 教皇通谕：AI伦理与权力的去中心化

**Jason**: 让我们进入正题。教皇 Leo 十四世发布了他的第一份关于 AI 的通谕（Encyclical），名为《**Magnifica Humanitas**》（壮丽的人性），长达 235 页。他在信中警告商业领袖要保护人类免受 AI 的侵害。他的核心观点是：AI 本身并非邪恶，但技术从来不是中立的，它会带有建造、资助和控制它的人的特征。教皇呼吁对 AI 公司进行监管。

<details>
<summary>Original English</summary>

**Jason**: We're going to start with the Pope. The Pope Leo, he's the 14th, released his first encyclical encyclical on AI. And it was long. 235 pages. In it, he warns business leaders to safeguard humanity from AI. His core argument is AI is not inherently evil, but technology is never neutral and that technology takes on the characteristics, wait for it, of those who build, finance, and control it. The Pope called for regulation of AI companies.

</details>

**Jason**: 他的中心问题是：AI 会被用来将权力集中在少数人手中，还是会为所有人服务？Sacks，你怎么看教皇对 AI 监管的兴趣？

<details>
<summary>Original English</summary>

**Jason**: His central question, Saxs, is will AI be used to concentrate power in the hands of a few or will it serve everyone? What's your take on the Pope and his interest and his missives on AI and promoting a bit of AI regulation?

</details>

**Sacks**: 我非常同意教皇的观点，AI 最大的风险是**权力的过度集中**。但我认为最可能以此来监视、审查和控制我们的是政府。我担心如果给政府太多权力去监管或批准 AI 开发，很快“安全”的定义就会无限扩张，演变成一种审查手段。

<details>
<summary>Original English</summary>

**Sacks**: Well, I very much agree with the Pope that the biggest risk of AI is a centralization of power and then its misuse against us um in some Orwellian way. I think it's government that's going to do that. I very much agree with him. The maybe where we end up in different places is he thinks that government regulation is the way to prevent this. And I would just say that we have to be careful not to empower government too much.

</details>

**Sacks**: 这是一个古老的政治哲学问题：**Quis custodiet ipsos custodes?**（谁来监管监管者？）。如果我们委托一组“监护人”来保护我们，如何防止他们变成暴君？美国建国者的天才之处在于“分权”，让监护人相互制衡。我对 AI 的看法也是如此：我们需要制衡。如果 AI 市场被垄断，我会积极使用反垄断法。但目前市场竞争非常激烈，有五家前沿实验室在竞争，只要有竞争，消费者就有选择权。

<details>
<summary>Original English</summary>

**Sacks**: This is a problem of political philosophy that goes all the way back to Socrates. It's called quis custodos custodes which is who will guard the guardians. The genius of the American founding... is that it was a second order solution to this question. Separation of powers. And that that is kind of my view on AI is that ultimately we have to have a solution of checks and balances. Right now we have a very competitive market. As long as the market is competitive, I would use that because I think competition generates the best outcomes.

</details>

**Bill Gurley**: 教皇提到这份通谕是模仿 1891 年教皇 Leo 十三世的那份。当年的通谕警告说工业革命对人类不利。但让我们看看从 1891 年到今天发生了什么：全球工作时长减半，实际工资增长了 8 到 10 倍，全球贫困人口占比从 75% 降到了 10% 以下。这一切都归功于技术创新和资本主义，而这正是当年教皇警告的对象。所以他完全搞错了。

<details>
<summary>Original English</summary>

**Bill Gurley**: So so this pope said that this encyclical was mirrored after one done by Leo I 13th in 1891. Leo the 13th encyclical warned that the industrial revolution was going to be bad for people. So let me tell you what happened from 1891 till today. Real wages went up 8 to 10x... global poverty went from 75% of humanity to under 10%. All those things happened because of technology, innovation, and capitalism, which is exactly what Leo the 13th was warning against. So he got it dead wrong.

</details>

### Anthropic的“Dr. Frankenstein”理论

**Jason**: **Anthropic** 对我来说一直是个谜，我从未见过一家公司既在领域内领先，又对自己所做的事情发表如此负面的言论。Bill，你怎么看 Anthropic 这种积极推动监管的做法？

<details>
<summary>Original English</summary>

**Jason**: I have to tell you that that Anthropic is a mystery to me. I've never ever seen a company that is both leading their field and the most negatively outspoken commenter on what they do. I I've just never seen it.

</details>

**Bill Gurley**: 我有一个新理论，我称之为“**弗兰肯斯坦博士理论**”（Dr. Frankenstein theory）。我见过一些人，他们认为自己的责任是创造一个优于人类的物种，并且对此感到兴奋。如果你读过 Anthropic 创始人 **Dario Amodei** 的博客《爱慈之机》（Machines of Loving Grace），你会发现他相信 UBI（全民基本收入），相信人类未来不需要工作。他甚至描绘了一个“AI 资本主义经济”，由 AI 系统根据人类的表现来分配资源。

<details>
<summary>Original English</summary>

**Bill Gurley**: I've come up with a new theory. This I call it the Dr. Frankenstein theory. I've met people who I who I dare say think it's their responsibility and they're excited about building a species that's that's superior to humans. And then Daario wrote this blog post called Machines of Loving Grace... he's talking about in the future what are humans going to do because he believes in the massive abundance and UBI and that we won't have to work. it could be a capitalist economy of AI systems which then give out resources to humans based on some secondary economy of what the AI systems think makes sense to reward in humans.

</details>

**Bill Gurley**: 我觉得他们不认为自己是在写软件，而是在“接生”一个神。

<details>
<summary>Original English</summary>

**Bill Gurley**: So, I don't think they think they're writing software. I think they're midwifing a deity here.

</details>

**Chamath**: 这就是**救世主情结**和**自大狂**。他们认为自己如此聪明，可以创造出上帝，并且那个上帝会是仁慈完美的。这简直是终极的自恋。

<details>
<summary>Original English</summary>

**Chamath**: these are delusions of grandeur. They believe that they are so powerful, these individuals, that they can create God and that by creating God, they are like this Prometheus kind of species. It literally is the ultimate level of narcissism and delusion of grandeur to think you can create God.

</details>

**Sacks**: 那为什么他们要推动监管呢？

<details>
<summary>Original English</summary>

**Sacks**: Well, I guess the question then is why are they pushing for the let's call it red capture agenda.

</details>

**Chamath**: 简单的**博弈论**优化。如果你想建立一个超级上帝，最好的办法就是把门关上，只留三四家实体在屋里，然后你设定规则。因为由于技术不对称，监管者根本看不懂比赛，你就能主宰游戏。

<details>
<summary>Original English</summary>

**Chamath**: That is very reductive game theory. So, if you want to be unexploitable... have three or four entities in a room, close the door behind you, and then dominate those other three or four entities, and then you set the rules. because the referees don't understand the game. If the refs don't understand the game, you'll run over the game.

</details>

**Sacks**: 如果你把 AI 看作是**中心化**与**去中心化**的斗争，Anthropic 的做法显然导向了更严重的中心化。我们需要 AI 去中心化，这样我们才能保护自己，能在自己的硬件上运行 AI，而不必受制于某家可能与“深层政府”勾结的公司。

<details>
<summary>Original English</summary>

**Sacks**: Now I think the issue is just you can see how this can lead to red capture, right? Which is if you brand yourself as the safe AI company and then try to characterize everybody else as a reckless player. This way of viewing the world leads to more centralization and I think that's dangerous. I mean, if AI is this very powerful technology, I think it needs to be decentralized so that all of us can protect ourselves to some degree, right?

</details>

### 开源的博弈：主权AI与监管捕获

**Jason**: 我一直在谈论“**AI 主权**”（AI sovereignty）。在本地硬件上运行开源模型非常重要。苹果在这里其实是个“黑马”，因为它一直注重数据主权。**数据主权**关乎隐私，而**智能主权**则关乎没人能告诉你该怎么思考。悖论在于，我们的对手中国反而在领导开源运动，而美国却在走向中心化。

<details>
<summary>Original English</summary>

**Jason**: I've been talking about AI sovereignty here for a bit... This is why it's super important that open-source, open-source agents and local hardware be able to run these models... And this is so paradoxical, Bill, that our adversary, the Chinese of all people, the Communist Party is leading the open-source movement and the United States is centralizing.

</details>

**Sacks**: 没错。开源意味着软件自由。如果你唯一的选择是来自垄断者的 AI，那你只能要么脱离现代社会，要么交出控制权给某种“社会信用系统”。所以开源是唯一的退路。

<details>
<summary>Original English</summary>

**Sacks**: Look, I Jacob, I agree with you about the importance of open source because open source means software freedom. You don't have to give up your privacy to again to some monopolist who's going to be, you know, in bed with the government or the deep state, right? It is the backstop.

</details>

**Chamath**: 我看到一个叫 **Rogo** 的公司发布的研究报告，指出目前最顶尖的几个模型（Opus, GPT-4, Sonnet）在金融分析评测中几乎难分伯仲，差距不到 0.3%。这意味着模型正在被迅速**商品化**。如果模型质量趋同，那么投入万亿美金进行增量训练的投资回报率（ROI）在哪里？

<details>
<summary>Original English</summary>

**Chamath**: This next wave of the market evolution I think is going to be extremely high stakes and messy. Opus 47, GPT55, Sonnet 46 appear almost indistinguishable... The results suggest convergence. these things are getting commoditized way too quickly. And then you'd say, well, what's the ROI on all this incremental spend, which is a very interesting economic and investment question.

</details>

**Bill Gurley**: 很多聪明的开发者正在尝试建立**抽象层**（Abstraction Layer），比如通过开源连接器使模型可热插拔。大企业非常害怕被某一家前沿实验室锁定，或者因为政治哲学不合而被突然切断服务。他们想要像 Sacks 说的，坐在一个“控制平面”上，拥有灵活性。

<details>
<summary>Original English</summary>

**Bill Gurley**: some of the smarter people in the open source community have suggested to me that we need more open-source connectors of types... the founders and developers that are out there should work on more of these interfaces and throw them into the open source world just to make it more exchangeable, swappable. They want abstraction above it. They want to sit in a control plane.

</details>

**Sacks**: 在华盛顿，我看到一股试图禁止开源模型或**开源权重**（Open-weight）模型的暗流。他们的理由是开源模型没有护栏（Guardrails），因此是危险的。这种说法在 Anthropic 的博客中反复出现。我觉得他们正在为未来的禁令制造舆论铺垫。如果美国禁止开源，那美国就成了孤岛，而世界其他地区将继续受益于开源带来的成本优势。

<details>
<summary>Original English</summary>

**Sacks**: I think where it's all leading to is an effort to ban open source models or open weight models. with open source models, the guardrails can be removed and therefore they're dangerous. You see this rhetoric already in anthropics blog posts. I think it's just a matter of time before they feel like they're at a position where maybe they can push for that type of ban directly.

</details>

### 就业叙事逆转：是AI替代还是“洗白裁员”？

**Jason**: 我们得谈谈 AI 对就业的影响。**Cloudflare** 的 CEO Matthew Prince 上周说他裁减了 20% 的“测量员”（Measurers）。Zuckerberg 在 Meta 裁员 8000 人的同时，还被爆出在员工电脑上安装“间谍软件”来收集训练数据。但高盛 CEO David Solomon 却在《纽约时报》发文说“AI 引发的失业末日被夸大了”。

<details>
<summary>Original English</summary>

**Jason**: we're going to have to talk for the 16th time in the last 18 months about AI's impact on labor because again this chaotic schizophrenic interpretation of the data continues. Cloudfare as we talked about last week, shout out Matt Prince. Zuck then paired his 8,000 cuts at meta with the fact that he has put uh spywear on everybody's laptop to study every employee to make their training data better. But on the other side of the table, Goldman Sachs's CEO, David Solomon, wrote an op-ed in the New York Times. The AI job apocalypse is overblown.

</details>

**Sacks**: 我在 1 月份的预测节目中就说过，AI 会导致就业增加而非减少。现在 Sam Altman 和 Dario 都在收回他们关于大规模失业的预测。他们现在的说法是，AI 可能自动化 90% 的任务，但剩下的 10% 会扩展出更多新任务。目前失业率处于历史低位，而软件工程师的职位发布量居然同比增长了 15%，尽管编程是 AI 最强的应用场景。

<details>
<summary>Original English</summary>

**Sacks**: my most contrarian take back in January on our prediction show is that AI would lead to job gains, not job loss. You have the CEO of Goldman Sachs writing in the New York Times. You had Sam and even Daario now walking back their claims of massive job loss. Software developers are not being laid off on net. In fact, job postings for software developers are at a three-year high, growing 15% year-over-year.

</details>

**Chamath**: 坦白说，过去 5 到 10 年，很多公司严重过度招聘。CEO 们没能很好地管理预算，现在他们需要一个**替罪羊**。AI 就是那个完美的借口。裁员其实是在清理过去管理不善留下的臃肿，这跟 AI 没关系。

<details>
<summary>Original English</summary>

**Chamath**: let's be honest. Over the last five or 10 years, a lot of companies overhired. They need a scapegoat. They point to this thing. It's very simple to say. It's AI. But underneath that is not AI because we know this. It hasn't done anything measurable yet at the end consumption of these tokens. That's what's happening today.

</details>

**Jason**: 我不同意。我认为扎克伯格在员工电脑上装软件就是为了发现更多可以消除的岗位。亚马逊说他们将取消 60 万个未来岗位。如果你在接下来的 10 年里还在开出租车或卡车，那你的工作肯定会消失。我们应该对这些受影响的人保持同情。

<details>
<summary>Original English</summary>

**Jason**: I think you're wrong. I believe Zuckerberg is putting that software on people's computers in order to to find more jobs to eliminate... Amazon themselves, these are the savviest people in the world said, "We are going to eliminate 600,000 future positions." Every cab driver is losing their job. Every truck driver is losing their job in the next 10 years.

</details>

**Sacks**: 既然 AI 已经实现了编程的完全自动化，为什么软件工程师的招聘还在增加？因为**当某些东西变得容易，人们就会做得更多**。去年有 10 亿次代码提交，上个月就有 11 亿次。代码量爆炸了 14 倍，这些代码需要人去管理。很多以前不需要程序员的公司现在都在招人。

<details>
<summary>Original English</summary>

**Sacks**: Explain to me why job postings for software engineers are up 15% year-over-year despite the fact that code has now been fully automated. make something easier, more people do it, right? We have basically a 14x year-over-year increase in code generation. That code has to be managed by somebody.

</details>

**Jason**: 这是一个非常活跃的市场。顺便提一下，刚才有一条快讯：一个 AI 顾问透露，他的一个客户因为没给员工设置使用限制，一个月误花了 **5 亿美金**的 Token。

<details>
<summary>Original English</summary>

**Jason**: Did you guys see what just hit the wire? an AI consultant revealed that one of their clients accidentally spent half a billion dollars in a single month after failing to set employee limits on clock usage.

</details>

**Sacks**: 哇！看来“**Token 效率**”将成为明年的大主题。

<details>
<summary>Original English</summary>

**Sacks**: Oh my god. there's no question that token efficiency is going to be a big theme over the next year because the spend has been ramping up way faster than enterprise customers thought.

</details>

**Jason**: 好了，各位。这又是精彩的一集。Bill，很高兴你能来。

<details>
<summary>Original English</summary>

**Jason**: All right, everybody. This has been another amazing episode of the AllIn podcast. Thanks for coming. Bill, we missed you.

</details>

**Chamath**: 顺便为 Tulsi Gabbard 和她的丈夫 Abraham 加油，他正在勇敢地与癌症作斗争。我们爱你。

<details>
<summary>Original English</summary>

**Chamath**: I just want to just give a huge shout out to Tulsy Gabbard and specifically her husband Abraham. Going through some really tough stuff with cancer. He is going to kick its ass.

</details>

**Jason**: 275 集录制完毕，下周见！

<details>
<summary>Original English</summary>

**Jason**: Cheers everybody. Uh that's episode 275 in the can. We'll see you next time. Bye-bye. Love you Blues.

</details>