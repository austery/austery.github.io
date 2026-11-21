---
author: How I AI
date: '2026-05-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pUHA_jNwuYE
speaker: How I AI
tags:
  - ai-agents
  - workflow-automation
  - developer-experience
  - continuous-integration
  - spec-driven-development
title: Notion的AI驱动工程会议：告别繁琐更新，拥抱高效开发
summary: 本期节目邀请Notion的工程经理Ryan Nystrom分享AI如何彻底改变软件工程工作流程。他介绍了AI代理如何自动化站会准备、加速代码编写及推动规范驱动开发，强调了AI在提升团队协作效率、减少倦怠和加速CI/CD中的关键作用，并探讨了未来工程师的角色转变。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Ryan Nystrom
companies_orgs:
  - Notion
  - Work OS
  - OpenAI
  - Perplexity
  - Cursor
  - Orcus
  - Stripe
products_models:
  - Codeex
  - GPT-54
  - Conductor
media_books: []
status: evergreen
---
### AI颠覆工程工作流：赋能更高效、更愉悦的开发体验

Ryan Nystrom分享了AI如何彻底改变他的工作方式，从传统的iOS开发转向充满新鲜感和乐趣的AI驱动模式。他提到，过去20多年的软件工程经验中，工程师需要花费大量时间在会议中讨论实现细节，而现在**AI**（Artificial Intelligence: 模拟人类智能解决复杂问题的技术）能够迅速将想法转化为可执行的规范，甚至一步到位地完成开发。Claire Vo总结道，嘉宾们普遍认为AI让他们工作更高效、更有趣，并指出AI不仅改变了工具和编码方式，更革新了团队管理模式。

Notion内部的项目Afterburner（代号“加力燃烧室”）旨在将**持续集成**（Continuous Integration, CI: 开发者频繁地将代码集成到共享主干，并通过自动化测试验证）时间缩短四分之三，体现了对开发效率的极致追求。Ryan强调AI代理的无抱怨特性，可以在会议前五分钟处理任务，这与人类员工需要提前准备形成鲜明对比，极大地缓解了工程师的焦虑和倦怠感。他指出，AI带来的“三赢”局面——更放松、更有趣、完成更多工作——打破了传统“质量-速度-成本”三选二的困境，实现了“全都要”的愿景。

<details>
<summary>Original English Source</summary>

One line that I've been putting in my prompts lately is I literally don't know what I'm doing here. You got to explain it like I'm a 5-year-old. I didn't start with writing code. I didn't start with anything. I just started with an empty markdown document. I actually just opened up Whisper and just started yapping about how this feature should work. I gave the YAP session to Codeex and was like, "Write a spec." I then opened up Codeex again, pointed it at this spec file, and I said, "Build it." And basically one-shotted this. I've been in software engineering for 20 plus years. We were writing these documents and we were sitting in meetings with other engineers debating the merits of one implementation versus another. And now no more waiting for the meeting, no more waiting for review.

>> I'm not a CI expert, but I kind of know what I want. And so other folks were kind of like, can you just bring some of your like puppy dog energy to like CI and just see what we can do? Your AI, your agent is never going to complain when you ask it to do this 5 minutes before the meeting starts.

>> It is more relaxing and it's more fun and I feel like I'm getting more done. It's weird to have this like win-winwin.

>> They do the triangle and they're like, "Pick two." And you're like, "No, I want to pick all three.

>> Give me the whole triangle.

>> Give me the whole triangle." Welcome back to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have Ryan Nestrom from Notion and he's going to show us as an engineering manager how you can never prep for a standup again. We're also going to see how you can get a background agent to write code for a fix your friend texted you and how specri development really works in a codebase at scale. Let's get to it. This episode is brought to you by work OS. AI has already changed how we work. tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using work OS to move faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today. Ryan, welcome to How I AI. I am really excited because you're gonna show us I think start medium advanced mode on some AI coding stuff. And so before we jump in, how has AI just changed how you live your life at work? I mean it's it has completely upended the way I work. Like I I've been doing this I did a lot of like mobile iOS work in my past and I worked the same way every day for like 12 plus years and then the last year I have changed IDE, terminals, tools like whatever like 10 plus times. Um, so it's like really weird and scary to be like changing this stuff so much, but it's also I feel that like I've been doing this for a while and I'm feeling like so much like joy and freshness and like newness in this that like I wake up every day super excited to like tinker and build things. Uh, and I'm also like working faster and harder than I feel like I ever have, but like in a in a good way. I know people are like kind of freaked out about like ah everything's changing the pace is up but like it's it's really energizing for me.

>> Well, you are not alone. I think every how I AI guest has come on and said I'm having more fun. I'm working faster and everything is different. And what I love about what you're going to show us is it's not just the set of tools which I think has changed or how we write code has changed. How you like run a team has changed. So, and I think for the better, you know. So, I would love to see how you're using notion AI to actually run teams differently.

