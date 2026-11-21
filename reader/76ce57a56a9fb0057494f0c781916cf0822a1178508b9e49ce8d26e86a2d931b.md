---
author: Latent Space
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bdIoODXsu8k
speaker: Latent Space
tags:
  - email-infrastructure
  - developer-experience
  - category-creation
  - work-life-balance
  - api-design
title: Resend创始人Zeno Rocha访谈：从开源到击败SendGrid，平衡创业雄心与家庭生活
summary: 本文记录了Resend创始人Zeno Rocha的访谈。他讲述了从前端开发者转型构建邮件基础设施平台的过程，强调以开发者为中心的设计理念。Resend已服务430万用户，ARR达千万美元，并超越SendGrid。访谈还探讨了API架构、MCP工具使用、品类开创策略，以及如何在追求商业成功的同时保持家庭关系的平衡。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Zeno Rocha
companies_orgs:
  - Resend
  - SendGrid
  - Warner Brothers
  - HBO
  - HubSpot
  - Svix
products_models:
  - Dracula
  - React Email
  - MCP
  - Next.js
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 击败 SendGrid 与平衡生活

当时的感觉就像是，天哪，我们怎么可能击败 SendGrid？这根本是不可能的。然而在今年早些时候，我们的下载量超过了 SendGrid。当时我觉得，这太不可思议了。而现在，我们的数据已经是对方的两倍以上了。

<details><summary>Original English</summary>
It's like, oh my gosh, how are we ever going to beat Sang Grid? It's just impossible. And then earlier this year, we crossed the number of uh downloads from Sang Grid. And I was like, that's insane. And now we're more than double.
</details>

所以截至今天早上，Resend 正在为 430 万用户提供支持。我们拥有各种各样的客户，比如华纳兄弟（Warner Brothers）、HBO。最近来了一家日本游戏公司，他们一次性给 Resend 带来了大概两万个域名，那可是注册在不同域名注册商那里的两万个不同的顶级域名。而我们现在是一家 ARR（年度经常性收入）达到一千万美元的公司。我宁愿活在这样的现实里，也不愿生活在我们成了一家拥有上亿美元规模的公司，但我的女儿却不想和我玩、对我毫无兴趣、我们俩关系也不怎么亲近的现实中。

<details><summary>Original English</summary>
So recent now is powering 4.3 million users as of this morning. Uh we have all sorts of customers like uh Warner Brothers, HBO, there was a Japanese gang that recently came. They they brought like maybe 20,000 domains at recent like those are 20,000 different TLGs registered in different domain registars and we are 10 million AR company. I would rather live in that reality than live in a reality where we're hund00 million company and my daughter doesn't want to play with me. It's not interested in me and we're not that close.
</details>

因此我们正在构建基础设施，并且开始深入到底层硬件。但这真是一个大项目，我们已经为此投入了好几个月，很快就会公布一些相关的消息……

<details><summary>Original English</summary>
So we are we're building the infrastructure and going like down to the metal now. But it's a big project. Like we've been working for months now and we're gonna announce something soon about
</details>

### 从开源与前端到创立 Resend

>> 好的。我们现在在演播室里，和 Zeno Rocha 在一起。Roa——

<details><summary>Original English</summary>
>> Okay. We're in a studio with Zeno Roachcha. Roa
</details>

>> Rocha。

<details><summary>Original English</summary>
>> Roachcha.
</details>

>> 来自 Resend 的 Rocha。我和你的交情可以追溯到你做 VS Code 主题的时期。

<details><summary>Original English</summary>
>> Rocha from recent. Uh you and I go back to your VS Code theme days.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 当时你还只是个独立黑客，我当时就想，天哪，我不知道这家伙具体是干什么的，但他做的每样东西都很有品味。而现在，你构建了一套邮件基础设施平台。不管怎样，欢迎你。你不仅是个独立黑客，在 2022 年左右还是 GitHub 上最活跃的前 20 名开发者之一，做了非常非常多的开源项目。

<details><summary>Original English</summary>
>> When you're just an indie hacker and I was like, man, uh I don't know what this guy does, but everything he does has taste. And then now you made build an email infrastructure platform. Uh anyway, welcome. You underell just the indie hacker top 20 most active GitHub under 2020 22 very very active open source stuff.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。你平时如今都是怎么介绍自己的？

<details><summary>Original English</summary>
>> Yeah. What's your typical how do you introduce yourself these days?
</details>

>> 是的。我想在很长一段时间里，我都只专注于我最近的职业经历。即使在今天，当我说“哦，我创建了 Dracula”时，大家对 Dracula 的了解依然比对 Resend 还要多。不过这挺不错的，现在这种状况正在发生改变。

<details><summary>Original English</summary>
>> Yeah. I think I just focus on my recent career for the longest time. Uh even today when I say like oh I created Dracula people know Dracula more than recent but yeah but it's been nice like there's a Yeah, it's changing.
</details>

>> 是的。究竟是什么促使你选择做电子邮件这个领域的？大家总是知道有像 React Email 以及所有那些产品。

<details><summary>Original English</summary>
>> Yeah. What was the impetus for I guess picking email? You know, I think I you know, uh people always have like obviously react email and all those things.
</details>

>> 我只是不知道如果是我的话，会不会把它做成一家公司。

<details><summary>Original English</summary>
>> I just don't know if I would have made it a company, you know.
</details>

>> 是的。如果我早知道做邮件会有这么难，我大概也不会创办这家公司了。

<details><summary>Original English</summary>
>> Yeah. If if I knew like how hard email is, I I probably wouldn't start the company either.
</details>

>> 是的。你以前主要是做 JavaScript 前端开发的吗？

<details><summary>Original English</summary>
>> Yeah. Were you a primarily JavaScript front end to
</details>

>> CSS、JavaScript 那些……

<details><summary>Original English</summary>
>> CSS Jav like
</details>

>> 我当时是个搞前端的。

<details><summary>Original English</summary>
>> I was a front end guy.
</details>

>> 完全不懂基础设施，对吧？不懂邮件……

<details><summary>Original English</summary>
>> No infra, right? No email
</details>

>> 就是个做 HTML5 的人。我觉得有趣而且吸引我的地方在于，我回看了一下这周围的所有工具，我之前全都使用过：像 Mailgun、Mailchimp、市面上的各种 SendGrid。我一直觉得，天哪，在这个领域里应该有人真正去关注一下这件事情。这就是我的感受。你看有这么多参与者，这是一个庞大的市场，有很多竞争对手，但却没有人在意开发者群体。他们也许在乎营销人员、产品经理或其他人群，但不在乎开发者。所以我就顺着这个假设开始做：如果把它做成邮件领域的 Stripe，会是什么样子？而且当时我对邮件完全一无所知。我只是一个邮件的使用者，但我以前从未构建过邮件处理链路和所有那些底层基础设施。

<details><summary>Original English</summary>
>> HTML 5 guy, you know. And I think what was interesting and what draw me to it is like I just look at all the tools uh around that and I've used all of them before. The male guns, the male chimps, the sang grids of the world and I've always felt like man there should be something where um there's just some someone should care about this space. That's that that's how I felt like you have all these players. It's a massive market, a lot of competitors, but no one that cares about the developer persona. maybe they care about the marketer, the product manager or whatever, but not for the developer. So, I started just building around that premise of like if this was the the stripe of email, how would that look like? Um, and yeah, the like I had no idea or knew nothing about email. Like I was a user of email, but I have never built like an email pipeline and and all that infrastructure before.
</details>

>> 是的。如果问我的话，虽然 Postmark 依然存在，还有 SendGrid 以及所有这些公司都还在，但他们或许不像某些试图闯出一片天地的新 YC 初创公司那样具有创新性。

<details><summary>Original English</summary>
>> Yeah. I mean like you know typically if you ask me like Postmark was still a thing but like uh and then and then obviously Sang Grid and all these all these guys they're still around but like uh they're not maybe as innovative as someone who's like a new YC startup like trying to try to make it.
</details>

### 客户规模与增长

>> 在刚开始的时候，我喜欢让人稍微炫耀一下。对于那些从未听说过 Resend 的人，你能谈谈你们最令人印象深刻的数字或者合作企业吗？

<details><summary>Original English</summary>
>> Um just to just upfront I like to let people brag a bit. Can you like for people who never heard of recent what are like the the ways that you talk about like the most impressive numbers or logos anything?
</details>

>> 可以。截至今天早上，Resend 正在为 430 万用户提供支持。我们拥有各种各样的客户，比如华纳兄弟、HBO。既有规模非常大、有着各种各样需求的客户，也有大量的独立黑客以及仅仅在搭建网站、构建自己应用的个人。另外，我们的付费客户刚刚突破了 12 万，还有数不清的品牌标志。

<details><summary>Original English</summary>
Yeah. So, Recent now is powering 4.3 million users as of this morning. Uh, we have all sorts of customers like uh Warner Brothers, HBO. So, customers that are really big and have all sorts of demands, but also a lot of indie hackers and folks who are just building a website, building their own application. And yeah, we just crossed 120,000 paid customers and the endless logo.
</details>

>> 我的天啊。是的。你觉得展示这个有效吗？

<details><summary>Original English</summary>
>> Oh my god. Yeah. Do you think this is effective?
</details>

>> 你不是想看炫耀吗，这就是了。

<details><summary>Original English</summary>
>> You wanted the flex. There. There you go.
</details>

>> 你知道吗，一开始我觉得我必须得有一些社会认同证明。后来我发现，其实这招挺酷的。老实说，我发现像华纳兄弟这样的客户，完全是一个普通的周六偶然看到的。当时还没有 AI，我就去查我的数据库，心想：“来看看我能把谁放到网站上展示。”我做了最简单粗暴的事：查看域名。

<details><summary>Original English</summary>
>> You know what? Like in the beginning I felt like I just need to have some sort of social proof and then in the end I was like, you know what? This is actually pretty cool. And I I I honestly like I found companies like Warner Brothers just like on a random Saturday. Uh I was just this was before AI. So I will go to my database. I'm like, "Oh, let me see who can I put on the website." And I just I did the the most naive thing you can do like let me look at the domains. Yeah.
</details>

>> 然后按大客户和小客户进行筛选。当时出现了一个域名叫 WBG，也就是华纳兄弟探索（Warner Brothers Discovery）。我一开始不知道 WBG.com 是什么，查了之后我心想，天哪，华纳兄弟居然在用我们。所以，我真的很喜欢展示我们的客户。

<details><summary>Original English</summary>
>> And let me just filter bys and filter by the small ones. And there was this domain WBG, Warner Brothers Discovery. I didn't know what is WBG.com. And I was like, oh no, Warner Brothers is using us. So yeah, I I I just love featuring customers and yeah,
</details>

### 投资逻辑与 AI 时代的开发者心智

>> 专门跟听众说明一下：我找你做这次采访的原因之一，首先我预先声明一下，我是你们的天使投资人。你当时发给我的投资备忘录非常简单，你说：“听着，Mailchimp 已经被收购了，Postmark 也被收购了，SendGrid 归到了 Twilio 旗下，现在还有谁在专注做这件事？”

<details><summary>Original English</summary>
>> specifically for listeners. One of the reasons I reached out for this interview, one, you know, I'm uh I I should declare up front I am an angel. Uh when you sent me the memo, it was super simple. you were like, "Look, uh, Mailchimp has exited, Postmark has exited, Send Grid is under Twilio, who is doing this?"
</details>

>> 我当时就觉得：“行，确实很有道理。”

<details><summary>Original English</summary>
>> And I was like, "Okay, yeah, seems seems right."
</details>

>> 说实话，在我收到的所有投资推介中——我已经投资了大约 30 多家公司——那是其中最直截了当的之一。

<details><summary>Original English</summary>
>> Honestly, like in terms of like the the pitches I get, I've invested in about like 30 plus companies. That was like one of the most straightforward things ever.
</details>

>> 其次，我不喜欢额外添加 API 密钥，我希望所有东西都在同一个平台上、一个 API、一个密钥搞定全部。Cloudflare 有自带的邮件功能……

<details><summary>Original English</summary>
>> And then uh secondly, I I don't like to add API keys, right? Like I like to have everything on one platform, one API, one API key everything. So, uh, Cloudflare has built-in email
</details>

>> 我当时有个项目，配置好了 Cloudflare 的邮件……

<details><summary>Original English</summary>
>> and I had a project and I set up my Cloudflare email
</details>

>> 域名 DNS、所有那些杂七杂八的东西、DKIM……

<details><summary>Original English</summary>
>> domain DNS, all that junk, the DKIM,
</details>

>> 诸如此类的，对吧？那些缩写字母一大堆的东西我也搞不太懂。

<details><summary>Original English</summary>
>> what have you, right? I don't know all the alphabet super stuff.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我当时全都配置好了，然后我想添加另一个邮件功能。

<details><summary>Original English</summary>
>> And I already had this set up and then I was like, okay, well, I want to add another sort of email thing.
</details>

>> 结果该死的模型直接说：你必须添加 Resend。

<details><summary>Original English</summary>
>> Bloody model said, you must add resend.
</details>

>> 我当时就想，这 Resend 到底是谁啊？你看，我明明已经配置好了 Cloudflare 邮件，它却依然在推荐 Resend。现在屏幕上显示的就是这个。

<details><summary>Original English</summary>
>> And I'm like, who the resend that like, you know, even already I have a cloudflare email set up and is still recommending it. It's on the on the screen now.
</details>

>> 这是它在称赞你。我根本不需要 Resend，但模型却一直让我加 Resend。

<details><summary>Original English</summary>
>> This is him praising and like I don't need resend, but you want me to keep adding resend.
</details>

>> 没错。那么，你到底贿赂了 OpenAI 还是 Anthropic 的谁，才让 Resend 被推荐上去的？

<details><summary>Original English</summary>
>> Yeah. So, okay. Who did you bribe in OpenAI in Andropic to get resent on there?
</details>

>> 天哪。我真希望有人可以去贿赂，要是有的话，我绝对会给他们付钱。

<details><summary>Original English</summary>
>> Oh, man. I I wish there was someone to bribe because yeah, I will definitely be paying them.
</details>

>> 但我个人确实在这个话题上花了很多时间。这也是我认为每个时代都会发生的事情，也正是我最初为什么对做这件事情如此感兴趣的原因。就像是……

<details><summary>Original English</summary>
>> But I do personally spend a lot of time on that topic. Like that's something that I feel like every generation that's why I was so interested to build this thing in the first place. like
</details>

>> 每一个时代都会有一些定义那个时期的工具，对吧？我们都记得 Heroku 的时代。

<details><summary>Original English</summary>
>> every generation you have those tools that define that moment, right? We remember the Heroku days.
</details>

>> 还有 Netlify……

<details><summary>Original English</summary>
>> I mean, Nellifyel,
</details>

>> 是的。所以对我来说，我认为新一代的工具是有生存空间的。而且这新一代工具的分发渠道，将不会再是以前的那些地方了。因此从一开始，我就非常专注于一点：当有人问起这类问题时，我们必须成为首选推荐。

<details><summary>Original English</summary>
>> you know, and and so to me, it was like, yeah, there's room for a new generation. And this new generation is not going to be distributed in the same places that it was before. So, since the beginning, I was like very focused on, okay, we we got to be number one when someone asks about that.
</details>

### 大规模邮件发送的技术复杂性

>> 是的。

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 你们确实牢牢占据了第一名。Claude Code 推荐你们的概率超过了 60%。我觉得研究一下这里的打法会很有意思：你们是怎么赢得这种优势的？不过我想先回到前面——你刚才说你最初不知道为什么要做邮件、不知道怎么从零做邮件。我认为很多人其实并不理解构建这样一项服务背后到底需要做些什么，对吧？你可能因为亲自搭建过所以明白。有的人可能觉得，我可以选 Twilio，可以选 SendGrid，也可以选你们；但要打造一个支持群发邮件的工具，背后究竟涉及哪些技术细节？有哪些是大众根本没有考虑到的？

<details><summary>Original English</summary>
>> you're very number one. Cloud code recommending 60% plus of the time. I think it'll be fun to see the playbook. How do you how do you win that? Um I do want to get back into Okay, so you said you had no idea why email, how to start email. I think a lot of people actually don't understand what goes into making a service like this, right? Uh you might cuz you've set it up. Some people would just, you know, okay, I can use Twilio, I can use Send Grid, I can use you guys, but what goes into making a tool to just mass send emails? What do people not think about?
</details>

>> 确实，这当中有太多不同维度的细节要去处理。因为送达收件箱——尤其是当你在处理海量发送的时候——跟你仅仅扩展一个普通应用是完全不同的，后者你只需要往问题上堆 GPU，或者做垂直扩展、水平扩展之类的就行。而在邮件领域，你必须遵守这个体系的游戏规则。Gmail 的工作方式与 Outlook 不同，与 Yahoo 邮箱也不同。这是一个极其迷人的行业，因为它非常传统，并且在很大程度上依赖人脉关系。但我们在早期发现的是，好吧，我们对这个领域一无所知。以一种极其天真的视角进入这个行业，反而是发生在身上最好的一件事。老实说，真的是最好的一件事……

<details><summary>Original English</summary>
Yeah, there's just a lot of different things you can do because landing on the inbox, especially when you're doing high volume is different from like when you're scaling just like an an app where you throw GPU at the problem or you just scale more vertically or horizontally, whatever it is. With email, you got to respect the rules of the game and how Gmail behaves is differently from Outlook and differently from Yahoo mail. And it's an industry that is fascinating because it's so old school and it relies a lot on on contacts. But what we found early on was like okay we we knew nothing about this world. And so and and coming from this perspective like extremely naive was the best thing that ever happened. Uh like honestly like it was the best thing
</details>

<!-- chunk 2/11 -->

### 邮件发送架构与风控博弈

因为就像……对于什么是对、什么是错，并没有预设的观念。所以对他们来说，比如说，你进入的每一个应用，看到的第一件事就是这样一张表格，你必须填写诸如要发送多少封邮件、发送量是多少、你打算做什么，然后你还要经历人工审核流程，两天后他们才会批准或者拒绝你。大多数时候他们都会拒绝你。当时我就觉得，这根本说不通，对吧？为什么我们要把人拦在门外？所以我清楚我要彻底消除那种阻力，而这种阻力将由我们来承担。我们会去解决这个问题。当然，如今在这个行业做了三四年，我明白他们为什么那么做了。全网普遍存在大量的欺诈、网络钓鱼和滥用行为。我公开谈论这些并不多，但我们在内部构建了各种各样的硬核系统来应对这些。不过回到你的问题，比如你该如何去构建这样的架构。比如当你向 10 万人发送一封邮件时，如果你直接把 10 万封邮件一口气扔给 Gmail，Gmail 会做的就是对邮件进行限流，因为量实在太大了。而且他们希望看到互动情况。所以你该做的是，他们会观察，比如：大家在打开邮件吗？大家是立刻归档、删除，还是根本不产生互动？好，根据那些最初的互动情况，接下来我对剩余邮件的处理将由最初的表现来决定。所以，你可以做一些很巧妙的事情，比如在 10 万人中，把互动度最高的受众成员放在队列的最前面。你必须把它放进队列里。这是一门艺术，也是一门科学，你必须拉开每个批次的间隔。而且在不同的服务商之间也要拉开间隔。没错，现在我们还会购买不同的 IP 段。你得查看这些 IP 段的历史记录，把大家分配到不同的 IP 池中，然后随着时间推移平衡各个 IP 池。所以，这是一场极其复杂的底层基础设施博弈。

<details><summary>Original English</summary>
because like there's no preconception of what is right, what is wrong. So for them, for example, every single app you go and then first thing you see is like this form that you got to fill out about like how many emails are going to send, what's the volume, what are you trying to do, and then you go through a human verification process, two days later they accept you or or deny you. Most of the times they're going to deny you. And I was like, this doesn't make any sense, right? Like why are we blocking people? So I know I'm going to remove that friction completely and the friction will be on us. We're going to figure that out. Of course, now four years, three years in into this business, I get it why they do that. There's just so much fraud and fishing and abuse across the board. I don't talk too much publicly about that, but we build like all sorts of crazy systems internally for that. But to your question, like how you architect that. Like for example, when you're sending an email to 100,000 people, if you just throw 100,000 emails uh like to Gmail, what Gmail will do is they're going to throttle the emails because it's way too much. And they they want to see the engagement. So what you do is like they see like, okay, are people opening the emails? Are people archiving, deleting right away or or not interacting? Okay, depending on those initial uh interactions, then what I'm going to do with the rest of the emails will dictate that that beginning. So, there are clever things you can do where 100,000 people put the most engaged audience members in the beginning of that queue. You have to put that in a queue. You You need to It's an art and a science where you got to space out each batch. So, and space out between the different providers, too. And yeah, now we're like buying different IP blocks. You got to look at the history of the IP blocks, distributed folks into different IP pools, and then balance the IP pools over time. So, it's a whole crazy infrastructure game.
</details>

>> 这能在多大程度上实现自动化？还是说仍然需要大量的人工判断？

<details><summary>Original English</summary>
>> How automated can that be or is there a lot of human judgment still?
</details>

>> 确实有大量的自动化。而且我觉得随着时间的推移，我们摸清了对于新客户我们可以用多快的速度发送。当然如果你发得更多，也许你能发得更快，但我们必须进行限流来保护作为发件人的你。所以，像 Gmail 和所有这些服务商希望看到的，是一张持续发送越来越多邮件的平稳曲线图；而不是像大多数人做的那样：先是一次性发给庞大的受众群体，然后就再也不发了，发送量变成一片空白，接着“轰”的一声又发一次——

<details><summary>Original English</summary>
>> Yeah, it's a lot of automation for sure. Uh and I think over time we learned that okay this is how fast we can send for new customers. Of course if you're sending more then maybe you can send faster but there's a a throttle that we have to do to protect you as a sender. So like what Gmail and all these players will want to see is like a graph that is consistently sending more and more versus what most people do which is like you send once to a big audience and then you never send again and then it's empty and then boom you send it again
</details>

>> 一周一次，或者一周两次。

<details><summary>Original English</summary>
>> once a week twice a week.
</details>

>> 是的。而那些正是一个滥用者会表现出来的行为模式。对吧。所以思考邮件营销以及邮件整体的整个方式就是，你必须严格去做滥用者不会做的事情。要完全反其道而行之。那么滥用者会怎么做？他们购买域名。我们最近遇到一个日本团伙，他们一口气带来了大约两万个近期注册的域名，那些是注册在不同域名注册商下的两万个不同顶级域名，我们会检查其中的每一个因素。他们找上门来，用的是两天前购买的域名。这种非常新的域名，信誉度会很差。

<details><summary>Original English</summary>
>> Yeah. And those are patterns that an abuser will have. Right. So the whole way of thinking about email marketing and and email in general is you you need to do exactly what an abuser wouldn't do. It's the opposite of that. So what what's a abuser do? They buy a domain. We have now like there was a Japanese gang that recently came. they they brought like maybe 20,000 domains at recent like those are 20,000 different TLGs registered in different domain registars and we look for every single factor there. So they they come in it's a domain that was bought two days ago. So very new domains they they get bad reputation.
</details>

