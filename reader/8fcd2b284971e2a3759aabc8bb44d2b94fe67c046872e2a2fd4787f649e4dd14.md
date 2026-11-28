---
author: How I AI
date: '2026-11-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DuYVOYsoJcw
speaker: How I AI
tags:
  - ai-agent
  - workflow-automation
  - edge-computing
  - agent-architecture
title: Innovaccer CTO Ankit Maheshwari 谈基于 OpenClaw 与 Mac Mini 构建个人 AI 幕僚长系统
summary: Innovaccer CTO Ankit Maheshwari 分享了他如何在 Mac Mini 上持续运行并演进名为 Jarvis 的 OpenClaw 智能体系统。该系统通过单一微调 Orchestrator 与专项子 Agent 架构，处理简历筛选、报销与差旅审批、外卖自动下单、智能电话催办与预订，以及逆向工程控制智能家居，并正探索端侧开源小模型以降低运行成本。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ankit Maheshwari
  - Clara Voe
companies_orgs:
  - Innovaccer
  - Parallel
  - GiveDirectly
products_models:
  - OpenClaw
  - Mac Mini
  - GLM-5.2-Flash
  - Claude Opus 5.5
media_books:
  - How I AI
status: evergreen
---
### 个人 AI 幕僚长与日常生活自动化

>> CEOs，你们会用自己的 OpenClaw 打电话催促那些在 Slack 上回复不够快的人。
<details><summary>Original English</summary>
CEOs, you use your open claw to call people who are not replying to you fast enough on Slack.
</details>

>> 如果我需要了解进展，而他们基本上没有在 Slack 或其他地方回复，智能体就可以直接打过去提醒他们，他们会回复这个代表我致电的智能体。第一个逆向工程的应用是这个智能家居部件。它逆向工程了智能家居，理解了整个协议，知道基本上在什么时间开启我的空调，而我什么都不需要做。我不需要告诉它“嘿，我正准备回家，你能开下空调吗？”它会自动完成。能不能有某种方式，当我要出门时，自动帮我叫电梯，这样我就不用等电梯了？
<details><summary>Original English</summary>
>> If I need to to get a status, they are not basically replying on Slack or something or the other right, they can just call them up, remind them of basically and they will reply to the agent that is calling on my behalf. The first app to reverse engineer was this home automation piece. It reverse engineered the home automation, understood the whole protocol at what time basically to switch on my air conditioning where I don't have to do anything. I don't have to tell it, oh hey I'm leaving for home, can you switch it on? It does it automatically. Can there be a way where if I have to go out the elevator gets called automatically for me so that I don't have to wait for an elevator?
</details>

>> 哪怕只有 1% 的麻烦，你都要把它自动化。欢迎回到《How I AI》。我是 Clara Voe，产品主管兼 AI 痴迷者，这里的使命是帮助大家利用这些新工具做得更好。今天我邀请到了 Innovaccer 的 CTO Ankit Maheshwari，他依然在使用 OpenClaw。是的，2026 年早期的心头好 OpenClaw，他至今仍在运行它，而且依然是在一台 Mac Mini 上跑。这是因为他摸索出了自己的系统来运行一个兼具大脑、生产力和所需工具的 Jarvis，以消除生活中的所有摩擦，消灭哪怕只有 1% 让人心烦的事情。让我们开始吧。本期节目由 Parallel 赞助播出，专为 AI 规模化构建的网页搜索。[音乐] 当你的智能体出错时，搜索往往要承担多少责任？[音乐] Parallel 为你的智能体提供最新鲜、最准确的网页数据，并在各种速度和价格区间内提供信源。[音乐] 搜索返回速度快至 200 毫秒，足以支持生产级实时产品。Harvey、Notion 和 Rogo 在精度容不得半点妥协的体量下将其应用于生产环境。[音乐] 需要做决策，而不仅仅是搜索结果？来看看 Web Jev，Parallel 刚推出的新决策 API。用于对变动数据进行快速且准确的分类。[音乐] 它核对实时网页，而非陈旧的训练数据，并在一秒内返回带有引用的答案。按量付费，起价为每千次搜索一美元。[音乐] 因此成本随你的规模而扩展。数分钟内即可启动，访问 parallel.ai/howiai 即可免费试用并获得最高 80 美元额度。Ankit，非常高兴你能来《How I AI》，因为现在已经是 2026 年末了，而你依然对我最初挚爱的 AI 智能体 OpenClaw 保持执着。你真的把它摸透了，因为我不知道你有没有看最近的一期节目。我最近用 Grokbot 处决了我的 OpenClaw 们。那真是非常悲伤、非常非常非常悲伤的时刻。但你把它搞定了。所以从宏观层面告诉我，你为什么仍然喜爱 OpenClaw，它们运行在哪里，以及你为了让它为你所用而构建了什么？
<details><summary>Original English</summary>
>> If it's 1% annoying, you are going to automate it. Welcome back to How I AI. I'm Clara Voe, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Ankit Maheshwari, the CTO of Innovaccer, and he is still on open claw. Yes, the 2026 early favorite open claw, he is still running it and he's still running it on a Mac Mini. That's because he's figured out his system for running a Jarvis with the brains, the productivity, and the tools he needs to reduce all the friction in his life and eliminate everything that's even 1% annoying. Let's get to it. This episode is brought to you by Parallel, web search built for AI [music] scale. When your agents get it wrong, how often is search to blame? [music] Parallel gives your agents the freshest, most accurate web data with sources at every speed and price. [music] Searches come back as fast as 200 milliseconds, fast enough for live products. Harvey, Notion, and Rogo run it in production at volumes where accuracy can't be second best. [music] Need a decision, not just search results? Meet Web Jev, Parallel's new decisions API that just launched. Use for fast and [music] accurate classification of changing data. It checks the live web, not stale training data, and returns a cited answer in under one second. Pay only for what you use, starting at [music] a dollar for every thousand searches. So costs scale with you. Start in minutes and try it free with up to $80 in credits at parallel.ai/ how I AI. Ankit, I'm so excited to have you here on How I AI because it is late 2026 and you are still committed to my original AI agent love Open Claw. And I I You figured it out because I don't know if you watched a recent episode. I recently with Grokbot executed my open claws. It was very sad. It was a very, very, very sad moment. Um but you have figured it out. And so tell me at high level why you're still loving Open Claw, where they live, and what did you have to build to make it work for you?
</details>