>> Yeah. For so for context, I I manage a team of like six, seven people. Um, I'm like an engineering manager or uh tech technical engineering, tech lead manager or whatever we call it. I manage people and I write code uh is like my role which I love. And I've run a bunch of different projects here at Notion. The the one I'm going to show today. Uh we've we've nicknamed Afterburner. Like kind of a quick backstory is I've been kind of vocal about our like DevX CI for a while. Um I've just I worked at places where it's really slow. I've worked at places where it's really fast. And I came here and I was like we're kind of like in between, but I feel like we're like slower than we need to be. Uh, and eventually this like caught up to me and somebody was like, "Could you just come fix it and like come work on it?" And I'm not like a infra expert. I'm not a CI expert, but I I kind of know what I want. And I think also most importantly, the the group that I manage and the the org that I work in, we're a little notorious for being like really fast and like very very AID. And so other folks were kind of like, can you just bring some of your like puppy dog energy to like CI and just like see what we can do? And that's what we've that's what we've done. So we had this really aggressive goal to cut our CI into like a quarter of what it is. Um we're on the path to to doing that. But so what I want to show you is a little bit about how we run projects in Notion and how I'm using um AI to kind of streamline those projects. So, what we're looking at here is like our like project hub called Afterburner. And so, in here, I've got all this documentation. I've got databases. Um, we'll look at some meetings. I have like a automation that looks for any sort of like little wins if we knock off seconds from different jobs or whatever. And we keep it we keep track of them in here. But what I want to show you is basically how we run our meetings. Our small group, we'd run a standup every single day.

and doing standups where everyone just like is kind of like deadeyed and going around being like I did this, I shipped this change or you know no updates for me, thanks is like painful and in my opinion like a huge waste of time. I want to like get to the the meat. So we have this kind of like automated meeting template that shows up every single day that we run our meetings which is basically every day and it starts blank and then what I have set up behind the scenes uh is a um custom agent. So, we chipped this Notion AI custom agent stuff a little bit ago, and this runs right after the meeting template gets generated, and it looks through all of our like Slack conversation in the last 24 hours, any tasks in Notion that we close, any um pull requests that we've like merged, just like all sorts of context. Oh, and it looks at like yesterday's meeting transcript as well. And then it compiles it basically like a pre-eread. And um this is a this is one from a week or so ago. And it yeah, it shows it pulls metrics. It can show us like what our latest CI time is. It shows some of the things we've decided. Shows like progress on different like projects or like different things that we're trying to like make faster. bugs, feedback, open questions, tag, like anything that's like of concern. And like I can basically work up until like the minute of our meeting without having done a bunch of like prep. And then we all get on a video call and we look at this screen and we're like, "Okay, here's what we need to talk about." And we'll like hit each bullet. We have like meeting notes that we run down here um within notion and like all the context is basically like captured all of the like agenda is like set up for me. So we spend the entire time talking about like problems, decisions, wins, findings, like what are we going to work on next and it's less the like oh I did this thing.

>> Yeah. What I want to call out for folks that are maybe listening and not watching is this is a very detailed meeting like kind of like pre-eread slatus update which if you're a you know TLM or an EM running good meetings unfortunately is part of part of the job and there's a really big difference between a good standup and a bad standup and I think the the ones you describe these like wrote like I wrote this PR today I'm going to start on this and then basically like a a notes document that's very high level because some human is putting it together. It stinks and you start to like do I the other thing that I found and maybe I'm I'm curious if this has impacted how you work or just made it easier which is like you start to have those meetings less because the updates aren't super rich.

>> People don't feel like it's a good use of their time and I think you lose something by reducing the frequency. But if you can have high bandwidth, high quality meetings with high frequency without the overhead, I think you can get better, more detailed work done collaboratively, especially if you're running like a remote team where not everybody's in the same same room. So I'm curious, do you feel like just being able to get to this level of detail in your standup has improved how you can actually build this product and do these do this work? Basically,

>> I've been in way too many meetings where I can tell like everybody's eyes are glazed over, nobody's paying attention, and I like I have run enough projects at this point where like to me that's like pretty dangerous cuz like everybody in that room has ideas, they have insight, but like because we've made it like so non-productive and like not engaging that like we're not we're just like we need the point of the meeting is to like exchange ideas and information and if we're like not doing that, like literally what's the point? The whole like this could have been an email, like that's what the meme is from. Um, and so I I found that this is basically a good conversation starter. Um, and a a key thing to me that that tells me that this is working is when I'm like I'm running these meetings and kind of going through like bullet by bullet and then I see like, oh, somebody like fixed our mock server environment in our our just tests and we're seeing a test improvement by like up to 13%. Like, oh, I missed that, you know, like that's that's super cool. like tell like let's talk about it and then from that maybe like oh there's additional headroom that we can make on this and so all of a sudden like let's drill into it and so just like I also think it sort of democratizes that like sharing so that you've got some people that um like I I could talk for an entire 30 meeting without shutting up and then other engineers are like you know kept keeping to themselves but like brilliant and super talented and I think it's great this kind of like raises everything up to the top um and makes it very visible. I was I was thinking last night truly this is a little bit of a sidebar but I was thinking last night how people don't know this it's very very confusing as Clarevo the podcast host I am such an introvert I'm a crazy introvert I will avoid humans with every fiber of my being and I find like AI as a proxy for me to get over my own anxiety communicating with the outside world it's like so insane but I really feel it whenever I like message my openclaw and I'm like, "Hey, Paulie, can you email soand so blah blah blah on my behalf?" My anxiety is gone. But when I sit in front of my Gmail and start typing an email, my introverts start showing. I'm like, I can't I can't do it. So, I think this is a real point, which is like you got to pull information out of everybody.

