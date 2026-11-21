---
author: Latent Space
date: '2026-05-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CSYWbbP_OkY
speaker: Latent Space
tags:
  - bootstrapping
  - rag
  - plg
  - ai-chatbot
  - saas-growth
title: 从大学副作用到 $10M ARR：Chatbase 创始人揭秘 AI 时代的 Bootstrapped 增长神话
summary: Chatbase 创始人 Yasser Elsaid 分享了他在 ChatGPT 爆发前夕，如何利用 GPT-3 和 RAG 技术雏形打造出爆款 AI 机器人，并在不依赖 VC 融资的情况下，仅用 117 天实现 $1M ARR。访谈深入探讨了 PLG 增长、内容营销、AI 客服的未来形态——“首席客户官”，以及在 AI 时代独特的招聘与管理哲学。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Yasser Elsaid
companies_orgs:
  - Chatbase
  - OpenAI
  - Anthropic
  - Google
  - Stripe
  - Vercel
  - Zendesk
products_models:
  - GPT-3
  - Claude
  - Gemini
  - Chatbase
media_books: []
status: evergreen
---
### 创业起点：从 30 个副作用到 $10M ARR

**主持人**: 好的，我们现在在录音室，请到了来自 **Chatbase** 的 **Yasser Elsaid**。

<details>
<summary>Original English</summary>

**Host**: All right, we're here in the studio with Yaser Al from Chatbase.

</details>

**Yasser**: 你好，谢谢邀请。

<details>
<summary>Original English</summary>

**Yasser**: Hello. Thanks for having.

</details>

**主持人**: 你是一位**自筹资金 (Bootstrapped)** 的创始人。你在两年前，不，三年前就开始做 Chatbase 了。

<details>
<summary>Original English</summary>

**Host**: um you are a bootstrap founder. Uh you started Chatbase in uh two years ago,

</details>

**Yasser**: 三年前。

<details>
<summary>Original English</summary>

**Yasser**: three years ago.

</details>

**主持人**: 三年前，也就是在 **ChatGPT** 发布之前，对吧？

<details>
<summary>Original English</summary>

**Host**: Three years three years ago before Chat GPT launch, right?

</details>

**Yasser**: 是的，当时还是 **DaVinci-002** 模型。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. So Dainci O2 was the model. Yeah.

</details>

**主持人**: 没错。现在我们正在配合你宣布达成 **$10M ARR**（年度经常性收入）里程碑的消息。这是一个非常励志的故事。你是那种会说“任何人都能创业，现在就去动手”的人，而且你真的付诸行动了。我在邀请这个领域的嘉宾时常在想，很多人都有过爆火的 AI 演示，偶尔在推特发发收入图表，大家都很兴奋，但突然他们就不发了。你知道后来发生了什么吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. and now you're we're sort of coordinating this announcement for uh your 10 million A milestone. Um so it's it's a very inspirational story, right? Like you like you you're one of those people that says like you know anyone can build you should build now build now but you actually took it seriously. The other thing I always think about when terms of featuring guests for in space is yeah a lot of people have viral AI demos they'll tweet their MR charts every now and then and then people will be very hyped and then they suddenly stop tweeting their MR charts. You know what happens then?

</details>

**Yasser**: 呃，我想是因为那些产品不够有**粘性**吧？

<details>
<summary>Original English</summary>

**Yasser**: Well, I mean it wasn't that sticky, right?

</details>

**主持人**: 是的。但你挺过来了，恭喜。让我们聊聊起源故事，你是如何决定启动 Chatbase 的？

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh so somehow you survived. Congrats. Let's tell the origin story like how did you decide to uh launch Chatbase?

</details>

**Yasser**: 好的。当时我在加拿大一所大学读计算机专业，是大四。我一直在做各种**侧边项目 (Side Projects)**，折腾这些东西的目标就是为了在网上赚钱。我深受 **Indie Hacker**（独立黑客）故事的启发。所以我一边做实习，一边忙于一堆副作用。如果全部算上的话，大概有 20 甚至 30 多个。但真正赚到钱的只有三个，Chatbase 是最新的一个。

在我做其他项目时，AI 开始进入主流视野。我看到人们在讨论 **GPT-3**，这很有趣，但当然远不如 6 个月后发生的事情。我当时在为学生做产品，因为我自己就是学生，我那时的想法是做一个帮学生写论文的东西——这其实是一门好生意，现在做这个的公司都发财了。但在开发过程中，大约在 2022 年底调用 **OpenAI API** 时，我意识到有一件事：你可以把数据添加到基础模型中，或者说假装添加数据，这基本上就是 **RAG (检索增强生成)**。但在当时它还不叫 RAG，我甚至不觉得它有个名字，只是通过 **Context**（上下文）来提供信息。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. So I was studying computer science in a university in Canada. I was in my fourth year. I was always doing side projects and you know tinkering with stuff with the goal of just making money online. like I was inspired a bit by you know the the indie hacker stories and and stuff like that. So I was doing internships but at the same time I was working on a bunch of side projects. I think I had maybe if you count everything it's maybe more than like 20 or or even 30 but the ones that actually made money were three and then chatbased was was the latest one. So while I was working on the other projects, I of course AI started like the very first days of AI starting to get into you know like mainstream. I saw people talking about GPT3 and it was interesting but of course it was it was nothing like what was going to happen like 6 months from that moment. And I saw I was basically like my other projects I was building stuff for students because I was a student and my idea back then was to build something to help students write essays which is actually like a very good business. And now companies that are doing this are crushing it. But yeah, I decided to build this product and then while I was building it, while I was like calling the OpenAI API like back in late 2022 when it was GPT3, I realized that there's this thing where you can add data to the foundation model or like pretend to add data which is basically rag. But it wasn't called drag back then. It was I don't I don't think there was a name, but it's just like this model as well.

