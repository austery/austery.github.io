---
author: How I AI
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zBROTIiHusc
speaker: How I AI
tags:
  - ai-agent
  - language-learning
  - solo-founder
  - prompt-engineering
title: Duolingo打卡千天无果后，他用Codex自制挪威语学习App并以AI Agents运营公司
summary: William Imoh在播客中分享了他如何通过Codex自制挪威语口语应用Mural Chat，以及如何利用Grok Bot与Codex构建指环王主题的AI Agent团队来独立运营公司的全流程与思考。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 开场与背景引入

**>>**: 我曾尝试构建这款应用，但体验实在不好。黑客马拉松搞砸了，我想我大概拿了倒数第一。但我们确实……
<details><summary>Original English</summary>
I tried building this app, but it just wasn't a great experience. Bombed the hackathon. I think I probably came in last. But we did
</details>

**>>**: 你拥有的元技能，就像一种成长型思维——“我可以学会挪威语，我可以学懂任何东西”。只要你坚信这个问题是可以解决的：学语言是个可解决的问题，做一款应用也是个可解决的问题。只要你能提出正确的问题并获得正确的反馈，你就能实现目标。
<details><summary>Original English</summary>
>> The meta skill that you have, which is like a growth mindset, which is I can learn Norwegian. Like I can learn something. If you just have this confidence that this thing is a solvable problem. Learning a language is a solvable problem. Building an app is a solvable problem. And if you can just ask the right questions and get the right feedback, you can get there.
</details>

**>>**: 我想说挪威语，首先需要一个不会评判我、并且愿意纠正我的交流对象。现在，我知道在某些方面和某些对话中，人们对AI拥有什么权限往往持怀疑态度。对我来说，我完全不纠结这些，唯独不给它写入银行账户的权限。
<details><summary>Original English</summary>
>> I wanted to speak Norwegian and have someone to something first that wouldn't judge me and someone that would correct me. Now, I know it's counterintuitive in some parts and some conversations that you want to be skeptical about what AI has access to. For me, I just let all that fly out the window. The only thing it doesn't have right access to is the bank.
</details>

**>>**: 你在经营一家企业，并且和我一样，喜欢借助智能体保持业务精简。那么，能跟我讲讲你是如何利用智能体运营公司的吗？
<details><summary>Original English</summary>
>> You run a business and like me, like to keep that business lean with agents. So, tell me a little bit about how you run your business with agents.
</details>

**>>**: 我不会感到沮丧，而是感到害怕。因为我现在对智能体太依赖了，以至于为自己担忧：如果这些智能体明天突然失效归零了，我该怎么办？
<details><summary>Original English</summary>
>> I don't get frustrated. I get scared because I'm so dependent on agents now that I fear for myself. What if these agents go to zero tomorrow? What am I supposed to do?
</details>

**>>**: 欢迎回到《How I AI》。我是Clara Vel，产品负责人，也是一名AI极客，致力于帮助大家用这些新工具打造更好的产品。今天我邀请到了Hack Mamba的创始人、Mural Chat的创造者William Imoh。Mural Chat是一款实时语言学习应用，是他专门为自己学说挪威语而开发的。William将向我们展示他是如何从对原生开发一无所知，到拼装出我见过的最酷的原生应用之一；此外，他还将分享自己如何作为独立创始人，利用一组以《指环王》为主题的Grok机器人军团来运营公司。让我们直接切入正题。

本期节目由WorkOS赞助。AI已经改变了我们的工作方式：工具正在帮助团队编写更优质的代码、分析客户数据，甚至自动处理客服工单。但这其中有一个关键难点：这些工具只有在深度接入公司系统时才能发挥良好作用。你的Copilot需要查看你的整个代码库，你的聊天机器人需要检索内部文档，而对企业采购方来说，这引发了严峻的安全担忧。

正因如此，这些应用从第一天起就面临严苛的IT审查。为了通过审查，它们需要安全身份验证、访问控制、审计日志以及全套企业级功能。从零构建这一切是一项巨大的工程，而这正是WorkOS大显身手之处。WorkOS为你提供企业级功能的即插即用API，让你的应用迅速具备企业就绪能力并更快进军高端市场。你可以把它看作企业级功能领域的Stripe。OpenAI、Perplexity和Cursor已经在借助WorkOS加速迭代并满足企业需求。欢迎访问workos.com，与它们及数百家行业先锋一同开启构建。

William，欢迎来到《How I AI》，感谢你的加入。
<details><summary>Original English</summary>
>> Welcome back to How I AI. I'm Clara Vel, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have William Imo, founder of Hack Mamba and creator of Mural Chat, a real-time language learning app that he built for himself to learn how to speak Norwegian of all things. William's going to show us how he went from knowing nothing about native development to hacking together one of the coolest native apps I've ever seen. Plus how he uses an army of Lord of the Rings themed Grock bots to run his business as a solo founder. Let's get to it. This episode is brought to you by WorkOS. AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire code base. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns.

That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features.

Building all that from scratch, it's a massive lift. That's where WorkOS comes in.

WorkOS gives you drop-in APIs for enterprise features, so your app can become enterprise ready and scale upmarket faster. Think of it like Stripe for enterprise features.

OpenAI, Perplexity, and Cursor are already using WorkOS to move faster and meet enterprise demands.

Join them and hundreds of other industry leaders at workos.com. Start building today.

William, welcome to How I AI. Thanks for joining.
</details>

**>>**: 谢谢。谢谢Claire，感谢邀请我。
<details><summary>Original English</summary>
>> Thanks. Thanks, Claire. Thanks for having me.
</details>

### Mural Chat 的诞生缘由

**>>**: 我邀请你来上播客，是因为我看到了你上线的这款应用——我想应该是叫Mural Chat。我觉得这是对AI极其酷炫的一次应用，在一两年前，普通人独自构建出这样的东西几乎是难以想象的、近乎不可能的。而你证明了完全可以凭借自身力量，借助AI做出这款具备如此有趣使用场景的惊艳应用。这对我来说简直不可思议。那么，请跟我讲讲是什么促使你开发这款应用的？你当时想解决什么问题？驱动力是什么？
<details><summary>Original English</summary>
>> So, I invited you on the podcast because I saw this app that you have up. Um it's Mural, I think it's Mural Chat, and I just thought it was such a cool use of AI and something that, you know, a year or two ago would have been sort of like unimaginable for someone to build on their own, like almost impossible. And you shown that you can build this amazing app with this really interesting use case and do it all by yourself with AI. It's just it's it's kind of unbelievable to me. So, tell me what brought you to building this app. Like, what problem were you trying to solve? What was driving you?
</details>

**>>**: 是的，我认为你说得很对，一年前在技术上确实是不可能的。构建出应用形态是可能的，但体验会很差，因为我试过。我当时在旧金山参加黑客马拉松，我想那是一个All Things Web黑客马拉松。我尝试做这款应用，但体验真的不好，黑客马拉松彻底搞砸了。我想我大概拿了倒数第一。