### 为何坚持使用 OpenClaw：控制力与管理审批起点

>> 哦，当然。首先，非常感谢邀请我。你说的很对，每周都有新的智能体推向市场，而我仍然钟爱 OpenClaw。我认为对我而言在于控制的程度，是的，有时确实会让人有点沮丧，但你所能获得的控制水平在于：它确实可以接管我的密码和凭证，并真正去把事情办成，而不是总回过头来向我确认“嘿，这不在我的许可范围内”。我认为这是我至今仍坚持使用 OpenClaw 的最大原因。目前它为我在旧金山家里的 Mac Mini 上运行，基本上就在那里处理所有事情。至于这一切是从哪里开始的，我认为起点在于一件总是让我头疼的事：我的团队老是对我催促说“嘿，你成了瓶颈了。你有这么多简历等着审批，它们都卡在你的流程阶段”。而我的原则是，在没有看过简历、教育与工作背景以及每个人在面试反馈中说了什么之前，我没法审批并给通行许可。就在那时引入了 OpenClaw，这是我交给它的第一个任务：每四小时运行一次 cron 定时任务，找出我名下所有待审批的事项，逐一审视，给我一份供查阅的完整清单，同时我也能追问后续问题：“嘿，能查一下候选人的背景吗？能看一下他们的 GitHub 链接，告诉我他们过去都做过什么吗？”所有这些换作平时我必须去联系当面面试过他们的人才能确认的问题，现在都变得非常轻松。这是我用它解决的第一个痛点。一旦迈出这一步，多米诺骨牌效应就开始发挥作用了：好，既然它能做这个，那就把 Nawan 交给它，处理所有需要我批复的人员出差航班申请，并不断向他们提问：“你们为什么要飞？在不在预算内？”等等之类的事情。Nawan 相当疯狂，因为它甚至不会在邮件里给你发通知。所以过去总是有人在 Slack 上敲你：“嘿，有一张出差机票等着你审批，你能去系统里批一下那笔申请吗？”
<details><summary>Original English</summary>
>> Oh, sure. And first of all, thank you for having me. And And you said right like still having still being in love with Open Claw when every new week you have a new one hitting the market. I think for me the level of control, yes, it does get a little frustrating sometime, but still the level of control that you can get, right, where yes, it can take my password and secret and actually do stuff rather than basically always checking back, hey, this is not allowed for me to do. I think that was the biggest piece of why I'm still have been still sticking to Open Claw. Where it runs for me right now, it runs on a Mac Mini sitting here in my SF home basically right now doing all the work. And And where it all started, I think where it all started was this one piece that was always frustrating me because my team was always on my neck that hey, you are the bottleneck. You have so many resumes to basically approve. They are sitting at your stage. And my thing is I can't approve until I've seen the resume, the pedigree, what everybody has said on the feedback, and then give a go ahead. And that is when Open Claw came in, and I gave this That was the first task I gave it to every four hours have a cron run what is pending on me to approve, go through that, give me a full list to basically check in, and where I can also ask basically follow-up questions. Hey, can you check the pedigree? Can you check their GitHub link and basically tell what they have done basically in the past? So all those questions which otherwise I would have to ping the person who would have interviewed them, right, was very easy. And that is the first problem that I kicked off basically with it. And once I did that, that is when basically the whole domino effect started playing that, okay, now it can do this. Let's give it Nawan for all my flight approval that I need to do for people and keep asking them basically, okay, why are you flying? Basically are you in budget? And all those kind of things. And Nawan is pretty crazy because it doesn't give you notification either on your email. So it was always somebody pinging your Slack, hey, we have a flight for your approval waiting. Can you go there and approve that particular piece?
</details>

>> 所以不得不说，你作为一名繁忙的高管喜爱 OpenClaw，这跟我喜爱 OpenClaw 或广泛智能体的原因一样，那就是我说这些智能体真正让我拥抱了我内心的“微观管理者”：我想审批一切，我想看到所有细节，每一桩招聘、每一笔支出。这会让周围的人感到很烦。[笑声] 但如果你在合适的位置放一个智能体——我是真的认为这就是杠杆的支点之一，追求高绩效的高管往往喜欢在非常详尽的层面上审视业务中发生的一切。我常说最优秀的领导者会在细节上下功夫，包括谁被雇用了、为什么要雇用、公司内部的钱花在了什么地方。所以听起来，如果光靠你肉身一人去做到这些会非常非常艰难，但如果和一个配置得当、高度个性化的 OpenClaw 协同合作，就会轻松得多。
<details><summary>Original English</summary>
>> So I have to say you like Open Claw as a busy executive, same reason I like Open Claw or agents in general, which is I say these agents really let me embrace my inner micro manager, which is I just want I want to approve everything. I want to see everything, every hire, every expense. Um it's very annoying for people. [laughter] But you put an agent in the right spot. I mean, I really do think that's one of the points of leverage, which is like high performance oriented executives like to look at what's going on in the business at a very detailed level. I always say like the best leaders sweat the details, including who's hired, why are they being hired, where is money being spent inside the company. And so it sounds like for you trying to do that just as a human was very very hard, but doing that in partnership with a good well sort of personalized open claw was much easier.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 智能体架构：灵魂文件、护栏与子 Agent 编排

>> 但你必须承认，有时 OpenClaw 并不完美。我知道你围绕 OpenClaw 构建了这套系统，以便更容易地管理它。那么跟我讲讲你的 OpenClaw 设置吧，因为也许我还会换回去，谁知道呢。但在 OpenClaw 的配置、可见性等方面，你必须添加和考量哪些原语，才能让它运转得如此顺畅？
<details><summary>Original English</summary>
>> But you have to admit sometimes open claw like isn't perfect. And I know you built this system around open claw to make it easier for you to manage. So tell me like a little bit about your open claw setup because maybe I'll go back. I don't know. You never know. But like what kind of like primitives did you have to add and think about in terms of your open claw setup and visibility and all that stuff so that it worked really well for you?
</details>

