---
author: INDIGO 数字镜像
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KW02EUe5LjY
speaker: INDIGO 数字镜像
tags:
  - autonomous-agent
  - artificial-intelligence
  - robotics
  - computing-infrastructure
title: Indigo 2024 年 10 月末直播：Agentic Internet、自回归进化与智能转型观察
summary: 分享者探讨了从人类主导向 Agent 主导的互联网架构转型，认为未来访问与商业模式将重构。内容涵盖前沿实验室通过自回归进化（RSI）加速模型自我提升、个人 Agent 协议与系统形态、具身智能及 AI for Science 的发展路径，并结合市场波动推演了算力集中与开发者范式转变。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Elon Musk
companies_orgs:
  - Cloudflare
  - OpenAI
  - Anthropic
  - Google
  - Meta
products_models:
  - Claude
  - Gemini
  - Grok
media_books:
  - 《上帝的测试》
status: evergreen
---
<!-- chunk 1/10 -->

[Speaker 0]: The yellow...

[Speaker 0]: 这就是界，嘿。

[Speaker 1]: 大家听声音怎么样？Hello？Hello hello，这个万圣节快乐啊，happy...

[Speaker 0]: Halloween...

[Speaker 1]: 我们现在 YouTube 和微信视频号同时在直播啊。我先测试一下声音，先测试一下声音，嗯。我看看，嗯好的好的，有声音，画面 OK，好的，YouTube 没问题。看看，OK，这边声音也 OK，好的，嗯。

对，再次祝大家——应该现在是北京时间已经万圣节了啊，对，应该是。那个礼拜六晚上是去过，对吧？这个不给糖就捣蛋，嗯。然后我看到亚洲好多城市已经开始过万圣节了，在街上，东京、香港。那我们这边还要等到明天，我们应该是礼拜六，嗯。

然后很高兴我们再一次来到 Indigo 的月末直播，这里应该有很多老的观众啊。我这个节目已经做了快两年了，对，每两个月或者三个月直播一次。时间频次很低，一年也就五次或者六次吧。然后呢，我这边主要是给大家分享我过去两个多月的总结，然后包括科技、AI 和投资，对吧。

现在今天此刻，美股收市之后，今天纳斯达克跌了 4% 啊，对，好久没这样跌过了。我记得七月份这样跌过，嗯对。然后每年都有两到三次这样的超过 10% 或者 15% 以上的回调，嗯，在一个上升通道里面，这个还是挺正常的啊。但是每次回调都不一样，对吧，我觉得大家应该很担心、很关心这个问题。我看到 China A 也在下跌嘛。OK，对，大家总说我这个月末直播是给大家来做信仰充值的，对，确实是有这个作用啊。

OK，我把声音再调小一点。我看看现在我们有多少人在线呢？现在有 80 个人在线，基本上我能看到有 100 人左右的时候我们就正式开始。通常会等 5 到 10 分钟左右，嗯，在这正式开始之前呢，我会跟大家聊聊天。我想想看，YouTube 这边 OK，声音也没问题，好的好的，非常好，非常好，谢谢大家的支持。

然后上一次直播是在八月底啊，8 月 28 号，那正好是类似是在两个月以前。然后正好这一次呢，我 10 月中在湾区也待了快 10 天吧，一周多，也正好有一些心得给大家分享一下，也正好赶上股市回调嘛。我们是叫回调啊，对，叫回调，股市回调。然后当然现在市场也很担心，AI 你会这么烧钱，然后你赚不到钱，还会影响你之前的业务是吧，导致你之前的业务受损，像 Google 这样子的影响它广告收入啊。但是这个不好评价啊，现在都不好评价，这个东西我们得走着看着才说得清楚。有时候 Google 自己来说他们是隐藏是吧，这个广告的收入下跌，这个也说不清楚，对吧，这也说不清楚。但是呢，总体的这个趋势来看呢，我们肯定会完成这一次智能的转型，对，所有的公司都需要这个转型。完了之后呢，还有很多的商业模式，新的商业模式会出现。

然后正好这一次，为什么这一次的主题叫 Agentic Internet？就是正好顺着 Cloudflare 的 Connect 活动，我们来做的这样的一次选题。这个对我个人的触动还是蛮大的，因为看到这些活动之后，我也有些想法吧，所以正好趁着这一次，我说赶紧赶紧要在这一次月末直播跟大家分享一下。因为我下下下周之后就不在温哥华，我可能在欧洲了啊，然后在这个万圣节的时候给大家分享一下我的一些看法。

今天准备了非常多的内容啊，我觉得是，而且我还裁到了三分之一。我之前准备了可能有一百多页，那真是太多了，这个内容我得放到新年直播里面给大家分享一下。很多东西可以往后放一些，但是呢，今天我也有很多的东西给大家来分享。

我们再等三分钟好吧，再等三分钟开始。我看看现在在微信这边有一百人在线了，大家可以鼓励一下啊。我这边是无偿的给大家自我分享，如果大家觉得过去一年两年看过我的内容，大家可以在这里帮我刷刷礼物，激励一下我啊，正好是万圣节吧，好吧。多谢多谢，多谢 Canana，跌麻了对吧，确实跌麻了。不过还好，你在美股如果待过十年以上，这真的不算什么啊。但是呢，现在这个市场因为所有的焦点都在科技和 AI 嘛，所以说你在这个板块上面的杠杆非常高，而且现在都是自动化程序的交易，它一跌就跌得很快。而且你看得出来现在股市的交易节奏就不像人类干的事情，对吧，它很机器，嗯，这很机器。所以说我觉得作为一种人类的生存还是挺重要的。我觉得人类在这个机器操作的股市里面生存法则就是降低交易频次，然后选择好阿尔法，有耐心，然后控制情绪就好了。

OK，再等两分钟好吧，一会儿就切入主题了。好，现在 106 人、107 人，好嘞。差不多，再等一分钟好吧，我们就开始。

今天这次的直播有几个，因为九月份模型发得太快了，因为这些 AI lab 头部的实验室，我们叫做 frontier，就是前沿实验室，他们基本上都进入了 RSI，就是递归式自我进化，是吧。这样子的一种，你可以看到 Google 现在发版的速度，它那个 Gemini 从 1.5 从 Argon 到 Carbon，然后后面还有一个新版本，在 Carbon 之后还有一个，他们内部已经在用了。我估计它就一个月一版吧，它就一个月一版会往上走，而且速度会很快。然后我们可以看到 OpenAI 和 Anthropic 也会非常快的速度，我一会儿会在里面给大家分享一下他们为什么会这样子。

好的，那我就开始了，好吧，我们就不耽误时间，我们正式开始，因为内容会比较多，我就节约一下时间，不然我讲太久也挺累的。

我先看看把 PPT 打开，稍等一下啊，我要录屏，要 record screen，等一下。我要用一个 QuickTime recording。好，这样子大家可以看得到我的头像，一会儿就看得到了。好的，这个屏幕上面我一会儿就切换过来啊，一会儿切换过来 keynote 模式。大家看到我的屏幕，我先开始 record video，我得先稍等一下，我先停一下啊。

稍等一下，我不知道现在的麦用的是哪一个，我再来录一次麦克 recording。我能够选到麦克风吗？稍等一下，我设置一下 input，OK，我用这个会好一点，这个会好一点点，我的麦克风换过来了。好，这样收声好，然后再来录啊，马上开始。确保一下，哎，这里 OK。这样子马上开始，好，在录了，在录制。

好，大家能看得到啊，看得到我这边的……为什么这个上面是个矩形的？我先把这个关掉啊，等一下。画面的把它挡住了，video device，嗯，这样就好了，这是个圆形的了，不会挡画面了。好，不好意思，时间一久就忘了怎么操作了。好了，好的，好了。

OK，现在我们就正式开始，欢迎大家来到 Indigo 的月末直播，这是 2024 年的 10 月底，今天正好是万圣节。然后呢，先祝大家节日快乐啊，对，祝大家玩得开心啊，如果有小朋友多要点糖。

这一次的主题是 Agentic Internet。我前面在直播开始录制之前给大家分享了一下，这个是正好过去一周多吧，过去十来天我在湾区待了一段时间，然后参加了 Cloudflare 的活动以及 Vercel 的活动。然后呢，大家都在提这个概念，Agentic infra，所以我就把这个东西当成这一次主要主题，好吧，我们就往后面来进行。

先跟大家快乐一下，这两天股市跌是吧，大家可能心情不好，我们来娱乐一下啊。我先拿这个 meme 视频给大家分享一下啊。这两天股市在下跌，我们用这个来烘托烘托气氛。这个是前两三周吧，在 X 上特别火的，来自于 B 站的一个视频，后来被人转到 X 上去了，然后埃隆·马斯克也转了一遍啊，超级火这个视频。对，这个就是没有 AI 我们不可能实现这样的人物场景切换嘛。

### 今日目录与核心框架

好吧，我们接下来进入正题。今天的目录啊，内容有点多啊。
- 第一个是 Agentic Internet；
- 然后第二个呢，我们会聊一下 Personal Agent。我记得我好像在差不多三周还是四周以前给大家直播过一场了，就是周末的一个氛围直播，讲了这个 Personal Agent，就是个人代理，然后这里我认为它可能就是 Agent OS 了；
- 然后呢，还有一个自回归式进化，为什么现在模型这么快的速度升级；
- 然后还有白领的再次危机，因为这个造成的一些数据分享；
- 然后呢，从 Agentic 到 Robotic 啊，我给大家分享一下这次在湾区也 get 到了很多新的观点吧在这里；
- 然后呢，AI 研究科学意味着什么；
- 然后推荐一本书《上帝的测试》；
- 然后以及投资的几个路线；
- 最后还是加仓啊，惯例。

然后这边我在左边放了一个视频，大家可以看一下，这是我当时我们记录的内容：

[Speaker 4]: 接待的内容核心是三样：AI 投资认知框架。它不追热点，追的是底层结构，布罗代尔的三层历史观、Deutsch 的乐观主义、Revired Index，这些框架反复用，用着用着就成了自己的招牌菜。最大的优点是真干活，vibe coding 现场写，token 成本当场算，不装。最大的问题是节奏慢，两三个小时一集，信息密度高但消化费劲，小白吃着容易噎。总的来说，贵是贵了点，但吃了不伤心。

[Speaker 1]: 对，这是我们当时在 Palo Alto 开车的时候，让那个 Grok 自己去研究 Indigo 的 YouTube，然后它做了一个总结，然后用少歆文学体是吧，来给大家做了一个总结。我觉得挺准的，挺准的。

其实这个就是一个 agent 对吧，这就是 agent，它实际上连接了我自己的 Grok 的 agent，它可以控制它们。我记得我之前做过很多的分享啊，这就是一种形式。这个 agent 非常依赖于入口，非常依赖于入口，我最方便地接触到它，我就能够使用它。我们开着这个 FSD，然后旁边就有一个超级牛逼的 agent，我觉得这我几年前想这就是科幻，但是现在科幻也变成现实，对吧。

### Agentic Internet

好吧，我们今天进入这个正题。OK，这有一张图啊，有张图，这个图我觉得不错，这是 Coatue 画的。我们现在在这个 Intelligent Age，就是智能的时代。然后呢，Tokens replace work。然后实际上在上一个时代，我们就是从个人电脑诞生一直到移动互联网，比如从 1950 年到 2020 年这一个阶段呢，是叫做 Software replaced paperwork，就大量的软件，digitalized world，大量的软件在代替人工或者手工，或者说是 paperwork。然后现在实际上是 tokens，就是 AI 来代替我们的人工劳动。再往前就是 Machine replace muscle，然后 Farm replace foraging，对，农耕代替狩猎，机器代替体力，然后软件代替 paperwork 或者脑力，然后 token 代替现在的脑力工作。我们正在经历这样一个时代啊，但是这个时代会比较颠簸，我再说一下。

所以我拿这个图，因为我之前在过去一两年的直播中都会不定期的给大家总结一下这个时代的节奏，我正好用最新的一张图给大家看一下。

然后第一个呢，我们就讲 Agentic Internet，这个就是代理式的互联网。Agentic，对，这个形容词，代理的互联网。这个是我当时现场拍的照片啊，应该是在 10 月 20 号，在 Cloudflare，它在旧金山的那个会展中心里面办了一个活动。这个第一个主题就是 Agentic Internet is here，对吧，然后——

<!-- chunk 2/10 -->

[Speaker 1]: 这里面过去就是我这样来说，互联网的结构转型已经开始，呃我们用户——互联网的用户正在从 human 迁移到 agent，而且用量会激增上千倍以上。我们五年之后可能每一千个互联网访问里面只有一个是人类的，剩下九百九十九个都是 agent 的，这是一千倍以上。

然后呢在这个时候我们其实要想什么投资所有获利率这一转型的公司，这是这是一个切换开始了。其实这个数字应该是在我记得当时 Cloudflare 分享，他们预测未来 2027 年实现，就是说 agent 的互联网调用超过人类，2027 年上半年一月份第一季度的时候。但是他们其实这个数字已经提前了，在 2026 年的 5 月份的时候，agent 访问的请求数量已经超过人类了，啊已经提前了，提前了半年对吧。因为可能因为今年上半年这个 agent 的这个发展得比较好。然后呢那所以说也是今年回报最好的公司之一，我自己和我的 fund 也都持仓了，就 shipping。当然这两天的回调对吧，just beginning。

### 互联网架构转型与 Agentic Infra

这是第一个主题。为什么是这样说呢？因为行动是发生在网络上，action 就是模型是 AI 的地基嘛，然后今天的世界上是由 agent 主导的。模型做决策，这是 GPU 的问题啊；然后第二个，agent 采取行动。agent 采取行动，因为模型主要是做做选择的，做决策、给出如何做，然后真的来做是 agent 来做。然后这个是 CPU 和网络的问题，这又回到了我们传统的这个前一代的互联网，CPU 来做这个访问的所有请求的序列，然后网络响应。GPU 云是为了决策而建的，那么 CPU 和网络和包括我们所说是 SSD 啊硬盘，是为了在网络上发生行动而建的，对吧。