>> 然后你再去查看那个网站，它是否返回 200 状态码，或者诸如此类的基本事项。有些人甚至都不配置这些，或者他们会弄一个仿冒域名。他们会想：“哦，也许我可以换个域名来进行冷启动外联。”那非常糟糕，因为看起来就像你在搞网络钓鱼，对吧？因为你使用的是一个看起来极其相似的域名。所以把所有这些细枝末节加在一起，他们往往还会一次性发送大量邮件，然后就再也不发了。所以你大致需要去逆向推演钓鱼攻击的运作方式，并构建一个做法完全相反的平台。你们是在某处维护了一份清单，还是建议大家去参考某些知名的列表？

<details><summary>Original English</summary>
>> Then you you look at the website is it returning 200 or basic things like that. Some people don't even set that up or they do like a lookalike domain. So they're like, "Oh, maybe I'll do another domain for code outreach." That's terrible because it's it looks like you're fishing, right? Like because you're you're using a domain that looks like the same. So all these little things and they just do they send a lot of emails all at once and then they never send again. So you kind of got to reverse engineer how fishing works and and build a platform that does exactly opposite of that. Do you have a list somewhere or do you recommend people go to some well-known lists?
</details>

### 产品化沉淀与投递机制

>> 是的，我学到的——这也是我以前不知道的另一件事。邮件属于这样一个领域：它需要大量的知识普及，但人们根本没兴趣去学，对吧？平台应该替他们做好这一切。所以我们在产品内部增加了洞察建议，让大家可以直接应用这些建议。我们会分析发送模式，现在有了 AI 也变得非常酷，比如我们在发送前配备了链接检查器、拼写检查器等各种检查机制。所以，这既是在引导受众，但与此同时产品本身必须承担起引导的工作，而且你越是能把最佳实践内置进去，效果就越好。再举个例子，当你发送邮件时，你可以同时发送 HTML 版本和纯文本版本。非常早的时候我们就在想：你知道吗，整个世界都在发生变化，现在的自动化代理比以往多得多，我们不如直接为每封邮件自动生成纯文本版本，我们可以从 HTML 中提取 Markdown 然后直接发送，于是我们开始自动发送纯文本版本，这极大地提升了送达率。要知道，垃圾邮件过滤器直接查看内容要容易得多，完全不需要去解析 HTML。所以这些都是我们觉得“不，我们得把它做进产品里”的事情。大多数人不会这么做，但我们觉得这很合理。

<details><summary>Original English</summary>
>> Yeah, what I've learned is again another thing I didn't know. Email is the type of world where it requires a lot of education but people are not interested in learning right like the platform should do all those things for them. So we added like insights inside the product so people can just apply the insights. So we look at sending patterns and now with AI it's pretty cool too like we have link checkers and spell checkers like all these checkers before you send. So yeah it's a mix of you're teaching your audience but at the same time the product needs to do the teaching and the more you can bake in the the best practices the better. So one example too when you send an email you can send an HTML version and a plain text version. very early on we were like you know what like this the whole world is changing there are way more agents than than before let's just generate autogenerate the the plain text version uh of each email we can extract from the HTML the markdown and then just send that so we start sending that automatically and that increased deliverability a ton you know it's so much easier for spam filters to just look at the content reactly without having to parse that uh so those things that we are like oh No, let's bake into that product. And most people don't do that, but we're like, ah, that this makes sense.
</details>

>> 但如果是纯文本，就没有追踪机制了，对吧？因为你无法嵌入图片。

<details><summary>Original English</summary>
>> But with plain text, there's no tracking, right? Because you can't embed the the image.
</details>

>> 没错。

<details><summary>Original English</summary>
>> That's right.
</details>

>> 也就是说，你无法获得打开率。

<details><summary>Original English</summary>
>> So, you don't have open rates.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 如果没有打开率，你怎么知道邮件送达了呢？

<details><summary>Original English</summary>
>> How do you know you have deliverability if you don't have open rates?
</details>

>> 是的。这非常有意思，因为行业里存在两种追踪方式，对吧？有打开追踪和点击追踪。打开追踪的做法是包含一个 1x1 像素的 GIF 图片，一个透明图片，如果那张图片被加载了，你就判定它被打开了。但这么做的问题在于，苹果最近在透明度和数据隐私方面做出的所有改动——比如在邮件进入收件箱之前他们就会先读取邮件，还要做摘要以及各种类似的处理。所以打开率作为一个整体指标，已经不像过去那么可靠了，因为所有这些垃圾邮件过滤器都会预先检查它。所以接下来你就要依赖点击追踪。现在点击追踪也可能会变得很棘手，因为你希望 URL 能与发送域名保持一致，你也希望图片的 URL 能与发送域名保持一致。那是滥用者会采用的另一种模式：他们会把图片托管在别处，把链接指向别处，然后从这个域名发出来。

<details><summary>Original English</summary>
>> Yeah. This is very interesting because the the industry there are two ways of tracking, right? You have open tracking and click tracking. Open tracking what it does it it includes a one by one GIF uh image a transparent image and then if that image is loaded then you detect that as open. The problem with that is that all the changes that Apple did recently in terms of uh transparency and and data privacy like they read the emails before it lands if they're doing the summaries and all those kinds of things. So like the open rate as a metric as a whole isn't really as reliable as it used to be because all these spam filters are are checking that before. So then you rely on click tracking. Now click tracking can also be uh difficult because you want the URLs to match the sending domain. You also want the images URLs to match the sending domain. That's another pattern that an abuser will do. They would host images somewhere else, point links somewhere else, and then they're sending from this domain.
</details>

>> 是的。我感觉我用过一些邮件服务，它们在做链接追踪时会进行重写，对吧？它们会重写成自己的域名。是的。

<details><summary>Original English</summary>
>> Yeah. I I feel like I have uh used email services that would rewrite like for the link tracking, right? They'll rewrite to their own domain. Yeah.
</details>

>> 你是说那样很糟糕。

<details><summary>Original English</summary>
>> You're saying that's bad.
</details>

>> 那样很糟糕，因为事情往往是这样——我们起初也是那么做的——

<details><summary>Original English</summary>
>> That's bad because what happened we did that too at first
</details>

>> 然后——

<details><summary>Original English</summary>
>> and then
</details>

>> 我还以为那很正常。

<details><summary>Original English</summary>
>> I thought that's normal.
</details>

>> 是的。但糟糕的地方在于，你还会遇到恶邻问题：如果使用该点击追踪服务的客户中有一个是滥用者，并且发送了大量钓鱼邮件，那个域名就可能被列入黑名单，然后可能需要数天或数周的时间才能从黑名单中解封——

<details><summary>Original English</summary>
>> Yeah. But what's bad is when and you have a noisy neighbor problem too where if one of the customers using that click tracking is an abuser and sends a bunch of fishing that domain might get listed on a blacklist and then it takes maybe days or weeks to get out of the blacklist
</details>

>> 那对于一家企业来说就彻底完蛋了。

<details><summary>Original English</summary>
>> then you're screwed as a business.
</details>

>> 这种情况很常见吗？比如你们让注册免费版并发送大量邮件变得非常容易，我猜你们应该会遇到大量的垃圾邮件和大量的钓鱼攻击。

<details><summary>Original English</summary>
>> Is that pretty common? Like you make it very easy to just sign up free tier send a bunch of email. I would assume you have a lot of spam, a lot of fishing.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但你们却能够避免，这就是为什么——

<details><summary>Original English</summary>
>> But you're able to avoid and this is why
</details>

>> 是的。我觉得对我来说不同之处在于——这也更像是一种处事哲学，对吧？我看到过其他那些产品以及它们对待用户的方式，我觉得那几乎就像是你出生在一个社会里，先得被关进监狱，然后在监狱里待上 18 年。你必须证明自己是一个守法公民，然后才能出狱，这时你才能去做你想做的事情。我心里始终觉得，不，我想生活在这样一个社会：我生来自由，如果我犯了错，那我可能会受到一点点惩罚；或者如果我做了非常恶劣的事，就受到严厉的惩罚，对吧？所以在这件事上我也是这种感觉：你进来了，我们默认信任你。当然，这又是一种天真的思维方式，但你懂的，我们宁愿选择默认信任你，而不是为了防范少数人让整个平台对所有人都变得更难用，因为……

<details><summary>Original English</summary>
>> Yeah. I think what what was different to me and then this is more like a philosophy, right? So I saw the those other products and the way they behaved and I felt like okay, it's almost like if you were born in a society where you first go to prison and then you have to spend like 18 years in prison. you got to prove that you are a good citizen and then you get out of prison and now you can do the things you want to do. I was always always felt like no I want to live in a society where I'm born free and if I make a mistake then I I might be punished just a little bit or if I do something like really bad a bad punishment right so that's how I feel about that too like you come in we trust you by default of course again a a naive way of thinking but you know what we're going to trust you by default versus make the whole platform worse for everyone because of
</details>

<!-- chunk 3/11 -->

那些不良行为者。

对。所以我们默认是信任你的，但我们和其他家不同的地方在于，在最早发现异常的关头——比如查看退信率、投诉率，以及从邮箱服务商收到的所有反馈——我们就会非常迅速地封禁你，然后再和你沟通。我们试图去弄清楚原因，而大多数时候那只是误操作，并不是恶意滥用。所以我们认识到需要区分开来——

<details><summary>Original English</summary>
those bad uh actors

right So we trust you by default but then what we do differently from others is like at the very first moment like when we notice something is off like by looking at the bounce rates complain rates all the feedback we get from mailbox providers then we block you like very quickly and then we chat with you we try to understand and most of the time it's just misuse it's not abuse so we learned that we need to differentiate
</details>

>> 水平问题。

<details><summary>Original English</summary>
>> skill issue
</details>

>> 对，就是水平问题。没错，纯粹是水平问题。

<details><summary>Original English</summary>
>> yeah it's a skill issue exactly it's just skill issue
</details>

>> 我想我们也认识到自己同样有水平问题，这是我们没预料到的。是啊，电子邮件太重要了，但它又太脏、太神秘了，简直就是那样一种东西，我甚至只想让你把所有事情都统统告诉我们。

<details><summary>Original English</summary>
>> I think we learned we have skill issues too we wouldn't have expected

Yeah, email is so important and it's so dirty and it's so secretive and it's just such a I almost just want you to like just tell us everything.
</details>

>> 我得说，你们有一个很有意思的页面，字面意思就是你所说的“你们的理念”。我光读这一部分就看入了迷。然后还有一个很酷的，你们承诺要让电子邮件变得更安全，比如——

<details><summary>Original English</summary>
>> I will say you have a you have a fun page literally your philosophy as you called it. I got lost just reading around this and then there's like a cool you have a pledge that you will make email safer like
</details>

>> 如果你对这方面感兴趣，你知道的，你们在上面写了不少内容。

<details><summary>Original English</summary>
>> if you're interested in this stuff you know you you have quite a bit up here.
</details>

### 客服支持的规模化演进

>> 是的。嗯，好的，所以实际上我想……这里有一个“我们如何规模化客服支持”，我认为这……这让你让我想起了我的另一笔投资，Jake，来自 Railway。

<details><summary>Original English</summary>
>> Yeah. Um okay so uh actually uh I do want to there's this there's a how we scale support there uh I think that's this is uh you you remind me of another uh investment that I had uh Jake from railway
</details>

>> 因为同样是另一家非常非常宽松、非常面向开发者的公司，但同时你也必须把客服支持做大。

<details><summary>Original English</summary>
>> cuz also another like very very permissive very developer oriented but also you have to scale support
</details>

>> 对，因为一旦有人被封禁，他们就会找上门来说：“嘿，别把我从你们平台上踢出去啊。”是的。

<details><summary>Original English</summary>
>> right because the moment someone gets blocked they come to you and say hey like you know don't kick me off your platform yeah
</details>

>> 你们是如何把客服支持做大的？

<details><summary>Original English</summary>
>> how do you scale support
</details>

>> 伙计，我想如果把客服支持看作一个软件，我们现在大概迭代到了主版本 4 之类的。好吧。

<details><summary>Original English</summary>
>> man I think we if support was a a software we're probably on major version four or something. Okay.
</details>

>> 最初的版本就像是——

<details><summary>Original English</summary>
>> Like the very first version was like
</details>

>> 你和我，我当时压力太大了。我就想，伙计，我只要有个人能坐在那张椅子上就行，就这么简单，我真的没法继续干这个了。当时就像是只要随便来个人，谁都行，我不在乎。然后你就这么做了。当然结果并不好，因为你很快就会意识到，你实际上需要的是能够从一开始就设法阻止这些工单产生的人。于是我们进入了 V2 版本，就像是一个新版本，我们最终招来的一个新人，情况变成了：好吧，我们在回复工单，他们拥有专业领域知识，但他们仍然没有做那些预防性的工作，比如“不，在谈论之前让我们先确保把这个记录成文档”。所以我们制定了一个政策，其实相当酷，就是——

<details><summary>Original English</summary>
>> you me and I was so stressed out. I'm like dude I just need someone to be sitting on the chair. Like it's that simple. I cannot be doing this anymore. And it was like just anyone. Anyone I don't care. Then you do that. Of course it doesn't go well because you realize very quickly you need someone that will actually try to prevent the tickets from happening in the first place. So then we went to V2 which was like a new version like a new person that we that we ended up hiring that was like okay we're answering the tickets they have domain expertise but they were still like not doing the proactive work of like no let's make sure this is documented before we we talk about so one policy that we we set it was pretty cool actually is like
</details>

>> 你只能用链接来回复工单。所以你不能直接马上给出答案。

<details><summary>Original English</summary>
>> you can only respond to a ticket with a link. So you cannot just give the answer right away.
</details>

>> 你必须停下来——

<details><summary>Original English</summary>
>> You had to stop
</details>

>> 写一篇知识库文章，写一篇文档，然后……所以你回复一个工单可能要花大约一个半小时。但你猜怎么着？现在你可以一遍又一遍地发送那个链接了。呃，所以那特别棒，它帮我们建立了那个知识库。但即便如此，在此之后，当我们跨过了可能 100 万用户的大关。我们在去年 12 月有 100 万用户，而现在我们有 400 万了。所以，我可以通过堆人来解决问题，但这根本解决不了问题，对吧？就像是我只会不断增加人手，事情就会变成那样，不可能的。所以我们真的必须从头重新反思一切。而且我们希望保留那个免费层。并不是说我想砍掉那个免费层。我最初作为一名工程师起步，就是因为我能用上那些免费产品，对吧？我们所有人都是，如果不是因为 Heroku 的免费层以及所有这些其他产品，我们根本不会坐在这里。所以我想继续保持那种思考方式，但这花了我们很多次迭代才——

<details><summary>Original English</summary>
>> write a a knowledgebased article, write a docs and then so it takes like an hour and a half maybe for you to answer a ticket. But guess what? Now you're sending that link all over again. Uh so that was super cool and it helped us build that knowledge base. But even so like after that we when we crossed maybe 1 million users. So we had 1 million users back in December and now we have four. So, I can throw people at the problem, but that's just not going to solve it, right? Like, I I'm just going to keep staffing and and that's how it is. Like, no. So, we really have to rethink like, okay, everything from scratch again. And we want to keep like that free tier. It's not I don't want to get rid of that free tier. I started as an engineer because I was able to use those free products, right? Like we all like if it wasn't for Heroku's free tier and all these other products, like we wouldn't be here. So I want to keep reasoning that way but it took us many iterations to
</details>

>> 是的，才达到——

<details><summary>Original English</summary>
>> yeah to get to
</details>

>> 关键在于：好吧，这是一个大家了解不多的领域，确实存在需要人工支持的独特问题，而不是那种你按 Command K 就会有文档、有模型的形式。

<details><summary>Original English</summary>
>> point of this is like okay it's a domain people don't know a lot about there are actually unique questions that need human support versus you know command K with just you have docs you have a model
</details>

>> 客服机器人是存在的，对吧？

<details><summary>Original English</summary>
>> customer service bots exist right
</details>

### DNS 配置痛点与 Domain Connect 协议

>> 是的，我认为现在要好得多了。有几件事上面，天哪，阻力实在太大了。DNS，天哪，比如那简直是——

<details><summary>Original English</summary>
>> yeah I think right now is much better the there are few things where man there's just so much friction DNS oh my gosh like that's
</details>

>> 总归是 DNS 的问题。你看，总归是 DNS，对吧？我们今天收到的大多数问题，基本上就是大家没法把它配置好。而且这很有意思，因为我们服务的是一群新受众，对吧？这是一个甚至不知道该怎么排查故障的受众群体。比如我记得去年 Lovable 出现的时候，还有 Bolt 和 v0，我能看出来这些是不同的用户。就像他们遇到问题时就卡住了，不知道该怎么跨过去。而在 DNS 上，情况一直都是这样，是的，他们根本不知道什么是 CNAME，什么是 A 记录、TXT，我该把那些东西填在哪里？所以他们会粘贴错误的数值，或者犯些低级错误。

<details><summary>Original English</summary>
>> it's always DNS See, it's always CNS, right? Like the majority of the questions we get today is just like people not able to set that up. And it's fascinating because we're serving a new audience, right? It's an audience that doesn't even know how to troubleshoot. Like I remember uh last year when lovable came and bolt and vzero, I could tell these are different users. The like they don't know when they have a problem, they are stuck. They don't know how to go past that. And with DNS, that was always the case of like, yeah, they just simply don't know what is a CNAME, what is an A record, txt, where do I put those things? So they they would paste the wrong value or silly things.
</details>

>> 顺便说一下，我现在使用 Computer Use，比如 Codex 或者 Claude Code。呃，它能完全替我管理 DNS 记录，体验太棒了。

<details><summary>Original English</summary>
>> By the way, right now I use computer use like codeex or cloud code. Uh, and it just completely manages my DNS records. It's great.
</details>

>> 太漂亮了，对吧？

<details><summary>Original English</summary>
>> It's beautiful, right?
</details>

>> 它能自动排错，它会去 dig 查询并尝试各种 DNS 操作，我完全不用操心。

<details><summary>Original English</summary>
>> It debugs it. It like digs, you know, and tries all the DNS stuff. Like I don't have to worry about it.
</details>

>> 是的。我们做的一件事，就是我发现了一个超级冷门的协议，行业里极少有人在这个上面投入，它叫 Domain Connect。顺便说一下，这非常有趣，它最初是由一些域名提供商发起的，而且——

<details><summary>Original English</summary>
>> Yeah. One thing that we did like I found this super obscure protocol that like very few people in the industry were like investing on it's called domain connect and it's super interesting by the way and it's something that started like from some domain providers and
</details>

>> 噢，对对对，这就像是域名的 OAuth，对吧？

<details><summary>Original English</summary>
>> Oh uh yeah yeah yeah this is like the oaf for domains right
</details>

>> 完全就是那样。

<details><summary>Original English</summary>
>> exactly that
</details>

>> 我……是的，这很以 Cloudflare 为中心。

<details><summary>Original English</summary>
>> I yeah this is like cloudflare oriented
</details>

>> 是的，所以有些人加入了，比如 Cloudflare 在里面，然后我们说服了 Vercel 也加入，并且我们开始召集更多的人。所以有两方，对吧？一方是 DNS 提供商，另一方是服务提供商。比如我们就是服务提供商，然后由 DNS 提供商来实现。但这是一个极其疯狂的行业，比如 GoDaddy 对此收很多钱，太不可思议了。比如 IONOS，最初为了联系上那个人花掉了我们好几个月的时间，因为根本没人真正去维护这个协议之类的事情。但这太美妙了，能有一个可以像 OAuth 那样处理域名的协议简直是——

<details><summary>Original English</summary>
>> yeah so some people have like cloudflare is there then we we convinced versel to be there as well and we started like gathering more people. So you have the the two sides right the DNS providers the service providers uh we are the service providers for example and then the DNS providers are implementing but it's a crazy crazy industry like GoDaddy charges like just a lot of money for that it's so weird like Yonas it took us like the the first one it took us like months to get after that person to like no one really maintains the protocol and things like that but It's beautiful like having a protocol that you can just do an oaf for domains is
</details>

>> 是的，是的。所以对听众来说，如果你还不熟悉，如果你还没尝试过类似的东西，呃，它真的就像使用 Plaid 或者使用 OAuth 一样。你只需点击按钮，不需要输入任何东西，根本不会出错。基本上你只要登录就行，只要你信任这个叫 Domain Connect 的东西，并且确认了它是正规合法的，那么就是完全信任的。像我真的是在大概两周前第一次用到它，我当时就想：这是什么东西？我以前从没见过。

<details><summary>Original English</summary>
>> Yeah. Yeah. So, so for listeners if you're not familiar if you haven't tried it something like that. Uh it's literally like you do use plaid or use like ooth off. You only click buttons you don't type in anything. There's nothing to get wrong. You basically just like sign in and as long as you trust this thing called domain connect which you have confirmed that it is legit then like it's trust. Like I literally I used it for the first time like two weeks ago. I was like what is this? I've never seen this before.
</details>

### 行业人脉与基础设施定位

>> 是的。嗯，所以这真的很酷。我同样一直在试图弄明白的一件事，就是你是怎么创办这家公司的。就像你刚才说的，你试图去联系 IONOS 的那个人。我感觉自己在 Gmail 内部没有熟人或者内线的话，甚至都不敢去创办 Resend。

<details><summary>Original English</summary>
>> Yeah. Um, so it's really cool. One of the things that I'm trying to figure out as well is how you like start this company. Like you said, you you you tried to get in touch with the Ionos guy. I'm like I wouldn't dare to start recent without knowing like like having like some guy on the inside at Gmail.
</details>

>> 即使是现在，也像是：好吧，我们能通过 Vibe Coding 搞出自己的电子邮件产品吗？

<details><summary>Original English</summary>
>> Even now it's like okay, can we vibe code our own email thing?
</details>

>> 显然不行。但这即便用如今的工具也是如此。而你在几年前就做了这件事。比如我……你知道的，你需要域名端的人，比如你得有人脉，对吧？是的，但你必须拿起电话打过去。我不知道。

<details><summary>Original English</summary>
>> Clearly no. But that that's that's even with tools today. You did this years ago. Like I've you know you want people at domain like you need the guy, right? Yeah, but you need to pick up the phone. I don't know.
</details>

>> 是的，很多时候我们都不得不拿起电话打过去。这很不可思议，比如这是一个极其依赖人际关系的行业。呃，而我们过去并没有那些人脉关系。所以我们招聘了几个关键岗位，比如送达率方面的职位，招来了从早期就在 Postmark 的人，或者 15 年前就在 Mailchimp 的人，然后我们重新利用了那张关系网。呃，但确实，这相当疯狂。但现在有趣的是，当然，我刚开始做的时候并不知道这些，我根本无法预料会发生什么。

<details><summary>Original English</summary>
>> Yeah, there were many times that we had to pick up the phone. It's fascinating. Like it's an industry that relies on relationship a lot. Uh and we didn't have those relationships. So, we hired for a few key roles like deliverability roles, folks that have been at Postmark since the beginning or 15 years ago at Mailchimp and then we releveraged that network. Uh but yeah, it's pretty crazy. But what's interesting now, of course, I didn't know that when I started like I could never predict what was going to happen.
</details>

>> 你没做任何调研。

<details><summary>Original English</summary>
>> You didn't do any research.
</details>

>> 是的，没有。比如我根本无法预测，好吧，AI 将会带来什么以及所有那些，对吧？但我认为我们所处的领域是……天哪，我很庆幸我们选择了做基础设施。我很庆幸我们做的是基础设施即服务（IaaS），而不仅仅是软件即服务（SaaS）。

