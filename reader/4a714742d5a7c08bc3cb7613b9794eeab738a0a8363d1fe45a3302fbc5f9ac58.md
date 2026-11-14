---
author: Latent Space
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zHG6sAss_kE
speaker: Latent Space
tags:
  - database
  - ai-engineering
  - remote-work
  - open-source
  - sre
title: Supabase Select 大会回顾：构建、运维与扩展及 AI 工程实践
summary: 文章回顾了 Supabase Select 大会，重点介绍了其构建、运维与扩展三大主题，包括无 Docker 启动、直连计算、MultiGres 1.0 等发布，并探讨了 Supabase 在 AI 工程中的应用、远程招聘策略及 AI SRE 的挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Supabase
products_models:
  - Supabase
  - MultiGres
  - OrioleDB
media_books: []
status: evergreen
---
<!-- chunk 1/10 -->

### 节目开场与 Supabase Select 大会回顾

大家好，又是我。希望大家喜欢我们做的这些简短的单集导语。希望能借此机会跟你们聊聊我们做某些单集的原因，以及访谈中有哪些值得关注的要点，让大家从音频访谈中获得更多收获。我们还添加了弹出的画面叠加层，保持视觉上的趣味性，并解释一些如果你是行业新人可能不了解的事情，因为我们在做访谈时没有时间逐一细讲。我最近参加了 Supabase Select，也就是 Supabase 公司的用户大会。会上有很多内容要讲。特别是，我觉得应该说明一下，我和这家公司的关系非常密切。六年前我是他们种子轮的天使投资人，他们是我非常非常早的第一笔天使投资。他们做得超级棒。估值在过去六年里从 0 增长到了 100 亿。是一家完全远程的开源公司，这非常了不起，而且他们几乎正在成为托管 Postgres 的标准。所以我想剖析一下他们成功的动力是什么。

<details><summary>Original English</summary>
Hello, it's me again. I hope uh you're enjoying these little episode intros that we're doing. Hopefully, it gives me a little chance to talk to you guys about why we're doing some of these episodes and what you should look out for in the interviews so you get more audio interviews. We're also adding overlays that you can see pop up to keep it visually interesting to explain things that maybe if you're newer to the industry, you don't know because I don't have time to go over every single thing while we're having interviews. Um, so I was at Superbase Selects recently, which is the Superbase company Conference. Um, and there's a lot of stuff to cover. Uh, in particular, I think I should share that I have a very close relationship with this company. Um, I was an angel investor in a seed round six years ago and they were my very very first angel investment. They've done super well. They went from 0 to 10 billion in in valuation in the last six years. is a fully remote open- source company which is enormous and they're pretty much becoming the standard for hosting Postgress. So I want to break down why what makes them tick.
</details>

我也想看看为什么他们在我的 AEO 排名中表现得这么好，因为这绝不是必然的。有很多公司都在争夺为智能体构建数据库的定义权。他们似乎也是我们在 2023 年举办的第一届 AI Engineer 大会的最早的赞助商，现在他们也将成为 Latent Space 的首位赞助商，因为我们开放了赞助，而且找那些我熟悉、信任并且能向我们的受众很好解释的公司和人来合作再合适不过了。我想讲的主要内容，他们在 YouTube 上有一个非常完整的总结，做得非常好。但他们有构建（build）、运维（operate）和扩展（scale）这三大主题。我觉得这些发布非常符合我对一家公司大会主题演讲的期待。

<details><summary>Original English</summary>
Um I also want to see why they did so well in my AEO ranking uh because it's not it's not a given for sure. Uh and there's a lot of companies that are fighting for uh what it means to build databases for agents. They were also I think our very very first sponsor for AI engineer the very first AI engineer in 2023 and they're now going to be our first sponsor for latent space uh which because we're open for sponsorships and uh you know who else to to do this with with companies that and people that I'm familiar with and trust and can explain very well to uh to our audience. And so the main things I wanted to cover they have they have a whole recap here on their YouTube which is very well executed and all that. Uh but they have this these three themes of build, operate and scale. I think the announcements are very much what I kind of look for in a company conference keynote.
</details>

### 三大发布主题：构建、运维与扩展

“构建”基本上是指他们希望如何为编码智能体的配置改善 Postgres 体验，其中真正让我眼前亮起的两点是：其一非常简单，就是无需 Docker 即可启动 Supabase。为了启动基本进程来与数据库交互，我需要的负担越轻越好。显然以后我可以将其扩展到完整的虚拟机。但第二点是基于直连的计算，即直接在数据库旁边运行计算。我认为将两者部署在一起超级简单。说实话，我觉得这被严重低估了。我觉得这可能被低估了它潜在的价值。你的应用拥有来自 Supabase 库的 MCP 服务器真的很好，但声明式模式也非常重要，对吧？你想要的是声明式模式，而不是先建一个模式然后一路不停迁移的标准 SQL 范式。我们在播客中也谈到了这一点，比如你希望 Git 里的所有东西都作为真实事实来源，以便你的智能体可以抓取它，并从中进行配置、分叉等等。这看起来很简单，但实际上 Postgres 最初并不是为了做这个而设计的，你必须把这些事件追溯改装到一个有着 40 年历史的数据库之上。我把 Supabase 现在的势头看作是在为智能体真正极致地利用 Postgres 进行最后一公里、或者说最前沿的开发。不过其妙处在于，它实际上不仅仅关乎智能体，就好像我们一直都需要这个功能。所以人类也能从中受益，我非常喜欢这一点。我不喜欢只为了让智能体开心而做事。

<details><summary>Original English</summary>
Um so build is basically how they want to improve post the Postgress experience for coding agents to set up and the two that I that really shot out to me is uh what one is is very simple one is which is that starting superb basease without docker that that is like the the less weight I can I need in order to start up basic processes to interact with the uh the database the better. Um and obviously I can scale it up to to full VM in the future. But um the second thing is through based compute where uh you run compute next to the database. I think collocating that is super easy. I think this is honestly super underrated. Um I think is uh maybe underelling what it potentially could be. Um your app having an MCP server from super library is really good and but declarative schemas is so important, right? But like you want declarative schemas rather than the standard SQL paradigm of uh set up a schema and then migrate migrate migrate. uh which is something we cover in the the the podcast like um if you you want everything to be in git as source of truth so that your agent can crawl it um and figure and set up and fork and whatever from there um it seems so simple but really when Postgress was not designed to do this uh it you have to kind of retrofit uh the events on top of uh onto a you know 40-y old database um and really I I kind of see Superbase's momentum now as doing the last mile or like the the really like frontier of Postgress development for agents to really use them super well. The beauty of it though is that it's not actually about agents. It's like we just needed this the whole time. Um so but humans also benefit and I I really like that. I don't like doing things only for agents to be happy.
</details>

第二部分是运维。这主要就是为了提供更多上下文，无论是更多的日志、检查、连接，还是用于 SQL 的 Markdown 文件[笑声]，这超级酷，还有知识和技能。他们每年都会推出一些有趣的流水线工作，比如从 Stripe 到其他类型的集成。随着你在 AI 工程职业生涯中走得越来越远，这种通用的 ETL 问题会越来越成为数据工程技术栈的一部分，但现在 Supabase 推出了他们自己的官方解决方案，你可以两者结合使用，怎样都行，但有时能把所有东西整合在一起是很棒的。最后一部分可能是最复杂、最偏向大规模的，这就是为什么 Supabase 将他们的品牌口号改为“从原型到拍字节（petabyte）”。显然他们正在追求更大的规模，因为他们的客户在不断增长。他们宣布了 MultiGres 的完整 1.0 版本，这是他们与 Vitess 的作者一起针对 Postgres 开发的类似 Vitess 的移植版本，这在数据库领域是件大事。如果你不知道什么是 Vitess，那你就落伍了，你需要知道，你现在就是在基于 Vitess 的网站 YouTube 上观看这个视频。还有 OrioleDB 等等，里面有很多内容。老实说，你能看出我和创始人之间的交情。我想这是他们两人有史以来第一次一起接受采访，我提到了这一点，并试图展现他们的默契，向大家展示讨论和经营一家价值 100 亿美元的数据库公司是什么样的。请大家收听收看。

<details><summary>Original English</summary>
Um so then the second part is operate operating. Um so that is mostly just about giving more context really whether it's more logs more checks more connections uh markdown files for your SQL [laughter] that's super cool uh knowledge and skills they every year they ship uh some interesting pipeline uh work from like you know stripe to to to to other sort of integrations um and I think the sort of general ETL problem as you get further and further in your AI engineering career becomes uh you know more and more part of the data engineering stack but now Suabase has their own first party solution you can use a mix of both like whatever but sometimes it's nice to have everything in one uh the last part is is perhaps the most uh complex and you know at scale thing uh this is why superbase changing their branding to prototype to pabyte um and really they're going after more and more scale obviously because they're grow the customers are growing um and so announcing a full v1 of multigress which is their uh their sort of port I guess of vitess for uh for posgress with the vitest guy which is enormous in the database world. If you don't know what vitest is you're losing out um you you need to know you're you're watching this on YouTube uh on a vitest website. Um Oreo DB and DB like there's a lot to go in there and honestly uh you can see my connection with the the founders. I think this is the first interview ever that the two of them have done and I make reference to that and try to uh you their chemistry and show show you what it's like to discuss and run a $10 billion database company. Enjoy.
</details>

### 正式访谈：回顾与重磅发布

>> 好，这期播客筹备了六年。[笑声] 我们非常高兴邀请到 Coppel 和 Ant 来到录播室。欢迎两位。谢谢，感谢邀请我们。

<details><summary>Original English</summary>
>> Okay, this podcast has been six years in the making. [laughter] We're excited to have uh Coppel and Ant in the studio. Welcome, guys. Thanks. Thanks for having us.
</details>

>> 我们是在 Superbase Select 前夕录制的，这是你们盛大的客户大会，我们会在大会结束后发布这期节目。我只是想庆祝一下你们所走过的历程。自从你们结束 YC 以来我就一直关注着你们，当时你们在新加坡庆祝，我第一次见到你们，心想这家在 Hacker News 上被某个随手发帖的用户悄然发布的火爆数据库公司到底是什么来头。不管怎样，祝贺你们取得的所有成功。你们在 Select 大会上宣布的重磅头条是什么？我们直接切入正题吧。

<details><summary>Original English</summary>
>> Uh we're recording this ahead of Super Select which you know it's your it's your big customer conference and we'll release this after the the conference. But I just want to sort of celebrate the journey that you guys have been on. I've seen you guys since you guys finished YC and you were like in that place in Singapore where you were sort of celebrating things and I you know I met you guys for the first time and I was like what is this like hot database company that like got like soft launched on hacker news by like you know some random user sometime um anyway congrats on all the the the success. What are you announcing the headlines at select? Let's just get right into that.
</details>

>> 好的，没问题。有挺多重磅消息的。我们要涵盖的内容很多。主要的先从 Compute（计算）讲起。我们提供了一款名为 Edge Functions 的产品，Edge Functions 是由 Deno 驱动的，基本上有两秒的限制。我们发现，也是我们长期以来从社区听到的反馈是，他们希望运行更长耗时的任务。他们想做分块（chunking）和向量嵌入（embedding）这类事情。所以明天我们就要宣布，在这期节目播出时已经发布了，Supabase Compute，在上面你可以运行任何程序。它是长时间运行的，无服务器的，与你的数据库运行在同一个私有网络中。因此它是同机房部署的，延迟非常低。你可以直接从 Compute 运行 Postgres 连接，并在里面运行任何东西。它不再仅局限于 Deno。你可以结合 Rust 或 Python 使用它。你可以在里面运行智能体。它基本上就是一个完整的计算实例。我们不妨聊聊其他云服务中用户可能熟悉的对标产品，这个会是……

<details><summary>Original English</summary>
>> Yeah. Yeah, sure. Um so there's quite a few headlines. We've got a lot to cover. The main ones would be starting off with um compute. So we offer a product called Edge Functions and Edge Functions are powered by Dino and they have basically a 2C limit. What we're finding is that well what we've heard from our community for a long time is that they want to run much longer workloads. They want to do things like chunking and embedding. So tomorrow we're announcing and by the time this comes out superbased compute which is you can run anything. It's longunning. It's serverless. It is running the same private network as your database. So it's colllocated has very good latency. So you can run postgress connections directly from compute and you can run anything inside it. So it's no longer constrained to just dino. You can use it with rust or python. You can run agents inside it. It's basically just a full compute instance. let's call it uh the comparable offerings in other clouds that other us might be familiar with. Uh would this be
</details>

>> 类似 Lambda 函数，但属于容器类型的 Lambda 函数。

<details><summary>Original English</summary>
>> yeah something like a lambda function but um the container type lambda function um
</details>

>> 基本上你可以运行一个完整的容器。

<details><summary>Original English</summary>
>> you can run a full container basically
</details>

>> 然后还有其他方面的更新。

<details><summary>Original English</summary>
>> and then there's the other stuff.
</details>

>> 是的。然后我们在数据库领域有三项创新。第一项是我们去年谈到过的 OrioleDB，在过去一年里我们对它进行了严格测试，以确保它坚如磐石，并为 Postgres 生态系统做好了准备。这三项创新基本上是：性能、垂直扩展（scale up）和水平扩展（scale out）。OrioleDB 关乎性能。它是当前 Postgres 存储引擎（即堆表 heap）的无缝替代品，运行速度快约 1.5 到 2 倍，而且你不需要做任何其他更改。它完全兼容。它彻底省去了一些后台任务，比如清理膨胀（vacuum bloat）。所以对你的数据库来说它实际上也非常高效。基本上所有的这项创新

<details><summary>Original English</summary>
>> Yeah. And then we have well three uh innovations on the database space. So the first one which we talked about last year which was Ore DB or DB we've basically put it through the ringer in the past year to make sure that it is rock solid and ready for the Postgress ecosystem. The three innovations are basically uh performance scaling up and scaling out. Uh Postgress touches on uh sorry Oriental DB touches on performance. It is a drop-in replacement for the the current Postgress storage engine which is heap and it runs about 1.5 to two times faster and you don't have to change anything else. It's just completely compatible. It completely removes the need for some of these background tasks like vacuum upload. So it's actually very efficient for your database as well. And basically the innovation that all
</details>

<!-- chunk 2/10 -->

我们今年必须完成的工作，是让它通过 PG regress 与 Postgres Antithesis 的完全兼容性测试。我们让它跑了每晚的 TPCC 基准测试和 Jepsen 测试，以确保它基本上永远不会丢失数据。因此，我们明天将以完整测试版（full beta）发布它，并且我们还采用了 Apache 2 许可证。它附带一项专利，而 Apache 2 许可证涵盖了该专利。所以我们实际上是收购了这项技术，继续进行开发，然后买下了专利，现在免费提供给大家。

<details><summary>Original English</summary>
 the work that we had to do this year was put it through PG regress full compatibility with Postgress antithesis. We put it through TPCC nightly benchmarks and JSON to make sure that it basically can never lose data. So we're releasing it tomorrow in full beta and we also made it Apache 2 licensed. It comes with a patent and the Apache 2 license covers the patent. So we actually acquired the technology, continue to develop it and then we paid for the patent and are now giving it away for free.
</details>

>> 你顺便提到的一件事让我依然无法平静，就是你测试了每一个 operator，并且你说每个 operator 在某些情况下都会丢失数据。

<details><summary>Original English</summary>
>> One thing that you mentioned in passing which I still don't I can't get over is that you tested every operator and you said um every operator drops data in some situation.
</details>

### Multigress 与 Operator 重写

>> 嗯，这是关于第二点，也就是横向扩展（scaling）。

<details><summary>Original English</summary>
>> Well so this is for the second the second one so scaling.
</details>

>> 所以那就是 Multigress。

<details><summary>Original English</summary>
>> So that's that's that's multigress.
</details>

>> 是的。Multigress 是第二个重大发布。基本上，我们审视了 Postgres 生态系统，审视了所有的 operator——对于不熟悉的人来说，当你运行 Postgres 时，你从单节点开始，但几乎对于任何数据库，你都希望运行多节点，你希望有诸如故障转移（failover）之类的功能，你希望它能管理备份，所以通常你会有这个叫做 operator 的东西，它可以为你运行整个集群——所以在 Postgres 生态系统中有不少 operator。我们发现的是，在特定条件下，它们每一个都可能会丢失数据。因此，我们在 Multigress 上决定对 operator 的整个结构进行从头重写。所以 Multigress 本质上，虽然我们最初的目标是成为或为 Postgres 社区带来分片（sharding），但它最终演变成为了这整套操作系统。我们实际上再次让它通过了非常严格的测试，我们进行了一千次连续的故障转移，它没有丢失任何数据；我们基本上以所有可能的方式对其进行了全面压测（clobbering），看看它是否会丢失数据。所以我们现在对其稳定性非常有信心，因此我们明天也会发布它。它是完全开源的。它将在我们的平台上以仅限邀请的方式向客户提供。因此，运行严苛业务负载的人可以来找我们，我们将开始帮助他们进行纵向扩展（scale up）。

<details><summary>Original English</summary>
>> Yes. So multigrass is the second big announcement. Basically we looked at the Postgress ecosystem and we looked at all the operators an operator for those who aren't familiar when you run Postgress you start with a single node but then with almost any database you want to run multiple nodes and you want things like failover you want it to manage backups so usually you have this thing called an operator which can run the entire cluster for you so there's quite a few operators in the Postgress ecosystem and what we had found was that under um certain conditions every single one of them could lose data and so We decided with Multigress to do a groundup rewrite of the entire structure of a of a operator. And so Multigress is essentially while our initial goal is to become or give sharding to the Postgress community, what it's turned out to be is this entire operating system. And we actually ran it uh again through very rigorous testing and we've done a uh 1,000 sequential failovers and it didn't lose any data and we've tested it in basically every way we can clobbering it to see whether it will ever lose data. So we're very confident now in its stability and so we're releasing that one as well tomorrow. It's completely open source. It will be on our platform for customers in uh invite only. So people who are running serious workloads can come to us and we'll start helping them to scale up.
</details>

>> 这是 Multigress 完全能够平行对标 Vitess 的最终完成态，还是说仍有未完成的部分？

<details><summary>Original English</summary>
>> Is this the full completion of multigrass being fully sort of parallel to Vites or is there still something left to go?
</details>

>> 不，实际上这很有意思。Sugu 最初在 MySQL 生态系统中创建了 Vitess，但专门是为了分片。其实当他加入时，他说：我们这次的首要目标——因为在 Vitess 时我们总是在兼容性上被动追赶，当你转向分片时你总是不得不做改动，比如修改某些查询——所以他说：我想先只专注于兼容性。因此我们设计它的方式、这种从头重写，专门就是为了确保当我们发布分片功能时，你实际上不需要为你的数据库更改任何东西，你将继续运行相同的查询，而 Multigress 将能够直接处理它，你的代码无需任何改动。

<details><summary>Original English</summary>
>> No actually yeah it was quite interesting. So, Sugu um originally created uh VES in for the MySQL ecosystem but specifically for sharding and actually when he came along he said well the number one goal that we want to do for this time because we're always catching up on compatibility when we used for test you always had to change things as you move to shard it so change some queries so he said I want to focus only on compatibility first and so the way we've designed it is in such a way this groundup rewrite is specifically so that we know when we release sharding you actually won't have to change anything for your database you'll continue to run the same queries and multira will just be able to handle it zero changes to your code
</details>

>> 我是说这真是不可思议的远见，而且你们居然能在两年内做出来。

<details><summary>Original English</summary>
>> I mean that's incredible vision and the fact that you've been able to do it in two years
</details>

>> 是一年。我们还没有发布分片功能，我已经看过了早期原型以及关于我们将如何实现的架构设计，其中一部分应该在明年初左右完成，具体取决于我们平台上正在发生的一些事情。我们手头有很多事情在推进，但我们非常有信心，我们对目前的进展感到满意。一直相当不错。