之后我等了一段时间。背后的主要动力是我住在挪威。我从迪拜搬到挪威是因为我想寻求一场冒险。我当时不知道会面对什么，只是希望大家都会说英语。一到这里，我发现大家实际上说挪威语。虽然很多人会说英语，但为了融入生活，你确实需要挪威语。

然而挪威人也非常客气：如果你尝试对他们说蹩脚的挪威语，他们就会切回英语回应你，不像法国人那样。他们会切成英语对你说话，导致我根本学不会挪威语，对吧？后来我尝试用Duolingo，打卡连续打了一千天，我总是在追求连胜打卡天数。但我渴望的是找一个交流对象——首先它不会评判我，其次它会纠正我；同时，我还想要一种仿佛被扔进挪威村庄、除了说挪威语别无选择的沉浸体验。那正是我想要的体验。
<details><summary>Original English</summary>
>> Yeah, I think you're also correct that a year ago it was technically impossible. Um it was possible to build the app, but with a poor experience, um because I tried. I was at a hackathon in San Francisco.

Um

and it was I think it was an All Things Web

hackathon. I tried building this app, but uh it just wasn't a great experience. Bombed the hackathon. I mean, I probably came in last.

I waited. Um, and the the main motivation behind this is I live in Norway and I want up to move from Dubai to Norway because I wanted an adventure. I didn't know what to expect. I just hoped everyone spoke English.

As soon as I got here, I learned that people actually speak Norwegian.

To make it by, I mean, a lot of people speak English, but you need Norwegian to get by.

But then the Norwegians are also very polite in the sense that if you try to speak Norwegian to them, but it's poor, they'll speak English back, unlike the French.

Mhm. So, they speak they speak English back to you. So, this might I couldn't learn Norwegian, right? And then I tried using Duolingo. I had a thousand-day streak

on Duolingo. I was always like chasing the streaks. And but I wanted to speak Norwegian to someone to something first that wouldn't judge me and something that would correct me. But also, I wanted to experience that felt like being thrown in a Norwegian village where you have no other option but to speak Norwegian.

That was just the experience I wanted.
</details>

**>>**: 我太喜欢这个点了。在我们家，我丈夫和孩子们也正在尝试学习意大利语。他们采用的是非常传统的语言学习方式：Duolingo加上听录音音频课程。他们坐在车里，听到有人讲意大利语，然后跟着重复。但真正学会一门语言的唯一途径是沉浸式环境。我非常赞同你指出的那点，这非常反直觉：你说你学不会这门语言，是因为当地人太礼貌了，他们会直接用英语回答你，以至于你根本无法建立“我说对了吗？我应该听到什么？”这种强化反馈闭环。所以你做出了这款应用来提供这种体验。给我们透露一下，你是iOS开发者吗？还是什么高阶程序员？
<details><summary>Original English</summary>
>> I love this because in our house, we are trying to we, my husband and my kids, are trying to learn

Italian. And they're doing it this like very classic language learner way, which is a combination of Duolingo

and like listening to it like basically these like tapes, these audio lessons. And so, they're in the car and they're like

you know, hearing somebody speak Italian and then they repeat it. But the only way you can really learn a language is immersion. And I love what you call out because it's so counterintuitive, which is you said you can't learn this language because people are so polite, they will respond to you in English and so you can't actually get that reinforcement loop of like did I say it right? What am I supposed to hear? And so, you built this app to give you that experience. Tell us a little bit about like are you an iOS developer? Are you like a

fancy developer
</details>

### 用原生语言与Codex构建应用

**>>**: 首先，我拥有化学工程学位，但我自学了编程来做Web开发。过去五六年里我做了大量的Web开发，我可以写一些前端，也能勉强写一点后端。

如果要开发移动应用，我本来可以用React Native之类的方案来做。但在构建Mural时，我想要纯原生的体验。我想要一种高级质感，因为我觉得技术上我可以搭建任何东西，但我希望针对最佳用户体验进行优化，并充分利用iOS更优秀的特性，所以我决定用Swift来构建。

当然，并不是由我亲自去写代码，我需要Codex来帮我构建。所以我让它在iOS端用Swift构建，在Android端用Kotlin构建。当有AI Agent帮你写代码时，编程语言本身就不重要了——掌握哪门语言已经不再是限制，我只需为所要构建的技术选择最合适的语言。这就是我选择Swift和Kotlin的原因，尽管我这辈子此前连一行Swift都没写过。
<details><summary>Original English</summary>
>> So first

I have a chemical engineering degree, but I taught myself to code to do some web development. So I did a lot of web development over the last um 5 6 years. I can write some front end. I can and then I can write some back end code save my life.

Building a web building a mobile app I can do it with something like React Native for instance, but I wanted today at least when I built Mural I wanted a native experience. I wanted like a premium feel to it cuz I felt like I could build anything, but

I wanted to optimize for the best user experience possible and I wanted to use like all the

the better iOS features.

So I decided to build in Swift.

Well, uh it wasn't going to be me building it. I needed Codex to build it. Uh

so

I just is building Swift for iOS and Kotlin for Android. And guess when we have AI agents building stuff

like the language doesn't matter. Like the language I know doesn't matter anymore. I just choose the best possible language for the tech that I'm building. Uh so that's why I went with Swift and Kotlin even though I haven't written a line of Swift in my life.
</details>

**>>**: 这点真的很有意思。十多年前我创办过一家真正的风险投资创业公司，当时我们选择开发语言的依据是身边谁会写那种代码。我们会盘算：“我们认识一帮能写Python的人，还认识一帮能写另外某种语言的人，所以我们就用那门语言开发应用，以匹配我们认识的人力资源。”而现在，正如你所说，你完全可以只为了用户体验和产品本身去选择最佳语言，团队里有没有人懂该语言已经无所谓了，因为有我们的朋友Codex在岗。

说到Codex，你介意打开它向我们展示一下你是如何规划的吗？你如何围绕Swift开展组织工作？坦白讲，别说出去，我得在这儿承认：我至今从未构建过原生移动应用，即使在AI时代也还没做过。所以我也在一边看一边学习。你是怎么启动的？具体是怎么推进的？
<details><summary>Original English</summary>
>> You know what's really funny about this is, you know, over 10 years ago I did a like a venture funded startup, a real startup, and we picked the language we built that application in based on who we knew could write

that code. So we're like, well, we know a bunch of people that can write Python and we know a bunch of people that can do this and so we're just going to build our app in that language to optimize for humans we knew

knew how to write that code. And now I love what you said, which is you can just pick the best language for the user experience, the thing that you want to build and it doesn't matter if you have somebody else staff that knows that language or not because you have our friend Codex on staff.

Speaking of Codex, do you mind pulling it up and just showing us how you like How do you get organized around a Swift I've actually never don't tell Sorry, we're going to do an admission right here. I have not built a native mobile app ever. Even in the age of AI, I have not built one. So, I am learning as we go. How do you How did you kick this off? How do you you know, how do you work it?
</details>

### 产品设计提示词与审美表达

