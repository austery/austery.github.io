---
author: AI Engineer
date: '2026-05-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sJ2jc7leKBk
speaker: AI Engineer
tags:
  - ai-agent
  - personal-automation
  - knowledge-management
  - obsidian
  - workflow-automation
title: AI Agent接管我的生活：开放式AI系统深度集成与个人工作流重塑
summary: 本文记录了Radic如何逐步将AI助手OpenClaw集成至个人生活，从简单的聊天工具演变为能够访问邮件、笔记、日历、操作系统甚至代码的强大代理。通过深度整合Obsidian知识库，AI不仅构建了个人知识体系，还实现了自动化日常任务、邮件草稿撰写及主动信息过滤。演讲者强调了AI系统演进的渐进性、关键挑战（如内存管理和自动化稳定性），以及AI作为“未来自我”助手所带来的生活变革，为理解AI赋能的个人生产力提供了深度视角。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenClaw
products_models:
  - OpenClaw
media_books: []
status: evergreen
---
### AI代理的渐进式生命集成

演讲者Radic分享了他如何逐步将AI助手 **OpenClaw** 集成到个人生活中，最终实现了对个人数字生活的深度控制。这个过程并非一蹴而就，而是通过一系列微小的、可控的步骤完成。最初，OpenClaw仅能通过单一渠道（如WhatsApp）进行交互，随着信任和能力的增长，它逐渐获得了访问邮件、笔记、文件、日历、操作系统（包括自动化脚本）以及对用户所有计算活动进行记忆和学习的能力。这种“把生活钥匙交给AI”的模式，如果一开始就尝试全部实现，将是不可思议且低效的。

<details>
<summary>Original English</summary>

Hey, I'm Radic. I'm one of the open claw maintainers and uh I want to talk what happens like in my life with open claw when I practically gave the keys to my life to to open claw and and like it almost like literally and uh what that actually means so so this happens like step by step it wasn't all at the same time but it can access my emails. It can access my notes, files, calendars, tools, my operating system, so automations and it builds on top of like memory of everything that I do uh at the computer. So, uh it can do anything with it that uh that is possible to do with the computer. But it didn't all happen in one big like leap. So I install OpenClaw and now I it just like controls my life and does everything for me. Uh that that would be silly to do or like even silly to expect that this could even work.

</details>

### 知识库赋能：Obsidian与AI的深度融合

OpenClaw能够真正“运行生活”的关键一步，在于其能够访问并理解演讲者多年的知识积累。演讲者拥有一个庞大的 **Obsidian** 知识库，包含约3000个markdown文件，涵盖工作、个人事务、项目、研究、文章链接等各方面信息。OpenClaw通过其强大的搜索和记忆能力，使得这些分散的知识点能够被关联、提炼，并置于特定的上下文之中。例如，当收到一个链接（如推文、文章或YouTube视频）并输入到“收件箱”时，AI会自动分析内容，添加标签和上下文，查找已有的相关笔记，建立新的连接，从而将原本可能被遗忘的书签转化为有价值的知识资产，并能在恰当时机主动提醒用户。

<details>
<summary>Original English</summary>

