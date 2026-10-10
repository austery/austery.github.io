---
author: AI Engineer
date: '2026-07-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JvKO40CFq-s
speaker: AI Engineer
tags:
  - agent-security
  - agent-auth-protocol
  - identity-management
  - authorization
title: AI 代理身份与授权安全：从“伪装用户”到“独立主体”的范式转换
summary: 本研讨会深入探讨了 AI 代理（Agent）时代的安全性挑战。主讲人指出，当前将个人凭证直接授予代理（即让代理“伪装”成用户）的做法存在极高安全隐患。研讨会详细介绍了新兴的“代理授权协议”（Agent Auth Protocol），通过为代理赋予独立的密码学身份与细粒度授权（Capabilities），实现代理行为的可审计性与可撤销性，推动 AI 代理安全从传统 OAuth 模式向“代理作为独立主体（Agent as a Principal）”的范式转换。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Agent-Auth-Protocol
media_books: []
status: evergreen
---
### 主讲人开场与背景介绍

**主讲人**: 大家下午好。大家都能听到我说话吗？好的，很好。欢迎来到我们的演讲，准确地说是一场研讨会。我知道大家可能原本也期待着 **Birgit** 能来，但他今天无法到场，不过我们是一起为各位准备了这次研讨会。如大家所见，这里有一个**二维码**，你们可以扫码进入我们的 **Agent Auth 协议**（Agent Auth Protocol，代理授权协议）页面，这样你们就能直接获取它，而不需要我费力向你们拼写这个网址了。

今天我的核心想法是，与其由我单方面向你们灌输知识、演示操作，我更希望我们能抽出至少一个小时的时间，共同思考**代理安全（Agent Security）**以及**代理（Agents）**本身。因为有时候，我们可能对这个全新的 AI 时代感到无比兴奋，对吧？但我们却很少去思考安全问题，或者说，思考得还远远不够。例如，当你对代理说“嘿，代理，我明天的日程是什么？”或者“帮我发封邮件”时，你有没有想过这背后会发生什么？在座的各位，每天都在使用 **AI 代理（AI agents）**的请举一下手？好，举高一点，别害羞。太棒了。那么，有多少人把自己的 **Gmail**、**日历**或者其他个人账户的访问权限开放给了它们？有多少人？哦，举手的人少了很多。好的。那些开放了权限的人，你们通常是怎么做的？是连接一个 **MCP（Model Context Protocol）服务器**吗？好的。还有别的做法吗？很好，也许你是把你的个人 Token 连接到了某个 API 端点。那么，当我们这样做的时候，实际上发生了什么？这其实是**代理在代表我们执行操作，但它是在伪装成我们**。那么，你认为这是一个好主意吗？是还是不是？谁觉得这是个好主意？

<details>
<summary>Original English</summary>

**Speaker**: Well, hello everyone. Can you hear me all? Okay. Yes. Perfect. Well, welcome to our talk, our workshop actually. Um, I know maybe you were expecting uh Burgett also. he couldn't come but we make this workshop together for you. Okay. So as you see you have there a QR code you can go ahead and go there is um our page for Asian health protocol so that you have it and I don't have to spell it for you. Um, okay. So, my whole idea today is instead of like me telling you stuff and you do this and show you how to do stuff, I want us to take one hour at least to think about Asian security, Asians because sometimes we are excited about like this new AI era, right? But we never think about or maybe yes, but not as much as I wished. What happens when you for example say hey agents what are my maybe my schedule for tomorrow what are send an email have you ever thought of this how many of you like raise your hand like how many of you use AI agents every day okay higher don't be shy okay great how many of you give them access to your Gmail to your calendar to your personal accounts how many of you oh so much less Okay. The ones that do like what do you do like you connect an MCP server? Okay. Yes. And they have another one. Good. Maybe you connect like your personal token to like endpoint. Okay. So what happened when we do this? We're actually doing like the agent is acting on behalf of us but pretending to be us. So do you think that's a good idea? Yes or no? Who thinks it's a good idea?

</details>

**观众**: 不太好的主意。

<details>
<summary>Original English</summary>

**Audience**: Not a great idea.

</details>

**主讲人**: 为什么？

<details>
<summary>Original English</summary>

**Speaker**: Why?

</details>

### 凭证共享 vs. 代理授权

**主讲人**: 没错。为什么我们之前没有想到这一点呢？不过没关系，至少我们现在站在这里，正在开始思考这个问题。我一直记得互联网刚诞生时的那一幕——我已经快 40 岁了，所以我对那个时期记忆犹新，当时每个人都为之兴奋不已。但随后大家就开始质疑：等等，所有的数据都是公开的，这安全吗？我们今天似乎正处于完全相同的历史时刻，对吧？我们对 AI 充满了狂热，紧接着我们开始担忧安全。但这是好事。