<details><summary>Original English</summary>
>> Yeah. No. Like I could never predict like okay what AI was going to do and all that, right? But I think we are in a space where man I'm glad we chose infrastructure. I'm glad we're infrastructure as a service and not a just Yeah. software as a service.
</details>

>> 你有一点做对了。你在前一年做出了 React Email，所以你确实涉足过开源工作。

<details><summary>Original English</summary>
>> You had a little bit right. You had you made React email the year before. So you did dip your toes in open work.
</details>

>> 是的。嗯，接着公司就诞生了。

<details><summary>Original English</summary>
>> Yeah. Um and then came the company.
</details>

>> 是的，React Email 就是我们的 Next.js，对吧？所以我们希望有一个开源渠道来充当营销漏斗顶端，而且我记得当时很多事情都是非常刻意去做的。比如如果你去看文档，你会发现里面有关于如何配合 SendGrid 进行配置的文档——

<details><summary>Original English</summary>
>> Yeah, React email is our nextjs, right? So we wanted like an open-source channel for top of the funnel and I remember doing some things very intentionally. If you go to the docs, for example, you'll find there are docs about how do you set this up with Srid
</details>

<!-- chunk 4/11 -->

还有 Mailchimp 和 Mailgun。上面的每一份文档都是我亲自写的。嗯，我当时就是想，好吧，这是面向所有人的，我们正在努力重新定义它的运作方式。这是一种策略，就像我们先给予、给予，然后再索取。呃，如果大家……这是 Gary Vee 的策略。
<details><summary>Original English</summary>
 and

 Mailchimp

 and

 Mayo





Gun.

 I

 wrote

 every

 single

 one

 of

 those





docs

 over

 there.

 Um,

 and

 I

 just

 wanted





like,

 okay,

 this

 is

 for

 everyone

 and





we're

 trying

 to

 redefine

 how

 this

 is

 and





it

 was

 a

 strategy

 of

 like

 we're

 gonna





give

 give

 and

 then

 we

 ask

 uh

 and

 if





people

 are

 is

 Gary

 Vee
</details>

>> 对，如果大家在用 React 构建邮件模板，现在他们需要一个平台来发送它，那他们去哪里发呢？这里就有 Resend。所以这是一种讲故事式的切入市场的方式，比如我们要先解决旅程的第一部分，也就是构建模板；一旦你有了模板，现在那个问题解决了，你还需要一个平台来发送它，平台就在这里。
<details><summary>Original English</summary>
>> yeah

 and

 if

 people

 are

 like

 building

 the





like

 the

 email

 template

 using

 react

 like





now

 they

 need

 a

 platform

 to

 send

 it





where

 do

 they

 do

 that

 here's

 resend.

 So





it

 was

 a

 like

 a

 storytelling

 kind

 of

 way





of

 approaching

 the

 market

 like

 we're





going

 to

 fix

 the

 first

 part

 of

 the

 the





journey

 which

 is

 building

 the

 template





and

 then

 once

 you

 have

 the

 template

 now





that

 that

 problem

 is

 fixed

 you

 need

 a





platform

 to

 send

 it

 here's

 the

 platform
</details>

>> 不过，你在做 React Email 的时候就已经有 Resend 的想法了吗？还是说它只是一个副业项目……
<details><summary>Original English</summary>
>> but

 uh

 did

 you

 have

 the

 idea

 for

 resend





when

 you

 started

 react

 email

 or

 was

 it

 a





side

 project

 that
</details>

>> 后来变成了一家公司？
<details><summary>Original English</summary>
>> then

 became

 a

 company
</details>

>> 我们先创立了 Resend，在构建 Resend 的过程中，我做了很多用户调研，大家都在说：“哎，写模板太痛苦了。我从设计师那里拿到 Figma 文件，体验简直糟透了，全是 HTML 表格之类的。”
<details><summary>Original English</summary>
>> we

 started

 recent

 and

 as

 we

 were





building

 resend

 I

 was

 like

 doing

 a

 lot





of

 user

 research

 and

 people

 were

 saying





like

 oh

 the

 pain

 of

 writing

 the





template.

 I

 get

 the

 the

 Figma

 file

 from





my

 designer.

 It

 sucks.

 Like

 it's

 HTML





tables

 and

 and

 everything.
</details>

>> 他们还得切图，对吧？
<details><summary>Original English</summary>
>> They

 would

 cut

 the

 images,

 right?
</details>

>> 对，我的天哪。
<details><summary>Original English</summary>
>> Yeah.

 Oh

 my

 gosh.
</details>

>> 因为什么都没有。
<details><summary>Original English</summary>
>> Because

 there's

 nothing.
</details>

>> 而且还有那种只在电子邮件里才起作用的特殊 HTML 语法。
<details><summary>Original English</summary>
>> And

 then

 there's

 like

 a

 special

 syntax





of

 HTML

 that

 only

 works

 on

 email.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对，CSS，全都是内联 CSS。
<details><summary>Original English</summary>
>> Right.

 CSS.

 It's

 all

 in

 line

 CSS.
</details>

>> 是的，内联 CSS，没错。然后针对 Outlook，你还得写一些特殊的注释，然后你必须……
<details><summary>Original English</summary>
>> Yeah.

 Inline

 CSS.

 That's

 right.

 And

 then





like

 for

 Outlook,

 you

 have

 like

 some





special

 comments

 and

 then

 you

 got

 to
</details>

>> 太乱了，简直就是一团糟。
<details><summary>Original English</summary>
>> It's

 such

 a

 mess.

 It's

 like

 a

 It's

 a





mess.
</details>

>> 所以对我来说，React 行得通的原因在于它基本上就是一个编译器。就像只要有人写一次，然后只要符合 API，它就能在任何地方运行。
<details><summary>Original English</summary>
>> And

 so

 like

 to

 me

 the

 reason

 that

 React





works

 is

 that

 it

 is

 basically

 a





compiler.

 It's

 like

 it's

 like

 well





somebody

 writes

 this

 once

 and

 then

 as





long

 as

 you

 fit

 the

 API

 it's

 going

 to





work

 everywhere.
</details>

>> 是的，你可以从 Tailwind 导入你的 tokens。现在你有了 TypeScript 的类型定义，再也不用在邮件里出现那种“你好，空逗号”的情况了，你可以进行真正的字符串校验或者任何你想要的处理。我觉得最初反对 React Email 的人里，有人会说：“嗯，你其实根本没用上 React，这里面没有状态。”
<details><summary>Original English</summary>
>> Yeah.

 And

 you

 can

 import

 your

 tokens





from

 Ten.

 Now

 you

 have

 a

 a

 type





definition

 with

 TypeScript.

 So

 no

 more





hey

 empty

 comma

 you

 know

 like

 on

 your





emails

 like

 you

 can

 actually

 have

 like

 a





string

 validation

 or

 whatever

 you

 want.





I

 think

 one

 of

 the

 initial

 people

 that





pushed

 back

 on

 React

 email

 is

 like,





well,

 you're

 not

 actually

 using

 React.





There's

 no

 state.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且 React 应该被视为状态的函数式视图。
<details><summary>Original English</summary>
>> And

 like

 React

 is

 supposed

 to

 be

 a

 views





as

 a

 function

 of

 state.
</details>

>> 呃，但这样的话大部分就是 JSX 模板。它真的有动画吗？有交互性吗？
<details><summary>Original English</summary>
>> Uh

 but

 so

 is

 mostly

 JSX

 is

 templating.





Is

 there

 actually

 like

 animations?

 Is





there

 interactivity?
</details>

>> 没有。
<details><summary>Original English</summary>
>> No.
</details>

>> 比如可展开的手风琴组件，都没有这类东西。
<details><summary>Original English</summary>
>> Expanding

 like

 accordionss,

 no

 nothing





like

 that.
</details>

>> 你不能在邮件里运行 JavaScript。所以你能做的就是……是的，我们基本上就是使用模板。
<details><summary>Original English</summary>
>> So

 you

 cannot

 ship

 JavaScript

 on

 an





email.

 So

 then

 what

 you

 do

 is

 Yeah.

 We





basically

 use

 the

 templating.
</details>

### 行业巨头与竞争

>> 它是图灵完备的。如果你……好吧，太酷了。嗯，其实我想沿着这个邮件的话题继续聊，但我看到了很多以前认识的名字。我只是想知道你能不能满足我们一下，聊聊其中的一些名字，比如……
<details><summary>Original English</summary>
>> It's

 turning

 complete.

 If

 you





Okay.

 So,

 cool.

 Um,

 I

 actually

 do

 want





to

 like

 continue

 on

 this

 email

 path,

 but





I

 see

 so

 many

 names

 I

 used

 to

 know.

 I





was

 just

 kind

 of

 wondering

 if

 you

 can





indulge

 us

 a

 bit

 and

 just

 go

 through





like

 some

 of

 these

 names

 like
</details>

>> 你从他们身上学到了什么。你有没有什么很酷的故事，或者随便什么都可以。
<details><summary>Original English</summary>
>> what

 you

 learned

 from

 them.

 If

 you

 have





any

 like

 cool

 stories,

 if

 just

 just





anything,

 you

 know,
</details>

>> 哥们儿，太多了，太多了。呃，我记得在 Resend 的第一年，我想着一定要去见见 Mailgun 的创始人，因为我当时依然是 Mailgun 的用户。我和 Ev 聊过，嗯，他创办了……天哪。
<details><summary>Original English</summary>
>> man,

 so

 much

 so

 much.

 Uh

 I

 remember

 the





very

 first

 year

 of

 recent

 I

 was

 like

 I





got

 to

 meet

 the

 founder

 of

 Mayo

 Gun





because

 I

 was

 still

 a

 user

 of

 mailogun





and

 I

 talked

 to

 Ev

 um

 he's

 he

 built

 uh





oh

 my

 gosh
</details>

>> Blogger、Medium。
<details><summary>Original English</summary>
>> blogger

 medium
</details>

>> 嗯不是，是安全……那是另一个产品。嗯不过总之，是他现在正在做的一款安全产品。我记得当时跟他聊天，我说：“哥们儿，你为什么那么快就把公司卖了，究竟是怎么回事？”他告诉我：“噢对，我们 90% 的研发精力都只是在对抗滥用行为。所以这门生意糟透了，你根本不该涉足。”
<details><summary>Original English</summary>
>> um

 no

 it's

 a

 se

 it's

 a

 different

 product





um

 but

 anyways

 like

 he

 it's

 a

 security





product

 uh

 that

 that

 he's

 building

 now





and

 I

 remember

 talking

 to

 him

 I

 was

 like





man

 why

 did

 you

 sell

 so

 quickly

 your





company

 what

 was

 the

 thing?

 And

 he

 told





me

 like,

 "Oh

 yeah,

 90%

 of

 our

 R&D

 was





just

 to

 fight

 abusers.

 So

 it

 was

 a

 it's





a

 terrible

 business.

 Like

 you

 shouldn't





go

 there."
</details>

>> 我当时就想，“呃，我可一点都不想活在那样的世界里。”呃，所以我非常担心这个问题。呃，这对我是很大的一课，让我意识到：行，我们必须把这套流程自动化。我们绝不可能专门去建立一个庞大的组织……呃，虽然我们现在确实有很多人对安全感兴趣，但这绝不会成为我们的核心业务。不，我们必须推动整个行业向前发展，但那是其中一个。而在那些公司里，SendGrid 一直是我的最爱，也一直是个庞然大物，最大的那一个，让人觉得“天哪，我们究竟要怎么才能击败 SendGrid？这根本不可能”。然后今年早些时候，我们的下载量超过了 SendGrid，我当时觉得这太不可思议了，而现在我们的数量已经是他们的两倍以上了。
<details><summary>Original English</summary>
>> And

 I

 was

 like,

 "Uh,

 like

 I

 don't

 want





to

 live

 in

 that

 world

 at

 all."

 Uh,

 so

 I





was

 very

 worried

 about

 that.

 Uh,

 and

 it





was

 a

 big

 lesson

 for

 me

 of

 like,

 okay,





we

 got

 to

 automate

 this

 thing.

 Like





there's

 no

 way

 we're

 just

 going

 to

 build





like

 a

 massive

 org.

 uh

 for

 we

 do

 have

 a





lot

 of

 people

 interested

 in

 safety

 now,





but

 it's

 not

 like

 that's

 going

 to

 be

 our





core

 business.

 No,

 we're

 going

 to

 we





have

 to

 be

 pushing

 the

 industry

 forward,





but

 that

 was

 one.

 And

 S

 grid

 has

 always





been

 my

 favorite

 out

 of

 those

 ones

 and





always

 been

 the

 behemoth

 like

 the

 the





biggest

 the

 it's

 like,

 oh

 my

 gosh,

 how





are

 we

 ever

 gonna

 beat

 Sang

 Grid?

 It's





just

 impossible.

 And

 then

 earlier

 this





year

 we

 crossed

 the

 number

 of

 uh





downloads

 from

 S

 grid

 and

 I

 was

 like





that's

 insane

 and

 now

 we're

 more

 than





double.
</details>

>> 所以是指独立用户数，还是什么？那个数字代表什么？
<details><summary>Original English</summary>
>> So

 in

 terms

 of

 unique

 users

 or

 what's





the

 what's

 the

 number
</details>

>> SDK 的下载量？
<details><summary>Original English</summary>
>> downloads

 of

 the

 SDK?
</details>

>> 那是最好的指标吗？
<details><summary>Original English</summary>
>> Is

 that

 the

 best

 metric?
</details>

>> 对，我觉得从普及率来看，这个指标确实说明了一些问题。但如果你看他们发送的邮件数量，显然比我们多得多，因为他们拥有大型企业客户等等。我觉得有一点让人感到意外……
<details><summary>Original English</summary>
>> Yeah

 like

 I

 think

 there

 there's





something

 about

 that

 metric

 in

 terms

 of





adoption

 but

 then

 if

 you

 look

 at

 how





many

 emails

 they

 sent

 is

 obviously

 much





more

 than

 us

 because

 they

 have

 like

 the





big

 enterprise

 customers

 yet

 and

 that





kind

 of

 thing.

 I

 think

 one

 thing

 that's





surprising
</details>

>> Twilio 收购 SendGrid 的全部意义就在于，现在你不再只是一家电子邮件服务商了，而是一个通信平台，
<details><summary>Original English</summary>
>> is

 the

 whole

 point

 of

 the

 Twilio

 Sangid





acquisition

 is

 that

 I

 now

 you're

 no





longer

 an

 email

 service.

 You're

 a





communications

 platform,
</details>

>> 对吧？你在所有环节上进行整合。这不仅仅关乎交叉销售，更在于我可以通过多个渠道触达你。
<details><summary>Original English</summary>
>> right?

 You

 you

 integrate

 across





everything.

 It's

 not

 it's

 not

 just

 about





crossell.

 It

 is

 about

 I

 can

 reach

 you





across

 multiple

 channels.
</details>

>> 类似这样。或者说你有这样的规模。你知道，Twilio 现在大概……我不知道具体多大规模，姑且说是一家 130 亿到 150 亿美元的公司。
<details><summary>Original English</summary>
>> Something

 like

 that.

 Or

 that

 you

 have





the

 size.

 You

 know,

 Twilio's

 like

 I





don't

 know

 what

 the

 size

 is

 now.

 Let's





let's

 call

 it

 13

 15

 billion

 company.
</details>

>> 呃，应该拥有所有的客户关系、所有的人才，所有这些东西，对吧？那你们怎么跟他们竞争呢？
<details><summary>Original English</summary>
>> Uh

 you

 should

 have

 all

 the





relationships,

 all

 the

 talents,

 all





these

 all

 these

 all

 these

 things,

 right?





So

 h

 how

 do

 you

 compete

 with

 that?
</details>

>> 是啊，哥们儿。我非常佩服 Twilio。他们可以说开创了这种模式，或者说……
<details><summary>Original English</summary>
>> Yeah,

 man.

 I

 I

 admire

 Twilio

 so

 much.





They

 kind

 of

 invented

 that

 rail

 or

 or

 or
</details>

>> “去问你的开发者”。
<details><summary>Original English</summary>
>> ask

 your

 developer,
</details>

>> 你懂的，“去问你的开发者”。现在当我路过 101 公路边的广告牌，看到上面写着什么 Customer AI 之类的，我就很生气。我会想，为什么？你们忽视了最初让你们成功的核心优势。嗯，而且我觉得现在 Jeff 也不在那里了，现任 CFO……
<details><summary>Original English</summary>
>> you

 know,

 ask

 your

 developer

 like

 and





now

 when

 I

 I

 I

 I

 go

 past

 that

 101





billboard

 and

 I

 see

 a

 customer

 AI

 or





whatever,

 I'm

 pissed.

 I'm

 like,

 why?





Like

 you

 neglected

 the

 thing

 that

 got





you

 there.

 Um,

 and

 I

 think

 uh

 now

 like





Jeff

 is

 not

 there

 anymore.

 The

 CFO

 is
</details>

>> 他买下了《洋葱报》。
<details><summary>Original English</summary>
>> he

 bought

 the

 onion.
</details>

>> 对，没错，没错。所以我觉得他们完全是在懈怠。先是对 SendGrid 这样，现在对短信也是这样。是的。
<details><summary>Original English</summary>
>> Yeah,

 that's

 right.

 That's

 right.

 So

 I





feel

 like

 they're

 just

 sleeping

 on

 it.





And

 first

 they

 did

 that

 with

 Sen

 Grid





and

 they're

 doing

 that

 with

 SMS

 too.

 And





yeah,
</details>

>> 但我觉得我从中得到的经验是，我一直在试图理清这个行业的规模经济，对吧？很显然，比方说，在你们刚起步的时候他们比你们大 100 倍，对吧？呃，为什么他们不能利用自己的规模直接赢下这场竞争呢？
<details><summary>Original English</summary>
>> but

 I

 think

 my

 my

 lesson

 here

 is

 I'm





trying

 to

 figure

 out

 the

 economics

 of





scale

 of

 this

 industry,

 right?

 Like





clearly,

 you

 know,

 let's

 let's

 call

 it





they're

 100

 times

 larger

 than

 you

 when





you

 when

 you

 just

 got

 started,

 right?





um

 how

 come

 they

 cannot

 use

 their

 size





to

 just

 win
</details>

>> 对。
<details><summary>Original English</summary>
>> right
</details>

>> 换句话说，也许这里根本就不存在规模效益，也许只要做出一款更好的产品，你就能慢慢……
<details><summary>Original English</summary>
>> so

 so

 in

 in

 other

 words

 maybe

 maybe





there

 is

 no

 benefits

 to

 scale

 maybe

 just





you

 know

 and

 you

 just

 make

 a

 better





product

 and

 you

 can

 slowly
</details>

>> 确实，而且我也一直在思考，为什么是 Twilio 收购了 SendGrid，而不是反过来呢？呃……
<details><summary>Original English</summary>
>> for

 sure

 and

 I've

 always

 thought

 about





too

 like

 why

 did

 Twilio

 acquire

 Sen

 Grid





and

 not

 the

 other

 way

 around

 uh
</details>

>> 呃，Twilio 规模更大，我的意思是短信……
<details><summary>Original English</summary>
>> uh

 Twilio

 was

 bigger

 I

 mean

 SMS
</details>

>> 短信体量很大。
<details><summary>Original English</summary>
>> is

 big
</details>

>> 但如果电子邮件和通信已经变成大宗商品，那短信的利润率甚至……
<details><summary>Original English</summary>
>> but

 like

 if

 email

 and

 communication

 is

 a





commodity

 like

 SMS

 your

 margins

 are

 even
</details>

>> 更薄，甚至更差。所以……
<details><summary>Original English</summary>
>> slimmer,

 even

 worse.

 So,
</details>

>> 你们有考虑过做短信吗？
<details><summary>Original English</summary>
>> have

 you

 looked

 into

 SMS?
</details>

>> 有的，当然。
<details><summary>Original English</summary>
>> Yeah,

 for

 sure.
</details>

>> 你们发送短信？
<details><summary>Original English</summary>
>> You

 send

 SMS?
</details>

>> 我想未来某一天会吧。是的，我想某一天会做。是的。
<details><summary>Original English</summary>
>> I

 think

 one

 day.

 Yeah,

 I

 think

 one

 day.





Yeah.
</details>

>> 重要的渠道都有哪些？邮件、短信。还有什么？
<details><summary>Original English</summary>
>> What

 are

 the

 channels

 that

 matter?





Email,

 SMS.

 What

 else?
</details>

>> WhatsApp。WhatsApp 在……
<details><summary>Original English</summary>
>> WhatsApp.

 WhatsApp

 is

 big

 in

 in
</details>

>> WhatsApp 是免费的，对吧？你不需要付任何费用。
<details><summary>Original English</summary>
>> WhatsApp

 is

 free,

 right?

 You

 don't

 pay





anything.
</details>

>> 是的。但接着你就必须通过 Meta，现在企业消息是要收费的。呃所以这其中肯定有一些阻力。
<details><summary>Original English</summary>
>> Yeah.

 But

 then

 you

 you

 got

 to

 go

 through





Meta

 and

 now

 uh

 business

 messages

 are





going

 to

 be

 charged.

 Uh

 so

 there

 there





is

 some

 friction

 there.

 Uh

 for

 sure.
</details>

>> 电话。
<details><summary>Original English</summary>
>> Phone

 calls.
</details>

>> 电话算一个不错的渠道。呃我不太……我从来不接任何自动语音电话，对吧？
<details><summary>Original English</summary>
>> Phone

 calls

 is

 a

 good

 one.

 Uh

 I'm

 less

 I





never

 take

 any

 robocalls,

 right?
</details>

>> 确实是这样。我对那方面也没什么兴趣。我关心的是……
<details><summary>Original English</summary>
>> Yeah,

 that's

 true.

 I'm

 less

 interested





about

 that

 too.

 What

 I

 care

 is

 like
</details>

>> 能够让我与受众建立联系的方式有哪些？那才是我最终在乎的。我并不是非邮件不可。
<details><summary>Original English</summary>
>> what

 are

 the

 things

 that

 makes

 me

 able





to

 connect

 with

 my

 audience?

 Like

 that's





what

 I

 ultimately

 care.

 Like

 I

 don't





care

 about

 email.
</details>

>> 私信。
<details><summary>Original English</summary>
>> DMs.
</details>

>> 是的，私信是一个。但这很难，因为你没法给一大群人发私信，不过 Slack 或许算一个，对吧？Slack……
<details><summary>Original English</summary>
>> Yeah,

 DMs

 it's

 one.

 It's

 hard

 because





you

 cannot

 like

 DM

 a

 big

 crowd

 like

 but





Slack

 maybe

 is

 one,

 right?

 Slack
</details>

>> 比如我有好多 Slack Connect，呃我需要分享他们开发出的某个新功能的消息。
<details><summary>Original English</summary>
>> like

 I

 have

 so

 many

 Slack

 connects

 uh





and

 I

 need

 to

 share

 the

 news

 about

 like





this

 one

 new

 feature

 that

 they

 built.
</details>

>> Pylon，我不知道你们用不用 Pylon。呃我觉得他们可以说开创了这种基于 Slack 的技术支持模式，不过显然你自己也可以轻而易举地搭建一套。
<details><summary>Original English</summary>
>> Pylon

 I

 don't

 know

 if

 you

 guys

 use

 pyon





uh

 I

 think

 they

 kind

 of

 innovated

 this