**>>**: 从背景来说，因为我有一些软件工程基础，我懂得如何做应用架构，也明白构建前端和后端需要什么。此外就是我想要的体验。我认为最核心的部分正是这款应用所追求的体验。我也曾做过4年的产品经理，习惯以史诗（Epics）和用户故事（User Stories）的方式思考，因为这些与用户痛点紧密相连。这是我在构建AI应用时获得最佳效果的一种方法。

那么我是怎么开始的呢？我首先用了一条非常长且具体的Prompt。这个Prompt开门见山地写道：我想要一个视觉极其美观的应用。这就好比我的“不要犯任何错误”指令，我明确说明需要一个极具美感的iOS应用来帮我学习挪威语。

然后我描述了所期望的体验：应用需要运行在GPT Live 1之上，因为当时GPT Live 1刚好发布了一周左右。GPT Live 1正是我测试后促成构建这款应用的核心技术；如果没有GPT Live 1，我认为现阶段自己是做不出来的。因此我明确指定必须使用GPT Live 1，其余AI任务则使用GPT-6 Luna。

我还描述了交互体验：我想要一个跳动的光球界面，我可以与它语音交谈，感觉就像在通电话一样，一个我们非常熟悉的界面形态。

接着我详细描述了视觉风格。我写道：“我想要一种秋天的感觉，使用秋季色调。整体必须非常优美。遵循设计最佳实践，就好像你是苹果的高级设计师一样。”我不断向它灌输参考标准，以契合我想要的品味。因为我现在住在挪威，非常偏爱极简主义风格，所以我要求：“做成极致的极简风。屏幕上的任何元素除非绝对必要，否则都不应存在；如果非必要，直接移除或者加个开关折叠起来。”这就是基础交互形态，接着我要求它在完成后对设计进行审查。

然而，它生成的第一个设计是深色模式。深色模式一出来，我就觉得：“不行，这样行不通。”
<details><summary>Original English</summary>
>> Uh background because I have some software engineering um background,

I understand how to architect apps. I understand like what's required if I need to make the front end and the back end. Um also the experience that I want. I think that was the most important piece here is

the experience I wanted for this app. I used to be a product manager as well. I was a product manager for 4 years. So, I've learned to work in epics and user stories,

right? Because those are closely tied to user problems. So, that's one way I found um

I've had like the best results when building AI apps. So,

how did you start?

I first started with a very long prompt that was very specific. And this prompt opened with literally I want a very aesthetically pleasing application.

Like it's This is my equivalent of make no mistakes, but is I want an aesthetically pleasing iOS application um that would that I can learn Norwegian with.

And I described the experience I want, which was basically I want this application to run on GPT live one cuz GPT live one was just released I think a week after. So, GPT live one was the technology that I tested that enabled me build this. I don't think I'll be able to build this without GPT live one today. So, I specified we need to use GPT live one.

And then um we needed to use GPT six uh Luna for any other AI um any other AI tasks on it. I described also the experience I wanted. So, I wanted an orb that was, you know, a pulsating an orb that I could talk to that felt like a phone call, like a familiar interface that we would use.

And then I went on to describe the the style. So, what is something one? I literally wrote, "I want something that feels like fall, like autumn.

Um use fall uh fall colors. Um and again, it should be really beautiful. Follow um

design best practices like you are a senior designer at Apple's. So,

I'm just giving

I'm just giving it references of like I cuz I needed to get the taste that I wanted. Uh because I live in Norway now, I I love to adopt like a very minimalist style. So, I was like, "Make it like it should be really minimalist.

No element on the screen should exist unless it absolutely has to.

And if something isn't necessary, remove it or put a toggle for it." Um so, this was the like the base experience and then I requested that it reviews it the design after it's done. Now,

the first design it produced was

It was in dark mode.

It was in dark mode. I'm like, "No, this isn't going to work."
</details>

**>>**: 也许在它看来，挪威的秋天就是那样？天色开始变得很暗。
<details><summary>Original English</summary>
>> Maybe that feels like autumn in Norway, right? It starts to get really
</details>

**>>**: 我想也是。所以我必须进行迭代调整。我说：“首先，这不该是深色模式，不是所有东西都适合深色模式。应该是浅色模式，使用柔和温暖的色彩，探索渐变效果，并尽可能多地采用毛玻璃（liquid glass）质感。”
<details><summary>Original English</summary>
>> I think so. Um yeah, I had to reiterate reiterate. I was like, "First, this shouldn't be in dark mode. Not everything belongs in dark mode. Um it should be light mode. Use light warm colors. Explore gradients. And I'll use liquid glass as much as possible as well."
</details>

**>>**: 我想在这儿稍停一下，因为你在刚才的Prompt和我们的交谈中所表达的内容非常耐人寻味：你不需要精通Swift，那完全不是关键；你也许只需要知道应该采用Swift，甚至这一点AI也能判断出来。但你所具备的、而很多人尚未投入提升的能力，是设计语言和产品语言——也就是极其具体地描述你想要什么的能力。当人们谈论“品味（taste）”时，总在讨论品味到底是什么。

实际上你所需要的是设计语言和现实世界中的参考物作为对照。你需要知道什么是毛玻璃质感，需要理解什么是极简主义，需要明白什么是渐变。在设计方面，你的参考系越丰富，效果就越好；而在产品方面，你越懂得如何清晰阐述用户旅程，使得任何工程师（无论是人类工程师还是AI工程师）都能贯彻执行，工作流就会越顺畅。所以当有人问我如何培养品味或提升能力时，我会说：试着去描述网站，用语言去表达为什么品牌A比品牌B特别，或者网站A与App A优秀在哪里。这种练习做得越多，在向智能体下达Prompt时就越能游刃有余。
<details><summary>Original English</summary>
>> So, I want to pause really quickly because what I think is so interesting about what you just said in that prompt and our conversation so far is

look, you don't need to know Swift. Like you just don't. It's none of your business. You don't need to know You need to know that maybe that you should use Swift, although AI could figure that out. But what you do have that I feel like a lot of people haven't invested in their own skilling is design and product language. Like truly the ability to describe what you want with specificity. And when people talk about taste, they talk about taste all the like what is taste? We need taste.

And really what you need is design language and references in the world that you can point to. You need to know what liquid glass is, you need to know what minimalism is, you need to know what a gradient is. And

and I think the more rich your reference set is when it comes to design, the better. And then on the product side, the more you know how to articulate a user journey

in a way that anybody can execute on an engineer, human engineer,

a AI engineer, the better that like workflow will be. And so, you know, when people ask me like, how do you develop taste or how do you get good at work? I'm like,

describe websites. Like use your words to describe what makes brand A versus brand B special or what makes website A or app A better. And the more you practice that, I think the better you can be at prompting

agents to do a great job.
</details>

**>>**: 是的，我很赞同。我最初把它做出来公开发布时，根本没打算分享给任何人，因为我纯粹是做给自己用的。后来我发了一条推文说：“我做了这个东西，觉得很酷。但我不会公开发布，因为我不想承担维护它的负担，也不想去应对用户的期望。并非所有事情都必须做成一门生意。我在经营公司上已经有一大堆头疼事了，不想再多添一件。”