当然这个大家如果上半年做半导体投资，这个故事因为讲过很多遍的很多遍的，但是但是我放到这儿，我再强化一下这个事实，它是正在发生的事情。你不管现在股市是怎么样子的，这个需求就在这里。当然股市上面很多公司的股价可能被 pricing 了，被 pricing 了，但是呢这个需求是真实的增长，而且未来会更多会更多。而且未来的这种对于这个 CPU、网络请求的这种结构会更加地来做变化或者小型化，每个人都会配上一个 VPS 嘛，这个是必须的。好吧，这个是这个结构性转型的开始，就真正的 agent infra 开始。

然后呢这里面商业模式会有什么变化呢？这是我第一天在 Cloudflare 的这个会场上，正好把这个信息给大家带来了啊。当时他们说了两个，但是我记得分享了两个，CEO 分享了两个。第一个是对 Cloudflare 这样 infra 来说，因为过去因为他们主要是做 DNS 和防火墙嘛，还有一些网络请求拦截的，因为它背负了世界上最大的无效请求。因为很多网站的 DNS 都是 20% 的流量来自 Cloudflare，互联网上如果它宕机了之后，可能我们市面上有一半的网站就没法访问的。

对，第一个是有先降负载。因为 agent 更多，因为 agent 的使用量会比人类高一千倍，那么我们不可能为了这个东西再去建一千倍以上的响应请求的设施。我们必须把很多这种响应请求变成就是让 agent 主动去获取，或者是 push 给他，就是这个东西变成抓取的变化。因为我们过去的互联网是搜索引擎去抓，或者说是像模型公司训练的时候他去抓数据，他去抓。然后接下来呢，我们所有的网络服务如果都 agent 在前面之后，他会和主动的搜索引擎和模型公司，和模型背后的这个 agent 服务来进行主动通讯，来降低网络请求、降低负载，减少重复抓取。啊这是站在 Cloudflare 的立场上，他们做的第一个——先降负载。

然后第二个呢，让内容获得收入。因为过去的每次请求都是没有收入的，所以我们叫 agentic payment，让所有的请求都能够获得收入，有需要的情况下，就内容创造者任何一个请求代理。所以说站在这个 infra 基础上面，把网络的抓取结构改变；第二个，让内容的付费生态产生改变，这最重要两个底层的改变。因为 agent 自己会去协商，对。然后这个是未来五年之后我们可能会存在的，当然包括电商啊，或者特别是我们现在 API 请求各种这种信息、调用信息，我们都可以来变成付费式的，然后 agent 自己去付钱。

那么这里面也会有因为 Cloudflare 自己也建，因为他们觉得现在所有的区块链速度太慢了，他们自己也建了 chain，自己也发了稳定币，对吧。当然接下来可能会有各种合规的问题和各种合规的推进，会让他们这个事情这个东西变得更加高效。

OK，这个是互联网商业模式的变化。那我们还能看得到啊，这个比较技术一点啊。那么在这之上，什么叫做 agentic infra？这个是来自于 OpenAI 发布的一个 Agent API，因为他们之前在今年 6 月份就发布过一版一个调用，然后现在呢他们把整个 agentic 分成了三层哦。

第一层就是他们自己啊，就他们自己模型加 infra，比如说 Codex 或者叫做放在 Anthropic 那边就是它的 Claude Code，在最上面这一层。然后他们所有的 agent 运行，它必须有一个环境啊。就是我们自己用 Grok 或者有个小虚拟机在云端，或者大家用 Modal 也有个虚拟机的云端。然后最终呢，如果说企业或者是执行某一些特定任务的这些 agent，他们都需要有个小电脑在云端。啊这不可能是你理解的电脑，也可能是一种安全沙箱啊，这个技术用词啊就 sandbox，一个沙箱。它执行完了之后才可以把沙箱放掉，这是个小电脑嘛，这是个小电脑。

然后呢所以说 OpenAI 它就和所有第三方在合作，你可以选择，比如说你可以选择 Cloudflare 的沙箱，你可以选择 Modal 的沙箱来做这种，包括 Vercel 的沙箱。正好这一次我参加了 Vercel 和 Cloudflare 的两场活动嘛，我觉得还是有一些收获。然后这里面就会涉及到什么算力、存储、冷启动，还有各种合规、VPC 部署，有非常多的新东西啊。这还不只是虚拟机哦，特别是在很多企业里面使用，它有很多新的东西，然后这里面最多的就是算力和存储，是需要大量的数据。

然后第三个就是开发者要做的事情呢，在最下面一层，我们自己的工具、我们的 knowledge、我们的工作流，我们就配在本地或者存在沙箱里面，然后呢当需要用的时候就装载到沙箱里面去执行。我现在我自己就是这样做的，我所有的工作流都在我的 Mac mini 上面，当 Grok 需要用的时候，它自己就从 Mac mini 上面把数据抓走，放到它自己的 VPS 里面去做，啊它已经实现了这些功能，还是不错的。

所以说这个结构给大家分享一下。那么中间这一层和下面这一层就是大家能够做的事情啊。当然我觉得可能我们能做的也是第三层，第二层也被部分的巨头给垄断了，对，做这个沙箱的工作。当然你可以在企业里面用啊，我觉得这一块呢我今天就不展开了，我计划是在有一个 agentic 的主题里面来做。好吧，我们可能年底或者明年新年直播的时候会来给大家分享这个东西。

OK，这个东西很关键啊。这是来自于 Sequoia 的，我当场拍了一张屏幕。第一天看了这个，这是他们的那个应该是 CPO 吧，就是首席产品官在分享的：“Company building is agent building.” 啊我们接下来在运行一个公司的时候、设计公司业务的时候，或者让公司运作的时候，实际上就是 build agent 啊。这个也很清楚的，从今天来看这个 slogan 我拍在这儿，我应该把它截个屏放在这儿。

然后这边还有一个数字，这是当时在 Vercel 的第一天的活动上面，他们邀请 Anthropic 的平台工程负责人，他们都有一个 cloud 工程的负责人，他们梳理的一个项目：如何让 agent 工作更有效率。这个数字我觉得特别好。如果你只让 agent 去做执行，只纯粹只是执行，呃它可能只有 21% 的任务能拿到满分；如果说你再找另外一个更强的模型当顾问，那么它的成功率就会提高啊；如果说对过去复盘的话会更高，会更高；如果说把经验都写入记忆，让它自己……因为 Anthropic 的 Claude 上面它有一个 Memory 功能，如果大家用企业版的调用的时候它就有这个功能，另外你所有的 context 它晚上它会给你自动做整理。然后有了 Memory 之后，人类也会这样，我们每天晚上睡觉的时候，我们做梦实际上就重新修建我们大脑里面的神经元，把哪些写入记忆、哪些不要的，就是这个东西非常重要，睡觉也是非常重要的。所以人要做梦，机器也要做梦，模型也要做梦。如果说我们有了这些机制之后，你的这个任务执行的准确度会高更多，执行拿到的分数就是到七十几分，实际上提高了 3 点多倍啊。这个数据我觉得比较重要的，全面跟着这个 agent 执行的分享给大家。

### 从流水线到 Agent Loop

好，那么实际上就是我们工作就是这样子，就是从流水线到 agent loop，工作在升维了。然后呢大家如果我知道在听众里面啊，应该有很多人已经玩过了，对不对？大家去用 Claude 做 MVP 是吧，后面会来分享一下 Claude 做的 MVP，然后用 JS 生成一个网站，或者说每天去自动需要执行的代码，我们都会把它配置成一个 agent loop，一个代理循环。我自己的每天我要做的工作，比如说每天的我的新闻日报，我的……有一个 agent 的工作；然后我的市场追踪、市场信号，我都有不同的 agent 来帮我做。然后它会写成我本地的文件，然后我的另外的我的 Claude、我的其他文件都能够去读这个东西，我问他们就好了。呃我现在还没有做网页啊，呃接下来会做。

所以说人类的角色就变了，传统的我们需要螺丝钉的执行方式，就大量的白领劳动会被替代掉，对。然后组织结构也会重新改变，未来所有的公司业务流都会是自动化的设计的 agent loop，嗯对。身为人类就退到循环之外。我后面正好昨天 Google 发了一个——前天昨天 Google 发了一个研究报告，就是关于这个人会怎么转变的，后面我给大家分享一下，对，人类智能的形式在逐步提高，我们人的工作会怎么变化，以及怎么退出这个工作舞台。嗯对，所以大自然相当于启动了新一轮的人类筛选程序啊。对，现在今年开始了，今年开始了，从流水线到 agent loop，这是工作的升维。

### Agentic Commerce

OK，那么再说一下这个里面有一个视频，我给大家看一下关于 agentic commerce 的电商的：

[Speaker 1]: "I think an agentic commerce is very real and very early. I think people like I wouldn't imagine it's overtaking all commerce. It's going to replace some percentage of commerce, maybe 20%, 40%, maybe 50%, with people just talking to agents and automating things. But it will also add 50%, it might grow the entire thing by 50%. But that's going to be so many new forms, and this is the stuff I'm really excited about, let me call it project-based commerce. It's like then people have some kind of objective, like, hey..."

[Speaker 5]: "...it's Halloween soon. The rest of my street makes sense of my houses, I always want to do it, I'm too busy, can you help me? And it's like, if you try this with tools right now, it might actually suggest, hey, can you go out, go to the street and take a picture of your house? And they can mock up some things, and they can order all the pieces that you want in time for Halloween. Or much simpler, you want a 3D printing project with your kids on the weekend, all the filament, whatever else I need, arriving before Friday. It's like whenever there's a bit of like this event, but you want stuff for a project. These kinds of things, I think that stuff is really, really cool, and you're seeing a lot of it, and most of that is additional consumption, so people like wouldn't have done it."

[Speaker 5]: 对，这里有个很重要的一个观点，就是我也我也挺认同的。Shopify CEO Tobias 当时我们现场录的，嗯 agentic commerce 实际上它会增加一种新的，它会让整个商业变大。就之前我们人类觉得很麻烦的事情、不想做的事情，比如说我自动的我看那天看到郭宇啊，郭宇在 X 上分享，他他把他家里的……

[Speaker 1]: 电子烤箱啊什么东西都连起来了，然后呢下单去去订食物。如果说这个很很像刚才 Tobias 说的这个意思，呃包括 3D 打印、机器人，有些事情这么麻烦地下单我就不做了啊，对人类来说。但是呢如果说我想了一个项目，而且呢把这个东西都有条理地帮我整好，让它去下单，那这个事情就成了对不对。因为人怕麻烦他就不做这个事情了，但是如果有 agent 配合你之后呢，它就会把你的消费量变大。对，以前不可能做的这些工作也都做了，所以说市场就自然变大了。他说整个盘子可能会再大 50%，当然其中的 20% 或者 50% 会被 agent 替代掉，就不是由人类主动去购物了，但是整个的电子商务的市场会再大 50%，因……

<!-- chunk 3/10 -->

[Speaker 1]: 为人的这个需求变多了，因为 agent 的驱动需求变多了。这个东西除了电商之外，它会延伸到各个领域里面去。你能够做的事情变多了，你能够做的事情、特别数字化的东西就变多了，你效率变高了。就是现在大家有了 agent 之后，其实每个人都变得更忙了，对吧？因为你的时间利用率就被它提升了，被它提升了。

所以我觉得，如果说真的互联网是一千倍以上都是 agent 访问的，那我们整个的生活和我们整个网络结构就会全部都不一样。

### Personal Agent 与 Agentic Internet

我们拿电商来举一个例子。OK，那么前面我们讲了这个 agent 体和 internet，当时我取了一个小的、我做了一个快速的一个分享。我接下来，我在后面的这一两个月里面，我会把这个东西做成一个更加详细的报告，叫 Agentic Internet，包括公司怎么看的，会来做报告给大家。然后呢，这也会包括这个 personal agent。Personal agent 就是 equal agent OS，这是我写的，我认为它是个等号，它就是 OS，它就是 OS，新的 OS。

我画了一张图，是三个我们用的比较多的：The Muse，中间是 Dot，然后最旁边是 Groq。这正好是我和……23 号的时候，我邀请万维钢老师，我们正好在 Podbean 录了一期节目，我应该会在 11 月中下旬的时候放给大家。对，然后我和老喻，然后还有万维钢，我们聊了一期这个 AI 时代的存在主义，然后 AI for Science，还有各自的 personal agent。我正好用这张图感受一下，我把我们自己三个人换成我们各自使用的 agent bot。对，好，预告一下，预告一下新一期的这个 Ego Talk。

好，这里有一个视频，大家也可以感知一下，拿这个 Groq bot。这是 8 月份的，8 月份他们上线的时候发的一个广告，比 Muse 早。我现在所有的社交频道都是有各种 bot 管理。

"bring on a worker to my team, is actually watch that that that someone who has having actual computer instance that has the browser open that understands how the site actually functions, that's I think why it's worked so well. All started with email. I said just go off and send all them, and sent out as I said. And it's kind of when I'm not switching between everything else and it's so natural. Can really imagine going back to an old way of working."

对，通过他的广告来感知一下大家怎么用 agent，团队怎么用这个 personal agent 的画面。

我自己就在用它来管理我的社交频道，因为它访问 X 是免费的嘛，这是非常好的一个福利了，包括 LinkedIn 啊这些东西，还包括我的账号整理、我所有的东西。我基本上通过 Groq bot 和 Muse 来管理。如果具体我怎么用，大家可以回看我差不多三周之前的那一次直播，好吧，这是 Groq bot。

对，这我做了一个总结，当时画了一个 meme。对，小扎又一次在抄 Elon Musk。上一次是 SpaceX 说要做 new cloud，就是他要做芯片，然后小扎说也要干这个事情，对吧，导致 6 月份的股市暴跌的起点开始。OK，大家都觉得他用不到这么多算力，他是不是模型不行了？

好吧，那么我自己的感受就是说，对于 personal agent，Meta 的 Muse 就是给普通人设计的，它体验非常好，很简单，一个对话，然后还有好多好多贴心的小功能，形象也很可爱。然后 Groq bot 呢，我觉得是给 geek 用的。对，这个区别就像是 Instagram 和 X 的区别。当然我觉得最终的用户量可能会更大，因为毕竟它的这个平台的覆盖量大很多，好吧，这是我的一个小总结。