>> 完全可以。我认为目前我的 OpenClaw 是直接通过 WhatsApp 与我交互的，基本上我就是在那里跟它同步核对。在初期阶段，它有时会出现幻觉、表现异常、没有完成工作，我认为在配置 OpenClaw 的灵魂（soul）时把护栏设立得非常到位，是我投入了大量精力的地方：即如何让灵魂设定得恰到好处，具备适度的护栏，并明确限定它的行动边界。另一个方面是，能否像——这与 Jarvis 是 Anton 之子的概念有所不同——能否采用微智能体与协调智能体协同的架构？也就是说，有一个主 soul.md，然后你也有其他的子 souls，这样它就知道该把什么路由到哪里。比如用于外卖点餐的模块，就需要一个类似健康教练的人设。这与去抓取并为我汇总精选 CTO 资讯的智能体大相径庭，也不同于梳理我邮件的智能体——后者负责告诉我哪些是最重要且必须立刻回复的邮件，哪些大部分只是仅供参考可以搁置、当下不需要打扰我，等我有空时再来提醒。我认为设置这四个文件，是我花了大把时间的地方。
<details><summary>Original English</summary>
>> No, definitely. So I think right now my open claw works directly with me on my WhatsApp is basically where I keep checking in. I think during the initial phase I think the hallucination of sometime basically misbehaving, not doing its work I think and just setting up the guard rails very well right in the when you're setting up the soul for the open claw I think that is where I put a lot of effort in basically that how do you make the soul right enough basically with the right amount of guard rails and basically where all it can move. And the other piece was right can I set like how you have like and that was a different than Java is the son of Anton concept that can you have basically micro agents with the orchestrator agent, right? So a master soul MD and basically then you have the other souls as well so that it knows where to route what like for my food ordering piece to have health coach kind of a persona. That's very different thing rather than basically if someone who is going and fetching me what is the right CTO digest or one that is going through my emails to tell me okay what is the most important piece that you should definitely reply right now and something that all are mostly FYI and can wait and you don't need to basically bother for now and when you're free then I will bother you about them. I think setting up those four files was something basically where I spend a good amount of time in.
</details>

>> 看来你之前的情况可能和我非常相似，因为我曾经也有我的主 Claw。她叫 Polly。愿 Polly 安息。我们都很想念 Polly。她有天还出现在播客上。所以我们真的很想她。但我那时也有类似主智能体的架构，然后设置了各个具有明确工作职责、灵魂设定、访问权限等要素的独立智能体。你是否认为——我的意思是你似乎在这点上和我想法一致——“一个智能体统治一切”的模式要在各项事务上都做得很精实在是太难了，这就是为什么你倾向于让这些子智能体来把工作做得更出色？这种架构最吸引你的地方是什么？因为我认为当前市场上关于“单智能体”对决“多智能体体验”存在着巨大的争论。
<details><summary>Original English</summary>
>> And you so you were probably very similar to me because I had my master claw. Her name was Polly. RIP Polly. We all miss Polly. She was like a she showed up at a podcast one day. So we really miss her. But I had like sort of my master agent and then I set up individual agents with like well scoped jobs, souls, access, all that kind of stuff. Do you think that I mean you seem similar to me in that like do you think the one agent to rule them all is just too hard to get good at everything and is that why you kind of have these sub agents do a better job? Like what appeals to you about that setup? Because I think there's this big debate in the market about like the one agent versus the many agent experience.
</details>

>> 确实是这样。至少在 OpenClaw 中，我开始发现它有时会出现严重的幻觉，遗失记忆。比如，我创建了一个语音模块，目前我以前用的是 ElevenLabs 加 Twilio，现在改用 Bland AI 来驱动，用它来在餐厅预订位置，甚至是致电我的同事跟进情况。比如如果我需要了解进展，而他们在 Slack 或其他地方没有回复，智能体可以直接打给他们、提醒他们，他们会回复这个代表我致电的智能体，接着智能体再做总结并反馈给我。如果让同一个主智能体来做这件事情，它在人设切换上就会产生大量幻觉。给餐馆打电话的人设，与打电话预约的人设，再到致电同事的人设完全不同。我希望它表现出不同的人设：有时不需要太强势，但有时又可以强势一些。无论我如何给它调整，它在这些细节上都处理得不好。就在那时我意识到，对它来说这太容易混淆了，因为要做的事情太多了，它既要兼顾这个任务，又要处理那个任务。它应付不过来，虽然会一直向我道歉，但又会一再犯错。于是我说好吧，这应该独立成一个专职模块，由一个专门懂电话外呼的智能体来负责，根据致电对象的不同清晰地划分到各个分类，并根据拨打的对象展现出对应的人设。
<details><summary>Original English</summary>
>> Yeah. Yeah. At least in open claw I started seeing it sometimes hallucinating a lot of missing memories. Like for example, I created so there's a voice piece like right which right now I used to use in 11 Lab plus Twilio. Now I use Blind AI basically to power that piece up to say book a point appointment for me basically either in a restaurant or even call my coworkers and check on with them. Like if I need to check get a status, they are not basically replying on Slack or something or the other right. They can just call them up, remind them up basically and they will reply to to the agent that is calling on my behalf to them and then some rise and give it back to me. Now sometimes if I had the same agent the my master agent do that, it would hallucinate a lot on what persona. If it is calling somebody say in a restaurant versus calling to set up an appointment to calling a coworker. There were different personas I wanted it to behave like That somewhere basically doesn't has to be very bossy. Sometimes it can be, right? So those things it was not handling very well even though how much I was easing at it. That is when I thought that okay, it's just too confusing for it because it's getting so much to be done, right? It's also doing this task, that task. It's not able to do it will keep apologizing to me, but it will keep making the mistake. That is when I said okay, this is a separate thing, one person who just knows how to do voice calling rate, know have different personas put easier easier into the different categories who they are calling and bases who they are calling, they will get that kind of a persona out.
</details>