<details><summary>Original English</summary>
>> that's one year um so we haven't released sharding yet I've seen the early prototypes and the designs for how we're doing it and it should should some of it should and by probably early next year depending on some of the things that are happening on our platform. We got a lot going on but um but we're very confident we're and we're we're happy with the progress. It's it's been pretty good.
</details>

>> 是的。我认为这是 Postgres 实现全面统治的最后一块拼图。

<details><summary>Original English</summary>
>> Yeah. I mean I think this is the last piece for the total domination of Postgress.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对。对于那些不知道的人，去查查 Vitess 吧，它支撑着 YouTube，还支撑着什么？GitHub，一切。

<details><summary>Original English</summary>
>> Right. That's and for those who don't know you know look up the test uh powers YouTube powers what else? GitHub everything.
</details>

>> 是的。如果有朝一日工作负载要从 MySQL 转移出来，你需要它转向 Postgres，这样 Supabase 才能获胜。

<details><summary>Original English</summary>
>> Yeah. if workloads were ever to shift away from my SQL, you need this to to Postgress and that's then for Superbase to win.
</details>

>> 希望它不仅仅是面向 Supabase 的客户，对吧？就像它是一个完全开源的社区项目。任何在大规模运行 Postgres 的人都应该能够使用 Multigress。

<details><summary>Original English</summary>
>> And hopefully it's not just for Superbase customers, right? Like it's fully open source community thing. Anyone who's who's running Postgress at scale um should be able to use Multigrass.
</details>

>> 是的。我相信每个联盟、每家在某种程度上参与 Postgres 的公司都在为此做出贡献，对吧？因为我们都想要这个。

<details><summary>Original English</summary>
>> Yeah. I'm sure like every coalition, every company that's involved in Postgress in some way is contributing to this thing, right? Cuz we all want this.
</details>

>> 是的。是的。我们有一个完整的设计合作伙伴计划。我们正在与 Booz Allen 合作，我们正在与 Postman 合作，我们正在与 Perplexity 合作。所以，是的，很多客户正在加入进来。很多人都需要它。他们正在大规模运行 Postgres，他们需要工具来帮助他们横向/纵向扩展。

<details><summary>Original English</summary>
>> Yeah. Yeah. We've got a whole design partner program. So um we're working with the likes of Boo Allen, we're working with Postman, we're working with Perplexity. So yeah, lots of customers coming on board. They a lot of people need it. They're running Postgress at scale and they need something to sc help them scale up.
</details>

### 收购 Turso 与 Agentic 数据库横向扩展

>> 对。第三个是——是的，这个是个大动作，向外扩展（scale out）。目前我们每个月在我们的平台上启动大约 500 万个数据库。而展望我们确知未来的发展方向，我们认为我们将必须达到每月启动数十亿个。因此，向外扩展是完全不同的另一头猛兽。所以我们决定必须审视一些新的架构，以及该领域、智能体（agentic）数据库领域的人士。在智能体领域，没有哪家领先的数据库供应商能比 Turso 做得更好。因此实际上就在明天，当宣布这一消息时它就公布了：我们宣布收购了 Turso，以帮助我们为智能体数据库赋能。是的，这太不可思议了。而且他们主要是基于 SQLite 的，但这并不影响，对吧？这更多关乎架构，比如我想我没有合适的词来描述，基本上就像广播（broadcasts），是用来形容向外扩展的词吗，对吧？对他们来说，扩展 SQLite 的思路是采用类似单写多读的模式。

<details><summary>Original English</summary>
>> Yeah. Third third one is uh Yeah. So this one's a big one. Um scale out. At the moment we launch about 5 million databases on our platform every single month. and kind of the future where we know we're going, we think that we're going to have to launch billions per month. And so scaling out is a whole different beast. So we decided that we would have to look at some new architectures and people within the space, the agentic database space. And there's no other leading database provider who does agentic well than Terso. And so actually tomorrow and when this is announced it would have come out where we have announced that we've acquired terso to help us power agentic databases. Yeah, that's an incredible. It's also like they're they're primarily SQLite based, but it doesn't really matter, right? Like it's it's more about the architecture of like I guess I don't have the word to describe how basically like broadcasts is that the word for for scale out right like um there's the idea for them scaling SQLite was that they would have like a single writer and like multiple readers.
</details>

>> 是的。SQLite 本身只是单写模式。它是一种文件格式。所以通常来说它不是——

<details><summary>Original English</summary>
>> Yeah. So so SQLite itself it's only a single writer. It's a file format. Um, so generally it's not
</details>

>> 他们称之为面向——的 MVCC

<details><summary>Original English</summary>
>> they call it MVCC for
</details>

>> 没错。正是如此。所以他们构建了 Turso 架构，基本上为 SQLite 构建了 MVCC，这样你就可以拥有多个写入者，并且——

<details><summary>Original English</summary>
>> Exactly. Exactly. So then they built this Terso architecture which basically builds MVCC for SQLite so that you can have multiple writers and
</details>

>> SQLite 的许可证比较特别。他们不得不对其进行分叉（fork）。

<details><summary>Original English</summary>
>> SQLite is has a weird license. They had to fork it.
</details>

>> 他们不得不分叉它。他们最初从 libSQL 开始，然后他们进一步搞出了这种另外非常酷的架构。实际上现在这个架构几周前就在 S3 上被广泛讨论。因此，数据库领域的一些创新实际上正源于对象存储领域的发展。对象存储增加了一堆新功能，这基本上意味着你可以开始把它当成有点类似数据库那样来使用。因为对象存储本身，我认为它具有 11 个 9 的数据持久性（durability），这虽不等于可靠性（reliability），但不管怎样。

<details><summary>Original English</summary>
>> They had to fork it. They originally started with lib SQL and then they they came along and they did this other really cool architecture and actually now the architecture actually it was very commonly discussed a few weeks ago while on S3. So some of the innovations in the database space are actually coming out of what's happening in object storage. So object storage has added a bunch of new features which basically mean that you can start using it a little bit like a a database and because object storage itself is I think it's 11 9 of data durability which is not reliability but whatever.
</details>

>> 是的，不是可靠性，但它能满足你对——基本上你通常在一个数据库集群中所需要的东西。它有点像底层支撑的集群。所以你可以开始做一些很酷的事情，比如现在确实有不少流行的数据库或数据用例直接构建在对象存储之上。以我们的视角来看，它有一些局限性。就事务而言，它可能适合这些较小的用例；因为当你使用事务型数据库时，你必须进行大量的读取和写入，因此在这种情况下，你可能不想在上面做超大规模的操作。这就是为什么我们有 Multigress。但对于我们所看到的需要达到数十亿个数据库的这些场景，我们所需要的正是一种文件格式。因此这就是 SQLite 非常吸引人的地方。它占据了主导地位。实际上真正激起我们兴趣、并且我联系了 Glauber 的事情是：他发表了一篇博文，介绍他们如何完成重写，这基本上为我们在其文件格式上实现 Postgres 兼容性提供了一条路径。所以我们正在收购他们，而且我们实际上会保留 Turso 这个品牌。Turso 将专注于 SQLite，然后我们将在 Supabase 上引入这种名为 Supabase Spark 的全新更小实例类型，它将与我们所有的库兼容，你可以为任何想法、任何你想要的原型提供一个数据库，当它发展壮大时，你就可以直接升级到完整的 Postgres 数据库，一路扩展到 Multigress。

<details><summary>Original English</summary>
>> Yeah, nonreliability but it it gives you what you need for for um basically what you would typically have for a cluster of databases. It's kind of like your cluster underneath. So you can start doing some cool things like yeah there's quite a few popular databases now or data use cases that are building directly on top of object storage. It's got some limitations um in our world view. It's probably good for these smaller use cases. In terms of transactions because when you got a transactional database you got to do a lot of reads and writes and so in this case you probably don't want to be doing something at massive scale on this. And that's why we have multigress. But for these what we're seeing where we need to get to these billions of databases, what we need them to be is a file format. And so that's where SQLite was super interesting. It's dominating. And actually the thing that really piqued our interest and I reached out to Globber. I said he released a blog post on how they done their rewrite basically makes the we have a pathway to get Postgress compatibility with their file format. So we're acquiring them and we're actually going to keep the Terso brand. So Terso is going to focus on SQLite and then we're going to introduce this new smaller instance type on Superbase called Superbase Spark and it'll be compatible with all our libraries and you can have one database for any idea any prototype that you want and when it takes off then you just upgrade to full Postgress databases all the way up to multigrass.
</details>

>> 我知道你们为此工作很久了。这就是梦想，对吧？

<details><summary>Original English</summary>
>> I know you've been working on this for a while. This is the dream, right?
</details>

>> 是的。是的。无论是横向扩展还是缩容，一直都是我们一直在努力尝试的方向之一

<details><summary>Original English</summary>
>> Yeah. Yeah. has been both scaling up and scaling down has been one of the things that we've been trying
</details>

<!-- chunk 3/10 -->

去弄清楚该怎么做

<details><summary>Original English</summary>
 to

 figure

 out

 how





to

 do
</details>

>> 确实是当其中的一些创新出现时，我们才意识到，噢，好的，我们可以做到这一点。

<details><summary>Original English</summary>
>> and

 is

 really

 when

 some

 of

 these





innovations

 came

 along

 that

 we

 realize





oh

 okay

 we

 can

 do

 this
</details>

>> 你知道，比如说你的量达到了每月 500 万，你看按每月几十亿的增长轨迹来看，其中的秘诀之一其实就是它们是那种比较小的数据库。

<details><summary>Original English</summary>
>> you

 know

 you're

 going

 to

 5

 million

 a





month

 let's

 say

 you

 see

 on

 the





trajectory

 of

 billions

 per

 month

 one

 of





the

 secrets

 is

 they're

 actually

 kind

 of





small

 databases
</details>

>> 对，就像这些东西都很小，它们是 vioded 应用，就像……我不知道你在这方面有没有什么见解，比如关于……

<details><summary>Original English</summary>
>> right

 like

 these

 these

 things

 are

 tiny





they're

 vioded

 apps

 like





I

 I

 don't

 know if

 you

 have

 any

 insights





on

 the

 on

 like

 what
</details>

>> 我的意思是，直到它们获得关注对吧，问题就在于，一旦你登上了 Hacker News 的首页，你就需要知道你可以走得远不止于此。嗯，所以整件事的核心想法就是，我们必须确保拥有一条非常顺畅的途径来在不同后端之间迁移，比如零停机迁移，就像我们……这完全是刚需，因为我们现在看到有很多非技术背景的构建者正在构建完整的公司，对吧？我们有一个客户 Magic School，那个创办人之前是个老师，对吧？他看到了教学中的所有这些低效环节，比如老师把时间花在那些本可以自动化的任务上。所以现在你有了这些在没有技术联合创始人、没有 CTO 的情况下起步的初创公司，而且这不再是个案了。这正变得越来越……

<details><summary>Original English</summary>
>> I

 mean

 until

 they

 get

 traction

 right

 and





that's

 the

 thing

 is

 like

 once

 you

 hit





the

 front

 page

 of

 hacking

 news,

 you

 need





to

 know

 that

 you

 can

 go

 far

 beyond

 that.





Um,

 and

 so

 the

 whole

 idea

 with

 with

 all





of

 this

 was

 we

 need

 to

 make

 sure

 we've





got

 a

 really

 smooth

 pathway

 to

 migrate





between

 the

 backends

 like

 zero

 downtime





migrations

 is

 like

 we

 it's

 just

 like

 a

 a





need

 to

 have

 because

 like

 we

 see

 now





that

 there's

 a

 lot

 of

 nontechnical





builders

 who

 are

 building

 like

 whole





companies,

 right?

 We

 have

 a

 a

 customer





magic

 school

 and

 the

 guy

 was

 like

 a





teacher,

 right?

 And

 he

 saw

 all

 these





like

 inefficiencies

 in

 teaching

 like





teachers

 spending

 time

 that

 on

 on

 tasks





that

 could

 be

 automated.

 And

 so

 now

 you





have

 these

 startups

 that

 start

 without

 a





technical

 co-founder

 without

 a

 CTO

 and





that's

 not

 like

 isolated

 incidents





anymore.

 That's

 like

 becoming

 more
</details>

>> 现在每个人都像是构建者了。嗯，这就是为什么我们看到过去 18 个月以来的增长简直疯了。是的，但这仍然感觉还处于早期，我认为还有一个大得多的市场，几乎就像是偏向消费级的那种构建者，对吧，公司内部的人，想要启动自己初创项目的人，这意味着会出现多得多的数据库，而这……

<details><summary>Original English</summary>
>> everyone

 everyone's

 like

 a

 builder

 now.





Um

 and

 that's

 why

 we

 see

 like

 the

 growth





we've

 seen

 over

 the

 last

 18

 months

 is





crazy.

 Yeah.

 But

 but

 it

 still

 feels

 like





early

 and

 I

 think

 um

 there's

 a

 much





larger

 market

 of

 almost

 like

 consumer-l





like

 builders

 right

 people

 inside





companies

 people

 who

 want

 to

 launch





their

 own

 startups

 which

 is

 going

 to





mean

 a

 lot

 more

 databases

 which
</details>

>> 就像我们说过的［笑］，如果我们给每个人都分配一个独立的 Postgres 集群，那可能你知道，我们可能很快就会耗尽世界上所有的物理计算机，这基本上就是正在发生的事情。

<details><summary>Original English</summary>
>> like

 we

 said

 [laughter]

 like

 if

 we

 give





everyone

 a

 dedicated

 Postgress

 cluster





it's

 probably

 you

 know

 we'll

 probably





run

 out

 of

 physical

 computers

 in

 the

 in





the

 world

 pretty

 fast

 which

 is

 basically





what's

 happening.
</details>

>> ［笑］

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 是的，我的意思是我们在这一整年里都面临着这个问题。我们只是……我们的增长一直都是我们在算力容量方面不得不去应对的事情之一。

<details><summary>Original English</summary>
>> Yeah,

 I

 mean

 like

 we've

 faced

 it





throughout

 this

 year.

 We're

 just

 our





growth

 has

 uh

 has

 been

 uh

 one

 of

 the





things

 that

 we've

 had

 to

 deal

 with

 in





terms

 of

 capacity

 of

 computing.
</details>

### 梗图营销与早期传播

>> 是的。所以，恭喜。另外，我也注意到，我感觉 Glober 也是个梗王。

<details><summary>Original English</summary>
>> Yeah.

 So,

 congrats.

 Also,

 I

 will

 observe





that

 I

 feel

 like

 Glowber

 is

 also

 a

 meme





lord.
</details>

>> 是的。嗯，那就是其中一点，我的意思是，拜托。

<details><summary>Original English</summary>
>> Yeah.

 Well,

 that's

 one

 of

 the

 things

 I





mean

 like

 come

 on.
</details>

>> 是啊，他太神了。所以对于那些不知道的人来说，这些基于橡皮擦梗图背后的人就是这家伙［笑］，你知道，暗地里是个狠角色。

<details><summary>Original English</summary>
>> Yeah,

 he's

 amazing.

 So

 for

 those

 who





don't

 know

 the

 the

 person

 behind

 this





rubber

 based

 memes

 is

 this

 guy





[laughter]

 that

 you

 know

 um

 low

 key





lowkey

 a

 killer
</details>

>> 我想说，Will Glober 也是。

<details><summary>Original English</summary>
>> I

 I

 would

 say

 and

 Will

 Glober

 also.
</details>

>> 是的。是的。是的。绝对是。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Yeah.

 Big

 time.
</details>

>> 不知道你们平时会不会交流交流什么东西比较好笑？

<details><summary>Original English</summary>
>> Any

 I

 don't know

 if

 you

 guys

 exchange





notes

 on

 like

 what's

 funny?
</details>

>> 我们肯定会把 Supabase 的 Twitter 账号权限给他。我也确实需要些帮手。

<details><summary>Original English</summary>
>> We're

 going

 to

 give

 him

 access

 to

 the





superbase

 Twitter

 account

 for

 sure.

 I

 I





could

 do

 with

 some

 help.
</details>

>> 是啊。等等，现在还是你自己在弄吗？

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Wait,

 is

 it

 still

 you?
</details>

>> 我们现在有一个由十几岁青少年组成的小团队来帮我。［笑］工作坊，对吧？

<details><summary>Original English</summary>
>> We've

 got

 a

 small

 team

 of

 uh

 teenagers





now

 who

 help

 me

 out.

 [laughter]





workshops,

 right?
</details>

>> 是的。但这……我们每周办一次工作坊，基本上是每周一次的梗图工作坊，但这个岗位很难招人，因为你必须懂技术，而且基本上得懂开发者觉得什么好笑，才能去做那种类型的营销，对吧？

<details><summary>Original English</summary>
>> Yeah.

 But

 it's

 we

 do

 a

 weekly

 workshop,





a

 meme

 basically

 weekly

 meme

 workshop,





but

 it's

 hard

 to

 hire

 for

 because

 you





need

 to

 understand

 the

 tech

 and





understand

 like

 what

 developers

 find





funny

 basically

 in

 order

 to

 do

 that

 type





of

 marketing,

 right?
</details>

>> 是啊。嗯……

<details><summary>Original English</summary>
>> Yeah.

 Um,
</details>

>> 其实，你暗地里也挺像个梗王的。［叹气并喘息］

<details><summary>Original English</summary>
>> actually,

 you're

 you

 are

 also

 lowkey





like

 meme

 lord.

 [sighs and gasps]
</details>

>> 我没你那么搞笑。你真的非常非常搞笑。哪儿来着……有一张是有只海鸥，然后你好像站在……上面。

<details><summary>Original English</summary>
>> I'm

 not

 as

 funny

 as

 you.

 You're

 really





really

 funny.

 Where's

 there

 was

 one

 with





like

 a

 seagull

 and

 you

 were

 like

 um





standing

 on

 top

 of
</details>

>> 超级乌龟站在 Post 之上，我觉得是一只海鸥……

<details><summary>Original English</summary>
>> super

 turtle

 standing

 on

 top

 of

 post

 I





think

 it

 was

 a

 seagull
</details>

>> 站着的海鸥骑在一只飞翔的海鸥身上，然后就像是……

<details><summary>Original English</summary>
>> standing

 seagull

 riding

 a

 flying

 seagull





and

 it's

 like
</details>

>> 我的天呐超级……我现在找不到了，但这全都是 Supabase 深层的历史了，但你知道曾经有一段时间，这些东西就是做得太绝了，人们想模仿你却模仿不来，这成了你的护城河，比如［笑］梗图。

<details><summary>Original English</summary>
>> oh

 my

 god

 super

 I

 can't

 I

 can't

 find

 it





right

 now

 but

 and

 this

 is

 all

 like

 deep





superb

 history

 but

 like

 you

 know

 there





there

 was

 a

 time

 when

 like

 those

 things





were

 just

 like

 it

 was

 so

 good

 people





wanted

 to

 be

 like

 you

 and

 they

 couldn't





and

 it

 was

 your

 moat

 like

 [laughter]





memes.
</details>

>> 是的。而且当时有一些大公司试图通过他们的 Twitter 账号来发梗图。我就不点名了，但都是非常庞大的机构。嗯，不过是的，这很难。就像我说的，招人很难。

<details><summary>Original English</summary>
>> Yeah.

 And

 there

 was

 some

 big

 companies





trying

 to

 run

 memes

 off

 their

 Twitter





accounts.

 I

 won't

 name

 any

 names,

 but





like

 very

 large

 organizations.

 Um,

 but





yeah,

 it's

 it's

 hard.

 Like

 I

 said,

 it's





hard

 to

 hire.
</details>

>> 有个人写了一篇大概四万字的长文来拆解我们的梗图策略。

<details><summary>Original English</summary>
>> The

 guy

 who

 did

 like

 a

 40,000word

 essay





on

 breaking

 down

 our

 meme

 strategy.