结果我发出来后大家都非常喜欢。除了喜欢它的体验之外，我也看到了很多其他人开发的同类应用。对比我做的与他们做的区别，我发现很大程度上在于使用体验——比如第一眼看到的感受。他们的很多作品也是深色模式，而且塞满了大量功能。对我而言，我只需要说话和字幕；对刚接触这门语言的人来说，字幕是理解对方在讲什么的唯一途径。这是我的想法，也是我当时唯一需要的功能。
<details><summary>Original English</summary>
>> Yeah, I I agree. I look at and as soon as I put this out there, I didn't intend to share it with anyone cuz I wanted to build this for myself to use just by myself. And then I put out a tweet that said, "I made this thing. I think it's really cool. I'm not going to share it because I don't want the burden of having to maintain it and having to like deal with users' expectation. Every Not everything has to be a business. I already have a lot of problems with running a business. I don't want another one. Uh so, I put it out there and people loved it and I just

people liking the experience, but I also saw a lot of people that had similar applications.

And then I looked at the difference between what I built and theirs and I noticed a lot of it just had to do with the experience, like how it felt when you looked at it, right? A lot of it were was also in dark mode. Like I rejected first, it had a lot of a lot of features, right? Um for for me, I just wanted a speak and a caption. A caption would be the only way you would understand what's being said if you're just hearing the language for the first time. That was my opinion and that was the only thing I wanted.
</details>

### 产品演示与挪威语纠错机制

**>>**: 能给我们现场展示一下吗？我们来测验一下你的挪威语水平。
<details><summary>Original English</summary>
>> Can you show it to us real quick? We're going to put your Norwegian to the test.
</details>

**>>**: 你能说英语吗？
是的，请讲英语。
好的，我们可以讲挪威语。
我和我的朋友在一起。
不，这不会是我朋友和我……
<details><summary>Original English</summary>
>> Can you speak English?

Yeah, uh please please just speak English.

Uh yeah. Yeah, we can speak Norwegian. Uh yeah, yeah, yeah,

I'm with my friend and me.

Uh yeah, it's not going to be my friend and me.
</details>

**>>**: 哇！首先，你的挪威语让我印象非常深刻——虽然我对挪威语一无所知，但真的惊艳到我了。其次，我完全理解了为什么必须用这种方式来学。你能带我们复盘一下刚才这段对话具体聊了什么吗？
<details><summary>Original English</summary>
>> No, and but one really impressed. impressed. Um at at your Norwegian I mean, I know nothing about Norwegian, but it really impressed me. And two, I totally get it. Like I get why that's the way you need it to learn like need to learn. So, can you just walk me through what that conversation we just heard kind of like was? Like what were you talking about?
</details>

**>>**: 基本上，我一开始说了声“嗨”。因为Duolingo通常以打招呼开始，并以此判断语言水平。我回了“嗨”，然后它说了一句复杂的句子，我也回了一句略微复杂的句子，表示“我还不错”。Miro问我在干什么，我说我正在和一个朋友开会。Miro接着说了些什么，但我跳过了那句，说：“请讲英语好吗？”Miro回答：“不，我不能讲英语，我必须讲挪威语。”我想我可以调出刚才的历史对话记录。
<details><summary>Original English</summary>
>> Basically, I was trying to first I was like um hi and because um Duolingo starts with hi and then figures out of level of language learning or speaking. Um so I said hi back and then said something complex. And I said something mildly complex back and I said,

um I'm doing all right. And it's it um Miro asked me, so what am I doing? I said I'm in a meeting

with a friend. And um Miro said something but I ignored that and I said, please can you speak English?

And Miro said, no, I cannot I cannot speak English back. I have to speak Norwegian. So I think I can pull up the the past conversation.
</details>

**>>**: 好呀，我想看看。
<details><summary>Original English</summary>
>> Yeah, yeah, I want to see.
</details>

**>>**: 对，记录显示是这样的：“嗨，你今天想聊些什么？”我说好。它问：“你准备好开始了，还是想再想一想？”我说“嗯”，然后问它：“你能听到我说话吗？”Miro说：“能，我听得到。你想聊什么？”我说：“我正在开会。”

我说“开会”时用错了词，我说了“yarap”或者用了错误的冠词“en møte”。它纠正说应该是中性的“et møte”，而不是阳性的“en møte”。

所以在我说错的当下它就纠正了我，紧接着追问：“会上在讨论什么？”我说：“你能说英语吗？”Miro说：“我只说挪威语。你在会上做什么？”我说：“求你了，就讲英语吧。”Miro说：“我明白，但我还是要说挪威语。不过你们在会上讨论什么呢？”然后我就放弃挣扎了。
<details><summary>Original English</summary>
>> Yeah.

Uh so it was like uh hi, like what do you want to talk about today?

I was like, oh yeah. It was like, are you ready to start or do you want to think a little bit?

I was like, hm. And I said, can you hear me?

Um and Miro said, yes, I hear you. What do you want to talk about? I said, I'm in a meeting.

Uh

and I said a meeting wrong. I said yarap or en mote.

But that's the wrong tense. So he says, uh it's called et mote.

Not en mote.

So it corrected me as I said that and then asked, what's happening in the meeting?

Then I said, can you speak English? Uh and Miro said, I'm only going to speak Norwegian. What are you doing in the meeting? I said, oh please, just speak English.

And then Miro said, I understand but I'm going to speak Norwegian. But what are you talking about in the meeting?

And then I gave up.
</details>

**>>**: 快速问个问题：你是什么时候开始学挪威语的？学了多久了？
<details><summary>Original English</summary>
>> Quick quick quick question. When did you start learning Norwegian? Like how how long?
</details>

**>>**: 我开始学挪威语是在……我在Duolingo上连续打卡了1000天。
<details><summary>Original English</summary>
>> So I started learning Norwegian. I mean, I had a a thousand day streak on Duolingo.
</details>

**>>**: 好吧，那你确实算是有一些基础。
<details><summary>Original English</summary>
>> Yeah. Okay, so you had a little bit of a head start.
</details>

**>>**: 是的，但我以前根本无法进行这样的对话，我都不知道该说什么。我的水平一直停留在“我是个男人”或者“这是一部手机”这种句型上，根本无法支撑真正的交谈。

后来我去参加了挪威语等级考试。在此之前我参加了大约为期一周的短期培训班，主要是为了搞懂语法。参加完考试并顺利通过后，我一走出考场就直接把Duolingo删了，因为我觉得它完全没用。正是从那时起，促使我有了构建Mimir（Mural）的想法。

Mimir帮助我在各种不同场景下更好地练习挪威语。比如我可以聊周末的安排，也能看到自己学过的生词以及每个单词的掌握程度。我最近还上线了抽认卡（Flashcards）功能，方便复习单词。
<details><summary>Original English</summary>
>> Yes, but I couldn't have this kind of conversation. I wouldn't know what to say.

I'm stuck at I'm a man or this is a phone.

You know?

Uh so I would I wouldn't be able to hold a conversation

and then I took the Norwegian I took the Norwegian language exams.

Um and I took a course for like a week like a short course for a week just so I understood like grammar.