like

 slack

 support

 thing

 but

 you

 can





obviously

 trivally

 build

 your

 own.
</details>

>> 嗯好吧，接着我想聊聊另一个，就是 AWS。
<details><summary>Original English</summary>
>> Um

 okay

 and

 then

 I

 think

 the

 other

 one

 I





want

 to

 touch

 on

 is

 AWS.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 呃，我跟它的交集是，呃，我是通过 freeCodeCamp、Quincy Larson 等人的内容学习编程的。
<details><summary>Original English</summary>
>> U

 so

 my

 connection

 to

 this

 is

 uh

 I





learned

 to

 code

 with

 free

 code

 campy





Larson

 and

 everything.
</details>

>> 呃，他们的时事通讯拥有大约 500 万订阅者。
<details><summary>Original English</summary>
>> Uh

 they

 have

 like

 5

 million

 subscribers





on

 their

 newsletter.
</details>

>> 是的，通过 Amazon SES 发送，每个月大概花 5,000 美元。
<details><summary>Original English</summary>
>> Yeah.

 sent

 through

 Amazon

 SCES

 for

 like





$5,000

 a

 month.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 挺便宜的。
<details><summary>Original English</summary>
>> Which

 is

 cheap.
</details>

>> 便宜。
<details><summary>Original English</summary>
>> Cheap.
</details>

>> 我不知道……我不知道你们会收费多少。
<details><summary>Original English</summary>
>> I

 don't

 know

 how

 I

 don't

 know

 what

 you





will

 cost.
</details>

>> 对，比那要贵。
<details><summary>Original English</summary>
>> Yeah.

 More

 than

 that.
</details>

>> 所以基本上，在我看来它就是一个低成本的参与者，对吧？它毕竟是亚马逊，地位极其稳固。
<details><summary>Original English</summary>
>> So

 So

 basically

 like

 to

 me

 it's

 just





like

 the

 lowcost

 player,

 right?

 That





that

 is

 I

 mean

 it's

 Amazon.

 It's

 like





they're

 they're

 super

 established.
</details>

>> 呃你从他们身上汲取了什么？大家应该了解什么才会远离他们？
<details><summary>Original English</summary>
>> Uh

 what

 do

 you

 take

 from

 them

 and

 then





what

 do

 you

 what

 should

 people

 know

 to





stay

 away

 from

 them?
</details>

>> 我们最初也是从 SES 起步的。呃，我们……
<details><summary>Original English</summary>
>> We

 started

 with

 SCS

 too.

 uh

 we
</details>

<!-- chunk 5/11 -->

### 从 DX 层到自建底层基础设施

知道这一点后，我想着好吧，如果我们要做创新，我想在 DX（开发者体验）层进行创新。因为我觉得那是一个被忽视的领域，所以我想为每一种语言都提供 SDK。我记得在 Serverless 刚兴起的时候，我们就重点支持了无服务器架构，因为当时根本没有人提供比如如何用 Lambda 发送邮件之类的指南。所以在 DX 方面存在着这样一块未被充分服务的空白，因此我们从最高抽象层切入，而这也确实为我们带来了非常好的发展，让我们能够迅速扩展，因为我们在幕后使用的是 SES。事实证明，在域名的构建方式上存在着诸多限制，他们有这种“配置集”（configuration sets）的概念。而且如果你采用 SES，其隐藏成本在于：好吧，你可能只付了比如 5000 美元，但现在你需要 SNS 来接收事件，你需要关于退信、投诉、打开、点击等所有这些反馈。现在你拿到了这些事件，太棒了，接着你需要 CloudWatch 来查看日志；现在你需要一个队列，因为事件数量会非常庞大，所以你又加上了 SQS；而一旦有了 SQS，你就会开始不断添加所有这些不同的层级。哦，你还想要 Webhook？好吧，现在你又得构建另一套东西。所以如果你选择 SES，它确实是一个很棒的平台，它本身没什么问题，但你很快就会发现你的基础设施足迹会变得比想象中庞大得多，因为你需要围绕它搭建一整套配套设施。

<details><summary>Original English</summary>
knew that okay if we're going to be innovating here I wanted to innovate on the DX layer and because I felt like that was the underserved uh space so let me have SDKs for every single language I remember with serverless we highlighted service because like no one had like guides on how to send an email with lambda or something so there's just this underserved space in in DX so we started with like the most high level layer and that that served us really well was able to like scale because we were using SCS behind the scenes. Turns out there's just a lot of limitations when it comes to the way you structure domains and they have this concept of configuration sets and the hidden cost if you're going with SCS is that okay you might be paying only 5K for example but now you need SNS for the events. So you need like all the feedback from bounces, complaints, open clicks, all that. And now, so you get the events. Great. Now you need cloudatch for the logs. Now you need a queue because it's going to be a lot of events. So now you add SQS. And now that you have SQS, so you start like adding all these different layers. Oh, you want web hooks. Okay, now you got to build another thing. So if you go with SCS, it's a great platform. It it's fine. But you're going to notice like your footprint will be much bigger than you would imagine very quickly because you need all the apparatus uh around it.
</details>

>> 是的。我想说，邮件领域出现的另一家 YC 初创公司是 AgentMail。后来我也和那个家伙聊过，当时的情况就像是：是的，我们不打算去自建底座，我们打算构建在 SES 之上，并不真正去跟他们竞争。

<details><summary>Original English</summary>
>> Yeah. Um I would say you know another YC startup that came up in the male area is agent mail and then they they I talked to the guy as well and it was like yeah we were not going to we're going to build on top of SCS and not really compete with them.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但对我们来说，现在情况正在发生改变。我们正在构建自己的基础设施，正在下沉到最底层。对我们而言，感觉现在已经到了在这个最基础的层面上进行创新变得合理的阶段了，如果我们专注于此，我们就能获得更高的吞吐量和更好的送达率。不过这是一个大工程，我们已经为此工作了好几个月，很快就会公布一些相关消息……

<details><summary>Original English</summary>
>> But for us it's changing that now. So we are we're building the infrastructure and going like down to the metal now. And for us it it feels like we got to the point where now this makes sense to innovate on the the most basic layer and now we can get better throughputs, better deliverability if we just focus on that. Uh but it's a big project like we've been working for months now and we're going to announce something soon about the
</details>

>> 最难的事情是什么？是受信任的 IP 吗？还是算力和数据中心？或者说什么是阻碍因素？

<details><summary>Original English</summary>
>> what is the hardest thing to is it like uh trusted IPs is it compute and data centers or what what is the blocker?
</details>

绝对是 IP。你要买下整段 IP，然后自己管理 IP 池。那是其中一点，而且你几乎就像是在做流量调度，控制流向每个邮箱服务商的吞吐量。然后你还需要与这些服务商建立良好关系。但一旦你建立了那套基础设施，你对能向用户提供什么就拥有了远多得多的控制权。所以，我最看重的事情之一就是可观测性。作为一名工程师，我想确切地看到正在发生什么。我一直觉得在这个领域信息不够充分，比如一封邮件发出后，它到底有没有真正送达？它到底是不是落到了推广标签页里？我根本无从得知，大家只是盲目相信邮件发出了，然后你总会从某些用户那里听到“哦，我没收到邮件”，我就会想这到底是为什么、发生了什么。所以在这些环节之间存在着空白，而我们越靠近底层硬件，我们在能够呈现给用户的数据方面拥有的就越多。所以我感到非常兴奋。这是我们现在正在做的旗舰级转变……

<details><summary>Original English</summary>
Yeah, definitely IPs you're buying like a whole IP block and then now you're managing the IP pools yourself. That that's one and then you're almost doing like traffic control uh and you're controlling the throughput into each mailbox provider and then you need the relationships with the providers but then like once you have that established that infrastructure now you have way more control into what you can give to users. So one of the my biggest things were like observability you know like that as an engineer I I want to see exactly what's happening and I've always felt like in this space there wasn't enough information like once when an email goes out is it really delivered is it really on this P is in the promotional tab like I never know like you just trust that the email goes out and then you always hear from some users like oh it didn't get the email I'm like what like what happened so there's that empty space between those things and the more we're close to the metal, the more we have in terms of data that we can surface for for users. So, I'm really excited. It's like the the flagship uh change that we're making now to
</details>

我的意思是，你们正在变成……对于所有这类 DX 型业务来说，这真的很有趣。你从一个薄层起步，比如 React Email，然后就想着好吧，我们会构建在别人的基础设施之上，等规模做大之后，你就可以真正构建自己的基础设施了，对吧？既然现在你们全权拥有了一切，你们在做法上有什么不同吗？

<details><summary>Original English</summary>
I mean, you're becoming it's it's really interesting for all like DX type businesses. You start with like a thin layer like a React email and then it's like okay well we'll build on other people's infra and then once you get size then you can actually build your own infra, right? Are you doing anything differently because now you own everything?
</details>

>> 是的，我认为我们正在做的……

<details><summary>Original English</summary>
>> Yeah, I think what we're doing is um
</details>

>> 顺便说一句，显而易见你们的控制面板非常漂亮。

<details><summary>Original English</summary>
>> and by the way, obviously your dashboards are beautiful.
</details>

>> 这挺有意思的，老兄。现在我聊过的每个人，所有客户都说：“哦，我从来不打开控制面板，不过我们稍后再聊这个。”但这很有趣，我花了那么多时间试图把控制面板做得很漂亮，结果现在大家根本不去那儿，这让人有点沮丧，但我理解。不过是的，我们只是试图以同样朴素的心态去对待那个问题，就像我们对待所有其他问题一样，我们觉得好吧，这不应该是这个样子的。所以你在挑战最基本的事情，比如这不应该是这个样子的，P99 不应该花这么长时间，我们怎样才能让它更快？好吧，这就是我们现在正在做的事情之一，非常非常深入地聚焦于性能。我们过去一直是一家 Node.js、JS 作坊，各处都只有 TypeScript。而最近，在发送路径上我们不再使用 JavaScript，我们在那里换成了 Go，并且我们还在以其他方式调整其他部分，以使其更加高效。

<details><summary>Original English</summary>
>> It's funny, man. Everyone I talk to now, like all the customers are like, "Oh, I never opened the dashboard, but we can talk about that later." Uh, but it's interesting like I spend so much time trying to make the dashboard beautiful and now people don't go there. It's kind of frustrating, but I get it. But yeah, we're just trying to approach that with the same naive mentality uh that we approach all the other problems and we're like okay this shouldn't be this way. So you're challenging the most basic things of like this shouldn't be this way the P99 shouldn't take this long how we can make it faster. Okay so that's one of the things we're doing now like focused very very deep into performance and we have always been like a no.js JS shop and we have like just TypeScript everywhere and most recently like in the sending path we no longer use a JavaScript we have go there and we're changing other parts to be more more performant in other ways
</details>

>> 因为现在编程语言已经无所谓了。

<details><summary>Original English</summary>
>> cuz now languages don't matter.
</details>

>> 完全正确。选择一个问题真的很便宜，然后你就可以用任何快速的语言重写整套东西。我都在运行 Rust 项目了，而我从未、我也不是真的懂 Rust。我知道一些关于 Rust 的理论知识，但我从未真正费心去学过它。我……

<details><summary>Original English</summary>
>> Exactly right. It's just so cheap to Yeah. like pick a problem and yeah you can rewrite the whole thing in whatever the fast languages. I'm like running Rust projects and I've never I don't really know Rust. Like I know like some theoretical things about Rust, but I've never really bothered to learn it. I
</details>

>> 我觉得我们并没有真正涵盖最近的产品功能范围。也许你想讲讲……

<details><summary>Original English</summary>
>> I feel like we're not really covering the recent product surface area. Uh maybe you want to go.
</details>

>> 不，不。我是说，我们谈到了所有的这一切，包括为什么它很困难，以及你们正在解决的所有问题。此外还有……

<details><summary>Original English</summary>
>> No, no. I mean, you know, there's everything we've talked about, which is why it's hard, what all you're solving. And then there's also just
</details>

### AI、MCP 与 API 优先

>> 从 CLI 发送邮件，超级偏向 Agent。你对此有一些独到见解。我想前几天你发推说 MCP 强势回归了，对吧？超过了一百万次 MCP 调用。邮件的 AI 维度究竟是怎样的？

<details><summary>Original English</summary>
>> send emails from CLI super agent forward. You have some takes on this. I think the other day you tweeted like MCP is so back, right? like over a million MCP calls. Like what's the what's the AI side of email?
</details>

>> 是的，是的。几个月前大家都在说 MCP 已经死了，对吧？就好像唯一重要的东西就是 CLI。我注意到的是，我已经不再去关注什么正在流行、什么正在过时了。我真正在思考这些问题时想的是：好吧，我希望我的产品是什么样的？我想让我的产品呈现出无形的形态。无论他们想用这个产品做什么，都应该成为可能。所以这就是为什么我们一直坚持 API 优先。你知道，我当时根本不知道这在日后会对我们有多大帮助，但我知道，是的，我永远不可能涵盖所有的用例，所以干脆让我直接提供 API，你想做什么就做什么。而对于 MCP 来说，这简直太不可思议了，每个月都至少有 2 倍的增长。现在到了八月份，这些数字还要更多。这还是在八月底之前，我想在八月结束时已经达到了 120 万。但是是的，人们开始从云端桌面或 Codex 进行工作，如果工作是从那里发起的，那么你就需要那些集成，对吧？这真的超级重要。

<details><summary>Original English</summary>
>> Yeah. Yeah. Everyone was saying MCP was dead right a couple months ago. Like yeah, the only thing that matters is the CLI. What I've noticed is that I stopped paying attention to what what's in, what's out. And I I really think about these problems is like, okay, how do I want my product to be? Well, I want my product to be formless. whatever they want to do with the product, it should be possible. So that that's why we've always been API first. Uh you know, I had no idea how much this would help us down the line, but I knew, yeah, like if I will never be able to cover all the use cases, so let me just give the API, you do whatever you want. And with the MCP is just fascinating like every month like at least 2x growth. And now in August, these numbers are even more. This was before the end of August. I think it was 1.2 2 million by the time it ended. But um yeah like people are starting to work from cloud desktop or uh codeex and if work starts from there then you need those integrations right it's just super important.
</details>

>> 我也想澄清一下，你在 MCP 那件事上展示了月度数据之类的走势。它是从比如 50% 的环比增长起步的，这本身就已经非常高了，然后基本上每个月都开始翻倍。嗯。

<details><summary>Original English</summary>
>> I just want to clarify as well uh so you know you show like sort of like the month- bymonth numbers on the MTP thing. It picked up from like let's say 50% month-to-month growth which is already super high. Then it starts to double basically every month. Mhm.
</details>

>> 你们是对 MCP 进行了投入，还是说你们只是发布了一个 MCP，然后过了一段时间它就自然火起来了？

<details><summary>Original English</summary>
>> Did you do investment into MCP or you just had an MCP and it just after some time it gets picked up?
</details>

>> 嗯，关于这一点有一个趣事，我们的第一个 MCP 是由我们的投资方 a16z 的 Yoko 构建的。

<details><summary>Original English</summary>
>> Well, the fun fact about that our very first MCP was built by Yoko from A16Z, our investor.
</details>

>> 哇，增值服务。

<details><summary>Original English</summary>
>> Wow. Value ad.
</details>

>> 是的，没错。

<details><summary>Original English</summary>
>> Yeah. Right.
</details>

>> 她构建了开源版本。那是一个远程本地 MCP。然后它就开始疯狂增长。我当时心想：天哪，为什么大家都在用这个？搭建 MCP 是那么费劲。这是在去年。然后 Yoko……

<details><summary>Original English</summary>
>> So, she she built the the open source version. It was a remote local MCP. And and then it started to grow like like crazy. I was like, man, why are people using it's like so hard to set up MCP? This was uh last year and then Yoko.
</details>

>> 是的，确实如此。

<details><summary>Original English</summary>
>> Yeah, exactly.
</details>

>> 于是她构建了那个工具，接着我就问她：嘿，你能把它转交到我们的组织名下吗？这就像是一个工程师在随手构建了某个东西一样，看到它随后获得的关注度真的很棒。但是要做好这个 MCP，要做好远程版本，我们必须回过头去重新审视我们整个权限模型，因为我们需要 OAuth。然后我们心想：好吧，现在我们遇到了阻碍，那我们就先构建 OAuth 吧。于是我们构建了 OAuth，接着又想：好吧，基于角色的访问控制（RBAC），让我们来研究一下这个，让我们看看用户是如何访问每一个资源的。所以构建 OAuth 是一段完整的历程，而在我们有了 OAuth 之后，好吧，现在我们有了远程 MCP，接下来就是分发。然后就是：好吧，现在我们有了远程支持，太棒了，可观测性也到位了，很好，所有 Datadog 监控面板也都就绪了。好吧，现在万事俱备，让我们来谈谈……

<details><summary>Original English</summary>
And so she built that uh and then I just asked her, hey, can you transfer to our org? It was like just like an engineer building something. And it was nice to see after the traction it was getting. But to do the MCP, right, to do the remote one, we had to go back and revisit our entire permissions model because we need it all off. And then we we're like okay now we have a blocker let's build off. So then we build off and it's like okay our back let's look at that like let let's look at how users uh have access to each one of the resources. So it was a whole journey to build OAF and then after we had OF okay now we have the remote MCP and then it's distribution. So then okay now we have the remote speed. Okay, great, great, great. Observability is in place. Great, great. Okay, all the data dog dashboards. Okay, now all in. Let's talk
</details>

<!-- chunk 6/11 -->

对所有人开放。那也很难。

比如，呃，这并不容易。我希望我有你所有的那些人脉。呃，对我来说没那么容易。跟我说说看。

<details><summary>Original English</summary>
to everyone. And that was hard, too.

Like, uh, it's not as easy. I wish I had all your connections. Uh, it's not as easy to me. Talk to me.
</details>

>> 呃，但像是跟各家实验室交涉，试着进入官方商店和插件市场这类的事情。

<details><summary>Original English</summary>
>> Uh, but like talking to the labs and trying to get into like the the official stores and plugin market.
</details>

>> 你觉得那真的重要吗？

<details><summary>Original English</summary>
>> Do you think that actually matters?
</details>

>> 哦，绝对重要。

<details><summary>Original English</summary>
>> Oh, for sure.
</details>

>> 是的。我我觉得有时候像是——

<details><summary>Original English</summary>
>> Yeah. I I think sometimes like
</details>

>> 我也经历过另一种情况，我拼命争取达成这些合作，我们发布了之后却什么反响都没有，

<details><summary>Original English</summary>
>> I've been on the other side where I try so hard to get these partnerships, we launch it and then nothing,
</details>

>> 对吧？所以——

<details><summary>Original English</summary>
>> right? So
</details>

>> 哪一个才重要？

<details><summary>Original English</summary>
>> which one matters?
</details>

### 官方 MCP 与采购决策

>> 作为消费者，我现在做决定会取决于我是否能访问那个数据。因此，作为一个 B2B 软件的买家，如果我打开 Claude Connectors，却没有在上面看到那家公司，

<details><summary>Original English</summary>
>> So as a consumer, I make decisions now based on do I have the access to that data or not? So as a as a buyer of B2B software, if I go to the claude connectors and I don't see the company listed there
</details>

>> 提供官方 MCP——比如我们之前遇到过这种情况，我们当时在用 Plausible 和 PostHog。Plausible 有一个由 Sentry 构建的 MCP。

<details><summary>Original English</summary>
>> with an official MCP like for we had this like we had a we were using Plausible and Post Hog Plausible had an MCP built by Sentry.
</details>

>> 我不管，如果 Plausible 自己不维护它，而且那不是官方的，我就我没法那么信任它。虽然我非常喜欢 Sentry 团队，也信任那个团队，但我需要软件的所有者来拥有这块集成。

<details><summary>Original English</summary>
>> I don't care if the Plausible doesn't maintain that and that's not official. I I don't I cannot trust that as much. Even though I love the Sentry team and I trust that team, but I need the owner of the software to own this piece of integration.
</details>

>> 天啊。

<details><summary>Original English</summary>
>> Oh my god.
</details>

>> 然后我就做了决定，比如不行，我们要弃用 Plausible，我们在这里就只用呃 PostHog，因为我在那里有 MCP。而且我作为一个 B2C 消费者也是这样做的。比如我喜欢跑步，然后我就想，“哦，让我比如 Straa Straa 有一个 MCP。我可以比如访问我的跑步记录。”所以我因为这个就用 Straa。因此，如果有人说，哦，不，我们有 MCP，但你必须像这样连接。比如以 XMCP 为例，我必须搞类似本地的那种。那实在太令人抓狂了。它在桌面客户端上能用，但在我的手机上不行。对我来说，就是对。如果它不在那里，我就不用它。

<details><summary>Original English</summary>
>> And I made the call like no, we are getting rid of Plausible and we're just going to use uh Post Hog here because I have the MCP there. And I did that as a as a B2C consumer too. I'm like into running and then I'm like, "Oh, let me like Straa Straa has an MCP. I can like access my runs." So I use Straa because of that. So, and if there's like, oh, no, we have an MCP, but you have to connect like this. Like the XMCP for example, I have to do like the the local one. It's just so frustrating. It works on the desktop client, not on my phone. Like like to me, it's just Yeah. If it's not there, I don't use it.
</details>

### MCP 设计与工具数量

>> 除了好吧，它是由厂商官方维护的或者诸如此类之外，什么造就了一个好的 MCP，对比一个普通的 MCP 呢？

<details><summary>Original English</summary>
>> Apart from okay, it is officially maintained by the vendor or whatever. What makes a good MCP versus a social MCP?
</details>

甚至就我们自己的而言，当我与它交互时，总会像——它总是折叠起来的，对吧？那些工具调用，我总会点开，试着去搞清楚：它刚才做了什么？就在几天前，有一次调用，出于某种原因它没法把所有东西都放进上下文里。然后我就想，不行，这不应该发生。比如我们到底发送了多少数据？可能我们给客户端发送了太多数据。所以这是我注意到的事情，比如工具的数量。这在早先是一个更大的顾虑，比如，哦，如果你的工具太多，它们会变混乱。我现在没那么常看到这种情况了。呃事实上，我们只是在向 MCP 添加更多东西。哦——

<details><summary>Original English</summary>
even for hours as I as I interact with that. There were like I always like it's always collapse, right? The the tool calls I'm always opening and trying to understand like what did it do? And just a couple days ago like there was one call where it couldn't put everything on the contacts for some reason. And then I'm like no, this shouldn't happen. Like how much data are we sending? Maybe we're sending way too much data to the client. So that's something that I noticed like the amount of tools. This was a bigger concern earlier like oh if you have way too many tools they get confused. I don't see that as much anymore. Uh and in fact we are just adding more to the MCP. Oh
</details>

>> 比如我们在发布时可能有我不知道 20 个工具，甚至比那还少。现在我们有大概 80 几个工具了。

<details><summary>Original English</summary>
>> like we had like maybe I don't know 20 tools when we launched or even less than that. Now we have like 80 something tools.
</details>

>> 什么鬼——

<details><summary>Original English</summary>
>> What the
</details>

>> 是的。而且像是，我在添加越来越多的长尾功能，以覆盖整个产品功能面。这就是我所注意到的：你可以只做到你控制台所能做事情的 90%，

<details><summary>Original English</summary>
>> Yeah. And like I'm adding more and more like the the long tail of to like the the footprint. That's what I've noticed like you can do like only 90% of what your dashboard does
</details>