所以我把今天的主题定为“**雇佣你的代理（Hire your agent）**”。我希望大家思考这样一个类比：假设你经营着一家公司，或者负责某个部门，你新雇佣了一名员工。你需要让他能够访问公司的一些资源，对吧？那么你会怎么做？你会给他分配他专属的邮箱、他专属的访问权限和凭证。如果你在代理的世界里思考一下，没有代理授权协议时我们是怎么做的？我们实际上是**把 CEO 的凭证直接交给了代理**！你绝对不会对一个新员工说：“这是 CEO 的账号密码，你去帮我看一下邮件。”绝对不会，因为这可能会发生任何不可控的灾难。这其实是完全一样的道理。我们的核心思路应该是“**雇佣你的代理**”，也就是**赋予代理专属的代理授权，而不是直接把你的个人凭证交给它**。你们觉得这是个好主意吗？怎么实现呢？是还是不是？（笑声）好的。我知道大家有时会比较害羞，但我认为如果能有一些互动会非常好，因为多亏了各位工程师以及我们在座的所有人付出时间，我们才能聚在一起思考。这种机会并不多，对吧？所以让我们 100% 地投入进来。

好的，太棒了。大家都扫了那个二维码进入页面了吗？很好。请记住，当我们说“代理，读取我的邮件”时，你有没有想过代理到底是如何访问到你的邮箱的？首先，代理是怎么知道它能做什么的？

<details>
<summary>Original English</summary>

**Speaker**: Exactly. And why we didn't thought about this like before. Okay. So it doesn't matter. Here we are. We are thinking about it. I always remember uh the time like when internet came like I'm almost 40 so I remember and everybody was so happy about it. But then started to question like okay everything the whole data is public it's like we are in the same moment today right like we are really excited about AI and then after we start to think about security but it's good so why I put there hire your agent the analogy I want you to think about let's say you have a company or a part of a company and you hire someone do you give them you need them to have access two things of the company, right? So, what you do with these people when you showing or when you show, what did they give to you? You have a your own email, right? Your own access, your own credentials. So, if you think about it in Asian world, what are we doing without agents? We are it's like we are doing like the CEO credentials, right? You never say like, okay, this is the credentials of CEO, go and read the email. No, because everything anything could happen. This is the same. The idea will be hire your agent in a sense of give them your agents authority instead of your credentials. Do you think it's a good idea? How? Yes or no? [laughter] Okay. My idea is like I know sometimes um we could be shy but I want I think it would be nice like we can interact a bit because it's a moment that thanks to a engineer and all of us being here all of your time we can get together and think about something. I think it's not common, right? So, make 100% off of it. Um, okay, great. So, did you all got the page there, the QR codes? Yeah. Great. So, remember like my idea of saying, \"Okay, agent read my emails, right?\" Have you ever thought like how the agent gets to there? How it gets to your email? First of all, how do Asians know what they can do?

</details>

**观众**: 啊？（表示没听清或疑惑）

<details>
<summary>Original English</summary>

**Audience**: Huh?

</details>

**主讲人**: 好的，太棒了。所以你是手动去配置它的，对吧？它并不是某种自动化的过程。

<details>
<summary>Original English</summary>

**Speaker**: Okay, great. So, you you do it by hand, right? It's not that something automatic.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**Audience**: Yes.

</details>

**主讲人**: 确实如此。

<details>
<summary>Original English</summary>

**Speaker**: Exactly.

</details>

**观众**: 但是……

<details>
<summary>Original English</summary>

**Audience**: But

</details>

**主讲人**: 没错，但是有些……呃……

<details>
<summary>Original English</summary>

**Speaker**: Exactly. But some huh

</details>

### 三大核心挑战：发现、授权与追踪

**主讲人**: 没错，还涉及到上下文窗口（Context Window）的限制。但无论如何，你总是得以某种方式将一些东西连接到**代理（Agent）**上，告诉它“好的，这是你能做的事”，对吧？那么，如果我们有一个理想的世界，代理能够直接去一个**目录（Directory）**中查找，然后说：“哦，这就是我能做的全部事情，这些是我可以执行的所有操作。”这难道不是一个更聪明的想法吗？你们用过电话簿吗？是的，这就是安全的做法：我知道我可以给谁打电话，我只要去查电话簿，我就能知道怎么联系他们，我就有了他们的号码。这和我们想做的完全一样：我想做什么，以及我该如何调用它。所以这就是我们的第一个问题：**发现机制（Discovery）**，即代理如何自动发现它们能够做些什么，而不是靠我们一直手动去配置和连接。

此外，还有另一个部分：如果我们能够明确告诉代理，或者说**授予代理（grant agents）**它们能做什么，而且是非常具体的授权。比如，那些连接了 Gmail 账户的人，可能都只给了代理“读取”权限，对吧？仅仅是读取，这样我们就可以确保代理不会发送邮件，也不会删除任何东西，这会更安全。但是，如果你在邮箱里有非常多重要的敏感信息，一旦代理出现异常，或者有其他人能够读取你的数据，这也完全算不上安全。那么，如果我们能把代理可以调用的所有工具（正如刚刚那位观众所提到的）整理出来，让你能够对每一个工具进行逐项授权——“这个可以，那个不行，这个读取权限没问题”，这显然是一个更好的主意，对吧？这就是我们所说的**代理授权（Authorization）**，而不是直接让代理代表我执行操作并继承我所拥有的全部权限。这又回到了我们之前“雇员”的例子：一个新雇佣的人却拥有和 CEO 完全相同的权限。或者在现实生活中，如果你雇了一个助理，或者让朋友帮你做一件事，你绝对不会把所有账号密码都交给他，即使交了，你之后也会立刻修改。所以这道理是一样的。