</details>

### RAG 的早期探索与爆火推文

**主持人**: 把它放进 Context 里。

<details>
<summary>Original English</summary>

**Host**: Put it in context.

</details>

**Yasser**: 没错，放进 Context。

<details>
<summary>Original English</summary>

**Yasser**: Yeah, exactly. Put it in context.

</details>

**主持人**: 当时的 Context 非常短，大概只有 4000 或 8000 Token。

<details>
<summary>Original English</summary>

**Host**: Really short context as well. It's about like 4,000 or 8,000.

</details>

**Yasser**: 我记得是 4000。天哪。当时我看到有人在做演示，但基本都是在 **CLI**（命令行界面）之类的东西里。市面上还没有产品能让这个模型在叠加额外数据的情况下运行。当我看到这东西的威力时，我意识到这非常有价值。于是我放下了所有其他侧边项目，也不去学校上课了，闭关锁定了大约一个半月。

当时还有一种信念帮了我：如果别人已经做了这个点子，那我就不能做了。你知道，当你创业时，如果你告诉朋友一个点子，他们常说：“哦，你做不了这个，因为已经有人做了。”我当时就是这种心态，这让我跑得快了很多。虽然这种心态不对，但那种**紧迫感**促使我向我仅有的 16 个推特粉丝发布了第一个版本。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. Yeah. Exactly. I think 4,000. Yeah. Oh my god. But there was like some people doing it like I saw some people doing demos but like in like a CLI or or something like that. But there was no product doing like this model but with additional data on top of it. So to me when I saw that when I saw like this thing is powerful because GPT was starting to like get actually useful and I thought hey like you can add actually like custom data to this like to me like of course this is valuable. So what happened was I dropped all of my other side projects. I stopped going to school. I just like locked in for I think maybe a month and a half. Yeah. And I think what also helped was this belief that like if someone else does the idea, I can't do it. You know when you're building a business and like you tell your friend a business idea and they say, "Oh, you can't do this because someone already did it already exists." So I had the same mindset and that made me like go a lot faster, which is a good thing. But of course, that mindset is is not true. But because I had that urgency, I I launched the very first version to like my 16 Twitter followers.

</details>

**主持人**: 那就是那条推文。这是最初的发布推文。

<details>
<summary>Original English</summary>

**Host**: Yeah. And that's the post. This is the very very OG launch tweet.

</details>

**Yasser**: 没错。

<details>
<summary>Original English</summary>

**Yasser**: Yeah.

**主持人**: 我很喜欢它。用 **LangChain**、**Pico**、**Pinecone**、**OpenAI** 构建，部署在 **Vercel** 上。你提到当时只有 16 个粉丝，现在已经完全爆火了。

<details>
<summary>Original English</summary>

**Host**: Yeah. I love it. The OG built on lang pico pine cone openai deployed to versel and at the time Yeah. You mentioned you had 16 followers and you know it's blown up now.

</details>

**Yasser**: 没错。那个演示很有趣。想象一下，那是在 2023 年，让人们感到震惊的东西其实只是一个 ChatGPT 界面，但它在聊 Chatbase 的信息，底部显示的是 RAG 的 **Chunks**（数据块），也就是来源。这种“不是在和基础模型对话，而是在和更多数据对话”的想法，在当时非常新鲜。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. Exactly. So this was the demo which is very interesting. It was just like imagine this what was you know like blowing people people's minds in 2023. It's just like basically like chat GPT interface but um it's talking about chatbased and these are like the this is the rag chunks basically like the sources at the bottom. Um but like this idea of like a chat GPT but it's not you're just not talking to the base model you're talking to like more data. Um that was very new

</details>

**主持人**: 而且你还展示了很好的 **Guardrails**（护栏）示例。早期的模型护栏确实是个大问题。**幻觉 (Hallucination)** 也是个问题，大家当时都说这东西影响不大，但它确实会胡说八道。你的例子很好：问光速是多少，如果文档里没有，它就说不知道。

<details>
<summary>Original English</summary>

**Host**: and you have good guard roll example there right? Yeah, like early early chip guard rolls were quite an issue. Hallucination was a thing everyone said it's not going to be that impactful hallucinates. Good example there, right? Like what's the speed of light? It's not in the document.

</details>

**Yasser**: 没错。因为我们收到的很大阻力是：好吧，它确实知道额外的数据，但它本质上还是基础模型。但他们不知道，通过指令和一些预处理，你可以让它不产生幻觉，或者降低幻觉率。所以这条推文火了，包括 **LangChain** 在内的所有元老级公司都转发了。这发生在我甚至还没做定价页面之前，纯粹是作为一个侧边项目发布的。