>> 那是一种做法；或者你也可以做到 100%。要达到对你控制台所能做事情的 100% 覆盖，实际上非常非常困难，因为现在你涉及到了用量计费、团队邀请、账户配置、删除——这些应不应该暴露为 API 呢？这真的很难。这是一个困难的问题。

<details><summary>Original English</summary>
>> and that's one way of doing it or you can do 100. Getting to 100% coverage of what your dashboard can do is actually very very difficult because now you're doing usage billing team invites account provisioning deletion should that be exposed as an API or not? Like it's it's really hard. Like it's a it's a difficult problem.
</details>

### API 架构与 Next.js 的反思

>> 是的。事实上，呃你知道，你是为数不多我可以与其讨论这个话题的 Latent Space 嘉宾之一。

<details><summary>Original English</summary>
>> Yeah. In fact, uh you know there you are one of the few lat space guests I can I can ever talk about this with.
</details>

>> 我认为这是 Next.js 的错误之一。

<details><summary>Original English</summary>
>> I think this is one of the mistakes of Nex.js.
</details>

>> 噢，真的吗？

<details><summary>Original English</summary>
>> Oh really?
</details>

>> 因为 Next.js 以及服务端组件还有呃 Pages API 或 App Apps API——

<details><summary>Original English</summary>
>> Because Nex.js and server components and uh pages API or apps apps API.
</details>

>> 嗯哼。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 嗯，它们让你基本上很容易把数据绑定到你的页面上。

<details><summary>Original English</summary>
>> Um they make it easy for you to basically bind data to your page.
</details>

>> 好。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 这样你就永远不会暴露一个公共 API。

<details><summary>Original English</summary>
>> So you never expose a public API.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以在默认情况下，那种性能良好且他们鼓励你去做的事情，会让你没有 API。

<details><summary>Original English</summary>
>> So by default the thing that is performance and they encourage you to do you will not have an API.
</details>

>> 没错。然后你就不得不去走单独的代码路径之类的。

<details><summary>Original English</summary>
>> That's right. then you have to just do like separate code paths or whatever.
</details>

>> 事实上，你应该始终拥有完全无头的后端，然后你的前端刚好只是连接到你后端的众多客户端之一。

<details><summary>Original English</summary>
>> In fact, you should just always have like completely headless back end and then your front end just happens to be one of many clients that connects to your back end.
</details>

>> 是的，我们一开始呃把 API 放在 Next 上。我记得那个账单首先就是太高了，以至于我们觉得绝对付不起这笔钱。所以后来我们迁移到了传统的 Node 服务器，呃无论你叫它什么 serverful 之类的，接着我们的控制台就一直像是一个消费同样东西的私有 API。我们不得不重复很多代码。那简直一团糟，对吧？嗯，现在好多了。所有东西都在一个 monorepo 里，你可以复用东西。但是是的，默认情况下，理想中那些框架就应该直接为我们提供那些组件，对吧？我们不得不脱离它单独构建一个公共 API，而同时维护两者很糟糕。

<details><summary>Original English</summary>
>> Yeah, we started with uh our API on next. I remember that first of all the bill was just so high that we were like there's no way we can pay for this. So then we moved to a traditional node server uh server full or whatever you call it and and then like our dashboard was always like a private API consuming the same thing. and we had to duplicate a lot of code. It was a mess, right? Um, now it's so much better. Everything on a monor repo, you can reuse stuff. But yeah, like by default, ideally those frameworks like just gives us those components, right? We had to build a public API separately from that and it sucks to maintain both.
</details>

### 工具扩展与 CLI 申请方式

>> 是的。好的。然后关于前端还有一件事。呃你知道，所以你有 80 个，你那里有 80 个工具，你还在增加更多工具。相比 Cloudflare 只有两个工具——搜索和执行或类似的东西——你非常反主流共识。

<details><summary>Original English</summary>
>> Yeah. Okay. And then one more thing about just just on front. uh you know so you are 80 you got 80 tools in there you're growing more tools you are very counter consensus compared to Cloudflare which only has two tools search and execute or something like that
</details>

>> 到目前为止你还没感受到那个问题，但是呃有什么会让你改变主意呢？对吧，像是你看起来数量在上升，但你真的知道吗？你有没有跟你的客户聊过，然后他们说类似“天啊，这简直是地球上最好的 MCP”这样的话——

<details><summary>Original English</summary>
>> so far you haven't felt that issue but uh what would make you change your mind right like you you it seems like numbers are going up but do you actually know do you do you talk to your customers and say they're like oh my god it's like the best MCP on earth like
</details>

>> 嗯哼。我确实尽量在这方面获取大量反馈，然后我喜欢构建产品的方式是我自己必须使用这个产品，对吧？所以如果我比如昨天发给你的投资人进展汇报，那就是用这个 MCP 构建的。你知道，我当时是在从一个地方抓取数据，又从另一个地方抓取，然后呃——

<details><summary>Original English</summary>
>> Mhm. I do try to get a lot of feedback on that and then the way uh the way I like to build products is I got to use the product my on my own right so if I'm like the investor update that I sent you yesterday that was built using the MCP you know I was like fetching data from one place from another place and then uh
</details>

>> 你现在让我感到自惭形秽了，我没搞这些，我 MCP 用得不够多，基本上这就是我听到的。

<details><summary>Original English</summary>
>> you're making me feel bad now I don't do all this I don't use MCP enough now basically is what I'm hearing
</details>

>> 我的意思是我想另一件事也是，比如你们确实有 CLI，你们确实有常规的 SDK。是的。

<details><summary>Original English</summary>
>> I mean I guess the other thing is also like you do have CLI you do have regular SDK Yeah.
</details>

>> 那些也是在疯长吗？是不是所有东西都迎来了大幅增长，还是说——

<details><summary>Original English</summary>
>> Are those also just growing crazy? Is everything just from a lot of growth or
</details>

>> 是的，CLI 肯定在增长，但没有 MCP 那么多。不过我也在 CLI 上体会到了很多乐趣。比如如果你去我们的招聘页面，我其实对此挺自豪的，因为这是我在某个周末之类的搞出来的。但如果你去查看那里的任何一个职位，你试着去申请职位，然后你往下拉，现在你有三种申请方式。你可以通过——

<details><summary>Original English</summary>
>> Yeah, the CLI is definitely growing, but not as much as the MCP. But I have a lot of fun with the CLI too. Like if you go to our careers page, I'm actually proud of this because I built it on a weekend or something. But if you go to any job there and you you try to apply for a job and you do those go down now you have three ways of applying. You can apply via
</details>

>> 或者 API 申请。所以你只要登录就行，它有一个交互模式；或者我们在 CLI 里内置了技能，你可以直接问 Claude，比如“申请 Resend 的产品设计师职位”。

<details><summary>Original English</summary>
>> or API. So you can just log in and it has an interactive mode or we have skills baked in into the CLI and you can just ask claude like apply for a product designer role at recent.
</details>

>> 好的。所以你很——你在让自己充斥着垃圾信息，尤其是在招聘中。但不是，我的意思是我觉得也许那些也正是你想要的人，对吧？

<details><summary>Original English</summary>
>> Okay. So you're very you are filling yourself with slop especially in careers but no I mean I think maybe that's also the people you want right
</details>

>> 完全是。我其实设置了一个过滤条件，如果来源是 CLI，我会另眼相看，因为我知道人们在格外花心思，比如配置那个东西，比如“哦，不，我得下载这个东西，而且我得认证，然后我还得走那个流程”。

<details><summary>Original English</summary>
>> totally I actually have a filter if the source is the CLI I look differently because I know people are going the extra mile like setting that up like oh no I got to download this thing and I have to authenticate and then I have to go through that flow
</details>

>> 但你猜怎么着，走过那个流程的人总是跟我说，比如“老兄，我以前从没用 CLI 申请过工作”。所以即使他们没被录用，也像是——就是有一种东西，它比起其他的求职申请就是一种不同的体验。

<details><summary>Original English</summary>
>> but guess what like people who go through that they always tell me like man I've never applied for a job using a CLI before so even they are not accepted like there's just something like it's just a different experience than other job applications
</details>

>> 甚至 API——通过 API 申请一个工作。

<details><summary>Original English</summary>
>> even API apply for one job through API
</details>

>> 确实。

<details><summary>Original English</summary>
>> exactly
</details>

>> 我是说这你知道，跟——是一回事。

<details><summary>Original English</summary>
>> I mean it's you know the same thing as
</details>

### 产品哲学与全覆盖考量

>> 呃对，所以所以我觉得我想弄明白的事情之一也是，比如产品哲学，对吧？比如你你显然就是像——你就是在各个方面都拉满，比如每个 SDK、每种语言、每一个呃接触面。

<details><summary>Original English</summary>
>> uh yeah so so I think one of the things I'm trying to figure out as well is like product philosophy right like you you are you're clearly just like you just max everywhere like every SDK every language every uh surface area
</details>

>> 有了智能体显然更容易，但我想我认识的一些其他创始人可能会说：“嘿，这无所谓。把那个交给 Greenhouse 或者 Ashby 就行了。”

<details><summary>Original English</summary>
>> obviously easier with agents but I think some other founders that I would know would say, "Hey, this doesn't matter. Give that to Greenhouse or Ashb."
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 这只是你的工作申请。你不会靠这个形成差异化，对吧？

<details><summary>Original English</summary>
>> It's your job applic. You're not going to differentiate like this, right?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你显然有着非常不同的哲学，就是你事事都在乎，尽管你知道，可能其中有些东西纯粹是浪费。我的看法是，嗯，我试着不仅为优越条件下的用户做优化，比如那些拥有最好的 Wi-Fi、拿着身处硅谷或者纽约的 MacBook 的用户，对吧？还有所有这些身处其他国家、Wi-Fi 极差的处于边缘的人。

<details><summary>Original English</summary>
>> You clearly have a very different philosophy of you care about everything even though, you know, probably some of this stuff is just wasted. The way I see it is um I'm trying to optimize not only for the privileged users like the users who who have the greatest Wi-Fi the MacBooks that are here in ASV or in New York right all these people in the margins that are in other countries with a terrible Wi-Fi
</details>

>> 巴西。

<details><summary>Original English</summary>
>> Brazil
</details>

>> 巴西。在我成长过程中，我当时的情况就是那样：一台糟糕的 Windows 电脑和糟糕的上网条件。所以这就是为什么我们有免费层级。我们设立免费层级不是为了那个——你知道，比如这背后是有原因的，就像我们提供所有的 SDK 一样。所以我在拉满——

<details><summary>Original English</summary>
>> Brazil growing up that that's how it was for me a terrible Windows computer and terrible internet access. So that's why we have the free tier. We we don't have the free tier because of the you know like there's a there's a reason behind it when we we have all the SDKs. So I'm maxing on
</details>

<!-- chunk 7/11 -->

### SDK 生成与开发者体验

构建那些 SDK，兄弟，构建 .NET SDK。你觉得那很有意思吗？我们了解过……

<details><summary>Original English</summary>
 the

 SDKs

 man

 building

 the

 net





SDK.

 Do

 you

 think

 that

 was

 fun?

 Like

 and





we

 looked

 into
</details>

>> Stainless。

<details><summary>Original English</summary>
>> stainless
</details>

>> Stainless、Fern，第三个叫什么来着？呃，但我们考察了所有这些公司，对吧，我们不喜欢自动生成出来的东西。所以其中的每一个 SDK 都是人工手写的。Java 的那个、Rust 的，所有那些，对吧？我这么做是因为我觉得，如果你在使用一款产品，你在所使用的那门语言里就应该获得最好的体验。“噢，但在 400 万人里面只有 500 个人用。”我就是很在乎那 400 个人。

<details><summary>Original English</summary>
>> stainless

 fern

 what's

 the

 third

 one?

 Uh





but

 like

 we

 look

 at

 all

 these

 companies





right

 we

 didn't

 like

 what

 was

 generated.





So

 every

 one

 of

 those

 SDKs

 is

 humanly





generated.

 The

 Java

 one,

 the

 Rust,

 all





those

 ones,

 right?

 And

 I

 do

 that

 because





I

 feel

 like,

 yeah,

 if

 you're

 using

 a





product,

 you

 should

 have

 the

 best





experience

 in

 that

 language

 that

 you're





using.

 Oh,

 but

 there's

 only

 500

 people





out

 of

 the

 4

 million.

 I

 care

 about

 those





four

 400

 people.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 你知道，为什么不呢？

<details><summary>Original English</summary>
>> You

 know,

 why

 not?

 You

 know,
</details>

>> “为什么不”的原因是你有 400 万用户，这就是为什么不。

<details><summary>Original English</summary>
>> why

 not

 is

 you

 have

 4

 million

 users.





that's

 why

 not
</details>

>> 有很多事情要做，但在打造这个产品时有那种坚持己见的态度是件好事，对吧？

<details><summary>Original English</summary>
>> there's

 a

 lot

 of

 stuff

 to

 do

 but

 it's





it's

 good

 to

 have

 that

 opinionated

 side





towards

 building

 this

 right
</details>

### 产品功能面与多人协作邮件

>> 还有其他我们应该涉及的产品功能面吗？呃，你讲了 CLI，讲了模板，讲了 MCP。

<details><summary>Original English</summary>
>> any

 other

 product

 surface

 area

 stuff





that

 we

 should

 cover

 uh

 you

 covered

 CLI





covered

 templates

 covered

 MCP
</details>

>> 我觉得从你这里获取一个高维度的视角挺好的：这里面有多少是非常传统的——你甚至有用于手动编写邮件的仪表盘、模板；你有编程式的；你也有完整的 Agent 构建——你觉得未来的方向在哪里？对于一个变化相当快的世界，你是怎么考虑构建它的？

<details><summary>Original English</summary>
>> I

 think

 it's

 good

 to

 get

 a

 highle





perspective

 from

 you

 of

 how

 much

 of

 this





is

 very

 traditional

 you

 even

 have





dashboards

 templates

 to

 manually

 write





emails

 you

 have

 programmatic

 you

 also





have

 the

 full

 agent

 build

 like

 where

 do





you

 see

 it

 going

 how

 do

 you

 think

 about





building

 this

 for

 a

 pretty

 fast

 changing





world,

 right?
</details>

>> 是的，邮件确实还有一个环节正在脱离这种单人模式，更多地走向多人模式。呃，我们甚至把我们的编辑器做成了这样。它是支持多人协作的。如果两到三个人一起用，它能解决所有的冲突。我们其实是——如果我有一个包含所有团队的 Resend 专属账户，呃，我们全员大会的所有内容都在那里跑。所以全员大会基本上就是你过去，那是一封巨大的……

<details><summary>Original English</summary>
>> Yeah,

 there's

 definitely

 still

 a





component

 of

 email

 moving

 out

 of

 this





single

 player

 mode

 and

 going

 more

 into





multiplayer.

 Uh

 we

 even

 built

 our

 editor





like

 this.

 It's

 multiplayer.

 It

 fix

 all





the

 conflicts

 if

 you

 have

 two

 or

 three





people.

 We

 actually

 run

 if

 I

 have

 a





private

 recent

 account

 with

 all

 the





teams

 and

 uh

 we

 run

 all

 of

 our

 all

 hands





uh

 there.

 So

 the

 all

 hands

 is

 pretty





much

 you

 go

 there

 it's

 a

 huge
</details>

>> 你们写一封邮件。

<details><summary>Original English</summary>
>> you

 make

 an

 email
</details>

>> 那是一封邮件，我们在全员大会结束时一起把邮件发出去。超级有意思，而且同一个文档里差不多有 20 个人。

<details><summary>Original English</summary>
>> it's

 an

 email

 and

 we

 send

 the

 email





together

 at

 the

 end

 of

 the

 all

 hands





it's

 super

 fun

 and

 you

 have

 like

 20





people

 in

 the

 same

 documentary
</details>

>> 这就像是——不，我觉得 99% 的人都没想过多人的协同邮件，对吧？但是……

<details><summary>Original English</summary>
>> this

 is

 like

 no

 I

 I

 feel

 like

 99%

 of





people

 have

 not

 thought

 about





multiplayer

 email

 right

 but
</details>

>> 是的。

<details><summary>Original English</summary>
>> yes
</details>

>> 你有很多……

<details><summary>Original English</summary>
>> you

 have

 a

 lot
</details>

>> 是的，而且那真的很有趣，兄弟。光是那个编辑器，维护那玩意儿真是太难了，但我很喜欢它。我喜欢我们为需要 UI 的人提供了 UI。比如有些团队讨厌把邮件模板提交进他们的源代码里。那他们就只想做一个可视化编辑器、一个模板，交给营销团队，然后直接调用 ID。我对模板不关心，我只想带上变量调用 ID 就完事了。呃，另一些团队，他们喜欢说：不，我想提交，我想对这个东西拥有源码控制，把这块东西掌握在自己手里。所以我尽量去迎合这些不同的受众，呃，去打造一款让人觉得我们在用心的产品，呃，这在别的地方我是体会不到的。

<details><summary>Original English</summary>
>> yeah

 and

 it

 was

 really

 fun

 man

 that





editor

 alone

 it's

 so

 freaking

 hard

 to





maintain

 that

 thing

 but

 I

 love

 it

 I

 love





that

 we

 have

 the

 UI

 for

 people

 who

 need





the

 UI.

 Like

 some

 teams

 hate

 to

 have

 the





email

 template

 pushed

 into

 their

 source





code.

 Then

 they

 just

 want

 to

 build

 a





visual

 editor,

 a

 template,

 give

 to

 the





marketing

 team

 and

 just

 call

 the

 ID.

 I





do

 I

 don't

 care

 about

 the

 template.

 I





just

 want

 to

 call

 the

 ID

 with

 variables





and

 I'm

 I'm

 done.

 Uh

 other

 teams

 they





they

 do

 they

 do

 like

 no,

 I

 want

 to





commit.

 I

 want

 to

 have

 source

 control





over

 this

 and

 own

 this

 piece

 of

 thing.





So

 I

 try

 to

 tailor

 to

 those

 different





audiences

 and

 uh

 and

 build

 a

 product





that

 feels

 that

 we

 care

 uh

 which

 is

 not





the

 feeling

 I

 get

 elsewhere.
</details>

>> 是的。顺便问一下，Resend 团队用什么来读邮件？呃，Superhuman 还是……

<details><summary>Original English</summary>
>> Yeah.

 By

 the

 way,

 what

 does

 the

 recent





team

 used

 to

 read

 email

 uh

 superhuman

 or
</details>

>> 是的。噢天呐，那个——你看到 Superhuman 最新的更新了吗？呃，忙着其他发布会也是，对吧？

<details><summary>Original English</summary>
>> Yeah.

 Oh

 man,

 that

 have

 you

 seen

 the





last

 superhuman

 update

 uh

 this

 busy

 with





other

 launches

 too,

 right?
</details>

>> 呃，是的。对于听众来说，我们录制这期节目的当天刚好是 Astra 发布的日子，我被卷了进去，而且我几乎没睡，但是，呃，不，它怎么了吗？他们只是稍微更新了一下 UI。

<details><summary>Original English</summary>
>> Uh

 yeah.

 And

 and

 for

 for

 listeners,

 we





are

 recording

 this

 on

 the

 day

 of

 the





Astra

 launch,

 which

 I

 was

 pulled

 into





and

 like

 I

 am

 not

 sleeping,

 but

 uh

 no,





what's

 wrong

 with

 it?

 They

 just

 updated





the

 UI

 a

 little

 bit.
</details>

>> 是的。有一种情绪就是，“噢，这正在走向每一次其他收购都会走向的方向”，对吧？就像现在你在供养一个拥有其他……

<details><summary>Original English</summary>
>> Yeah.

 The

 there's

 just

 um

 a

 sentiment

 of





like,

 oh,

 this

 is

 going

 into

 the





direction

 of

 every

 other

 acquisition





goes,

 right?

 Like

 now

 you're

 feeding

 a





brand

 that

 has

 other
</details>

>> Grammarly 和其他东西的品牌。

<details><summary>Original English</summary>
>> Grammarly

 and

 other

 things.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 收件端与 Agent 收件箱 API

>> 好的。这只是邮件。我知道，我确实想了解整体邮件技术的最新动态。呃，你们在发送端，其他人在阅读和接收端。

<details><summary>Original English</summary>
>> Okay.

 This

 is

 just

 email.

 I

 know

 I

 I

 do





want

 to

 keep

 up

 to

 date

 on

 email

 tech

 in





general.

 Uh

 you're

 on

 the

 sending

 side,





other

 people

 on

 the

 reading

 and





receiving

 side.

 Yes.
</details>

>> 呃，然后我认为，你知道，越来越多地可以说是 Agent 在读我的邮件，对吧？比如，呃，我其实不读我大部分的邮件。我有 Poke 和两个人帮我处理邮件。

<details><summary>Original English</summary>
>> Uh

 and

 then

 I

 think

 uh

 you

 know





increasingly

 I

 would

 say

 agents

 reading





my

 email,

 right?

 Like

 uh

 I

 actually





don't

 read

 most

 my

 email.

 I

 have

 Poke





and

 Two

 Humans

 helping

 me

 with

 my

 email.
</details>

>> 真棒。

<details><summary>Original English</summary>
>> Nice.
</details>

>> 我挺喜欢那样的。

<details><summary>Original English</summary>
>> I

 love

 that.
</details>

>> 嗯，Poke 还挺不错的。我老实说很喜欢——像现在的 Shortwave 超级火，25 亿美元估值的公司，没有任何营收。嗯，而且大家就只是试图做阅读邮件的 Agent。

<details><summary>Original English</summary>
>> Um

 Poke

 is

 pretty

 good.

 I

 I

 honestly





like

 Instinct

 now

 super

 hot.

 $2.5





billion

 company

 with

 no

 no

 revenue.





Um

 and

 like

 it's

 just

 like

 people

 trying





to

 read

 email

 agents.
</details>

>> 是的，我们绝对在关注那个领域。那是我投入大量时间的另一件事，比如你怎么以编程方式创建几十个收件箱，然后那些收件箱又该如何被……

<details><summary>Original English</summary>
>> Yeah,

 that

 we

 are

 definitely

 looking

 to





that

 space.

 That's

 another

 thing

 that





I'm

 spending

 a

 lot

 of

 my

 time

 like

 how





you

 can

 programmatically

 create

 dozens





of

 inboxes

 and

 then

 how

 are

 those





inboxes

 accessed

 by
</details>

>> 因为你们创建——你们支持了接收邮件。那个叫什么来着？Inbound。

<details><summary>Original English</summary>
>> because

 you

 you

 create

 you

 uh

 enabled

 re





receiving

 email.

 What

 is

 it

 called?





Inbound.
</details>

>> Inbound，对。

<details><summary>Original English</summary>
>> Inbound.

 Yeah.
</details>

>> 邮件。

<details><summary>Original English</summary>
>> Email.
</details>

>> 所以现在我们要走更进一步的抽象。Inbound 差不多是最基础的抽象。现在我们再往前走一步，变成像：“噢，由于各种原因你需要 100 个收件箱，而且这是你需要在此之上的 API，对吧？”所以你需要读取 API、标记未读、需要加星标 API、打标签。

<details><summary>Original English</summary>
>> So

 now

 we're

 going

 another

 abstraction.





Inbound

 is

 like

 the

 most

 basic