### 构建方式：摒弃复杂调度，回归终端 TUI 对话

>> 好的，所以你把子智能体架构理顺了，我完全赞同。边界明确的上下文线程确实能极大地提升智能体体验。在 Opus 5.5 中，我非常重度地使用 Claude Projects。我重度使用 Claude Projects 是因为我认为它在管理子线程以及跨线程协调方面非常出色。我认为对于不了解的人来说，第一，这是在大公司管理上下文成本的好办法；第二，它在处理职责清晰的事物、特定范围的智能体和特定边界的线程上，确实表现更佳。好了，让我们深入聊聊你是如何围绕 OpenClaw 搭建起整套系统的。你是怎么做的？因为我曾经有一段时间用 Codex 去运行我的 OpenClaw，简直完全乱套了。告诉我你是如何构建整个系统的。
<details><summary>Original English</summary>
>> Okay, so you've got you've got your like sub agent structure figured out and I totally agree. It well scoped threads just really improve agent experience. So I use cloud projects a lot. I really like in Opus 55. I use cloud projects a lot because I think it's really good at managing sub threads and coordination between threads. And I think that one, for people who don't know, it's a good way to manage your context costs in large companies. And two, it actually does I think do a better job well scope well scope things, well scope agents, well scope threads. Okay, so let's get into how you built this whole system around your open claw. Like what did you do? Cuz I was at some point running Codex to run my open claw. Like it was totally bonkers. Tell me how you built kind of like this whole system.
</details>

>> 是的。我也尝试过，在浏览相关内容时，有很多相关的论坛帖子和博客提到使用 Codex 或 Claude Code 来构建 OpenClaw。我选择了一条非常简单的路径：一旦进入 OpenClaw，我的主界面就是它所谓的 Operator 界面以及常规的 TUI，即终端用户界面，那就是我的命令界面。所以我从不用 Claude Code 来运行它。我就是像跟真人说话一样持续向它输入提示词。我不断与它对话，直到今天这依然是我构建新功能的主要界面。在 TUI 层面上，我去到那里，不断提示它、与它交谈，它也会不断反馈它的理解、它构建了什么以及准备向我交付什么。我就是通过这种方式一步步搭建起来的。甚至当我想编写任何代码时，我提出需求，在底层 OpenClaw 就会拉起 Claude Code 或其他任何工具来替我完成。至于运行 OpenClaw 本身，我从不用 Claude Code 或 Codex。我只使用 TUI 界面，就像在与 OpenClaw 面对面交流，让它进一步学习、调研某项技术、提升某项能力、摸索如何与 Twilio 或 Bland 进行集成，或者寻找更好的新服务；让它自己去完成，当它做不到时，我再介入……
<details><summary>Original English</summary>
>> Yeah. So I think and I tried it like I think when I was reading through that like that okay, how do you set up there were a lot of basically related threads and blog posts that a view the Codex or use a cloud code to build your open claw. I chose a very simple step like once I got into the open claw I had my main interface as the what it says is the operator interface and the normal TUI, the terminal user interface, and that was my command interface. So I never used cloud code for it to run it, right? I just kept prompting like how you talk to a human. I just keep talking and even today that is my primary interface to build anything new with that. That in the TUI layer basically I go there, I keep prompting it, talking with it, it keeps talking back what it understands, what it has built, what it will give back to me. And that is how I have been able to build. Even when I want anything to be like coded, I ask it and it will behind that basically the open cloud will fire up a cloud code, will fire up basically anything and will do it for me. I to run the open copies I never use cloud code or codec. I just use the TUI interface where I'm likely talking to open cloud and asking it to learn more, research about this, get better at this, figure out basically how it needs to integrate with Twilio or with Bland or figure out some new service which is better, but do it itself basically and when it doesn't basically then I
</details>

>> 本期节目由非营利组织 GiveDirectly 赞助播出。他们将资金直接送到世界上最贫困的人手中，不附加任何条件。GiveDirectly 的模式意味着你无需怀疑善款流向何处、是否真的产生了效果。他们利用移动支付——一种遍布非洲的技术，让人们通过功能机就能接收现金。[音乐] GiveDirectly 为人们登记并通过短信进行付款，而且他们正在创新性地应用 AI。在危机期间，他们利用卫星图像和手机元数据来定位受影响最严重的人群，并将紧急资金直接发送到他们的手机上。[音乐] AI 让他们能在几分钟内筛选海量数据，在数小时而不是数周内将援助分发到位。[音乐] 这就是我对 GiveDirectly 模式推崇备至的原因：它不仅简单、高效、有尊严，而且依托移动电话技术迅速将现金送到需要的人手中。如果你是第一次听说 GiveDirectly，先不要捐款。不妨去 givedirectly.org/howiai 详细了解它的运作原理。[音乐] 我看过了，觉得非常大开眼界。网址是 givedirectly.org/howiai。好的，你真的……你真的要把我拉回坑里了，我们要在 2026 年末掀起一场 OpenClaw 复兴，因为你确实说服了我，有些方面确实变得更好了。不过让我们来探讨具体的实际用例吧。就在刚才，我想先暂停一下。各位 CEO 们，在我们深入其他用例之前，我想确保你们没有漏掉几分钟前的那一幕：用 OpenClaw 打电话给那些在 Slack 上回消息不够快的人。我对这个功能简直着了迷。我有一个 10 个月大的婴儿，我们正在对他进行睡眠训练。有时半夜我给睡在沙发上的丈夫发短信，想抓紧睡 5 分钟，我们分工协调让他来替我，但他没有回复。那我直接让我的 OpenClaw 打电话给他。太天才了。大家听好，这真的是一个核心用例，千万别忘了。好了，除了给回复不够快的人打电话，Jarvis 还能做什么？
<details><summary>Original English</summary>
>> This episode is brought to you by Give Directly, a nonprofit that puts money directly in the hands of the world's poorest people, no strings attached. Give Directly's model means you don't have to wonder where your donation goes and if it does any good. They use mobile money, a technology across Africa that lets people receive cash on a basic phone. [music] Give Directly signs people up and pays them through a text message and Give Directly is innovating with their use of AI. During a crisis they use satellite imagery and cell phone metadata to find the people most [music] impacted and send emergency cash straight to their phones. AI lets [music] them sift through tons of data in a matter of minutes, getting aid out in hours, [music] not weeks. That's what I love about Give Directly's model. It's not only simple, efficient, and dignified, it's building on mobile phone technology to get cash to people in need quickly. If you're just hearing about GiveDirectly, don' donate yet. Just go read up on how it works at givedirectly.org/howiai. [music] I did and I found it really eye-opening. That's givedirectly.org/howiai. Okay, you really like you're really going to bring me back maybe yeah, we're going to bring me back to the open claw. We're going to do a late 2026 open claw revival cuz I think you've convinced me that some things have gotten better, but let's go into actual use cases and just a few minutes ago, I just want to pause. CEOs, before we get into the other use cases, I want to make sure you didn't miss the one from a couple of minutes ago, which is you use your open claw to call people who are not replying too fast enough on Slack. I'm kind of obsessed with this. Um I have a 10-month-old baby and we're like sleep training him and I like sometimes text my husband in the middle of the night when he's sleeping on the couch to get 5 minutes of sleep and we do this tradeoff where I'm like come help me and he doesn't reply. I'm just going to get my open claw to call him. It's genius. This is you really this is a key key use case, people. Do not forget this. All right, so other than voice calling people who don't reply fast enough, what else does Jarvis do?
</details>