当时是在我 10 月 7 号的时候，我做了一个……现在此刻我们都只能玩……为什么我喜欢玩 Groq bot？因为我让 Groq 可以访问所有的模型，所有的模型都可以用在这里。你用 Gemini 帮我生成一张图，你把 The Information 这个采访里面的采访人提到的数字帮我生成一张极简的信息图，只强调数字，黑色底板的白色前景。现在就来调用 Gemini 来……对我先放出去，他现在在兢兢业业地帮我干活了。

对，我问他，我让他……我说数字有错误标注，可能不对，然后你用 Opus——我都配置好了——来校验，然后你给我结果。他说哎用高能力模型，他知道他不行，对。然后上面还有就是 info 之前大家有没有在的时候，他就直接说用 Gemini 来，所以 Groq 就直接调用 Gemini 来去生成，对对对。然后他也愿调用 Opus 来，他知道用高能力的，因为 Opus 很贵嘛，是吧？也还好，也还好，还好。然后 Opus 3.5 挺不贵的，然后跑起来，他现在把结果出来了，他说这个重复了。

好吧，这个是我上一次的录屏，给大家看一下我怎么用的。但是我现在的 agent 比这更多了。在这个里面，当时演示了一个让 Groq 来路由其他的模型。后来发了之后，被 Elon Musk 给赞了一下。我当时为什么呢？当时正好当天的时候，Groq bot 他在……Elon Musk 在 X 上说他们也要支持多模型调用，好像那个时候我正好把这个演示给发出来了，特别巧这个时间，对他点了个赞。对，我觉得大家想要趁流量多，在 X 上去发 Groq bot 功能，说不定 Elon Musk 跑来转发你的内容的，好吧。这是一个我自己的使用的一个案例，我怎么用 Groq bot 的。

### 协议与商务：从网页抓取到 Agent 通讯

对，这里有一个采访我觉得比较重要。对，因为 Meta 是把浏览器的能力直接训练了模型，然后其实商家什么都不用做，然后 Meta 就是用他们的网站。如果说合作的商家可以开放 API，那么 agent 就不用再去跑网页了。对，就是小扎说今天每一家公司都有网站、社交账号和邮箱，未来每一家公司都会有自己的 agent，你的 agent 会和商务 agent 去连接，对吧？你可以听一下他怎么讲的：

"It starts off with, I think, we trained into the model very good browsers, right? So that way we want to make it that no one has to do anything to integrate with Muse. And then, but then of course, for what companies go on the list is the most important partners and for people who want to work with us, we'll just get direct API access, right? Then it's okay, then it ends up way more efficient and faster for people to use Muse. It's more efficient because then you don't have an agent crawling your website just going. So anyone who wants to do that, we eventually want to get there."

"And then I think the fullness of time is that, you know, just like today every business has a website and social media accounts and email addresses and all these things, every business is going to have agents too. So in the world we're building that on the other side of it, and so, of course, Muse agents will talk to other type of agents, but they'll work really well with our agents, right? Because I mean, we'll yearn to integrate that. Just, I mean, just using websites is just a moment-in-time thing. It's just to make it easy for everyone to have as a backstop, so it's reliable for people using it, yes, and easy for businesses to get bootstrapped."

"But we have way more businesses that are calling us asking to integrate deeply, and very few really who have tried to block it. And my guess is that the ones that try to block it will end up not being the right strategic thing for them. But we'll see, this will play out over time. We have been very excited about agentic commerce for a long time. Again, it's felt to us like clearly how people are going to buy things in the future. And that was both apparent because no one needs all that friction in their life from the actual buying stage, and how early product research with AI had product-market fit. Thinking from kind of the earliest days, it really felt like computer use was like the last big unlock that we needed to make it happen, because now you can ask Muse to buy anything more or less and it will just figure it out. The computer is right, and so it's the ultimate backwards compatibility, like..."

对，我顺着他这个采访里面，我来补充一下我的一个观点。对于购物或者其他形式的这种商务活动来说，任何机械的，就是说比如我在家里买补给品，买这种东西，我真的不需要选择，标品的标准 SOP 的东西完全可以让 agent 去做，因为我不需要选，品牌很少，这是自动化的工作就可以完成的。

但是还有一些工作呢，对于女生来说，购物过程本身就是一种体验。如果说我们把这个过程让 agent 替代掉了，那就毫无意义了，这个购物就，对吧？所以说有两种商务体验：一种是纯机械化的、标准的，男生干的这种事情，我们可能都用 agent 替代掉；但是很多体验式的活动、购物，我觉得包括线下的商家，它会更加地繁荣。在 agent 多了之后，人还是需要去体验的，我们人生就是体验的，我们有身体嘛。

所以说这个东西会分化。如果说你做的东西不上不下，又是一个标准品，然后体验又不好，那你肯定直接就会被 agent 替代了，或者直接转化成 agent。如果说你的体验会非常好，你强化的就是人的线下体验，那你的东西会非常好，会更适合人来做。所以这是一个我觉得会变的区别，好吧。

那我们看得到，Meta 和 Stripe 他们还和很多公司一块联合发布了一个协议，就是说让 agent 来……就是个人 agent to commercial agent，to merchant agent 来进行通讯的一个协议，叫 Personal Agent Protocol。你可以通过这个协议实现登录、实现钱包，各种各种功能都可以。然后对方的网站呢，它就能够来响应你的 personal agent，你就不需要让你的 agent 去抓他的网页了，对吧？

就前面我们最开始讲到的 Agentic Internet 里面讲到的 Cloudflare，他们说第一点我们要把这个网络请求变得更加高效，现在是很不高效嘛。因为现在是抓取，是吧，然后无谓地读取，因为它是给人类设计的，或者说是这种单向读取网络。如果说我们都是 agent，那么 agent 的握手他们就有更好的通讯方式，那就用这种协议来做，用不着我去抓取、我去读取。所以有这样一个协议在，那么 agent 去别的网站上的时候，他就不是读 API 了，他肯定就是一个 agent protocol，他就把所有的事情干完了，对吧？然后剩下的可能一些很漂亮的东西让大家、人类去看网页或者线下体验就好了。OK，这是这个协议的作用。

那么在这一面呢，其实在 agent 层面上，过去已经出现了几个协议了。第一个是 MCP 嘛，就是 agent 调用工具的协议，就是 Anthropic 提出来 MCP，相信大家很多人用过了。然后第二个是 A2A，A2A 是 Google 这边提出来的 agent to agent，让两个 agent 之间委派任务的，是吧，agent 和 agent 之间通讯的。然后还有一个 A2P，这个 agent payment。然后这个是 PAP，这个是 Personal Agent Protocol，这个是 Meta 这边出的个人 agent 代表用户去企业办事，就 B2C 的前门。然后 user、personal agent、company，这里面要实现 OS 授权、身份权限。

然后呢，在这下面有一张图，PAP 的调用链有网站、API，包括各种 company agent 对话任务，可以再叠加 A2A 是吧，对，你的 agent 呼叫别人家的 agent 和调用工具。很快很快这个东西都会出现的好吧，其实大家能看到这里面很多机会啊，对不对？

OK，这是 personal agent，我们前面讲了体验、使用，然后协议我都给大家展示了一遍。那我不知道现在国内这边的这个 personal agent 的情况怎么样，回头大家有时间可以在评论里面说一下。

OK，这个是八款 agent 的速览图，大概现在有……

<!-- chunk 4/10 -->

[Speaker 1]: 多少，就是我们可能比较流行的几个吧。Claude 刚刚出了 Dialt，然后 OpenAI 出了 Operator。OpenAI Operator，然后有 Minimax 他有 Jspark，他现在改名字了，啊？然后呢可能很快又要改名了，因为现在竞争太激烈了。然后有 Geekbot，然后有 Instinct，这个是最早出的，应该是在，哎这出来大概六七月份吧今年。我记得我当时注册了一个云短信和 WhatsApp，它只有这个界面，但是现在我觉得他面临 Manus 竞争压力太大了，然后在卖他的 Manus。

然后还有两个是开源的，大家应该都用过。最火的应该是最右边的这个 OpenClaw 小龙虾，然后中间还有一个 Hermes 的 Agent。这两个基本上是一样的，开源托管的。

这个是大概现在的一览图，我给大家总结一下。那么我认为是这样子的一个情况：对于 personal agent 会是怎么来分工的？一个 consumer 的处理日常事务，然后呢它会在你的手表、手机、眼镜镜面，然后每个人的云端。其实我觉得最适合做 personal agent 的公司是苹果，但是苹果的 Siri 做的跟坨屎一样是吧？对，没办法没办法。所以说你可以看得到 Meta 想用眼镜和各种穿戴设备来抢苹果的这个手机的地位。手机的地位就是至少如果他的 Manus 表现得非常好的话，再配合他的眼镜，我觉得还是很有威力的在这个上面。但是苹果会用手机和手表守住这个战场。

Consumer 我觉得普通创业者就不要在 consumer 去打了，所以说巨头守天下。你像连马斯克带着 Grok 甚至打得都很吃力是吧？在这里面。然后呢我觉得这个定位呢更多的、更大的市场应该是在 pro user，在专业这个用户上面。就是我们可以看到我前面用的那个 Geekbot，它就是这样的一种使用，它有 agent 的组合，它有 loop，有本地、云端电脑——你的电脑和它云端电脑混合使用，然后形成自己的工作闭环。如果你每天有很多个人工作任务或者公司里面的工作任务，它就可以来做支撑的。我觉得这个里面呢开发空间很大很大。但是呢我觉得大部分这个场景呢可能做不大，对不对？但是很多专业用户都会自己配置这些工作流嘛，他并不需要一个你帮他做好的通用工具。但是呢我觉得这里面还有很多 infra 工作可以做。

然后最大的机会呢应该是在这边企业的。企业的它是有非常非常多的 Agent 基础设施、私有环境、云端环境，这是一个巨大的市场，巨大的市场，但是这巨复杂。我们企业转型还没开始啊，我后面会给大家分享一下为什么还没开始，去支撑整个组织的流程。OK，这是最大的市场。

### 个人 Agent 与商业博弈

OK，那么我在最后用一句话来总结一下，就是个人 Agent 会重写整个市场的反向传播。什么意思呢？这个是那个 Stripe 的 CEO 发的：公司是最早的超级智能，他们干嘛呢？他们用摊薄后的认知运营去收割个体消费者的有限理性。我不认为所有的消费者都是理性的。你去银行存款，你不会把所有的钱都放在一个高储蓄账号里面去，对吧？当时说发布了那个什么时候说个人 Agent 可以管理你银行账号了，导致很多银行的股票下跌，因为 Agent 会极大地利用极其理性的方式去把你的钱部署到最赚钱的地方，对不是去收割银行的利息产品。但是个人不会，等于说大量的公司为什么能赚钱？就是因为个人不足够理性嘛，他会非理性消费。

如果说同样的逻辑，Agent 并不会消灭这种不对称，它只是把它挪到了新的位置、新的配置。就今天的博弈发生在公司和个人的注意力之间，明天这个东西就发生在公司的 Agent 之间。就是说你的公司做的生意，你要怎么去路由这个 Agent 是很重要的，所以路由的这个需求是不会消失的。它只是从搜索框和信息流变到了 Agent 推荐逻辑里面去了。谁掌握 Agent，谁就掌握了过路费。所以当时是那个 Stripe 把这个给收购了嘛，把 OpenRouter，开放路由协议的模型路由。估计他们还会做这个 Agent Router 是吧，来做这个事情。我觉得这个是一个很大的变化，因为之前所有的公司就是在消耗人类的不理性，你从人类的不理性里面来赚钱的。如果说其中一部分的使用都变成了 Agent，你的个人 Agent，那就太理性了，那这里面曾经的商业模式就不存在了。

这里面可能有一部分受到威胁，就是为什么这两天 Google 股价暴跌，就是因为他的搜索业务可能会受到威胁。Google 得用自己的 AI 业务来证明他能够把这个收入给补回来对吧？但是我觉得广告是很暴利的，还挺难补的，看看情况了。好吧，这是一个结论啊，这一章的。等一下这个 MV 来休息一下，大家可以看到这个是版权作者的，把它放在这了。

### 自回归进化（RSI）与模型前沿

好，我们下一个话题就是自回归进化 RSI 和白领危机。在这个里面，这是一个专门来做 RSI 的一个评测机构，METR 对，METR AI 他们做了一个视频：

[Speaker 2]: We measure outside index, so we're collecting inside of proxies of the work that researchers do within these labs on pretraining, post-training, harness-level engineering. So it's almost ML research.

[Speaker 3]: Yeah, that's right. There are things that are outside the scope.

[Speaker 2]: In terms of kernel engineering or hardware engineering, um, but we're going to expand over time to cover more sets of tasks like that. And then we're comparing to human baselines to talk sharply how far away we are from the human frontier in terms of these research tasks. And based on our last estimates, um, it seems like Anthropic will get to full RSI by July, maybe August 2027. And like, if you...

[Speaker 3]: Look back six months ago, how far out did that seem?

[Speaker 2]: Actually, the pace has been fairly uniform. It's almost a linear trend over the last year. So like six months ago, the trend line was still July.

[Speaker 3]: Actually, the steepest curve has been...

[Speaker 2]: With Gemini. I think something has changed where they prioritized RSI, and so the most recent model showed a rapid jump on RSI.

[Speaker 1]: 对，这里面两个结论。第一个是 Anthropic 会在明年七八月份达到完全 RSI，它所有的能力都可以让模型自我改进，对模型自己就左脚踩右脚嘛，对明年明年可以完全实现。在这个里面增长最快、速度最快的是 Gemini 是吧？为什么现在 Gemini 发模型的速度这么快？他的 experimental 版本一个月时间不到三周多就出一个版本，那基本上就是模型自己在训练自己嘛。