Um I took the exams. I passed. As soon as I came out of like the exam hall, I deleted Duolingo because I was like nah, this is just completely useless.

And I tried it and that was my like my motivation to build something like Mimir started after that. So Mimir has just helped me get better at practicing my Norwegian in different like settings. And you know, this is

I could talk about like the weekend. I can also see like the words that I've learned.

Um

And how well I've you know, I've gone with like with each one. I recently introduced flashcards for instance in case I want to practice like the the words.
</details>

**>>**: 单词卡。
<details><summary>Original English</summary>
>> Words.
</details>

**>>**: 没​​错。而且我还设置了主题，因为归根结底你需要在特定情境下使用语言。我可以随机选一个当下世界上的主题，比如AI，它就会检索网络并基于此展开对话。但最终一切都落在对话界面上：我只需点开这里，与Mimir开始对话，随心所欲地聊天。它会在过程中不断引导我并进行纠错，直到我发音表达正确它才会停下来。
<details><summary>Original English</summary>
>> Yeah, exactly.

And I also have themes because at the end of the day you want to be able to speak these languages

within a particular setting. And I can also pick like a random theme about like maybe AI or something in the world today. It would search the internet and come up with the conversation

about about that. But at the end of the day it all lives on the talk screen. I just go to here. I start a conversation with Mimir and I just talk about stuff whatever. And it just keep nudging me further and correcting me as I go and it wouldn't stop correcting me until I say it properly.
</details>

### 成长型思维、低姿态与GPT Live模型

**>>**: 随着AI应用的普及，企业的安全风险和合规要求也随之增加。新的框架、审计和供应商层出不穷，但团队人手并没有增加。大多数合规工具承诺自动化，但你仍然不得不手动做所有事情——到处找截图、验证控制措施，在审计季到来时疲于奔命。Vanta的做法截然不同：其Agentic信任平台旨在伴随业务扩展而扩展，而非拖慢进度。凭借跨400多个集成的1400多项自动化测试，Vanta全年收集凭据并监控控制措施，将审计准备时间缩短82%。此外，你可以在工作的任何地方使用Vanta Agent，无论团队每天登录Vanta，还是在Claude或Cursor等工具中工作。想要实证吗？Ramp、Rider和Harvey等16000多家高速发展的企业在快速扩张的同时，使用Vanta节省了时间和资源。我的听众访问vanta.com/howiai即可享受1000美元优惠。

好的，我们在《How I AI》迎来过许多令人钦佩的嘉宾，他们达成了很多了不起的成就。首先，先撇开你在这个项目上倾注的开发热情不谈；其次，我想强调你身上的元技能——成长型思维。坚信“我可以学会挪威语，我可以学会任何东西”，我觉得这正是能让人在AI时代走得非常远的关键能力：只要坚信这是个可解决的问题，学习语言是可解决的，构建应用也是可解决的，并且掌握了工具，只要提出正确的问题并获得反馈，就一定能做出来。

另外还有一种极其低姿态的心态：不介意犯错，只要能被纠正就行。我认为AI是非常棒的老师，正如我常对学编程的人说的那样：它是一位无限耐心的私人导师，不会嘲笑你，不会说你蠢，不会让你觉得难堪。因此，能够将AI作为任何领域的导师，让它耐心地陪伴你、允许你犯错，这种能力是一个强烈信号，预示着在这个时代能产生极高的影响力。这是我站在更高层次对你的观察。

在进入其他工作流之前，我还想先探讨一下GPT Live。可能有人还不了解GPT Live，它是OpenAI推出的一种实时语音模型，在低延迟实时交互和处理打断方面表现非常优异，非常契合这种语言测试场景。另外GPT Live也非常适合用来语音控制应用程序，因为它的响应速度极快。我想我们之前做过一期节目，探讨过在应用中通过GPT Live进行语音控制。我觉得GPT Live是一个被严重低估的模型，很多人还没意识到用它能实现多少可能。不过我必须问一个问题：运行这个成本高吗？
<details><summary>Original English</summary>
>> As AI adoption grows, so do your company's security risks and requirements. New frameworks, audits, and vendors keep piling on, but your team isn't getting any bigger. Most compliance tools promise automation, but you're really stuck doing all the work by hand, chasing screenshots, validating controls, and playing catch-up when audit season comes around again. Vanta works differently. Their agentic trust platform is built to scale with you, not slow you down. With over 1,400 automated tests across 400 plus integrations, Vanta collects evidence and monitors your controls year-round, cutting your audit prep by 82%. Plus, you can access the Vanta agent everywhere you work, whether your team is in Vanta every day or living in tools like Claude or Cursor. Want proof? Over 16,000 fast-growing companies like Ramp, Rider, and Harvey save time and resources while scaling fast with Vanta. My listeners can get $1,000 off by going to vanta.com/howiai. That's vanta.com/howiai for $1,000 off. Okay, so we've had a lot of impressive people on How AI. They've done a lot of impressive things.

One, let's put aside that you've viper to this whole thing, which is awesome. Two, let me just say the meta skill that you have, which is like a growth mindset, which is I can learn Norwegian. Like I can learn something, and I feel like this is the skill that really helps people go very far in the age of AI, which is like if you just have this confidence that this thing is a solvable problem, learning a language is a solvable problem, building an app is a solvable problem. Like these are solvable problems that you have the tools, and if you can just ask the right questions and get the right feedback, you can get there. I think that is just like that is the skill of the And also, I would say

being really low ego, which is like I'm okay getting it wrong. As long as I can be corrected, and I think AI is such a great teacher because I tell this to people about learning to code,

I say it is an infinitely patient private tutor. Like it's not going to make fun of you. It's not going to say you're stupid. It's not going to be embarrassing. So, like the ability to use AI as a tutor for any topic and let it be patient with you and let it let you make mistakes. I just I think it's the skill that is a real signal that somebody's going to be very high impact in this in this next phase of of the world. And so, that is what I'm observing of you at a higher level. Uh no, thank you. This is This is so I like it's like giving me so many ideas. The other thing I just want to pause before we go into a couple other workflows is

GPT live. So, for people that don't know what GPT live is, um it's Open AI's like kind of real-time voice model and it does really good with real-time experiences and like interruptions, which make it great for this kind of language testing.

The other thing GPT live is really good at is voice control of apps because it's so fast. So, um I think we did an episode. I'll have to dig it out of voice control

through GPT live in your app. Um so I I I I I think GPT live is a totally slept on model that people don't appreciate how much you can do with it. The only thing I have to ask you a question. Is this expensive to run?
</details>

**>>**: 实话实说，确实挺贵的，但我直接把它算进自己的Token预算里了。

我把它开源了，所以任何人都可以运行。目前和Mural通话大概30分钟，成本大约在5美元左右。确切地说，30分钟的费用在3到5美元之间。但我做这个纯粹是为了好玩，我直接给OpenAI充了1000美元，任大家尽情调用测试。现在账户里大概还剩100美元左右了。
<details><summary>Original English</summary>
>> Uh

So, the honest answer,

um

yeah, but I just chuck it into like my token budget.

All right? Um I made it open source, so anyone can run it. And uh it currently costs around