### 具体用例：全流程审批、外卖自动下单与差旅谈判

>> 好的。就像我刚才提到的，招聘和审批是我添加的第一个模块，并且涵盖了各项审批，包括 Nawan 和 Coupa：检查是否有任何事项积压在我这里。任何我成为瓶颈的新环节，它都会全面梳理弄明白，让我不再是瓶颈。另一个场景是外卖点餐，这是另一项被摸索出来的应用：在旧金山办公室时，我们使用 DoorDash 企业送餐管理，它有一个非常硬性的截止时间，即必须在上午 10:00 之前下单，否则当天就无法加入统一配送名单。而过去我经常错过，因为我一早总是有会，经常漏点，导致吃不上午饭。所以我配置了这套流程让它接手。我训练了我的餐饮偏好：我是素食主义者、我什么时候想吃印度菜、什么时候想吃健康餐等等，把所有要求输入进去，它学会后就会为我下单，这样我就不会挨饿。它知道首先在上午 9:30 向我发起确认。如果我没有回复，它就会按照自己的判断自主帮我下单。而且它会在犯错后持续学习。比如有一次点印度菜，它只点了咖喱而没有点饼，结果被我批了一顿。从那以后它就学到了：如果点咖喱，必须配套点饼。但在执行中它又进一步学到，有些套餐本身就已经包含饼了。对于了解印度餐饮的人来说，这类套餐自带主食，所以在那种情况下它就不会重复下单买饼。所有这些研究，它都是在挨了一次训之后自行研究掌握的。[笑声] 但这是一个我认为对我来说使用率极高的功能，从那之后我总能准时吃上午饭。另一个场景是我之前提到的语音通话旅行规划。这非常棒，比如我和妻子去度假，现在我所有的行程规划基本上都由 OpenClaw 完成。它会核对：是否属于星空联盟航班、我的积分该怎么兑换、怎么使用我的 Amex 积分等。过去我必须同时打开五个不同的浏览器窗口比对时间来完成这些复杂的琐事，现在不仅连订房都能搞定，而且语音通话功能还有一个妙用：它能代表你去向商家谈判议价，我确实用过这个功能。我让它：去自我训练，看视频，读文献，掌握优秀的谈判技巧，建立话术，然后去谈判。它甚至成功帮我预订到了一家很棒的餐厅，说明这是我的十周年结婚纪念日，对方必须为我留一个位子。
<details><summary>Original English</summary>
>> Yeah. So like I said, the hiring and approval was the first piece that I add like an that's approval across everything across Nawan, across Cooper, basically is there any basically of those pending on me, right? So any new thing that is well where I'm becoming a bottleneck, it goes through figures it out basically is that how uh I'm not anymore the bottleneck. The other piece was the food ordering piece, right? So this was another thing discovered that um so when I'm in SF office, we have this meal DoorDash meal manager and it has a like very um like um stop time basically that before 10:00 a.m. you have to place your order, otherwise basically it doesn't get added up uh into the daily list and I was always missing that because I earlier like I will always have early morning meetings and it will always get missed and I won't have my lunch. So I've figured it out where it can now go. It I train my meal preferences. Okay, I'm a vegetarian. When do I like Indian? When do I like healthy food and everything and all the instructions and it learn and then basically placing orders for me so that I don't go hungry, right? And it knows that first it will take a confirmation for me at 9:30 a.m. If I don't reply, it will just go on its own whim and order for me and it it keeps learning like from when it makes a mistake. Like for example, ordering Indian food and just ordering the curry and not the bread and then getting a bash from me. Basically, it learned if I'm ordering curry, I also need to order bread. But in I I did that and then it learned there are certain meals that come with bread. So when it's ordering and people from India will understand like it comes like the meal in itself contains a bread. So in that case, it won't order a bread. So it did all that research only after one scolding it got [laughter] but that was a but that was a very I think that is one of the most used thing for me that I always get my lunch since then. The other piece I talked about the the voice call travel planning, right? That has been one thing right going on vacation with my wife like now all my planning basically are done by O law. See okay, it has to be a star line of lives or like what I can use my points. See basically where I can use my Amex points and everything all those complex thing which I had to do opening five different browsers basically out there finding out time it does even booking places and one good thing with the voice call feature it can do is also negotiate on your behalf at places and I have used that, right? That hey, go train yourself, see videos, see read literature, what are good negotiation skills and build the and then negotiate and it has been able to get me some good restaurant looking that hey, why it needs to basically invite is my 10th anniversary and they definitely need to give me a seat.
</details>