同时，在这个代理能够自动发现能力、我们可以对其进行细粒度授权的理想世界中，我们又该**如何追踪它们（trace them down）**呢？今天，当你授权某些应用程序时，你该如何追踪它们代表你做了什么？

<details>
<summary>Original English</summary>

**Speaker**: exactly context window also too. But you always somehow connected something to the Asian that okay this is what you can do right. So what if we have like an ideal world or that can go to maybe a directory and say oh this is the whole thing I can do and this is all the things I can execute. That would be a smartest idea right? Have you ever used a phone book? Yeah right. this is safe like who I can call so I go and look in the phone book and then I have how to call it I have the number they will be the same what what I want to do and how do I call it so that's is our first problem discovery how agents discover what they can do and the idea will be it will be an automatic way not just us all the time telling how and connecting and stuff right then also there's another part it would be nice to tell the agents or like grant Asians what they can do and we're not but really specific the ones that connected the Gmail accounts maybe they all gave them read access right just read so we can I don't know don't send or like not remove anything so it's more safe okay but what if you have so many important uh information there that then if the agent something gets um wrong and somebody else can read your data it's good either. It's not safe in any way. So what if we can get all these what the agent can do all these tools as he mentioned and you can grant access to every tool like this yes this no this reading is okay that would be a better idea right so we think about authorization to that agent not like to act behalf of me and have everything I can do then the agent can do it's like going back to the higher example that a person like I just hired has all the same access that the CEO or maybe you hire have an assistant uh or a friend that do something for you like in your real life you will never give your access to all your things right and if you do you change them after so this is the same thing and also okay we have an ideal world when agents can discover what they can do then we can tell them what they can do or not but how do we trace them down. How do we trace today what the apps do on our behalf when you authorize them?

</details>

**观众**: 啊？

<details>
<summary>Original English</summary>

**Audience**: Huh?

</details>

**主讲人**: 没错，**审计日志（Audit logs）**。这就是完美的**可审计性（auditing / auditability）**，对吧？能够清晰地知道哪个代理代表哪个用户做了什么。为了实现这一点，就引出了我们的核心解决方案：**赋予代理独立的身份（Agent's Identity）**。如果每一个代理都有它自己的独立身份……

<details>
<summary>Original English</summary>

**Speaker**: Exactly. Audi logs. So perfect audification, right? Which agent did what on behalf of which user. In order to do that, that comes to our main thing. Give the agent's identity. If we have if every agent has its own identity...

</details>

### Agent Auth 协议的核心设计

**主讲人**: OpenAI、Gmail 等等，我们在这里都可以看到。但我们举个例子，来看看这是否可行。比如 OpenAI 的 `openapi.json`。有时候他们有公开的 API 定义，但我们需要一个 JSON 格式的文件。呃，我在这里没看到。API opening……好的，我知道了。我想是这一个，不对。好吧，你们知道吗？刚才那个找错了。

<details>
<summary>Original English</summary>

**Speaker**: open AI okay Gmail we have it there but let's say for example let's see if it works open AI open APIJSON and sometimes they have public they have the publics but we need like a JSON Uh, I don't see it. API opening. Okay, I do know. I think it's this one. No. Well, you know what? That were wrong.

</details>

**主讲人**: **Notion**。Notion 拥有一个非常好的 API 定义。我原本想用你们大家的另一个例子，但 Notion 更加容易获取。所以你们可以看到，虽然不是每个服务都提供，但如果它们有 `openapi.json`，我们的协议所做的就是将它进行转换。哦，我已经注册过了。那我展示给你们看。是的，是哪一个？不好意思，我在这没看到。好的，它会生成类似这样的结构。这只是个例子，但原理是一样。你可以从 API 端点中获取所有的**能力（Capabilities）**。你有时会看到比如删除（delete）操作。所以，在这个位置引入一个中间件（middleware）会是个不错的主意。是的。啊，不好意思各位，屏幕没显示对，谢谢提醒。好的，现在这样好多了，谢谢，不好意思。

好的，这里的核心思路是，你可以**将 API 端点翻译为代理的能力（Capabilities）**。由于我们目前还没有很多已经实现该协议的服务——或者说几乎还没有，但目前的过渡方案是使用一个转换器。这意味着什么？这意味着，在 **Agent Auth 协议**中，你会有一个**目录（Directory）**。在这个目录中，例如我们做过的 Gmail 示例。你可以看到它列出了 20 个能力。我们的思路是，你获取该服务能做的一切事情（可能是通过公开的 OpenAPI 定义暴露出来的，也可能是你自己定义的，因为你可能想将某个工作流自动化），然后将它们全部列在这里。这个目录就相当于代理的电话簿。大家能听懂我的意思吗？

<details>
<summary>Original English</summary>