<details>
<summary>Original English</summary>

**Yasser**: Exactly. Yeah. So because a big um push back we got from some people is like okay sure it knows extra data but it's still like the base model but they didn't know like that with instructions and maybe like some pre-processing you can have it not hallucinate or like maybe like improve the hallucination rate. So yeah this was the first tweet all the OG companies you know like gold lang chain and um this yeah this this went viral. This was before having even a pricing page or anything. This was just like me publishing basically a side project.

</details>

### 从爆红到变现：117 天达成 $1M ARR

**主持人**: 那甚至是你最早的几条推文之一。

<details>
<summary>Original English</summary>

**Host**: What are your first tweets too, right? You didn't have any followers or anything.

</details>

**Yasser**: 我之前也发过推。

<details>
<summary>Original English</summary>

**Yasser**: I had tweets before this.

</details>

**主持人**: 我觉得更鲜为人知的是你在 117 天内就做到了 **$1M ARR**。很多人发布后会有高光时刻，但不知道如何将其转化为商业价值。你当时是怎么做的？

<details>
<summary>Original English</summary>

**Host**: I think obviously that was interesting then. Uh I think the ramp to 1 million AR in 117 days is also very undertold or I don't know. I obviously you've told this for listeners check out starter story where I think you uh got a little bit more detail. A lot of people will launch, they have the viral moments and then they don't know how to capitalize on it. So what did you do?

</details>

**Yasser**: 当时每隔三天我就会看到有人发布同样的东西，因为这行**进入壁垒**几乎为零。大约一个月后，我就能看到 YouTube 教程在教人们怎么复刻我做的东西。我觉得将一个演示转化为真正产品的关键在于**向业务侧推进**。很多人只是发个演示，然后纳闷为什么没人付钱。我当时停掉了生活中所有的其他事情。我甚至挂掉了最后一学期的课，但我认为这值得。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. So that's very true because when I launched this, I think maybe like every 3 days I would see someone like launching the same thing because it was like there's no barrier to entry. It's it's like very easy and of course this is valuable like people can get value out of this. And then maybe like a month after I would see like YouTube tutorials of people like basically building what I had built. But I think what like what separates you know like just a launch uh tweet or a demo from an actual product that people use was pushing more towards doing like the business stuff. So a lot of people just like post a demo and then like why isn't people like paying me money now? But I think what happened was I posted this and then I said I just stopped doing anything else in my life. I I failed actually like my my last semester, but I think it was it was worth it. Um,

</details>

**主持人**: 你毕业了吗？

<details>
<summary>Original English</summary>

**Host**: did you graduate?

</details>

**Yasser**: 毕业了。但拿的是另一个学位的毕业证，不需要那些挂掉的课程。

<details>
<summary>Original English</summary>

**Yasser**: I did. Yeah. But I graduated with like a another degree. Yeah. That didn't need those like courses that I failed.

</details>

**主持人**: 明白了。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Yasser**: 很多人说 AI 会改变创业方式，但我认为帮我真正把这变成生意的是那些“传统的商业动作”：和用户聊天、接销售电话、做演示。这些动作帮我实现了 117 天达成百万美金营收。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. But yeah, I I started like I think a lot of people were saying, "Oh, like AI is going to change how you build a business." But I think what helped me actually like make this a business is I did all the, you know, like the normal business stuff, you know, like talking to users, getting on sales calls, doing demos, all of that. I think doing that helped a lot into getting me from like zero basically to 117 uh sorry to 1 million R in 117 days.

</details>

### 渠道的力量：LinkedIn 与 Twitter 的爆发

**主持人**: 主要靠推特吗？你没有做网红营销（Influencer Marketing）吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Like primarily Twitter. You didn't do influencer marketing.

</details>

**Yasser**: 当时 **LinkedIn** 效果出奇得好。在 AI 浪潮初期，LinkedIn 上每个人都是 AI 网红，而且受众对新产品非常包容。现在的难度大多了，但当时大家都很兴奋，想尝试新东西。我的目标是每天都要搞出一点爆款内容，同时处理 B2B 的销售和演示。基本上，如果一个大的 AI 账号发了关于 Chatbase 的内容，几小时后我的 **Stripe** 收入就能增加 $3,000 MRR。

<details>
<summary>Original English</summary>

**Yasser**: so LinkedIn worked like so so well back then because like at the start of you know the AI wave everyone was an AI influencer uh especially on LinkedIn and also like the audience like basically everyone on LinkedIn was very receptive to new products and new ideas. I think now it's much harder but back then like everyone was excited and everyone wanted to try new products. So, I had like I was my goal was like every day I needed to have something go viral and also like do you know like the B2B stuff like the sales and demos and stuff like that. But basically like I would have like this maybe big AI page post about chatbase and I would see Stripe like maybe a few hours later go up by like 3,000 MR from just that one post. Yeah. Because people wanted to try new things.

</details>