然后这个里面他们会评测人类在做预训练、后训练，包括什么芯片设计啊这些东西的人力和 AI 进行对比，他们来做这个测试。回头大家可以去这个网站上、METR AI 上看到更详细的数据。那么我们可以看到过去九月底的时候，九月几号出的这个 Opus 3.5 出来之后，它的一系列出来之后，3.5 Sonnet 和 Haiku 出来直接把 Anthropic 的这个量给拉起来了，这是 OpenRouter 上的数据。基本上它抢了其他模型的使用量，因为它又快又便宜又好，Opus 3.5 现在还是王者啊。这个是相比 Gemini 的 1.5 Pro 可能能够跟它差不多，可能还差一点点，比它还差一点点，但是我觉得目前来看还是最好的。这个是因为他们内部也在采用 RSI 训练。

那么你可以看到整个 Claude 内部，这来自于他们的一个指数报告里面，到底有多少工作自动化了。从今年开始，今年五月份开始，五月份之后就百分之十二、二十。我记得跟他们里面一个做系统工程师聊过，他说他百分之九十九代码都是 AI 帮他写的，他基本上不做什么事儿。但是说如果整体来看所有的研发工作，模型 lead，Claude 在这个事情可能很重要，现在是 Claude lead 26% 的工作。对，这个就是他的 RSI。如果到明年六七月份的时候，可能是百分之七八十的工作都是由 Claude 自己的了，自己指挥人类改进自己。Level 5 是完全自动化，现在还没有，现在只是 AI lead。OK，我们明年可能再来看这个表就完全不一样了。

OK，那么现在再来看一个数据，是来自于他的 S-1 报告里面的：到底把算力用在哪了？我记得是 Anthropic 说把他们的更多的算力不用在推理给用户使用，而是用在训练 internal R&D。你可以看到他这个数据，2025 年的 H1、2025 年 H2 和 2026 年逐年在提高，每半年在提高。就是 customer serving 会越来越少了，但是呢他们可能把 customer serving 用更加压缩得更厉害的、蒸馏得更厉害的模型给我们来用，对吧？然后更多更好的模型留给内部使用，然后训练新的模型。因为如果我不这样做——其实表示半年了——如果我不这样做，我就会被对手超过。一被对手超过，我头部的这个 API 的价格肯定卖不出来，知道吧？所以说他应该把最多的算力放在来提高模型能力，然后用少量的算力卖高价的 API 给你用，这个商业模式肯定成立了，对吧？

OK，所以说我说如果说你做不在头部，你的 API 就是地板价，那就是地板价，那你就永远卷在这个商品化的竞争里面。但是永远有头部，那他就可以定价，头部就有定价权。这个就是为什么要争前沿的逻辑。这两天 Google CEO 皮查伊不接受采访嘛，他就说为什么他们 Google 依然要做争头部，就是这个目的，要把这个定价权拉上去。好吧，这个是可以看到他这个投入大量的落在内部，而且越来越多算力的使用。

那么逻辑就是这样子，这也是来自于 Anthropic S-1 的图，那个文档里面的。这边左侧是更多的智能增长，它有 improvement loop，内部的这个循环；那么右侧更多的算力投资会带来更多的智能增长，更多的算力投资就是 investment loop。我赚了更多钱，我就投了算力上去；投了更多的算力，我获得更多的智能，我就赚更多的钱，就形成两个循环。这是前沿模型公司的商业逻辑，就是这样子。我把所有的算力赚到的钱都花在我最好的模型研究上去，我保持领先，当然他也得想办法阻止别人超过他。所以说这是他的商业模式，他就能够把这个模型 API 的溢价给抬上去，然后才能保持更高的收入。这个就是 Anthropic 的逻辑。包括 OpenAI 也是这个逻辑，好吧？

OK，这个是从 RSI 里面讲到的。那我们现在看到此刻最新的模型就是 Gemini 2.0 的 Flash，应该是前天发布的吧？对吧？对，它的所有的指标上你可以看，我提了一下，不到一个月，从 Flash 到 2.0 Flash 不到一个月份，两个版本的提升非常明显非常大。我还没用到 Flash 2.0 呢，还没用到，我估计可能下周就有 API 可以使用了。这个速度是非常惊人的，他们都在通过 RSI 自我提升。而且较前面那个评测公司讲到的，Gemini 是在这个里面增长最快的，Google 投入和增长最快的 RSI 上面。这是他最早的愿景嘛。

因为我记得为什么说 Anthropic 在它的版本 Claude 3.5 Sonnet 从 3.5 到后面的版本出了很多问题，应该就是 RSI 训练出了问题，就是他可能因为这个 RSI 模型还没调好，导致自己训练自己出了一些问题。但是现在到 3.5 的时候已经修正好了，就是非常好了，对，而且语言能力也提升了很多。OK，这中间大家都受过了挫折嘛，但是慢慢会改好的。

OK，那么 RSI 是什么？对，递归自我改进，对，recursive self-improvement，就是递归自我改进。分成两部分：第一部分是现在的 LLM 加软件的演化，其实本质上它就是说语言模型提出修改意见，然后让 Agent 自己写代码，然后运行任务评测，然后再改自己代码。其实它是一个 coding agent 的过程，它并不是模型自己在调参，是模型在写代码优化。之前通过代码来改进自己，然后再让模型提出修改意见。对，这个其实为什么代码能力是最重要的，代码连接重要，它是可以通过代码来实现一切，包括修改自己软件。软件通过修改代码升级的嘛，所以模型也是通过修改代码提升自己的训练能力，改进工具、策略和工作流来改进 Agent 系统，而不是通过直接去改模型权重的。对，因为实验的有效性不等于数学的最优解，对吧？因为数学最优解可能我们用在这现实中使用的时候，

<!-- chunk 5/10 -->

[Speaker 1]: 就感知没那么好，所以说他通过代码做这个平衡。是现在的 RSI 终局是什么样子？软件型，软件循环加硬件闭环。我通过改进算法和设计让机器人自己去做实验，那我后面会讲的，对，然后呢参与自动化制造和维修，然后更强的机器人和算力，就是采矿、加工、制造、复制这机器体系的自循环。

对，我们就是说，我上次前期前两天刚放了一期 podcast，我和郑迪来录的，叫做他叫硅基循环吧。就是硅基循环就是这样子的，嗯，硅基循环就是如果是如何让让让一个人工智能，然后让他自我演化，他必须得参与到芯片设计里面去，改造他自己的数组运行他的东西，然后才能够实现自我进化。这种终局啊，终局现在还实现不了。

所以核心跃迁就是从改进自身代码到改进承载整个自营体的生态系统，从芯片设计、机器人系统都可以自我改进，这个是终极 RSI。好吧，我给大家就科普一下啊。如果再讲更更详细的，因为 RSI 还还有很多流派的，好吧。OK，我们可以讲讲这个最简单的版本。

那么这有个例子啊，一个研究员加一群 agent。这是嗯 Mirae Data 是一家小公司啊，他们做了一个 Mirae Data 的 base 的模型。他用一个一个研究员花了就是只花了一千万美金左右时间，从零开始，从零开始不买数据、不蒸馏、不合成，百分之九十九实际上代码都有 agent 写。那么他自己完成了一个模型，这有个评分啊，这有个评分，评分相当还是相当不错的，就是训练好训练好了一个模型出来。

那么这个东西呢，相当于是所有的之前过去训练模型，由人转向了算力和数据了，然后呢以及 agent 的指挥，有人来指挥 agent 来干这个事情，就是这个把所有人员给释放出来了。那么这个带来的好处就就是说会他给的我，我觉得这个事情的意义就是说并不是说这个模型公司有多强，我觉得更更这个公司做的事情更像是 Codex 或者说 OpenAI 和 Anthropic 的广告。因为他也用了 Anthropic 的模型来训练 agent，来训练这个这个从零开始的模型吧，预训练。就这第三方的 coding agent 来干成这件事，那模型护城河只剩下自己的判断力了，对吧？

那同样的这个东西呢，它也意味着我们未来有多少事情可以变成现实。芯片设计、机器人实验室，甚至是医院，我们都可以用这个方法来改进自己的训练基座模型，啊不对，而不只是租用通用模型来进行微调。那么任何组织扩张不是只招人了，我加算力就好了。然后研究员的日常工作就是更像带的一个小型实验室，定方向、分配分配算力就够了，啊这是很大的一个变化。后面还有很多人会验证这个变化。

OK，那这里埃隆·马斯克当时是在一个月以前吧，他做了一个采访。我也收到了，嗯点开听一下他了：

"I learned a lot learned about chip making, I don't know how to make chips to be clear, um no idea how to make chips. I'll figure it out, um and and I think like there's a lot..."

[Speaker 4]: "...of risk aversion in the chip industry, um and I think what we're going to do when Tesla's basic chip comes out is is like really try some of these um high risk, high payoff bets. Um and in order to do that, you really have to have the complete loop of being able to fabricate the logic, memory, do the packaging, um do the lithography masks and and just... I just have an internship that's all in one building, so you're making a complete computer, testing it, then making new masks and a new chip and have that iterative loop be super fast in the same building. That that's what we're doing at Giga Texas with the research fab. I think it's going to be fundamentally a very powerful tool, because what before any given technology, the measure of any given technology is like how many iterations and and what is that, how much progress between iterations. So like what's your iteration, how many iterations per unit time? Like like how many how many chip designs can you do, um and can you make a test in a year? Um like these days, like it's never..."

[Speaker 4]: 对，这里最重要就是他的两个观点。首先我需要做一个大的 loop，我把所有的就现在都是——

[Speaker 1]: 分散的嘛。现在芯片、光刻都是分散的，我放到一个环境里面去，它是一个 loop。所以说他做 Terafab 就要干这个事情。

然后第二个呢，要靠迭代的版本来加速。因为这个是发火箭的逻辑，因为火箭一版版迭，从从他那个 Starship 第一版一直这样到到十七、十八，每版版的迭代他就能够进步。一样地，如果说我们把这所有的东西放在一块，我设计芯片我也能够通过这个方式来加速改进。

对，因为现在都是分散的嘛，不同的公司在做不同的事情。然后呢这是因为过去的产业结构造成的。如果说以后集成化更高，什么光模块、内存、芯片然后刻板都在一块，对，那说不定我们可能让这一个大工厂里面就是 AI agent 来控制这个工厂，可以完全实现自动化改进和循环。这也是当时埃隆·马斯克要做 Terafab 的这个这个初衷了，对对吧？

所以说我说在未来五到十年，整个硬件行业还有巨大的这个结构性变化，结构性变化。当然这个里面会带来很多波动啊，就会带来很多波动。但是呢这个东西要配合 AI 的进展，AGI 的进展。整个硬件行业现在就在进化，就是芯片就玩开始了。

现在其实 AI 已经参与了好多的芯片设计，包括呃呃 OpenAI 和那个那个赛灵思吧，那那一家芯片设计公司的，做做那个芯片版图设计的这些公司呃来进行合作。他提供专用的模型给他用，然后呢模型就学会了怎么设计芯片。如果他学会了之后呢，那最终只人类只是进行测试了，人类的工作只是测试了。回头如果我实验室 AI 可以来做测试，人类的工作只是监督了，对吧？只是监督了。慢慢的人类在往外退，在往往再往环外走啊，AI 做所有的事情。

如果 AI 真的能够自己设计芯片，通过工厂来生产芯片，那么硅基循环就正式开始了。对，这个是这是一个标志性的一个时刻。

当然埃隆的这个事情呢，总是现实很理想，是吧？对，所以说这个理想理想很丰满，现实很骨感，对，就这样的。他总是会想得很远，然后呢把一个巨大的一个一个一个正确、我认为正确的一个方向时间压得很短，导致大家嘲笑他，你这个事情天天在吹牛逼。但是我认他的很多路线都是对的，这个路线也一定是位的。最终的 AGI 一定是 AI 要接管硬件生产的 AGI，这个才能够真正的……

而且像 Google，Google 的 Gemini、Google TPU 已经在同步生产集成了。那 TPU 的改进会适应 Gemini，Gemini 要改进 TPU，它是这样的一种循环，对。

### 资本向算力集中与市场推演

OK，OK，我们看一张图啊，这张图有点像什么最后的晚餐是吧？当时当时这个 Trump 说要改名，从 AI 改名到 SI，就是从 Artificial Intelligence 改名到 Super Intelligence。啊这张图很有很有很有现实意义啊，也也很嘲讽了我觉得。对，这个人类开了会之后宣布超级智能到来的，大概是这样的一个意思，OK 好吧。我放到这儿，中间带一个梗图。

嗯嗯这里是一个数据啊，这是一个数据。我觉得挺挺有趣，这也是来自于 Coatue 的那个 S-1 报告里面的，他现在的收入和 operating income。

[Speaker 0]: 对，现在 operating—

[Speaker 1]: Income 也是正数了，他已经赚钱了。如果说为什么他是亏本的，因为他当时是融资嘛，融资的这个股票被买回去，应该是卖出去之后导造成了一种财务上的一个负一个负负数，所以导致是亏亏的。但他实际上公司现在是挣钱的了啊，挣钱速度巨快。

然后同时这边是微软宣布了一个裁员百分之二十五，不是这天就劝退，不要裁员叫劝退，你可以收到邮件之后你决定你要不要走是吧？当然如果脸皮厚一点可以赖着，但是每年都会劝退，就是大公司都在做这个，VSP 在做劝退。然后这边模型公司的收入在暴涨，嗯就是这样的一个对比。

对，Token 正在 replace worker 对吧？这是很形象。我前面讲的这个 token 在这前面有张图，token replace worker 啊，就是这样的一张图。那么当智能可以复制，那资本未来会被锁死嘛？就是从人才的竞争到算力竞争嘛，就是很简单。大家用用我用最大的算力，前面也讲到了，刚才那个从零开始训练模型，它只需要用 Anthropic 的模型就可以来干这个事情了。只要一个出色的研究员，代码全部都用模型来写，那么就他只要增加算力就好了，他只要买更多的 token 就能干这个事情，对。他花了一千万，基本上都买个 token 的，花了一千万美金，好吧。

对，那么当资本可以购买了算力能够复制，人才的稀缺溢价就下降了，然后资金会向算力集中。为什么现在大家都在投这个算力？我只我我总觉得华尔街是比较短视的，对，大家不知道投进去的这些钱能够产生多少价值，现在这样的衡量来算他的这个收入。对，我觉得不不应该这样来计算，不应该这样来计算。当然产生的收入会更大，会改变很多行业，但是我们可能会经历过很多很多痛苦，对，但是这个这个回报肯定是会有的。非 AI 部门的融资受压，就是只要是没有 AI 的融资都受压，公司也是一样的。