**Speaker**: Notion. Not has a really good one. I wanted to use another one from you guys, but the notion is more reachable. So here you see so if you have for example not every service has but the open API JSON what we doing with the protocol is translating this oh I already register it. So, I'm going to show you guys. Yeah. Where is this one? Sorry. Don't see it here. Okay. It will form something like this. This is like an example, but it's like the same. So, you will get all the capabilities from the endpoints. You see sometimes you see like a delete again. So it would kind of be idea to approach like a middleware to this point. Yes. Oh, sorry guys. Thank you for telling me. And okay, here is better. Oh, thank you. Sorry guys. Okay. So the idea is to see here it's like you can translate the endpoints to capabilities. So because we are still this is just because we still we don't have so much services or let's say none like implementation stuff but the idea is like in the meantime we have something that translate this. So what this mean? It means like let me check. It means like you will have something for example do you have there in the agent of protocol you see do you have a directory this directory we have for example the Gmail one that we did the same. So you see you have for example 20 list of capabilities. So the idea is like you grab what the service can do, what is exposing maybe through open or maybe you do it yourself because uh for example maybe you want to automate a workflow. So the idea is like everything get list here. So the directory will be like a phone directory for the agent. Are you following me?

</details>

**观众**: 听懂了。不过你刚才说的是什么？不好意思。

<details>
<summary>Original English</summary>

**Audience**: Yeah. The what? Sorry.

</details>

**主讲人**: 是的，这是一个很好的点。你们听到他说的了吗？他提到了**细粒度授权（fine-grained auth）**。我们的思路是，在尽可能限制权限范围（scope）的同时，依然保持细粒度。这就像是为用户颁发 Token，但我们现在想**为代理本身颁发专属的 Token**。所以我们正在改变的是“**主体（Principal）**”。我们现在主张**将代理作为独立的主体（Agent as a Principal）**。这确实是一个非常棒的想法，也是我们设计灵感的来源，我认为这是我们能做的最正确的事情之一。好的，太棒了。

回到代理的能力（Capabilities），核心想法就像我刚才说的，一旦划分了这些范围——比如仅限读取、或者仅限 GET、DELETE 或 POST，一切操作都会被清晰地界定，你可以自主做出决定。大家有什么问题吗？

<details>
<summary>Original English</summary>

**Speaker**: Yes. I mean it's a good point. Did you hear? Did you hear him? Like fine grain out. Okay. So the idea is yes in a sense of having the most scope thing as possible but still fine out is still goes like minting a token to the user. We want to meet a token for the agent. So what we are switching is the principle. We now want that the agents are a principal actor. But it's a really good thing. That's why we inspire on that. I think it's one of the best things we can do. Okay, great. Um so going back to the capabilities the idea is what I just said like having this scope once you have like the readings or like maybe uh just the gets or the deletes or the post like everything is quite discerned so you can decide whe you have any questions.

</details>

**主讲人**: 是的，没错，那确实很糟糕。目前的思路是你可以手动配置。你可以在目录中声明所有的内容，这样在未来代理就会知道该怎么做。虽然目前这种情况不太普遍，但确实有可能发生。我们的想法是在各大服务原生支持代理身份认证之前，先通过这种方式进行过渡。不过这确实是一个很好的问题。

好的，回到我们面临的核心问题。现在我们正尝试寻找解决方案：代理如何通过目录了解它们能做什么，以及我们如何通过“能力”为它们进行授权。接下来，如果大家还记得的话，我们提到过为代理赋予**独立身份**是个好主意，对吧？所以我们的设计是**为每个代理生成一把私钥（private key）**，也就是大家熟知的私钥。每个代理都将拥有自己专属的私钥，并与它的身份绑定。

由于每个代理都有了自己的独立身份……哦，我看台下有观众希望我把屏幕切换到浅色模式。你之前也是这么说的吗？好的，让我们切回浅色模式。这样好多了。太棒了，再放大一点。好的，这样可以了。

既然代理可以访问自己专属的私钥，它们就可以签署 Token，拥有自己专属的计量 Token（metered tokens），并且所有数据都通过私钥进行加密。这意味着什么？这意味着从现在起，当 Gmail 这样的服务检测到交互时，它看到的不再仅仅是一个“用户”在操作，我们能提供一份清晰的日志，上面写着：“**这个代理正代表我执行操作，它与我这个用户相关联，但它具体是来自 Cursor 的代理，或者是来自 Claude 的代理，或者来自其他任何地方。**”

我们正在彻底改变这个范式：**我们不再让代理隐藏在用户的身份背后，而是让代理作为一个独立的主体（Principal）走向前台**。这对我来说是极其令人兴奋的。那么，对于这种私钥、公钥以及策略机制，大家有什么疑虑吗？

……没错，这正是它美妙的地方，对吧？你可以说：“哦，这个代理没有按照我预期的去做，我可以直接去**撤销（revoke）**它。”这非常酷。你可能会想：“如果我撤销了它，但访问令牌（access token）依然有效怎么办？”你可以通过 GDI（或身份标识符）来彻底删除它，直接跟它说拜拜。

<details>
<summary>Original English</summary>