</details>

>> 其实很早的时候就有人研究了我们的 Twitter 策略，并把它发到了 Hacker News 上。

<details><summary>Original English</summary>
>> Someone

 studied

 our

 Twitter

 strategy





actually

 really

 early

 on

 and

 posted

 it





on

 on

 Hacken

 News.
</details>

>> 是的。发在 Hacker News 上。呃，那挺有意思的，因为他们记录这种策略的方式是我们自己当时都还没落到纸面上的。所以后来当我们给新营销人员做入职培训时，我们就说，看，这是别人写的策略。［笑］

<details><summary>Original English</summary>
>> Yeah.

 On

 Hacking

 News.

 Uh

 and

 and

 that





was

 funny

 because

 they'

 recorded

 the





strategy

 in

 a

 way

 that

 we

 hadn't





committed

 to

 paper

 yet.

 So

 then

 when

 we





on

 boarded

 new

 marketing

 people,

 we

 were





like

 here's

 the

 strategy

 that

 was





written

 by

 someone

 else.

 [laughter]
</details>

>> 是啊。当然，Hacker News 上的人讨厌它，然后他们就在下面评论，抓住了第一个人。这家伙……

<details><summary>Original English</summary>
>> Yeah.

 And

 of

 course

 hacking

 news

 hated





it

 and

 then

 they

 were

 commenting

 on

 it





and

 took

 the

 the

 first

 guy.

 This

 guy
</details>

>> 是的。是的。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.
</details>

>> 《从 Supabase 动态四个月中所学到的东西》。他就只是研究了你们的工作。

<details><summary>Original English</summary>
>> Learnings

 from

 four

 months

 of

 superb





feed.

 He

 just

 looked

 at

 your

 work.
</details>

>> 这是多久以前的事了？2022 年。好吧。

<details><summary>Original English</summary>
>> How long

 was

 this?

 2022.

 Okay.
</details>

>> 是的。是的。等等，我……我提到了。噢，好的，你在那儿。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Wait,

 I

 I

 I

 mentioned

 it.





Oh,

 okay.

 There

 you

 are.
</details>

>> 所以他就那么拆解了一番。

<details><summary>Original English</summary>
>> So

 he

 just

 broke

 it

 down.
</details>

>> 他做了拆解，然后 Hacker News 上的人就开启了嘲讽模式，于是 Ant 截了一张他们评论的图，发到了我们的 Twitter ［笑］账号上。

<details><summary>Original English</summary>
>> He

 broke

 it

 down

 and

 then

 hacken

 hated





it

 on

 it

 and

 so

 Ant

 took

 a

 photo

 of

 them





 on

 it

 and

 posted

 it

 on

 our





Twitter

 [laughter]

 account.
</details>

>> 你们的仇恨只会让我更强大。

<details><summary>Original English</summary>
>> Your

 hate

 just

 fuels

 me.
</details>

>> 这是什么？呃，挺有意思的文章。是的。好吧。所以我评论了。［笑］

<details><summary>Original English</summary>
>> What

 is

 this?

 Uh

 interesting

 article.





Yeah.

 Okay.

 So

 I

 commented.

 [laughter]
</details>

>> 是啊。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我们的很多增长都要归功于 Hacker News。我的意思是，在早期我基本上就不得不泡在他们那儿。

<details><summary>Original English</summary>
>> That

 was

 like

 a

 lot

 of

 our

 growth

 is





thanks

 to

 Hacken

 News.

 I

 mean

 in

 the





early

 days

 I

 just

 had

 to

 live

 on

 their





end.
</details>

### 与 Hacker News 的渊源及发布策略

>> 所以我们应该聊聊这个。你到底跟 Dang 做了什么魔鬼交易，呃，才能够……

<details><summary>Original English</summary>
>> So

 we

 should

 talk

 about

 that.

 What

 deal





with

 the

 devil

 do

 you

 have

 to

 do

 with





Dang

 uh

 to
</details>

>> 我们被被骂过［笑］，被 Dang 骂过很多次，基本上就是因为一周内发布了太多东西……

<details><summary>Original English</summary>
>> we

 we've

 been

 scolded

 [laughter]





by

 Dani

 like

 many

 times

 like

 for

 for





launching

 too

 many

 things

 in

 a

 week





basically
</details>

>> 而且对于 Hacker News 和 YC 之间的关联，他有合情合理的偏执戒心。所以他有点像是，如果出了什么事，他会有点想把我们推出去背锅，好让大家知道，噢，我们不是为了 YC 的客户在搞特殊，我们是一个独立的网站。所以他一直在帮忙确保我们不会抹黑 YC News 的名声。

<details><summary>Original English</summary>
>> and

 he's

 like

 rightfully

 paranoid

 about





the

 association

 of

 hacken

 news

 and

 YC.





So

 he

 kind

 of

 like

 if

 something

 happens,





he

 kind

 of

 wants

 to

 throw

 us

 under

 the





bus

 so

 that

 he

 people

 know,

 oh,

 we're





not

 doing

 this

 for

 YC

 customers.

 We're





an

 independent

 site.

 So

 he's

 been





helpful

 to

 uh

 make

 sure

 that

 we

 we

 don't





smear

 the

 name

 of

 of

 YC

 News.
</details>

>> 我的意思是，在现阶段你们已经不需要他们了，但毫无疑问，我认为 Dang 的公信力非常高。但我确实认为你们的“发布周”策略很厉害，我记得有一次发布周，好像是第四次还是第五次，每一次单独的发布都登上了 Hacker News 的第一名或者首页。

<details><summary>Original English</summary>
>> I

 mean,

 at

 this

 point,

 you

 don't

 need





them,

 but

 like

 for

 sure,

 I

 think

 Dang





does

 a

 Dang

 has

 super

 high

 credibility.





But

 I

 do

 think

 you

 guys

 strategy

 of





launch

 weeks

 and

 I

 think

 there

 was

 one





of the

 launch

 weeks

 I

 think

 four

 or

 five





where

 every

 single

 launch

 was

 like





number

 one

 or

 page

 one

 on

 hacker

 news.
</details>

>> 我因为那件事被狠狠训了一顿，因为我很自豪地发了推文。我当时就像是说，噢，我们又上榜了。然后我就被训斥了，因为大家觉得这基本上看起来很糟糕，因为［笑］因为突然间这家 YC 孵化的公司就像是霸占了 Hacker News 的首页一样，看起来像是有偏袒。

<details><summary>Original English</summary>
>> I

 got

 told

 off

 so

 badly

 for

 that

 because





I

 tweeted

 that

 proudly.

 I

 was

 like

 oh





here

 we

 are.

 Then

 I

 got

 told

 off

 cuz

 we





were

 like

 it

 basically

 looks

 bad

 because





[laughter]

 because

 like

 suddenly

 this

 YC





company

 is

 like

 dominating

 the

 front





page

 of

 Hack

 News.

 It

 looks

 like

 it's

 a





bias.
</details>

>> 就像在炫耀自己上了首页的事实一样，确实是这样。所以给所有人的建议是，永远不要把你上了 Hacker News 首页的事实截图发到 Twitter 上，因为那确实看起来像……而且坦白讲，那确实就是在炫耀。所以批评得完全在理。是的。

<details><summary>Original English</summary>
>> I'm

 like

 parading

 the

 fact

 that

 you're





on

 the

 front

 which

 is

 true.

 Like

 so

 like





tip

 to

 anyone,

 never

 screenshot

 the

 fact





that

 you're

 on

 the

 front

 page

 of

 hack





news

 and

 put

 it

 on

 Twitter

 because

 it's





it

 does

 look

 like

 and

 and

 to

 be

 honest





it

 it

 was

 gloating.

 So

 so

 it's

 a

 fair





fair

 call

 out.

 Yeah.
</details>

>> 是的。所有那些事情，要我说的话，我现在都觉得那算是过去的陈年旧事了。你知道，距离这些成为当下热点已经过去好几年了。但对于那些不了解 Supabase 历史的人来说，这些都是你必须了解盘点的……就像……

<details><summary>Original English</summary>
>> Yeah.

 There's

 all

 that

 which

 like

 I





would

 say

 I

 was

 cons

 considered

 that





somewhat

 ancient

 history

 now.

 You

 know,





it's

 been

 a

 few

 years

 since

 since

 this





is

 a

 relevant

 thing.

 But

 for

 those

 who





don't

 know

 Superbase

 history,

 these

 are





the

 things

 that

 you

 must

 check

 off

 as





like
</details>

>> 巡礼回顾一番。还有什么？我的意思是……

<details><summary>Original English</summary>
>> the

 tour

 of

 things.

 What

 else?

 I

 mean,
</details>

>> 我觉得那里的第一篇帖子很有意思，因为……

<details><summary>Original English</summary>
>> I

 I

 think

 the

 the

 top

 post

 there

 is





interesting

 because
</details>

>> 这是当初发布的帖子。

<details><summary>Original English</summary>
>> this

 is

 the

 launch

 post.
</details>

>> 是的。但那是别人帮我们发布的，当时我们都还没准备好。我们还没准备好在 Hacker News 上发布。

<details><summary>Original English</summary>
>> Yeah.

 But

 but

 it

 was

 someone

 else

 who





launched

 us

 like

 we

 weren't

 ready.

 We





weren't

 ready

 to

 be

 launched

 on

 hacking.
</details>

>> 而且你们当时也没把自己当作 Firebase 的替代品。

<details><summary>Original English</summary>
>> And

 you

 didn't

 consider

 yourself

 a





Firebase

 alternative.
</details>

>> 噢，对。所以那就是我们更换标语的那一天。我们当时的标语是原本的标语。

<details><summary>Original English</summary>
>> Oh

 yeah.

 So

 that

 was

 the

 day

 that

 we





changed

 the

 tagline.

 We

 had

 the

 tagline





original

 tagline.
</details>

>> 当时是“实时 Postgres”，因为当时的情况是……

<details><summary>Original English</summary>
>> It

 was

 real

 time

 Postgress

 because

 what





had

 happened

 was
</details>

>> 我想要……当时我们觉得，噢，我们来做一家 Postgres 公司吧，但在我之前的公司里，我不得不从 Firebase 迁移到 Postgres，但我需要一个实时功能，所以最后我就在 Postgres 之上构建了这个实时引擎，因此我们当时觉得，噢，这太厉害了，它在开源社区获得了一些关注，这个实时引擎挺酷的。所以我们当时就标榜“实时 Postgres”，但根本没人搭理。当我们上线网站时根本没人在意，于是我们就想，既然这是我当初迁移的原因，那就把它改成“开源 Firebase 替代方案”吧。我想大概仅仅过了 12 个小时左右，这篇文章就冒出来了。

<details><summary>Original English</summary>
>> I

 wanted

 like

 we

 we

 were

 like

 oh

 let's





build

 a

 Postgress

 company

 but

 in

 my





previous

 company

 I

 had

 to

 migrate

 from





Firebase

 to

 Postgress

 but

 I

 needed

 a





real

 time

 feature

 and

 so

 I

 ended

 up





building

 this

 realtime

 engine

 on

 top

 of





Postgress

 and

 so

 we

 thought

 oh

 that's





the

 killer

 thing

 like

 it's

 getting

 some





open

 source

 traction

 this

 real

 time





engine

 is

 kind

 of

 cool.

 So

 we

 were

 like





oh

 real

 time

 Postgress

 no

 one

 cared.

 No





one

 cared

 when

 we

 had

 a

 website

 and

 so





like

 we

 were

 like

 let's

 change

 it

 to





open

 source

 firebased

 alternative





knowing

 that

 that

 was

 the

 reason

 why

 I





switched

 and

 it

 was

 I

 think

 only

 12





hours

 later

 or

 something

 like

 that

 that





this

 article

 went

 up.
</details>

>> 是的。至今仍是历史最高。

<details><summary>Original English</summary>
>> Yeah.

 Still

 the

 top

 of

 all

 time
</details>

>> 当时我们是运行在 DigitalOcean 之上的，每一个新数据库对应两个 Droplet 实例。也就是两个每月 5 美元的 Droplet 实例。方式也……

<details><summary>Original English</summary>
>> and

 at

 the

 time

 we

 was

 running

 on

 top

 of





digital

 ocean

 and

 every

 new

 database

 was





two

 droplets.

 So

 two

 $5

 a

 month





droplets.

 way

 too.
</details>

>> 嗯，一个用于数据库，一个用于 API，

<details><summary>Original English</summary>
>> Um,

 one

 for

 the

 uh

 database

 and

 one

 for





the

 APIs,
</details>

>> 对吧？因为我们……

<details><summary>Original English</summary>
>> right?

 Because

 we
</details>

>> 因为我们想升级 API，而且……

<details><summary>Original English</summary>
>> cuz

 we

 wanted

 to

 upgrade

 the

 APIs

 and
</details>

>> 那时候我们只有极少数的测试用户，然后……

<details><summary>Original English</summary>
>> and

 we

 only

 had

 a

 handful

 of

 like

 test





users

 at

 that

 point

 and

 then
</details>

<!-- chunk 4/10 -->

突然间——
<details><summary>Original English</summary>
all of a sudden
</details>

>> 我想我们当时只有 8 个用户。仅凭那一次发布，我们的用户就从 8 个涨到了 800 个。
<details><summary>Original English</summary>
>> I think we only had eight users. We went from 8 to 800 on that that launch alone.
</details>

>> 是的。然后我们烧光了，我想我们大概有 1 万美元的 DigitalOcean 额度，基本上在 48 小时内就烧光了。嗯，接着我们刚进了 YC，所以 AWS 就表示：“哦，只要你们迁移到我们这里，我们就给你们，你知道的，不管是多少，15 万美元的额度。”于是我们在 YC 的第一周就花在将 800 个数据库迁移到另一个云平台上，你知道的，如果你曾经迁移过一个数据库，就知道这有多痛苦了。迁移 800 个数据库绝不是你希望度过在 YC 第一周的方式。
<details><summary>Original English</summary>
>> Yeah. And then we burned through I think we had like 10k of digital uh ocean credits which we just burned through in basically 48 hours. Um, and then we just got into YC, so AWS was like, "Oh, we'll give you, you know, whatever it was, 150k in credits if you migrate to us." And so we spent the first week of being in YC migrating 800 databases to a different cloud, which, you know, if you've ever migrated one database, you know how painful it is. It's like migrating 800 is not how you want to spend your first week in
</details>

>> 战争。你还记得我们本来可以留在 Digital——基本上我们本来应该继续在 DigitalOcean 上构建的，因为当你进入 YC 时，他们有这个额度项目，当时在 DigitalOcean 上有数额巨大的额度，我们就问：“嘿，我们能拿这些额度吗？因为我们这边快要顶不住了。”他们说：“哦，不行，你们已经用过了 10,000 美元的额度项目，我们不能把这个 300,000 美元的额度给你们。”所以我们就只能，“好吧，那我们必须迁移到 AWS 了。”[笑声] 所以这是 Digital 最大的错失机会——
<details><summary>Original English</summary>
>> war. Do you remember that we could have been on digital like bas basically we should still be building on digital ocean cuz when you get into YC they have this credits program like huge number of credits on digital ocean at the time and we're like hey can we have these credits because we're like we're blowing up here and they said oh no you've already used the $10,000 credit program we can't give you this other one for 300,000 so we're like well we have to migrate to AWS [laughter] and so the biggest lost opportunity of Digital
</details>

我知道我们付给 AWS 的账单。现在，这可能是他们因为过于死板而失去的最大客户之一了——
<details><summary>Original English</summary>
I know our bills with AWS. Now, this is like probably one of their biggest customers ever that they lost from being too strict about
</details>

>> 因为那是疫情时期，当时每个人都在担心接下来会发生什么。所以，我想他们当时觉得不想让自己过度扩张。
<details><summary>Original English</summary>
>> because it was co it was a time when everyone was worried about like what's going to happen. So, I think they were like we don't want to overextend ourselves.
</details>

>> 嗯，
<details><summary>Original English</summary>
>> Um,
</details>

>> 是的，这也说得通。
<details><summary>Original English</summary>
>> yeah, it's fair.
</details>

>> 对。所以，考虑到当时整个世界的情况，这完全合情合理。
<details><summary>Original English</summary>
>> Yeah. So, it was like totally fair at the time just given the um the way the world was looking.
</details>

>> 在疫情期间人们做了很多不理性的决定，但你永远说不准。我本来还想说你们现在的市值可能超过 DigitalOcean 了，但后来 DigitalOcean 不知怎么地也迎来了一轮超级大涨。
<details><summary>Original English</summary>
>> People made many irrational uh decisions during co but you never know. I was still going to say you might be worth more than Digital Ocean now, but then somehow Digital Ocean has also like gone on a super tear.
</details>

>> 看这个。
<details><summary>Original English</summary>
>> Look at this.
</details>

>> 因为算力在过去一年里翻了三倍。
<details><summary>Original English</summary>
>> Because computers tripled in the last year.
</details>

>> 哇，真厉害。那么他们现在是多少？16——
<details><summary>Original English</summary>
>> Wow, that's cool. So, what are they? 16
</details>

>> 现在是 160 亿。
<details><summary>Original English</summary>
>> 16 billion now.
</details>

>> 10 亿。是的。
<details><summary>Original English</summary>
>> Billion. Yeah.
</details>

>> 而且像……好吧。我想现在存在 CPU 短缺。
<details><summary>Original English</summary>
>> And like like uh Okay. Well, I guess there's a shortage of CPUs.
</details>

>> 是的，确实短缺。
<details><summary>Original English</summary>
>> Yeah, there's a shortage.
</details>

>> 你们感受如何？我们真的，我的意思是，我们一直面临着跑道告急的情况，我们多次与 AWS 会面。
<details><summary>Original English</summary>
>> How are you guys experiencing it? We literally I mean we're up against runways all the time where like we meet AWS like multiple times.
</details>

>> 当出现峰值时，有办法应对突发流量吗？或者你们怎么做，就是直接和相关方签订协议？
<details><summary>Original English</summary>
>> Is there a way to spike when you have a spike or what do you do like you you just have agreements with people?
</details>

### 多云与算力

>> 是的，我们必须非常紧密地进行规划。我们付更多的钱。我们与他们合作，事实上明天我们也会宣布引入一个新的投资合伙方，也就是 CapitalG。CapitalG 基本上能获取 Alphabet 生态系统的资源。这对我们双方都有好处。这就好比我们现在必须考虑多云战略。
<details><summary>Original English</summary>
>> Yeah, we've got to like plan very closely. We we pay more. We partner with them and in fact tomorrow as well we're announcing that we're bringing on a new investment partner which is Capital G. Capital G basically has access to the Alphabet ecosystem. Good for us on both sides. It's like we now have to consider a multi cloud strategy.
</details>

>> 我们需要 GCP。
<details><summary>Original English</summary>
>> We need GCP.
</details>

>> 我们需要 GCP。基本上，我们需要更多算力。所以 GCP 是一个非常显而易见的选择，当然我们也希望尽可能与所有 AI 实验室合作，他们有一整套产品。我们在 Gemini 上已经与他们展开合作，并且我们希望确保深度嵌入到他们的所有产品中。还有另一件事，你之前提到数据库生态系统有很大一部分正在被块存储以及所有这些创新技术所重塑。显然 AWS 是这方面的领导者。
<details><summary>Original English</summary>
>> We need GCP. Well, we need more compute basically. So GCP is a very obvious choice and of course we want to partner with all the AI labs as much as possible and so they have a suite of products. We work with them already on Gemini and we want to make sure that we're embedded deeply into all of their products. And that's another thing where you're mentioning how so much of the database ecosystem is being [clears throat] shaped by block storage and all these innovations and all these things. Clearly AWS is is is the leader there.
</details>

>> 如果你打算用 GCS 作为 S3 的替代品，做多云是很难的。
<details><summary>Original English</summary>
>> It's hard to be multiloud if you're going to use GCS as like a swap for S3.
</details>