对，算力向资金向算力集中，然后呢用用利润持续在投资。我们看前面 AWS 就在干这个事情，他赚到了钱，两个循环嘛，看到那张两张图，收益投入了更多的算力和研发，然后存量不停的积累，让算让智能变得更加好。嗯那么就是这样的一个循环。那么人在这个里面才华向上流动就更难了，是吧？对，然后国家依赖依托于这个个人税收和融资能力就下降了。啊资本集中自我强化，然后个人和国家的追赶的空间就狭窄。啊这是一个就是我觉得这是一个比较暗淡的现实啊，未来啊。

对，就算算力持续集中，我们不希望最后最后能够成为这样子，成为这样子就是少数的公司控制更大的资源，然后然后呢技术扩散可能会被会被打破，会被垄断。啊这是一个情景推演啊，情景推演，这只是一个推演。AI 加资本就强过度强化的一个推演。

但是我们也不能够说没有创新出现，对，只是说我们现在投入的这些公司，它的投入 AI 每一分钱的这些算力的投入，未来都会获得更大的回报，啊我们不要看不要短期的看现在的这样的这样的一些市场的波动就好了。但是呢，如果真的实现这样一个未来，社会是很惨惨的，可能当人类不能消费的时候。

就是之前我记得这个 SocGen 写一个报告，把全部市场吓趴了，今年二月份。就说说当大家都裁员之后，我们我没有消费的基准市场啊，知道吧？怎么叫通缩啊，对，就是这个问题。大家都没钱了，我怎么消费呢？没钱，这个公司怎么挣钱呢？啊全世界就一块通缩，AI 带来 AI 会带来巨大的通缩对吧？

这个是一种情景啊，一种情景。但是我觉得这个也不会不会出现，因为人一定会发现其他的事情的意义的，他一定会去干其他事情来做消费的。我这个现在也不好下结论啊。

OK，至少我们看到目前现在市场的几种推演是这样子的，嗯。然后看到一个数据啊，这是 Mag 7 的利润率的增长，只有 Mag 7。这是标普 500 里面的，就是标普的 493 家成分股公司利润停滞不前，从 2015 年到现在只涨了一点点，所有的利润都被谁涨了？都被 Mag 7 涨了，都被头部公司涨了。因为这还只是标普 500，很多新的 AI 公司或者技术公司不在这里面，所以说他们肯定也在涨。

但是呢，标普 500 里面大部分公司，其实标普的带来的上涨都是 Mag 7 带来的上涨，基本上都是的。为什么他们能上涨了？因为他们的垄断，算力垄断形成了，这个人才积累形成了，这个资本他还会更加上涨，还会更加上，他还会更加强大。接下来这些人，Anthropic 这些新的公司上市，他们也会加入这个 Mega 7、Mag 8、Mega 10 在这里面去。然后剩下的所有和这个算力无关的公司都不会上涨，都不会上涨，对。

除非是企业的这个还有一张图，还有效率的问题，企业的整个结构发生改变了，下面的这个曲线才会改变，不然现在不会。因为只有科技公司是从这里面受益最大的，其他的公司很难受益，目前来看。

那么对于个人来说是什么样子呢？这当时 Karpathy 发了一张图，呃现在有 60 亿人没有接触过大模型，75%。然后这里面约有 10 到 20 亿人只用过免费版本。然后呢，有两千万人可能会用过数学和代码这种专业模型，已经用 agent。然后找这是两千万人啊，只有两千万人啊。如果大家用过 agent，你是全球里面的两千万之一，0.2%。OK，我觉得我这里的听众应该都用过都用过，大家都是两千万之一啊。

这里面也只有五千人，五千人是怎么算出来？只有在前沿实验室，包括 Gemini 里面的人，包括 Anthropic 的人，包括 OpenAI 的人，包括现在 SpaceX 里面做呃 xAI 的人，五千多人吧，可能最多有一万人吧。他们用过最前沿的系统，用过成千上万 agent 的协作，他们做科学发现，推动数学前沿，

<!-- chunk 6/10 -->

[Speaker 1]: 人类开始理解不了了。在做这样，这个就是现实世界 AI 能力的认知正在变成一种漏斗。所以说那些说 AI 对自己没有用的人，那确实他也没说错，对吧？很多时候他并没有说错，对他生活里没有需求用这种能力。对，这不是他的问题，这是时代给你出来一个考题，你能做什么变成你的想做什么，对吧？因为之前就是说这是很大的一个选择，就是说我们是量力而行，就是我的能力只能做这么多事情，所以说我就只做这些事情。就前面说到的，为什么 Agent 会提高电商的使用率？因为我不可能自动化的去买这么多我们 3D 打印材料嘛。当我想了一个想法，我跟 Agent 说，它去买，那不就把我的需求提高了吗，对不对？

一样的是，首先你得有想法。那么接下来这是一个非常大的问题，这不是人能，这是一个人的野心问题，你到底想要什么是最重要的，你想做什么最重要的。所以说接下来漏斗的最顶端，这下面他是属于提出大问题的人。为什么前沿实验室都能攻克科学？因为这是大问题，这是难题，他们觉得这个事情有价值。所以说我觉得这个东西，AI 把所有人的需求能力都往上提，但是很多人他确实没有想法，他就提不上去，那他就上不去了。

那如果说大家想学的更多，或者说觉得 AI 能够赋予我这么多能力，我想把它用好，那你就能上去，那你就能先变成两千万人。对啊，你最好最牛逼一点，你可以去到这个头部实验室里面去解决人类的大问题，对吧？这个是现在的一个漏斗，对于个人来说，挺残酷的，挺残酷的。

### 前沿实验室的路线分歧与安全风险

[Speaker 1]: 好，这是我看看，这是九月份的、九月初的。因为这个哥们他发了这条 X 之后，导致 Claude 出来说要减缓，发了很多声明，然后 Elon Musk 出来支持。因为就是因为这一条 X，他今天从 Anthropic 辞职了。他发现在过去三年他在里面做了预训练，他觉得这里面的人，呃，他的下一代系统正在迈入超级人类级别。他们不仅能够渗透任何网络系统，颠覆所有行业，还能获取真正的权力和物理资源。对，他在实验室正在制造这样的模型。

而且这些实验室的人呢，他们对外言行很谨慎的，一般都不说，不能说这个事情。对，他是第一个出来说的，然后导致他们说要减缓嘛。然后私下里都是这样，我见过，我也跟这些研究员聊过，实际上我们在很小范围里面，他们都会说：“我们在给自己挖坟嘛。”就是这个意思。在人类历史上从来没有任何技术活动带来如此沉寂的生存危机，真实的事情。

在这一个风险上面，我觉得他觉得 OpenAI 和 Anthropic 走向了完全不同的极端。OpenAI 多数人并没有意识到这是一个文明级别的风险，他们还在工程和商业关系里面打打转转。但是 Anthropic 显然不一样，他们心知肚明，但是他们却掉进了另外一个“我必须抢先冲锋”的囚徒困境。他们不相信别人能解决这个问题，只有自己先把 AGI 造出来来拯救世界。对，就是说他们是“反正大家都能召唤，还不如我们先召唤出来，然后我来管束他”，对吧？就是 Doomer，就是全员 Doomer 嘛，就是这一套逻辑，宗教式的逻辑。这两个公司价值观是完全不一样的。OpenAI 其实更加商业一些，更加工程化一些；然后 Anthropic 更加宗教一些，对，他们相信自己是救世主，救世主降临派嘛，救世主。

那这是大概的一个来自于前沿研究员的。包括九月份为什么一大堆公司说要延缓 AI，其实他们根本就没有延缓。出来发了一个视频之后，发版本依然很快了，发的更快了。对，因为有竞争的存在。

### DHH 的演讲与开发者范式转变

[Speaker 1]: 那分享一个这个视频，这 DHH，Ruby on Rails 的创始人：

[Speaker 1]: "I have retired from being a professional programmer. I haven't pinned down the exact date, I think it was somewhere around 4 to 5 months ago, maybe March. I should find out exactly when it was, because you know what? That little clip totally true. I spent a quarter of a damn century chiseling code by hand and loving every moment of it. What a wonderful experience and productive time in that era. And that's how..."

[Speaker 5]: "...I believe we should all look at it, not with regret, but with joy of what was, and joy that we were there when we still have to do such things, because they were filled with excitement and learning and satisfaction and flow states. This is not something to look back upon with regret, this is something to look back upon with joy and accept that it is over. Writing code by hand is no longer an economically productive enterprise for the vast majority programmers working at the vast majority of companies. That's today. By the end of the year, it will be virtually all domains, virtually all programmers, virtually all companies. So we best get used to it. We best embrace that we had a wonderful run chiseling that code by hand, and that is over."

[Speaker 5]: "And on the other side of that is a new career, an exciting career, an energized career as a professional maker of things. Yes, you will no longer be chiseling that code by hand, but you will be making amazing things. You will be steering intelligence that was only available in science fiction up until a few moments ago. What a privilege on both sides of that passing, to have been there when we did it all by hand, to be there at the exact moment where we switch over."

[Speaker 5]: 他虽然演讲真的很棒，非常有激情，对吧？首先来了一个过渡，所有的程序员都没有经济价值了。然后这个东西今年是这样子的，明年会扩展到所有行业、所有领域、所有公司。但是呢，带来了一个新的转变：

[Speaker 1]: 我们有了一个超级的智能工具，我可以用它来做所有的事情，是多么让人激动的一件事情，对吧？对，这事物的两个极端都被他说了。这段演讲非常棒。

所以说我这边做一个总结是：Don't panic，不要恐慌，对。然后呢，做一个 builder，做一个 maker。然后呢，我们需要做一个新的 agentic 的 business。然后呢，我会在今年的新年直播、后续的专题直播里面给大家讲解这些东西，好吧？这是一个小插曲或者一个小预告内容的。

### 从数字 Agent 到物理具身智能（Robotics）

[Speaker 1]: 这里到下一个环节，对，从 agentic 到 robotic。这里正好做一个过渡，因为 Agent 大部分都是属于 digital 的，纯数字的；到 robotic 就现实世界了。为什么会做这样的一个环节呢？我觉得这个很重要，这是很重要的观察。

GPT-4 指挥 Blender，因为大家很多人玩过。这是我自己的，我把我家里面的这个平面图设计图我给它，我说你指挥 Blender 帮我渲染成一个视频，它 20 分钟就做完了。这个就是空间智能啊，这也是空间智能。你说那个 World Labs 李飞飞好歹把公司卖了，对，卖得很好，卖得很及时。卖给了 AMD 是吧？对于专门做这个空间的智能，但是我觉得这是一种路线啊。

同时这也是一个信号，Gemini 和 GPT 包括接下来的 Claude，他们都会有类似的这种能力。他们能完全理解空间，完全理解这些东西，而且它能够指挥工具去干出这些事情来，用工具把这个事情给渲染出来。这是另外一种通向空间智能的路径。

好，这里有人正好拿这个 GPT-4 来控制一个 900 多块钱的机器人来做了一个这个事情，直接它控制机器人就能理解，对吧？这是一个例子。通向空间智能有很多路径，World Labs 是一种方式，DeepMind 对吧，3D 世界模拟的是。其实 GPT 已经把 robotic 的这一部分能力给训练到它的模型里面去了，它就有这个东西，但是它是在更高层面上的一种推理智能上实现的。它不是反射式的这种智能，对吧？人类大脑也能思考空间，但是我们的小脑就直接不通过大脑来做空间定位，这是两种能力。但是这个东西呢，我觉得大模型都能实现，他们都能做出来，只是这个架构问题，对吧？

这是一个信号，对空间智能的。那么湾区有这么多公司在做这个，有 50 多家公司在做机器人的，对吧？从上到下整理的，我看到是有人整理那个地图，我自己后来又把它做了一个详细清单。有做机器人，有做模型，有做组件的，有做软件的。大部分的其实做组件的都实际上到了深圳、中国。湾区这边只要做机器人公司的，这些团队他们必须有一个深圳的伙伴，不然他们没法生产，美国没有制造能力是吧？这是一个现代湾区的机器人地图。

那么讲到了对于大脑的结构物理认知，只处理文本的 AI 不一样，物理 AI 必须没有延迟的去感受物理反馈。那么实际上你看得到前面的那个 GPT 实现的，不，它是顶层，它把推理转化成现实世界的高频的物理动作策略，它都完全理解，它已经做到了。然后呢，中间这个层次叫意识推理，我们现在可能我觉得 FSD 算是中间层次的意识推理，光子进动作出嘛，是吧？就 VLA，我只要光线视觉进来，我就动作反馈出去。它可能是在中层和底层来实现的，然后它能够理解物理定律。底层是这样子的一种结构。

但是现在是有不同的公司在做不同的层次，这个我觉得接下来会从顶网吃到下，顶部的公司是最有优势的，因为他们可以用顶部模型的公司用 Agent 来帮助训练下面的东西，对吧？但是你下面的公司，你没有最好的智能模型，你没有这个 coding agent，你还是得去买 OpenAI、Anthropic，对吧？这个是很大的一个区别。但是下面的东西呢快速训练，我觉得他们积累的数据是最有价值的，这是两条路线，数据是最有价值的底层的。

这是大脑的结构。那么对于做机器人来说，刚才说机器人的是大脑，第二个终极挑战就是最难的就是手。最难就是手，那么这里面技术路径是分成三种嘛：就夹子；然后呢有一个就仿生的，就线束驱动的，Optimus 就是线束驱动的，就是 Tesla 机器人就是线束驱动的；然后还有那个直接驱动，就是电机驱动的，都是电机，它很精准，但是它很热，有点笨，没法做到完全人类的自由度。所以现在在这一块呢，最牛逼的是中间这一个线束驱动。应该会在 12 月份的时候 Tesla 会展出它的机器人。因为他们很多供应链都中国做的，但是 Tesla 很聪明的把供应链给分散了，你没法察觉到他是怎么做的，因为他们防止其他公司抄袭嘛，像素级抄袭，所以压到最后才发布。