So what happened is that I I tried installing uh just like like everybody does just like with one channel. I think it's at the beginning it was just WhatsApp then I migrated to telegram now I'm on discord but it was just uh just WhatsApp just uh one ability to do to do to just like chat okay so we are there uh what what's next that we can do uh let's let's do some like one simple workflow or one very simple task that we can do once we are there let's go to the next step so this is how it happened where I am today where I used to think that I have quite a simple setup with uh my open claw and what it does because I never did any big change but when I encounter different I don't know Twitter threads uh YouTube videos or talking to other people how they have it set up I see that like my setup has everything that they have more on top of that and most also is just like more sophisticated than what what I see out there which was really surprising to me because I felt that it's just like one small step at a time. I have a pretty like simple setup works for me but uh that that's what I want to to show how that happened and how it looks like today. So you you already had like a lot of talks about how the sausage is made, how we are making it better. You'll have more talks about the insides of the open claw. I want to show how it looks from the other side from the first the simple user then power user. Now I'm also a maintainer. you don't have to go to the maintainer route but uh when I was playing like with one of the uh workflows I just encountered some errors and just like submitted first PR then the second PR then just looked into Discord and then you just got involved now I'm a maintainer there so it's also was just like one one step at a time uh so that that's the set of these are the steps that uh it usually happens that I see I see the need uh I solve it in in a very simple way uh and and then I add more steps to it and this is also why I usually don't have big issues that people have that okay now it broke my computer or it just like completely bricked during the update because I have all these small steps that I take if something breaks I just like step take one small step back fix it see what doesn't work, understand why it didn't work, uh have a setup that it never happens again, and just like take one step further again. So, uh where it started being more and more helpful and kind of like running my life is when I gave it my knowledge base. So, I had a lot of stuff in my Obsidian which I built up for years. So, right now I have like about 3,000 pages or notes, markdown files in my Obsidian. And this is everything. This is work stuff, personal stuff, tasks, projects, research. Um, what else? Articles kind of like an inbox of links that I'm just putting there and it then finds the the connections u, and puts it in in perspective and in context to to other stuff that I have. So all of that is now accessible through my open claw with a very good search. I have search and memory. I have like normal search. I have QMD search for for obsidian. I have different memory for for my workspace. uh and all of that is interlin and and and that that's where that magic happens. And when I saw recently and that that's where it hit me that I probably don't have a simple setup. When I recently saw Andre Karpat's tweet that went viral uh where he says about LLM knowledge bases, I was reading that and it's just like yeah, that's exactly what I have. like what's like super uh revolutionary about it and then I I I understood that okay so I got there step by step it works for me so it's probably probably worth I don't know sharing sharing telling more about it u showing how it works showing how you can get to that point as well uh and uh for example for Obsidian um do Yeah, this this is how this is the real screenshot of my my vault and all the nodes and these are different clusters. Some are probably uh project related like the big clusters. Some of the one off uh these are probably more uh kind of like bookmarks. And one of the tasks that I'm doing and that I have is that when I add something uh to inbox it then takes that link that I add there looks what's there it could be a tweet it could be a thread uh it could be an article it could be a YouTube video analyzes it adds tax to it adds context to it looks at what's already there on this topic in my vault, how it could be helpful in other areas and adds connections to it. So what previously was just like Twitter bookmarks that you bookmark and you never go back to that now it just adds more context builds up my knowledge base and is much more helpful and even surfacing the things for me when I add a bookmark that okay so you already had like this and this and this about this subject and this is how it connects maybe you should look at those notes and very often it's just like yeah completely forgot about that and and that's a good source of of knowledge and of thinking about it. Uh because that was the reason why I'm adding this bookmark. Uh so that that's where it's it's starting to uh to be super super useful.

</details>

### 自动化夜间任务与多功能代理

OpenClaw的一个重要能力体现在其自动化夜间运行能力，允许AI在用户休息时执行关键任务。这包括同步更新所有索引（如QMD、记忆和Obsidian Vault），备份数据以防丢失，以及执行一些预设脚本来管理更新过程。通过这些自动化脚本，AI能够判断哪些操作可能导致问题，如何在更新前进行验证，以及如何在网关重启后确保其恢复正常。这种“代理我”的模式，使得用户第二天醒来时，AI助手已经准备就绪，并能提供最新的邮件摘要、日历更新等信息，极大地解放了用户的日常精力。

<details>
<summary>Original English</summary>

On top of that also uh at 4:00 a.m. well like 4 a.m. is just like uh an example of that that I have. This happens probably between 3 and 6 more or less. Um, so this is what what is happening when I'm sleeping. So when I'm sleeping again, my agent does everything so that it runs well. It indexes everything. It backs everything so that worst case I if I lose something, I lose maybe couple hours of work of content of anything else. refreshes all the indexes for for QMD for memory for my Obsidian vault and I I start fresh in the morning uh with uh whatever waits for me maybe summary of the emails of the calendar uh everything updated the latest uh the latest open version is waiting for me which also took like step by step I have some scripts around it so that it knows what to do and what not to do when updating what can break, why it breaks, how to verify it before updating or before restarting uh your gateway so that it is able to come back online again. So that that all is uh also uh automated and as as I get up it's it's already waiting for me uh fresh and ready for me to start the day.