**主持人**: 当时企业级市场有一种“我们必须拥抱 AI”的强烈冲动。大家都在想：是自己从头开始造，还是买现成的？早期的产品版本是什么样的？大家当时买的是什么？

<details>
<summary>Original English</summary>

**Host**: I think at the time there was like a big push that we need to adopt AI in enterprise, right? And like everyone was like, "Okay, do we build it from scratch? How do we start using it? What do we buy? What was like the early early product version of it? Was it was it the same thing? What were people buying at the time?"

</details>

**Yasser**: 最早的想法只是一个非常简单的企业 AI 聊天机器人。你上传一些文档，然后就有了一个简单的 RAG 机器人，你可以把它嵌入到网站里。

<details>
<summary>Original English</summary>

**Yasser**: So when I launched that first tweet, my idea was just like an AI a very simple AI chatbot for your business. Uh so you upload like some documentation and then then you have an AI this very simple rag that you can kind of embed on your website.

</details>

**主持人**: 这里面有**内部**使用场景和**外部**场景的区别。

<details>
<summary>Original English</summary>

**Host**: So I think there's a difference between sort of internal use cases and external.

</details>

**Yasser**: 没错。大部分感兴趣的人主要是为了外部场景，因为他们习惯了那种极其受限的、拖拽式的画布聊天机器人。当他们看到“我可以基于公司数据训练它”时，他们意识到这将彻底改变客户支持。最初版本并不是专门做客服的，只是网站上的一个助手。但当然，很多人也想要内部场景，比如 **Slack** 集成，很多人为此买单。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. Yeah. Exactly. So most of the people that were interested were mainly interested in the external use case because they were used to like the you know like the drag and drop canvas AI chatbot like like a flow builder which was very limited. But when they saw like oh I can do this and it's trained on my company's data then uh like this will change everything about customer support. Um but the very first version was not specifically customer support. It was just you know like a a chatbot helper on a website but a very simple one. And I think that's the use case that people liked but of course a lot of people also wanted the internal like use case. So we have like the Slack integration. A lot of people ask for that and what was interesting is that when you get a company to adopt a use case and they like it, it's very easy for them to adopt more use cases. So I think that also helped a lot with growth.

</details>

### 拒绝融资：刷爆信用卡与自主增长

**主持人**: 现状如何？你 117 天做到了 100 万营收，现在大概是 1000 万。你完全是自筹资金，转型成了专业的客服机器人。这个过程中有哪些转型点？为什么从不拿 **VC** 的钱？

<details>
<summary>Original English</summary>

**Host**: How's that been? So you you 117 days 1 mill R eventually now you're about 10 mill pivoted to proper bootstrapped as well you know customer service chatbot. There's a few other players that have raised a lot of money. key things you're like team of 20ish you're fully bootstrapped you're getting up there what was the story what were the pivots um why never raise VC funding just talk about that

</details>

**Yasser**: 早期我也想过走标准流程：写 Pitch Deck（商业计划书）、找投资者、找合伙人。但我没这么做的原因是：**我没时间**。产品增长太快了，我醒着和睡着的时候都有客户在尖叫，因为早期我用的是个人信用卡支付 OpenAI 的账单，当额度刷满 2.5 万美元支付失败时，客户就疯了。

<details>
<summary>Original English</summary>

**Yasser**: so I think very early on the reason I like I knew like I I wanted to build a company so like this the first step is you know like you build the pitch deck you go to investors you try to get a co-founder like you do what the playbook says you should do um and like I thought I was going to do that but because the product went So like it got so much traction so quickly. The reason I didn't do this is I didn't have the time. Like I I was basically like waking up, not even waking up, like when I'm sleeping, I would get like customers, you know, like screaming at me because the very early on, you know, like this was my personal credit card that I was using on OpenAI and

</details>

**主持人**: 你的 2.5 万额度刷满了，支付失败。

<details>
<summary>Original English</summary>

**Host**: you maxed out a 25K and then like your payments failed. Yeah,

</details>

**Yasser**: 没错，支付失败，客户就开始对我大吼大叫。

<details>
<summary>Original English</summary>

**Yasser**: my payment failed and then customers are shouting at me now.

</details>

**主持人**: 这里有个推文截图，显示你在 20 多岁时用个人信用卡支付了 2.5 万美元。在那个时代，很多初创公司发一个酷炫演示、拿巨额融资然后就“跳票”了，你反其道而行之。

<details>
<summary>Original English</summary>

**Host**: I just wanted to pull up the Yeah. This is your your credit card. Yeah. Uh payment failure. For those just listening, it says, you know, in your 20s, 25 grand being spent on your Visa credit card. And you know just for context as well in the time this is a time when like startups would be not even startups people would post post a flashy demo get crazy virality and raise massive funding rounds and never ship you know there'd be promises of vaporware cool demos that never really made it production you kind of just did the opposite right just keep shipping no need to raise and then eventually you know is growing you start building out a team all that your first company too right

</details>

**主持人**: 两年后，你出现在了 OpenAI 的大客户名单上。那也是刷个人信用卡吗？

<details>
<summary>Original English</summary>

**Host**: and then I think you know fast forward a few a year later you're on the openi all of names which uh they didn't apparently didn't tell you about but you're just on there. Is that all through your personal credit card?