>> 是的，只要他们具备那些功能。实际上，我不知道他们的对象存储是否具备全部功能，但我确信，无论 S3 做什么，其他厂商都会跟进。所以——
<details><summary>Original English</summary>
>> Yes, as long as they've got the features. Actually, I don't know if their object storage has the all the features, but I'm sure that like whatever S3 do others follow. So
</details>

>> 我还记得大概 3 年前，他们引入了强一致性。
<details><summary>Original English</summary>
>> I I still remember I think like 3 years ago they introduced like strong consistency.
</details>

>> 是的，那基本上就是起作用的创新点。是的。
<details><summary>Original English</summary>
>> Yeah, that's the innovation basically that that helps. Yeah.
</details>

>> 他们就是直接免费提供，并且向所有人推送，就像是“现在上线了”。什么？[笑声]
<details><summary>Original English</summary>
>> And they just like they did it for free and they just rolled it out to everybody and it's like it's live now. What? [laughter]
</details>

>> 是的。是的。接着还有 S3 Express。那也是个重大变革，因为为什么呢？
<details><summary>Original English</summary>
>> Yeah. Yeah. And then S3 Express as well. That was a big game changer because why?
</details>

>> 嗯，基本上现在你想做的是，通常先写入本地磁盘，然后你需要将其批量写入更具持久性的介质。那个批处理过程，写入这些介质的耗时是 1 到 2 毫秒。因此，在你能向客户端保证写入成功之前，基本上需要先批量写入到具有持久性的介质。所以这个是持久的。虽然不像 S3 那样持久，没有 11 个 9，但足够持久，让你可以——
<details><summary>Original English</summary>
>> Well, basically now what you want to do is like you typically write to a local drive and then you need to batch it to something more durable. And that batching process um and so the right times to this are 1 to 2 milliseconds. And so before you can guarantee a right back to your client, you basically need to batch it to something that's durable. So this one's durable. Not as durable as S3, not 11 9s, but durable enough that you can
</details>

>> 它是短暂持久的。
<details><summary>Original English</summary>
>> it's ephemeral durable.
</details>

>> 对，完全正确。然后你在后台将其用作缓存，接着在后台转移到 S3 中。
<details><summary>Original English</summary>
>> Yes, exactly. And then then in the background you take you take you use this kind as your cache and then you move into S3 in the background.
</details>

>> 你们还需要 Redis 吗？
<details><summary>Original English</summary>
>> Do you need radius anymore?
</details>

>> 嗯，需要的。是的，你仍然需要 Redis。这离那个速度还差得远。你的缓存层基本上要么是内存、NVMe 驱动器、本地挂载存储、S3 对应物，然后才是 S3。
<details><summary>Original English</summary>
>> Uh yes. Yeah, you still need radius. Like this is no nowhere near fast enough. You need like basically your cache layers are either memory, MVME drive, um, local attached, S3, they're equivalent, and then S3.
</details>

>> 是的，标准的。
<details><summary>Original English</summary>
>> Yeah, normal.
</details>

### 从原型到 PB 级：Vibe Coding 与 AI 浪潮

>> 太棒了。太棒了。刚才聊了些数据方面的内容，我们跨度相当大。基于新的方式。我们要谈的还有几件事。你们之前的口号是“周末构建，扩展至数百万人”。现在是“从原型到 PB 级”，这非常棒。这确实反映了你们正在实现的规模演进，对吧？
<details><summary>Original English</summary>
>> Amazing. Amazing. That was a little bit of data like we we jumped around quite a lot. Uh, based new way. Uh, a few more things that we're going to talk about. You your slogan was build in the weekend, scale to millions. Now we're prototype to pabyte, which is excellent. And really, it is reflective of the evolution in scale that you guys are doing, right?
</details>

>> 是的。你有什么轶事吗，比如早期的 Supabase 与现在相比？当大家开始做一个项目时，他们的扩展速度有多快？
<details><summary>Original English</summary>
>> Yeah. Do you have anecdotes on like let's say early Superbase versus now? How fast are people scaling when they when they start a thing?
</details>

>> 是的。嗯，最大的事情是，我认为是人们变现的速度。
<details><summary>Original English</summary>
>> Yeah. Well, the big thing is um I think how fast people are monetizing.
</details>

>> 噢，对。
<details><summary>Original English</summary>
>> Oh yeah.
</details>

>> 最初的时候就像是，你选择你的数据库，构建你的产品，然后在某个时间点加上计费。现在因为你可以在 Agent 层加入 Stripe。我们看到有客户刚启动一个项目，在同一周内就能赚到大钱，而且——
<details><summary>Original English</summary>
>> At the start it was like you choose your database, you build your product at some point you um add in billing. now because you can add in stripe like at the agentic layer. It's like we see customers starting a project and within the same week like generating serious cash and and
</details>

>> 在 vibe coding 的早期，我们并不明显觉得这会长久存在。这将会改变软件构建的方式。但当我们一看到有人在产品发布的头几天内就赚了大概 10,000 美元时，我们心想：“哇，这是真的。
<details><summary>Original English</summary>
>> in the early days of vibe coding it wasn't obvious to us that this is something that's going to stick around. This is going to change the way software is built. But as soon as we saw someone earning like I think it was $10,000 within the first few days of launching their product, we were like, "Wow, this is this is real.
</details>

人们正在做出能产生真金白银的真正东西。”嗯，所以我们知道我们必须以某种方式深入投入，过去我们曾成功顺应过一些浪潮，比如当 NFT 非常火热的时候，我们稍微跟进了一下，添加了“使用以太坊登录”和“使用 Solana 登录”。嗯，但我们没有投入大量的开发时间，因为大家都隐约知道这在某个时候会消退。而对于 vibe coding 做出这个决定，就像是，你知道的，我们团队内部讨论了很多关于我们要投入多深？当时我们也知道我们需要稍微向更高客单的市场拓展。就像我们最大的客户当时在逼近我们所能提供的极限。所以我们知道我们必须双管齐下。就是，你知道的，嗯，既要在小型的原型这类事物上创新，也要在规模大得多的领域进行创新。这样你就需要更多的人手。这很有意思，因为基本上对 Supabase 来说，在数量方面经历了 AI 的三个篇章。第一篇章是向量嵌入。我想我们正在——
<details><summary>Original English</summary>
People are making real things that generate real money." Um, so we knew we had to lean in in a way where there was waves we'd ridden successfully in the past, like when NFTts were huge, we leaned in a bit and we added like sign in with Ethereum and sign in with Salana. Um, but we didn't dedicate like tons of dev time because everyone kind of knew it was going to go away at some point. And making that decision for for vibe coding was like, you know, we we discussed it a lot as a team of how much do we lean in? And it was a time when we knew we needed to go slightly more up marker. It's like our biggest customers were like stretching the limits of of what we had at the time. And so we knew we had to then just do both. It was like, you know, um, innovate on the on the small like prototype stuff and innovate on the on the much larger side as well. And then you just need more people for that. So that one's funny because like on the number side basically for superbase there's been three chapters of AI. So the first chapter was um embeddings. I think we're on
</details>

>> Supabase Vector，我现在已经把它记录下来了，它将永远……我们大概应该更新这个，因为……
<details><summary>Original English</summary>
>> superbase vector which I have now transcribed and it will always uh we we should probably update this cuz uh
</details>

>> 是的。是的。你做过的唯一一场演讲是在——
<details><summary>Original English</summary>
>> Yeah. Yeah. The only talk you've ever done at
</details>

>> 是的，[笑声] 我们做了这场演讲。基本上，当时所有这些向量嵌入数据库不断涌现，矢量数据库，很棒的向量数据库。所以我们当时在推广一个事实：你可以将 PostgreSQL 用作矢量数据库。而且 Andrew Kane，一个完全独立的开发者，开发了这个超赞的扩展，我们当时觉得，好吧，尝试去教育市场。Postgres 基本上什么都能做。如果你打算存储向量嵌入，你不需要另一个数据库。所以这是第一篇章，这确实是我们的一大增长引擎，同时也对 Postgres 生态系统有益，让人们了解到这一点。现在向量嵌入领域有很多创新，例如 Turbopuffer 所做的，他们利用了 Turso 正在做的很多创新，我认为对于这类应用来说这是一个极佳的用例。所以那是第一篇章。第二篇章就是 vibe coding 浪潮，像 Lovable、Bolt 这些项目纷纷涌现，那是 2024 年底，当时我们内部进行了大量讨论，嘿，我们真的想进入那个领域吗？我们想为这些产品提供服务吗？我们甚至想拥有自己的 vibe coding 类平台吗？
<details><summary>Original English</summary>
>> Yeah, [laughter] we did this talk. Basically, all these embedding databases were coming out, vector databases, great the vector. And so we were pushing the fact and you can use Postgress as a vector database. And Andrew Kane, a a completely independent guy, has developed this awesome extension and we're like, okay, trying to educate the market. Postgress can kind of do anything. You don't need another database if you're going to store your embeddings. So this was chapter one and it was it was a really a good growth driver for us and also good for the postgres ecosystem just letting people know now there's a lot of innovations in in embeddings what turbuffer for example are doing they use a lot of the innovations that terso are doing and I think it's a phenomenal use case for that type of stuff so that was chapter one chapter two was like the vibe coding wave whereas lovable bold all of these ones coming along that was end of 2024 and that's where we debated a lot hey do we really want to be there do we want to be servicing these. Do we even want to have our own VIP coding type platform
</details>

<!-- chunk 5/10 -->

### 漏斗顶端爆发与转化率逆势上升

在 Supabase 之上？但归根结底，我们的使命是存储全世界的数据。而要做到这一点，我们基于我们的宣传语：在人们刚刚起步时就伴其左右，确保他们永远都不想离开。所以我们看到人们开始起步了。他们当时做的是玩具般的小玩意儿，但这依然符合我们的使命。我们只需要坚信，随着时间的推移，这些工具会变得更好。然后第三点，也就是那些疯狂的数字开始出现的契机，是今年模型基本上变得更好了，接着我们开始看到我们漏斗顶端的新增注册率开始迅速增长。但通常当这种情况发生时，你是在向营销投入大量资金。我们实际上在营销上几乎没花什么钱——

<details><summary>Original English</summary>
on top of Superbase? But in the end, like our mission is store the world's data. And to do that, we based on our tagline. It's like be there when you're getting started. Make sure that they never want to leave. And so we saw people were getting started. They were doing toy things, but still it fit our mission. We just had to believe that over time these tools would become better. And then the third one which is the like crazy numbers started this year the models just got better basically and then we started seeing our top of funnel our signup rate start rapidly increasing but usually when this happens you're pouring a lot of dollars into marketing. We actually barely spend any dollars on marketing
</details>

>> 而且大部分就只是一些梗图之类的内容。所以，嗯——

<details><summary>Original English</summary>
>> and uh most of it's just memes and things like that. So um
</details>

>> 我这里拿到了你的一张图表。这就对了。是啊，我是说你所有的图表看起来都一样，但因为它们都在呈指数级增长，你只要一直、一直换坐标轴就行了。

<details><summary>Original English</summary>
>> here I got one of your charts. There we go. Yeah, I mean all your tries look the same, but because they're just like [laughter] exponentially scaling, you just keep you just keep changing.
</details>

>> 关于这点的另一件疯狂的事情是，通常当你获得更多偏向消费者类的流量以及漏斗顶端流量时，你的激活率和付费转化率会下降，但这两项指标却双双上升了，

<details><summary>Original English</summary>
>> The other crazy thing about this is is often when you get like more consumer-l like traffic and the top of funnel, your activation and conversion to pay goes down, but both of those things went up,
</details>

>> 而且也开始相当迅速地上升。是的。因为……

<details><summary>Original English</summary>
>> started going up quite rapidly as well. Yeah. Because of the
</details>

>> 你怎么知道激活和付费转化情况的？哦，看你们的超级……

<details><summary>Original English</summary>
>> How do you know activation and conversion to pay? Oh, your super
</details>

>> 我们的指标。是的，我们的全盘指标。嗯，原因在于从注册到激活，智能体全替你包办了。是的。

<details><summary>Original English</summary>
>> our metrics. Yeah, our full metrics. Um and and the reason is because the sign up to activation, the agent does it for you. Yeah.
</details>

>> 就像一步搞定。所以它基本上、几乎达到了 100%。

<details><summary>Original English</summary>
>> Like in one step. So it's basically it's almost 100%.
</details>

>> 嗯，于是那些用户转变为付费用户的转化率，比我们传统的开发者用户更高。

<details><summary>Original English</summary>
>> Um and so those users then were converting to paid at a higher rate than our traditional developer user.
</details>

>> 好吧。我是说，太棒了。

<details><summary>Original English</summary>
>> Okay. I mean, excellent.
</details>

>> 很好。[笑声] 不错。

<details><summary>Original English</summary>
>> Great. [laughter] Good.
</details>

>> 但但我敢肯定，但我敢肯定，我敢肯定所有的开发者工具都在经历同样的事情，对吧？

<details><summary>Original English</summary>
>> But but I'm sure but I'm sure I'm sure like like all developer tools are seeing the same thing, right?
</details>

### AI 推荐与早期社区积累

>> 嗯，速率各有不同。我认为你们显然是其中的佼佼者之一。你知道，我刚才正准备拿出其中的一件东西。我有这个 AEO 追踪器，嗯，如果你在里面输入 Supabase，有几个类别中你们都是领先者。呃，但基本上，它导致每一个前沿模型都推荐你们作为集成后端的首选。集成后端是什么意思？它就是你们最初提供的那些产品，比如你们的认证、你们的函数、你们的……你知道，嗯，还有你们的数据库以及所有其他东西，呃，API。而且我觉得很有意思的是，比如你必须在 LLM 爆发前正好在你的时区/时期内进入市场三到四年，然后在当时将自己展现为那个领头羊的最强竞争对手。

<details><summary>Original English</summary>
>> Well, at different rates. I think you guys are clearly one of the the leaders there. You know, I was going to bring out this one of these these things. I have this AEO tracker uh where you know, if you if you type in Superbase and there's a there's a few categories where you're the leader. Uh but basically, it has led to every single frontier model recommending you as your primary choice for an integrated backend. What does integrated back end mean? It it is your original offerings like your your off your uh functions, your you know um and your database and and all the other stuff uh APIs. And I think it is interesting like you had to be in the market for three to four years exactly your time zone before LLM took off and then present yourself as the leading competitor to the leading thing at the time.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后你就能接管过去。

<details><summary>Original English</summary>
>> And then to you can take over.
</details>

>> 是的。是的。是的。[笑声] 我们的时机非常幸运。我是说，我们的时机抓得再好不过了。就像是纯属偶然。不过，我的意思是，如果从第一性原理的基础来看的话。我们也采访过其他可能是在大语言模型出现之后成立的创始人，Resend 算是他们的……我们也跟他们聊过，比如为什么我的 LLM 老是在推荐 Resend？那是因为他们有很多优秀的实践。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. [laughter] We're very lucky with our timing. I mean we couldn't have timed it better. Like it's complete accident. Well, I mean I think like on first princip principles basis. So we have interviewed other founders who maybe started post LLMs and resend was kind of their we've also talked to them like why does my LLM keep recommending resend and it's because they have a lot of good a practices.
</details>

>> 当然。是的。当然我们在这方面投入巨资，但你知道，我们从一开始就处于那个位置，而那是纯属偶然，对吧？现在我们只需要保持那个领先地位，还有社区也是，对吧？比如我们早期的增长策略之一，就是花大量的时间与社区在一起，结果就是他们在撰写博客文章、制作 YouTube 视频、发布各种播客，全都是关于如何在各种情况下使用 Supabase，比如“我是怎么构建这个东西的”。我确信这些内容全都被那些模型给吞食吸收了。

<details><summary>Original English</summary>
>> Sure. Yeah. And of course we invest very heavily in that but you know when we've been at that point since the start and that was an accident right? Now we just need to maintain that lead and community as well, right? Like our one of our growth strategies early was just was spending so much time with the community and it resulted in they were writing blog posts. They were making YouTube videos, they were putting out podcasts all about how to use Superbase in what situations like here's how I built this thing. I'm sure that all just got slurped up by the the models.
</details>

### 社区股权赠予与传奇贡献者

>> 是的。开源也起到了帮助。开源本身自然大有裨益。呃，实际上你在社区方面发布过一个有趣的公告，因为你们融了那么多资金，并且试图以某种更深的方式让你们的社区参与进来。

<details><summary>Original English</summary>
>> Yeah. And open source helps as well. Of course being being open source. Uh you actually had a fun announcement on the community side because you're raising so much and you're trying to involve your community in some in in more deeply.
</details>

>> 是的。所以，去年在 Supabase Select 上，我们宣布打算进行一轮众筹。这是我们一直想做的事情，我们本应该更早去做的，但我们当时手头有太多其他事情要做。然后基本上过去这一年我们都在和律师争辩，律师一直在说，就我们希望参与的人数而言，如果不让他们成为合格投资者，根本没有任何机制可以做到这一点；直到我们问他们一个问题：“那要是他们不投资呢？如果我们直接把股票送给他们呢？”

<details><summary>Original English</summary>
>> Yeah. So so last year at Superbase Select we announced that we were going to do a crowdfunding round. It's something we've always wanted to do and we should have done it much earlier on but we just you know had so many other things going on and basically then we spent the last year fighting with the lawyers who are saying you know for the number of people we want to be involved there is no mechanism to do it without people being accredited investors until we asked them the question well what if they don't invest what if we just give them the stock
</details>

然后他们就说：“行，我们去研究一下。”之后他们回来说：“实际上还真有一种机制，如果你真的只是想把股票赠送出去，是可以做到的。”所以现在我们拨出了大约 100 万美元的 Supabase 股票，基本打算分发给一批社区成员。我们要站上台去隆重宣布的第一位社区成员就是这个人，他在 Supabase Discord 里的名字叫 Gary Austin。

<details><summary>Original English</summary>
and they were like yeah we'll look into it and then they came back and like actually there is a mechanism where if you really just want to give the stock away you can. And so now we've earmarked like a million dollars in Superbase stock that we're basically going to give to a bunch of the community members. The first community member we're we're going to stand up on stage and sort of announce is is this guy. His name's Gary Austin in the Superbase Discord.
</details>

>> 这家伙堪称 Supabase 社区的传奇人物。他……我们查过他的数据，Gary 在过去六年里回答了……呃，在 Supabase Discord 里回答了 20,000 个问题。而最离谱的是，其中有 13,000 个问题是他提问后第一小时内回答的——

<details><summary>Original English</summary>
>> And this guy's like a legend of the Superbase community. He we looked into his stats and Gary has answered uh 20,000 in the last six years, 20,000 questions in the Superbase Discord. And the crazy thing is 13,000 of them he answered within the first hour of them being asked
</details>

>> 而且他不是 Grok 机器人。他是个[笑声]活生生的人。

<details><summary>Original English</summary>
>> and he's not a Grockbot. Like he's a [laughter] real human.
</details>

>> 你见过他吗？他……他是个什么样的人？

<details><summary>Original English</summary>
>> Have you met him? What what is he?
</details>

>> 他是真有其人。我们……我们见过，他基本上算是个退休人员。是的。

<details><summary>Original English</summary>
>> He's real. We we've met he he was basically like retired. Yeah.
</details>

>> 只是对 Supabase 很感兴趣。

<details><summary>Original English</summary>
>> And just interested in Superbass.
</details>

>> Gary Austin。Gary Abbott。

<details><summary>Original English</summary>
>> Gary Austin. Gary Abbott.
</details>

>> 是的，他的真名叫 Gary Abbott。

<details><summary>Original English</summary>
>> Yeah. Gary Abbott is his real name.
</details>

>> 好吧。这家伙 [笑声]

<details><summary>Original English</summary>
>> Okay. This guy [laughter]
</details>

>> 而且……而且他喜欢 Supabase 是因为他自己做了一个类似的应用，因为他喜欢红酒。