>> Yeah.

>> And there's like spikes and valleys of who is going to come and show off their work, how detailed they're going to be. It does not mean the work is not good. It does not mean they are not talented. they just have different skills in different environments. And so I love this call out of like we're gonna pull equal amounts of information out of everybody because the playing field is is equal. I also want to go back to something you said which makes me think about burnout which you said I can like work up until this meeting starts.

>> Yeah.

>> And I I know so many people who feel like they are in meeting after meeting after meeting one because when they're not in meetings they're preparing for meetings. So you're getting rid of that.

>> Yeah.

>> And then two, I think managers being able to, for example, code up until the standup is such a burnout like protection mechanism, which is you would much rather your managers hands on the code, hands-on doing work, filling a creative impulse than prepping for meetings. Sure, they're great at running the meetings, but let's do that in like this just in time mechanism where they're supported. um through these automations. And so I just imagine I used to feel so stressed as a leader and as a manager being like if I'm not in a meeting, I'm prepping for a meeting and then I'm in a meeting. And if I can carve back more of my time to just do real things, that feels so much so much so much better. So I'm guessing you're having more fun just through the balance of the kind of work you're trying to do.

>> I'm Yeah, I'm having so much more fun working this way. I I have done the like run a big engineering group where yes, you're spending half of your time just compiling information, synthesizing it, writing reports, like doing all this stuff. And I I hated it. Like it's so draining. And now I feel like I'm in a sweet spot where I can support and work with a team of like very talented individuals, but also not have to Yeah. be like doing like paperwork the entire time. Like I I don't want to do like the TDM. I get a lot of joy out of

>> working with people. It's like why I like managing. I like talking with them, having fun. I love like sol solving hard problems together. And then I like building stuff. And um yeah, I think that we're maybe at an inflection point where like I maybe this is controversial or not, but like if you're like a line manager, like write write code, you know, get in there and like

>> 100%

>> stay stay close. Maybe don't do the the the P 0 hero projects, but like yeah,

>> help your team fix bugs, like make optimizations, like whatever, you know? I it's just it's so easy now. I mean, I'm gonna pull that thread all the way up, which is like directors of engineering, VPs of engineering, like CTO's.

>> Yeah,

>> CPOS's it right some code. Now is the time. And I say this all the time on this podcast. This is the era of the hard skill. This is not

>> how do I get better at my my soft skills and managing stakeholder. This is literally like how do you write code? How do you write automations? How do you learn these new tools? How do you understand what models do do what for your own skills?

>> That I think is super important.

>> Okay, we could go on forever on this topic. I do want to show folks how you built this.

>> Yes,

>> because we haven't seen actually haven't seen we've had a couple Notion folks on the podcast. We haven't seen Notion AI

>> in action and I just want to see kind of your thought process on how you build something like this out.

</details>

### 自动化站会与AI驱动的代码生成：提升协作与开发效率

Ryan详细阐述了Notion团队如何利用定制**AI代理**（AI Agent: 能够理解环境、自主行动以达成目标的AI程序）自动化日常**站会**（Standup Meeting: 每日例会，团队成员分享进展、障碍和计划）。该代理会从**Slack**（团队协作通信平台）对话、**Notion**（一体化工作空间应用）任务、已合并的**拉取请求**（Pull Request, PR: 软件开发中请求将代码合并到主分支的操作）以及前一天的会议记录中提取信息。

代理生成一份详细的“预读”（**Pre-read**: 会前阅读材料），包含CI时间、决策、项目进展、改动、缺陷和未解决问题等。这使得团队成员无需会前准备，直接在视频会议中聚焦于问题、决策和重要发现。Claire Vo强调，这种高带宽、高质量的自动化会议能够显著提升远程团队的协作效率，通过细节化的报告激发更深入的讨论，而非传统的“流水账式”更新。她还幽默地提到，自己作为内向者，通过AI代理发送邮件可以避免交流焦虑，这凸显了AI在**信息共享**（Information Sharing: 在团队或组织内传递数据和知识）中的“公平化”作用。

接着，Ryan介绍了“Boxy”项目，一个将AI代理（如**Codeex**：一个代码生成和处理的AI模型）集成到Notion任务流中的内部开发工具。他通过简单的文本描述和截图，让AI代理在**虚拟机**（Virtual Machine, VM: 模拟计算机系统，可在其中运行操作系统或应用）中自动完成代码修复和功能开发，并在短时间内生成包含UI验证截图和测试结果的拉取请求。这种**规范驱动开发**（Spec-Driven Development）模式，将AI作为代码编写者，极大地加速了开发周期，并改变了**代码审查**（Code Review: 开发者之间相互检查代码，确保质量和发现问题）的模式，使得工程师可以更专注于架构和验证。

<details>
<summary>Original English Source</summary>