</details>

**Yasser**: 那已经是两年后了，我有了公司信用卡。

<details>
<summary>Original English</summary>

**Yasser**: Two years later. This is after I had a company credit card.

</details>

**主持人**: 你们消耗了多少 Token？100 亿？

<details>
<summary>Original English</summary>

**Host**: Yeah. Okay. Okay. But yeah, I mean uh how many tokens is that? Like 10 billion 10 billion.

</details>

**Yasser**: 那只是 OpenAI 的数据。我们还有很多客户用 **Anthropic** 和 **Gemini**。到 2025 年 10 月，总计可能超过 500 亿 Token 了。

<details>
<summary>Original English</summary>

**Yasser**: This is 10 billion. Yeah. uh now I think maybe close to 100 because this is this is only open AAI too. So correct we have a lot of customers using anthropic and Gemini specifically. October 2025. But yeah we had also a lot of growth since then. So maybe like above 50 billion. Yeah.

</details>

### 模型之争：谁是客服领域的王者？

**主持人**: 市场份额分布如何？

<details>
<summary>Original English</summary>

**Host**: Actually, I I get to ask you this now. Like, what's the market share?

</details>

**Yasser**: 大约 50% 还在 OpenAI，另外 50% 主要是 Anthropic 和 Google。

<details>
<summary>Original English</summary>

**Yasser**: Maybe 50% is still on Open AI. Yeah. And then 50 on everything else. But everything else is like mainly Anthropic and Google.

</details>

**主持人**: Anthropic 增长很快。

<details>
<summary>Original English</summary>

**Host**: Yeah. Anthropic growing

</details>

**Yasser**: 是的，增长很快。因为我们允许客户选择模型。不同模型在不同行业和场景下的表现不同。

<details>
<summary>Original English</summary>

**Yasser**: it has been growing a lot because because we let our customers choose which models they're using, but we also have so like we have the main model that's generating the answer and that we let the customers choose because I think different models are different in like different industries and use cases.

</details>

**主持人**: 你会针对不同模型单独调整你的 **Harness**（脚手架/封装层）吗？

<details>
<summary>Original English</summary>

**Host**: Do you tune your harness individually for different models?

</details>

**Yasser**: 有点区别，但很接近。最简单的例子是指令。有些模型你必须告诉它“别说太多”，因为它们喜欢啰嗦；有些模型本身就很好。对于客服场景，大多数新模型都非常棒。

<details>
<summary>Original English</summary>

**Yasser**: It's a bit different, but it's it's still like very close. But yeah, like some models respond like simplest example is instructions. You know, some models you have to like say like don't talk too much for example because they just like love to ramble. Some models they're just good. So I think yeah like we have to add some tweaks um for different models. I think for for for customer service like most of the newer models are very good. Yeah.

</details>

**主持人**: 从标准的“预测下一个 Token”模型转向**推理模型 (Reasoning Models)**，对客服领域有什么影响？

<details>
<summary>Original English</summary>

**Host**: How is the transition from like standard next token predictors to reasoning models in a domain like customer service, right?

</details>

**Yasser**: 有趣的是，在客服这个场景，95% 的限制不在于模型，而在于 Harness。这是我的工作。现在的模型智能已经足够了，除非是处理极度复杂的推理，否则平均能解决 80-90% 的产品问题。虽然这看起来很显而易见，但要把 AI 客服产品真正做好，还有很长的路要走。

<details>
<summary>Original English</summary>

**Yasser**: I think what is very interesting in a use case like customer service is that I would say like 95% of the limitation is not from the model. It's it's from the harness. So like it's my job to to to fix. But I think the intelligence is there and like I think has been there for a while especially for like if you're only thinking about customer service which means like when a customer has an issue um of course like when it's very complex you still need like a lot of reasoning but but the models now are very good at that. So I I would say maybe you can if the harness is good enough I would say of course it depends on the industry but on average you can get to 80 90% of uh resolutions for for like customer product issues but to get there it's the job of the hardness and there's so many like you would expect that like it's I've been doing this for three years and like also a lot of big companies are doing the same thing because it's extremely obvious how like valuable this uh industry is, but I still think there's a long way to go to get like actually good products for AI customer service.

</details>

### 迁移成本与定价策略

**主持人**: 关于开源模型呢？你们提供 **DeepSeek**、**Meta** 等，还有 24 小时微调服务。需求大吗？

<details>
<summary>Original English</summary>

**Host**: How's the split of open models? Um I noticed like on the pricing page some of the things you offer in different tiers is open models and fine-tuning like 24-hour fine-tuning on models as well. know like uh you get access to deepseek meta moonshot and up here somewhere it also mentions 24-hour finetuning uh is there good demand is it people not wanting to send data how do you see this game

</details>

**Yasser**: 企业有时确实需要通过微调来解决指令无法解决的问题。但开源模型的情况是，热度一度很高，但随着时间推移，用户还是会回到 OpenAI、Anthropic 和 Google。而且你不希望频繁更换模型。当客户花了三四个月去完善 Harness 后，更换模型会导致表现变差。