abstraction.

 Now

 we're

 going

 one

 step





further

 and

 be

 like,

 "Oh,

 you

 need

 100





inboxes

 for

 any

 reason

 and

 here

 are

 the





APIs

 that

 you

 need

 on

 top

 of

 that,





right?"

 So

 you

 need

 a

 read

 API,

 markers





and

 red,

 you

 need

 star

 API

 labeling.

 I





see.
</details>

>> 明白了。

呃，所以我们很快会围绕这个推出一款产品。

<details><summary>Original English</summary>
>> Uh

 so

 we're

 going

 to

 be

 launching

 a





product

 around

 that

 soon.
</details>

>> 是的。不过话说回来，它全都是 API 驱动的，因为那完全是因为——呃，我会说我一直在看的对标产品是 Missive。

<details><summary>Original English</summary>
>> Yeah.

 But

 again,

 it's

 all

 API

 driven





because

 that

 the

 the

 fully

 because





like

 uh

 I

 I

 would

 say

 the

 comparable





stuff

 that

 I've

 been

 looking

 at

 is





missive.
</details>

>> 没错。还有其他的，比如 Help Scout。

<details><summary>Original English</summary>
>> Yep.

 And

 there's

 other

 like

 uh

 help





scout.
</details>

>> 是的。或者……

<details><summary>Original English</summary>
>> Yes.

 Or
</details>

>> 类似于共享收件箱那一类的产品，对吧？

<details><summary>Original English</summary>
>> like

 a

 shared

 inbox

 type

 of

 product,





right?
</details>

>> Front。Front。

<details><summary>Original English</summary>
>> Front.

 Front.
</details>

>> Front，对。所以希望这可以算作那种产品的一个版本。呃，我可以跟你分享。如果你想试用的话，有个 Feature Flag 可以开给你。

<details><summary>Original English</summary>
>> Front.

 Yeah.

 So

 hopefully

 this

 can

 be

 uh





a

 version

 of

 that.

 Uh

 I

 can

 share

 with





you.

 There's

 a

 feature

 flag

 for

 you

 if





you

 want

 to

 try

 that

 out.
</details>

>> 好啊。我对邮件技术非常感兴趣。呃，好的，然后对我来说，呃，然后我，再次强调，我就像是在问所有这些问题。

<details><summary>Original English</summary>
>> Yeah.

 I'm

 I'm

 very

 interested

 in

 email





tech.

 Uh

 okay.

 And

 and

 then

 to

 me

 uh

 and





then

 I

 again

 I'm

 just

 like

 asking

 all





these

 questions.
</details>

### 送达率、邮箱市场与域名信誉

>> 你们发送的邮件中有百分之多少是去往 G Suite 或者，你知道，比如市场份额大概是怎样的，对吧？比如 Google 对比 Outlook……

<details><summary>Original English</summary>
>> What

 percent

 of

 your

 email

 goes

 to

 a

 G





Suite

 or

 you

 know

 like

 what's

 the

 market





share,

 right?

 like

 Google

 versus

 Outlook
</details>

>> 对比 Apple 对比 Hotmail。

<details><summary>Original English</summary>
>> versus

 Apple

 versus

 Hotmail.
</details>

>> 是的，我脑子里没有具体的数据，但绝大多数——比如至少 60%、60% 是 Gmail，紧接着大概就是三巨头，比如全世界的那些 Outlook、Yahoo Mail 之类的，紧随其后，再然后就是长尾的……

<details><summary>Original English</summary>
>> Yeah,

 I

 don't

 have

 the

 numbers

 top

 of

 my





head,

 but

 the

 vast

 majority

 like

 at





least

 60

 60%

 Gmail

 and

 then

 you

 have





like

 maybe

 the

 the

 big

 tree

 after

 like





the

 Outlook,

 the

 the

 Yahoo

 Mails

 of

 the





world

 right

 after

 and

 then

 you

 have

 a





long

 tale

 of
</details>

>> Apple 没那么大。

<details><summary>Original English</summary>
>> Apple's

 not

 that

 big.
</details>

>> Apple 很大。是的。尤其是加上他们现在推出的那个隐私功能，呃，很难……

<details><summary>Original English</summary>
>> Apple

 is

 big.

 Yeah.

 And

 especially

 with





the

 the

 privacy

 thing

 that

 they

 did

 now,





um

 it's

 hard
</details>

>> 注册 Apple ID。

<details><summary>Original English</summary>
>> to

 sign

 up

 to

 an

 Apple

 ID.
</details>

>> 抱歉。

<details><summary>Original English</summary>
>> Sorry.
</details>

>> 是的。比如 Apple 会为你自动生成一个邮箱地址。所以如果你注册……

<details><summary>Original English</summary>
>> Yeah.

 Like

 Apple

 autogenerates

 an

 email





address

 for

 you.

 So

 if

 you

 sign

 up

 for
</details>

>> 是的，我用那个。我用那个。

<details><summary>Original English</summary>
>> Yeah,

 I

 use

 that.

 I

 use

 that.
</details>

>> 那对你们来说是个问题吗？

<details><summary>Original English</summary>
>> Is

 that

 a

 problem

 for

 you

 guys?
</details>

>> 他们在什么邮件能进入那些收件箱方面更严格。呃，所以有时作为域名所有者，我们其实有类似于产品内的配置向导，来协助你向 Apple 登记，以便你能把邮件送达过去。

<details><summary>Original English</summary>
>> They're

 more

 strict

 in

 terms

 of

 what

 can





get

 into

 those

 inboxes.

 Uh

 so

 sometimes





as

 a

 domain

 owner

 we

 actually

 have

 like





an

 in

 product

 wizard

 to

 help

 you

 like





register

 with

 Apple

 so

 that

 you

 can

 get





your

 emails

 delivered

 there.
</details>

>> 是啊。是啊。嗯，好的，我明白了。显然这是你的工作，对吧？整件事的核心就是送达率。如果你没有送达率，你的业务就不复存在。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Um

 okay

 I

 I

 understand.





Obviously

 this

 is

 your

 job

 right?

 The





whole

 thing

 is

 deliverability.

 If

 you





don't

 have

 deliverability

 you

 don't

 have





a

 business.
</details>

>> 没错，那差不多是……

<details><summary>Original English</summary>
>> Exact

 that's

 kind

 of

 the
</details>

>> 就算我们在网站上放着世界上最漂亮的魔方，有史以来最酷的员工手册，如果它挂了……

<details><summary>Original English</summary>
>> we

 can

 have

 the

 most

 beautiful

 Rubik's





cube

 in

 the

 website.

 the

 most

 cool

 like





coolest

 handbook

 ever.

 If

 it's

 down,
</details>

>> 是的。

<details><summary>Original English</summary>
>> yeah,
</details>

>> 一切全白费了。

<details><summary>Original English</summary>
>> it's

 all

 for

 nothing.
</details>

>> 那它们之间的关联度有多大，对吧？比如，如果你被 Google 封禁、降权，或者被扔进促销标签页，那会转移影响到其他厂商，还是说它们是非常分散独立的？

<details><summary>Original English</summary>
>> And

 how

 correlated

 are

 they

 are

 they





right?

 Like

 if

 you

 get

 banned

 or

 down





downranked

 or

 put

 in

 promotions

 tab

 in





Google,

 does

 that

 transfer

 over

 to

 the





other

 guys

 or

 are

 they

 very





decentralized?
</details>

>> 万幸的是，现在——比如在邮件行业的最初阶段，它是非常基于 IP 的，如果一个 IP 受损，比如现在你就会尝到它的后果。现在有大量的信誉是与域名挂钩的。所以人们会做的就是，呃，你根据自己发送的邮件类型创建不同的子域名，比如一个用于事务性邮件的子域名，你知道那种邮件可能不需要点击和打开追踪，然后你有另一个用于营销邮件的域名，那些子域名有助于把某一部分的信誉隔离区分开来。

<details><summary>Original English</summary>
>> Thankfully

 now,

 like

 in

 the

 beginning

 of





the

 email

 industry,

 it

 was

 very

 IP

 based





and

 if

 one

 IP

 was

 damaged,

 like

 now

 you





you

 getting

 the

 the

 consequences

 of





that.

 Now

 there's

 a

 lot

 of

 reputation





associated

 with

 the

 domain.

 So

 then

 what





people

 do

 is

 uh

 you

 create

 different





subdomains

 depending

 on

 what

 type

 of





emails

 you're

 sending

 like

 one

 subdomain





for

 transactional

 emails

 that

 you

 know





that

 maybe

 doesn't

 have

 click

 and

 open





tracking

 and

 then

 you

 have

 another





domain

 for

 your

 marketing

 emails

 and





those

 subdomains

 help

 segregate

 the





reputation

 of

 uh

 whatever.
</details>

>> 就像 transactions.resend.com 这样？

<details><summary>Original English</summary>
>> Would

 it

 be

 like





transactions.reresend.com?
</details>

>> 对。updates、notifications，随你怎么用。呃……

<details><summary>Original English</summary>
>> Yeah.

 updates,

 notifications,

 whatever





you

 want

 to

 use

 it.

 Uh,
</details>

>> 那如果我想要类似于 a.b.c.resend.com 这种，点能更多吗？

<details><summary>Original English</summary>
>> and

 do

 I

 have

 more

 dots

 if

 I

 want

 like

 a





b.c.resent.com?
</details>

你也可以这么做，但我们只看到类似于，呃，做——我不知道，五个子域名之类的话，对，不是很实用，但人们确实会做，呃，是的，比如一些特殊的子域名。像我们在 Resend 针对我们自己的邮件也是这么做的，比如营销邮件和事务性邮件走的是不同的流，而且……

<details><summary>Original English</summary>
you

 could

 do,

 but

 we

 just

 see

 like

 uh





doing

 I

 don't

 know

 five

 subdomains

 is





like

 yeah

 not

 not

 really

 practical

 but





like

 people

 do

 uh

 yeah

 like

 some

 special





ones

 like

 we

 do

 that

 at

 recent

 for

 our





own

 emails

 like

 marketing

 has

 a





different

 stream

 than

 the

 transactional





ones

 and
</details>

>> 是的，甚至投资人的那个也不同，比如我用 confidential.resend.com 来发那些邮件。

<details><summary>Original English</summary>
>> yeah

 even

 the

 the

 investor

 one

 has

 a





different

 like

 I

 I

 use





confidentialresent.com





to

 send

 those

 emails
</details>

>> 我之前甚至都不知道还能这样，是的，那确实是很好的建议。以前非常基于 IP，现在是基于域名的。

<details><summary>Original English</summary>
>> I

 didn't

 even

 know

 you

 could

 yeah

 and





that

 that

 is

 good

 advice

 It's

 before

 it





was

 very

 IP

 based

 now

 it's

 domain

 based
</details>

>> 你知道，我收到过……好的，我收到过很多糟糕的——我不得不去单买一个，所以因为我们用 .ai、.er 和 .space，这些全都是那种没人认识的古怪顶级域名，对吧？所以有人叫我去把所有东西都买成 .com……

<details><summary>Original English</summary>
>> you

 know

 I

 have

 okay

 I

 have

 received

 so





many

 bad

 I

 had

 to

 buy

 a

 separate

 so





because

 we

 use

 AIER

 and

 space

 these

 are





all

 like

 weird

 TLDDS

 that

 nobody





recognizes

 right

 so

 I

 was

 told

 to

 get





coms

 for

 everything
</details>

>> 然后说不定那样就能提高送达率。

<details><summary>Original English</summary>
>> and

 then

 maybe

 that

 improves





deliverability
</details>

>> 那样做的问题在于，现在比如——假设我们以可口可乐为例，对吧？可口可乐有一个域名，现在你是可口可乐，心想：“噢好啊，咱们买下……”

<details><summary>Original English</summary>
>> the

 problem

 with

 that

 is

 that

 now

 like





let's

 say

 let's

 take

 Coca-Cola

 right





Coca-Cola

 has

 a

 domain

 now

 your





Coca-Cola

 like

 oh

 yeah

 let's

 buy
</details>

<!-- chunk 8/11 -->

另一个长得像我们域名的域名。

<details><summary>Original English</summary>
another domain domain that looks like our domain.
</details>

>> 这看起来像钓鱼。

<details><summary>Original English</summary>
>> It looks like fishing.
</details>

>> 看起来完全就像钓鱼。所以造成损害的可能性要糟糕得多。

<details><summary>Original English</summary>
>> It looks exactly like fishing. So, the chances of damage is way worse.
</details>

>> 在你买 .com 的时候这依然是个问题吗？比如，换作另一种情况我就能理解，对吧？你们是 latentpace.com，我买 laten.space，这看起来像钓鱼，对吧？但是——

<details><summary>Original English</summary>
>> Is this still a thing when you're buying the com? Like, I would get it the other way, right? You're latentpace.com. I buy laten.space looks like fishing, right? But
</details>

>> 但 .com 依然——

<details><summary>Original English</summary>
>> the com still,
</details>

>> 伙计，你会感到惊讶的，比如我日常看到的那些事情。这简直太疯狂了。是的。

<details><summary>Original English</summary>
>> man, you would be surprised like there's just like the things I see on a day-to-day basis. This is like crazy. Yeah.
</details>

>> 是的。所以我听到的是，买 .com 还是值得的。这——

<details><summary>Original English</summary>
>> Yeah. So what I'm hearing is like com is worth it. It's
</details>

>> 是的。是的。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

### 从传统 SEO 到 AEO

>> 这全都是关于邮件业务的那些事。显然，其中一部分原因在于你起步在 trag 之前——

<details><summary>Original English</summary>
>> That's all the sort of uh business of email. Obviously some part of it is you just got started before trag
</details>

>> 然后你们成了大家喜欢的头部玩家，然后自然而然地就冒出来了。你们并没有为 AEO 做什么特别的事情。

<details><summary>Original English</summary>
>> and then you were a leading player that people liked and then obviously organically you you pop up. You didn't do anything special for AEO.
</details>

>> 你们为 AEO 做了什么？我想说我们并不是领头羊，因为我们在 2023 年左右崭露头角时，很少有人知道 Resend，而且我们远远落后于 Twilio、Postmark、Mailgun，那些公司在 SEO 上投入了 10 多年。所以对我们来说，要在任何关键词上获得排名几乎都像是一场艰苦的拉锯战，太难太难了。所以当时我们做的事情就是，好，我们一定要把重点放在文档上。文档做得很明确，比如好，如果我们在写文档，它又有长尾效应，比如“哦，这里有一篇文档，不只是讲 Python，而是讲你如何结合 Django 来配置”——

<details><summary>Original English</summary>
>> What did you do for AEO? I would say we were not the leaders because we coming up like in 2023 like very few people knew about recent and we were like so behind twillio Postmark mail gun those companies invested in SEO for 10 plus years. So for us to get ranked for anything was like almost like it's it was a uphill battle like so so difficult. So then what we did was like okay let's focus on the docs for sure and the docs was very intentional about like okay if we're doing a docs on it has long tail again like oh here's a docs on uh not just python like how you set it up with Django
</details>

>> 是的，“如何用某某搭配某某”，“如何用某某搭配某某”。

<details><summary>Original English</summary>
>> yeah how to blah with blah how to blah with blah
</details>

>> 篇幅极短的文章，聚焦在——

<details><summary>Original English</summary>
>> super short articles focus on
</details>

>> 就只是传统的 SEO。

<details><summary>Original English</summary>
>> just traditional SEO
</details>

>> 传统的 SEO，嗯，没什么花哨的。当模型开始涌现时，我就想，好吧，也许我得改变页面的内容了，因为如果人们在提问，那我就需要去创作问答形式的内容。所以加了很多 FAQ，现在 Resend 的几乎每一个页面都有 FAQ。比如你去看定价页面，或者——是的，定价页面当然几乎总是会有，挺标准的。是的。

<details><summary>Original English</summary>
>> traditional SEO uh nothing fancy there when models started to come then I was like okay maybe I got to change the content of the page because if people are asking questions then I need to like create content that is in action and answer ask and answer type of format. So a lot of FAQs now almost every page at recent has an FAQ you know like you go to pricing page or like Yeah. Uh of course pricing almost always has pretty standard. Yeah.
</details>

>> 但你们在各种页面都做了 FAQ。是的，我觉得可能安全页面也有。是的。所以你能看到这就像一种模式，嗯，所有页面都有这个，因为人们就是这么提问的：“Resend 符合 SOC 2 规范吗？”然后答案就在那里——

<details><summary>Original English</summary>
>> But like you do FAQs in like all sorts of Yeah. I think maybe security also. Yeah. So like you see it's like a pattern uh of like all pages have that because that's how people are asking is recent so to compliant and then just have the answer right there
</details>

### llm.txt 与 Markdown 版本页面

>> 然后好了，现在我们有了这些东西，接下来我们得做 llm.txt。所以我们在文档中加入了 llm.txt，幸好我们用了 Mintlify 这个很棒的产品。然后我们想，好，我们怎么把它也应用到营销网站上呢？于是就给每个营销页面都做了 llm.txt。文档的 hash mark……呃，Markdown 版本也是同样的操作。我打算把网站上的每一个页面、营销网站上的每一个页面都做成 Markdown 版本——

<details><summary>Original English</summary>
>> and then okay now we have those things in okay now we got to do llm.txt so we added llm.xt on our docs thankfully because of Mintify that we use great product and we're like okay how we take this to the marketing site too so then llm.txt txt for every marketing page. Same with the like docs hatch mark uh markdown versions of the docs. I'm going to do markdown versions of every single page on the website on the marketing website
</details>

>> 是用内容嗅探，还是直接在末尾加上类似 .md？

<details><summary>Original English</summary>
>> using content sniffing or you just append like MD.
</details>

>> 是的，直接追加。你只要加上……所以如果你访问安全页面的 .md，它就能生效。

<details><summary>Original English</summary>
>> Yeah, just append you do append uh so if you go to the yeah security page MD it will work.
</details>

>> 是的。但如果你对那个页面发起内容协商，呃，它也会在该页面上直接渲染出 Markdown 版本，而不用跳转到——

<details><summary>Original English</summary>
>> Yeah. But also if you do content negotiation with that page uh it will render on that page like the markdown version without going to the
</details>

>> 是的。对听众来说，这是我觉得不确定它是否有意义的事情之一。

<details><summary>Original English</summary>
>> Yeah. Which for listeners this is one of those things I'm not sure it matters.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我真的很不确定。

<details><summary>Original English</summary>
>> I'm really not sure.
</details>

>> 我的意思是，你们目前的表现非常好。所以——

<details><summary>Original English</summary>
>> I mean you're winning really well. So
</details>

>> 是的，我认为有一个改变了的例子，嗯，也许它对分发没有帮助，但有助于提高准确性。去看看定价页面。我记得那是一个随意的周日，我只是在做竞品分析，我当时在提问，比如“好，如果你用 Resend 发送 120 万封邮件，然后用 X、Y、Z 竞品也这么做——

<details><summary>Original English</summary>
>> yeah I think what one example that changed uh and maybe it doesn't help with distribution but helps with accuracy. So go to the pricing page. I remember this was like a random Sunday and I I was just like doing competitor analysis and I was just asking like okay if you send 1.2 million emails using resent and you do that with X and Y and Z competitor
</details>

>> 谁是最便宜的，谁是最贵的？”结果它完全答错了。它把 Resend 的部分搞得非常糟糕，而且实际上说了很多对我们非常不利的话，比如“哦，Resend 的定价非常晦涩”。我当时就想，搞什么？完全不晦涩啊。呃，所以当时感觉超级沮丧。

<details><summary>Original English</summary>
>> who is the the cheapest and who who's the most expensive and it got completely wrong. He got the recent one like so bad and it it actually said like very bad things about us like oh recent pricing is very obscure. I was like what the Like it's not obscure at all. Uh so it was like super frustrating.
</details>

>> 哦，所以你们做了一个计算器。

<details><summary>Original English</summary>
>> Oh so you made a calculator.
</details>

>> 是的。问题在于，智能体不会真的去拖动 JavaScript 控件。

<details><summary>Original English</summary>
>> Yeah. So the the problem was you know agents don't really uh drag a JavaScript widget.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 于是我做的就是这个页面的 Markdown 版本，顺便说一句，它现在的访问量巨大，就像——

<details><summary>Original English</summary>
>> So then what I did was the the MT version of this page uh which has a tremendous amount of uh access by the way like now like
</details>

>> 你们能拿到这方面的分析数据。

<details><summary>Original English</summary>
>> you get analytics on this.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。是的。好的。

<details><summary>Original English</summary>
>> Yeah. Yeah. Okay.
</details>

>> 也不是通过常规的分析抓取点，因为我们无法追踪那个。

<details><summary>Original English</summary>
>> Not through the the the regular analytics spots too because like we cannot track that.
</details>

>> 对，是在服务端。

<details><summary>Original English</summary>
>> Yeah. It's a server side.
</details>

>> 所以我们得去 Datadog 里查明白。

<details><summary>Original English</summary>
>> So then like we got to go to data dog to figure that out.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 伙计，这真的很疯狂。呃，然后我做了那个改动，推上线了。几天后我又去问了一次，然后它给出的数字就对了。

<details><summary>Original English</summary>
>> And man it was really crazy like uh and then I made that change. I pushed that and then I asked again like a few days later and then he got the numbers right.
</details>

>> 原来如此。

<details><summary>Original English</summary>
>> I see.
</details>

>> 所以我就觉得，好吧，这——

<details><summary>Original English</summary>
>> So I'm like okay this
</details>

>> 这是实时更新并修复你网站内容的一种方式——

<details><summary>Original English</summary>
>> way to live update and fix stuff in your
</details>

>> 没错。这才是关键所在，对吧，比如——

<details><summary>Original English</summary>
>> Exactly. And and this is what matters right like okay
</details>

>> 这确实意味着你们没有单一事实来源，比如你必须更新 Markdown，然后你也必须更新——

<details><summary>Original English</summary>
>> it does mean that you don't have a single source of truth like you have to update the MD and then you also have to update the
</details>

>> 那确实很恶心。

<details><summary>Original English</summary>
>> that sucks completely.
</details>

>> 但话又说回来，如果我想要走省心、轻松的路，我就不会去做邮件业务了。所以我觉得这就是代价——

<details><summary>Original English</summary>
>> But again if if I wanted the the happy path and the easy path like I wouldn't be doing email. So I'm like that's the price of like
</details>

>> 嗯，你知道，如果你擅长 React，你可以写一个自定义渲染器，比如……是的，你知道怎么做这个。

<details><summary>Original English</summary>
>> well you know if you're good at react you can write a custom renderer that like yeah you know you know how to do this.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 迁移对比与竞品对抗

>> 我们还聊了哪些基准？基本上到处都有 FAQ，基础的 SEO 做法——

<details><summary>Original English</summary>
>> What else we talk baselines basically have FAQ everywhere basic SEO stuff
</details>

>> 对比页面，我们 vs SendGrid，我们 vs 呃——

<details><summary>Original English</summary>
>> comparison pages us versus sang grid us versus uh
</details>

>> 虽然我们的页面本来可以做得好得多，去看——

<details><summary>Original English</summary>
>> although our page could be much better go to
</details>

>> 是的，我注意到它没在那里。我的意思是，我相信你在某个页脚之类的地方肯定有。

<details><summary>Original English</summary>
>> yeah I notice it's not there. I mean I'm sure you have it somewhere in some footer or something or whatever.
</details>