**Speaker**: Yes. Yeah. Yeah. That's that really sucks. Uh the idea is you can do it manually. You can actually declare everything so in the directory or in the future the agent know how to do. It's like less common. But yeah, it could happen. But the idea is like in in the meantime we do this until services implement these sessions out. But yeah, it's a good question. [snorts] Um okay so remember like our problems right so now we we are trying to get a solution for how like the agents the agents know what they do with the directory then we have a way to authorize them through the capabilities and now if you remember we said it was a good idea to get them identity right so what we come is giving agents like a private key like famous private key. So each agent will have its own and that will be attached to the identity. Um so in that sense because every agent has its own identity. Now if you I see you want me to put this on light mode too. Uh what did you say that before? Okay, let's go back to this there. That's better. Great. zoom in. Okay, there. So now that the agent will have like a access to its own private key, they can sign tokens, they can have like their own metered tokens and everything is encrypted with the private key. So what this means like for now on instead of like a service let's say Gmail seeing like a user interacted with the service we can have a log that we actually say okay this agent is doing something on my behalf that is connected to the user but it's actually for example agent from cursor or an agent from cloud or an agent from whatever. So we are changing the paradigm. We stop seeing as an agent is like hiding behind the user and now the agent is there as a principal acting. So is is for me was really exciting. So do you have any concerns about this private key private key public policy key things? Yeah. Exactly. That's beautiful, right? You can say, \"Oh, this is not doing what I supposed to be doing, and I go and I revoke it.\" So, it's cool. And maybe you can think of like, okay, the the I revoke it, but the access token is still there. So, what you can do is like deleting with the GDI. So, bye.

</details>

**观众**: 是的，嗯。代理和它们所持有的 Token 总是会有它们需要汇报的关联用户。它们绝不是脱离用户独立存在的。所以代理始终是与特定用户绑定的。

<details>
<summary>Original English</summary>

**Audience**: Yes. Mhm. Always the token always the agents they always have a user they are reporting to you. They are never detached. So always the the agent is like with a user.

</details>

**主讲人**: 是的，没错。

<details>
<summary>Original English</summary>

**Speaker**: Yeah.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**Audience**: Yes.

</details>

**主讲人**: 没错，完全正确。你拥有所有的关联信息。此外，我们还引入了一个新的概念，叫做“**宿主（Host）**”，也就是你创建和托管这个代理的地方。所以你……

<details>
<summary>Original English</summary>

**Speaker**: Yes. Exactly. you have like all the information the agent also the host we are in introducing a new thing that is called host that is like the place when you are like creating this agent from so yo

</details>

**观众**: 你能说得再大声一点吗？

<details>
<summary>Original English</summary>

**Audience**: Can you speak a little bit higher?

</details>

### 协议演示与交互验证

**主讲人**: 好的，这是一个非常好的问题。实际上，这更多是面向企业级（enterprise）的关注点，对吧？因为我们是在今年二月份启动这个项目的，从那时到现在，事情已经发生了翻天覆地的变化。比如，当时的代理还没有像现在这样……

<details>
<summary>Original English</summary>

**Speaker**: Yeah, that's a great question. Um, actually it's more like an enterprise focus, right? So because we did this in February, the things changed so much until now. Like for example, Asians are not so

</details>

**观众**: 比如发送“Hello”这类的测试，但我们需要实际的操作（笑声）。

<details>
<summary>Original English</summary>

**Audience**: hello really but no but actual one [laughter]

</details>

**主讲人**: 谁能提供一个可以用于演示的邮箱？如果没有的话，我就用我自己的。好的，那我输入我自己的邮箱，大家看，我给自己发一封主题为“Hello World”的邮件。我原以为你们会觉得用“Hello World”作为邮箱地址很酷呢（笑声）。好的，这里的核心逻辑是，正如你们刚刚看到的，代理一开始只被授予了“读取”能力。在理想情况下，如果没有我的明确授权，它**绝对不可能**发送这封邮件。例如我们可以在这里看到，它仅拥有的两项读取权限。当它尝试发送时，系统会拦截。我们还专门开发了一个浏览器插件，以便更直观地监控授权的执行情况。好的，通过安全验证来进行授权。

大家可以看到，代理现在使用的是 **CIBA（Client Initiated Backchannel Authentication，客户端发起通道后授权）**，而不是弹出一个重定向窗口或者让我去另一台设备上确认，我直接在这里就可以点击批准。为了演示，我直接点击批准。现在代理获得了授权，它就能够真正把邮件发出去。你们会在“能力”列表中看到，它现在多了一项“发送邮件”的权限。实际上我们看到邮件已经成功发送了，对吧？

那我们接下来测试什么呢？假设代理出了问题，比如有人试图恶意访问我的 Gmail，或者进行其他窥探行为。我们这套系统最核心的价值，就是刚刚在日志中看到的可信追踪能力。那如果我们想直接撤销授权呢？让我们试着撤销它，然后尝试让它读取我的邮件。我们先点击撤销，这样它就什么都看不到了。噢，我找不到那个页面了（笑声）。好的，在代理管理界面，我们点击“撤销代理”。再见！