>> 这真是……老兄，你太厉害了，我只能这么说。如果不回 Slack，你的 OpenClaw 就打电话催；如果订不到位子，你那经过 YouTube 训练的 FBI 谈判专家智能体就会出马，帮你拿到餐厅最好的位置。我对你的这些用例赞赏有加的地方在于，我觉得这完全是你个人风格的体现：极其关注细节，掌控一切事务，确保能吃上午餐（这也是我的一大痛点），渴望追求卓越。但作为一个人，要在预订行程、挑选餐食等所有方面都做到极致是非常困难的。因此在我看来，你的智能体就像是你想亲自成为的最完美版本。我认为这真的是一个极佳的构想角度。
<details><summary>Original English</summary>
>> This is so I mean, you're dangerous, man. That's what I have to say. If you don't get the slack, your open close calling. If you don't get the table, your YouTube trained expert FBI negotiator is going to go in there and get you the best table in the restaurant. What what I love about your use cases is like I just think I you know, I think you and I will be friends, but like just an expression of your personality, which is just like I want to be detail oriented. I want to be on top of my stuff. I want, you know, I want to make sure to eat lunch, which is also a big problem for me. I want to have like I want to be able to be the best, but as a human, it is hard to be the best across every across booking travel, across picking your meals. And so to me, I look at this and I'm like, okay, your agents are like the best version of what you would want to do yourself here. And I think that's really like a great way a great way to frame and think about it.
</details>

>> 是的。还有其他你想了解的吗？
<details><summary>Original English</summary>
>> Yeah. That's that's very Any other ones you want to you want to show?
</details>

### 逆向工程智能家居与电梯自动化构想

>> 最新搞定的是智能家居控制。当我在印度时，我有一整套全屋智能控制系统，但该应用与 Google Home 等平台的适配并不好，它采用的是专有技术栈。所以当 REA 逆向工程框架火起来时，我让 OpenClaw 去研读整个项目，深入 GitHub，把 REA 等相关工具部署运行起来。它逆向工程的第一个应用就是这个智能家居套件：逆向了智能家居，理解了底层全部协议，以及现在如何能操作我家里的所有设备。现在它知道我何时离开办公室，因为它通过我的 WhatsApp 和 Android Auto 联动运行，因此它能在恰当的时间开启空调，我完全不用做任何事。我不需要对它说“哦对了，我正准备回家，你能开下空调吗？”它全自动完成。既然它知道我在未来 15 分钟内就会到家，正是开空调的最佳时机，我又何必还要去给 Google Home 下指令呢？所以这是我最近做的一个项目：先让它通过 REA 学习如何逆向工程，然后找到应用并替我搞定。
<details><summary>Original English</summary>
>> The the latest one is the smart home control. So when I'm in India, right? So I have this whole completely home control piece, but the application was not well tuned with say a Google Home, right? It was a proprietary stack and everything. So when the reverse REA thing became viral, I asked my open cloud to learn the whole thing, go into GitHub, implement the REA and everything. And the first app to reverse engineer was this home automation piece. Reverse engineer the home automation, understood the whole protocol, how it can basically now operate everything uh my home at my home. And now it knows when I leave from office, right? So because it will run from my WhatsApp uh with uh my Android Auto. So what to basically at what time basically to switch on my air conditioning where I don't have to do anything. I don't have to tell it oh yeah I'm leaving for home, can you switch it on? It does it automatically. So why even I need to prompt the Google Home to switch it on when it knows I'm going to reach home in the next 15 minutes. That's the right time for it to uh switch on the air conditioning. So this is the latest one that I did basically using for for a first it learn how to reverse engineer stuff, right? Using the RE and then finding an app and doing that for me.
</details>

>> 那么你是怎么构想家里那些想要自动化的事情的？因为很多人像我一样，我之前破解了一个灯泡，因为它闲置在那，我为自己从没用过它感到恼火，现在它成了我漂亮的小型旋转播客补光灯，看起来超酷。但我觉得很多人都在纠结“什么是可能的”。这些都是你自己的想法吗？都是你回到家后觉得“哎，要是再也不用干这个就好了”的事情吗？你是如何头脑风暴并发现这些新点子的？对于寻找灵感的人，你有什么建议吗？
<details><summary>Original English</summary>
>> And then how do you how do you think I mean how do you think of things around your house that you want cuz that you want to automate? Because I think a lot of people like me I I hacked this light bulb um because it was sitting around and I was so annoyed that I never used it and now it's like my nice little rotating podcast light looks super cool. But I kind of I mean I think a lot of people struggle with this idea of like what is possible? Are these all ideas that you had? Are these all things that like you did when you got home and you were like ugh I could never have to do that again, that would be great? Like how do you how do you brainstorm and discover these new ideas? Do you have any tips for people that are looking for inspiration?
</details>

>> 这些灵感主要源于成长过程中的幻想，是我一直想做的事情。你看电影，看各种科幻故事；现在有了 AI，所有这些都有可能实现，我的大脑就是这样运转的。如果其中有任何事情稍微带来一点麻烦，我的想法就是：如何用 AI 把这个自动化？能不能把那个也自动化？所以我觉得只要有 1% 的不便，并且我必须重复做两三次，就会想去改造。比如现在我们楼里有几部大电梯，我就在琢磨：能不能有一种办法，当我要外出时，电梯就自动被呼叫过来，这样我就不用站在那等电梯了？到目前为止我已经想明白了，可以有一个守卫设备，当我要走时直接替我按下按钮，这样总有一部电梯在等我，省去了等待时间。我能用它实现这个吗？
<details><summary>Original English</summary>
>> And these have been the ideas like because when you see like growing up have been like those fantasies which I always wanted to do, right? You watch movies, you watch stuff. Now with AI all these things being possible is how the brain works, right? for me. And if any of these things becomes an even little bit of an annoyance, my thing is like oh how can I now build basically uh with the AI piece oh can this be automated? Can that be automated? Now so so I think that is what like if even if it is like one person annoyance and if I have to do it twice or thrice, right? Can they be like right now like so we have these large elevators and I was thinking hey can there be a way if I have to go out the elevator gets called automatically for me so that I don't have to wait for an elevator and till that I have figured out with that particular It can I have a god with that I need to go and it can just press that button so that there's always an elevator for me and I don't have to wait for it. Can I have that with it?
</details>