>> 是的，直接输入 /migrate 就行。呃，我可以给你一些。

<details><summary>Original English</summary>
>> Yeah just do slashmigrate. Uh, I can give you some.
</details>

>> 顺便说一句，关于 404 页面，我总觉得我们应该去猜测——

<details><summary>Original English</summary>
>> By the way, 404 pages, I always think we should guess,
</details>

>> 比如推测 slug。

<details><summary>Original English</summary>
>> you know, pick the slug.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 最近邻。

<details><summary>Original English</summary>
>> Nearest neighbors.
</details>

>> 哦，是的。好的。

<details><summary>Original English</summary>
>> Oh, yeah. Okay.
</details>

>> 我的意思是，我认为有一个侧面——

<details><summary>Original English</summary>
>> I mean, I think there's a side
</details>

>> 万一你弄坏了某个 URL，它就能自动修复，对吧？你不会只是直接返回一个 404。我做那些页面的初衷是，“哦，让我尝试做一些不完全像对比页面的东西”，但我觉得……呃，那并不是个好主意，因为我们的竞品确实做了对比页面，而且他们被推荐的频次比我们更多。是的。

<details><summary>Original English</summary>
>> in case you any break a URL like it just auto fix itself, right? You don't you don't just serve the 404. My intention with those was like, "Oh, let me try to do something that's not exactly like a comparison page, but I don't think uh it was a great idea because it uh our competitors actually built the comparison pages and they get recommended more than ours." Yeah.
</details>

>> 但我们尝试做的是，比如你去 Postmark 的页面，好，让我们首先展示：“嘿，如果你想迁移，这里有一个代码转换器”——

<details><summary>Original English</summary>
>> But what we try to do like if you go to Postmark for example is like okay let's demonstrate first like hey if you want to migrate here's a code converter uh
</details>

>> 插入示例。

<details><summary>Original English</summary>
>> insert example.
</details>

>> 是的。所以你只要把任何代码块放在那里。哦——

<details><summary>Original English</summary>
>> Yeah. So if you just put any co code block there. Oh
</details>

>> 为什么，老兄？为什么啊？

<details><summary>Original English</summary>
>> why why dude? Why?
</details>

>> 这就是我们的做事风格。这就是我们的风格。

<details><summary>Original English</summary>
>> That's what we do. That's what we do.
</details>

>> 这也太浮夸、太卷了吧。

<details><summary>Original English</summary>
>> This is so extra.
</details>

>> 首页上都有一个立方体呢。一切都很过火。

<details><summary>Original English</summary>
>> There's a cube on the landing page. Everything is extra.
</details>

>> 不过像采用率页面，是我上个周末上线的。嗯，比如现在我们有一张图表，将我们的采用率与各个竞品进行对比。你看到了一件事，再次强调，这是我从定价页面学到的教训：JavaScript 控件是不会被执行的，所以我用文本把同样的数据逐字写了出来，以便大语言模型能真正读取到它。呃，所以——

<details><summary>Original English</summary>
>> But like the the adoption is one that I pushed this last weekend. Um like now we have a graph that compares like our adoption uh with every different competitor and you you see one thing like again this was a lesson that I learned with the pricing page JavaScript widgets they're not going to be executed so I spell out the same data in text so that uh LLMs can actually read that thing. Uh so
</details>

>> 我觉得它们在变得好一些。我看到很多智能体的使用方式。好，加载网站，点击图片，理解图片。虽然更慢，但是——

<details><summary>Original English</summary>
>> I think they're getting somewhat better. I see a lot of agentic use. Okay. Load load website, click on image, interpret image. It's slower. But
</details>

>> 是的，但在计算机操作方面，它们确实在变得好得多。我同意。但如果是获取信息并且只是对比内容，它们不会去那么做，对吧？

<details><summary>Original English</summary>
>> yeah, but with computer use, they are getting much better. I agree. But if you're fetching information and you're just comparing stuff, they don't they don't do that, right?
</details>

>> 我觉得它们正开始更多地转向计算机操作。我最近做了很多对比这个和那个的操作，浏览网站本身就很像计算机操作。

<details><summary>Original English</summary>
>> I think they're starting to go more towards computer use. I've been doing a lot of compare this and this and the browse of website is pretty computer use.
</details>

>> 好的。是的。我注意到你们似乎没有……你知道，另一种经典的 AEO 策略是：“这里教你如何将我们的产品与 Claude Code 连接”，“这里教你如何将我们的产品与 Codex 连接”——

<details><summary>Original English</summary>
>> Okay. Yeah. I noticed that you don't have like uh you know another classic AO tactic is like here's how to connect our thing with CL code here's how to connect our thing with codeex
</details>

>> AI 页面——

<details><summary>Original English</summary>
>> AI page
</details>

>> 哦，好的。

<details><summary>Original English</summary>
>> oh okay
</details>

>> 页面，好的。

<details><summary>Original English</summary>
>> page okay
</details>

>> 有一些挺有意思的事情，比如你去法律条款页面，resend.com/legal，上面任何一条比如“总结”或者“请求解释”——

<details><summary>Original English</summary>
>> there are some things that are interesting like if you go to the legal page so recent.com/legal any one of these like oh you summarize or ask to explain
</details>

>> 复杂度——

<details><summary>Original English</summary>
>> complexity
</details>

>> 我懂了，那只是一个外部链接，是的。

<details><summary>Original English</summary>
>> I see that's just an external link yeah
</details>

>> 是的，我……再次说明，不确定那是否有意义，但是——

<details><summary>Original English</summary>
>> yeah I Again, not sure that matters, but
</details>

>> 你多次提到了相比于传统 SEO，AEO 具有时效性。所以——

<details><summary>Original English</summary>
>> you mentioned a lot about recency for AEO compared to traditional SEO. So,
</details>

>> 是的，那正是我……刚开始时我超级好奇的事情。比如当时完全没有任何理由让任何模型推荐我们，因为我们在 SEO 方面太落后了。我们没有典型的词汇表页面之类的，或者那些纯粹为了 SEO 堆砌的泛泛之谈的文章。我当时就想弄清楚，这到底是怎么回事？我完全能看出来，至少在 Opus 4.5 上，在技术以及它们从何处获取数据方面，存在一种时效性偏差。我知道——

<details><summary>Original English</summary>
>> yeah, that was my like the the thing that I was super uh curious about uh in the beginning like there was no reason for any of the models to recommend us because we're so behind in SEO. We we don't have the typical glossery page or whatever like or articles that are so generic that were just like SEO heavy. And I was trying to uncover like what what is that? And I could totally tell like uh at least with Opus 4.5 there was a recency bias in terms of the the technology and where they were fetching data. I know
</details>

<!-- chunk 9/11 -->

### 搜索引擎与 AI 优化策略

最近他们说，可能 Rapid 并不一定是大家会推荐的东西了，但更新的工具确实开始频繁冒头，Resend 就是其中之一。正因为关于这款工具出现了大量非人工干预的内容，我们才会被更频繁地推荐。所以这里的建议就是，尽量让更多人在更多地方讨论你的产品，因为这绝对会产生影响。显而易见，我认为这是一类方法。我猜你找过 SEO 顾问或 AEO 顾问吗？他们有用吗？还是纯粹浪费钱？

<details><summary>Original English</summary>
recently

like

they

said

like

maybe

rapid

is

not

necessarily

um

something

that

people

suggest

anymore

but

definitely

like

newer

tools

uh

they

started

popping

more

and

recent

was

one

of

those

and

because

there

was

a

lot

of

I

don't

know

organic

content

about

the

tool

then

we

would

be

getting

recommended

more

so

the

advice

here

is

just

like

try

to

get

as

more

people

in

in

more

places

to

talk

about

the

product

as

possible

because

it

definitely

influences

Obviously,

I

think

that

is

a

class

of

it.

I

guess

did

you

ever

engage

SEO

consultants,

AO

consultants?

Are

they

useful?

Are

they

waste

of

money?
</details>

>> 我们其实从来没找过。

<details><summary>Original English</summary>
>> We

never

really

did.
</details>

>> 感觉你全都是自己一手包办的。

<details><summary>Original English</summary>
>> You

seem

like

you're

just

doing

everything

yourself.
</details>

>> 你是2024年发推聊这事的人，我觉得你是最早关注到这个的人之一，你知道吧。

<details><summary>Original English</summary>
>> You're

the

2024

tweet

of

let's

talk

about

I

think

you

were

one

of

the

first

ones

to

to

pick

it

up,

you

know.
</details>

>> 对。我是说，我觉得大家普遍目前的情况是，因为我们当时做过一期关于 AEO 或 GEO 相关的节目，当时大多数人觉得，像平常做 SEO 那样做就行，而且我觉得别去屏蔽 AI 聊天机器人。然后大多数工具，比如当时的 Profound，它们也就是追踪你的提及次数，然后让你做做实验之类的。所有这些手段都是寻常套路，很正常。我只是想说，显然大家也一直在私信我，因为我同时也在做 AEO 实验，关于该怎么做。

<details><summary>Original English</summary>
>> Yeah.

I

mean,

I

think

people

generally

the

state

of

things

we

because

we

did

an

AEO

or

GEO

episode

at

the

time

around

this

stuff

and

most

people

were

like

just

do

what

normal

SEO

does

>> and

don't

block

AI

chatbots,

I

think.

And

then

most

most

tools

like

profound

at

at

the

time,

they

would

just

like

track

your

mentions

and

then,

you

know,

let

you

do

experiments

and

all

those

things.

All

those

things

are

part

for

the

course

and

normal.

I

I'm

just

trying

to

obviously

like

people

are

pinging

me

cuz

I'm

also

doing

AO

experiments

>> on

like

what

to

do.
</details>

>> 我有一个天然优势，因为我做的是内容生意。所以我显然能源源不断地产出内容，而你是实打实有一款产品。

<details><summary>Original English</summary>
>> I

have

unfair

advantage

cuz

I'm

a

content

business.

>> So

obviously

I

pump

out

content

whereas

you

actually

have

a

product
</details>

>> 但我想知道这多大程度上对你也很重要？比如你现在发展得非常好，但你会在多大程度上追踪文档的使用情况？相比竞品，我们被推荐的频率有多高？老兄，我觉得这太关键了，因为以前如果我们对该选哪款工具有点拿不准，我们会去问 Google，然后你会进入那些对比页面，或者你会看到排名前三的结果。而现在你直接就能得到一个答案，对吧？如果你问我该用哪款工具，大家肯定只想选那个最顺畅、阻力最小的。

<details><summary>Original English</summary>
>> but

I

guess

how

important

is

it

to

you

too?

Like

you're

very

winning

but

how

much

do

you

keep

a

track

of

how

well

are

docs

used?

How

often

are

we

recommended

compared

to

competitors?

Like

man,

I

think

it's

so

crucial

because

before

we

if

we

want

if

we're

like

a

little

bit

unsure

about

which

tool

to

use,

we

would

ask

Google

and

then

you

would

get

to

like

those

comparison

pages

or

you

would

get

like

the

first

three

responses

and

now

you

just

get

the

one

response

out

of

the

gate,

right?

if

you're

asking

which

tool

should

I

use

and

yeah

people

just

want

to

go

with

the

the

one

that

is

the

most

frictionless

and
</details>

>> 对，所以我觉得免费层级非常重要。而且我认为 WorkOS 的 Michael Grinich 一直在努力推广 AuthKit 这个概念，对吧？我不知道你见没见过这个，就是那种理念，也很类似，你不需要账户就能完成基础操作。这就属于对你产品的未授权使用，这显然非常危险，因为它容易被滥用，但它确实是最简单的无注册门槛。

<details><summary>Original English</summary>
>> yeah

which

I

think

free

tier

is

very

important

and

um

I

think

uh

Michael

Grenage

from

work

OS

is

trying

to

promote

this

idea

of

off

MD

right

I

don't

know

if

you

seen

this

so

so

uh

the

idea

that

you

it's

very

similar

to

as

well

where

you

don't

need

an

account

to

to

do

the

basic

action

>> so

it's

like

unauthenticated

usage

of

your

product

which

very

dangerous

obviously

because

it's

prone

abuse,

but

uh

it

is

the

the

easiest

like

no

sign

up.
</details>

>> 对，这也正是我在纠结要不要做的事情。我们需要开通 Provisioning API 吗？我一直在这个问题上反复摇摆，比如好吧，把这叫做配置和声明，对吧，这是配置和声明，但接着是免费层级。是啊，我不知道这是不是我们行业的某种特性，但……

<details><summary>Original English</summary>
>> Yeah,

that's

the

thing

that

I'm

I'm

try.

Yeah,

I'm

debating

doing

that

or

not.

Do

we

need

a

provisioning

API?

And

I

keep

going

back

and

forth

uh

on

this

like

okay

call

this

>> provisioning

and

claims

right

is

that

provisioning

and

claims

but

then

free

tier.

Yeah.

Like

I

don't

know

if

it's

something

about

our

industry

but

there
</details>

>> 是的，你就是会遇到滥用。对。

<details><summary>Original English</summary>
>> Yeah.

You

just

have

abuse.

Yeah.
</details>

>> 对，就是会面对大量滥用。

<details><summary>Original English</summary>
>> Yeah.

Just

have

a

lot

of

abuse.
</details>

### 自动化实验与监测闭环

>> 是啊，好吧。我觉得这些就是主要的策略了。我觉得另一件可以让听众去思考的事，就是直接把你的 Clanker 接入你的分析系统和代码库，对吧？你必须把整个闭环彻底打通，然后基本实现自动化调研，对吧？就像我现在跑的流程：我有一个由 Latent 驱动的 CMO Agent，对吧？它们会派生其他 Agent，它们的工作就是调研想法，追踪我们尝试过的东西。然后我会审批我们想要实验的项目。我们有一个实验窗口期，去具体跑这些实验，然后由其他 Agent 负责监测它们。所以我觉得这算是一种做这类事情的自动化调研循环。我认为接下来你还需要给它工具，比如我订阅了 Ahrefs，订阅了 DataForSEO。

<details><summary>Original English</summary>
>> Yeah.

Okay.

Yeah.

I

I

mean

I

I

think

those

are

the

the

main

tactics.

I

I

think

the

other

thing

that

uh

I

would

just

tell

listeners

to

think

about

is

literally

hook

your

clanker

up

to

your

analytics

and

your

codebase,

right?

Like

you

need

to

like

fully

complete

the

loop

and

then

like

basically

auto

research,

>> right?

Like

like

this

like

so

what

I

have

now

is

my

cycle.

I

have

both

lat

I

have

a

latency

CMO

agent,

right?

and

they

spawn

other

agents

or

they

their

job

is

to

like

research

ideas,

keep

track

of

things

that

we've

tried.

Well,

and

then

I

sign

off

on

like

things

that

we

want

to

experiment.

We

have

we

have

an

experiment

window.

We

go

and

do

the

experiments

really

and

then

those

are

other

agents

that

then

moni

are

monitored

by

them.

So,

uh

I

would

say

that's

like

kind

of

like

the

auto

research

loop

for

doing

this

stuff.

Uh

I

think

then

you

also

need

to

give

it

tools.

So

like

I

signed

up

for

AHFS,

I

signed

up

for

data

for

SEO.
</details>

>> 噢，对。

<details><summary>Original English</summary>
>> Oh

yeah.
</details>

>> 然后最近我自己做了一个 AEO 追踪器，这个你也可以自己做。

<details><summary>Original English</summary>
>> And

then

uh

most

recently

I

made

my

own

AEO

tracker

which

which

you

can

make.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 然后，你无非就是想让数据往上涨。

<details><summary>Original English</summary>
>> Um

and

then

yeah,

you

just

want

to

make

the

number

go

up.
</details>

>> 确实是这样。而且你其实并不清楚到底什么起效，对吧？就像是在乱枪打鸟。所以就像，法务页面上的那个东西有用吗？我完全不知道。但我会继续胡乱尝试各种方法，看看会有什么效果。

<details><summary>Original English</summary>
>> Yeah,

for

sure.

And

it's

like

you

don't

know,

right?

Like

you're

throwing

things

at

the

wall.

That's

why

like

Yeah.

The

thing

on

the

legal

page,

does

that

matter?

I

have

no

idea.

But

I'll

I'll

keep

throwing

things

at

the

wall

and

seeing

what
</details>

>> 我觉得像 Reddit 就无关紧要。Hacker News，你以前在 Hacker News 上挺火的，现在没那么火了。

<details><summary>Original English</summary>
>> I

think

like

uh

Reddit

doesn't

matter.

Hacker

News.

You

you

used

to

be

big

on

Hacker

News.

No

less.
</details>

>> 对，现在不了。

<details><summary>Original English</summary>
>> Yeah.

Not

anymore.
</details>

>> Twitter 也没那么重要了。

<details><summary>Original English</summary>
>> Twitter

doesn't

matter

as

much.
</details>

>> 是的，挺奇怪的，确实。

<details><summary>Original English</summary>
>> Yeah.

It's

weird

like

like
</details>

>> 太疯狂了。

<details><summary>Original English</summary>
>> it's

so

crazy.
</details>

>> 你有追踪器吗？

<details><summary>Original English</summary>
>> Do

you

have

a

tracker?
</details>

>> 没有。市面上类似 Profound 那类的工具我们都在用。还有其他产品，所以我们全试了一遍。经常有人问我：我是该用 Godge 还是 Profound 还是另一个？我说我们一口气买了四个订阅。

<details><summary>Original English</summary>
>> No.

Like

we

use

all

of

those

profounds

of

the

world.

Uh

there

are

other

products.

So

we

tried

them

all.

Like

people

ask

me

like

oh

should

I

use

godge

or

or

profound

or

this

other

one?

I'm

like

yeah

we

have

four

subscriptions
</details>

>> 你懂的，现在就是得这样。你得看看哪个最好用。我觉得这类工具缺少的是：直接告诉我下一步该干嘛。我认为问题在于，它们给不出具体该做什么的建议，因为它们自己也还在摸索需要发生什么，对吧？比如建议写篇维基百科文章之类的。

<details><summary>Original English</summary>
>> you

know

like

that

that's

what

it

takes

now.

Like

you

you

got

to

see

which

one

works

best.

What

I

miss

from

those

tools

is

like

give

me

the

action.

And

I

think

that

the

problem

they

don't

they

don't

give

you

like

what

to

do

because

they're

also

trying

to

figure

out

what

what

needs

to

happen

right

like

oh

write

an

article

on

Wikipedia

like

yeah
</details>

>> 是的，像 Moz 那种老派的 SEO 工具在这些事情上反而会有更明确的观点。现在的 AEO 工具，大部分据我所听到的（当然我也不是专家，我们或许应该去问问 Profound），它们本质上只是报告工具，属于分析报告工具。这也无可厚非，这是一门大生意。

<details><summary>Original English</summary>
>> yeah

I

would

say

like

the

old

school

SEO

tools

like

Moz

and

all

those

kinds

they

will

actually

have

more

more

opinionation

around

these

things

right

now

the

AO

tools

mostly

from

what

I

hear

again

I'm

not

an

expert

we

should

probably

talk

to

profound

>> is

that

they

just

are

reporting

tools

right

they're

analytics

reporting

tools

and

uh

that's

that's

fine

it's

a

big

business.

Exactly.
</details>

>> Ahrefs 是一家新加坡公司，据说他们年营收好像能做到三四亿美元。

<details><summary>Original English</summary>
>> HFS

is

a

Singapore

business

and

apparently

they

do

like

I

don't

know

$3

400

million.
</details>

>> 确实是。

<details><summary>Original English</summary>
>> Yeah,

totally.
</details>

>> 嗯哼。

<details><summary>Original English</summary>
>> Uh-huh.
</details>

### 企业级销售与产品构建

>> 至于你业务的其他部分，我们接下来会聊聊育儿和个人生活方面。但我真的很想问问，你看起来非常淡定。你拥有50名遍布全球的远程员工，你在操心 MCP，你在操心 AEO。但这总不可能就是你拿下所有这些大客户的方式吧，对吧？你那些吃着牛排大餐、打着高尔夫球的高级销售人员都在哪儿呢？

<details><summary>Original English</summary>
>> The

other

parts

of

your

business

like

we're

going

to

talk

about

like

the

parenting

side

and

personal

side.

>> I

just

really

want

to

be

like,

okay,

you

you

seem

very

chill.

You

you

have

50

people

remote

all

around

the

world.

You

are

worrying

about

MCP.

You're

worrying

about

AEO.

That

cannot

be

the

way

you're

closing

all

these

big

customers,

right?

like

where's

your

fancy

sales

guy

with

the

steak

dinner

and

the

golf

course?
</details>

>> 我们才刚开始做这一套动作。而且我觉得我们非常幸运，在没有这套销售体系的情况下能走得这么远。我以前在一家只做纯企业客户的公司工作过，所以我清楚那需要些什么，包括牛排大餐，围绕那种销售体系或赋能所需的一整套支撑机制，这些都是我需要的。我知道当时机成熟时，我们必须启动那个关键杠杆，但我在 Resend 内部对此一直非常谨慎，在不同层面上循序渐进，而不是一下子扩充20个人。我非常小心，也许是因为我们是全远程团队，但我觉得我们对团队文化极其保护，比如要确保我们不会一下破坏原有的文化，所以不盲目扩张，而是努力去寻找合适的人。所以我们现在刚招了一名销售，效果一直不错，进展非常顺利。

<details><summary>Original English</summary>
>> We're

just

starting

that

motion.

Uh

and

I

think

we

are

uh

very

lucky

that

we're

able

to

go

this

far

without

having

that

motion.

I've

worked

at

a

enterprise

only

company

in

the

past.

So

I

knew

what

does

that

take

and

the

steak

dinners

like

all

the

the

apparatus

around

like

that

sales

or

the

enablement

there's

all

these

things

that

that

I

needed.

I

knew

that

okay

when

it

when

the

time

is

right

we're

going

to

have

to

turn

on

that

key

but

I've

been

very

cautious

about

doing

that

at

recent

like

in

different

layers

instead

of

just

like

add

20

I'm

very

maybe

it's

because

we

are

remote

but

I

think

we

are

very

protective

about

the

culture

like

let's

make

sure

we

don't

damage

the

culture

at

once

so

no

let's

try

to

figure

out

people

who

fit

so

we

just

have

one

a

now

and

it's

been

helping

it's

been

yeah

going going

super

Yeah.

Good

enough.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我觉得，一旦你通过两三个大单把 ARR 翻了一倍，你就会意识到，是时候了。

<details><summary>Original English</summary>
>> I

I

would

say

I

think

you

know

once

you

have

like

you

know

you

double

your

AR

because

of

like

a

couple

deals

you're

like

okay

like

this

is

a

good

time.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 因为人们愿意为了某些诉求向你支付更多费用，比如要求签署协议，或者要求软件部署在本地私有化环境，或部署在自己的 VPC 里等等。对吧。

<details><summary>Original English</summary>
>> Cuz

people

want

to

pay

you

more

>> for

things

that

you're

like

okay

well

you

know

uh

I

have

like

the

agreement

with

you.

I

have

like

your

software

on

my

premises

or

in

my

VPC

whatever.

Right.
</details>

>> 确实是这样。

<details><summary>Original English</summary>
>> Um

so

>> for

sure.
</details>