So, I'm going to flip over to uh this is our custom agent. Don't ask me why we got this like potato theme for like the entire project. I think it was kind of something about like CI is just this like cobbled together like mess and so we're going to like make the potato like a rocket ship. I don't know. I don't even know if that makes any sense, but like now we're having fun with it and we have reactions and like agents and it has spun off into its own thing which is fun. But this is our hot potato agent. So you can see I have this set up to run at 9:00 a.m. every single day. Um it's also set up for chat. it's set up if the agents mentioned, but we never really use any of that. And probably the important part is the actual instructions. So in this instruction page giving context on like what the purpose of this agent is, I am telling it to run yeah look back at 24 hours. So basically telling it your job is to run every single day and I only want you to look back for the last like 24 hours of activity. I'm explicitly telling it to use sub agents, which is kind of a sleeper feature in Notion AI. Like, this exists, but we don't we don't really push it to use it very often yet because it's one, it's very expensive, and two, it can be kind of finicky sometimes. But, um, I help build it, so I know how this works. Uh, and then I ask it to kind of like fan out and do like a map reduce where I'm saying go use the honeycomb MCP to figure out what the latest metric is. look in our project channel and like find updates, feedback, questions. I tell it where the task uh database is and how to look for tasks within this project and then how to find yesterday's meeting. And then I give it a template in the instructions where I'm like this is your format. I care about CI speed, decisions, progress, changes, bugs, questions, risks, a little bit of guidance on writing, and then when it's done, uh, I have it post to Slack and I like emphasize this like b I want it to be brief and fun and sometimes it's really corny and then sometimes it's like really good, uh, and it'll be very quirky and just post this like link in our Slack channel and it's like, hey, here's your your pre-eread, some little quibble about like whatever, you you know, like, hey, you guys are not making enough progress. Uh, and then that's it. And then it's we have our meeting note. It's updated. What I like the most about this one, you can show you some of our like internal settings. So, this is like I give it access to all these things. And I'm like, you can only view all of this stuff because I don't want it going and like modifying our task database, our project database. Like, everybody at Notion uses those. But this meetings database in particular, I'm like, you know, you can edit content because this is the one you're going to like write and update the page. It can read from our Slack channels, respond to our project one, and then th this was new to me actually when I set this agent up is our MCP. So, we've had MCP and we have this other thing called workers, which is like kind of like writing code. I haven't used them very much within custom agents, but in this one in particular, I'm like I know exactly where this metric is. It's in honeycomb. And so I like just configured the MCP in notion. By the way, I like I like used the agent to like set itself up. I was like, here's the query. I literally gave it a screenshot of the honeycomb query. I was like, I don't know how this works. Can you just like update your instructions? And

>> I love that you screenshot it. You didn't even copy and paste it. You're like, "Please OCR this screen."

>> Exactly. Too lazy. I'm like, "Here it is. Just take it. Figure it out." And it it kind of it got it mostly like most of the way there. I had to fiddle with it a little bit, but yeah.

>> What what I appreciate about this, and again, for anybody trying to just brainstorm workflows where AI can actually have a huge impact on your productivity at work or life, I just feel like write down what you would do if you had time. If you had time, every morning at 9ine, you would sit down and you with your eyebrows would go through Slack. You would go through Honeycomb. You would ask people what's going on. You would look at GitHub and then you would compile it and then you would try to be very fun in Slack. Like it's it's just a description of what you would do. And

>> yep,

>> it's it doesn't have to be that complicated. You can iterate so quickly on it. What I appreciate about this, you know, versus old era of more deterministic like workflow style builders is the updates are so easy to make. Just change the natural language, redo the order, change the trigger, give it more

>> um access to data, and then it's it's ready ready to go.

>> Yeah. And you know, I think the other thing I I've gotten hung up on when trying to think about like these automations and I I've seen others do is that like you get this like you start gigabraining it and you're like, well, how am I going to save like 5 hours of work a day? And I what you just said made me realize too that like the the tedium that this removes for me is not like worldchanging, but it's like 20 minutes a day. And that's like 20 minutes I can spend doing other stuff. And that like it's not even just about like saving that 20 minutes, but it's like protecting my brain from like having to context shift about all this stuff and like ingest it. and instead, yeah, it's just I know that the information will be there when I'm ready to like read it and I'm ready to like shift gears to this project. Um, rather than Yeah, I I hate doing the like read this update, copy all this information, like put it into like an update board. Like it's soul sucking.

>> I mean, you and I have been doing this for a while. That's like that was I feel like 70% of my job at some point 70% of my job was just like, what's going on? How do I massage it into a format appropriate for the audience at hand? And it's always the same information. It's just like what's the executive version of it and what's the team version of it and what's the fellow team version of it and like like my shoulders drop out of my ears when I realize we don't have like we just don't have to do it anymore. And the other thing that I think people maybe underappreciate about AI and this like just in time delivery is your AI your agent is never going to complain when you ask it to do this five minutes before the meeting starts.

>> I know it's so it's so great.

>> It's so great. It's just like when you have it, drop it, get it done and out of your brain. I think is just again I go back to like burnout and enjoying your work and reducing toil and it just feels like a more relaxed way to work.

>> Yeah,

>> we're happy.

>> It's so funny because it is more relaxing and it's more fun and I feel like I'm getting more done. It it's weird to have like this like win-winwin.

>> Yeah. You know, they they do the triangle and they're like, "Pick two." And you're like, "No, I want to pick all three."

>> Yeah. And I'm like, "Give me the whole triangle.