### 系统护栏与自动审批边界

>> 这太搞笑了。“只要有 1% 的麻烦就要自动化”，这种对抗摩擦的精神实在很有趣。这太精彩了。你展示了这么多我想重新借鉴到我自己的 OpenClaw 里的东西。在架构方面，你还有什么想展示的吗？或者如果有人想自己搭建这套系统，有什么需要格外留意的技巧？哪些地方做起来其实很难？
<details><summary>Original English</summary>
>> This is hilarious. This idea of like if it's 1% annoying you are going to automate it. Like this friction with I I think that's hilarious. Well this has been awesome. You have shown me so much that I think I want to bring back into my you know my open claw. Anything about the architecture you want to show off or somebody wanted to build this themselves like any tricks, any things that you think like pay attention to this. This was really hard.
</details>

>> 从架构的角度来看，正如我所说，我选择了一条非常精简的路线。在办公室里我的 CEO 和其他人看到后问我时，我也是这么说的：不要走复杂路线去搭建 OpenClaw，直接走 TUI 终端交互路径即可。安装完成后，把它当成你刚雇用的新人类助理，不断与它对话让它学习并持续改进，这对我来说是核心。其次是多服务智能体模块，理清哪些任务在 WhatsApp 上执行，哪些配置为 cron 定时任务，哪些需要给它浏览器控制权，梳理好这些流程；同时要明确你对哪些权限是放心的。有时我非常乐意交出我的用户名、密码或直接共享会话，但必须设立严格的护栏。因为如果不设护栏，风险会很大。比如有一次把我吓了一跳：当时我正在中转乘机，团队成员提交了差旅审批，而这些申请即将过期。由于我正在睡觉或在飞行途中无法联系到我，它竟然进行了自动审批。
<details><summary>Original English</summary>
>> From a architecture point of view right like I said like I went very simple in it and that is when people when asked me also like after the seeing that in my office my CEO like building open claw going through rather than a complicated route just going the TU route where you are just talking once you have installed just imagine you knew a human new assistant that you have hired and keep talking to it for it to learn and right and keep in improving that piece is core for me the multi-service agent basically piece figuring out that okay what can do on WhatsApp or what are basically you setting up as cron, what are thing basically you want to give it control on the browser to be done right some of those pieces like figuring those flows out and also what things you are comfortable with right? I am very much comfortable sometimes giving my like say username or password or basically opening up the session but then having the right amount of guard rails, right? Because if you don't have the guard rails, right? It can become risky. For example, something that freaked me out was at one point in time, I was in a transit. I was flying out and there was some travel approval from my team members that were waiting for me and they were about to expire. And because it couldn't reach me because I either I was sleeping or I was on myself on a flight, it just auto approved it.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mm.
</details>

>> 它直接自动通过了，尽管它向我汇报：“嘿，我核查了你平时关注的所有要点：差旅在预算内，属于必不可少的客户拜访，因为我不想让申请过期，所以我给自动批准了。”虽然在这种情况下没出问题，但你显然不希望这种自动审批发生在岗位招聘录用之类的决策上。因此，设定清晰的护栏——哪些绝对不能做，哪些可以放行——我认为这是至关重要的事情。
<details><summary>Original English</summary>
>> it auto approved it and though it told me, hey, I looked for everything that you used to look that oh, it was in budget. It was an essential customer travel and because I didn't want it to expire, I auto approved it. And those cases were fine, but you don't want sometimes those auto approval to happen say for a job role or something. So setting up those guard rails and these things you never do. These things you are fine doing. Those are something important what I feel.
</details>

### 端侧小模型探索：GLM-5.2-Flash 与成本优化

>> 太棒了。这就是我们在 2026 年底急需的 OpenClaw 安利。我敢说你肯定能吸引一些人入坑。我手边就有四台 Mac Mini。是时候擦亮落灰的 Mac Mini 了，它们目前是我的远程 Codex 编程机，用来把工作负载从我本机移开。在放你离开前，我想进行几个快问快答。我很好奇的一个问题是：你提到目前这套系统全部跑在 Opus 5.5 上，但你是怎么看待本地模型的？也就是走出 OpenAI 和 Anthropic 的生态系统，你是否在尝试这方面的探索？
<details><summary>Original English</summary>
>> I I love it. Okay. Well, so this has been the late 2026 open claw pitch that we all need. I bet you're going to get a couple of people. I have four Mac minis over here. So dust off dust off the Mac minis. They're currently remote codex coding machines so I can get this stuff off my computer. But I I love this. Before we let you go, I want to do a couple of lightning round questions. One that I I'm curious about, which is like how how are you thinking? Because you said this is all running Opus 55, but how are you thinking about local models, you know, going outside the OpenAI Anthropic ecosystem? Like are you playing with any of that?
</details>

>> 是的，目前我的一台 Mac Mini 正在运行 GLM-5.2-Flash。我一直在琢磨这些开源模型，在工作业务层面我们也非常倚重开源模型。就我个人而言，在企业级架构中，前沿模型的规模化应用必定存在一个财务上不再合算的拐点。比如在医疗行业，你不可能给每一个患者都配一个前沿模型，否则账单会高到根本承受不起。所以我们非常重视开源模型。对于小型智能体来说，我运行的这个 GLM-5.2-Flash 拥有 230k 的上下文窗口，支持工具调用（Tool Calling），能够处理一系列相对小型的任务。它当然不如能够处理任何我指派任务的 Jarvis 强大，但它能够胜任小型事务，这正是我进行压力测试的方向。因为运行 Jarvis 每月光是付给 Anthropic 的账单大概就要 500 到 600 美元。如果有些环节我不需要付费、几乎零成本（只需承担本机的电费与运行开销），我能借此完成多少事情？开源模型绝对是我越来越深入探索的方向，看看它在不同硬件规格和设备上能发挥怎样的效用。
<details><summary>Original English</summary>
>> Yeah, one of my Mac minis right now is running GLM 5.2 flash, right? So I'm being tinkering with some of these open models, right? Even work wise, we are very heavy on that. Personally, I do believe in enterprise architecture. There is going to be a threshold after which a frontier model at scale financially you won't be able to make sense like if somebody thinks something like a healthcare you can't give an oped to all the patient that you have otherwise you will end up with a bill that you can't afford, right? So we have been very high on this open model. So
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 有没有你认为 GLM 特别擅长的具体任务？比如有人想知道“我能把什么工作迁移到 5.2 Flash 上”，你有没有发现它在哪些方面表现相当稳定？
<details><summary>Original English</summary>
>> Is there task that you think GLM in particular like does well where somebody's saying like what could I move to a 52 flash? Like is there one that you found like yep it's pretty solid at whatever?
</details>