这个是对于手。机器人最难的，第一个是大脑，第二个就是手。所以当时 Elon Musk 说他要把这两个东西解决好，FSD 做大脑，然后灵巧手就解决手的问题，这两个都是同时做的。

所以说这个阿西莫夫悖论，廉价的躯壳和昂贵的灵魂，这个是阿西莫夫悖论啊。机器人身体是很便宜的，你看宇树把这个价格已经做到了一万多美金了，非常便宜的。还有很多开源组件，你也可以快速的组装出一个和宇树差不多的机器人出来，而且都是开源的，只有几千个组件就可以搞出来这个机器人。所以你可以看到在深圳有巨大的这个机器人公司，我发现在中国应该会有一个巨大的泡沫在这个上面。

然后另外一个呢，大脑的闭环才是护城河，大脑和数据的闭环，这个是非常难的。就前面看到模型这一块，硬件正以前所未有的速度在降本，真正长期护城河是大脑和软硬协同的一个物理闭环。就有了大脑之后还不行，你还得有取得训练数据的训练环境。这个当时 Tesla 做 FSD 都已经证明了，只有它有几百万辆车在路上跑，才能做得出这么好的自动驾驶出来，没有哪个公司做得出来，对，这个是闭环形成的。所以说为什么 Tesla 它要先生产 5000 台机器人在工厂里面用，快速的把数据弄上来。量产才能弄数据，不然你天天做 PPT 是没有用的，对吧？

那么这里面可以发现呢，中美的两边不一样：中国是硬件先行，这是国家战略，然后强大的制造和整合链优势，湾区的公司要生产还得到中国来；然后美国就是大脑先行，因为他们从头部实验室一直到下面，软件追求端到端的软件生态，然后顶尖的 AI 实验室主导研发，然后算法和模型的代差。这里面会是市场不会赢家通吃的，两边都有优势，两个策略完全不一样。所以说我觉得这里面还挺纠结的，机器人的竞争。

好吧，这个是我跟大家分享一下，就是关于机器人现在大模型公司和它是怎么融合的，以及有哪些空间智能的思路可以采纳新的，好吧，包括现在机器

<!-- chunk 7/10 -->

[Speaker 1]: 人的一些问题。然后呢，有一个迷思：我们正在等待一个 ChatGPT 时刻，机器人呢其实是没有的、不存在的。因为这个东西硬件达标，因为它毕竟不是像软件一样的，硬件的进化是非常缓慢的。自主性飞跃和真实世界的部署都是环环相扣的，我们不可能等到像 ChatGPT 在云端部署一个模型，你马上就使用，然后一下子就能到不到一个亿用户了，机器人是不可能这样子。机器人得实验、生产，然后就是就跟……你可以把机器人的这个时刻想象成 FSD 的进化。它从2019年开始，18年、19年，一直到2024年左右才开始有 FSD 12，五六年、七年之后才有这样逐步的线性式的进化。当然它最后全部用这个神经网络来做之后呢，它进化速度就非常快了。所以机器人应该也是这样一个路径，先有数据，现在有足够多的数据。对，这是一个。所以说不存在一个 ChatGPT 时刻，大家不要为……特别是做投资人来说，不要被这个东西给忽悠了。对市场上多来讲，哦，这个公司实现了这个、发了一个什么模型，实现了机器人的 ChatGPT 时刻，我认为是没有的。

OK，好，我们再来看这个 AI 和科学。AI 研究科学意味着什么？然后我今天讲了，我已经讲了一个小时20分钟了，好吧，今天的内容实在是有动作不好意思。OK，大家继续，回头我还得休息一下。

OK，这里是 AI for Science。我拿这两个公司做例子：OpenAI 的路径是 AI 能当科学家，他能够提出假说、设计分子、推进证明；然后呢，Anthropic

[Speaker 0]: 就

[Speaker 1]: 路线有点不一样，AI 当研发操作系统，协调实验、管理流程、支持临床规划。OpenAI 这个东西引起的科学家、特别是数学家的，因为他要主攻数学，相当大的反弹，对吧？大家能看得到现场、市面上的各种报道，他一个晚上提交了700多个那个 GitHub 的论文，没有同行评议，对，大家觉得太搞笑了这个事情。然后 Anthropic 就做得更加柔和一点，它从生物开始，然后从实验室开始，而且提出了这个模型控制硬件设备的协议，就跟 MCP 一样一个协议。然后呢，对于商业上下游来说意义……这是 AI for Science 意义，它提供模型和工具支持研发，持有药物管线这个价值更大。这一块价值会更大，就是这三种：模型工具，然后研发运营——就是现在做的研发运营和模型工具，最终如果说 OpenAI 想的方法，它能够设计出这个分子做证明来，它能够持有这些专利，那么它能够有更好的这个收益嘛，就是它价值更高。对，这个是三种商业模式。

然后第二个呢，就是新的组织形态：领域专家加 AI 智能体加 CRO。CRO 就是可被雇佣的那种实验室组织，就是你可以找一个实验室来帮你做化验、帮你来做什么药物设计。对，这样子的一个一种新型的组织形态：专家加 AI 智能体加 CRO。但是现在 CRO 很大一部分美国想了 CRO 也自动化，因为现在很多 CRO 都中国做的，中国这个非常多、做得很好，然后就是合同研究机构嘛。然后呢，核心竞争力是把 AI 介入到真实的实验闭环。对，这个是现在 AI for Science 的一些主要的路径。

来看一个 Anthropic 做了什么事情。Anthropic 收购了一个一人公司（one-person company），他做这个肌营养不良的药物的这个哥们，他自己设计这个药物，然后完全……为什么 Anthropic 收购他？因为他全完全部都是用在用 Anthropic 来做研究、做实验管理、做所有的事情。就是完美的验证了一个人带上一堆 agent 就可以做实验室了，他可以做研究，订单也是他自己去下给那个 CRO 的，下给 CRO 的，然后他18个月就完成了这样一个药物设计。同时呢，Anthropic 还和六家实验室深度合作中，利用 Claude 在设计抗原、CAR-T，包括制造、文件审核、临床实验规划，就是前面我讲的他做的这个辅助功能，加快药物研发，对，这样子的工作，这就是 Anthropic 的路径。

然后第二个呢，这有一个，我可以看看这个视频：
"I guess we are seeing the end of the romantic era... the age of heroes, which I thought happened in other disciplines centuries ago... the industrial revolution. Somehow, math has held on, and we had our iducy tradic traditions... We all use blackboards from the special Japanese/Korean chalk, and so we have these quirks. We do a lot of one-on-one advising students and things. And I think we are moving to an industrial era where math will become much more large-scale. We work in big teams, more like the other sciences. We really had to adapt to industrialization."

对，这个是陶哲轩最近反弹最大的。对，他说数学的

[Speaker 7]: 数学领域的浪漫时代已经结束

[Speaker 4]: 了。浪漫时

[Speaker 7]: 代就是大家用心发现，大家同行讨论，然后大家来在黑板上推导来证明题，这样的一个时代已经结束了。现在已经让 OpenAI

[Speaker 7]: 现在叫做让数学工程化了，暴力破解。就是同时让模型启动成千上万、几万个这种 agent 去做研究，去读以前所有的论文，然后找到

[Speaker 1]: 以前的这个论文存在的一些合理可能性来做证明，这完全把这个东西给工程化了。并不是说这个可能科学家会有反弹、数学家会反弹，因为现在主攻的数学，还没到物理，现在主攻数学，OpenAI 还在主攻数学，因为他们希望在这个科学上面走出一条不一样道路出来。所以说对于科学家来数学家来说，全面抵制肯定不是出路嘛。陶哲轩做的是“数学2.0”。如果说我们现在同行评议机制或者奖励机制不改，因为现在都是 AI 做出来的，你就把这个第一个发现你要给他获奖了，但其实现在对你都不知道他是怎么推得出来的，你怎么给他颁奖的，对不对？然后在这里抵制不是出路，然后在这个里面其实需要推进科学的重点的就是整个这个评审机制要改变，整个科学评审机制要……因为本身科学人类科学是一个咱们叫做最大价值是一个科学共同体，你做出来一个实验或者一个证明，你得写论文，然后让其他的同行同意你才行，对吧？不然你说我 AI 特别厉害，我做了700多个证明，最终大家看不懂看不懂这个证明怎么出来的，所以说相当于它是没有价值的。当然，这只是现在啊，如果说未来 AI 可以把这个东西解释给人类看，让人类懂，因为它智能确实比我们高嘛。然后在整个这个评议流程里面把 AI 给卷入进去，我觉得还是可以实现的。所以说我们整个科研、数学这个工作，包括物理理论的数学和理论物理的工作，有可能在 AI 的帮助之下工程化了。所以说人类最终提供的是永远未知的那一半，因为科学是一个验证循环嘛。但最终呢，最终呢，这个还是会工程化的，这是我们现在这个时代最大的转变。很快很快我们会有非常非常多的科学突破科学突破在这上面，就是在捡漏也可以检测出一些出来。AI 在这个里面，但是这个导致了这个科学共同体和 AI 的科研之间形成了一个裂缝。目前来看不知道这个人会怎么平衡，这是我们静观这个事情的发展的变化。

好吧，这我们可以看得出来 Anthropic、OpenAI 两种路线在 AI for Science 上面。然后这里我再举几个更加现实的例子，这三家公司三条科研探索。这个是 Warp Science，它也是一个他做了个 CRO 嘛，做 CRO 小型实验室。对，后来这是以前 OpenAI 的这个 CRO 出来做的开……对，我好像我参与了他们家的这个 fund。然后第二个呢是 Periodic Labs，这个很有名的一家公司，这个也是自主实验室和新材料探索的。第三个 Discovery……大家都知道大名鼎鼎的 Jeff Dean 的这个，刚刚一宣布就不止100亿了。对，这按多 agent 做自动化研究的总机器学习。前面两个都做实验室的，最后一个是做自动化研究的。最后一个方向估计和 OpenAI 现在做的方向比较像，然后前面两个都是做 labs。

我们可以看到，这个可以看看 Kevin 怎么来讲这个东西的：
"It seems almost obvious to me that you have large-scale automated factories that are running experiments at a scale beyond anything that we can imagine today. The point really is around intellectual property and geopolitics. There are now multiple documented examples where key intellectual property getting leaked out of these... you are really giving your crown jewels... Suddenly, all of your competitive advantages lose. The labor is much more expensive in the US, and so typical price points of US CROs are kind of four to five-fold higher than the offshore CROs. How do you thread that middle, and how do you put on top of that a lot of thought that goes into doing things that are unexpected? One of the benefits for us is..."

对，这个很简单的，他们就做一个自动化的 CRO，自动化的那个实验室。然后因为为了避免这个疫情期间出现的这种供应链问题。因为美国确实没有本土基本上没有这种实验室，越来越少了，然后小分子的基本上全部包给了中国，对吧？在中国的几家公司。然后呢，所以说现在让制造业回美国，他们就这个逻辑。OK，那么我们可以让这个实验室回到美国来，他们用机器人来做这个东西，最终交付。这个是这是一个 Warp 的这个 Science 的工作。

然后呢，其实现在我们来总结一下这个里面一些公司和一些路径：
通用科学发现的，对，就是来做科学家加自动实验室、科研 agents，对，这是第一个；
然后第二个，机器人实验室，就是最接近 Warp 的，通用就是 AI 闭环的实验室，我们前面讲的芯片生产硬件也闭环；
然后还有一个就是材料和化学发现的，最接近 Periodic Labs 的，就是 AI 加材料加自动化实验的；
然后还有一个是生物和制药的，Isomorphic Labs，那这个是 Demis 做的，是吧？这个是一直是 Google 孵化的公司，在英国的，他们主要是设计药物的，从设计药物一直到药物的研发，实际上它就是新一代的 AI 驱动的药物研发公司；
然后最后一个就是数学的形式化证明的，专门做数学推理的。
这五种目前我看到的总结出来的一些 AI for Science 目前比较火的、结合前面我推荐的三个案例的公司，让大家了解一下。这一块 AI for Science 我也会做更加详细的报告，我后面会跟大家分享。

看一个视频，自动化的集成电路工厂。自动化集成电路的工厂，我发现美国人听着太搞笑了，就是因为他们现在连板卡都做不了，都得去深圳做，对吧？就是我想下个订单去深圳订一个什么东西即时链路。所以现在在美国本土用机器人来做这个东西，可能速度会比去深圳做快三到四倍，加起来贵两倍。深圳人力还是比这边机器人便宜。这是一个叫做半导体工厂，就只生产集成电路的。好吧，我正好放在这放在这个 Science 后面给大家一个视觉上的一个感知，这样的一个 labs 吧，或者叫做一个工厂，自动化工厂。当然现在中国的自动化工厂也很厉害的，具体的到时候可以做一些调研分享给大家。OK，这是 AI for Science。

好，我们再分享，后面还有两个还有两个小节，很快了。

### 《上帝的测试》与超级智能

《上帝的测试》，推荐一本书，对，《造神之后》。它的英文名翻译过来叫做《上帝的测试》，中文名翻译了《造神之后》，紧接着《吾辈如神》开始了。我上一次翻译那本书6月份的时候和湛庐一块宣发的《吾辈如神》，这是另外一本，也是湛庐出的，但是不是同一个作者。这个作者应该我觉得也挺有名的，Robert Wright，他也挺有名的。就是这本书讲到了如果超级智能到来之后我们会怎么样，未来会成为什么样的文明，什么行星之脑啊，地球是不是一个生命体啊，非常多的一些很有想象力的一些想法，然后一些关于人类存在的一些思考。因为 Robert Wright 特别适合写这本书，尤其是我们即将进入 RSI。可能大家真的现在不知道 RSI 对我们的这个……因为我觉得我们作为生物个体，挺难理解什么叫指数增长的。RSI 带来就指数增长智能的，我们现在还是线性的，我们还是线性思维。之后的这个黑箱循环会不会有什么问题，这个书里面也讨论了。你比如说，比如说现在 Anthropic 和 OpenAI 他们都在去找宗教人士，那判断模型里面会不会有意料？如果真的有了之后会怎么办，对吧？这个书里面讨论这些东西会挺有趣的。而且我在 Indie Talk EP43 里面我和正理也详细讨论这本书里面的一部分内容，大家可以回头去听一下，我这边就只推荐这本，我就不做详细的来讲解了。