>> Give me the whole triangle." That stamp it for the YouTube thumbnail. Give me the whole triangle. All right. This episode is brought to you by Orcus, the company behind Opensource Conductor, which powers complex workflows and process orchestration for modern enterprise apps and agentic workflows. Legacy business process automation tools are breaking down. Siloed, low code platforms, outdated process management systems, and disconnected API management tools weren't built for today's AI powered world. Orcus changes that. With Orcus Conductor, you get a modern orchestration layer that scales with high reliability and brings humans, AI, and systems together in real time. It's not just about tasks. It's about orchestrating everything. APIs, microservices, data pipelines, human in the loop actions, and even autonomous agents. So build, test, and debug complex workflows with ease, all while maintaining enterprisegrade security, compliance, and observability. Orcus, orchestrate the future of work. Learn more and start building at orcus.io. Let's talk about So we talked about how meetings happen. Love this. You do write code, though.

>> I do write

>> sometimes with your fingers and sometimes with You're my favorite harness of the moment. Um, so let's go to how you get coded.

>> Yeah, I I want to show the little bit of a new workflow that we have going on in notion. Um, I honestly don't think this is necessarily a big feature that we're going to ship or some we might ship some version of this feature. So, this is all basically internal only at this point. But prior to this, the way one, I love codecs. I've been a codeex stand for like I don't know six seven months now and we started uh we started building this like codeex integration into notion. Prior to this it was like I mean obviously you're using the CLI to like write your prompt and then they created the codeex app which is which is nice but I'm still like writing my prompt in this thing. So, I started actually writing prompts in notion pages where I can be a little bit more like free form and structured and you know I'm in like the CLI. I don't have to worry about like hitting enter and then like oh like I sent my prompt. Uh I can actually like write a document in uh notion but then of course I'm like cop or like highlighting all of the text, copying it, going into my terminal, hitting paste and like letting it go. It's like fine. Um, there's like MCPS and other stuff that I could be using, but I'm I'm a very simple person. There's like too much too much stuff. Um, so we built this thing that uh we're kind of like calling it I think we're calling it both software factory, but I like its internal project name is uh Boxy um because it's like all these little VMs that we install codecs and cloud code on. That's our little boxes where now we can actually invoke them from like tasks within notion. And so, uh, literally happened this morning. A friend of mine, um, who's a notion fan text me. He's like, "Hey, I like the tab block that you built." Um, which is this thing. He's like, "But I really wish I could like you. I can like copy." I'll show you now. if I click on the dot dot dot thing next to a block, there's like copy link to block. He was like, "Man, I really wish I could just like copy link to a tab and then like send it to somebody." And I was like, "Oh yeah, that that sounds really easy." So, I opened up this task and I just took some notes and I dropped in this screenshot showing them uh where it could live. You know, this is like on the the tab block. If I right click on it, we get this little flyover menu. and I just described the task. I was like, "Yeah, let's put a copy link button here." I also noticed that hovering over the delete button didn't change to red. So, I was like, "Yeah, we should fix that." And I was like, "I know when edge cases like you're going to have to like if you land on a URL where we're like linking to this block and this tab, like it's got to like switch to the tab on like fresh refreshes." So I like kind of outlined all the the cases, but you can see here this is one, two, three paragraphs, four like four sentences and a screenshot. It was like not not a lot. And then uh this new thing that we built, I can actually mention codecs from within our comments. And this triggers are like boxy. Uh this is all our like internal dev tooling stuff. And then it got to work. And I was looking at the time stamps earlier and I think 10:40 10:51 started the implementation and then another 10 minutes later it replies with a pull request link and a preview URL because we like we do the um like preview environment stuff and uh it like built the entire thing and if I switch actually over to here's the pull requests it built like the entire thing and it was like here's how I tested it and this this was actually the coolest part to me is like it actually uploaded screenshots of it doing its own like UI verification and there was like a CI failure in it. So I was like, "Hey, I replied down here like, oh yeah, this part of this code change, I was like, I don't know what is going on here. This doesn't make sense. There's some type check things." And it was like, "Cool. Here's why we did this change." And I fixed your types.

>> And then there was a merge conflict.

>> Let Let's also talk about just old world, new world. The emotions around code review.

>> Uhhuh. Like I love that you're like I don't get this. Not I'm gonna try to get it or I've done my best to investigate and I'm pretty sure this is wrong. Like literally just I don't get it.

>> I don't get it. Fix. Imagine like send sending that to somebody.

>> One of your human teammates be like no look it up. It makes it so that's one of my one of my code review mechanisms as well is I'm just like I don't think this is right.

>> I Yeah. One one one uh line that I've been putting in my prompts lately is I'm like, I literally don't know what I'm doing here. You need to explain this to me. Especially doing all this CI stuff. I'm like, I'm in over my head. Like you gota you got to like explain it like I'm a 5-year-old. And sometimes it's like literally like caveman style. Like here are the things. And I'm like I needed this. Well, what I appreciate about this, and we'll talk about it in in a little bit later, I think, is we're not getting any of these Claude code warm fuzzies from Codeex. It I love it,

>> but when it talks to me, I'm like, I feel real dumb when you're talking to me, Codex. Can you

>> like, okay, okay, dum dum, here's what's going on.

>> So, I think that sort of like, I don't understand what I'm doing. Please explain it to me. is I love it but I think it is a a codec specific experience that you get. Claude code shows up and it's like hey buddy guess what I made for you. Okay. So stepping back before we go too deep on the personalities of all these coding models you have built just at mention and I think people missed this but it's important for particularly our engineering team and engineering leader listeners to pay attention to which is everybody they know that's smart it has some background agent hooked up to a virtual machine that they kick off so that you're not spinning up your local environment and doing all this stuff on your machine. Um, yeah,