现在我们命令它：“读取你刚刚发送的那封最新邮件。”好的，大家看，系统提示连接已被撤销。那接下来会发生什么？为什么它依然无法读取？因为我们刚刚把之前的代理身份彻底撤销了，不过它刚才自动创建了一个新的代理身份来尝试连接，因为在我们的宿主（Host）默认策略中，获取列表被认为是一个安全的默认能力。但如果我此时要求它“给我自己发一封写着 hello 的邮件”，它就会再次触发拦截并请求授权。所以这确实在起作用，对吧？我可以随时撤销它，可以随时查看日志，可以精确定义代理可以或不可以做什么。大家不觉得这种受控的工作流非常好吗？一切都在掌控之中。大家对此有什么疑问，或者脑海中有什么想法吗？

……是的，没错。任何你认为需要谨慎对待的限制条件，你都可以写入“能力（Capabilities）”的定义中。这非常好。是的，你完全可以限制它的最大执行次数、执行时间，限制一切你想限制的维度。

<details>
<summary>Original English</summary>

**Speaker**: who has like a good email. If not I can put like my own but if you want to show okay so I gonna put mine you see I to myself saying I'm gonna use hello world. I thought that your email was hello world was so cool. [laughter] Okay, so the idea here is if you as you just saw like the agent just have like the reading capabilities. Ideally, it will never could send the email without me granting it. So for example we can see it here right the only capabilities it has is two of these two. So it will try to see it here. We can also we also did like this extension for us to actually watch it better what the aation was doing. Okay. Okay. Authorize patch with security verification. Okay. So you see this um the agent now is using CA like asyn like it's client back channel authorization instead of like just showing me like a redirect and see a device that I approve I could approve from here. So for the demo I just going to approve and now that the agent has approved. I approve it. It will be actually sending the email. So you will see in the capabilities here that now you can send the capabilities of uh send emails and actually we can see here he just it just send the email right so what do we want to try this we're going to see if you see no no okay here is the email okay so what we want to try now let's say this something went wrong with the agent Somebody was trying to access my Gmail trying to propector whatever. So the idea of this whole thing is to have the trustability we just saw is on the logs right and what if we want to revoke it let's try you let's try to revoke it and try to for example read my emails. So we're going to revoke it first so it cannot see a thing. Oh I lost the page here. [snorts] So in agents we can revoke the agent. So bye-bye. And now we can say read that last email you just sent. Okay. You see the connection got revoked. So what happened now? Why it can't read it anyway? Because what we did is like he created another agent an identity because I revoked the one before but this is just happening because the get the list is a default capability in our host because for us it's safe. What if now I wanted to say um send an email saying hello to myself. It will do the same. It will ask for it. So actually it's working right. I can actually revoke it. I can see the logs. I can say what the agent can do or not. Don't you think it's a it's kind of nice to have this kind of workflow? It's more controlled. Yeah. You have any questions about this? How something that pops in your mind? Yeah. Yes. Yes. Yeah. Every constraint that you want to be careful about, you can put in the capabilities. So, it's good. Yeah. Yes. Yes. Yes, exactly. You can say maximum maximum time of executing. You can say the time. You can say everything.

</details>

**观众**: 是时，确实如此。谢谢你的解答。

<details>
<summary>Original English</summary>

**Audience**: Yeah, it is. Thanks there.

</details>

**主讲人**: 嗯，其实你完全可以同时拥有这两种限制。

<details>
<summary>Original English</summary>

**Speaker**: Mhm. Well, you can have both.

</details>

**主讲人**: 我们的设计初衷是既要保证安全，又不能给用户带来烦恼。想象一下，如果代理每次去读取东西你都必须手动确认：“哦，天哪，我每次都要批准。”你们一定会恨死我们的。所以，我们的思路是引入类似“宿主（Host）”策略。例如，公司里的联合创始人（Co-founder）可以拥有所有操作权限，而一个刚刚加入的新人则只能拥有非常特定的访问权限。你可以通过我刚才提到的“**用户策略（User Policies）**”来实现，也可以通过“**宿主策略（Host Policies）**”来实现。因此，我们必须在良好的用户体验（UX）与足够的安全性之间找到一个平衡点。

<details>
<summary>Original English</summary>

**Speaker**: Our idea is like to be safe but not to be annoying. Imagine every time you had to read something. Oh, I had to approve every time. You're going to hate us, you know. So the idea is like a host for example or inclus sorry I spoke in Spanish include um or like maybe a host like someone specific you want like for example let's say co can do everything and then like are recently joined just have like this specific access so you can do it like by user policies as I was talking about or you can do it like host policies. So you have to be like in the middle I think of like good UX uh the good user experience but also secure enough

</details>

**观众**: 但最终决定权在于……

<details>
<summary>Original English</summary>

**Audience**: but ultimately

</details>

**主讲人**: 是的，最终是在服务器端。因为正如我所说，你们可以亲自去测试。服务器端负责对代理进行验证，并与用户端配合来校验策略，从而验证代理是否拥有相应的访问权限。这套系统一直在进行验证。

太好了。我们做这个演示就是为了向大家展示这一点。我刚刚尝试让代理发送邮件，但需要我进行确认。大家看，请求已经发送到了我这里，如果我不接受，比如我点击拒绝（deny），结果就会和我刚才演示的一样，它就无法发送。你们可以看到那部分显示为红色。这说明它工作得很完美。如果它再次请求我允许，我就予以批准。你还可以随时查询“代理状态”，这样你就可以时刻追踪代理正在做什么，以及它是否被撤销了。