<details><summary>Original English</summary>
>> and and he loved Superbass because he basically built his own sim similar um app cuz he loves red wine.
</details>

>> 嗯哼。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 嗯，然后他就乐在其中，你知道，他的圣诞树上挂着 Supabase 的标志。[笑声] 他还经常说：

<details><summary>Original English</summary>
>> Um and then was just getting a kick out of, you know, he's got Superbase logo on his Christmas tree. [laughter] And he's also like,
</details>

>> “顺便说一句，这些是我最喜欢的 Supabase 梗图。”所以这就好比你在提醒我：我快要用光我的 Supabase 额度了。

<details><summary>Original English</summary>
>> by the way, these are my favorite Superbase memes. So, it's just like you reminding me that like I'm about to run out of my Superbase.
</details>

>> 这就是那项公告，我们基本上就是，嗯，任何在 Supabase 生态系统中成为传奇的人，我们现在都能够……

<details><summary>Original English</summary>
>> That's the announcement is we're basically like um anyone who's a legend in the Superbase ecosystem, we can now
</details>

### 社区渠道选择与 GitHub 作为 CMS

>> Discord 现在依然强势吗？我是说，我对 Discord 的感觉很复杂。它……它是最好的聊天工具，你知道，Slack 很烂，但它也是不公开的，对吧？所以在里面做的一切工作都是无法规模化的。

<details><summary>Original English</summary>
>> Is Discord still a strong I mean I I got mixed feelings about Discord. It it is it is the best chat, you know, Slack sucks, but also it is not public, right? So, all the work in there is not scalable.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你有找到解决这个问题的办法吗？

<details><summary>Original English</summary>
>> Have you found anything to solve that?
</details>

>> 早些年我们考察过一些工具。我们决定不用，因为你依然需要去审查哪些内容是你希望公开的，哪些是你不想公开的。但我记得我们最初激烈争论的问题是：好吧，我们想要承载这个社区，我们是用 Discord？做 Slack 社区？还是建 Reddit？我们尝试了几种不同的选择，但我们最终落脚在了这么一点上：Discord 用户就是要用 Discord，Reddit 用户就是要用 Reddit。我们基本上必须全部都做，去到他们所在的地方。是的，这就是答案。那需要做大量的工作。

<details><summary>Original English</summary>
>> There was some tools that we looked at uh in the early days. We we decided not to do it because you still needed to police like what things you wanted to be public and and what things you didn't. But the original debate that I remember we debated a lot was okay, we want to host the community. Do we do a Discord? Do we do a Slack community? Do we do a Reddit? And we tried a few different options, but we landed on this thing of like Discord users are going to use Discord. Reddit users are going to use Reddit. And we basically had to do all of the be where they are. Yeah. That's the answer. It was a lot of work.
</details>

>> 是啊。[笑声] 而且结果证明行之有效，对吧？我的意思是，那是正确的答案。

<details><summary>Original English</summary>
>> Yeah. [laughter] And it worked out, right? I mean, that was the right answer.
</details>

>> 但随后开始冒出很多非常棒的工具，对吧？嗯，或者……

<details><summary>Original English</summary>
>> But then there's a lot of like great tools that started popping up, right? Um or
</details>

>> 我不觉得有哪一个经受住了时间的考验，姑且这么说吧，但是是的，确实有一些工具，有一些把 Discord 镜像到公开问答网站的工具。确实有人在做这件事。

<details><summary>Original English</summary>
>> I don't think anyone has has uh stood the test of time, let's call it, but yeah, there there are there are tools there are discord mirror to public Q&A site. That is a thing that people do.
</details>

>> 我不知道对其他人来说这算不算成功。

<details><summary>Original English</summary>
>> I don't know if it's been successful for anyone.
</details>

>> 还有像 Common Room 这种……嗯。

<details><summary>Original English</summary>
>> And and like common room um
</details>

>> 我们唯一做过的事是针对我们自己。所以基本上只要有人在上述任何一个地方提出了一个正经的问题，我们接着基本上就会把问题和回复抓取到我们自己的网站上。不，实际上我们是把它抓取到了 GitHub Discussions 里，然后再镜像到我们的网站上，这样一来那些被……的内容

<details><summary>Original English</summary>
>> the only thing that we did was for ourselves. So basically anyone who had asked a legitimate question on any one of these, we then would basically scrape the question and the response into our own website. No, actually we scraped it kind of into GitHub discussions and mirrored that onto our website and so the content that was getting
</details>

>> 把 GitHub 当作 CMS 来用。

<details><summary>Original English</summary>
>> used GitHub as a CMS.
</details>

>> 是的，我们把它当作 CMS 来用。完全正确。是的。这是一个极好的策略，因为每个人归根结底都在一遍又一遍地问同样的问题。所以我们心想：好吧，那我们每次都把它展示出来。是的，这可能会让人困惑，因为有 Git……有开源的 Supabase，

<details><summary>Original English</summary>
>> Yeah, we used it as a CMS. Exactly. Yeah. It was a great strategy because everyone ultimately everyone was asking the same questions over and over again. So we're just like okay well we'll surface it each time. Yeah, it can be confusing because there's gith there's superbase the open source
</details>

>> 然后又有作为云平台的 Supabase，

<details><summary>Original English</summary>
>> and then there's super superbase the cloud platform
</details>

>> 而且有些人……大多数人可能都是冲着 Supabase 云平台的支持服务而来的。

<details><summary>Original English</summary>
>> and some and most people are probably going to come into support for superb cloud platform.
</details>

>> 所以是的，这……你对自己……呃，这个很难讲，你们开源市场的份额有概念吗？所以，呃，这是一件如果你处于开发者工具圈子里，你……你

<details><summary>Original English</summary>
>> So yeah it it is do you have any idea of your uh this is very hard to tell your open- source market capture. So uh this is a thing that like if you're in the developer tools circles you you
</details>

<!-- chunk 6/10 -->

know you do

<details>
<summary>Original English</summary>
know you do
</details>

>> 我们确实是故意不……不知道的。所以我们开源产品里不放任何追踪代码。你可以直接用，而且已经有企业——比如大型制药公司——跑来跟我们说：“嘿，我们内部跑了 100 个你们开源项目的实例。你们能为我们提供一款产品吗？”所以我们做了一款叫 Control Tower 的产品，让企业能够监控一整套数据库集群。你在我们官网上是找不到它的，不过……

<details>
<summary>Original English</summary>
>> we like quite deliberately do not don't know. So we don't put any tracking in our open source offering. You can use it and we've had enterprises, large pharmaceutical companies for example, come to us and say, "Hey, we're running 100 instances of your open- source project. Can you offer us a product?" So we've got this product called Control Tower, which allows enterprises to have monitor a fleet of databases. You won't find it on on our website, but
</details>

>> 哎呀，得了吧。是啊，是啊。

<details>
<summary>Original English</summary>
>> Oh, come on. Yeah. Yeah.
</details>

>> 为什么找不到？

<details>
<summary>Original English</summary>
>> Why not?
</details>

>> 因为明天才发布。［笑声］

<details>
<summary>Original English</summary>
>> Cuz it launches because tomorrow [laughter]
</details>

>> 我不知道明天发不发公告，但总的来说基本上它就是个控制台视图。它所做的就只是提供这种集群视图。我们有一款非常受欢迎的产品叫 Supabase for Platforms，那些 AI 公司全都是基于它构建的，我们为他们启动了数以百万计的数据库。所以我们只需要把它重新包装一下卖给企业就行了，而企业也想做同样的事情：他们想为内部所有用户启动多个内部 Supabase，他们想看到并对它们进行管理。所以 Control Tower 本质上就是把我们已经为那些平台提供商开发的东西重新打包，只不过专门针对单个企业。

<details>
<summary>Original English</summary>
>> I don't know if we're announcing it tomorrow but yeah basically it's control D it all it does is it's this fleet view we've got this very popular product superbase for platforms so that's what all these AI companies are building on top of we launch millions of databases for them and so all we needed to do was repackage this for enterprises and enterprises as well want to do the same thing which is they want to spin up many internal superbase for all of their users they want to see and administer them. And so control tower is essentially a repackaging of what we've already been developing for these platform providers except specifically for for individual enterprises.
</details>

>> 确实，我确实想聊聊这个，因为我觉得很多人都认为你们是自底向上的市场拓展模式，呃，了解一下你们在企业端所做的工作。呃，所以首先，向……致敬。

<details>
<summary>Original English</summary>
>> Yeah, I do want to cover because I think a lot of people think of you as bottoms up GTM uh you know what the work you've been doing on on the enterprise side. Uh so first of all, shout out to
</details>

>> 我觉得这是你们近期最成功的发布，那就是……

<details>
<summary>Original English</summary>
>> I think this is your most successful recent launch which is
</details>

>> 呃，Supabase for Platforms。这款产品发布于……对。

<details>
<summary>Original English</summary>
>> uh Superbase for platforms. This one launched in Yeah.
</details>

>> 对。对。我是说 2025 年 12 月。噢对，

<details>
<summary>Original English</summary>
>> Yeah. Yeah. I mean December 2025. Oh yeah,
</details>

>> 我看到了一些数据，或者说是你们把它称作是成功的。我不知道。

<details>
<summary>Original English</summary>
>> I saw some stats or like you guys called it successful. I don't know.
</details>

>> 呃，企业端到底是什么情况，就是除了“给我一个仪表板”之外，背后的故事是什么？

<details>
<summary>Original English</summary>
>> Um what is the enterprise side right like what what are what is that story apart from like give me a dashboard.
</details>

### 企业销售策略与产品触发器

>> 嗯，首先我们应该聊聊销售策略。

<details>
<summary>Original English</summary>
>> Well first of all we should talk about sales strategies.
</details>

>> 好。

<details>
<summary>Original English</summary>
>> Okay
</details>

>> Supabase 是一家非常出名的……公司，比如我们对……我们每期 YC 团队里有 60% 都在使用 Supabase。我们把几乎所有的精力都放在了成为一家指数型公司上。基本上，我们在这方面的榜样就是 Stripe。我们希望追随他们的脚步。他们是我们见过的极少数经历十多年向高端市场转移，却依然保持着开发者喜爱的开发者工具之一。这是第一点。所以为了做到这一点，我们开始做销售时，所做的一切就是叠加我们所称的“产品销售”。因此我们改为去寻找产品触发信号。它可能是一个企业品牌标志，一个我们认为非常重要的人；但更重要的是，他们可能正在扩容。他们可能会触及某些限制、出现一些报错、支付特定金额的费用。我们有一大堆这类触发信号。接着 AI 出现了，我们就觉得：“噢，我们可以用这个来做些有意思的事。”举个例子，假设我们每周有一千个产品触发信号。我们会给遇到问题的人发出 1000 封邮件，假设其中有 500 人回复了。我们把不回复的人群作为对照组，

<details>
<summary>Original English</summary>
>> so superbase is a very famously Pong company like we give a about we have 60% of every YC batch use superbase. We focus almost all of our attention on this like becoming an index company. Basically, our role model here is Stripe. We want to follow in their footsteps. They're one of the only developer tools that we've ever seen that has withtood more than a decade of moving our market and still keeping that developer love. So that's the first thing. So to do that, all we started doing when we did sales was layer on what we call product sales. So we look instead for like product triggers. It could be like a a logo, someone who we think is really important, but more importantly, they could be scaling up. They could be hitting some limits, having some errors, paying a certain amount. We've got a bunch of these triggers. And then AI came along and we're like, "Oh, we can do some interesting stuff from this." So, let's say we have a thousand product triggers every single week. We send off a,000 emails to people who are having problems and say 500 of them respond. We take the cohort who don't respond and we use them as a control group,
</details>

>> 好的？

<details>
<summary>Original English</summary>
>> okay?
</details>

>> 然后我们衡量他们的增长幅度。结果显示他们环比增长 25%。接着我们把所有回复的人组织起来，对我们的销售团队说：你们唯一要做的事情，就是跟这些人通个电话，帮他们解决问题。因为我们掌握了他们所有的流量模式，我们可以给销售一份话术。我们知道他们的问题所在。AI 在这方面发挥了很大作用。呃，我们给销售一份纯粹为了帮忙的话术。事实证明，仅仅通过通个电话帮人家解决问题，他们的账户随后就增长了 125%。所以这 100% 的提升，也就是增量提升，就是我们给销售人员发提成奖金的依据。传统上，你会说“跟这些人通电话，直接卖东西给他们”，然后你拿到全部配额的佣金。但因为我们知道在这群用户上，我们的数据库会增长，我们的平台环比会增长 25%，所以我们就知道我们的销售团队带来了这 100% 的额外增量。这就是我们运作销售职能的方式。它始终专注于这些大客户品牌或者非常具体的产品需求。所以，企业级客户找上门来，通常是因为他们想要启动非常多的数据库；而几乎绝不可能是因为要迁移他们的生产数据库。所以，把数据库比如从 MySQL 迁移到 Postgres，或者从一个可扩展数据库迁移到另一个可扩展数据库，这种情况几乎从未发生过。这也是 Supabase 最初的核心假设。我们知道，过去我们看过的每一家试图做数据迁移的 Postgres 公司或数据库公司，随着时间推移都失败了。你根本无法说服人们去迁移。哪怕你构建了一个更大、更好、更具扩展性的 Postgres，你真正必须做的，是在第一天就打入他们内部，然后确保他们能一直留存到第 1,000 天、第 10,000 天。所以我们全部的重心就是在第一天赢得这些企业级客户。

<details>
<summary>Original English</summary>
>> And we measure how much they grow. Turns out they grow 25% month over month. Then we take all those who do respond and we say to our sales team, the only thing you need to do is get on a call with these people and help them. And because we've got all their traffic patterns, we can give them a script. We know what their problem is. AI has been great on this. And uh we give them a script just to help out. And it turns out just getting on a call and helping people out, their account then grows 125%. So that 100% uplift, the incremental uplift is what we compensate our salespeople. Traditionally, you'd say get on a call with these people and just sell them and then you get the full quotota. But because we know our database grows, our platform grows at 25% month over month on this cohort of users, then we know that our sales force are adding this 100% incremental uplift. So that's how we do our sales function. It's always focused on these logos or very specific uh product needs. So yeah, the likes of the enterprise is usually coming in because they're wanting to launch lots and lots of databases or almost never it'll be a transfer of their production database. So migrating databases from say my SQL to Postgress or from say one scalable database to another scalable database almost never happens. And that was the core thesis of Superbase at the start. We knew that every single Postgress company we had looked at or database company we had looked at in the past that had tried to do migrations had failed over time. You just can't convince people to migrate. Even if you build a bigger, better, more scalable Postgress, what you have to do is land with them on day one and then make sure that they stick around to day 1,000, day 10,000. So all of our focus is winning these enterprise logos on on day one.
</details>

>> 全新绿地项目。

<details>
<summary>Original English</summary>
>> Green field.
</details>

>> 全新绿地项目。是的，

<details>
<summary>Original English</summary>
>> Green field. Yeah,
</details>

>> 他们还是不会迁移。

<details>
<summary>Original English</summary>
>> they're still not migrating.
</details>

### 绿地场景与企业内创新

>> 我保证他们几乎绝不会迁移。有一批客户确实需要 Multigress。我们接触过一些大客户，他们正在考虑以开源方式使用它。他们非常希望能够基本上协助我们指明方向，因为他们在大规模使用 Postgres 时遇到了问题。但在接下来的大概 5 年里，我们在企业端的几乎所有重心，都是确保我们能承接全新绿地用例；事实证明，现在这类用例在企业里非常普遍，因为他们希望自己的所有产品人员都尽可能多地进行开发和创新。所以，这对我们来说又算是一个完美的时机，因为这正是我们长期以来一直专注的事情。这个 Control Tower 算是我们最重要的产品之一。当然，如果大型工作负载未来真想要迁移的话，Multigress 确实为我们赢下它们提供了机会，但它绝不会成为我们的核心重心，或者至少在接下来的大概 5 年内不会是。我们将必须极其聚焦于仅仅是打入这些企业内部，然后向上拓展。另一件发生改变的事情是，显然我们过去把所有的精力都放在了开发者身上。以前的模式是：向开发者销售，让他们成为推广者，他们再帮你在内部推销。呃，有趣的是，现在我们遇到了一些首席产品官，他们会说：“哇，过去 10 年我都没写过代码了，但现在靠着 Lovable 和 Supabase，我在内部把这些东西全搭建起来了。”我们现在即便没有针对那一层大费周章做推广，也能在高管层拥有这样的拥护者。

<details>
<summary>Original English</summary>
>> I guarantee they'll almost never migrate. There's a cohort that will need multigress. We talked to some logos who are looking at using it open source. they're very interested on making sure that um they can basically help us direct because they're running into problems of Postgress at scale. But for the next say 5 years almost all of our focus on the enterprise side is making sure that we can handle green field use cases which now in the enterprise it turns out to be a very prolific use case because they want all of their product people to be developing innovating as much as they can. So again, it's kind of perfect timing for us because that's what we've been focused on for so long. This control tower is like one of our biggest things. Multigress of course gives us the the opportunity to win these large workloads if and when they want to ever migrate, but it won't ever be one of our core focuses or at least not for the next say 5 years. We're going to have to focus really heavily on just landing inside these enterprises and then expanding up. The other thing that's changed is we obviously put in the past all of our focus into developers. So it was like selling to the developers enable them as a champion. They help you sell internally. H interestingly now we have like CPOS who are like wow I didn't code for the last 10 years but now because of lovable and superbase I'm building all these things internally that we now have like champions at the at the sea level without needing to put like a huge motion around there.
</details>

>> 噢，那太棒了。对，提到 Lovable，提到 Bolt，你知道 Lovable 也会搞他们自己的数据库功能，而且从大局来看，基本上每个人都会试图侵入对方的地盘，呃，这在宏观格局中很正常。哪一个粘性更强？

<details>
<summary>Original English</summary>
>> Oh that's great. Yeah. mentioning Lovable, mentioning Bolt, Lovable is going to have their own database stuff, you know, and and like everyone is going to basically try to intrude on on each other's turf, uh, which is normal in in the in the grand scheme of things. Which is more sticky?
</details>

>> 哪一个粘性更强？

<details>
<summary>Original English</summary>
>> Which is more sticky?
</details>

>> 更……更具粘性。比如，首席产品官是更有可能绑定在 Lovable 上，还是绑定在 Supabase 上，你知道的，这类问题会出现吗？

<details>
<summary>Original English</summary>
>> More more sticky. Like, is the CPO more likely to be married to lovable or married to Superbase, you know, like is that a question that comes up?
</details>

>> 问得好……问得非常好。我认为归根结底，运行数据库是非常困难的。

<details>
<summary>Original English</summary>
>> That's a great That's a great question. I think ultimately running databases is very hard.
</details>

>> 说得在理。嗯，而且正如我们刚才讨论的，迁移数据库可比迁移前端工具困难多了。

<details>
<summary>Original English</summary>
>> Fair enough. Well, and and as we just discussed, it's harder to migrate your database than it is your front end tool.
</details>

>> 倒不是说我觉得 Lovable 没有粘性。我觉得它非常棒。事实上，他们是最早把一件事情做得很好的人，那就是确保他们的智能体不会在数据库上做傻事。因为我们很早就发现，智能体曾试图把图像数据硬塞进 Postgres 里。你知道，他们为了让项目能跑通，基本上是通过回形针式的极端手法去关闭行级安全策略（RLS）。Lovable 写出了非常优秀的技能来阻止他们的智能体干蠢事。他们是……他们是第一家。

<details>
<summary>Original English</summary>
>> Not that I don't think Lovable is sticky. I think it's amazing. And actually, they were the first people to do a really good job of making sure their agent didn't do stupid with um the database because we had very early on the agents were like trying to shove image data into Postgress. you know, they were turning off RLS in order to get their projects to work um by papercliping basically is that Lovable wrote really good skills to stop their agents doing stupid stuff. They were they were the first.
</details>