然后这第一个，那么从现在看，我刚刚正好有人在问我泡沫破裂。泡沫每年都会破次，大家在股市上面每年都会破几次。OK，现在我们来看这个想象空间的是什么，这也是我们在上一期的 Indie Talk EP43 里面讨论过的讨论过的。就首先太空方面讨论过 SpaceX，这样的一个代表太空的这种开拓是一个重要的一个方向，包……

<!-- chunk 8/10 -->

[Speaker 1]: 包括物理 AI 和计算智能，为什么我前面讲 agentic robotic 这数据、算力，包括这个智能的提升，这个是一个很重要的一个方向。这个可能大部分的一级市场里面我们自己也在投资这个东西。然后还有这个通讯的基础设施，光通讯的基础设施，在机房之间的设备、服务器和服务器之间的这种光通信的，整个涉及到这个数据中心大型改造的这样一些设施。然后呢，这硅基递归啊。

然后第二个叫碳基健康，AI science，湿实验主要是 wet lab 的自动化循环和生物制药。这个现在半导体跌得挺厉害的，但是生物很好。对，生物非常好的。对，生物永远都是这个尿性的，就是它如果跌下来更可怕，对，中国如果跌下来会更可怕。嗯，但是我经历过这些很多个周期之后就习惯了。但是现在确实是它带来的这个突破会很快，但这个里面的泡沫也很大。但是呢，嗯，我认为像 Moderna 这种突破是显而易见的、垂手可得的，这是现在正在突破的真实的东西。对我得到了这个癌症、预防癌症的疫苗。

然后最后一个就是叹息快乐、情绪价值和心理锚点。就是怎么说呢，我之前可能在前面连续的，从去年底、前年底开始到去年，我一直在说，嗯，这个 AI 现在大部分的这个都是 to B 的，to C 的应用基本上没有，基本上没有。除了今年就是 8 月份之后看到的 personality 有点起色之外。但是呢，有一个现象呢，中国其实已经实施了，已经实现了，就是在红果的这个短视频网络里面，实现了 token 生产，然后到 AI 短剧制作，然后到人类消费，这样一个完美循环，是吧？我们可以看到后面这样一个视频。

哦，“Micro-dramas, these ultra-short video series often with over-the-top plot lines seem to be what most AI tokens are used for in China. Meanwhile, the recent report shows most Americans are using tokens for coding.” 

[Speaker 6]: 对，这个数据我不知道，这数据没有验证过，好像有人反驳这数据不对。

[Speaker 1]: 这字节出来反驳出的数据不对。但是这个数据比较好玩、有意义，就是中国的 AI token 消耗 55% 都用在了这个视频生成上面，对吧？然后呢，在美国主要是用在生产力和代码上面。对，这两个极大的区别，50% 多，对，极大的区别。

但是跟我之前发过一条 Twitter，我说在抖音上的 token 消耗就生成了短剧，X 市场上最大的 token 消耗就是生成了各种 AI 科普视频。它一个为了快乐，一个为了学习，反正都是 AI slop。OK，这代表一个很好的一种，怎么说呢，to C 端的一种服务形态。嗯，这种娱乐形式短剧可能还只是初级形态啊，还没到互动游戏，还没到互动游戏。但是我觉得短剧可能看多了跟吸毒一样，它很快会洗脑嘛，可能用户也不需要有游戏了，因为玩游戏还挺累的。啊，这是我个人作为一个老游戏玩家的判断啊。对，但是我还是蛮期望有真正的虚拟实境的游戏的、AI 生成的，就是戴上眼镜之后的这种新的娱乐型产品出现。嗯，只是现在还没看到。

但是我觉得在 AI 对于个人的这个状况来说，更多地都是在娱乐和时间消耗上面啊，而不是帮个人节省时间。所有帮节省时间的、帮个人节省时间的 AI 产品呢叫 pro user；如果是 normal user、消费 consumer，那就是帮你打发时间的，嗯，永远都是这样的。特别是在中国，对吧？这个中国已经验证了，我觉得中国的验证的东西挺适合往海外走的，就跟现在中国的这个传统的这个网络小说、短剧出海一样，会非常有竞争力的，中国的公司就不要在国内卷了，对，嗯，不要在国内卷了。

自我分享一个另外的一个数据啊，因为在硅谷很少很少有人讨论这个东西，非常少，非常少。嗯，但是呢这是中国巨大的一个市场。

好了，我们再总结一下，前面这个是当时也是 EP43 里面聊的一个图，我们从 2077 反推到 2027。啊，这个具体的详细内容大家可以听我这一期播客去啊。这个是当时何政迪分享给我的一张图，最中间的就是在能源、算力、实验和机器人，然后它能够带来周围所有的变化。嗯，那些所有的变化，就我们如果说 2077 我们人类能够发展成为太阳系文明，那么我们在这之前我们就要做这种东西，就要做这么多东西：太空运输、生命科学、可信赖的 agent 和经济，agent 经济，agent economy，包括芯片设计、计算 AI 模型，都在这一块。因为最终我觉得芯片和模型会融合的，你想让模型更高效地执行，你必须得有自己的芯片。嗯，包括 NVIDIA 的这个，包括 TPU，他们都会往这个方向进化。嗯，然后呢，或者在执行层面上，在执行层面，但是训练层面可能会不一样啊。机器人和制造，包括实验材料，这是一个完整的图。啊，回头大家可以听我们这期节目。好吧，我就不多讲了，因为今天时间有限。

OK，最后再分享一下鸡汤和思考啊。OK，嗯，看看，先放一个小视频，让我休息一下。

“I think it's also difficult for those of us who have chosen math. We chose it probably because we liked rules and formalism, and uncertainty is uncomfortable. I think the humility aspect is really important, though. This is a really good opportunity for us to remember why we're doing this, like what is human purpose. It's not to be famous, it's not to have a Fields Medal, you know, solving interesting...”

[Speaker 7]: 对，最后这一句话我是想说的。人类，我们做科学研究或者做所有事情的终极的目的是什么？对。

[Speaker 1]: 当然不是为了出名，不是为了获得菲尔兹奖。这是 Lex Fridman 最新的一期播客，最新的一期播客，他采访了三个数学家，这里面有一段。作为一名科学家或者作为一名科研工作者，或者做一名前沿研究者吧，大家都希望解决有趣的问题，这个是科学本身的动力，科研本身呢，我解决有趣的问题，解决未发现、未知的问题，解决这些问题同时能够用这些解决的方法帮助到他人，这个是我们做这些事情的目的。对，AI 是助手，因为他发现不了这个事情的意义，因为他没有体验。

我觉得这个接下来它会影响很多人的思考，从事科研的包括很多工作人员思考我们做的问题是不是一个有趣的问题？如果是一个狗屎工作，或者说是一个无聊的工作，你赶紧就放弃了。你一定要把你的目标层次往上顶，你去发现有趣的问题，并且解决这个问题。我觉得这一轮 AI 大淘汰之后，我们所有的人都会往这个方向去想，人类社会会变得更加丰富和有意义。就是新一代的文艺复兴时代，就下一轮的文艺复兴 2.0 就即将到来了，文艺复兴 2.0。对，我们人类是被逼出来的。好吧，这是第一个看法。

然后第二个呢，我看到这个 Dan Koe 的这个特别有感，有感慨啊。他当时分享，我总结了一下：网红时代开场，经验时代到来。嗯，之前创作者的三个演化阶段，就是网红纯粹追求注意力、让人停留，到个人品牌优化转化、让人购买，personal brand 吧。现在我们都要做什么？现在都要做思想的匠人，artisan，做积累终身作品，改变人的思考和行动。我感觉我现在就能干这个事情，我已经干了快两年了。对，做 artist，这是一个思考者，我觉得这个事情很有意义的。

回到前面的那个科学家讲的这个事情，我们的意义，我们做事情的意义是什么？意义是什么？解决有趣的问题，发现有趣的问题，解决有趣的问题，能够给别人带来帮助啊，这个是意义，对。

那么 AI 时代的护城河是什么呢？我们亲身的经历是护城河，我们的思想积累，然后形成我们独特的视角。没有人可以拥有一个话题，因为所有的话题就问 AI 就好了。“今天发生了什么？这个事情怎么看？”AI 会给你非常详细的答案，但是 AI 给不了你视角，它给你的视角是平均视角。对，作为一个人，你就要独特。

我觉得人的意义是什么？我上上周和万老师录节目的时候，我们特意聊了这个话题了，人的意义是什么？我觉得因为我们每个人个体都独立的，我们都是独立的，我们就是我，所以你才有你的视角，这是非常重要的。对，这个是我们要变得更加独特。整体的这个循环目标是存在一个积累思想、多维表达、分享出去、观察和真实的追问，然后解决问题。对，“内容是市场的调研，产品是经验的延伸”，我觉得这个总结得太好了，对，我就把这一块分享给大家。这是第二个鸡汤啊。

然后第三个，就是上周，在前两个，哦，9 月底的时候，我的朋友来我家，我赶紧就记下来了，对，灵光一闪。有三个连环策略给老人们，我们接下来很多工作就要干这个事情：让公司和自己的工作自动化，变成 human-in-the-loop；把自己网络化，加强人感，前面说的你是你，你也成为你自己，成为你，那用你的东西来形成网络；然后第三个就是拿赚来的钱投资下一代科技公司。啊，刚刚前面还有说泡沫，没关系，泡沫把价格打低多好，对吧？你要认准这些公司，它能够形成垄断就一定投它，对吧？这个市场就是这样子的。我们虽然进不了这个头部前沿公司，但是你可以投它呀，对吧？你可以投资它呀，一样对不对？你可以拿赚来的钱投资他们就好了。对，未来做好的三件事情就行了，我们人就能升级了。嗯，对。

所以说，那我们就是最后一个总结啊。对，公司本质上就是一连串的 loop。我们从 prompt 驱动 agent，再由 agent 构成 loop，编码 loop 构成迭代现有代码库，

[Speaker 0]: 然后，

[Speaker 1]: 重塑 loop 就重塑业务本身。那么最强形态的 loop 是主动给 CEO 发消息：“我们是不是该改商业模式了？”是吧？对，这个是你最强的 loop，它给出你建议来。那么 loop 只能爬到局部最优解。我跟你说，现在的大语言模型它们都只能给出局部最优解，因为它们平均值，它是平均化的。决定下一座山在哪的，永远是人，是你自己。对，人就是，我觉得 AI 可以做出很好的作品出来，但是它不是艺术，艺术就代表艺术家自己这个人。除非是以后我们 AI 的训练都能够让它具身化训练，当它诞生的时候，我就让它在人类的社会中一块成长，以至它形成有意识了，这不就跟当前那个游戏《底特律：变人》一样，它在人类社会中形成了自己的意识，它就是我了，它就是生物，它就有权利了。虽然它是一个硅基的，但是它有权利，因为他有完整的体验，对吧？但是现在没有，现在 AI 也没有体验，所以说不存在。决定下一座山在哪里，永远是我们自己。啊，这是一个最后一个鸡汤。

OK，嗯，再分享一下我们这个社群产品的进展啊。对，忽悠了很久了，我 6 月份就收了会员费，这个不好意思，7、8 月份家里有点事儿比较忙，9 月份才开始做。嗯，然后呢做了一些东西，网站也做了升级。大家可以看到网站，我们快速地做了一个，我 build 了一个 On-Demand 的在线版，然后和一个 review index 的一个 loop 的在线，正在做。对，这个是当时让 agent 帮我来做的设计，嗯，就自动的。对，因为我现在我自己我个人使用，我只在本地就好了，我用 Markdown 文件管理就好了。但是，嗯，如果分享给大家使用，还需要有个界面比较好，有 UI。

[Speaker 0]: 这，

[Speaker 1]: 才能以后所有的会员都能够使用到的所有的这些工具在线的。好吧，OK，这是进展。然后呢，有个小宣传片给大家看一下。对，我会把现在我的个人的这个知识库的同步、个人的新闻，包括市场动态，包括我现在追踪的股票，就是 real index 的股票，我都会发布到这个 AI board 里面去，大家都能看得见，得到，嗯，在这个里面。

OK，这是做个预告啊。然后呢，我即将在推出我们的研报。我刚刚讲的这一个，一个是 AI science，另外一个是还有一个 AI 体和 internet，我会做更详细的分析。因为今天相对给大家做了个预告吧，这个太多东西讲了，可以分享了。因为在这两个方向我觉得也是我重点接下来投资的，除了我们基础的这个 mega 几多少多少之外，我觉得这两个是我们重点的投资的一级市场、二级市场重点的投资和分析的方向。所以说我会来做这样的两个研报给大家，在今年年底或者明年春节之前吧，啊，对，这样子的一个预告。

然后呢，再给大家推荐一个工具，这也是我们团队的小朋友跟我们一块儿来完成的，呃，一个 Markdown 编辑器。我现在本地就是在用这个，这个所有的音乐都是 Claude 自己写的，自己写的，他没有用那个音乐生成的工具，用代码写的。OK，好吧，这就是我本地的资产类工具。OK，一个 agent for agent 的一个 Markdown 编辑器。

[Speaker 8]: 好，我们今天就基本上快结束了，我最后再放一个视频，

[Speaker 1]: 让我休息一下啊，烘托一下气氛。

[Speaker 8]: 加拿大 BC 省，这是加拿

[Speaker 1]: 大卑诗省的一个艺术家做的。我觉得埃隆·马斯克好像每隔一段时间在转发一个这个视频。

“...build future, but above the skies is where we became limitless. Lunar was the first site for large-scale space...”

这前面

[Speaker 9]: 我们讲到的这

[Speaker 1]: 个太阳系文明，是吧？就是这样子具象化的。

“...was from here. On the red soil, we built our first interplanetary city, New Olympus. Slowly, the essence of Earth took root. Mars was

[Speaker 9]: now our second home. In the Asteroid Belt, we