um

it'll cost about

$5

to

to chat with Mural for

I think for

30 minutes.

Yeah. So, for about 30 minutes, it's going to cost $5 in

Now, it's going to cost between $3 and $5 for 30 minutes. Um but then, I'm building this for fun, so

I'm just I I put $1,000 on my Open AI mesh

and just let folks burn it to the ground.

I think it's really like $100 now.
</details>

**>>**: 我想说的是，这依然比一对一真人外教便宜得多。而且你不可能半夜把私人家教叫到家里说“我准备好练习挪威语了”。这确实太酷了。

接下来我们再聊几个工作流。除了开发酷炫的应用和学挪威语之外，你还在经营一家公司，而且和我一样，喜欢用智能体保持业务团队的精简。请跟我们分享一下，你是如何利用智能体来运营公司的？
<details><summary>Original English</summary>
>> Well, what I

I'll also say is that it's less expensive than a 101 tutor. Um and and you can't call your tutor to your house in the middle of the night and say I'm ready to practice some Norwegian. So,

I it's it's so cool. Okay, we're going to do a couple more workflows. We'll get you out of here. So, aside from building cool apps and learning Norwegian, you run a business

and like me, like to keep that business lean with agents. So, tell me a little bit about how you run your business with agents.
</details>

### 用AI Agents实现业务“100X”运营

**>>**: 好的。大概在今年6月份我们开始规划第三季度时，我在公司内部提出了一个指标要求，称之为“100X”。这是为了让我们在不大幅增加人员编制的情况下，将营收目标提升100倍。这意味着我们必须尽可能多地利用AI，但前提是不使用AI去凭空生成低劣内容，也不把核心创意工作让渡给AI工具。

首先，我必须梳理出自己目前所做的所有事情。第一步是在Notion上列了一张清单，把所有工作都列了出来。作为独立创始人，我需要承担一部分客户成功（Customer Success）工作，处理大部分Inbound销售——目前大概同时并行跟进11到15个交易；由于我曾担任过产品经理，我还负责产品团队；此外我还负责一些财务、HR、面试招聘，以及与人沟通。我们内部大概有25人左右的团队规模。

我想找到一种能统筹管理大量事务的方法。起初我想招一名参谋长（Chief of Staff）。我曾尝试招过一个人，但他还没正式入职，不知出于什么原因就在入职前夕离职了，那对我来说像是断了最后一根救命稻草。

于是我决定拥抱AI工具。我尝试了不同的工具：起初试了Claude，习惯了在Claude上协同工作，但后来由于某种原因我的账号被封了。我不知道为什么，索性直接放弃，转回ChatGPT并重新配置工作流。

我决定使用Projects功能，就像我现在在这里设置的那样。我基本上为每件事都建立了对应的Project，因为我想通过一套规范的方式来管理我负责的各项具体事务。我的公司叫HackPanda。对于我直接参与的每个核心业务模块，我都创建了Project：比如HackPanda Operations，用于管理开发票、营销活动等；如果有人在Discord上给我发消息，通常也会归入这里，并在此处执行对应任务。

我还设置了负责增长（Growth）的Project。比如每周日晚上我会收到一份运营简报（Operator Brief），列出：我们应该开始做哪些事、应该停止做哪些事、应该继续坚持做哪些事；我还会让它列出我本周将执行的3个最高影响力的行动。这形成了一种日常惯例（Routine），我也频繁使用Routine功能。

我们内部还在构建一款用于增长的工具，用于配合客户，覆盖从内容创意到Booksy分发的全流程。我也参与支持Booksy的增长和内容创作，因此也为此建了一个Project。销售方面也是如此，还有针对我们官网的、针对播客的——涵盖代码之外的方方面面。我会在里面整理采访简报等所有内容。

我在Codex中大量使用Projects。目前我倾向于把复杂繁重的工作留给Codex。例如Mural项目需要编写Swift代码，我希望由Astra来处理Mural的事务，在这类工作上调用前沿模型，这就是我在Codex上的用法。

但在另一端，我发现了Grok Bot，并且立刻觉得它太不可思议了。对我来说这堪称颠覆性的变化，因为它赋予了我“同事”。如果说在ChatGPT和Codex里我得到的是一个个“文件夹”，那么在Grok Bot上，我得到的则是我的“护戒使者团（Fellowship）”。
<details><summary>Original English</summary>
>> Yeah. Um so, first of all, in sometime in June when we started planning Q3,

I put together a mandate internally and I called it 100X. And this was a way for us to go 100X our kind like revenue goals and we we set up as a company without drastically increasing head count. And this meant that we needed to use AI as much as possible without using AI to generate content or seeding any of our creative work to AI tools.

Um

Uh so, first of all, I had to figure out everything I, you know, I currently do. I put together a list on Notion. That was my first step. I listed everything. So, as the founder and I'm a solo founder, so I do a bit of customer success. I handle most of the inbound sales. Currently working, I think, about 11 to 15 deals in parallel at the moment.

Um I handle the product team as well because I used to be a product manager. Um and I do a bit of like accounting, HR, interviews, like hiring, to just talking to folks. And we have a team of around 25 people

internally. Uh so, I wanted a way to be able to manage a lot of things. First, I wanted to hire near of staff.

Um I tried hiring someone. They didn't start. They quit on like just before they started for some reason. I think that was like a hail Mary for me.

Um, so I decided to adopt AI tools. Um, and I tried different tools, right? I tried Claude first. I got used to use to Claude co-work. And then for some reason my account got banned.

Um, I don't know why. I skipped it. I went back to ChatGPT and installed work. Um, and I decided to use projects as I currently have on here.

I set up projects for everything, basically. Cuz I just wanted a solid way to manage

um, to manage individual things I do. My company's called HackPanda. So, for every critical piece that I work on directly, I create a project for it. I have a project for HackPanda operations. This is where I manage things like, you know, invoicing,

um, campaigns. Not just And if anyone sends me a message on Discord, this is where that would likely fall into. And that task will be run um, from here.

Um, I have stuff for growth. So, this is like I also get like an operator brief every Sunday night of the week. So, what's something we should start doing, what's something we should stop doing, and what stuff we should keep doing. I also ask you for like the three highest impact activities I will conduct this week. So, that's a routine. So, I use routines a lot as well.

Um, we're building an internal tool for growth. Um, this is what we use to uh, we we use with our customers. We go from content ideation all the way to distribution in Booksy. Uh, I also support with the growth of Booksy and content creation.

Uh, so I created a project for it. For sales, I did the same thing for our website. This is my podcast, everything outside code. Um, I manage like interview briefs and all that um, in there. And just every other thing. So, I use projects a lot with with Codex. Uh, now for Codex, I kind of reserve reserve like the complex work. So, for instance, Miro having written Swift, so I kind of like wanted Astra to work to work on Miro. So, I wanted frontier model on that stuff.

Um, that that's what I do on Codex.

But, on the flip side,

I found Grok Bot and instantly, I think it was amazing. Like it was a game-changer for me because it gave me colleagues.

Whereas with ChatGPT, I got and like Codex, I got folders.