>> 这就是秘诀所在。

<details>
<summary>Original English</summary>
>> That's the secret sauce.
</details>

>> 对。对。解决所有这些……

<details>
<summary>Original English</summary>
>> Yeah. Yeah. To solve all this
</details>

>> 而且……而且现在模型本身也不再做那些蠢事了。

<details>
<summary>Original English</summary>
>> and and and now like the models themselves don't do that stupid stuff anymore.
</details>

>> 没错。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 所以情况已经大有改善了。它已经从类似于大约 2022 年威尔·史密斯吃意大利面的状态，变成了 2026 年威尔·史密斯吃意大利面的水平。

<details>
<summary>Original English</summary>
>> So, it's it's the situation has improved a lot. It's gone from like um Will Smith eating spaghetti circa you know 2022 to Will Smith eating spaghetti in 2026.
</details>

>> 是的。是的。呃，而且那是个……那是个著名的梗。

<details>
<summary>Original English</summary>
>> Yeah. Yeah. Um and that's a that's a famous meme.
</details>

>> 呃，聊到……说完这个我就不再纠缠迁移这个话题了。你知道，让我深受启发的大领悟之一，就是当我见到 CO2 的 Karen 时——她是你们的董事会成员之一——她说，比如她的论点是整个……你知道，你们不仅仅是……

<details>
<summary>Original English</summary>
>> Uh talking about I'll leave the migration point alone after I mentioned this. You know, one of the things that I got like a big aha moment was when I met Karen from CO2 was one of your board members and she said like her thesis is whole like you know you are not just
</details>

<!-- chunk 7/10 -->

### 企业数据库迁移与去 Oracle 化

替代 Firebase，你看起来也像是……你知道的，就像亚马逊的新版 RDS，对吧？[清嗓子] 针对亚马逊。嗯，如果存在第四阶段，也就是 Supabase 在后 AI 时代的第四纪元，那就像是另外……你知道的，就是你增长中的万亿倍跨越。拔掉 Oracle。我、我不知道，比如对啊，那是不是……这就是著名的迁移目标，我听说过一些疯狂的统计数据，比如——现在情况可能会有所不同，因为他们正在尝试……Oracle 正在尝试把一切都搬上云端——但我记得大概是一年前，有人说按营收计算，只有 5% 的 Oracle 工作负载运行在云端。所以几乎每个人都在说：噢，让我们拔掉 Oracle 吧，让我们搞迁移吧，大家……

<details><summary>Original English</summary>
replacing Firebase you're also like you know coming off as like new new RDS right for [clears throat] for Amazon. Um if there was a you know stage four of fourth era post AI of superbase that is like the other you know the one trillionx in your in your growth. Rip out Oracle. I I don't know like yeah what is is is that that's the one that the famous migrations are after I heard some crazy stat like that it might be different now cuz they're trying to Oracle are trying to move everything to the cloud but I think it was like one year ago someone said that only 5% of Oracle workloads by revenue ran in the cloud and so like almost everyone was saying oh let's rip out Oracle let's do migrations people
</details>

不过这就是我的意思：当我回顾那些尝试执行这种策略的数据库提供商的历史时，它听起来确实令人惊叹，而且这当然也是我们自己会尝试去做的事情。我们为什么不去试着做这件事呢？但这极其困难，我认为你首先只想专注于打入企业内部。

<details><summary>Original English</summary>
that's what I mean though when I look through the history of database providers who have tried to run this strategy, it sounds amazing and it's something that we will of course try to do ourselves. Why would we not try to do this? But it is incredibly difficult and I think you will just want to focus first of all on landing inside the enterprise.
</details>

>> 是的，这很有道理。这是属于那种……你知道的，当我整天看到并与搞编程智能体的人交谈时，最大的承诺就是你终于可以从拥有的所有这些旧遗留软件中迁移出来，对吧？希望这意味着你能把所有东西都切换过来。

<details><summary>Original English</summary>
>> Yeah, that makes sense. It's it's one of those things where like you know when I see and talk to coding agent people all day long the great promise is that you can finally migrate off of all this legacy software that you have right and like hopefully that means that you cut over everything.
</details>

>> 确实如此，因为让 Oracle 如此具有黏性的原因之一，就是你最终写了这些多达百万行的存储过程，比如你把所有东西都塞进了数据库里，所以实际上如今重写那些东西可能要容易得多了。

<details><summary>Original English</summary>
>> That's true because one of the things that actually makes Oracle so sticky is like you end up writing these million line stored procedures like you stuff everything into your database and so actually probably rewriting that is these days a lot easier.
</details>

>> 没错。没错。所以希望编程智能体能带来繁荣。也许它们还没发展到那个地步。也许你们必须变得更偏向本地部署。

<details><summary>Original English</summary>
>> Right. Right. So like hopefully coding agents are the boom. Maybe they're not there yet. Maybe you guys have to become more on prem.
</details>

围绕迁移的大多数问题其实并不在于重写，例如在数据分析方面，你可以很容易地从一个数仓迁移到另一个数仓。问题在于，通常你的 OLTP 数据库支撑着你最能产生收入的应用程序。因此，一分钟的停机时间基本上就意味着直接损失金钱。于是你最终要做的事情就是必须让这两个东西并行运行。而这样做的风险在于你会遇到这种脑裂，也就是一部分数据在一边运行，另一部分在另一边运行。如果你试图去调和脑裂——任何尝试过这样做的人都知道——那是一个非常困难的问题。所以当涉及到 OLTP 时，风险要高得多，以至于很多时候人们只是开始将工作负载拆分出来，他们会启动新的工作负载。他们会在这里做很多操作，并希望最终能把东西迁移过去。

<details><summary>Original English</summary>
Most of the problem around migrations is actually not not rewriting it and you can do migrations for example on the data analytics side quite easily from one from one warehouse to another. The problem is that usually your OLTP database is powering your most revenue generating application. So a minute of downtime means that you end up with basically dollars lost. And so then what you end up doing is having to run these two things in parallel. And then the risk of this is that you get this split brain where you've got some data running on one side, some on another. And if you try to reconcile split brain anyone who's tried to do it, it's a very hard problem. So the risks are just so much higher when it comes to OLTP that a lot of time people just start doing splitting the workloads off and they'll start new workloads. They'll do a lot of operations here and hopefully they'll migrate things over.
</details>

>> 是的。不过通常那样你就会遇到两个问题了。[笑声]

<details><summary>Original English</summary>
>> Yeah. Usually then you got two problems though. [laughter]
</details>

### HTAP 与 DuckDB/Duck Lake

好吧，说到 OLTP，我是说，呃，这纯粹是数据库爱好者的沉迷探讨了。我们这里也请过 Databricks 的两位联合创始人，Matei 和 Reynolds，他们当时声称自己已经解决了 HTAP。

<details><summary>Original English</summary>
Well, speaking of LTP, I mean, uh, this is just like down database indulgence. We also had two of the co-founders of data bricks here, mate and Reynolds, where they are making a claim that they have solved HTAP.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这有点像数据库从业者心中的白鲸，对吧？如果你了解的话，呃，传统上你需要一个 OLTP，你需要一个 OLAP 数据库。嗯，两者永不相交，只不过呃，有时候你希望永远都不需要去复制任何东西。

<details><summary>Original English</summary>
>> Which is the sort of the white will of database people, right? If you if you know like uh well, traditionally you need an OOLTP, you need OLAP database. Um, never the two shall meet except that uh sometimes you you would like to never have to replicate anything.
</details>

>> 是的。你们有在关注那些东西吗？比如对于未来的某个阶段，Supabase 在那方面会有动作吗？

<details><summary>Original English</summary>
>> Yeah. Are you are you paying attention at all to that stuff? Like is is there is there a story there for super basis on some one someday?
</details>

>> 有的，我们对 Duck Lake 特别感兴趣。我认为 Duck Lake 是一项非常……并且 DuckDB 是一项非常有趣的技术。

<details><summary>Original English</summary>
>> Yes, we are particularly interested in duck lake. I think ducklake is a very and ductb is a very interesting technique.
</details>

>> MotherDuck 但加上一个数据湖？Duck Lake 是什么？

<details><summary>Original English</summary>
>> Mother duck but a but a data lake like what what is what is duck lake?
</details>

>> 呃，Duck Lake。好的。那么嗯，DuckDB——最近有 DuckDB，它基本上就像是用于分析的 SQLite——

<details><summary>Original English</summary>
>> Uh duck lake. Okay. So um duct DB which was recently there's duck DB which is basically like a SQLite for analytics
</details>

>> 列式存储。

<details><summary>Original English</summary>
>> column the storage.
</details>

>> 对。没错。完全正确。它可以直接从对象存储中读取。通常大家都是这么宣传它的，而且它实际上也可以从你的 Postgres 数据库中读取。所以这是开源的优秀技术，实际上还有呃，DuckDB Labs，它最近被 AWS 收购了。是的。所以他们是一个正在开发的基金会，他们正在围绕该开源项目建立一个委员会。我实际上觉得 DuckDB 有点像分析生态系统中的 Postgres，因为他们试图让它不属于任何人。它能做很多事情。它非常通用。

<details><summary>Original English</summary>
>> Yes. Exactly. Exactly. It can read directly from object storage. That's typically how it's touted and it can actually read from your Postgress database as well. So open source great technology and actually there's also uh duct DB labs which was recently acquired by AWS. Yeah. So they're a foundation that are developing so they're building a committee um around the open source. I actually think of duct DB a little bit like the Postgress of the analytics ecosystem in that they're trying to make it so that it's owned by no one. It does a lot of things. It's very versatile.
</details>

>> 就像是荷兰的一位教授搞出来的。

<details><summary>Original English</summary>
>> It's like a professor in Netherlands.
</details>

>> 对，没错。他们常驻荷兰并在那里工作，这挺酷的。因此，我们在数仓方面的主要兴趣并不是试图把 Postgres 变成分析型数据库，而主要是在于针对特定的任务使用合适的技术。我不知道 HTAP 是否……很多人都试图屠杀 HTAP 这条恶龙，对象存储可能是解决之道，但通常我们认为，一旦在 OLTP 方面达到一定规模，你就需要进行分片；你能拥有的 NVMe 磁盘空间是有限的，所以如果你需要跨两个服务器拆分事务，你基本上最终就得从对象存储中获取它，这最终会拖慢你的数据库。所以我们认为分片绝对是扩展到拍字节（PB）级的最佳途径，然后你应该对你的分析区别对待。现在这并不意味着你不能把数据直接存放在对象存储上，比如然后再通过不同的路径去读取它，但据我看来，试图把这两者强行揉在一起并不一定有多大意义。

<details><summary>Original English</summary>
>> Yeah, exactly. They live they live and work out of the Netherlands which is pretty cool. So our interest mostly on the warehouse side is not trying to make Postgress an analytical database but mostly then focusing on using the right technology for the right job. I don't know if HTAB many people have tried to slay the HTAB dragon object storage could be the solution to that but generally we think once you get to a certain size on the OLTP side you need to have sharding there's a limit to the amount of MVME disk space that you can have so if you need to split transaction across two servers you're basically then going to be fetching it from object storage eventually that will slow down your database so we think that sharding is by far the best way to do scale up into the pabytes and then you should treat your analytics differently. Now that doesn't mean that you shouldn't store your data directly on object storage for example and then read from it from a different route but trying to smash these two together doesn't necessarily make that much sense in my opinion.
</details>

>> 是的，我、我很乐意就聊到这，因为我们确实还有更多……呃，要……呃，探讨的内容。我确实觉得，你知道的，他们有一些创新，基本上我所理解的是，他们利用了数据库机器上闲置的计算资源来支持所有这些复制。

<details><summary>Original English</summary>
>> Yeah, I I I'm happy to leave it there because we do have more uh to uh work on. I do think, you know, they have some innovations where they're they're basically using their their spare compute on their uh database uh machines to power all this uh replication is is my read of what they're doing.
</details>

>> 而且老实说，我并没有太深入研究他们是如何实现 HTAP 的。所以我可能会说错。

<details><summary>Original English</summary>
>> And actually to be honest, I haven't looked so much into how they're doing HDAP. So I could be misquing.
</details>

>> 是的，没错。这就像你专注于自己的赛道，你知道的，又不是说你的客户在拍桌子向你索要这个功能。这只是相当于如果你未来某天想成为首屈一指的数据库公司，你必须有一个应对方案。

<details><summary>Original English</summary>
>> Yeah, exactly. It's it's like you're you're in your lane, you know, it's not exactly like your customers are like banging the table asking you for this. It is just like if you want to become the preeminent database company someday you have to have an answer.
</details>

>> 是的。[笑声]

<details><summary>Original English</summary>
>> Yeah. [laughter]
</details>

>> 是的。确实。是的。

<details><summary>Original English</summary>
>> Yeah. Exactly. Yeah.
</details>

### 持久化工作流与大模型实验室合作

>> 这就像……是的。这很有意思。呃，我还要关照的另一个话题是持久化工作流以及、以及你知道的那个领域，正如你所知，Temporal……呃，我一直在、我一直在为其击鼓呐喊好一阵子了。你们已经做了……呃，比如每年你们都会做一点点东西。

<details><summary>Original English</summary>
>> Which like Yeah. It's it's interesting. Uh the other mention I will check in on is durable workflows and and you know that world which as you know temporal uh I've been I've been uh banging the drone for a while. You have made uh like every year you made you do a little thing.
</details>

>> 是的。是的。我们正逐步朝着……[笑声] 那个方向迈进。

<details><summary>Original English</summary>
>> Yeah. Yeah. We're incrementing our [laughter] way towards
</details>

>> 所以比如你难道不……为什么这对你们来说不是更高优先级的 P0 级任务呢？因为比如你知道 Temporal 发展得极其出色，对吧？

<details><summary>Original English</summary>
>> So like don't you like how come it's not like more P 0 for you because like you know temporal is doing super well right?
</details>

>> 好吧。那么我们做持久化工作流所缺少的是什么呢？计算，

<details><summary>Original English</summary>
>> Okay. So what was missing for us to do durable workflows compute
</details>

>> 对吧？所以你们现在正在做这个了。

<details><summary>Original English</summary>
>> right? So you're you're doing this now.
</details>

>> 是的。这是一个非常有趣的领域，我认为……是的，现在我们已经看到社区里有人尝试在 Supabase Functions 之上构建工作流引擎，但这根本行不通，因为有两秒超时的限制。

<details><summary>Original English</summary>
>> Yeah. Super interesting space to be in I think like yeah now we have had people in the community try to build workflow engines on top of superbase functions and it just didn't work because of the 2C timeout.
</details>

>> 是的。现在我们拥有了可以解锁执行长时间运行的持久化工作流能力的原语。

<details><summary>Original English</summary>
>> Yeah. Now we've got the primitive that would unlock the ability to do longunning durable workflows.
</details>

>> 我想我对 Supabase 最初的设想就是，你想要那种多合一的、那种作为后端一体化整合的 Agentic 云，供人们可以使用，对吧？比如你们现在有了通过 ChatGPT 登录，这是呃很棒的一部分，就像你基本上只需要给 AI 提供它想要的一切，然后它就会成为你最好的朋友。

<details><summary>Original English</summary>
>> I think my original pitch for Superbase is like you want the sort of the all-in-one the the sort of aentic cloud that like is the back end integrated back end that that people can can use, right? Like you've got signing with Chad BT now which is uh a great part like you you just kind of have to sort of give the AI everything it wants and then it will be your best friend.
</details>

>> 是的。是的。差不多。[笑声] 差不多就是这样。并且还要保持多产。我的意思是，我们的 V1 策略就是尽可能多地与这些前沿实验室和模型展开合作。所以，我们必须在那方面保持高产。然后基本上我们看到我们的附着率也在上升。

<details><summary>Original English</summary>
>> Yeah. Yeah. Pretty much. Pretty [laughter] much. And be prolific. I mean, our B1 strategy is to partner with as many of these frontier labs and models as we can. So, we've got to be prolific there. And then we basically we see our attach rates just going up as well.
</details>

>> 是的。我的意思是，显然有美国的实验室，而且你、你、你人就在美国。其他实验室有重大的合作关系吗？它们是怎样的？Mistral，

<details><summary>Original English</summary>
>> Yeah. I mean, obviously there's the US labs and you're you're you're here in the US. Do the other labs have significant partnerships? What What are they like? Mistrol,
</details>

>> Cohere，中国的实验室。我不知道是否……

<details><summary>Original English</summary>
>> Coher, the Chinese labs. I don't know if
</details>

>> 倒没那么多，它们可能、它们可能会有。

<details><summary>Original English</summary>
>> Not so much where Well, they might they might do.
</details>

>> 好的。你主要关心的是美国。好的。[笑声] 好的。没错。

<details><summary>Original English</summary>
>> Okay. You primarily care about the US. Yeah. [laughter] Okay. That's right.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。主要只是因为目前是它们带来了最多的流量，对吧？这可能会改变。

<details><summary>Original English</summary>
>> Yeah. Mainly just cuz like that's who's delivering the most traffic at the moment, right? That could change.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但合作具体是怎样的？比如基本上，出现在他们的应用商店里是一回事；而在他们发布时成为其默认选项是另一回事，当你发布……

<details><summary>Original English</summary>
>> But what does partnership look like? Like basically it's one thing to be on the their app store. It's the other thing to be their default thing when they when you launch in
</details>

<!-- chunk 8/10 -->

Artifact。

<details><summary>Original English</summary>Artifact.</details>

>> 对。所以那一点对我们来说非常有趣，希望能成为那些提供商之一。我们过去无法做到的原因之一，就是根本承受不了他们的规模。我是说以 ChatGPT 为例。他们现在有多少用户？十亿月活，12 亿月活跃用户。如果他们的用户每个月都启动一个数据库，那我们现在每个月就得启动 12 亿台 Postgres 服务器。正如我所说，我们必须达到每月数十亿个数据库的规模。直到今天我们收购了一家公司，此前我们一直没能做到这一点。这意味着我们拥有了能够推动它提升的技术。

<details><summary>Original English</summary>>> Yeah. So that one's super interesting for us to be able to hopefully be one of those providers. One of the reasons why we couldn't in the past was because we just couldn't handle their scale. I mean take chat GPT for example. What do they got now? A billion monthly 1.2 billion monthly active users. One of their users launching a database every single month. Now we've got to launch 1.2 billion Postgress servers. It's just as I said we've got to get to the billions of databases per month. We just haven't been able to do it until today where we acquire a company. That means we've got the technology which can drive it up.</details>

>> 规模化。向上扩展。好的。嗯，除此之外，公司还有哪些其他的 P0 目标？比如你知道，在接下来的一年里，你们大致是如何引导方向的？P0 基本上是拿下战略实验室，拿下模型公司，并且呃继续推进我们的 PLG 布局，我们专注于企业级市场的地方在于赢得这些……

<details><summary>Original English</summary>>> Scale up. Scale up. Okay. Um other than that what are other I guess P 0 objectives for the company like you know over the over the next year how are you sort of guiding the direction P 0 are basically win the strategic labs win the models and uh continue our PLG push where we are focused on the enterprise is is winning these</details>

### PLG 的天花板与 AI 带来的转变

>> 新业务。而且更多的是像 PLG 的天花板，当我们创办公司时，我们的想法是靠 PLG 可以做到 1 亿。我们大概能做到 2 亿，但之后我们在打法上就需要做些不同的事情了。但因为 AI，这个天花板一下子被拉高了，我们不知道它被拉高到了哪里，是 10 亿，还是 20 亿，还是你知道，完全可以继续往上走。但我们仍然也想做其他那些事情。所以我们基本上就像去年那样，觉得好吧，我们两者都得做。