>> and it just I think the velo we'll we'll talk about this, but the velocity plus your DevX plus your CI is

>> a huge piece of AI adoption in engineering. So, if you are not if you don't have a like VM strategy and background agent strategy in your large engineering org time time to get one time to do it and we'll just ask codeex to build it like I don't know how to I don't know what I'm talking about, but I think I think this is Claire said this was a good idea. Please build. Make make no mistake. Um, okay. Last last one. We have a last use case you were gonna you were going to walk us through.

</details>

### 规范即真理：工程师角色演进与CI加速的重要性

Ryan阐述了**规范驱动开发**（Spec-Driven Development: 以详细规范为起点，驱动代码生成和验证的开发模式）的核心理念：不再以代码为起点，而是从详细的规范文档开始。这些**规范文档**（Spec File: 详细描述软件功能、设计和行为的文档）作为代码库中的“真相来源”（**Source of Truth**: 某一数据或信息的权威且唯一的来源），并通过版本控制追踪其演变。

这种模式下，**AI代理**（AI Agent: 能够理解环境、自主行动以达成目标的AI程序）根据规范自动生成代码，并通过内置的**验证流程**（Verification Loop: 验证系统或功能是否符合预期的循环过程）确保代码的正确性。工程师的角色也随之演变为**系统思考者**（Systems Thinkers）和**架构师**，专注于定义行为、设计架构和验证方案，而非底层的代码实现。他指出，过去工程师同样需要编写技术设计文档和规范，并在会议中辩论实现方案，但最终仍需手动编写代码。现在，AI接管了编码工作，人类的注意力则转向更高层次的设计和验证，这并未增加工作量，而是转移了工作重心。

他强调，快速的**持续集成**（Continuous Integration, CI: 开发者频繁地将代码集成到共享主干，并通过自动化测试验证）管道对于AI时代的工程至关重要。CI速度越快，开发者获得反馈信号越及时，迭代周期越短，也越能激发工程师的创新意愿和行动力。AI代理永不疲倦，可在**虚拟机**（Virtual Machine, VM: 模拟计算机系统，可在其中运行操作系统或应用）中不间断工作。如果CI耗时过长，AI代理也会空转等待结果，严重影响效率。因此，将CI时间从数小时缩短到几分钟，将极大地提升人类工程师和AI代理的整体吞吐量。Claire Vo强调，快速CI是AI在工程领域实现价值的关键，慢速CI将成为AI赋能的数学极限，工程领导者应优先投入资源优化CI流程，因为这既有利于AI，也极大地改善了人类工程师的工作体验，减少了等待的痛苦。

<details>
<summary>Original English Source</summary>

>> Yeah. So, we recently rebuilt our entire agent harness. The quick TLDDR is just like everybody else. We reached like this point of tool and instruction fatigue. We had this bloated system prompt. So, we're like, "Okay, we need to dumb this down." And we borrowed the the kind of like skills and progressive disclosure concept from coding agents and brought that to notion AI. And when we were doing this big rewrite, we were asking ourselves like, you know, it had only been like six months since we shipped the last rewrite. And this time we were like, what would what would we do differently? like seeing the state-of-the-art with coding agents and someone had this really great idea to like let's not start with code like let's just start with specs and what we've ended up building um is we have this like in our checked into our codebase you see this we have this we're looking at this is a notion repo but we have this agent specs subfolder and within this subfolder we have all of these markdown documents this is one that that I worked on uh we have this thing in our uh AI called ask mode where we basically um ban all the like mutating tools so it can only just like read and answer questions and so when I was building this I didn't start with writing code I didn't start with anything I just started with an empty markdown document and uh I mean I actually just opened up like whisper and just started yapping about how this feature should work and at the end of it I gave that I gave the YAP session to codeex and was like here's our other like spec library learn the format take my information write a spec and then it spiked the first version I did a couple uh revisions on it and I ended up with this markdown document now the markdown document is like it's nice but what we did with it next in my opinion is is I I kind of think that this is like the future of software engineering where I then opened up codeex again, pointed it at this spec file, and I said, "Build it." And it basically oneshotted this because the entire spec file is so comprehensive with code pointers with um down at the bottom we have verification. You It was like, "Here is how you're going to verify all of this stuff works." And we've even built our own um CLI tools so that you can run Notion AI from the CLI and it could once it's done seeing that all the tests pass, it can actually just spin up notion AI itself, send it queries, send it questions, enable ask mode, disable ask mode, and then see the transcripts and like see what actually happens. And I think the first shot of this took a couple hours, but I came back to whatever couple thousand lines, did some code review, played with it myself, and I was like, it's right. It's like done. And you know, since then, we've made I can The other beauty of this is like this is in version control. So I can go to the past changes of this spec file and I can see how the the spec has evolved. And I it I could go look through all the code changes which also have their own like history but this is now the sort of like source of truth for how this part of notion AI works and it's just in plain English that can then be verified and implemented by agents.