很多人说更换模型的成本为零，这不对。即便在同一家族内升级容易，但在不同供应商之间切换的**迁移成本 (Switching Cost)** 是很高的，尤其是在客服领域，护栏可能会失效，原本该交给人工处理的事情变得不再一致。

<details>
<summary>Original English</summary>

**Yasser**: yeah so I think for enterprises sometimes they they want like some problems you can't fix by just you know like adding more instructions so you have to fine-tune so that's something we we but like it's very limited to only some enterprise companies but yeah like all the open source models I think what happened was they got like very hyped and people were very interested in using them but I think like over time like there was a spike in usage for for these models and then it goes back to open anthropic and Google and also like you don't want to change your your model like way too much because once the our customers spend some time into like perfecting the the harness like changing the model new yeah like you so that's the thing about people keep saying like the cost of switching between models is zero. It's cheap but it's not zero because sometimes you like spend you know 3 4 months like fine-tuning exactly how the model should be or like how the the product should be and then once you like change the model it it it's bad especially in customer service. I'm guessing like uh you know guardrails would break stuff that you want to hand off to a human is no longer consistent. So there's quite a switching cost there.

</details>

### PLG 与自省式增长

**主持人**: 你们的定价很有意思，基本版每月 40 美元，包年有 20% 折扣。人们在销售电话里最担心什么？

<details>
<summary>Original English</summary>

**Host**: Yeah. I'm also curious. So first of all, actually I I just noticed there's no discount for annual or is is is there 120? So this is annual. It's 40 monthly. Sorry. Got it. Got it. Got it. This is a 20%. Yeah. Very interesting how how it's priced but but basically you want people to do do annual, right? I think like onboarding these things is is really interesting. Are people more worried about guard rails? Like when when you get on these calls like what do they say they want, you know, and how are they choosing you over other competitors?

</details>

**Yasser**: 我们的增长方式和竞争对手完全不同。我们依靠 **PLG (产品驱动增长)**。拥有强大的自助服务能力其实比招一堆销售接电话更难。因为我们没融资，所以第一天雇不起 10 个销售，这反而成了优势。我们被迫打造了一个极其直观的产品。

现在，一些大公司的员工会自己注册并折腾产品，然后我们再去跟进说“嘿，我们可以帮你设置”。这种自助服务流程我非常喜欢，就像 **Stripe** 和 **Vercel**。即使是财富 50 强的公司，他们也喜欢直观、好用的产品。现在我们有了 10,000 个活跃客户，基础稳固了，我们正准备向中型市场和企业级市场进军。

<details>
<summary>Original English</summary>

**Yasser**: I think there's multiple things. I think the So the way we're growing is is interesting compared to like basically all the other competitors. I think we're growing by PLG um product like growth and we have very strong self-s serve uh demand and I think that's actually harder than you know like hiring a lot of sales people and just getting on sales calls and building the the product for your customers like that's much easier but that the problem with that for us is that it costs money to like hire all of those sales people. So I think you can only do that early on if if you raise. But because we didn't raise, we had to basically start from self-s serve because we we couldn't hire like 10 sales people on day one. But I think now that's an advantage. I think because we were like basically forced to have a very good self-s served flow and like very intuitive uh product. Now you you get like people from like insane companies just signing up and like tinkering with the product. So that's one. and then you you just reach out to them and say hey like we can help you set this up. Um so that's one and then the second is the product itself is much more intuitive and that's a good thing even for the bigger companies that you would like help on board and all of that but the downside of course is that you're not growing as fast in the early days when you're not like doing a lot of a lot of sales. So yeah, I think the reason like like the way we're getting customers now is a lot of people are going through that soft serve flow and I honestly think that flow I like a lot more because when I look at companies I like they all do that. So I I look at companies like Stripe. I look at companies like like Versel. These companies have like very easy to start tools, easy to like set up on your own, but it still is powerful enough that Fortune50 company can use it and like they do use it. So I think having that like base of building a self-s serve first company does help when you're moving up market because that you're forced to build a very intuitive product and that's very appreciated even at those bigger companies. So yeah I think that's that's what like that's what is very different from other other companies in the space. I don't think any companies has has been gone doing that a lot. But now for us, we are moving up market because now we have that base. We have like those companies that big companies that have signed up. We have 10,000 active customers. A lot of them have like a lot more needs than what they're using today for. So now we're trying to move up market and like expand into mid-market enterprise.

</details>

### 奇葩客户：从 Chuck-E-Cheese 到联合国

**主持人**: 你有一些家喻户晓的客户。**Chuck-E-Cheese** 很特别，还有什么有趣的客户故事吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh let's talk for some of the customers. Uh you got some household names. Chuck-E-Cheese is interesting. I have never been on a Chuck-E-Cheese website, but any cool customer stories you want to tell.

</details>

**Yasser**: Chuck-E-Cheese 就是通过自助服务流程注册的。有一天我们查域名才发现他们在用。由于我把 Chatbase 推广为通用的 AI 客服代理，不针对特定行业，所以客户范围极广。

**联合国 (UN)** 也在用我们，在他们的 Facebook Messenger 上。在战区等严重情况下，很多人需要帮助，但没那么多人工去回信，Chatbase 就在帮他们处理咨询。还有很多主题公园也在用，我猜是一家开始用，竞争对手就全跟进了。