<details>
<summary>Original English</summary>

**Speaker**: yeah is the ser yeah yeah yeah because uh agent what we're doing like as I said you can try it out uh with the server part is the one going to verify the agent like back with the users going to verify the policies we're going to verify has access or not so yeah all the time verifying so Great. Um, so the whole idea was to show you this. Uh, I was trying to ask the to send. Um, I need to confirm. So you see, so I here I have the request. I didn't accept it. So let's say I deny it. It will be like the same. I just did. So ideally he wouldn't. You see that's red. Okay. So it's working good. So he wants me to allow it and I'm going to I'm going to So can you tell me agent status? So you can have all the time like track down what agent is doing if it's revoked or not. Yeah.

</details>

**观众**: 哦，你的意思是，如果我们有一个特定的技能（Skill），它指示以不同的方式去使用 MCP 服务器……

<details>
<summary>Original English</summary>

**Audience**: Oh, are you saying if you have for example a skill that is saying to use the MCP server differently

</details>

**观众**: 直接调用吗？

<details>
<summary>Original English</summary>

**Audience**: directly?

</details>

### 架构无关性与生态共建

**主讲人**: 是的。其实，我们目前所做的只是为了向大家展示协议是如何运行的，这只是一个演示。但在实际应用中，你可以进行强制约束，例如规定代理在当前场景下**唯一允许调用的就是 MCP 工具**——这正是我们通过插件实现的效果。不过，在我们规划的下一代协议中，控制将会更加严格：**代理向外请求服务的唯一合法通道必须是通过 Agent Auth 协议**。所以这确实是一个非常棒的问题。

<details>
<summary>Original English</summary>

**Speaker**: Yeah. Well, actually what we are doing is we are infor in this just an example for you to see how the protocol is doing just like a demo but you can enforce for example that the agent the only thing that can use um is the MCP tools in this case that's what we did with the plug-in but yeah you have like for our next protocol it's going to be like more uh more cap down so the only way the agent can go out and ask for services is through the agent out protocol so it's a good really good question. Yeah.

</details>

**观众**: 什么？不好意思。

<details>
<summary>Original English</summary>

**Audience**: The what? Sorry.

</details>

**主讲人**: 代理服务（Proxy）。

<details>
<summary>Original English</summary>

**Speaker**: The proxy

</details>

**观众**: 好的。

<details>
<summary>Original English</summary>

**Audience**: here.

</details>

**主讲人**: 是的，在目录里会有这些定义。现在，当你登录并连接目录中的许多服务时就可以使用它。这样，当代理连接到 MCP 时，它就能确切知晓自己能够执行的所有能力。在我们的代理目录服务内部，你可以查看到诸如 Gmail 等服务的状态，可以看到代理所拥有的全部能力，也可以查看到代理的操作日志等所有信息。每份日志都是按服务提供商进行分类和隔离的。

关于这个所谓的“代理（Proxy）”，我想澄清一下，**我们这里的 Proxy 实际上只是一个目录**，它并不是传统意义上的数据代理服务。我们认为传统代理并不是一个好主意，它缺乏可扩展性，因为传统代理需要路由和处理大量数据。而在我们的方案中，它仅仅是一个**用于将用户意图（Intent）与代理能力（Capabilities）进行匹配的目录**。

回到我们的主题，如果你想尝试它，你可以进行实操，可以使用我们的插件和 SDK。这真的很棒，因为我们是从实际问题出发，一步步推导出了最终的解决方案：**发现机制、授权与独立身份**。

这就是我想向大家展示的，比如如何连接 MCP。在我们的 SDK 侧，它会配合 MCP 生成密钥并分配给相应的代理；而服务器侧则负责进行验证、执行授权策略，并向代理授予经由用户批准的特定权限。

对于我来说，这一切最核心、最引人深思的一点在于：**我们必须停止向代理直接提供我们自己的凭证，我们应该赋予它们专属的授权。我们不能再让代理去‘伪装成我’，而是要让它们‘在明确的限制范围内代表我执行操作’。**

我们的研讨会快要结束了。大家还有什么问题，或者有什么想法想交流的吗？或者对我的发言有什么补充？不知道大家以前有没有思考过这方面的问题。你们认为在行业中实现这样一套机制是一个好主意吗？我不一定指我们做的这套，但类似的机制。是的。好的，我们的核心理念是这套协议应该对所有人完全开源开放。因此，我非常欢迎大家加入我们的 Discord 频道，或者直接给我发消息、发邮件，在社群里保持活跃。因为如果我们能共同完善这个协议，对我们所有人以及整个行业都将是一件大好事。

<details>
<summary>Original English</summary>