</details>

### 多维任务支持与渠道化管理

AI代理通过其多任务处理能力，支持了演讲者日常工作的多个维度。这包括：
1.  **环境操作 (Ambient Operations)**：负责后台的更新、维护和“管道”工作，无需用户介入思考。
2.  **注意力过滤 (Attention Filtering)**：利用对用户知识库（Obsidian）的全面理解，识别重要且紧急的信息（如支付失败、域名续期），并主动通知用户，甚至在特定情况下（如处理项目邮件）直接起草回复。
3.  **执行支持 (Execution Supports)**：能够根据邮件内容和项目背景，草拟回复，并将其置于草稿箱供用户最终审阅。
4.  **信息合成 (Synthesize)**：例如，将零散链接汇集成知识库，构建上下文。

为了更好地管理这些功能，OpenClaw通过Discord中的不同频道进行组织，如“收件箱”（Inbox）用于构建知识库，“咨询”（Consulting）处理客户项目，“视频研究”（Video research）用于内容创作前的资料搜集，“早报”（Briefing）提供每日摘要，“Instagram”和“YouTube”分别支持社交媒体发布和视频创作，而“开放式抓取”（Open claw）频道则用于维护者事务。“游乐场”（Playground）频道则作为测试新模型、设置或工作流的实验区域。

<details>
<summary>Original English</summary>

And each open claw is like I'm not a big fan of sharing like my exact setup because that exact setup is like very specifically for me for what I need right now uh for what I will need in the near future for like the errors that I encountered for issues that I want to be solved. But to give you some idea so that we can talk more also about specifics and not just like in general. So these are some like five areas or five types of jobs that my agent is doing. Uh the first one is is ambient operations. So so this is what I just uh showed you. So it it does all the updating. It does all the plumbing. Uh it does all all the stuff that needs to happen. But I don't need and I don't want to think about um the the second is attention filtering. So this is also super useful that because it has access to everything and because it has all the content context actually uh so it knows that for example when an email comes and uh it's something important or urgent and it knows from obsidian what's the context and the background behind it. Uh yeah I I keep everything in obsidian about projects about everything else. So it then can proactively tell me that uh I think I have here. So like these are like three very specific examples that I had recently that when the system notices that something is important and urgent, it just lets me know. So like Netflix payment failure for some reason didn't go through uh was fixed within five minutes when it happened. Domain renewal coming up. I would probably miss that email. Uh but uh it it picked it up uh gave me gave me a message on my discord uh renewed my domain uh emails uh that can already be with enough context given about the project for example it can already uh give like read the email uh understand what's happening understand what's already done within the project and just draft the reply and and it's already in in draft uh folder for me to uh accept or or delete or make some changes. So, so these are some examples of like potential filtering uh execution supports. Yeah. So, that's draft synthesize is that uh the the inbox and these are on the right. These are the channels that I have in my discord that more or less relate to these types of jobs. So general is where I have everything. Uh I just start the conversations uh see where it goes and if enough times I have a type a certain type of conversation I added a specific channel for it. So the these are uh like real screenshots from from today morning. Uh the inbox is where I just like drop links and it builds the knowledge base for me. Consulting is for for for the clients and every all the backgrounds. It knows all the projects. It's know knows all the quotes, deadlines, tasks, next steps, everything else. Video research is for for YouTube for researching what's what's out there uh to help me uh with with the next episode. Uh briefing is for morning briefings. Instagram for social posting. YouTube is uh for for creating creating the the videos. Open claw is for maintainer stuff and there's also one playground channel uh which it changes depending on day month or the need. Uh it's for testing. I usually test maybe a different model, maybe a different uh workspace, different way of setting up uh the the important files like memory and everything else. So I just play there, see what works. If something worked, uh I promote it. If if it doesn't, uh I discard it.

</details>

### 系统协同与优化方向