<details><summary>Original English</summary>>> new work and it's more that like the ceiling of PLG when we started the company we were like we can get to 100 million on PLG. We can probably get to 200 million, but then we're going to need to do something different in terms of motion. But because of AI, like that ceiling just lifted and we don't know where it got lifted to like is it a billion, is it two billion, is it, you know, you could just we could just keep going. But we still want to do the other stuff as well. So we basically like last year we were like, well, we have to do both.</details>

>> [笑声]

<details><summary>Original English</summary>>> [laughter]</details>

>> 小的事情和大的事情两手抓，你知道，也许我们是有点贪心了。[笑声]

<details><summary>Original English</summary>>> to both the small stuff and the big stuff and you know maybe we're a bit greedy. [laughter]</details>

>> 不，我觉得这正是大家想要的，对吧？同样的心智模型，而且你知道，他们会付钱让你去处理向上跨越几个数量级时的那些细微细节……

<details><summary>Original English</summary>>> No, I I think it's it's what people want right the same sort of mental model that uh and you know they they'll pay you to handle the fine grain details of moving up in terms of orders of magnitude</details>

>> 我不知道那是多少个数量级，但确实相当多。

<details><summary>Original English</summary>>> and I don't know how many orders of magnitude that is but quite a quite a lot.</details>

>> 这真是太疯狂了，因为如果你在 18 个月前问我们，那时我们增长很快。如果你当时问：“你们能做些什么让漏斗顶端扩大 10 倍？”我肯定会说：“没什么办法，这太离谱了，对吧？”然后紧接着整个市场就这样爆发了。所以，咱们拭目以待吧。

<details><summary>Original English</summary>>> It's just crazy because if you would have asked us 18 months ago we were growing fast. If you would have said, "What can you do to 10x your top of funnel?" I would have said, "There's nothing like it's crazy, right?" And then just this whole market just exploded. So, let's see what happens.</details>

>> 是的。我记得在今年年初我们公司的 Offsite 上，我们定了一个极其宏大的营收目标数字，有人跑过来对我说：“哎呀，你不该定那个数字的。大家肯定会完不成，团队会非常失望的。”结果我们只花了大概 4 个月就达成了那个数字。从今年年初开始，这简直就是一条不可思议的增长曲线。

<details><summary>Original English</summary>>> Yeah. I remember at our company offsite at the start of the year, we we put this crazy ambitious revenue number out and someone came up to me and said, "Oh, you shouldn't have set that number. Like, the team are going to be we're going to miss it. The team are going to be so disappointed." And it took us like 4 months to hit the number. It's just like a ridiculous growth curve from the start of this year.</details>

>> 太不可思议了。嗯，你现在有哪些悬而未决的疑问？比如，如果你有一个能改变你下注方式的水晶球……

<details><summary>Original English</summary>>> Amazing. Um, what are the open questions that you have? Like, you know, if you had a crystal ball that it would change the way that you bet on things,</details>

### 代码优先与声明式 Schema

>> 软件开发未来将如何进行，以及人们将会开发什么。这是我经常思考的两件事。

<details><summary>Original English</summary>>> how development will be done and what people will develop. These are the two things that I think a lot about.</details>

>> 好的。你知道，可能的答案是什么？就只是更多的 Agent，比如……

<details><summary>Original English</summary>>> Okay. You know, what are the possible answers? Is just more more agents like</details>

>> 是的。所以像今年我们重点关注很多……我也会在我的主题演讲中讲到，基本上就是我们正在转变：我们起步时是一家做 Dashboard 的公司，那是当时最好的 DX；然后像大家所熟知的，很多人说“噢，Headless 模式”，Headless 就是我们起步时的模式，Headless 360、Salesforce 这一类东西，我是说我们一开始就具备这些，比如你可以直接使用 API 驱动的 Supabase，这也是我们成功的原因之一；今年我们的重点是从……转向代码优先、Git 原生。基本上就是，当你在本地机器里启动一个 Supabase 实例时，你会得到这个 `supabase` 目录，它代表着你的数据库。里面包含你所有的函数，所有东西。

<details><summary>Original English</summary>>> Yeah. So like this year we're focusing a lot like and I'll talk about it in my keynote basically that we're moving from like we started as a dashboard company that was the best DX then like you know a lot of people are like oh headless mode headless was what we kind of started headless 360 salesforce all these sort of things I mean we had that at the start like you could use superbase directly API driven that's one of the reasons why we succeeded this year our big focus is moving from from to code first get native So basically when you launch a superbase instance inside um your local machine you get this superbase folder and it represents your database. It has all your functions everything.</details>

>> 这个现在就存在了吗？

<details><summary>Original English</summary>>> Does this exist today?</details>

>> 如果你使用我们的 CLI，这个现在就已经存在了。所以……

<details><summary>Original English</summary>>> This exists today if you use the our CLI. So</details>

>> 它是一个虚拟文件系统。

<details><summary>Original English</summary>>> it's a virtual file system.</details>

>> 呃，就像它是……的一种表现形式，就像基础设施即代码。

<details><summary>Original English</summary>>> Uh like it's a representation of it's like infrastructure as code.</details>

>> 明白了。

<details><summary>Original English</summary>>> Okay.</details>

>> 是的。事实上，我们明天要宣布的，就是我们完成了针对声明式 Schema 的最终改动。这其实是一个非常具有挑战性的工作，要覆盖 Postgres 的方方面面。所以现在你可以在你的目录中以声明式的方式拥有 Postgres 的完整文件表示，也就是你数据库的形态。这对 Agent 来说非常重要，因为通常你操作 Postgres 的方式是使用 migration 文件，每次做改动，你就会在这个 migrations 目录里添加一个文件，它就像一个历史日志。好的，这很棒，是行业标准；但想象一下，让一个 Agent 去看上千个文件，并问它：“噢，这个表的结构是什么？”它就必须在这一千个文件里去推测。所以……

<details><summary>Original English</summary>>> Yeah. And in fact what we're announcing tomorrow is like we've done our kind of final change for declarative schemas. This was a a really challenging one actually covering all of Postgress and so now you can have a full file representation of Postgress uh the shape of your database declaratively in your folder that's really important for agents cuz generally how you operate with Postgress is you have a migration file every time you make a change you add a file to this migrations folder and it's like a historical log okay so that's great it's industry standard but imagine putting an agent across a thousand files and telling asking it, oh, what is the shape of this table? It has to guess through a thousand files. So,</details>

>> 它必须重新编译它的……或者你必须在本地启动数据库，跑完所有的 migration，然后再去内省检查数据库，但这太慢了。所以，基本上我们想做的，就是把我们的 `supabase` 目录里的 `schemas` 目录变成你数据库的完全声明式状态。这样我们把从表、策略、呃数据库注释等所有内容都捕获到了这些文件里面。因此我们正在发布一个新的库 PG Delta。你可以把它用在任何 Postgres 数据库上。嗯，但我们为 Supabase 提供了专门的机制。所以这对 Agent 来说是重要的一步。我们知道 Agent 主要将在代码上运作。它们不想去外部调取任何东西。它们必须在文件系统上非常快速地迭代。所以这很好。而今天人们使用的是 CLI，他们对这些 Harness 感到满意。我猜想我们未来会更多地迈向……比如目前我正在尝试仅用手机来进行一些开发，而且我能相当轻松地完成。当然，我知道幕后在发生什么，所以我输入的内容是我清楚从基础设施角度它必须做的事情。但我们正在进入这样一种状态：我可以想象你不需要成为一名工程师。你有了一个想法，你对你的手机、你的 Dot 或者你拥有的任何个人 Agent 说：“我想构建 X”，一秒钟后你就差不多能让这个应用上线运行，你自己就可以对它进行迭代。所以这些就是我正在思考的事情：好吧，如果真是这样，人们会想要哪些用例？是个性化的吗？我们关心的是什么？这些东西会规模化扩大吗？机制是什么？我们将如何进行开发？我们需要提供什么样的工具，才能确保我们成为这个新世界里的默认提供商？

<details><summary>Original English</summary>>> it has to recompile its or you have to launch the database um locally, run the migrations up, and then you inspect introspect the database, but that's too slow. So, basically what we want to do is turn the schemas folder inside our our superbase folder into a completely declarative state of your database. And so we've captured everything from tables, policies, uh database comments all inside these files. So we're releasing a new library PG Delta. You can use it with any Postgress database. Um but we've got mechanisms for for superbase. And so this is an important step for agents. We know that agents are going to operate mostly on code. They don't want to reach out to anything. They've got to iterate very fast on the file system. So that's fine. And today people are using CLIs. they're happy with these harnesses. What I suspect we're moving more towards is like at the moment I'm trying to do some development just on my mobile phone for example and I'm quite comfortably able to do it. Of course I know what's going on behind the scenes. So I'm telling it things that I know it has to do from an infrastructure point of view. But we're getting to a state where I can imagine you don't need to be an engineer. You you have an idea, you say to your phone, your dot or whatever personal agent you have. I want to build X and 1 second later you kind of have this application live you can iterate on it yourself so these are the things that I'm thinking okay what are the use cases that people are going to want if this is the case is it personalized what do we care about are these things going to scale up what are the mechanisms how are we going to develop and what tooling do we need to provide to make sure that we are the default provider in this new world</details>

>> 你感兴趣的、想用通向未来的水晶球窥探的问题还有哪些？

<details><summary>Original English</summary>>> any questions that you're you're interested in is for crystal ball into the future.</details>

### 开发模式的收敛与多样性

>> 作为一个做了几十年的软件工程师，你对于软件应该如何构建有着很强的执念，对吧？比如在持续集成，或者持续交付之类的方面；而且我发现自己会把自己的意见强加给 Agent，比如“噢，你要用这种方式来做”。但现在越来越觉得，你其实不需要这样做了。但我那里的担忧是，它们会不会最终全都收敛到一种构建软件的方式上，或者……

<details><summary>Original English</summary>>> As someone who's been a software engineer now for like a few decades, you have strong opinions on like how the software should be built, right? Like in terms of like uh continuous integration or like continuous delivery or whatever and I find myself like pushing my opinions on the on the agents of like oh you want to do it in this way and but now more and more like you don't need to. But my worry there is are they all just going to like converge on one way of building software or</details>

>> 是的，模式崩溃，你知道的。

<details><summary>Original English</summary>>> yeah mode collapse you know</details>

>> 那挺好的，你们全都会用 Supabase。[笑声] 但……但软件开发行业之所以优秀，就在于这个行业有着著名的论战，对吧？关于什么是正确的方法……

<details><summary>Original English</summary>>> which is great you're all going to use super bases [laughter] but but like the the thing that's great about like the software development industry is like industry is like these are like famous flame wars right of like what's the correct approach</details>

>> 比如我们会失去那种东西吗，或者……

<details><summary>Original English</summary>>> like are we going to lose that or</details>

>> 是的，所以你需要思想的多样性，这样最好的想法才能胜出。但随后模型会让你变得极其懒惰，以至于根本没人费心去看细节。

<details><summary>Original English</summary>>> yeah so you want diversity in ideas so that the best idea can win and but then the models are just going to make you so lazy that nobody even bothers to look at the details.</details>

>> 是的。然后它们就全都收敛到一种构建软件的方式上，接下来，你知道，这会不会成为某种局部最优……

<details><summary>Original English</summary>>> Yeah. And and they just all converge on one way of building software and then that's you know is it going to be like a local maxima in terms of</details>

>> 是啊。我……我不知道。我确实认为，呃，是的，首先我认为这是一种合理的担忧。我确实认为这是你无法控制的。嗯，而且……是的，呃，缺乏品味、或者就叫休闲应用构建者吧，他们会收敛到模型的均值上，也就是你们所处的位置。但是那些有眼光的、高技能的人将始终真正关注细节，正如他们理应做到的那样。

<details><summary>Original English</summary>>> Yeah. I I don't know. I I I do think uh yeah so first of all I think that's a valid fear. I do think it's out of your control. Um I and and yes uh the low taste let's call it casual app builders will will converge on whatever the the mean is the model is which is you guys. But then the the discerning high skill people will always really care about the details as as they should.</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 对。而这些最终会向下渗透……

<details><summary>Original English</summary>>> Right. And which which will which will then filter down eventually</details>

>> 这是我的想法。

<details><summary>Original English</summary>>> is my idea.</details>

>> 但是这些高技能的人还会继续被培养出来吗……

<details><summary>Original English</summary>>> But are these high skill people going to continue to be trained by</details>

>> 呃，我不知道。是的。是的。我是说，我觉得人们足够有热情。我……这是其一……

<details><summary>Original English</summary>>> uh I don't know. Yeah. Yeah. I mean I think I think people are passionate enough. I I it's one</details>

<!-- chunk 9/10 -->

### 大学与自学人才

在这类事情上，比如你看，我确实觉得普通大学大概要完蛋了，对吧？对吧？就像你大概不再需要去读大学了，因为你大概可以自学，然后就是找到自己的工作。向来都是这批顶尖的人在真正推动关键进展，而你得……而且他们总会找到办法来满足自己的利益与好奇心，去探索可能更好的东西。你知道就是那种人：休学一年去 Recur Center，就专门钻研酷炫的编程问题，即便他们本来可以在行业里赚钱……

<details><summary>Original English</summary>
of those things where like you know I do think like uh you know the average um college is probably screwed, right? right? Like you probably don't need to go to university anymore because you can probably self teach and just like you know uh get get your own uh job. It's always been like this top tier of people that that are moving a lot of the the needle and you need to uh and and they will always find a way to have their own self-interest uh be satisfied curiosity in terms of like what what is possibly better. You know the type of people that take a year off and go to the recur center and just work on cool programming problems even though they could be making
</details>

>> 赚钱，在行业里，而且……是的。［笑］绝对是。

<details><summary>Original English</summary>
>> money in in the industry and like Yeah. [laughter] Definitely.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 创始人的合作与分歧处理

>> 你们两个人之间会有什么分歧吗？难得能把你们两位都……

<details><summary>Original English</summary>
>> What do you disagree on between the two of you? It's rare to have the two of you have
</details>

>> 噢，对。这问题太棒了。

<details><summary>Original English</summary>
>> Oh, yeah. That's a great
</details>

>> 请到播客上来。所以，你们懂的，我想捕捉一下这个。

<details><summary>Original English</summary>
>> on on the pod. So, you know, I want to capture this.
</details>

>> 我觉得我们在一起工作之所以这么高效，原因之一是肯定会出现意见不合的情况，但只要对方稍微推进坚持一下……

<details><summary>Original English</summary>
>> I think one of the reasons we've been so effective like working together is because there are definitely situations when we'll disagree, but as soon as the other person like pushes a little bit,
</details>

>> 另一个人就会说：

<details><summary>Original English</summary>
>> the other person's like,
</details>

>> “行，也许你是对的。咱们试试看吧。”是的。

<details><summary>Original English</summary>
>> "Yeah, maybe you're right. Let's let's try it." Yeah.
</details>

>> 所以我们从不会闹到大争吵的地步。事实证明，大部分这类事情其实本来也无关紧要。［笑］只要大方向是正确的，那就还行。但是，呃，是的，我想不出……

<details><summary>Original English</summary>
>> So, we never end up in like big busts. And it turns out like most of that stuff actually doesn't matter anyway. [laughter] Like as long as the general direction is is correct, then then it's going okay. But uh yeah, I can't think of
</details>

>> 噢，你们俩在这儿可真是犯难了。天哪。

<details><summary>Original English</summary>
>> Oh, you guys are really struggling here. Oh my god.
</details>

>> 是啊。是啊。［笑］正因为……因为事情从没有重要到那个程度，比如我们从来没有彻底谈崩过，因为它从来没有重要到需要真正激烈争执的地步。而且我们也很忙。所以通常就像在处理……是的，我们各自在努力处理公司业务的不同部分。

<details><summary>Original English</summary>
>> Yeah. Yeah. [laughter] Which is why like because it's it's never an important enough thing like we've never had a bus stop because it's never been important enough to actually fight hard enough on it. Like and also we're busy. So like usually like handling Yeah. We're trying to handle different parts of the business.
</details>

>> 也可能是业务在增长，显然你们各有各的地盘，大家配合好就行，对吧？

<details><summary>Original English</summary>
>> Maybe it's just like things are growing and obviously you got your domain and and you just need to work together, right?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 起步经历与技术人员合住屋

>> 是啊。挺有意思的，你看，呃，Laura 在这儿，呃，我们三个人当时都在新加坡的 Entrepreneur First。你们各自在做不同的公司，然后在这期项目结束后你们留了下来，在项目结束后成了合租室友。

<details><summary>Original English</summary>
>> Yeah. It's interesting, you know, uh so Laura here uh all three of us were in entrepreneur first in Singapore. You were all different working on different companies and then you guys stayed back after the cohort at your housemates after the cohort.
</details>

>> 是的。是的。当时我们都在……我们住在一间七个人的房子里，大家都在做不同的创业项目。

<details><summary>Original English</summary>
>> Yeah. Yeah. So we were all we lived in a house with seven people and we were all doing different startups.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 于是他在做他的创业项目，我做另一个。这都是在 Supabase 之前。

<details><summary>Original English</summary>
>> And so was doing his startup, I was doing another one. This is before superbase.
</details>

>> 然后不知怎么的，我想是你们的气场，呃，你们发现很适合一起共事，一起做这个……

<details><summary>Original English</summary>
>> And so like I think somehow your energies uh you know you you you found that you were suitable working together and and working on this uh this
</details>

>> 是的。因为传统上，尤其是在孵化器模式里，你作为技术人员会被推着去和某个领域专家搭档，对吧？呃，但在我们住的那栋房子里，基本上七个人全都是建造者，全是技术人员。我们发现这种配对要高效得多，尤其是在做开发者工具的时候，因为作为开发者你本身就是领域专家，我们能把事情做得多得多。于是后来我们把住在那个公寓里的大多数其他人也招了进来，成为我们的员工。Rory 是……

<details><summary>Original English</summary>
>> Yeah. Because like traditionally especially in in an accelerator model, you're pushed as a technical person to work with some domain domain expert, right? Um, but in the house we lived in, it was basically seven people who were all builders, all technical people. And we found that pairing to just be like so much more effective, especially on when you're building dev tools cuz you are the subject matter expert as a developer is that we could could just get so much more done. And so then we ended up hiring most of the other people who lived in the the flat as well as our employees. Rory, who
</details>

### 早期招聘与 PostgREST 维护者

>> 是第一号员工吗？呃，不是第一位，但他是负责市场拓展的第一人，比如现在他掌管整个市场拓展。

<details><summary>Original English</summary>
>> was the first employee? Um not the first but the first to on go to market like now he runs all of go to market.
</details>

>> 那个 PostgREST 的人是第一个。

<details><summary>Original English</summary>
>> The post guy was first.
</details>

>> 不是，呃，Angelico。

<details><summary>Original English</summary>
>> No uh Angelico.
</details>

>> Angelico。是的。我们带了个实习生。

<details><summary>Original English</summary>
>> Angelico. Yeah. We had an intern.
</details>

>> 是我上一家初创公司的实习生。

<details><summary>Original English</summary>
>> An intern from my previous startup.
</details>

>> 我们就直接把他拉过来了。［笑］

<details><summary>Original English</summary>
>> We just dragged him along. [laughter]
</details>

>> 是的。然后另一位可以说是第一位全职雇员，是 Steve Chavez 这位，呃，他是 PostgREST 的维护者。有趣的是，我们当时在 YC 营里，在 YC 他们给你的建议是：好的，我们会给你一大笔钱；现阶段不要招任何人，最大的诱惑就是招一个大团队。我们去找我们的合伙人说：噢，但我们碰到了 Steve，他是 PostgREST 的首席维护者。他当时就说：立刻招他。［笑］他说：别管那些建议了，去把他拿下。

<details><summary>Original English</summary>
>> Yeah. And and then the other like first like full-time hire was this guy Steve Chavez who um who was the Postgress maintainer. And the funny thing is we were in the YC batch and the advice they give you in YC is like okay we're going to give you a bunch of money. don't hire anyone at this the big temptation is to hire a big team and we went to our partner and we said oh but we've got this guy Steve he's the lead maintainer of Postgress and he was like hire him immediately [laughter] he was like forget the advice go and get him
</details>