Um,

and on Grok Bot, I got my fellowship as I like to call them.
</details>

### 指环王护戒队：各司其职的Agent团队与权限配置

**>>**: 看过《指环王》的人都知道护戒使者团是什么。

一开始系统提示我创建一个参谋长，我毫不犹豫直接把他命名为甘道夫（Gandalf）。接着我让甘道夫去创建其余的角色。我需要负责工程、营销、产品管理、财务、销售和客户成功的Bot。它们的人设非常契合原著：英俊的莱戈拉斯（Legolas）负责营销；精灵埃尔隆德（Elrond）主管工程开发；坐拥金币的矮人吉姆利（Gimli）掌管财务审计；阿拉贡（Aragorn）负责招募所有人并推广护戒团，由他执掌销售；山姆（Sam）始终扮演坚实后盾，负责客户成功；佛罗多（Frodo）负责夺取魔戒，实质上扮演产品负责人（PO）的角色，主管产品管理。

就这样，我组建了护戒使者团。在我的AI工作流中，组建好团队之后的第一步，不仅在Grok Bot上，在Codex上也一样，就是赋予它们访问一切的权限。

我知道在很多探讨中这显得有些反直觉：人们对于AI拥有哪些权限、能做什么、有什么读写权限往往非常谨慎警惕。对我来说，我把这些顾虑统统抛在脑后。唯一不给写入权限的就是银行账户。

只要不动银行账户，其他出点问题都无所谓。而且我也接触不到客户敏感数据，所以那部分也是安全的。除了银行和客户敏感数据，其余一切全部开放：我给它接入Loom套件等各种工具；我直接扫一眼浏览器窗口，通常开着15、16个标签页，凡是我能接触到的工具——从Linear、Notion、日历，到Pipedrive、QuickBooks，全部对它开放访问权限。

对于ChatGPT和Codex，我直接开启了Computer Use和Browser Use。如果它无法通过MCP找到数据，直接操作我的电脑就行，完全没问题。每次弹出“允许一次”的提示，我直接选“始终允许”，放手让它使用。

完成这些配置后，我的工作方式在最近迎来了巨大转变：我不再需要手动给它喂信息，甚至在输入框里打出错别字也无所谓。我只需要随手抛出一个想法，比如我一直在面试和接触大量候选人。

我们在内部构建了一个名为Three Pipes的工具。我之所以做这个工具，是因为我坚信最终我们只会留下两样东西：记录系统（Systems of Record，即围绕特定问题定制的数据库）以及AI交互界面。因此我在内部构建了这些工具，让它们充当记录系统。Three Pipes专门用于人事和HR管理。

现在我只需吩咐我的Grok Bot——而且好在对此根本不需要专门编写特定的Skill。我跟候选人聊完后，直接对Grok Bot说：“嘿，我刚和这个人聊过了，把他们录入到Three Pipes里。”它就会自动翻阅我的所有邮件、日历、查看会议记录，汇总全部信息，整理录入到Three Pipes中，并向我输出摘要。这一切全自动完成，它还会给候选人打分并提示：“你已经面试了15个人，供参考，该候选人在列表中排名第7。”这样我就可以略过繁琐事务，立刻将上下文切换到销售等其他工作上。

这构成了我目前AI使用布局的一部分。最后一部分就是我所沉淀的Skills。我有几个非常核心的Skill。之所以称它们核心，是因为随着时间推移，尽管我积累过很多Skill，但底层模型变得越来越强大，很多Skill已经不再必要，只有极少数沉淀保留了下来：一个用于增长营销的Skill，根据Hack Mamba的内部知识库制定增长策略；一个用于制定内容策略的Skill，同样基于我们的知识库；还有我的内容分发（Content Disrup）Skill。
<details><summary>Original English</summary>
Um, if you've seen Lord of the Rings, uh, you know what the Fellowship of the Ring is. So, I just, um,

I was first asked to create a chief of staff. I just called him Gandalf. Straight up.

Straight up. And then I asked Gandalf to create everyone else. I needed, um, other bots for engineering, marketing, project, uh, product management, accounts, sales, and customer success. And kind of the personas are, you know, very close match, you know, like Legolas, you know, pretty Legolas is, uh, the

the marketing dude. Elrond, the elf, runs engineering.

Um, I have Gimli, um, the dwarf with the coins, um, in accounts. Uh, Aragorn recruits everyone and, you know, sells the fellowship. He runs sales. Um, and Sam always plays support. So, he's his customer success, uh, for this one. And yeah, uh, Frodo is in charge of getting the ring. Uh, he's basically the product owner

in this case. So, uh, Frodo runs PM. And yeah, so this I set up the fellowship. And with with my AI workflow, what I do first of all after set up the fellowship, and not just on Grok Bot, but also on Codex, also giving it access to everything.

Now, I know it's counterintuitive in some

parts and some conversations that you want to be skeptical about what AI has access to

and what it does and what, you know, it has read or write access to. Uh for me, I just let all that fly out the window. The only thing it doesn't have write access to is the bank.

So, unlike anything else can go wrong. I mean, I don't have access to customer data, right? So, that's safe as well. But, uh the bank and customer data, aside from that, everything is up for grabs. So, give it access to like Loom Suite, I give it access. I just look at my browser window.

I have like 15, 16 tabs open and I just give it access to everything that I could, you know, I could see from Linear, Notion, my calendar, Pipedrive, QuickBooks, everything that I had access to,

I give it access. And then for ChatGPT, like for Codex,

um I just enabled computer use and browser use. So, if it cannot find it via MCP, just use my computer. That's all right. It's fine. It's whatever. I I I I just give it access. It's like allow once, I'm like, "No, allow always." That's you know, just use it. Um so, setting those up,

that was like the next thing and that just recently changed a lot of things for me, right? So, I wasn't giving it information. I would just like I could even put a typo

in the input box. I would just like give it my like a thought, like I've been hiring and talking to like a lot of candidates.

Um

I built a tool internally called um Three Pipes. So, uh and the reason I built it is because I have a firm belief that at the end of the day, we're going to be left with systems of record, like a custom database that is designed around a problem.

That's what's going to be left and then AI interface.

So, um I'm I would build these tools internally and they just become systems of record. Three pipes is for people and HR. So, now I just tell like my Grok Bot and

the good thing is I don't need a skill for this. I talk to candidate and I just say to my Grok Bot, "Hey, I just spoke to this person. Get them into three pipes." It goes through all of my email, my calendar,

looks at meeting notes, collects all that information, puts it in three pipes, gives me a summary. It's all done and it scores the candidate as well and says, "You've spoken to 15 people. This person ranks number seven on that list, just so you know, like FYI." Um and I skip down it then I can switch context to something else to sales. So, that's that's like the one piece and then the final piece of how I use AI and how I'm set up currently would be

the skills that I have. Um so, there are a couple important skills

um

that I do have and I call these important because over time, while I've gained a lot of skills, the models have gotten a lot better that I don't need these skills anymore. Um so, there are just very few that stuck.

Uh a skill I use for um growth marketing, like to create a growth marketing strategy based off what we know at Hack Naja.