<details>
<summary>Original English</summary>

**Yasser**: So, so yeah, like it's funny like Chuck-e-Cheese just signed up on like the self-s serve flow and then when we were like on a random day just going through customers, we just found their domain. So, and they're using it. Yeah. I think because um we have this self-s serve motion and like basically I'm I'm promoting chatbased as an AI agent for customer service not to a specific industry. We have so many different like ranges of industries. It's I'm actually surprised by like who's using us and what they're using us for. So we have yeah we have nonprofits using us in like very like serious situations in in like war zones and stuff like that when when like a lot of people want help but like you can't stab that many people to like respond to questions like the UN is using us right now on their Facebook um messenger. So when people reach out to them specifically for like specific regions it gets routed to chatbase and chatbase helps them. So like that's a very interesting use case and we also just discovered that randomly. Um, we have like theme parks using us on the other end. Like a lot of like for some reason a lot of theme parks like just started using us I think maybe 6 months ago. And I think the reason is like one theme park started using us and like all competitors like we're copying them.

</details>

### GTM 宣言：找到“投钱进去就增长”的公式

**主持人**: 你的“GTM 宣言”在网上很火，你能大概讲讲吗？

<details>
<summary>Original English</summary>

**Host**: You guys have really good viral just uh video marketing, you know. Uh Chatbase as a company and of course you sharing all your work along the way. I I think it's like it's pretty cool. So like you post a lot of these uh basically the full playbook is out there, you know, here's here's how you do it. Yeah. This is like I basically leaked our like go to market manifesto. Do do you want to give a quick high level?

</details>

**Yasser**: 作为一个 B2B 初创公司，你要找到那个公式：投入 1 美元，能产出更多回报，然后不断加注。

首先，如果是做 B2B，就去做 B2B 该做的事。很多年轻创始人会把 B2C 的玩法搬过来，比如在 TikTok 上拼命做 **UGC**（用户生成内容）。那也许有用，但你应该先做那些肯定有效的事：演示、销售电话、**Outbound**（主动出击）、冷邮件。这对老兵来说是常识，但对想搞创新的年轻人来说很重要。

其次是内容。每个人都知道要做内容，但如何从中提取价值并不显而易见。内容应该帮助 GTM 的所有环节：品牌建立后，付费广告效果更好，Outbound 转化率更高。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. Yeah. Yeah, we can we can go through it. But I think the like the biggest thing that you want to find as a B2B startup, especially like if you're building an AI, is you want to find the equation where if you put like $1 in, you get more out and you just basically like continue putting more money in until it doesn't work anymore. So that's like the end goal. You want to find that equation and then now it's just like a matter of investing more into what what works. B2B stuff means you need to go the demos, you need to do the sales calls, you need to do the outbound, you need to do the cold emailing, you need to do the outreach. This is like obvious probably to people who have been building companies for a while. But I think to like younger founders that who want to experiment with new things, which I think they should because that's how you not just copy whatever is working with other people. I think they need to do this first and then experiment. Content helps like all other aspects of go to market because when you have good content like consistently you have a good brand and then paid ads work because like people have seen your your brand before people have seen these people in ads before they're more likely to click on it.

</details>

**主持人**: 你提到了 **EGC (Employee Generated Content)**，也就是员工生成内容。

<details>
<summary>Original English</summary>

**Host**: EGC. That's new.

</details>

**Yasser**: 没错，这在近几个月非常火。像 **Lovable** 这样的公司做得很好，每个团队成员都有发帖的任务。人们更愿意关注真实的人，而不是品牌。我认为 EGC 是新的影响力营销，传统的网红营销已经失效了。

<details>
<summary>Original English</summary>

**Yasser**: EGC. Yeah, that's very important. Yeah, it's been I think people have been talking about that for for a few months. Uh I think companies like Lovable have been doing a good job at that which basically means like part of the job of everyone on the team is to post and you want to be seen by people like every time they open LinkedIn and every time they open, you know, Twitter, they want to see something from you. And I think people want to follow, you know, people rather than brands. And I think everyone has like something interesting to say just like you know your twist on like whatever is happening from your like position or your side of a story. EGC is very underrated. I think that's the new influencer marketing. Influencer marketing I feel like doesn't work anymore. So I think that's yeah that's the new thing.

</details>

### AI 客服的未来：首席客户官

**主持人**: Chatbase 的未来路线图是什么样的？

<details>
<summary>Original English</summary>

**Host**: back to chat base what's what's new what are you guys doing in the future where do you see customer service agents where what's like the road map what's coming up next

</details>

**Yasser**: 我们正在把 AI 客服升级为**首席客户官 (Chief Customer Officer)**。这个代理不仅知道你的所有文档、内部笔记，还整天在网站、Slack、邮件里和客户聊天。它手里握着改进业务的“金矿”。

它将贯穿客户支持、销售和入驻 (Onboarding) 的全过程。它不仅是在用户有问题时回复，而是主动根据用户之前的交互预测需求。另一方面，它会向企业主汇总洞察：比如你想做到 1 亿营收，它会告诉你由于缺少某个功能，你正在流失哪些大客户。这些信息都埋藏在对话里，我们将把它们挖掘出来。