>> Well I think the other thing that people don't appreciate is you know taking this outside of the engineering flow is this plain English can be ingested by other parts of the business that need this information. So let's say you need to then release this feature via some sort of marketing. This is actually like a pretty good asset that explains how it works that can be translated into another another thing in a way that like code itself

>> is still a little intractable. And so this idea of spec driven development, but what I like about what you said I don't want people to miss is the way you make these updates is you update the spec and go go look make the make the update change the thing.

>> Exactly.

>> Um and so like the spec is the source of truth. The spec as the the change log I think is a really interesting model and for people that aren't watching it's very detailed. It's very technical. So, it's not like there is not code in the spec.

>> There's just not all the code in in the spec.

>> And I think that's uh a really kind of good hybrid model for experienced engineers to start to bridge into what would it look like to have an agent do more of your coding work while you still do architecture work, while you still do design work, while you still make sure that the thing is going to scale.

>> Yeah, exactly. I I view our job as like engineers evolving into like systems thinkers and architects and not and not even just necessarily writing like the spec and thinking about the behaviors but most importantly is like the verification loop like is it a like how should it verify correctness of this feature um or this change and honestly it's like if it can't or if like the verification's a little hazy it's like that's the first thing you should be going and doing is like do you have a tool to let the agent uh run itself? That's like one of the first things we did with this project was like we we should actually build a CLI so that I can tell Codeex like send this prompt and like see what happens. And now that we have that then we can take these specs and actually just like go deeper and deeper and deeper. And so it's like we're still doing engineering it but I'm not doing the like plumbing work of like wiring up this ask mode feature. Well, and what I think is really funny is me, I've been in software engineering for 20 plus years. Like we were writing these documents anyways. We were writing technical design documents, spec documents anyway. And we were sitting in meetings with other engineers debating the merits of one implementation versus another

>> and then we still had to go write the code. So, yep.

>> It has like really it it hasn't added work to to go into this model. It's maybe like shifted the emphasis of where the human attention goes. But these were documents that at least I was in every org that I've ever been in writing before. And the other thing that I think has changed so much is those meet those docs then waited for review and they waited for a meeting and now no more waiting for the meeting. No more waiting for review. Ship it. Have a verification loop. debated on the merits of it being live and working versus the theoretical merits of it sitting in a document waiting for everybody's calendar to open up for an you know a live argument.

>> Yep. Yep. Couldn't agree more.

</details>

### AI交互策略与未来展望

Ryan分享了他的**AI提示策略**（Prompting Strategy: 与AI模型交互以获取预期结果的方法）：当AI未能理解或“脱轨”时，他会要求AI**为其论点辩护**，提供有力的证据和理由，而非仅仅接受AI的输出。这种“解释给我听，就像我五岁一样”的提问方式，能有效引导AI提供更清晰、更基础的解释，尤其在处理不熟悉的领域（如CI配置）时非常有用。他提到，这种严谨的交互方式有助于在与AI协作时获得更可靠的产出，并强调了AI在**代码审查**（Code Review: 开发者之间相互检查代码，确保质量和发现问题）方面的强大能力，能够进行代码审查和**安全审查**（Security Review: 评估软件安全性，发现潜在漏洞），并且不知疲倦、从不抱怨。Claire Vo补充道，AI能够处理最繁琐的任务，是日常工作的“驱动器”之一，极大地减少了“劳役”（**Toil**: 耗时、重复、无价值的手动工作），提升了工作满意度。

最后，两人总结了AI在工程领域的三个核心应用：
1.  **自动化会议准备**：整合多源数据，提供高质量的站会预读，消除会议准备的痛苦。
2.  **背景代理代码生成**：通过Notion任务触发**虚拟机**（Virtual Machine, VM: 模拟计算机系统，可在其中运行操作系统或应用）中的AI代理，快速完成代码修复和功能开发，并生成**拉取请求**（Pull Request, PR: 软件开发中请求将代码合并到主分支的操作）。
3.  **规范驱动开发**：将详细规范作为代码实现的“真相来源”，由AI代理负责代码生成和验证，工程师则专注于架构设计和高级验证。
他们一致认为，当前是**硬技能的时代**，工程领导者乃至CFO、CTO都应该学习编码、自动化以及如何利用AI工具和模型，以适应新的工作范式。

<details>
<summary>Original English Source</summary>

>> Let's let's do it. Uh this is what my I I just you and I could talk all day about this. Just to recap for everybody because I know I got to get you out of here. Three use cases. One, never prep for a meeting again. and hook it up not only to your Slack but to your meeting notes, your GitHub, your telemetry and build the best standup meeting so no one has to stand there glassy eyed being boring giving updates. Second use case, background agents, at mention from wherever you work, notion being a great place to do that, kicking off virtual machines, getting PRs done, just saying yes when your friend texts you, can you ship this feature? And then the last one, putting all your specs in your repo, using them as a source of truth for a more autonomous coding agent like Codeex. Let it cook for a couple hours. Review the code and then when you update, update the specs. Don't update the code. Did I get it right?

>> Nailed it.

>> H. Okay, let's do a couple lightning round questions and I'll get get you out of here. You and I love Codeex. Why why you love Codex? I'll tell you why I love Codex, but you go first.

>> Um, okay. I well so I first I first fell in love Oh my god did I just say that you did