OpenClaw的成功运行依赖于多个组件的协同工作：**LLM**（大型语言模型）用于理解、判断和建立连接；**文件**、**工具**和**脚本**提供了执行能力，其中脚本甚至可以在无需LLM判断的情况下直接执行任务。演讲者强调了优化**记忆文件**（如 SoleLM 文件和 Critical Rules MD）的重要性，因为记忆的质量直接影响AI的可靠性。他分享了从单一记忆文件到多记忆文件管理，再到“梦想”（Dreaming）功能（用于促进记忆）的演进过程。此外，他也指出了几项关键的优化挑战：**糟糕的记忆**会累积并导致问题；**脆弱的自动化**（尤其是多步骤自动化）容易出错，需要拆分或增加保护机制；**噪声节点**需要定期清理；以及**薄弱的边界**（weak boundaries）也需要优化。

<details>
<summary>Original English</summary>

Uh and all of that works because it's not just uh it's a system that has many moving parts that work well together. So LLM is for judgment like understanding the email, understanding the context, making the connections. Then there are all the files the the tools the scripts that I have built the scripts are just like if this happens do this it's done you don't even need judgment so LLM is even skipped uh and important uh thing is also to optimize your memory file your sole soulm file uh I have also critical rules MD uh because even if I had something in agents MD or in soulm uh it it still managed to to forget something or not do something uh with critical rules. Having critical rules helps and having it uh mentioned quite high in the agent D file. Uh so that that's also an improvement. Uh I I went through a few different setups of memory where I had one memory file. Now now that uh I have like the whole memory folder now we also have dreaming where uh we have like promoting the memories. So this is important to work on these files uh and but it's easy to do in open because everything is inspectable. These are markdown files editable you can look at it you can read it you can understand it uh and it works well. Uh what gets harder? Uh bad memory compounds. If the memory is not set up correctly and your vault, your nodes, your memories grow to thousands, you're going to have an issue. So you need to actively work on that. Brittle automations, especially when it's like 10step automations, uh it can break and it probably will break at some point. So it's again either split it up into simpler ones or or have uh some guard rails uh that are more effective uh noisy nodes I'm getting rid of them cleaning um cleaning regularly and weak boundaries. So so those are all the sol everything else uh that the files that that are important to optimize for your needs.

</details>

### AI代理作为“未来自我”的赋能者

演讲者最后总结了他的AI使用哲学：AI代理是帮助“未来自我”的工具。他将过去、现在和未来自己比作不同个体，而AI的任务就是帮助“未来自我”——那个更强大、更能干的自己——减少执行任务的负担，使其在醒来时拥有更优化的状态。通过AI，他不再需要为过去的自己（那个“懒惰”的自己）承担所有工作，因为AI已经为“未来自我”做了大量准备。这种理念强调了AI在个人生产力、时间管理以及减轻认知负担方面的潜力。他鼓励听众从解决一个反复出现的痛点开始，逐步建立信任，增量式地构建知识库，并将重要信息迁移至markdown格式，最终实现AI与个人生活的深度协同。

<details>
<summary>Original English</summary>

Uh so what I want you to take away from this is that like do what I did and then at some point you realize yeah this stuff is awesome and this stuff helps my life. Um start with one recurring pain grow trust incrementally build the knowledge base uh move everything or like move as much as you can or as you want to markdown files and and start making those connections. Um, inspecting system expectable is is easy for you done for with uh with open claw um and optimize for the future you and this is what I want to close with. So couple years ago I had an article about like the past me, the present me and the future me and the past me is just like this completely stupid guy. He does nothing. He's lazy. Uh he doesn't want to do anything. So now I present me need to do everything for that like past me and and the future me the future me is just like kind some kind of like god creature it can do anything uh that that that creature is like um all powerful and just like if I don't do something today it's fine that that other creature will do it for me. So that that was the the issue and uh the job for me is to to become friends with the future me to to treat that as a person that I want to help with and that's the job of the agent. So I don't need to do as much as I used to because the agent just helps the future me as much as possible so that when I wake up tomorrow it's like as much as could be done but someone else other than me is done. So that's that that's the whole purpose of of this setup at least for me. I don't know it could be different for you. So that's what I want to leave you with. Thank you.

</details>