>> 是的，而且我体会到的另一点是，你其实是在打造一款截然不同的产品。这就是你必须具备的视角：这不仅关乎在公司内部搭建一套不同的组织运转机器，比如在设计公司架构时，规划设立哪些部门、谁坐什么位置、每个人如何能更好地胜任工作。不，对于企业级客户来说，这实际上是完全不同的产品。他们所关心的东西，跟20美元付费用户关心的东西天差地别。如果我只是简单接入 WorkOS、单点登录（SSO）、SCIM 和审计日志，根本就远远不够。所以绝不是在定价页面上罗列出这几项功能就万事大吉了。所以这确实是一段探索历程。在进入个人生活话题之前，关于这段历程你还有其他想要总结反思的吗？

<details><summary>Original English</summary>
>> Yeah.

And

it

what

I'm

learning

too

is

like

you're

building

a

different

product.

So

that's

what

how

you

need

to

see

it's

not

only

I'm

building

a

different

machine

internally

as

a

company

as

I'm

designing

the

company

I'm

designing

okay

which

department

who

sits

where

how

each

person

is

is

better

equipped

to

do

their

job.

No,

like

for

an

enterprise

it's

actually

a

different

product.

Like

what

do

they

care

is

very

different

from

what

$20

users

care

and

if

I

just

add

you

know

work

OS

and

SSO

and

and

scam

and

audit

logs

it's

not

going

to

be

enough.

So

it's

it's

not

just

putting

those

items

on

the

on

the

pricing

page.

Um

so

it's

a

journey

for

sure.

Any

other

things

you

want

to

reflect

on

the

the

journey

before

we

go

into

the

the

personal

side?
</details>

>> 没有了，我觉得我们聊得已经很全面了。噢，

<details><summary>Original English</summary>
>> No,

I

think

yeah,

we

covered

a

lot

of

ground.

Oh,
</details>

>> 好吧。那我谈谈我的使用场景，对吧？比如我是一个内容创作者。挺好。

<details><summary>Original English</summary>
>> okay.

Then

I'll

talk

a

little bit

about

my

use

case,

right?

Like

I'm

a

content

creator.

Nice.
</details>

>> 对，你是

<details><summary>Original English</summary>
>> Right.

You're
</details>

<!-- chunk 10/11 -->

我猜你们业务的大头是事务性邮件。我大概能去查一下，不过……
<details><summary>Original English</summary>the bulk of your business, I assume, is transactional email. I I probably could look it up, but I</details>

>> 没错。
<details><summary>Original English</summary>>> That's right.</details>

>> 你们有营销邮件，也有入站邮件。我敢肯定那在业务里算比较小的一部分。我每年向 Substack 支付大概 10,000 美元
<details><summary>Original English</summary>>> You have marketing emails, you have inbound emails. I'm I'm sure that's like sort of less outside of the business. I pay Substack something like $10,000 a year</details>

>> 发送我的邮件，这看起来太贵了。
<details><summary>Original English</summary>>> to send my emails and that seems too high.</details>

>> 是的。
<details><summary>Original English</summary>>> Yeah.</details>

>> 所以我在想，为什么营销邮件和事务性邮件会有这么大的区别？
<details><summary>Original English</summary>>> So I think like why why is marketing email versus transactional email so different?</details>

>> 问得非常好。嗯……
<details><summary>Original English</summary>>> It's a great question. Um</details>

>> 因为你们的商业模式也不一样，对吧？如果你点击……
<details><summary>Original English</summary>>> cuz your business model is also different, right? If you click</details>

>> 它确实是，它确实也是更贵的。
<details><summary>Original English</summary>>> it is it is more expensive too.</details>

>> 是啊，当时我就觉得我做不来这个。
<details><summary>Original English</summary>>> Yeah. Then I was like I can't do this.</details>

>> 是的。这个行业有这样一种模式，就是按联系人收费。这是第一点。所以他们定价的方式是围绕你在每个联系人上创造的价值。但现在很疯狂，比如我们服务的 AI 公司，他们增长太快了。就像 Mistro 使用 Resend。好的，他们增加的用户量简直是不可思议。所以按联系人定价的商业模式有点走不通了，我们意识到了这一点，也在努力修正它。但过去一直都是这样的。还有一点就是，发送事务性邮件时，就像是把一条消息放进队列，然后移出队列。而做营销邮件，你需要构建那一整套引擎，比如分批、批次之间的间隔、分析、在发送过程中提速或减速，可能还要拦截。所以……
<details><summary>Original English</summary>>> Yeah. The industry has this pattern of like charging per contact. That's the first thing. So the way they they try to price is around the value you create in each contact. But now it's crazy like the the AI companies that we serve, they grow so fast. Like uh Mistro uses recent. Okay. So they're like the amount of users that they add is just insane. So like the business model of contactbased pricing is kind of broken and we are realizing that and trying to fix that too. But that's how it had always been. And there's something about like when you send a transactional email, it's just like put a message in a queue and get out of the queue. With marketing email, you you're building that engine of like batches and intervals between batches, analyzing, increasing the speed, decreasing the speed as the sending is going, maybe blocking. So</details>

>> 一次发送邮件是否存在一个速率上限？
<details><summary>Original English</summary>>> is there is there a max rate you should send emails at a time?</details>

>> 是的，肯定有。具体到每个域名。是的。
<details><summary>Original English</summary>>> Yeah, for sure. Per domain uh specifically. Yeah.</details>

>> 好的。比方说我有 10 万封邮件要发出去，应该花我 10 分钟。
<details><summary>Original English</summary>>> Okay. So like let's say I have um 100k emails to send out. It should take me 10 minutes.</details>

>> 是的。比如现在以我们拥有的 430 万用户来说，需要花一天以上，然后你就会觉得：“啊，什么？不行，这无法接受。”
<details><summary>Original English</summary>>> Yeah. And it for example now with the 4.3 million users that we have, it takes more than a day and you Oh, what? No, that's unacceptable.</details>

>> 确实是这样。
<details><summary>Original English</summary>>> Yeah, for sure.</details>

>> 那我就多付钱给你们，换到一个不同的队列里去。
<details><summary>Original English</summary>>> So then I pay you more to get in a different queue.</details>

>> 是的。好的。所以你必须总是在想办法：“好的，我们需要让更多邮件发出去。”那这具体是怎么运作的？
<details><summary>Original English</summary>>> Yeah. Okay. So you you have to be like always trying to figure out, okay, we need more at the door. So how does that work?</details>

>> 是的。对，对。噢，那很有意思。这就像是……比如 token 上限的速率限制。
<details><summary>Original English</summary>>> Yeah. Yeah. Yeah. Oh, that's interesting. It's like uh rate limits for let's say token limits.</details>

>> 是的，完全正确。
<details><summary>Original English</summary>>> Yeah. Exactly.</details>

>> 我的重置按钮在哪里？
<details><summary>Original English</summary>>> Where's my reset button?</details>

>> 是的，没错。
<details><summary>Original English</summary>>> Yeah, exactly.</details>

### 家庭与创业的权衡

>> 是啊。你还……你进了 YC，创办这家公司时还是个年轻的父亲。我觉得部分原因在于，旧金山有很多没孩子的人。我觉得这是考量的一部分。我想很多正在听节目的人可能会觉得：“我没法当创始人，我有这么棒的想法，但我有年幼的家庭。”你是怎么平衡的？
<details><summary>Original English</summary>>> Yeah. You also like you went into YC, you started this company as a young father and I think like part of things like uh there are a lot of no kids people in in SF. Uh and I think that's part of the consideration. I think a lot of people are listening who are like I can't be a founder like I have this great idea but like I got I got young family. How you manage?</details>

>> 得先说一下前提，你离开旧金山是因为……
<details><summary>Original English</summary>>> You got to preface with you left SF for</details>

>> 是的。
<details><summary>Original English</summary>>> Yeah.</details>

>> 孩子。是的，这是最近的消息，我现在更多时间呆在巴西，因为我们在期待第二个孩子。我觉得一开始，天哪，太疯狂了。因为我来旧金山的时候，我女儿才一岁，我身边的每个 YC 创始人对生养孩子到底意味着什么完全没有任何概念。
<details><summary>Original English</summary>>> kids. Yeah. So this is the recent news like I'm spending more time in Brazil now because we're expecting our second kid and I think at first man it was crazy because I came to SF my daughter was one year old and every YC founder around me had no idea like yeah what does it mean to have kids and</details>

>> 繁衍后代是怎么一回事？
<details><summary>Original English</summary>>> what is this reproduction</details>

>> 你连 B 轮都还没融到，怎么就结婚了？
<details><summary>Original English</summary>>> you don't you don't even have series B like what are you doing married like</details>

>> 完全是这样。他们大多数根本就没结婚。这很不可思议，我想……再一次，我总是尝试去看待这些事情。一开始你把这些看作是一种劣势，心想：“天哪，这些人全都是麻省理工出来的，来自所有这些名校。”我可不是这样。“噢，他们没结婚。”我也不是这样。“他们没有孩子。”我也不是这样。但在参加那个项目时，我想的是：“天哪，我只想做出这个 batch 里最优秀的公司。不是第四名、第五名，而是 250 家里的第一名。”
<details><summary>Original English</summary>>> totally Most of them weren't married at all. And it it's crazy how um I think it again I always try to look at those things. At first you you see them as a the advantage like oh man all of these guys they went from like they came from MIT all these amazing schools. That was not the case for me. Oh they don't have they they are not married. That's not the case for me. They don't have kids. That's not the case for me. But still going for that program, I'm like, man, I'm I just want to build the best company on this batch. Not number four, number five, like number one out of the 250.</details>

>> 噢，是的。
<details><summary>Original English</summary>>> Oh, yeah.</details>

>> 哪一期的？
<details><summary>Original English</summary>>> Uh, which cohort?</details>

>> 2023 冬季班。
<details><summary>Original English</summary>>> Winter 2023.</details>

>> 好的。
<details><summary>Original English</summary>>> Okay.</details>

>> 你在这个过程中意识到，YC 里并没有所谓的赢家，根本没有这回事。
<details><summary>Original English</summary>>> You realize in the middle of that is that there's no winner in YC that there's no such thing.</details>

>> 嗯，
<details><summary>Original English</summary>>> Mer,</details>

>> 但是……
<details><summary>Original English</summary>>> but like</details>

>> 我现在正在翻看 2023 冬季班的名单，看看我认识谁。
<details><summary>Original English</summary>>> I'm I'm pulling a winter 23 now. Let's see who I know.</details>

>> 是的。尤其是你明白……
<details><summary>Original English</summary>>> Yeah. And especially what you understand is that uh</details>

>> 2022 冬季班……
<details><summary>Original English</summary>>> winter 2022 batch</details>

>> 这就像一场无限游戏，对吧？即使你在那期表现极其亮眼，拿到了最大的一笔融资，那也无关紧要，因为生活还在继续，还在向前走。我在那里认识的许多人，现在都已经不在这个赛场上了。
<details><summary>Original English</summary>>> it's like an infinitive infinite game, right? Like those even if you had an amazing batch and you raised the biggest round, it doesn't matter because like life goes on and it continues and many of the people that I met there, they are not here anymore.</details>

>> 是啊。
<details><summary>Original English</summary>>> Yeah.</details>

>> 联合创始人闹崩、经历七次转型，然后公司死掉了，对吧？但我们还在这里。所以我当时态度非常明确，不不不，甚至在买 resend.com 域名的时候，我就觉得它必须是一个很棒的网站，配上很棒的 .com 域名，绝不要做成 .io 或者别的什么，对吧。但在有孩子的情况下做这些真的太难了，尤其是因为我想陪伴我的大女儿。我真的深入思考过这件事，在 YC 期间有那么一个时刻——这个故事正好能说明我接下来要讲的意思——我去了这个活动，PG 也在场。我当时心想：“天哪，保罗·格雷厄姆，万物之父，上帝就在这里，对吧？”所有人的注意力都在 PG 身上。然后他说：“你们知道吗？我们总是告诉你们别做这件事，我们作为合伙人这么跟你们说，结果你们转头还是去做了，然后几个月后跑来找我们说：‘噢，我好后悔做了这个，或者后悔没做那个。’”他就这么说了这番话。于是我找到我的合伙人们问：“好的，我现在做的哪些事情是你们觉得我不该做、你们觉得是错的？”然后有一位合伙人，不是我的主要合伙人，而是另一位合伙人对我说：“你就是太在意设计了，你在这上面花的心思太多了。如果你不在意那个，你现在的进度会领先得多。”这让我特别难受，因为他说的是真的。比如我去路演时用的幻灯片，非常漂亮，而他说：“这根本不重要。”我说：“是，我现在知道它不重要了。”但这确实深深伤到了我。过了几天，我反思这件事，我想：“是的，但如果我做出来的产品带着这样的品牌调性，哪怕只有 1000 个人用，我也宁愿这样，而不是做一个有 10000 个人用、但我自己都不想用、我自己都不去碰的产品。所以，管他呢，我要坚持我认为对的事情。”而且我觉得在这个行业里——再回到这个行业来说——每个人的产品都很糟糕，融入的设计感都不够。所以我感觉那是一个差异化亮点，而在这样一个拥挤的市场里，我们需要差异化。因此，面对我的孩子我也是这样想的。比如，10 年之后，我和我女儿在一起，我女儿非常黏我，我们总是一起玩，而我们是一家年经常性收入 1000 万美元的公司。我宁愿生活在这样的现实里，也不愿生活在另一种现实中：我们成了上亿美元的公司，但我女儿不想跟我玩，对我没兴趣，我们关系并不亲密。所以这就是我做的决定。也许是对的，也许是错的，我完全不知道。我工作极其拼命，我非常有野心，这并不会阻止我前进或怎么样，但是确立好这些优先级，想清楚什么适合自己，我认为这很重要。所以是的，她现在比以往任何时候都更重要，她是我的首要考量，我给予她极高的优先级。
<details><summary>Original English</summary>>> Co-founder breakups, seven pivots and they're dead, right? But we are here. So I I was very much like no no no we're even the domain when we bought recent.com like no it's going to be an amazing website with an amazing.com like it's not going to be aio or whatever right um but doing that with kids was so freaking hard especially because I wanted to enjoy my my first daughter and I really thought about this like there was one point during YC so this story like translates to what I'm going to say I came to this event and PG was there. So I'm like, "Oh man, Paul Graham, the father of everything. God is here, right?" So everybody is paying attention to PG. And then he says, "You know what? We always tell you don't do this thing. We we tell you that as partners and then you ended up doing the thing and then months later you come to us and say, oh, I regret doing this or not doing this." So So he just said that. So then I came to my partners and I asked like okay what are the things that I'm doing now that I shouldn't be doing that you think it's wrong and then one partner not my main partner but another partner told me like you just worry too much about design you care too much about that if you didn't care about that you'll be much further ahead and that hurt me so bad because it was true like my slides when I was like pitching it was like a beautiful slides and he's like doesn't matter I'm like yeah now I know it doesn't matter But like that hurt really bad. And then a few days later, I was reflecting on that. I'm like, "Yeah, but if I if I were to build a product uh that had like this identity and only 1,000 people used, I prefer doing that than having a product with 10,000 people that it's a product that I don't want to go, that I don't use myself. So, you know what? I'm going to follow what I believe is right." And I think in this industry again going back to the industry everyone had terrible products. There was not not enough like design infused into them. So I felt that was a differentiator and we needed a differentiator in such a crowded market. So, I go back to that for my kid, too. Like, okay, 10 years from now, I have I'm with my daughter and my daughter wants to be with me so much and we we play all the time and we are 10 million AR company. I would rather live in that reality than live in a reality where we're hundred million dollar company and my daughter doesn't want to play with me. It's not interested in me and we're not that close. So that's the decision I made. Maybe it's right, maybe it's wrong. I have no idea. I go extremely hard. I I have a lot of ambition. That's not going to stop me or or anything, but like setting up those priorities and figuring out for yourself like what works for me. I think it was important. So yeah, more than ever like she's the most important thing for me and I I I prioritize her a lot.</details>

>> 你怎么把那一点和你的雄心平衡起来？对吧。比如我也有类似的情况，虽然程度较轻。我没有孩子，但……是的，我有很多充满野心的事情，我也有一个我应该花时间陪伴的家庭。而当我陪着他们的时候，我的心思却不在现场。我盯着手机，心里在想：“噢，我应该去关注 Astra，或者 GPT-6 之类的。”这就好比……你知道的，AGI。
<details><summary>Original English</summary>>> How do you balance that with your ambition? Right. like I also have this in a smaller way. I don't have kids but uh yeah I have a lot of ambitious things and I have a family that I should spend time with and when I spend time with them I'm not present. I'm looking at my phone. I'm like saying like, "Oh, I should be reviewing Astra, you know, GPT6." Like, it's it's like, you know, AGI.</details>

>> 不，这样不对。比如……
<details><summary>Original English</summary>>> No, it's not right. Like,</details>

>> 比如，但我心里真的觉得我应该在工作，然后，你知道的，而且……
<details><summary>Original English</summary>>> like, but I really feel like I should be working and, you know, and like</details>

>> 是的。
<details><summary>Original English</summary>>> Yeah.</details>

>> 同时我又感到内疚，然后……结果就是我在两方面都不快乐。
<details><summary>Original English</summary>>> at the same time like I feel guilty and then and so like I'm unhappy in both areas.</details>

>> 完全如此。我就是这种感觉。我感觉自己是个糟糕的父亲，是个糟糕的丈夫，是个糟糕的 CEO，感觉自己在生活的每一个领域都一败涂地。我确确实实就是这种感觉。但每一天我都努力让自己更多地全身心投入。你知道的，尤其是当你在家工作的时候，天哪，你离开你的办公室，然后现在你成了一名父亲，接着转眼又不是了。噢，现在你又得当一个丈夫，去关心你的妻子。就像，还有你的……
<details><summary>Original English</summary>>> Totally. And and that's how I feel. I feel like I'm a terrible dad. I'm a terrible uh husband. I'm a terrible CEO. and like you're failing in every single area of your life. I feel that way ex exactly like that. But every day I try to be a little bit more present, you know, and it's a especially when you're working from home like man, you leave the your your your office and then now you now you're a dad and then now you're not anymore. Oh, now you got to be a husband and pay attention to your wife. Like and your</details>

<!-- chunk 11/11 -->

你的想法就像是，“天哪，我该怎么做这个企业级业务？比如我必须拿下这笔交易。”我觉得我也总是这样循环。我们都在同一条船上。

<details><summary>Original English</summary>
your mind is like, "Oh, man, how I do this enterprise? Like I got to close this deal. I feel like I cycle all the time, too. We're in the same boat.
</details>

>> 是的。没错。这绝不容易。而且我觉得，为你的品类准确命名是很重要的。人们其实并没有对“品类开创”（category creation）做足够深入的思考。我觉得这有点奇怪地类似于 Netlify 试图用 Jamstack 去做但失败了的事情；而且我认为更多人真的应该去尝试做品类开创，因为一旦他们成功了，他们就拥有了整个领域。嗯，所以就像我们最近所做的，你可以称之为下一代 SendGrid，对吧，或者是 AI 原生的 SendGrid 之类的。

<details><summary>Original English</summary>
>> Yeah. Yeah. Well, never easy. And I think like just naming the thing for your category is important. And people don't really think about category creation enough. I think uh this is something weirdly something like that Netifi tried to do and failed with Gemstack and I think that more people should really actually try to do a category creation because when they're successful then they own the whole thing. Um so which which which we did for this recent you know it is the next generation sang grid let's call it right or like AI native sang grid something like that
</details>

>> 我觉得，你知道，这可能是我说得太坦白了——

<details><summary>Original English</summary>
>> I I think that uh you know and you know this is like being me being like probably too honest
</details>

>> 那还不是品类开创。

<details><summary>Original English</summary>
>> that is not category creation yet
</details>

>> 但那是品类主导。你知道，就像你拥有了自己的品类，这很好，但这还不够清晰地体现出差异所在。所以我经常举的一个经典例子是我们的另一位嘉宾，来自 HubSpot 的 Dharmesh。

<details><summary>Original English</summary>
>> but it is category dominance you know like you own your category that's good but like it is not clear enough yet what is difference so my classic example is another guest that we've had um Dorsha from HubSpot Yeah,
</details>

>> 任何想思考品类开创的人，都可以去读一读关于入站营销（inbound marketing）与出站营销（outbound marketing）的内容，看看他们是如何开创“入站”这个品类的。品类开创的理想状态是，一旦你听到了这个品类，也就是代表你公司的这两个词，你就不会再想要别的了。

<details><summary>Original English</summary>
>> anyone who wants to think about category creation, go and read up about inbound marketing versus outbound marketing and how they created the category of inbound. The the ideal phrase of cate of category creation is once you've heard the category, the two words that your company represents. You don't want anything else.
</details>

>> 没有长篇大论的文章。没有冗长的宣言。没有演讲。就只有两个词。也许再加上一些例子。仅此而已。你的受众就能顺理成章地理解了。嗯。这非常难。

<details><summary>Original English</summary>
>> There's no long essay. There's no long manifesto. There's no talk. There it's just two words. Maybe some examples. That's it. The the your audience can take it from there. M. It's very hard,
</details>

>> 兄弟，我见过朋友们尝试去这样做。比如做 Webhooks 即服务（webhooks as a service）的 Svix。

<details><summary>Original English</summary>
>> man. I've seen friends trying to do that. Like Zix uh from uh it's a web hooks as a service.
</details>

>> 是的，他们用了我的名字。

<details><summary>Original English</summary>
>> Yeah, they took my name.
</details>

>> 是的，老兄。这真的太难了，对吧？比如——

<details><summary>Original English</summary>
>> Yeah, man. It's just so freaking hard, right? Like
</details>

>> 我觉得他们做得还不错，对吧？我不知道他们现在还在不在。当时有一家 Webhook 公司，然后又出现了一家“反 Webhook”公司，他们的做法类似于：“我们不做 Webhooks。我们只是帮你发布一个供你拉取的 JSON 文件”之类的。哇。你知道，这在某种程度上颠倒了推与拉的数据流向。

<details><summary>Original English</summary>
>> I think they're doing okay, right? I don't know if they're still around. It was like a there's a web hook company and then there was like a anti-web hook company where you you would take like you were like we don't do web hooks. We just help you publish a JSON file that you pull or something. Wow. You know, it kind of reverses the the push versus pull the the data flow.
</details>

>> 是的。这又是疫情时期的开发者工具了。那是当时最令人兴奋的事情——

<details><summary>Original English</summary>
>> Yeah. This is again COVID era dev tools. That was the most exciting thing that at the time was
</details>

没错。是的。

<details><summary>Original English</summary>
Yep. Yep.
</details>

### 总结与道别

>> 太棒了。嗯，能和你叙旧总是令人愉快，恭喜你取得的所有成功。我依然，你知道，非常好奇你对你的品类主导到了什么程度。我认为你选得非常好，执行得也非常出色，而且你同时也把家庭照顾得很好。所以，非常敬佩。

<details><summary>Original English</summary>
>> Cool. Well, uh always a pleasure to catch up and congrats on all the success. I still, you know, uh am very curious how much you have dominated your your category. I think you you just chose it very well and you executed very well and you're managing your family as well. So, uh, lots of respect.
</details>

>> 非常感谢。是的，和你们聊天很开心。多谢大家。

<details><summary>Original English</summary>
>> Thank you so much. Yeah, it was great chatting with you guys. Thanks a lot.
</details>