>> I first I first fell in love with codeex so because uh when I was like evaluating both like cloud code and codeex um I found anytime cloud code like filled up its context window it would just kind of like lose the plot really quickly and codeex I don't I don't know exactly what it's doing if it's the model if it's the compaction if it's like both. But it can it can grind for like hours. Um and uh with with the way that I work, both the systems and things that I work on and just like I I like to be able to fire off a bunch of them like at the same time and then like go to a meeting or go do something else or like uh spend my time kind of like roundroin managing like all of these agents. It's like I I I don't necessarily want to I'm not the person that is like sitting with the browser open and like um some agent next to it and like iterate look at the browser iterate look at the browser. I'm like the more the closer I can get to oneshotting solutions the better uh because that frees me up to do other stuff. Um and so I found that like Codeex was was pretty good about that. I also just feel it's like pretty simple like it's there's not a lot of bells and whistles. It's not like too fancy necessarily. Um, I'm happy with the addition of like MCP and skills. Um, and some like other stuff coming out. I also really love GPD 54. Um, I think it's a great model. So, I'm like all of those things together, it's just it really like matches my working style uh and type of work a lot.

>> Yeah. I'll I'll tell you why I love Codeex. And I sent this to somebody. I said work trees everywhere. ports three 3000 through 3009 spoken for. Like we're just we're just going across across the board. Um I do think it's fit at longunning tasks. I like its concept of projects because I run a lot of different projects. I think it's just

>> like a very helpful

>> mental model. And then it's great at code review, honestly. Like it's just like a really good code reviewer. It's a really good security reviewer. um tireless, uncomplaining um with the most tedious of things. And so I I find it's one of my daily drivers. I just I really really like it. It's good. Okay. Second question because you and I also agree on this.

>> Give people the reason. This isn't even a question. This is a a demand for you to share my point of view, which is why bang on developer experience and CI speed right now.

>> A couple a couple things. To me, CI was like super important prior to agents. Um, because in my opinion, I mean, it's not even an opinion, it's like fact that like the faster your CI completes, the faster you get signal, um, the faster your like the more comfortable your engineers will feel with like making changes and doing things because they know like I can make a change and get it pushed into dev or into production really quick because I know my CI is fast. If it's slower, then you're building up these like monster changes and you're going to be even slower about like judiciously like reviewing every little like tiny thing when I I'm like a learn through like doing sort of person. And if I can close the iteration loop like even tighter, then I'm going to be putting out a change. People are going to be using it. I will take that feedback. I will make another change and I don't have to worry about um you know it taking another day before like the deploy train is ready to go. I just want to like I want to crank really really fast. And that was all pre-agent. And now that we're like in the agent land, it's it's that but like on steroids because agents don't get tired. They can work on a VM, they can work like while I'm sleeping. And you know, if I'm take if I've got a CI loop that takes an hour to run that, your agent's just going to sit there and spin for like an hour waiting for results to like do something. If it takes three minutes to run, like holy crap, how much more stuff are you you as a human and then especially as your like little swarm of agents going to be able to get done? Like so so much more. Um, and so I super important. I I agree. And we just had Steve from Stripe on and they're doing like 1300 agent PRs a week. You cannot do

>> Yeah. You like cannot do that if your CI is slow. It's just you might as well be throwing all those PRs in the trash.

>> And so I do think there is just a true mathematical limit

>> y

>> on your capacity to ship code to production that is a reflection of how fast your CI pipeline is. And so if you are again engineering leaders, if you are not spending time on making that fast and you are tolerating something slow there, you're not going to get the the benefits of AI that you could. And honestly, like good for AI, good for humans. No engineer wants to sit waiting for their stuff to hit hit production. It's miserable on the engineer side. Lots of downsides. So allocate time to your pipeline, please.

>> Yep. Yep.

>> Ryan Ryan and Claire say so. All right, last question. When AI is not listening, it's writing bad specs. It's not being funny in Slack. What is your prompting strategy? Do you yell?

>> Yeah, I can tell.

>> I can be a little bit of a diva sometimes if it like really goes off the rails though. The the other the other prompting strategy that has like saved my ass working on the CI stuff lately is because like even the best models I feel like can sometimes be a little sick of fantic. I'll be like I will just like be like you're wrong. like you need to defend your argument because I like I want it to defend it in the way that I like I want but I'm like I just need I just need to see the evidence that if I push counter to what it has done that it can like back up with like good pointed reasons rather than just be like are you know are you sure this like change looks okay? It's like oh boy it's like totally fine. I'm like, "No, no, no. I need like the cited hard argument against it." Because like in in a lot of times like with the CI stuff, I'm like, "I don't know what I'm doing. I know generally what I'm doing, but like the specifics are a lot more nuanced and I like I need to get this right." Um, and that's been super helpful. And then when it goes off the rails, I'm like I could be such a diva to it.

>> Escape all caps. No. That's what I do. interrupt and no steer the conversation. Little arrow button has never gotten so much work. Ryan, this was so much fun. Where can we find you and how can we be helpful? Uh, you can find me on X. Um, I'm out there shilling for Notion right now a lot. Um, but that's that's basically where I spend my time. Yeah, I my DMs are open, so if you have notion problems, I like to try and fix them. I you I'll send it to Boxy and we'll get it done. Perfect. Love it. Well, thanks for joining the podcast.

>> Thanks for having me, Claire.

>> Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.
</details>