**Speaker**: Yes. Uh you have this in the directory. Now you can use it like when you log into for example you are connecting a lot of services in the directory. So the agent when it connects to the MCP can know all the capabilities that it can do. So inside of the MC the proxy you can see for example the Gmail you can see all the capabilities that agent can do. You can see like the agents doing stuff the logs and everything. So every log is like cut down by provider. Okay. Okay. Um and about that um our actually proxy is just a directory. It's not a real proxy for us like proxy is a really bad idea. It's not scalable because proxy uses data. So in this case it's just like a directory matching intent with capabilities. Okay. Um so so back again if you want to try it you can like live you can use like the plugin the SDK. It's really nice because we started like from the problems and now actually the solutions right like the discovery authorization and identity. Um this is kind of a what I will show you guys like MCP how to connect it. Um the SDK side with the MCP is the one that is creating the the the keys and assign it to the to the agents and the server side is like verifying authorizing grant um giving the grants that are authorized by the user and and so on. So for me the most interesting thing of all is we need to stop giving credentials our credentials to our agents we need to give them authority this should we stop saying like pretend to be me instead of saying like act for me within these limits. So we are almost in the end. If you have any questions, something that pop into your mind or it could be also an addition of what I'm saying. I don't know if you ever thought of this. Do you think it's a good idea that we implement something like this? I'm not saying this one, but maybe. Yeah. Okay. The idea is that this is open for everyone. So I would love you guys to join us on Discord or you can send me a message, send me an email, be in the channel like be active because if we improve this for all it's going to be good for all of us. Yes.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**Audience**: Yes.

</details>

**主讲人**: 好的，好的，非常欢迎，请务必联系我们。当然可以。

<details>
<summary>Original English</summary>

**Speaker**: Yes. Yes, please. And please do. Yes, please do. Sure.

</details>

**主讲人**: 不，它完全是平台无关且兼容的（Platform Agnostic）。

<details>
<summary>Original English</summary>

**Speaker**: No, it's totally diagnostic.

</details>

**观众**: 好的。

<details>
<summary>Original English</summary>

**Audience**: Yes,

</details>

**主讲人**: 没错，正是这个思路。

<details>
<summary>Original English</summary>

**Speaker**: exactly. That's the idea.

</details>

**主讲人**: 是的，没错，这已经在我们的 V2 版本规划中了，也是我们目前的重中之重。所以，是的，这是一个非常棒的主意。

<details>
<summary>Original English</summary>

**Speaker**: Yes. Yeah, that's on our B2 and that's our prime focus now. So, yeah, that's a great idea.

</details>

**主讲人**: 太棒了。还有其他人有什么问题吗？好的，请说。

<details>
<summary>Original English</summary>

**Speaker**: Great. Any anyone else? Yes.

</details>

**观众**: 不，它是不同的。

<details>
<summary>Original English</summary>

**Audience**: No, it's different.

</details>

**主讲人**: 是的。

<details>
<summary>Original English</summary>

**Speaker**: Yeah.

</details>

**主讲人**: 不，我们确实从市面上现有的各种方案中吸取了灵感，但它并不一样，它是不同的。是的，因为现有的方案依然没有**将代理视为独立的主体（Agent as a Principal）**。而我们坚持将代理作为主体来对待，它们拥有自己独立的身份。因此，从这个角度来看，我们是有本质区别的。

<details>
<summary>Original English</summary>

**Speaker**: No, we also I mean we have like as an inspiration like everything that's out there, but it's not the same. It's different. Yeah. Because they are not still treating ancient as a principle. We are treating nations as a principle. They have their own identity. So from that it's different in that way.

</details>

**主讲人**: 我不太清楚。我们……我目前还没有这方面的信息。是的，请讲。

<details>
<summary>Original English</summary>

**Speaker**: I don't know. We don't I don't have that information. Yes.

</details>

**主讲人**: 抱歉，您刚才说什么？

<details>
<summary>Original English</summary>

**Speaker**: Sorry. What?

</details>

**主讲人**: 哦，是的。大家看，它由于发现机制而建立起了连接，但这本质上是相同的。对我而言，最关键的部分在于**让代理作为主体拥有它们独立的身份（Agent as a Principal）**。AI 网关（AI Gateway）目前还没有做到这一点，我希望它未来能支持，但我们协议的核心目标是实现可追溯性，管理代理的完整生命周期，并在必要时能够精准追踪或停用某个代理。要做到这一点，唯一的途径就是让每个代理拥有自己的独立身份。AI 网关目前并不提供这种能力。

好的，大家还有其他问题吗？好的。大家可以通过页面上的邮箱联系我，如果你想参与共同建设，那将是非常棒的事。这里是我的 LinkedIn 以及整个 **Agent Auth 协议**的 Discord 频道。好的，非常感谢大家，这是一次非常愉快的交流。（掌声）

<details>
<summary>Original English</summary>

**Speaker**: Oh yeah. You see I it's connected because of the discovery but it's still the same like for me the most important part is like the Asian B principles have their own identity AI gateway doesn't have doesn't do that yet I hope it does but the whole idea is to have like traceability have the whole life cycle and to be able to track down and hunt if you want an agent so that you only have if you have identity on on each agent. and AI gateway is not providing that. Sure. Is there any more questions? Okay. Well, you can reach me in the that's my email if you want to email you want to contribute together would be nice. Uh that's my link in and the discord channel from the whole Asian protocol. Okay. Thank you so much. It's been a nice one. [applause]

</details>

（背景音乐）

<details>
<summary>Original English</summary>

[music]

</details>