>> 是因为他的声誉，还是因为对 Supabase 合适？

<details><summary>Original English</summary>
>> of his reputation or because it made sense for superbase
</details>

>> 嗯，对，两方面都有。当时很明确，这项技术是我们重度依赖的，我们打算全面投入。而且有意思的是，我们招了 Steve 并对他说：不用担心 Supabase，只管继续构建 PostgREST，把它做得很棒就行。

<details><summary>Original English</summary>
>> well yeah both it just made sense that you know this was a technology we were very reliant on and we going to lean in and it was like and the the funny thing is we hired Steve and we said don't worry about Superbase just keep building Postgress and just making it awesome.
</details>

>> 呃，然后显然如果我们有支持请求或者别的什么，我们可以去问他们。不过，呃，这种模式运转得非常好。后来当 Steve 想扩大 PostgREST 团队时，我们就招了更多专门做那个项目的人。你们为社区和开源做了这么多。我脑子里一直在想的一件事是：大型商业开源的未来会是怎样？呃，一方面显然存在大量的垃圾代码，而且我相信你们也正在面对这个；但另一方面，你们的依赖项现在也变得……呃，可选了，就像你可以随意凭感觉去写出任何东西……

<details><summary>Original English</summary>
>> Um and then obviously if we have support requests or whatever we can we can ask them but um and the model just worked really well and then we ended up when Steve wanted to grow the Postgress team just hiring more people dedicated to work on that project. Well you guys are doing so much for community and open source. One thing I do have in my mind is like what is the future of large commercial open source? Um, one obviously there's a lot of slop and and I'm sure you guys are dealing with that but two also your dependencies are now becoming uh optional like you can just vibe code whatever you want
</details>

>> 任何东西。是的。是的。是的。

<details><summary>Original English</summary>
>> anything. Yeah. Yeah. Yeah.
</details>

### 开源的重写与 Rust 趋势

>> 所以，关于开源的未来，无论你们脑子里在想什么，我都非常想听听。

<details><summary>Original English</summary>
>> So I I whatever you is in your heads about the future of open source I'd just love to hear it.
</details>

>> 我觉得用 Rust 重写是一种合理的机制。我是说，我们团队里有人来找我，他们说：噢，对，对，我正在用 Rust 重写我们正在做的所有东西。然后我说：你打算重写到什么层级？要重写数据库吗？你要重写 PostgREST 吗？PostgREST 还没有重写，还不是用 Rust 写的，但我怀疑你不会关心到那么深的层级。所以这取决于你希望推进到哪一层，在这些层级上东西会被重写，然后你又不想把自己宝贵的创新代币或实际代币花在重写所有东西上面。所以几乎每款工具都可能会收拢，假设收拢到 Rust，如果这最终成了编写工具的终极方式的话，因为它更快、更正确。这对大多数开源工具来说可能都会发生。但在你做完这轮迭代、所有东西都跑在这种极其高效的语言上之后，你就不会每一次都把所有东西都重写一遍了。到时会出现少数几个赢家。一个很经典的例子可能就是 PostgREST。它是用 Haskell 写的，这是一种非常不寻常的语言，维护起来非常困难。它现在能用 Rust 写吗？是的，大概可以。而且这个机制、这个功能依然很有价值，如果真的发生了，可能会出现一个 PostgREST 的 Rust 分支，并且那会成为那个特定领域的赢家。

<details><summary>Original English</summary>
>> I think the rewrite in Rust is a valid mechanism. I mean someone came to me on our team and they're like oh yeah yeah I'm rewriting everything in Rust that we're doing like uh and I was like to what level are you going to rewrite the database are you going to rewrite Postgress? Postgress is not rewritten is not in ROS but I doubt down to that level you care. So there's like layers upon which you want to get to where things will be rewritten and then you don't want to be spending your actual innovation tokens or your actual tokens rewriting everything. So there's going to be like a a collapse of almost every tool probably into let's say it's Rust if that ends up being the the ultimate way of writing things cuz it's faster and more correct. And that will happen probably for most open source tools. But then after you've done this iteration and everything's running on this highly effective language, then you're not going to be rewriting it all of the things every single time. There'll be a few winners. A really classic one could be say Postgress. It's written in Haskell which is a very unusual language and it's very hard to maintain. Could it be written in Rust now? Yeah, probably it could. And the mechanism the the function is still valuable and probably there'll be if that happens there'll be one rust fork of Postgress and that will be the winner for that particular category.
</details>

>> 但你们目前还没这么做，而且你们有很多东西也是用 Elixir 写的。

<details><summary>Original English</summary>
>> But you haven't done it yet and you're and a lot of your stuff is elixir as well.
</details>

>> 是的。所以那是另一回事。在基础设施方面你也得去考虑。Elixir 是门非常有趣的语言，因为有 BEAM。所以，当你在进行运维时，你就会开始思考：运维的正确机制到底是什么？所以……

<details><summary>Original English</summary>
>> Yeah. So that's the other thing. Then you have to think on the infrastructure side. Elixir is like a really interesting language because of the beam. So, so and then you start thinking when you're operating things, what is the right mechanism for operating? So,
</details>

>> 但现在你其实很容易就能切换编程范式，只要你能通过所有测试，诸如此类。

<details><summary>Original English</summary>
>> but now you can change paradigms pretty much easily as long as you fit all your tests and you know.
</details>

>> 是的。是的。嗯，这是个好问题。我倒没怎么想过我们要不要把 Elixir 换成 Rust。

<details><summary>Original English</summary>
>> Yeah. Yeah. Well, that's a good one. I haven't thought a lot about would we switch Elixir to Rust.
</details>

>> 这在现在只是多了一种选项。呃，Vercel 的 Malte，呃，你知道，他发过一条推文让我印象很深。他有许多很有意思的想法。他说拨出一笔钱，把我们所有 C 层级或 C++ 层级的依赖项都用 Rust 重写。呃，因为我们心里清楚它就是更好。它更安全，更正确，诸如此类。

<details><summary>Original English</summary>
>> It's just an option now. Uh Malta from Vercell is uh you know one of his tweets that sticks in my mind. He he's got lots of uh interesting thoughts. He set aside some amount of money and rewrite all of our dependencies uh at at the C level or C++ level into Rust. Um because we just know it is better. It's safer, more correct, whatever.
</details>

>> 而且这是一次针对开源的彻底升级。

<details><summary>Original English</summary>
>> And it is it is a one-time upgrade of open source.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 涵盖所有驱动程序，所有你使用的东西。呃……

<details><summary>Original English</summary>
>> All the drivers, what whatever you you use. Um
</details>

>> 所以我觉得这算是一个挺有意思的……

<details><summary>Original English</summary>
>> so I thought it was like a pretty interesting
</details>

>> 我挺喜欢这个构想的。是的。我觉得它不会发生，因为大家都喜欢亲手去做。

<details><summary>Original English</summary>
>> I quite like that as an idea. Yeah. I don't think it will happen because people love to do it themselves.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但是作为一个想法，我……作为一家公司，我们百分之百会支持。

<details><summary>Original English</summary>
>> But but as an idea I I would like we as a company would 100% get behind that.
</details>

### Supabase 内部的 AI 编程政策

>> 太棒了。然后，呃，我想最后一个收尾问题，也是我之前应该在前面某个地方提出来的：Supabase 内部的 AI 编程情况，对吧？呃，显然你们是外部编码 Agent 的巨大受益者。呃，内部的政策是怎样的？你们在这上面花销多大？有针对这笔开支的担忧或类似情况吗？Supabase 一直以来感觉就像是把一堆不同的初创团队拼贴在一起。比如我们有认证授权产品，而且我们一直非常坚持他们应该自己做决定，比如自己选用什么工具。

<details><summary>Original English</summary>
>> Awesome. And then uh I think closing question which I I should have stuck in somewhere earlier. AI coding within Subbase, right? Uh obviously you guys are big beneficiaries of coding agents outside. Uh what is the policy internally? How much are you spending? Is there is there concern about spend anything of that sort? Superbase has always felt like a bunch of different startups like glued together. So we have like the orth product and we've always been very insistent that they should make their own decisions like on what tools they use
</details>

<!-- chunk 10/10 -->

### 团队自主权与 AI 政策

比如他们作为团队的行为方式，比如汇报架构。AI 政策也差不多是这样，很多人都在问 AI 编程政策是什么，我们的回答就是：这完全取决于你们团队自己。我想我们已经开始在一些细节上进行整合，特别是在成本方面，但只要可以，我们还是希望尽量保持那种模式，让各个团队自己决定他们想如何开展工作。就是这样，非常去中心化。[笑声]

<details><summary>Original English</summary>
like how they behave as a team like the reporting structure and the AI policy was kind of no different is like a lot of people asking what is the AI coding policy and we were like well just it's up to you as as your team. I think we have started to consolidate a few bits especially around cost but as much as we can we'd like to keep that model of like let the teams decide how they want to run things that's it very decentralized [laughter]
</details>

### AI 支出基准与人机支出比

>> 我想说的是，呃，我正试着为公司领导者们理出一个可以带回去参考的数字，也就是市场标准大致是怎样的。那么，呃，这里有哪些可以作为依据的数据点呢？人们常说，呃，你知道的，普通人每月大概花费 20 美元，普通员工每月大概是 200 美元。OpenAI 呃，你知道，在差不多第 50 百分位数的水平，每月支出大概是三千到五千美元，而最高百分位数大概在几十万美元，对吧？所以大概就是这样的概念。我认为一个很好的衡量指标基本上就是你的 token 支出与人力支出的比例，对于很多人来说，可能是在 0.1 个 token 对应一个人力薪水，呃，你知道，你大概可以很安全地提高到 1，而如果你超过了 1.5，你可能就有麻烦了，大概是这样。是的。所以我们，我只想说，幸运的是作为一家远程公司，基本上发生过的所有事情都有记录。

<details><summary>Original English</summary>
>> I I would say um I am trying to figure out a number for company leaders to take home with them as like what is the market standard and so uh what what are data points you can hang your head on here people say uh you know the average person is spending like $20 a month and and uh average employee is maybe $200 a month. OpenAI uh you know at the the sort of 50th percentile is spending maybe three to 5,000 a month and the top percentile is in the maybe hundreds of thousands right and so that is the rough idea I think a good metric is basically what is your ratio of token spent to human spend and it's r like for a lot of people is may be 0.1 tokens to to one human salary and uh you know you can probably go up to one pretty safely and if you're over 1.5 you're probably in trouble something like Yeah. So our I just say luckily as a remote company basically everything that's ever happened is documented.
</details>

>> 所以我可以问我们的 AI 我们花了多少钱。目前我们每月大概花费 30 万美元。

<details><summary>Original English</summary>
>> So I can ask our AI how much we're spending. So currently we spend about 300k per month.
</details>

>> 是的。对应 600 人。

<details><summary>Original English</summary>
>> Yeah. For 600 people.
</details>

>> 不，450 人。

<details><summary>Original English</summary>
>> No 450 people.
</details>

>> 450 人。好的，明白了。这能给人们一个概念。但是，关于你刚才说的根据员工数量来按比例衡量成本，对我们来说也是说得通的，因为我们招人非常快。所以如果我们最终能仅仅通过额外的……

<details><summary>Original English</summary>
>> 450 people. Yeah. Okay. It gives people an idea. But but what you've said about like scaling the cost in terms of related to the number of employees makes sense also for us because we are hiring very quickly. So if we end up getting a lot of leverage out of just like extra
</details>

>> 你应该会，对，那就……

<details><summary>Original English</summary>
>> you should be right then
</details>

>> 没问题。你需要一大群无服务器员工，可以根据需要随时启动和关停。对吧。

<details><summary>Original English</summary>
>> fine. You need a whole bunch of serverless employees that can spin up and down as as you need. Right.
</details>

>> 是的，完全正确。就像，对，你知道，我刚才有一位另一家顶级初创公司的 CTO 说，他很担心自己公司的支出，而我说，其实那是你对其他所有人的投资，而且可能分布非常不均衡，对吧？就像你公司里有两三个人极其狂热，而其他人可能根本没怎么用……

<details><summary>Original English</summary>
>> Yeah. Exactly. which is like yeah like you know I I just had a CTO of uh you know another top startup say like he was worried about his company's spend and I'm like well actually your that's your investment in everyone else and probably it's very skewed right like there's there's like two or three people that are super insane at your company and everyone else is like probably not using
</details>

>> AI，对。

<details><summary>Original English</summary>
>> AI yeah
</details>

>> 这也正是我们所看到的情况。我们搞了一个排行榜，把排行榜挂出来，大家通常会觉得有点不好意思，所以他们就有点像……[笑声]

<details><summary>Original English</summary>
>> that's exactly what we see as well we got a leaderboard and people we put the leaderboard up and usually people are a little bit ashamed so they kind of like [laughter]
</details>

### 端到端系统思考与异步文档

>> 是啊，因为你可能在浪费钱，而且那也是错误的重点。重点不应该放在你花了多少钱上，而是从系统思考的角度来看，你在端到端上带来了多少改变。你应该去思考：你到底实际解决了多少个不再需要人工介入的端到端流程，或者将原本漫长的人工作业流程压缩成了非常简短的过程。所以这才是我们在如何使用 AI 上投入最多精力的地方。幸运的是，你知道，正如你所见，由于我们是一家异步协作公司，在 Supabase 发生过的每一件事都有文档记录。所以围绕 Supabase 构建一个公司治理框架（比如一个日程管理框架），基本上就只是进行形式化的固化。你可以让 AI 对准它提问，我们的原则是什么？它就会把 Supabase 整个历史上的所有决策原则都记录下来。所以那是我们投入大量时间的地方。在我们聊完人员之前，我想我们现在大概有 50 个在招职位，而且我们是完全全球远程的。所以我们不在乎你身在何处。如果你非常出色……

<details><summary>Original English</summary>
>> Yeah cuz you're wasting money probably and that's also the wrong focus like The focus shouldn't be on how much you're spending, but like how much end to end like in terms of systems thinking, you should be thinking like in terms of how many end toend processes are you actually solving that where you no longer need a human in the loop or collapsing down longunning human problems that suddenly become very short problems. So that's where we're spending most of our investment on like how we're using AI. Luckily, you know, as you saw, like every single thing that's ever happened in Superbase is documented because we're an async company. So, building a company harness like an agenda harness around Superbase is basically just formalizing. You can point AI at it and say, what are our principles and it'll do document down all our decision making principles for the whole history of Superbase. So, that's where we're spending a lot of our time. Before we move on from people, we do have I think now like 50 open roles and we are fully globally remote. So we don't care where you are. If you're very good
</details>

### 全球远程招聘与 SRE

>> 无论在哪薪资都一样，对吧？

<details><summary>Original English</summary>
>> same salary everywhere, right?
</details>

>> 是的。不论你住在哪里，薪资都一样。如果你在自己的专业领域非常出色，请务必看看我们的招聘板。

<details><summary>Original English</summary>
>> Yeah. Same salary regardless of where you live. If you're very good at what you do, please take a look at our job board.
</details>

>> 好的。你能否挑出一个岗位画像——随便选一个你脑海中最先想到的——重点说说你们在招什么以及为什么？

<details><summary>Original English</summary>
>> Yeah. Can you uh can you like one profile just pick one whatever is top of mind as uh as your highlight for what you're looking for and why?
</details>

>> SRE。好的。是的。

<details><summary>Original English</summary>
>> SR. Okay. Yeah.
</details>

>> 为什么呢？

<details><summary>Original English</summary>
>> Why?
</details>

>> 因为我们的增长速度太惊人了。我们能招到多少 SRE 就要多少。

<details><summary>Original English</summary>
>> Because we're just growing at a ridiculous rate. We need all the S surres we can get.
</details>

>> 那什么样的品质会——你知道，你们大概会收到很多 SRE 的求职申请，但大多数可能连看都不会看，那什么样的人能够脱颖而出呢？

<details><summary>Original English</summary>
>> What is the quality that is like you know you probably get a lot of S applications and you don't look at them like what what stands out.
</details>

>> 我们真正在乎的是，你确实想做远程工作。呃，所以这是——虽然听起来挺奇怪的，但确实如此。我们收到了很多优秀人才的申请，但要在 Supabase 融入进来，你必须得适应并活跃在远程优先的环境中，也就是完全异步的环境。这其实并不适合每个人。我们在很早期就吸取了这个教训。有些人进来之后会说：“噢，这……我还是需要见到活人。”

<details><summary>Original English</summary>
>> The thing that we really care about is that you you actually want to work remotely. Um so it's this is a strange one but yeah it's true we get a lot of quality people but to fit in at Superbase you kind of need to thrive in a remote first environment like a fully async environment. It's actually not for everyone. We learned that pretty early on. People would come in and they'd be like, "Oh, this is like I need to see humans."
</details>

>> 我对 SRE 的典型印象就是那种灰白胡子的极客，坐在某个地牢般的地方，反正本来也不想跟人类说话。

<details><summary>Original English</summary>
>> My typical model of an SR is like this gray beard that's like sitting in a dungeon somewhere and doesn't want to talk to humans anyway.
</details>

>> 那就是最完美的人选。[笑声] 这样的人，请一定要申请。

<details><summary>Original English</summary>
>> That's the perfect person. [laughter] All of those people, please apply it.
</details>

>> 希望他们能收听这期播客。

<details><summary>Original English</summary>
>> Hopefully they listen to the podcast.
</details>

>> 是啊，是的。不，我是说，是的，在 SRE 领域我们可能确实有很多资深的大胡子。呃，我公开表达过一个观点：对于智能体初创公司来说，AI SRE 是最难攻克的领域之一。我觉得我可能很快就会被证明是错的，但到目前为止这个判断依然成立。不知出于什么原因，AI 还没有搞定它。抱歉。

<details><summary>Original English</summary>
>> Yeah. Yeah. No, I mean, yeah, we we we probably do have a lot of great beards um in SR. I I think one of I have been on the record as saying AI sur is one of the hardest categories for for agent startups. I think I might be wrong soon, but so far it's been correct. Like the AI has not cracked it. Sorry. For for whatever reason.
</details>

>> 不，不，不，还没有，我同意。

<details><summary>Original English</summary>
>> No, no, no, no, not yet. I agree.
</details>

>> 是啊。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 比如编写软件，你知道，尚且可以说是已解决的问题。而维护它，比如保持系统持续平稳运行……

<details><summary>Original English</summary>
>> Like building software is, you know, debatable. Solve problem. Maintaining like keeping things running.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 完全是另一头完全不同的猛兽。

<details><summary>Original English</summary>
>> Is a whole different beast.
</details>

### 结语与祝愿

>> 嗯，好的。好吧，感谢你们为大家保持系统稳定运行。伙计们，祝贺你们一路走来的历程。能够作为你们的朋友和投资人，见证你们的进步，我感到非常骄傲。我迫不及待地想看到你们上市敲钟的那一天，无论什么时候。呃，看起来还需要一些时间，但那一定会非常有意思。我真的很想看到你们，你知道，去完成敲钟，并且建立起下一个伟大的开源公司，对吧？太棒了。

<details><summary>Original English</summary>
>> Well, okay. Well, thank you for keeping things running for everyone else. You guys, congrats on your journey, man. Like, I'm so proud to be your friend and an investor and and just like just see the progress. I cannot wait for the IPO whenever that is. Uh it looks like it's going to take some more time, but it it'll be it'll be fun. I I really want to see you guys like, you know, do the whole ring the ring the bell and, you know, building the next great open-source company, right? Excellent.
</details>

>> 必须的，兄弟。感谢邀请我们。

[音乐]

<details><summary>Original English</summary>
>> Definitely, man. Thanks for having us.

[music]
</details>