[Speaker 1]: tapped into nearly infinite material. We rose above the acid clouds of Venus, proving the harshest worlds could be reimagined. Callisto linked the moons of Jupiter, and with time, I emerged as...”

<!-- chunk 9/10 -->

[Speaker 9]: A thinking city, our path was no longer found, it was……怎么中断了？Together, no else, when will go, what will become, the rest lies beyond.

[Speaker 3]: 好吧，我们今天的这个……

[Speaker 9]: 嗯对，这个 Keynote 部分就结束了。我讲了两个小时，讲的内容太多了。OK，我看还有多少人在线啊，看一下啊。哦，还有一百多人在线。

[Speaker 0]: 嗯，OK，好。

[Speaker 9]: 这个我得我得休息，我水都喝完了。

### 直播互动与社群分享

[Speaker 1]: 嗯好，全程都在呀。呃对对对，刚才我的助理说给了一个二维码，我就是发这个二维码把那个视频给中断了。我得把这个投到屏幕上来一下，嗯对。

我有一个群，进来大家可以我们在里面，在进来之后可以呃，我来投一下。大家可以扫这个码，我这里应该也可以打开，对，大家扫这个码就好了，就能够看到，可以进进到群里面来了。对，这个是科技加速同步群。因为进来之后我所有的资讯都会在这里分享，这群是免费的啊，大家千万不要进收费群。因为这是免费的，我们收费会员只在网站上去 Dashboard 用的，群都是免费的。

对，现在对，但我我觉得我在微信直播里面就不方便去讨论太多股票的事情了。但是呢，现在市场确实是在回调。大家相信啊，不同的时候，市场都有不同的叙事吧。

[Speaker 0]: 现在，

[Speaker 1]: 因为大科技的这个预期可能有的到不了，有的是我觉得最主要的是其实增长的还是不错。最主要就是说 AI 带来这一部分增长，你产生的实际收益会不会影响你——这是对 Google 的问题，就是会不会影响你现有的业务？对，它能够提升效率，但是并没有给你带来真实的收益，对吧？这是一这是一个问题，就帮它帮你提升效率了，但是没有带来收益。

因为 Agent 的这些收益呢，还没有从产品里面体现出来，没有从财报里面体现出来。呃现在我觉得最快增长的收益，现在我觉得为什么呢？我觉得我们现在模型进化这么快，它并没有一个终点。模型每年大家都觉得 token 消耗不动的时候，都会有新模式出来说我要消耗更多 token。所以说这个大家在湾区待过几天你就知道，一卡难求，卡的租赁都涨了百分之两百了、百分之一百七十多了，卡太难求了。现在对于算力的需求非常大。

然后当然是第一梯队，Google 现在已经回到第一梯队了，我觉得他很快就会逼近，他肯定要超过 OpenAI 的，这个没问题的，只是说能够逼近 Anthropic 了。对啊对，我们和这个一卡难求，所以说对卡的需求是非常高。

### AI 泡沫与市场看法

[Speaker 1]: 但是呢，我觉得 AI 的泡沫分两个来看。我觉得 AI 泡沫大部分发生在早期，就是那些 A 轮、B 轮的公司里面，还有 C 轮，如果过了 C 就好一点。然后这些公司，他们可能拿 VC 的钱去买卡、去租卡，他们还在发债，一些垃圾债在上面。然后但是他有需要有算力的嘛，这是一个这是一个比较现实的问题。在这些公司因为估值太高了，这是估值高，估值是它的一个问题。

然后第二个呢，是现有的就是前面头部的公司、上市公司里面，如果用 AI 提效了，那 AI 生成了新产品，你的 AI 能不能够带来新的收入？大家都会还是会怀疑怀疑这个问题。

所以 Google 对金融的话题……嗯没有，OK，我不能讨论金融的话题了，OK，又警告一次了。好的，对对于 Google 来说会有这个会有这个问题。

其他的就是关于现在硬件的，对吧？为什么硬件会跌这么多？我觉得硬件跌这么多，就是之前涨太多，大大家好不好都被大家加杠杆地乱玩，对吧？它必须得暴跌啊，然后找一个机会就要跌回去。但因为一个被过度炒的这种市场不都是这样子吗？看多了就习惯了，对，Meme 化了。

OK，微信又提醒我说不能讨论金融问题。对，我确实是我本来不想讨论的，刚刚大家在问嘛。呃我得申请一个资质才行啊，对，太麻烦了，太多了，什么都要审核。

直接问我就好了，对，我看看大家还有什么问题。

[Speaker 0]: YouTube 这边，

[Speaker 1]: 对，芯片设计正在被接管啊，正在被接管。验证做不了，但是设计是在被接管。我估计现在是百分之二十几、三十几，然后接下来可能百分之五六七十几的都会被……但再多我都就不能说了，对，有很多机密就不方便在直播里面说了。

[Speaker 0]: 我看大家还有什么问题。

[Speaker 1]: 每周看播客，播客的内容好丰富啊。对我看播客的，我把这个东西挪一下，把我挡住了。这样扫码还扫得进去吗？这样扫码可能后面的背景是个白色的，这样是清楚了。大家看不见啊？好，让那个群群弄一下。

看看满了，我一下就满了。我看看啊怎么弄啊，好了，我正在协调一下，马上就……没办法，它只能带两百个人吧好像啊。对，这里我得我得先 merge。好的，到时候会发新二维码吧。这个码建不了了，没关系的。看一下啊，看看大家还有什么问题。

满了没关系，我们回头在回放里面再放一个新的二维码，大家就可以进来了，好吧？到时候我这边我会做的一个，大家记得看回放就好了。好，那我先把这个二维码撤掉。

### 个人 Agent 工作流与系统预告

[Speaker 1]: OK，我今天今天整整讲了两个小时，我都没停啊，中间放了两个视频休息了一下。巴西市场？我对巴西市场没有研究。回放我这个结束之后就会生成。

OK，问我那肯定得 AI 帮我吸收了，对对，AI 帮我总结。你自己看肯定看不了这么多的。然后怎么说呢？我觉得还是得提炼吧，就吸收不用那么多，你得关键是得提炼。因为看到的信息会比较多，但是呢，提炼之后你就会有新的发现，比较重要。然后再从提炼里面去找、总结出来，你就会很多东西可以分享了。完了对，日本市场是最混的。

不过我今天已经直播已经结束了，新进来的朋友大家可以看回放啊。我尽快的我看看，我再跟大家聊个五分钟吧，我就准备休息了。今天讲了两个小时，慢慢两个小时。

[Speaker 0]: 讲太多了，东西有点多。今天讲了，

[Speaker 1]: Agentic Internet，还有 Personal Agent，然后以及 RSI，然后关于这个白领工作被替代的问题。刚才我没讲太多数据啊，我觉得总是分享这个白领被替代不好。这个东西呢都只是预测而已，对这个。

但是，我个人觉得既然所有实验室都是 AGI 在 2027，而且他们认为的 AGI 就是完全可以实现让 AI 来自己训练自己提升模型，应该是明年年终吧。我认为 Google、OpenAI、Anthropic 三家肯定是，然后呢这个实现之后呢，他们这种 AGI 已经到来了。对，因为不需要人再参与在里面去改进模型了。然后这是一个比较重要的一个时间点。

大家在问医疗大模型，我觉得不存在医疗大模型，对不存在的，一个通用模型全部解决了。你用最好的模型去调用工具指挥东西就好了。然后呢我觉得需要其他的模型，可能是一些来生成专用模型，专用模型比如蛋白质啊，比如说像 AlphaFold 这种这种专用模型，你用大模型指挥小模型就好了。或者说是我觉得天天说说自己做什么垂直大模型那是不靠谱的，而且很多模型都可以自己训练嘛，现在工具这么成熟了。

New Cloud 的债务问题？我觉得债务问题得过一段时间吧，得看看现在这个市场上……我觉得非常好，现在市场上这样回调调整、警醒是一个很好很健康的状态。如果它一直往上拉，拉得太高了之后再回调，那就更可怕，对吧？这样子间歇性的调整是很健康的。现在利息太高了，主要是利息太高了。对，“机会坑”说得对，机会坑，但是不要跳太早了，因为下周还有中期选举啊，我不知道后面会怎么样，所以观察一下吧，观察一下就好了，不用着急。

反正我的情我的情报里面我看看，我这里有一个小信号。我会看看我的这个，给大家看一下我的桌面。我在这儿，我放了一个 code 在，从我的因为我自己这不是我用的一个 Down 吗？呃 Down 里面有，我这里有一个 inbox。回头我会把这些东西都给直接就是同步到网站上，大家可以看。因为我在本地我只需要有一个浏览器就够了。

然后我这里会每天的总结跟我的今天的总结是信用评级嘛，主要信用评级和融资，科技股继续抛售，然后是今天的主线，我的 AI 帮我做的。我的本地回头会我会把这个发在网站上去，发在刚才说的那个 Web 上。我这边会 Groq bot 会跟我读信号，我本地都写了很多信号了。对，26 号信号是什么，其实在信号里我能看得到，其实它已经告诉我是一个可以买的信号了。对我不能讲太多金融了，等会儿就被警告了。

在这里它会有生成的一些内容吧和动态，它会帮我自动做的。然后我自己会有一个知识库，我自己有运营的任务，还有循环，回头这就这是我自己的 loop。我会把 loop 的结果发一部分到同步到这个 Review 的网站上去，大家就看到刚才我演示的那个界面。

我可以看一下啊，看看等一下啊，我先把它关一下再来。这里会有一个网站有个预览的，可以看一下。哎不是这里，它就可以看得到，上面有这个可以看得到东西，对，数据，但是这个还没有还没有发出去，大概这样子。

对，微信群满了，这个群满了主要进不来大家。我想办法我再弄一个，我看看有人能跟我说，我来看一下我发过来还有一个群。

[Speaker 0]: 临时群还是临时群？

[Speaker 1]: 嗯，我怎么投上来啊？这样就好了，大家可以扫一下，对，可以进来这里。刚刚弄了个新的群，是不是？对，弄了一个临时群啊。

[Speaker 0]: 就新建的，那个没法突破，因为扫码只能到两百就满了。超过两百之后只能够只能够人工邀请了。对，哇，还有一百多人在线啊，这么长时间。

[Speaker 1]: 好了，我再给大家五分钟时间吧，我们就看看。对，显示需要验证，那就不知道怎么破了，不知道了，我就不知道了。没办法，我有办法的，大家回头可以直接加加人就好了，对。

哇，看来还要做算力的特别好，现在现在算力紧缺。OK，再等几分钟，大家可以扫扫这个群就好了。对，再总结一下。

然后后面因为六月份的时候卖过那个社群的早鸟会员，但是后面两个月有事儿就是一直没有交付东西给大家，所以说我决定 9 月份开始我们做一个系统，做一个新的 Dashboard，我们把所有的资讯都集成上去，刚才给大家看到了这个画面，产品。然后大家可以订阅上来直接访问，回头我也提供 API 嘛，可以让你的 Agent 来读啊。

有 YouTube 专属内容？但是还没有，都是一样的内容，对，都是一样的。YouTube 这边我可能我可能在我自己的这个社群网站上会有一些专属内容。YouTube 主要是在发发我的这个 talk，发 talk 和发我这个直播的一些回放，这上面都有，相当于是做我的历史记录用的。

然后在这里我会把这个网站给开放出来，我尽快我尽快，我会尽快。可能大家等个一个月之内吧，一个月之内我应该 showcase 把搞定的，发布一部分东西上来。大家可以追踪市场和追踪追踪我的阅读就好了，这个就比较有效率。然后还有我们一些报告也在做。

好了，再等三分钟我下线了，正好还是两个半小时，对，录两个半小时时间。其他的我想想还有什么需要预告的，倒没有了。其实我现在一个是我其实很想分享，就是一个是搭建我自己的这个个人系统的 Agent loop、personal agent loop，然后呢就是主要是消化信息的、消化和分享信息的。然后另外一个就是一个关于投资管理的一个 Agent loop，就是 investment 的这两个 loop。回头我会把这两个都开放出来，呃怎么构建

<!-- chunk 10/10 -->

[Speaker 1]: 的，然后我觉得这还挺有用的一些方法论吧。因为每个人构建 loop 的方式不一样，所以说，他说我觉得 loop 的方式挺难标准化的，有点因人而异。而且很多地方你需要有自己的介入进去，你自己参与进去，然后 Agent 才会按照你的方式来改。如果说你拿一个程序一样去用，挺难用的，对，你没法、没有一个专门的程序可以去来做这种 loop 的。

对于个人来说……如果说对于企业标准工作流程来说的 SOP 的工作流是可以的。比如现在我们做视频、生产视频是很简单的，我现在我这小伙伴们都帮我来做切片啊、做什么东西，都是 Agent loop 来做的。Agent 来做，它就自动地来就做完了，挺快的。

所以说，这个东西我觉得是挺值得分享的。但是真实的在分享这些东西的人挺少的。大家能看到的、大家能看到的视频号上那些，或者说是，大部分都是忽悠人的，对，我看了一下，就说卖课啊干什么那些为了分享而分享的人。咱们真的去做了这些东西的呢，其实不是不是很愿意把把这个东西给分享出来，或者是很难分享，就是因为这个东西呢太、太定制化了，太个人了。所以说因为我在分享我这些东西有很多隐私问题，我也不想对外打到屏幕上给大家看，它有点怪怪的，就是这个问题。

但是这个我本来说在我的课程里面会放一些这个课程——我怎么构建知识系统的，这个还欠大家的，对，这个要做的。我先把它给做成一个课程，然后呢我再把它变成一个产品，来变成一个产品。这两个东西是我前面说了嘛，就是要把什么东西产品化嘛，对，要把自己的给产品化掉。

OK，这个就不用再投了，关掉吧。好吧，那我们今天的直播就到这里结束，也请大家欢迎关注我的这个视频号，关注我的 YouTube，可以关注我的 X，然后呢同时也关注 rebel 的社群的发展。我会在我所有的能够触达的渠道上面通知各种进展。如果大家进到群里面，你可以去群里面直接问就好了。好吧，就是大家 happy holiday，大家万圣节快乐！会有回放的，会有回放的，YouTube 和视频号都有回放。好，谢谢大家！