>> 目前我发现，涉及到浏览器自动化操作的事情它做不了，那是它的短板。但我以前设置的内容摘要类任务，比如各类信息流资讯的摘录、汇总并发送邮件，它都能完成得非常出色。但当需要执行复杂的浏览器操作时——因为 Jarvis 会对浏览器当前状态截屏，然后基于画面决定下一步操作——GLM（至少 Flash 版本）就开始掉链子了。但对于普通的外呼调用，它表现得非常好，因为那不是由它直接驱动主函数，它只需调用像 Bland 这样的服务发起呼叫，然后对通话内容做总结，这它完全能胜任，而且能把信息提取出来。它在摘要生成、对我的邮件执行 cron 定时检查方面表现极佳。只要是直接交互、无需操作浏览器的场景，它都表现良好；一旦需要与浏览器打交道，它就难以应对了。
<details><summary>Original English</summary>
>> So right now what I found it like any of my browser staff it can't do like so that is where it like but any of the summarization piece that I used to have right so like all these feed your digest that I used to have summarizing some of those things emailing those thing it can do really well but when it has to operate through complex browser function because that is what Jarvis will do right will take a screenshot of the of the browser what is happening over there and then form what the next action there is where GLM basically start like at least the flash one starts to fail but normally like for calling for that it does very very fine because it is not the main function. It is calling something like a bland to make the call. Get summarization of that call it can do. It can do fine there and take myself those pieces. It is great at summarization doing some of these cron checks on my email. It's great at right wherever there is direct where it doesn't have to play with a browser it's good at. When it starts had to play with the browser then it starts to fail.
</details>

### 人机协作与督导策略

>> 明白了。最后一个问题：当 Jarvis 没有按你的预期行事，比如它没有去按电梯按钮、或者没有回复时，你是怎么给提示词的？你会大吼大叫吗？你对 Jarvis 友善吗？你的 Prompt 策略是什么？
<details><summary>Original English</summary>
>> Got it. Okay, well and then my last question for you which is when Jarvis is not doing what you want, when it doesn't press that elevator button, it doesn't reply, how do you how do you prompt? Are you are you a yeller? Are you kind to Jarvis? What's your what's your prompting strategy?
</details>

>> 我想我更倾向于大吼大叫那一派。[笑声] 不仅仅是大声嚷嚷，我说话确实挺刻薄的：“这实在太蠢了，这事我已经跟你强调了五遍了！”它也会道歉：“哦我明白了，非常抱歉，保证不会再发生”之类的话。但我确实会给它很大压力，让它觉得自己搞砸了。所以介于大声嚷嚷与和蔼可亲之间，我算得上是尖酸刻薄那一类。
<details><summary>Original English</summary>
>> I would say I'm more of a yeller something [laughter] I'm more than a yeller I'm I do get mean right that this is really stupid like I have told you this five times and it also apologizes oh I understand I'm really sorry I do won't happen again and those kind of thing but I do make it feel really bad that it did a really bad job at it. So it's like that so it's between a yeller and a kind person it's like mean mean mean.
</details>

>> 我今天早上用 Codex 时自己也感到非常抓狂，心想“你甚至都没问我一下”，气得不行。你知道，有时候我们寄予厚望，但最终期望却落空了。这次聊得实在太尽兴了。非常感谢你向我们展示你的架构配置。我们在哪里可以关注你？怎样能为你提供支持？
<details><summary>Original English</summary>
>> I I was uh I thought myself pretty frustrated with Codex this morning I was like you didn't even ask me like I was so exasperated. You know sometimes we have high expectations um then they they get failed failed to be met. Well this has been super super fun. Thank you for showing us your setup. Where can we find you and how can we be helpful?
</details>

>> 大家可以在 LinkedIn 和 Twitter 上找到我：LinkedIn 上搜索 Ankit Maheshwari，Twitter 上是 Ankit28。目前我在 Innovaccer 负责工程和产品团队，我们正在招募同样认为哪怕只有 1% 的痛点也需要被解决的同路人，尤其是医疗领域的痛点。这就是我们所做的事情，也是我在不跟 Jarvis 捣鼓时的主业。如果有人渴望解决医疗领域的麻烦，我们随时欢迎这样的聪明人才加入。
<details><summary>Original English</summary>
>> You can find me on LinkedIn and on Twitter right Ankit Maheshwari on LinkedIn Ankit 28 on Twitter and right now at Innovacer I believe the engineering and product and we are looking for people who also like feel that even one person annoys need to be solved and especially if that annoyance is in healthcare and that is what we do, that is what I do basically uh when I'm not basically playing with Jarvis. And people who are looking to solve the healthcare annoyance, we are always looking to hire smart people like that.
</details>

>> 太棒了。非常感谢你做客《How I AI》。
<details><summary>Original English</summary>
>> I love it. Well, thank you so much for joining How I AI.
</details>

>> 谢谢你。非常感谢邀请。
<details><summary>Original English</summary>
>> Thank you. Thank you for having me.
</details>

>> 非常感谢大家的观看。[音乐] 如果你喜欢这期节目，请在 YouTube 上点赞并订阅；更欢迎留下评论分享你的想法。你也可以在 Apple Podcasts、Spotify 或任何你常用的播客客户端找到本节目。请考虑为我们评分和留下好评，这能帮助更多人发现这个节目。你可以在 howiaipod.com 查看所有往期节目并了解更多信息。我们下期再见！
<details><summary>Original English</summary>
>> Thanks so much for [music] watching. If you enjoyed the show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.
</details>