Uh a skill to create a content strategy um also based on what we know and then my content disrup skill.
</details>

**>>**: 在这套架构中绝对关键的Skill。
<details><summary>Original English</summary>
>> Critical critical skill in this in this stack.
</details>

**>>**: 确实。
<details><summary>Original English</summary>
>> Exactly.
</details>

### 故障应对、依赖反思与尾声

**>>**: 我觉得这太有价值了。对于坚持听到这里的听众来说，你们收获了真正的干货：用Codex处理复杂开发任务，利用Codex Projects进行分类组织；像我一样使用Grok Bot分工角色，涵盖营销、HR、销售各个职能；再配一个“索伦之眼（Eye of Sauron）”巡视全局查缺补漏；最后极其精准地配合少数特定Skill。

William，这是我最喜欢的单集之一。我做过很多期播客，但这期绝对是我的最爱之一。在让你回去继续投入精彩工作之前，我想问你一个我们对每位嘉宾都会问的问题：当你的Grok Bot、Codex或者挪威语智能体不理你、无法按预期执行时，你的Prompt策略是什么？你是礼貌沟通，还是严厉训斥？真实情况究竟是怎样的？
<details><summary>Original English</summary>
>> I just

I I think this is so useful. I mean, for folks that have stuck around this long in the episode, you've gotten like true gold, which is: you have Codex for complex tasks,

Codex projects to keep everything organized, Grok Bot as you do this very similar to me, where like Grok Bot has roles, so it's like your marketing role, your HR role, your sales role. Um you need an Eye of Sauron that looks across everything for things going wrong. That's the last one.

Eye of Sauron. Um and then you use just like skills very precisely, like very specific ones.

Um

William, this is one of my favorite up. I'm not I've done a lot of episodes. This has been one of my favorite one of my favorite ones. I'm going to ask you our one question we ask every guest and then I'm going to get you out of here to back back to all your awesome work. But when your Grok box, your Codex, your Norwegian agent just is not replying to you, doing what you want, what's your prompting strategy? Are you polite? Do you yell? What's the what's the real truth?
</details>

**>>**: 首先，我会直接重启这些智能体，彻底重新加载。

我重新启动并重试。如果还是不行，我会尝试更具体地去描述要求。因为我自己已经知道该怎么做，只是不想亲自动手做这些低阶琐事。所以我会变得极其具体：“先做这一步，先测试这部分，并且审查你做好的内容，确保符合我的要求。”也就是要求它重新复盘审视一遍。

最近我还让Grok Bot来驱动我的Cursor Agent。当Cursor Agent做出一些不太准确的操作时，Grok Bot就像监督审查员一样，去复查所有产出并进行完善。这是一套办法。但如果智能体一直表现出色，偶尔搞砸了，我就会去Twitter上吐槽，抱怨Tibo为什么还不修复它。
<details><summary>Original English</summary>
>> Um so first I just restart the agents. I just reboot.

I reboot um and I try again. And if it doesn't work, um I try to be a bit more specific.

Right? Cuz

I know how to do it already. I just don't want to do it because it's like low-level work. Uh so I get very specific on do this first, test this first. And also review what you've done to be sure this is what I asked for. So just asking it to like go over it again.

Um and more recently I've had um my Grok bot drive my cursor agent. Um so while the cursor agent would do like some random stuff that isn't really accurate, my Grok bot is sort of like that

agent that goes and reviews all that again and uh improves it also. Um so that that's been like one way, but the agents have just been like really good that if it doesn't get it, I just go on Twitter and I blame Tibo for not fixing it.
</details>

**>>**: 找Tibo，完全没错。
<details><summary>Original English</summary>
>> Uh Tibo, that's exactly right.
</details>

**>>**: 直接向他开火，质问他怎么还不修复Codex。或者我就直接换个智能体，改用其他工具，等待更新。

但通常我的应对策略就是这样。我并不会感到烦躁沮丧。我真正感受到的不是烦躁，而是害怕：如果它最终无法达到我想要的质量，我会感到恐慌。因为我现在对智能体太依赖了，以至于为自己担忧——如果这些智能体明天突然失效归零了，我该怎么办？我该如何一个人在同一周内一边接听所有电话，一边并行处理15个销售机会，同时还要推进招聘并处理所有事务？那是我唯一会恐慌发作的时刻，因为一旦系统瘫痪，我就彻底走投无路了。我该怎么办？
<details><summary>Original English</summary>
>> was straight, you know, for not fixing Codex like

Yeah, I try

or I just switch the agent use something else and wait and update it. Oh, then But yeah, that's that's typically my strategy. I don't get frustrated.

The frustration I feel is if it eventually doesn't get it at the quality I want, I get scared because I'm so dependent on agents now that I fear for myself. I'm like, what if all these tags? What if I What if these agents go to zero tomorrow? What am I supposed to do? How am I supposed to manage 15 different like sales opportunities in a week in tandem having all these calls, still doing my hiring, doing all these things at once. I That's the only like panic attack I get because I'm like, this goes down, I'm screwed.

What am I going to do?
</details>

**>>**: 真是极其精彩的收尾，William。这期节目太有趣了。对于我们的观众，大家可以在哪里找到你？我们能为你提供什么帮助？
<details><summary>Original English</summary>
>> What What a perfect end to our episode, William. This has been super, super fun. Um for our audience, where can we find you and how can we be helpful?
</details>

**>>**: 我在LinkedIn上，也在X上，账号是@IChulo；在LinkedIn上搜William Imoh就行，就是那个戴着飞行耳机小哥的照片——我平时开轻型小飞机。这是找到我的方式。如果有人对增长感兴趣，尤其是拥有开发者工具类产品，想要实现5000到10000名用户的增长突破，我很乐意一起探讨如何达成这一目标。
<details><summary>Original English</summary>
>> Yeah, um I'm um I'm on LinkedIn. I'm on X at I Chulo. Um William Imoh on um on LinkedIn. Just find a dude with I put on headphones. Like, I fly small planes off these. So, um

uh that's that's a way to find me. And if anyone's interested in growth, especially if you have a dev tool product, and you want to reach an X5, 10K users, I'm always happy to chat about like how we could do that together,

basically.
</details>

**>>**: 太棒了。非常感谢你参加《How I AI》。
<details><summary>Original English</summary>
>> Amazing. Well, thank you so much for joining How I AI.
</details>

**>>**: 谢谢，感谢你的邀请。
<details><summary>Original English</summary>
>> Yeah, thanks. Thanks for having me.
</details>

**>>**: 非常感谢大家的收看。如果你喜欢本期节目，请在YouTube上点赞并订阅，或者给我们留言分享你的想法。你也可以在Apple Podcasts、Spotify或你喜爱的播客应用中收听本节目。请考虑为我们留下评分和好评，这能帮助更多人发现我们的节目。欢迎访问howiaipod.com收看所有往期节目并了解更多信息。我们下期再见！
<details><summary>Original English</summary>
>> Thanks so much for watching. If you enjoyed the show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts.

You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiai pod.com.

See you next time.
</details>