<details>
<summary>Original English</summary>

**Yasser**: yeah so I think the intelligence is there and I think has been there for maybe a few months now to do a lot more than we're currently doing with with uh customer service agents and I think now the hardness needs to be updated to like extract all of that intelligence into something valuable. So that's that's what we're building and that's that means two things I think in the idea of what the customer support agent will do. I think that will change a little bit. I think what we're building is more than just customer support. We want to make it the brand ambassador for the whole company because I think we thought about it and like we this AI agent knows everything about your business because you had to train it on everything on your business. So it knows all of your documentation. It knows some important internal notes that you gave it. It knows all the the website data, the documents and all of that. And at the same time, this is added to your site and it's added to your email and it's added to like Slack or any channel where your customers are. So, it's talking to your customers all day. So, I think when you have those two things together, you have an agent that has all the context from your business, what it does, and like what the goal is, and then it's talking to your customers all day. This is just like a gold mine of of information about how to improve your business. So what we're building is is two things. One, we're building a what we call a chief customer officer. So this agent instead of only replying to like customers when they do have an issue, it's doing that across customer support, it's it's doing that across sales, it's doing that across onboarding, it's just a brand ambassador for the whole company.

</details>

### 关于旧金山、招聘与股权

**主持人**: 你正准备搬去旧金山？在一个到处是融资公司的环境里做一个自筹资金的公司，感觉如何？

<details>
<summary>Original English</summary>

**Host**: And moving to SF, right? Moving to SF. Um you're filling the pool. It's it's weird, right? cuz I think when you move to SF, everyone around you is VC backed. Everyone around you is like building AGI and it's interesting that you are deciding to move and then also and and I'm also curious about how you're building company, but maybe we talk about the moving first.

</details>

**Yasser**: 我觉得被一堆创业的人包围很有启发。即使他们是融资的，也会促使我去建立一个融资规模级别的公司。虽然我是自筹资金，但现在我们的盈利能力让我们运作起来就像已经融过资的公司一样。

关于招聘，我更看重“结果导向”的人。有些开发者喜欢编程的“手艺”，喜欢把代码写得漂亮；但在 AI 时代，我更需要那些因为编程的“威力”而喜欢编程的人。代码现在是可消耗的，你可以重写、扔掉，结果才是最重要的。

<details>
<summary>Original English</summary>

**Yasser**: Being here is like one, it's fun, I think, to be surrounded with all of those people building uh around you. I think it's inspiring and I think it just pushes me. I think even like the fact that they're all venturebacked, I feel like, okay, I'm gonna I'm gonna like build a venturebacked scale company even if I don't raise capital. From what I've seen, a lot of people are hiring on experience, which also like I think is is a good idea for some roles, but I think for for for things like building building the product, you want people who like don't have any preconceived notions about anything. And I I think that's what I what I try to look for is because a lot of people especially for like development a lot of people get into development because they like the craft of you know like writing you know like lines of code and making it look nice and all of that. But some people like it because of the result and like what you what coding allows you to build. And I think those kinds of people, the people that like coding because of what how powerful it is, those people will thrive in in this era.

</details>

**主持人**: 最后一个问题，员工在意股权吗？毕竟你们没有公开的估值。

<details>
<summary>Original English</summary>

**Host**: Last question. I was just kind of wondering do employees care about uh equity because technically you don't have a valuation?

</details>

**Yasser**: 实际上这有助于招聘。因为我持股比例很高，我可以给出更慷慨的股权。而且，这比那些背负着巨额估值压力的初创公司更真实。如果公司估值太高，期权很难变得值钱；但在自筹资金的公司，股权从今天起就有意义。我从多伦多一些估值极高的公司挖到了非常聪明的人，正是因为这个原因。

<details>
<summary>Original English</summary>

**Yasser**: actually like this is helping us with hiring because I think we we do give out equity, but and like we're able to be more generous with equity because I have a lot of it. I actually think it's more real than when you're raised like at a high valuation that the company needs to one live up to but then surpass for your options to like start to be worth something. I think for when I talk to a lot of a lot of people for hiring I think the advantage of like going to like a like the hot new startup is the name brand. I think it's just looks better on the resume. But I think like that that's the definition of like risk because you like you you need you need to believe that this company will live up to the valuation that they raised at which like it can be true of course but there's a high chance it can't. that when you are bootstrapped your options mean something today because you don't have like this high valuation number that you had your options at and then after that your options make sense.

</details>

**主持人**: 太棒了。很高兴能了解 Chatbase 的下一阶段。希望明年你达到 1 亿美金营收时，我们再聊。

<details>
<summary>Original English</summary>

**Host**: Yeah. Cool. Excellent. Uh it was great to catch up with you and get a look into like the next phase of Chatbase. Uh we'll do this again when you hit 100 million next year.

</details>

**Yasser**: 希望如此。也许就是今年。

<details>
<summary>Original English</summary>

**Yasser**: Yeah. Hopefully. Yeah. This year.

</details>