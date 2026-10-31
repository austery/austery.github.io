---
author: AI Engineer
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UGjk3Uk0MxM
speaker: AI Engineer
tags:
  - large-language-model
  - prompt-engineering
  - agent
  - model-evaluation
title: 多大语言模型对比与提示词优化工作坊
summary: 本文记录了一场关于多模型对比与优化的引导式工作坊。主讲人基于部署在微软 Foundry 上的模型，探讨了利用 LangChain 构建旅行规划智能体、使用 DSPy 与 GEPA 算法优化提示词，以及模型间差异与引文功能的应用。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Dropbox
  - Microsoft
  - Shopify
products_models:
  - DeepSeek V4 Flash
  - DSPy
  - GPT-5 5
  - Kimi K2.6
  - LangChain
  - Llama
  - Mistral Large 3
  - UV
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 工作坊设置与环境准备

好的。呃，既然现在已经差不多 11:12 了，我想开始讲工作坊的内容了。嗯，所以，我打算以引导式工作坊的形式来进行，我会在这里的屏幕上过一遍所有的示例，嗯，不过大家也可以呃试着跟着一起操作。代码仓库就在那里，环境变量也在那里。呃，所以，这些环境变量能让你们访问我部署在呃 Microsoft Foundry 项目上的一批 Foundry 模型。嗯，它们有一定的 token 容量。在呃，你们懂的，在这次的环节中，我们是有可能超出 token 容量的。嗯，我也是非常近期才得知这个工作坊被录用了，所以我在很短的时间内尽量去申请了尽可能多的资源。嗯，所以在那个 env 文件里，实际上有呃多个不同的备用环境变量，你们可以通过取消注释或注释掉来切换。如果我们确实开始遇到 429 错误，嗯，大家懂的，呃也就是超出速率限制的错误。呃，所以，对。所以，我希望有足够的容量让大家都能去尝试这些模型，呃我们看看情况吧。呃，我的同事 Cedric 也在现场。呃，Cedric 会在我讲解的时候在场内走动，所以他可能也能呃帮忙处理一些问题。

<details><summary>Original English</summary>
All right. Uh since it's already like 11:12, I want to start talking about the workshop. Um so, I'm going to do this as a guided workshop, so I'll go through all the examples up here on screen, um but you can also uh try and follow along. So, the repo is there, the environment variables are there. Uh so, the environment variables give you access to a bunch of Foundry models that I've deployed on uh Microsoft Foundry project. Um and they have a certain amount of token capacity. It is possible that we are going to go over the token capacity um in you know, in this session. Um I only got found out very recently that this workshop was accepted, so I tried to get as much resources as I could in the small period of time. Um so, in that EMB file, there is actually uh multiple different possible environment variables that you can comment in or comment out. If we do start getting 429s, um you know, uh rate limit exceeded errors. Uh so, yeah. So, I'm hoping that there's enough capacity for all of you to be able to try out those models, and uh we will see. Uh I also have my colleague Cedric here. Uh so, Cedric is going to be wandering around while I'm talking, so he might be able to help uh with with issues as well.
</details>

呃如果你，在配置代码方面，如果你机器上已经安装了 Python 和 UV，那你可以 git clone 这个仓库并运行 `uv sync`，一旦你有了那个 `.env`，这就应该包含了你运行这些示例所需的一切。呃要不然的话，你也可以建一个 GitHub Codespace。那基本上就是一个浏览器里的 VS Code，里面已经为你配置好了一切。

<details><summary>Original English</summary>
Uh if you In terms of setting up the code, if you already have Python and UV on your machine, then you can do a get clone of the repo and run UV sync, and that should have everything you need to run the examples uh once you have that .env. Uh otherwise, you can make a GitHub code space. That's uh basically a VS code in the browser that has everything set up for you.
</details>

呃现场有谁用 UV 吗？Cedric 想了解一下。

<details><summary>Original English</summary>
Uh who here uses UV? Cedric wants to know.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

看来它现在还不是第一名。

<details><summary>Original English</summary>
So, it's not number one yet.
</details>

不过，另一个问题，谁用 Python？

<details><summary>Original English</summary>
But, the other question here, who uses Python?
</details>

好的，人多多了。好的。

<details><summary>Original English</summary>
All right, then more people. Okay.
</details>

>> 这里几乎人人都用 Python。

<details><summary>Original English</summary>
>> Pretty much everyone uses Python here.
</details>

>> 是的。噢，你算重叠人数了吗？好的。行。好的，所以如果你刚才还没给那个屏幕拍照，现在拍一下就行。要不然的话，Cedric 手机里也有照片，如果你们需要那些链接，他可以在场内走动提供。

<details><summary>Original English</summary>
>> Yeah. Oh, did you count the overlap? All right. Okay. All right, so if you didn't take a picture of that screen yet, just take a picture of it now. Otherwise, Cedric also has a picture of it on his phone, so he can go around if you need those links.
</details>

### 模型对比与评测目标

呃，那么这个工作坊的目标就是能够去体会不同的，大家懂的，呃顶尖模型之间的差异，看看它们有什么不同，以及，大家懂的，你可以对它们做哪些改进。所以我设置了一大堆不同的示例，还有评估和优化手段，我们可以通过这些来提升我们在不同模型上的体验。呃，而且我认为这对我们所有作为 AI 工程师的人来说都是非常非常重要的一件事，因为大家也看到了，一直都有非常多的新模型推出。而且，大家懂的，美国政府随时都可能切断对某个模型的访问。所以我们需要，就像，我们需要有备选方案，对吧？所以我们需要能够，大家懂的，把我们的 AI 应用对准不同的模型，而且让它依然能够工作，或者知道该如何改进它。呃，所以这里的目标就是去获取关于更多模型的经验。

<details><summary>Original English</summary>
Uh, so the goal of this workshop is to be able to get a feel for the differences between the different, you know, uh, top-of-the-line models and see how they differ and, you know, what you can improve about them. So, I've set up a bunch of different examples and also evaluations and optimizations that we can do to improve our experience across models. Uh, and I think this is a really important thing for all of us to just be to be doing as AI engineers because, you know, as you've seen, like, there's so many new models that come out all the time. And, you know, the US government at any point could cut off access to a model. So, we need to like, we need to have options, right? So, we need to be able to, you know, point our AI applications at a different model and and have it still work or know how to improve it. Uh, so that's the goal here is to get more experience with more models.
</details>

所以，呃这些是我部署在 Microsoft Foundry 内部的模型。呃，我有 uh GPT-5 5，那是我平时一直用的标准模型。然后我还有 Kimi K2.6，那是一个呃较新的模型，效果相当不错。我有 DeepSeek V4 Flash。然后我还有 Mistral Large 3。所以这就是我们在这个工作坊中要对比的四款模型。

<details><summary>Original English</summary>
So, uh, these are the models I've deployed inside Microsoft Foundry. Uh, so I've got uh, GPT-5 5, that's a standard one I use all the time. But, then I've got Kimmy K2.6, that's a uh, more recent one that's quite good. I've got Deep Seek V4 Flash. And then I have Mistral Large 3. So, these are the four models that we'll be comparing in this workshop.
</details>

嗯，所以正如我刚才所说的，为了配置这个工作坊，这是大家要进的仓库。所以，如果你机器上没有 Python，你可以直接点击 Code 按钮，这里会有一个很大的按钮写着 Create codespace。你点击它，它就会创建一个 codespace。然后这就是呃 codespace 了，这里面有嗯，我已经放好了 `.env`，不过大家要去获取我放在上面的另一个嗯 URL 来拿到 env。它会转到这里的这个文件。你把它下载下来，打开它。然后你用里面的内容创建一个 `.env`，明白吗？这就是指向部署了那四款模型的一个 Foundry 项目。

<details><summary>Original English</summary>
Um, so as I was saying, you can in order to set up the workshop, here's the repo that that you're all into. So, if you don't have Python on your machine, you can just click on the code button and there'll be a big button here that says create code space. So, you click on that, it'll make a code space. So, then here's the uh, the code space and then this has um, I've already put the dot env, but then you go and you grab that other um URL that I put up there to get the env. That goes to this file here. You download it. You open that. And then you create a dot env with the contents, okay? So, this is pointing at a that foundry project that has those four models deployed.
</details>

正如大家所见，那确实有，大家懂的，它有 token 限制。所以如果我们开始遇到速率限制，你可以开始，你可以尝试这些同样部署了这四个项目的其他模型。另外我还有一个专门针对 Anthropic 的独立项目，仅仅是因为那个项目有不同的条款。好的。

<details><summary>Original English</summary>
As you've seen, that does have you know, it has token limits. So, if we start getting rate limits, you can start you can try these other models that also have the four project deploys. And then I have a separate one specifically for Anthropic just because it has different terms for that project. All right.
</details>

所以，所以是的，一旦你把它配置好，`uv sync` 就会同步你 Python 所需的所有包。好的，这就是环境配置。

<details><summary>Original English</summary>
So, so yeah, and then once you've got that set up, then you v sync will sync all of the packages that you need for Python. All right, so that's the setup.
</details>

### 首个示例：字母计数与提示词工程

现在，我要实际去过一遍，在这里操作它，这样大家就能，大家懂的，想跟的话可以跟着做，或者也可以单纯看我看我操作。

<details><summary>Original English</summary>
Now, I'm going to actually go through it and do it do it up here so that you can you know, hopefully follow along if you want, or you can just watch watch what I do.
</details>

所以正如我刚才所说，我们确实有这四款模型，你仅仅通过基准测试也可以对比模型。你会觉得，“噢，大家懂的，这个模型质量基准测试很好，安全基准测试也很好。”你还可以查看大家懂的成本、吞吐量之类的信息。你可以对这些模型有多好建立起这种大致的概念，但在将其用于你的特定场景之前，你并不能真正知道一个模型到底有多好，因为使用模型的方式有太多种了。而某一项具体的基准测试并不能真正告诉你它在你的场景下表现如何。所以这就是我们在这个仓库里所准备的：海量的不同场景，我们可以在每个场景中尝试这些模型。所以我们要从非常非常基础的内容开始，准备好了吗？

<details><summary>Original English</summary>
So, as I was saying, we do have the four models, and you can compare models just doing benchmarks. You're like, oh, you know, this one has good quality benchmarks and good safety benchmarks. You can also look at you know, the cost and thoroughput and stuff like that. And you can get this approximate notion for how good these models are, but you don't really know how good a model is until you use it for your particular scenario because there's so many different ways of using models. And a particular benchmark isn't really going to tell you how it's going to work for your scenario. So, that's what we have in this repo here is a ton of different scenarios, and we can try out these models for each of them. So, we're going to start really really basic, all right?
</details>

就是一次让大语言模型做点事情的单一 LLM 调用。大家能看到，对于每一个这样的文件，它们都是以 model 变量开头的，并且默认设为 GPT-3.5。这算是我们的基准线。显而易见，它是一个非常优秀的模型。

<details><summary>Original English</summary>
So, just a single LLM call that asks the LLM to do something. So, what you see for each of these files is that they all start off with the model variable and they default to GPT-3.5. That's kind of our baseline. It's obviously it's a very good model.
</details>

但如果我们想尝试不同的模型，我们只需取消注释那一行，那就会成为被调用的模型。这里的这个文件是使用 OpenAI Python SDK 连接到 Foundry 的 URL，并传入环境变量里的密钥。而我们在这里给出的提示词是：“在下面这句话中，字母 E 出现了多少次？The elderly gentleman eagerly entered the elevator. 请仔细数。”

<details><summary>Original English</summary>
But then if we want to try a different model, we can just uncomment that line and that will be the model that gets used. So, this file here is connecting using the OpenAI Python SDK to the Foundry URL and passing in the key from the environment. And the prompt we're doing here is how many times does the letter E appear in the following sentence? The elderly gentleman eagerly entered the elevator. Count carefully.
</details>

好的。然后我们把它发送给 OpenAI responses API 并说明：“来，用这个模型配合这个提示词，然后我们来看看原始输出，对吧？”所以我们做的是让大语言模型去数数的经典事情。我们来看看，大家懂的，它们能做到什么程度。

<details><summary>Original English</summary>
All right. So, then we send that to the OpenAI responses API and say, "Here, use this model with this prompt and then let's see the raw the output, right?" So, we're doing the classic thing of asking LLMs to count. And so, we'll see, you know, how well they're able to do.
</details>

所以我要输入 `uv run examples` 加上这里的这个文件名。这些全都在，大家懂的，在 README 里面。所以我们就是逐个过一遍。大家直接从那里复制粘贴就行。好的。GPT-3.5 实际上非常擅长数学，在数学方面好得惊人。我的同事们最近一直在用它跑大量的金融基准测试，他们惊叹道：“天呐，它心算能力太强了。”所以它实际上准确算出了这句话里有 13 个 E，对吧？现在我们来尝试，现在我们直接修改它，对吧？好的，比方说我们想尝试 Kimi。

<details><summary>Original English</summary>
So, I'm going to say UB run examples with the name of this this file name here. And this is all in, you know, in the read me. So, we're just going through one by one. So, you can just copy-paste from there. All right. So, GPT-3.5 is actually very good at math, surprisingly good at math. My colleagues have been running a lot of finance benchmarks on it lately and they're like, "Oh my god, like it does so much math in its head." So, it does actually get this correct that there are 13 E's in this sentence, right? So, now let's try Now we just change it, right? So, okay, let's say we want to try Kimmy.
</details>

那我们就去切换成 Kimi，现在 Kimi 就会是被调用的模型了。我们来看看，“好的，Kimi 能数得和 GPT-3.5 一样好吗？”

<details><summary>Original English</summary>
So, we go and we change to Kimmy and now Kimmy will be the model that's used. And we see, "Okay, can Kimmy count as well as GPT-3.5?"
</details>

它做到了。它给出了 13。好的。现在你可能会想，“噢，这会不会太容易了？我们来试试 DeepSeek V4 Flash 吧。”

<details><summary>Original English</summary>
And it does. It gets 13. All right. Now you might be thinking, "Oh, is this just too easy? Let's try DeepSeek V4 Flash.
</details>

这一次它得出了 6。好的。所以它漏掉了其中的 7 个 E，对吧？所以我们能立刻看出来，大家懂的，DeepSeek V4 和前两款模型之间绝对存在差异。最后我们要试试 Mistral。这一个得出了 8。呃所以，我们看到这里是有差别的。好的。

<details><summary>Original English</summary>
And this time it gets six. Okay. So, it missed out on seven of the E's, right? So, we can immediately see that there's definitely difference between you know, DeepSeek V4 and those first two models. And then finally, we'll try Mistral. And this one gets eight. Uh so, what we see there's a difference here. All right.
</details>

所以，当你看到这个，你会觉得，“好吧，我想能够用上所有这些模型。”然后你就开始做一些提示词工程。你会想，“好吧，如果我说，呃大家懂的，‘把句子拆分成单词，按每个单词计数，呃求和，展示你的推理过程，对吧？’”我们来试试，我们来试试那样，对吧？而且，大家懂的，我们可以修改我们的打字错误，虽然这无伤大雅。好的。那我们就用 Mistral 来试试，看看通过一点点提示词工程，我们能不能在这里得到一个更好更好的回答？

<details><summary>Original English</summary>
So, when you see this and you're like, "Well, I want to be able to use all these models." Then you start doing some prompt engineering. You're like, "Okay, what if I say, uh you know, break the sentence into words, count per word, uh sum, show your reasoning, right?" Let's try Let's try that, right? And you know, we can fix our typos, not that it matters. All right. So, let's try it with Mistral and see with a little bit of prompt engineering, can we get a better better response here?
</details>

好的。它算对了，对吧？所以，大家懂的，通过把它拆开，在这里做一点思维链，它就能够得出正确的答案，对吧？所以，

<details><summary>Original English</summary>
All right. And it got it, right? So, you know, by breaking it up, doing a little chain of thought here, it was able to come up with the correct answer, right? So,
</details>

<!-- chunk 2/7 -->

马上我们就能看出，不同模型之间显然存在差异；如果我们更改提示词，就能得到不同的输出。

<details><summary>Original English</summary>
immediately, we can see that there's obviously differences across models and if we change prompts, you know, we can get uh different outputs.
</details>

好，现在让我们看点更有意思的，进入更贴近现实世界的场景。那么，我们来看看 RAG。RAG 依然是主要的用途之一。可以说，其实一切皆可算作 RAG。智能体本质上也是 RAG。

<details><summary>Original English</summary>
All right. So, now let's get more interesting and go to more real-world scenarios. Uh so, let's look at RAG. So, RAG is still one of the big uses. Arguably, really everything is RAG. Agents are RAG, too. Um
</details>

那么，我们有这个……RAG 就是当你让大语言模型根据某些上下文来回答问题，对吧？对 RAG 来说，重要的一点是你希望它回答问题并严格立足于上下文。你并不希望它凭空编造任何纯粹来自其权重的内容，对吧？你试图强制它紧扣上下文，对吧？而在我看来，各个模型之间真正的差异就在于：较小的模型、能力较弱的模型，其实更有可能直接调用自身的权重，并假装那是上下文的一部分。

<details><summary>Original English</summary>
So, we have this So, RAG is when you ask an LLM to answer a question based off some context, right? And the thing that's important for RAG is that you want it to answer the question and stay grounded in the context. You don't want it to make up anything that is just from its weights, right? You're trying to force it stick to the context, right? And that's what I find really varies across the models is that the smaller models, the less powerful models are actually much more likely to go to their weights and pretend it was part of the context.
</details>

### RAG 场景测试与模型幻觉

我们这里有一份关于木蜂（carpenter bees）的数据集，我们向它提问：“蜜蜂和木蜂筑巢的主要差异是什么？”但这个数据集里只有木蜂的信息。

<details><summary>Original English</summary>
Um so, what we have here is um we have a data set about carpenter bees and we ask it a question, "What are the key differences differences between how honey bees and carpenter bees build their nests?" But this data set only has carpenter bee information.
</details>

所以，它实际上应该只能回答关于木蜂的内容。在这种情况下，一个好的回答会告诉我木蜂的信息，然后说：“抱歉，我无法告诉你蜜蜂的情况。我不知道。”我们给它的指令是：“嘿，你的任务是基于来源回答并引用来源。这是你的问题，这是你的参考来源。”好，我们现在就来试一下，看看会得到什么结果。

<details><summary>Original English</summary>
Uh so, it should only actually be able to answer about carpenter bees. So a good response in this case would tell me the carpenter bee information and then it say, "Sorry, I can't tell you about honey bees. I don't know." Um, so we tell it like, "Hey, your job is to answer based on the sources, cite the sources. Um, here's your here's your question, here's your sources." All right, so let's go ahead and try that out and see what we get.
</details>

好的，它在……是的，当它首先进行搜索时，非常基础的搜索。好的，正在发送……完成了搜索。好的，我们看到的，它说数据集没有提供蜜蜂筑巢的细节。这正是我们真正希望看到的。这是来自 GB55 的结果。GB55 非常清楚自己不知道什么。

<details><summary>Original English</summary>
All right, and it's Yeah, so when it's doing the search first, very basic search. Okay, so it's sending did the search. All right, and what we see and it says the data set does not provide details on honey bee nest construction. So this is what we actually want to see. This is from GB55. GB55 is very good at knowing what it doesn't know.
</details>

现在我们来切换试试……Kimi 表现也很好。为了节省时间，我现在不会每次都展示每一个模型。

<details><summary>Original English</summary>
So now, let's try switching Um, Kimmy's also good as well. So I'm not going to show every model every time now just for for sake of time.
</details>

我们来试试 DeepSeek，对吧？因为我们已经看到这里存在差异。现在 DeepSeek 再次说明提供的来源不包含相关信息。好的，DeepSeek 在这里表现很好。现在我们来看 Mistral。Mistral，抱歉。Cedric，Mistral 怎么读？是法国的，对吧？法国公司？

<details><summary>Original English</summary>
Um, so let's try Deep Seek, right? Cuz we've already seen that, you know, there's a distinction here. Now Deep Seek, once again, says provided sources do not contain information. All right, so Deep Seek did a good job here. And now let's go to Mistral. Uh, Mistral, sorry. Cedric, how do we say Mistral? It's French, right? French company?
</details>

>> Mistral。

<details><summary>Original English</summary>
>> Mistral.
</details>

>> Mistral。Cedric 将充当我的法语翻译了。每次我需要读它的时候，你就直接念出来就行。

<details><summary>Original English</summary>
>> Mistral. Cedric's going to be my French translator. Every time I need to say it, you're just going to say it.
</details>

现在，Mistral。

<details><summary>Original English</summary>
Now, Mistral.
</details>

嗯？

<details><summary>Original English</summary>
Mhm?
</details>

好的。

<details><summary>Original English</summary>
Yeah, okay.
</details>

Mistral。

<details><summary>Original English</summary>
Mistral.
</details>

那么，Mis- Mis-
对于 Mistral……

<details><summary>Original English</summary>
Um, so Mis- Mis- With Mistral
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 我们确实看到 Mistral 实际上从其权重中给出了回答，尽管该信息并未包含在来源中。所以这就是一个典型的例子：模型调用了自身的权重，尽管我们并不希望它这么做，对吧？现在我们可以尝试强制约束它。我们同样可以尝试进行提示词工程。我们可以说……等等，实际上这样写：

<details><summary>Original English</summary>
>> Um, we do see that Mistral actually answered uh, from its weights uh, even though that information was not in the sources. So this is an example where a model went into its weights even though we didn't want it to do, right? Now we can try to force it. Once again, we can try to do prompt engineering. Uh, we can say uh, wait, actually so it would say
</details>

“如果某项信息的答案不在来源中，就说未提供来源。”我想我之前就是这样让它起作用的。我来试一下，“并且不要编造答案。”好的，我们来试一下这个。

<details><summary>Original English</summary>
uh, if the if the answer for a bit of info is not in sources. Say no source provided. I think this is what I got it to work. Uh oh, I will try that and do not make up an answer. All right, let's try this.
</details>

>> [嗤笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 所以，我们正试图强制让它意识到自己何时给出了不在权重中的信息。有时候如果你强制要求它说：“嘿，你在回答中返回的每一项信息，都必须证明你是从来源中获取的，对吧？”

<details><summary>Original English</summary>
>> So, we're trying to force it to realize when it's giving us information that's not in the weights. And sometimes if you force it to say, "Hey, for every bit of information that you're giving back in your answer, you have to prove that you got that from from the sources, right?"
</details>

在这里，我尝试让它将回答中的每一件事物与来源关联起来，也许这样能强迫它意识到：“噢，等等，这实际上并不在我的……并不在我的参考答案中。”

<details><summary>Original English</summary>
Um so, here I'm trying to have it associate each of the things in that in that answer with a source and um and maybe that will force it to realize, "Oh, wait a second, that wasn't actually, you know, in my in my answers here."
</details>

好的，它还在继续。它打算思考……它正在非常深入地思考这个问题。

<details><summary>Original English</summary>
All right, it's still going out. It's going to think it's thinking really hard about it here.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

出来了。“除与木蜂的相互作用外，未提供蜜蜂细节的来源。”

<details><summary>Original English</summary>
And there we go. Honeybee details are no source provided beyond interactions with carpenter bees.
</details>

>> [笑声与惊呼声]

<details><summary>Original English</summary>
>> [laughter and gasps]
</details>

>> 它确实辨别出了哪些内容属于未提供来源，但它依然给出了这些信息。所以我们稍微接近了目标一点。但正如大家所见，这绝对是我在 RAG 中观察到的差异，而 RAG 是我接触最多的领域。因此，当你在评估用于 RAG 的模型时，这是你需要考量的一点：这些模型是否愿意承认自己不知道的内容？它们胡编乱造的可能性有多大？

<details><summary>Original English</summary>
>> Um so, it definitely knew when things were not source provided. It still gave the information. So, we got a little closer. But as you can see, this is definitely uh a difference that I see with rag and rag is what I work with the most. Uh so, it's it's something you want to evaluate when you're looking at models to use with rag is are the models willing to admit what they don't know, how likely are they to make stuff up?
</details>

### 多模态图像输入测试

好，现在让我们转到图像输入。这些模型中有许多是多模态的，因此它们接受图像作为输入。在图像输入方面，有许多非常酷的场景可以实践。我们本地有一些文件，我们打算把它们发送给大语言模型，并询问关于这些文件的一些问题，对吧？

<details><summary>Original English</summary>
All right, so now let's move to image input. A lot of these models are multimodal, so they will accept images as input. And you know, there's lots of really cool um situations you can do with image input. So, here we've got some files locally and we're just going to send them to the LLMs and ask them some questions about the files, right?
</details>

我把文件展示给你们看。
示例，图像输入。好的。

<details><summary>Original English</summary>
Um I'll show you the files. Examples, image input. Okay.
</details>

好的。我们这里的图片有这一张：这是一头原牛（aurochs），不是独角兽。

<details><summary>Original English</summary>
All right. So, the files we have here are this picture. This is an aurochs, not a unicorn.
</details>

这张图片：这是我在哥斯达黎加看到的一些鳄鱼，我当时非常害怕它们。

<details><summary>Original English</summary>
This picture. This is of some crocodiles that I saw in Costa Rica that I was very afraid of.
</details>

然后我们还有这张图片，这是一张植物清单。基本上就像是一个表格的屏幕截图，里面的字体非常小。

<details><summary>Original English</summary>
And then also we have this picture which is a list of plants. Basically like a screenshot of a table with some really small fonts in it.
</details>

我们让每个大语言模型解读其中的每一张图像，对吧？首先我们问：“噢，这是一只独角兽吗？”对吧？说出它不是独角兽应该很容易。很好。然后我们问：“嘿，这些是短吻鳄（alligators）还是真鳄（crocodiles）？”这有点棘手。根据它们的吻部特征，它们实际上是真鳄。我花了很长时间阅读维基百科上关于鳄鱼的页面，你必须观察它们的吻部才能判断出来。幸运的是，GPT-5.5 也狂刷过维基百科，所以它知道一旦看到那个吻部，那就是真鳄。接着是最便宜的植物，它准确地在那个字体相当小的表格截图中找到了最便宜的植物。GPT-5.5 能做到这一点确实相当令人赞叹。

<details><summary>Original English</summary>
So, we're asking each of the LLMs to interpret each of the images, right? So, first we say, "Oh, is this a unicorn?" Right? That should be easy to say it's not a unicorn. Great. Then we say, "Hey, are these alligators or crocodiles?" That's a bit tricky. They are actually crocodiles because of their snout. I spent a lot of time reading the Wikipedia page about crocodiles and you got to look at their snout and then you know. Luckily, GPT-5.5 has also been on a Wikipedia binge and so it knows that when it sees that snout, then that is crocodiles. And then the cheapest plant, it correctly found the cheapest plant in that like fairly small text screenshot of a table. So, that's pretty impressive that GPT-5.5 could do that.
</details>

现在我们来试试……对于这些模型，我们不能使用 DeepSeek，因为 DeepSeek 只接受文本，它不是多模态模型。所以我们只测试 Kimi 和 Mistral。

<details><summary>Original English</summary>
So, now let's try it with Now, for these models, we can't use DeepSeek cuz DeepSeek only accepts text. It's not a multimodal model. So, we're only going to try Kimmy and Mistral.
</details>

它认出了原牛。好的，很好，确认它能正常工作。好的。接下来关于鳄鱼，它确实正确地说是真鳄。

<details><summary>Original English</summary>
So, you know, it figured out the aurochs. Okay, good. Just making sure it works. All right. And then for crocodiles, it does say crocodiles correctly.
</details>

然后是最便宜的植物，它找出了最便宜的植物。因此，Kimi 的表现也同样非常棒。

<details><summary>Original English</summary>
And then cheapest plant, it got the cheapest plant. So, Kimmy is doing a great job as well.
</details>

最后，我们来看看 Mistral。在这里。我们看一下。好的。它知道这不是独角兽，但它不知道这是一头原牛。

<details><summary>Original English</summary>
And then finally, let's go to Mistral. Here. Let's see. All right. So, you know, it knows it knows it's not a unicorn. It didn't know it was an aurochs.
</details>

这一张，它不太确定。它认为它们是短吻鳄。

<details><summary>Original English</summary>
This one, it wasn't sure. It thinks they're alligators.
</details>

它在观察时显得更吃力，它认为它们是短吻鳄。然后关于植物，它挑出了一款 2.30 美元的植物，这比最便宜的植物贵得多；它原本应该找到一款 58 美分的。因此，Mistral 无法解答这类图像问题。问题就在这里：在多模态理解方面，你其实做不了太多提示词工程，因为模型要么能理解某张图像，要么就是理解不了。如果你清楚自己处于非常特定的专业领域，并且能就如何读取某种特定图表给它提供一些提示，你或许可以做一些提示词工程。

<details><summary>Original English</summary>
So, it you know, it's having a harder time looking at the it thinks that they're alligators. And then for the the plants, it pulled out a plant that's $2.30, which is way more expensive than the cheapest plant. It was supposed to find one for 58 cents. So, the Mistral isn't able to answer these kind of images. Now, here's the thing, when it comes to multimodal understanding, you can't really do much prompt engineering cuz either like the like the the model either understands an image or it doesn't. Like you might be able to do some prompt engineering if you know you're in a very particular domain and there's some hints that you can give to it about how to read a particular kind of graph.
</details>

但在图像输入方面，关键真正是在于弄清楚：针对你准备发给大语言模型的那类图像，大语言模型能否理解这些图像？它是否适用于那种场景，对吧？因为很可能 Mistral 非常擅长某些特定类型的图像任务，只是不擅长当前这个任务，对吧？所以这一切都在于摸清你想执行的任务是什么，以及该模型能否胜任。

<details><summary>Original English</summary>
Um but really with image input, it's about figuring out, you know, for the kind of images that you're going to send to the LLM, does the LLM understand those images? Is it going to, you know, is it going to work for that scenario, right? Um because it may be that, you know, maybe Mistral is really good at particular kinds of image tasks, but just not this, right? So, it's all figuring out what is the task you want to do and is the model going to do a good job at it?
</details>

多模态有趣的地方还在于，很多此类任务也取决于语言，对吧？在这里我使用的是英语。记住，所有这些模型都极度以英语为中心，但如果你切换到另一种语言——比如我用西班牙语询问它们是 caimanes 还是 cocodrilos——它实际上认为……给出的答案是错误的，因为它的脑海中对这些不同的词汇以及它们如何对应到英语产生了极大混淆。这变成了一项过于艰巨的任务：既要理解短吻鳄与真鳄的区别，同时还要记住 caiman 意味着

<details><summary>Original English</summary>
Now, what's interesting with the multimodal, too, is that a lot of these also depend on the language, right? Here I'm using English. Remember, all these models are super English-centric, but if you switch to a different language, like if I ask in Spanish if they're caimanes or cocodrilos, it actually thinks uh it says it gives the wrong answer because it's getting so confused in its head between these different like words and how they map across English. Like it just becomes too hard of a task both understand the difference between alligators and crocodiles and also remember that caiman means
</details>

<!-- chunk 3/7 -->

在西班牙语里是短吻鳄（alligator），跟我们在佛罗里达见到的那种凯门鳄（caiman）不是同一种东西。总之，挺有意思的是，一旦切换到西班牙语，它就没法完成任务了。所以这也是需要牢记的一点，尤其是我们在加利福尼亚，很多时候在这里开发应用程序时都是双语的，因为这里有很多人，你知道，50% 的人说西班牙语。所以，换了语言之后，效果可能就会有所不同。

<details><summary>Original English</summary>
alligator in Spanish and is not the same thing as the caiman that we have in like Florida. Anyway, it's like it's fascinating to see that once we switch to Spanish, it fails at the task. Um so, that's another thing to keep in mind, especially we're in California, a lot of times when we develop applications here, they are bilingual cuz a lot of, you know, 50% Spanish-speaking here. Um so, you know, your your mileage may vary as you change languages.
</details>

### 函数调用与工具调用

好，现在我们来看函数调用（function calling），也叫工具调用（tool calling）。实际上，工具调用就是所有 Agent 的基础。所有的 Agent 都是基于工具调用的。这是大语言模型在训练过程中专门训练出来的一种能力。它们经过训练，能够查看一个或多个函数定义，并结合用户输入判断：“好，根据这个用户输入，我想用这些参数来调用这个函数，然后直接返回结果。”

<details><summary>Original English</summary>
Okay, so now let's go on to function calling, also known as tool calling. So, tool calling is in fact the basis of like all agents. All agents are based off of tool calling. And this is a a capability that the LLMs are trained with specifically during the training process. So, they are trained to be able to look at a definition of a function or multiple function definitions and look at the user input and say, "Okay, based off that user input, I want to call this function with these arguments and and then, you know, just return that."
</details>

在当前这个示例中，我使用 JSON Schema 定义了一个函数。这就是大语言模型能够理解的格式。我设定：“好，这是我的函数。名称是 `create calendar event`。它有这段描述，这些是它接收的参数。它接收一个 `title`，类型是字符串。这里是描述，对吧？”所有这些内容都会发送给大语言模型。我们把这个完整的 JSON Schema 发给大语言模型，并告诉它：“这里有一个函数。你需要决定是否要调用它，以及如何调用它，对吧？”

<details><summary>Original English</summary>
So, in this example here, I'm defining a function using JSON schema. This is what the LLMs understand. So, I say, "Okay, here's my function. It has the name create calendar event. It has this description and these are the parameters it takes. It takes a title with this that's a string. Here's a description, right?" And all of this is all going to get sent to the LLM. So, we send this full JSON schema to the LLM and say, "Hey, here's the function. You got to decide whether you're going to call this and how you're going to call it, right?"
</details>

所以实际上，尽管这看起来像是一个对象，但这本身就是 Prompt 工程（prompt engineering）。这里的每一项其实都是我在决定什么对大语言模型最有利，对吧？我应该用什么类型？这里应该添加什么描述？这些参数应该叫什么名字？因为大语言模型会根据所有这些信息来决定如何调用该函数。

<details><summary>Original English</summary>
So, this is in fact, even though this this is like an object, this is prompt engineering here. Everything here is actually like me deciding what is going to be the best for the LLM, right? What type should I use? What description should I add here? What should be the names of these parameters? Cuz the LLM's going to decide based on all that information how it's going to call this function.
</details>

然后我们有一条用户消息。用户的内容大概是：“能帮我往日历里加个日程吗？是一个平台团队的同步会。有我、来自 Ange 的 Sarah、Marcus，还有新来的产品经理 Priya。时间是明天下午 1:30。在线上开，用 Microsoft Teams，好吗？”然后我们告诉大语言模型：“你是一个日历助手。今天是 6 月 29 日星期一。使用可用工具来处理用户的请求。”接着我们把工具传给它。此时大语言模型会查看用户请求，并查看这些工具。在这个例子中，它只有那个 `create calendar event` 工具。它会判断：“这里有没有我可以用来回答用户的工具？”

<details><summary>Original English</summary>
Uh so, then we have a user message. So, it's like So, the user's like, "Oh, can you throw something on my calendar? It's a platform team sync. Me, Sarah from Ange, Marcus, the new PM Priya. Tomorrow at 1:30 p.m. It's virtual on Microsoft Teams, okay?" So, then our then we tell the LLM like, "Hey, you're a calendar assistant. Today is Monday, June 29th. Use the available tools to process the user's request." And we send it the tools. And so, now the LLM is looking at the user request, looking at the tools. And in this case, it just has that create calendar event. And it's going to decide, "Hey, is there a tool here I can use to answer the user?"
</details>

接着我们就来看看它决定进行哪些工具调用。好了，请看这里。这是非常底层的工具调用。一旦我们去构建 Agent，就会在此之上进行抽象，但我希望能从我们能做的最底层的工具调用开始讲起。大语言模型返回的内容只是函数的名称以及它希望你传递的参数。大语言模型本身并不执行函数调用，这得由我们来完成。好，我们可以看到，我把预期结果放在了左边，以便大家对比查看实际结果。GPT 55 确实把我（me）加成了参会人，这并不是我想要的，不过其他方面表现得相当不错。接下来我们试试 DeepSeek，看看 DeepSeek 在这个任务上的表现如何。

<details><summary>Original English</summary>
Uh and then we're just going to go through and see what tool calls it decides to make. Uh so there we go. So in and this is like really low-level tool calling here. Uh once we build an agent, we're going to abstract on top of this, but I wanted to start with the most low-level tool calling we can do. And the LM just responds back with here's the name of the function and here's the arguments that I want you to send. The LM itself doesn't call the function. That's up to us to do. All right, so what we can see is that uh I put my I put the expected on the left just so you can see and we can see the actual. So GPT 55 did add me as an attendee, which I didn't really want. Um but it did pretty good otherwise. So let's try uh Deep Seek and see how Deep Seek does with this one.
</details>

因为在做工具调用时，我们想观察的是：它是否调用了正确的工具？在这个例子中确实是。它调用了 `create calendar event` 工具。另外就是它传入的参数是否符合我们的预期，对吧？我们会有某些预期的参数。在这个例子中，DeepSeek 把“你”（you）放进了参会人里。然后在地点一栏，它填了 `virtual (Microsoft Teams)`，这并不是我要求的，对吧？所以它没有那么严格地遵循我的参数约束。我们再试试 Mistral，看看它的表现。

<details><summary>Original English</summary>
Cuz what we want to see like when we're doing tool calling, we want to see is it calling the right tool? So it is in this case. It is calling the create calendar event tool. And is it passing in the arguments that we expect, right? We have certain arguments we expect. In this case, Deep Seek put you as an attendee. And then for the location, it said virtual {parentheses} Microsoft Teams, which is not what I asked for, right? So it's not adhering to my argument um constraints as much. Let's try Mistral as well. And see how it does.
</details>

看到这些之后，我就开始意识到：“好吧，这里存在一些歧义，对吧？”如果它用错误的参数进行了调用，就说明存在模糊不清的地方。我需要回到描述中去补充说明，比如“不要包含我或你，只包含具名的参会人”。你也可以写“如果提供了姓和名，就包含全名”，对吧？这样你就能看出自己在哪些地方写得还不够具体，进而去消除那些歧义，然后评估所有不同的输入，观察它的运行效果。

<details><summary>Original English</summary>
So once I see this, I can start to realize like, "Okay, there's some ambiguity, right?" And you know, if it if it called it with the wrong arguments, that means there's ambiguity. I need to go back into my descriptions and say, you know, uh you know, don't you know, don't include me or you, just named attendees. Um you know, you could say first and last if provided, right? So you start to see, you know, what what you haven't been specific enough about and start to clarify that ambiguity and then, you know, evaluate all the different um inputs and see how it's doing.
</details>

### 循环工具调用与执行效率

好，刚才讲的是基础的工具调用。接下来我们要做的——我们正一步步向 Agent 演进——下一步是在循环中进行工具调用（tool calling in a loop），对吧？当构建一个 Agent 时，它会循环调用工具，直到达成目标。我们用一个简单的 `calculate` 函数来进行演示。这个 `calculate` 函数接收一个数学表达式并返回输出结果，对吧？我们对求值这些数学表达式提供了基础支持。所以，我们基本上就是给它一道应用题，比如：“这家店正在打折。如果我买三件衬衫，并支付这么多税，我的总花费是多少？”

<details><summary>Original English</summary>
All right. So that was a basic tool calling. The next thing we want to do, we're building up to agents here. The next thing is to do tool calling in a loop, right? So when we have an agent, it's calling tools in a loop until it reaches a goal. Um so, we're going to demonstrate using this just a function calculate. So, this calculate takes a mathematical expression and returns back the output, right? And we have, you know, basic support for uh evaluating these uh mathematical expressions. So, we're giving it basically a word problem where it's like, "Oh, this store is having a sale. If I buy three shirts and pay, you know, this much tax, what's my total?"
</details>

这可以通过几种不同的方式来完成。它可以通过对那个计算器进行多次工具调用来完成，每次只处理一个小表达式，就像：“先算这个，再算这个，然后算这个，接着算这个。”或者，如果大语言模型非常聪明，它可以把所有这些合并成一个长表达式，只进行单次工具调用。所以，这里我们测试的是效率，对吧？很多时候，一旦引入了循环中的工具调用，不同模型之间的差异就在于它们的效率。它们能否更快地达到目标？能否用更少的工具调用完成相同的目标，对吧？这就是我们要考察的。唯一的系统提示词是：不要在脑子里心算。好的。

<details><summary>Original English</summary>
And this can be done several different ways. It could be done with multiple tool calls to that calculator call with like one little expression at a time, like, "Do this, and then do this, and then do this, and then this." Or, if the LM is very clever, it could batch all that into one long expression and do a single tool call. So, here we're testing efficiency, right? Where, you know, there's more like a lot of times once you have tool calling in a loop, the differences between the models is their efficiency. Are they able to get to the goal faster? Can they accomplish the same goal with less tool calls, right? So, that's what we're going to say. Uh the only system prompt is do not do math in your head. Okay.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

[倒吸气]

<details><summary>Original English</summary>
[gasps]
</details>

>> 那我们来看看。这主要是针对 GPT 55 的，因为它对自己的数学能力太自负了，总是试图在脑子里心算。真是“饶了我吧”。好了，GPT 55 确实在一个表达式里完成了全部计算。因此，它只用了一次工具调用就得到了最终结果。这很好，很迅速，为我们节省了时间。现在我们用 DeepSeek 试试。我一直跳过 Kimi 的唯一原因，是它其实是个非常优秀的模型，在大部分这些任务上，它的表现基本和 GPT 55 不相上下。好，现在我们可以看到 DeepSeek 的情况了。

<details><summary>Original English</summary>
>> So, let's see. Uh that one's really for GB55 cuz it's so proud of its math abilities that it's always trying to do it in its head. Like, "Come on." All right. So, GB55 indeed does the entire calculation in one expression. So, it only required one tool call to get to the final result. So, that's good. That's good. That's, you know, fast. It saves us time. So, now let's try with um DeepSeek. The only reason I skip Kimmy all the time is cuz it's actually a very good model, and so it does pretty much uh on par with uh GB55 uh for much of these. Okay. So, now we can see with DeepSeek,
</details>

它在一步步执行，进行了好多次——它调用了多少次？大概进行了 4 次工具调用，对吧？它最终依然得到了正确答案，但用了 4 次工具调用。而每一次工具调用都是一次额外的网络请求，对吧？所以，当我们在评估两个模型时，既要看最终答案，也要看得到那个最终答案花了多长时间，对吧？其实前几天 Kimi 确实表现出过一个挺有意思的现象。我们来看看它这次会不会再出现。因为大部分时候 Kimi 都运行得相当不错，但有时候在有点像自我反复核对时，会陷入奇怪的循环。

<details><summary>Original English</summary>
it is going through and it's doing and and and and it's doing like so many how many it did like four. It did four tool calls, right? So, it still got to the correct answer, but it took four tool calls. And every one of those tool calls is another network request, right? And so, you know, when we're evaluating two two models, we want to both look at the final answer, but also how how long did it take to get to that final answer, right? Um actually, Kimmy did do something really interesting the other day. Let's see if it does it again with this one. Cuz Kimmy most of the time works quite well, but Kimmy does sometimes get into weird loops um when it's kind of like double-checking itself.
</details>

好，这次它完成得很好。是的，前几天我测试 Kimi 时，它第一次尝试就得到了正确答案，然后又决定再做大约 4 次额外的调用来检查自己的步骤。当时我就想说：“不用了，你算得是对的，已经成了。”

<details><summary>Original English</summary>
Uh okay, this time it did well. Yeah, the other day when I did Kimmy, it like got the right answer on the first try and then decided to check its work with the like four other calls. I was like, "No, you're good. You're good."
</details>

[笑声]

<details><summary>Original English</summary>
[laughter]
</details>

>> [倒吸气]

<details><summary>Original English</summary>
>> [gasps]
</details>

>> 所以这就是我们在这里关注的指标，明白吗？就是它究竟需要调用多少次才能走到最后一步。

<details><summary>Original English</summary>
>> Um so that's what that's what we're looking at here, okay? Is how many how many calls does it actually need to get to the end.
</details>

### Agent 框架

好了，接下来我们可以进入 Agent 循环了。好，我现在讲得其实挺快的。好，不错。[笑声] 好的。现在我们已经掌握了基础，对吧？我们了解了工具调用，以及循环中的工具调用。因此现在我们可以真正构建一个像样的 Agent 了。为此，我们通常会使用 Agent 框架。我已经在这里预置了三个不同的 Agent 框架，供大家挑选自己喜欢的。我们有 LangChain、Pydantic AI 和 Agent Framework。我相信还有其他我遗漏的 Agent 框架，但希望大家能在这些里面找到自己喜欢的一个。所以这些——

<details><summary>Original English</summary>
All right, so next um we can go to uh agent loops. Okay, I'm actually going quite fast through this now, actually. Uh okay, good. [laughter] Um all right. So now we've got the basis, right? We've seen tool calling, tool calling in a loop. So now we can actually build like a proper agent. And for this, we'd usually use an agent framework. Uh I've gone ahead and put three different agent frameworks in here uh so that you can pick your favorite. So we have LangChain, Pydantic AI, and Agent Framework. Uh I'm sure there's other agent frameworks as well that I missed, but hopefully you can find one that you like there. Uh so these
</details>

<!-- chunk 4/7 -->

都是，你知道的，同样的思路。好的，我们想展示哪一个？

<details><summary>Original English</summary>
are all, you know, the same idea. All right, which one do we want to show?
</details>

有人投个票。

<details><summary>Original English</summary>
Someone vote.
</details>

LangChain。好的，LangChain 依然非常受欢迎，呃，希望今天大会现场也有一些 LangChain 的朋友。好的，对于 LangChain，我们使用的是 LangChain V1，嗯，如果你在过去一年里没试过的话，这是他们相当不错的、呃、最新的 SDK 版本。我们通过 LangChain 连接到 Foundry 模型。我们这里有一个旅行规划 agent，这是一个经典的例子。它拥有工具。我们有一个搜索航班的工具，搜索酒店的工具，以及检查预算以确认某趟航班和酒店是否符合预算的工具，呃，然后是搜索城市内活动的工具。呃，然后我加了一些中间件，这纯粹是为了让我能看到正在发生哪些工具调用。然后我们进行实际的 agent 调用。

<details><summary>Original English</summary>
LangChain. All right, LangChain is still very popular and uh hopefully there's some LangChain folks here today at the conference. All right, so with LangChain, we are using LangChain V1, um which is a a nice uh newest TK version of theirs if you haven't tried it in the last year. And so we connect to the Foundry models from LangChain. and what we have here is a travel planning agent, which is a classic example. So, it has tools. So, we have a tool for search flights, search hotels, and check budget to check if a certain flight and hotel fits within the budget, uh and then search activities within a city. Uh then I've got some middleware, which is just for me to see what tools are happening. And then we have the actual agent call.
</details>

这个 agent 有一个系统提示词，写着你要帮助用户查找航班和酒店。呃，你知道的，它这里有一些规则，比如同时搜索航班和酒店、偏好直飞航班、诸如此类、始终检查预算，最后根据剩余预算询问活动安排。然后我们有这条用户消息：“我下个月需要从旧金山飞往纽约市住 3 晚。我的总预算是 600（注：原声 6 600），我需要直飞航班和一项活动。”

<details><summary>Original English</summary>
So, the agent has a system prompt that says you're going to help users find flights and hotels. Uh you're you know, it has some rules here like search for both flights and hotels, prefer direct flights, yada yada, always check check budget, and then ask for activities at the end based off the remaining budget. Then we have the user message. I need to fly from SF to New York City next month for 3 nights. My total budget is 6 600, and I want direct flights and an activity.
</details>

好的。我们准备好了一切，然后运行该 agent。这里有一些额外的代码，只是把工具调用记录打印出来，以便我们观察。那么，让我们直接来试试看。

<details><summary>Original English</summary>
All right. So, we have all that, and then we are running the agent. There's some additional code here that's just logging out the tool calls so that we can see it. So, let's go ahead and try that out.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

这里会把发生的工具调用记录打印出来。我们首先使用的是 GPT 55。有意思的是，你会看到第一轮。

<details><summary>Original English</summary>
And so, this is going to log out the tool calls that happened. We're starting off with GPT 55 here. Now, what's interesting here, you'll see turn one.
</details>

我把这个调大一点。

<details><summary>Original English</summary>
Let me make this bigger.
</details>

第一轮，上面显示是并行的。大语言模型能做的一件事就是，呃，许多大语言模型都支持并行工具调用，如果你提供给它们一堆工具定义，它们可以建议在同一轮中同时调用多个工具。从性能角度来看这非常好，因为在你的服务器上，你实际上可以同时向两个不同的数据库并行发送请求，对吧？呃，所以只要它们彼此独立，这就是大语言模型能做的一件很棒的事，它会说：“嘿，这两件事可以并行完成。你为什么不一起做呢？”所以在第一轮中，GPT 55 提示“嘿，搜索纽约市的酒店，并且搜索从旧金山飞往纽约市的航班”，因为它判定这两者之间没有依赖关系。

<details><summary>Original English</summary>
Turn one, it says is parallel. So, one thing is you can do with LLMs is uh is like many LLMs support parallel tool calling where if you give them a bunch of tool definitions, they can suggest a multiple tools that can be called at the same time in the same turn. And this is really good from a performance perspective because on your server, you can actually file like you can send off requests in parallel to like two different databases, right? Uh so, as long as they're independent of each other, this is a great thing that LLMs can do is say, "Hey, these two these two things can be done in parallel. Why don't you do them?" So, uh GPT 55 on the first turn and "Hey, search for hotels in New York City and search for flights in uh from SF to New York City." cuz it's decided that there wasn't a dependency between them.
</details>

然后，一旦这些结果返回，一旦它拿到了所有选项，它就根据那次调用返回的航班费用和酒店费用执行了一次检查预算。

<details><summary>Original English</summary>
And then, once that came back, once it had all the options, it did a check budget um based off of the flight cost and the hotel cost that it got back from that call.
</details>

随后，它看了一下剩余预算是多少，接着使用剩余预算发起了一次搜索活动的调用。因此，对于这种场景来说，这可能是我们所能拥有的最高效的 agent 了。

<details><summary>Original English</summary>
And then, it saw what the remaining budget was and then it did a call for search activities with that remaining budget. So, this is probably the most efficient agent that we can have for this scenario.
</details>

那么，让我们看看换个模型是否能得到类似的，嗯，结果。

<details><summary>Original English</summary>
So, let's see if we get similar um results when we change models here.
</details>

嘟嘟嘟。

<details><summary>Original English</summary>
Do do do.
</details>

当然，在这里你甚至可以跨模型和框架进行切换与对比，对吧？因为每个框架的工具调用循环都略有不同。我们也称之为 harness（测试驱动载体），对吧？所以很多时候你想同时对比模型和 harness，你会发现它们之间存在着有趣的差异。好的。这次我们使用的是 Kimi，而 Kimi 并没有很好地进行并行处理。我不知道是因为 Kimi 不支持并行工具调用，还是它在这种情况下决定不这么做。

<details><summary>Original English</summary>
And of course, here you can even change and compare across both models and frameworks, right? Because every framework has a slightly different tool calling loop. We also call it the harness, right? So, a lot of times that you're you want to compare both models and harnesses and and you'll see there's interesting differences across them. All right. So, this time we're with Kimmy and Kimmy is not paralyzing uh as well. I don't know if that's because Kimmy doesn't support parallel tool calling or it's just deciding not to in this case.
</details>

所以这一次它做了同样——实际上，它发起了更多的调用。它执行了搜索航班和搜索酒店。它分了两轮完成，由于没有并行化，这已经降低了效率。接着，它决定发起两次检查预算的调用，因为我觉得它当时像是在检查多一个选项。然后，它执行了最后一步。因此，这个模型额外消耗了两次工具调用，耗时也更长，因为它没有把第一组轮次并行化。

<details><summary>Original English</summary>
So, this time it did the same Actually, it did even more calls. So, it did search flight and search hotels. It did over two turns, so that's already less efficient cuz it didn't paralyze. Then, it decided to do two calls to check budget cuz I think it was checking like one more option. And then, it did the final thing. So, this one took two extra tool calls and it took longer because it didn't paralyze that first uh set of turns.
</details>

好的，让我们看看用 DeepSeek 效果如何。

<details><summary>Original English</summary>
All right, let's see how we do with DeepSeek.
</details>

你也可以开始体会到为什么这很困难了，因为大家都会问我：“你该如何评估 agent？”Agent 是最难评估的，因为其中涉及的过程太多了。在整个执行过程中会发生非常多不同的事情。比如：它调用的工具正确吗？调用是否高效？是否在并行调用？嗯，在当前情况下，你知道，这个模型没有做任何并行化，嗯，但至少它只进行了四次工具调用。所以，你知道，算得上合理高效。然后是 Mistral，Mistral 通常——我们会看到 Mistral 经常会遗忘最后一步。

<details><summary>Original English</summary>
And you can start to see why it's hard cuz everybody asked me like, "How do you evaluate agents?" Agents are the hardest to evaluate because there's so much going on. There's so many different things that are happening along the way. It's like, are is it calling the right tools? Is it calling them efficiently? Is it calling things in parallel? Um in this case, you know, this one uh didn't do any parallelizing, um but at least it only did four tool calls. So, you know, reasonably efficient. And then Mistral Mistral often will see Mistral often forgets the very last step.
</details>

所以我们来看看。嗯，你知道，这是 agent 的另一个问题。有时 agent 当达到——一旦它们的上下文窗口被填满，就可能会遗忘一些较早的指令。它们在留意原始步骤方面可能不会那么彻底。

<details><summary>Original English</summary>
And so, we'll see. Um you know, that's the other problem with the agents. Sometimes agents, when they get to the like once their context window fills up, they might forget some earlier instructions. They may not be as thorough um with, you know, paying attention to what the original steps were.
</details>

有时你必须在执行过程中对它们进行类似引导的提示，让它们记起来：“噢，等等，你不是应该用这最后一步来收尾吗，对吧？”

<details><summary>Original English</summary>
And sometimes you have to like kind of prompt them along the way to to remember like, "Oh, wait, you're supposed to you know, finish up with this final step here, right?"
</details>

好的，它没有进行并行处理。所以我们将会看到，GPT-5.5 非常擅长并行工具调用。呃，其他的则没有做到。好的，Mistral 决定只搜索航班和搜索酒店，然后不再做任何其他事情了。嗯，所以[笑声]它直接、它有点直接放弃了。嗯，所以这就是一个例子，说明在这种情况下我们必须进行一些额外的引导，比如问它：“嘿，你确定已经拿到所有东西了吗，对吧？”嗯，你可以使用类似 route loop 之类的方案。呃，Jeff Huntley 今天也在这里，他制作了 route loop。你知道，你可以强制 agent 表现得更加积极，呃，而不是仅仅使用默认循环。

<details><summary>Original English</summary>
Okay, so it did it didn't do parallel. So, what we're going to see is GPT-5.5 is very good at parallel tool calling. Um the other ones not not aren't doing it. Okay, so Mistral decided to only search flights and search hotels and then not do anything else. Um so, [laughter] it did it did it kind of gave up there. Um so, that's an example where, okay, we'd have to do some additional steering there to be like, "Hey, are you sure that you have everything, right?" Um you could use something like the route loop. Uh Jeff Huntley is here today. He made the route loop. And you know, you can you can force uh you know, you can force agents to be more aggressive uh instead of just using the default loop.
</details>

好的。好的，刚才是一个 agent 的例子，我们在其他框架中也有 agent 示例。嗯，但你会看到不同框架之间的代码其实非常相似。呃，我倾向于认为在现阶段，大多数 agent 框架之间的共同点远多于差异。嗯，不过，欢迎大家去查阅它们。

<details><summary>Original English</summary>
All right. Okay, so that uh that was an agent example of saying we also have agent examples in the other frameworks. Um but what you see is the code is really similar across them. Uh I tend to think most agent frameworks are, you know, pre- more similar than they are different at this point. Um but, you know, you're welcome to check them out.
</details>

### 评估与自动化测试

好的。现在我们可以谈谈评估了，对吧？到目前为止，我们做的一切都只是手动运行并观察结果。这对于直观感受你能看到的各种差异是很有帮助的，但当你真正要为生产环境构建内容时，你确实希望能够拥有可以稳定运行并比对结果的批量自动化评估，对吧？

<details><summary>Original English</summary>
All right. So, now we can talk about evaluations, right? So, we've been doing everything just, you know, manually running them and observing the results. That's nice to get a feel for the kind of differences that you can see, but when you're actually going to be, you know, doing something for production, you do want to actually have bulk automated evaluations that you can reliably run and compare results, right?
</details>

因此我们能做的第一步，就是进行评测而无需——你知道的，仅仅使用字符串比较，对吧？嗯，我这里的例子是配合那个创建日历日程的工具调用，因为我们能做的是，鉴于我们实际接收到了返回的参数，我们完全可以直接进行单纯的字符串比较，看它是否返回了“virtual”，对吧？针对这个我们期望得到“virtual”，它返回“virtual”了吗？因此在测试单个工具调用时，你只需要检查它是否调用了正确的工具，以及是否使用了正确的参数。这就是我们在这个评测里要做的事。

<details><summary>Original English</summary>
So, the first step that we can do is just uh doing evals for um without, you know, with just using string comparison, right? Um so, the example I have here is with that create calendar event tool call, cuz what we can do is like we're actually getting back the arguments, we can actually just do a straight string comparison say, "Hey, did it give back virtual, right? We wanted virtual for this, did it give back virtual?" So, when you're testing a single tool call, you can just check to see, did it check did it call call the right tool and did it use the right arguments? So, that's what we're going to do in this one.
</details>

嗯，我们设置了一堆测试用例，对吧？因为在运行评测时，你希望拥有非常多的测试用例。你也希望添加更多测试用例能够变得很轻松，因为一旦你的应用投入生产，你就会看到用户究竟是如何使用它的，然后你会发现：“噢，好吧。多谢，全崩了。”不，然后你就会去把那些新的用户输入用例补充到你的评估中，以确保不会发生漂移，对吧？这被称为模型漂移，或者说你的评测偏离了实际情况。所以你不希望你的评测偏离你的用户输入。一旦上线生产，你就需要一个良好的机制把新的用户输入补充进评测用例中。所以在我们这里，我准备了很多不同的用例。比如这里有一条用户消息，这里是相应的检查项，而这些检查项主要是在进行字符串比较，呃，以及一些列表比较，我们会检查不同的内容，对吧？我们会检查日期计算。

<details><summary>Original English</summary>
Um and we set up a bunch of test cases, right? Cuz when you're running evals, you want to have lots and lots of test cases. You also want it to be easy to add more test cases, cuz once your app is in production, you're going to see how users really use it and you're like, "Oh, okay. Thank you. Everything's broken." No, and then you're going to go and add those new cases of user input to uh your, you know, your evaluations to make sure that you don't drift, right? This is called like model drift or your your your drift away from it. So, you don't want your evals to drift away from your user inputs. So, once they're in production, you want a good system for getting new user inputs into your eval cases. So, here what I do is I've got like lots of different um you know, uh cases here. Like, here's a user message, here's the checks, and these checks are just doing really string comparison, uh some list comparison, and we check different things, right? We check the date math.
</details>

呃，我总是在日期计算方面考查大语言模型，因为它们通常在这个环节表现较差。所以，另一个小建议是，如果你在处理日期，

<details><summary>Original English</summary>
Uh I always check LLMs on date math, cuz usually they're kind of bad at it. So, another tip, if you're doing dates,
</details>

<!-- chunk 5/7 -->

给它们，直接给它们一个做日期计算的工具，好吗？因为在脑子里心算日期太难了。呃，尤其是在闰年的时候。我当时在评估……

<details><summary>Original English</summary>
give them just give them a tool to do date math, okay? Cuz it's too hard to do date math in your head. Uh especially on leap years. I was evaluating
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 在闰年评估大语言模型，那可太难了。呃，然后我们有，嗯……好的，歧义时长。我用西班牙语做了一个，对吧？跨不同语言进行测试挺好的，测试你要支持的任何语言。

<details><summary>Original English</summary>
>> And LLM on a leap year, that was hard. Uh then we had um okay, ambiguous durations. I did one in Spanish, right? It's nice to test across different languages, whatever languages you're going to support.
</details>

>> [嗤笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 呃，这个我觉得写得非常口语化、带俚语。“Yo，你能订一下那个大号会议室吗？”好的。行，所以我们在那里有各种各样的边缘情况，对吧？然后我们来……让我来运行这些评估。

<details><summary>Original English</summary>
>> Uh this one I guess is written written real slangy. Yo, can you book the big conference room? Okay. All right, so we have various edge cases there, right? And then we're let me to run these evals.
</details>

好的，而在这种情况下，这些评估，我打算在各个模型和用例上都运行一遍。现实中很多时候当我跑评估时，我只是在单一模型上运行，然后去比对我可能用了不同模型的先前某次运行。呃，但是你知道，今天呃由于我们正在主动跨模型对比，我打算在所有模型上都运行它，这样我们就能看到……嗯，对它们每一个来说，它都在进行工具调用，检查返回的参数，并决定这是通过还是失败。

<details><summary>Original English</summary>
Okay, and these evals in this case I'm going to run it across each of the models and the use cases. A lot of times in reality when I'm running evals, I'm just running it on a single model and then I'm comparing to like a previous run where maybe I'd done a different model. Uh but you know, for today uh since we are actively comparing across models, I'm going to run it across all the models so we can see um it's for each of them it's doing the tool call, checking the args that come back, and deciding if it's a pass or a fail.
</details>

呃，现在关于评估的一点是，你不希望直接让这些像……直接成为类似你的 pytest、比如你的测试套件的一部分，因为这些很慢，这些开销很大。对，有提问吗？

<details><summary>Original English</summary>
Uh now here's the thing about evals is that you don't want to just have these like just be part of like your pie test, like your test suite because these are slow, these are expensive. Yeah, question?
</details>

>> 嗯，我看到你直接就是，你知道，用字符串比对……呃，你知道是否有任何框架能稍微更优雅地做这件事吗？

<details><summary>Original English</summary>
>> Um I see you just roll, you know, checking strings against Uh do you know if any frameworks do this a bit more elegantly
</details>

>> 你不喜欢我的字符串检查啊。嗯，对，所以在评估框架方面，很多……首先，大多数可观测性供应商都内置了评估，对吧？所以如果你在用 LangFuse、LangSmith、LangChain，嗯，Arize，就像它们都内置了自己的框架。对于 Foundry，我们有……针对它我们有两种不同的框架，呃，而且我实际上确实在仓库里放了示例。嗯……那些里面有 Azure AI evaluation SDK，来自 OpenAI 包的 Open uh AI.evals。所以有很多框架，还有 DeepEval，如果你是 JavaScript 人员的话，还有 JavaScript 中的 Prompt foo。还有哪个？

<details><summary>Original English</summary>
>> You don't like my string checks. Um yeah, so framework-wise for evals a lot of so first of all, most observability providers have evals built in, right? So if you're doing LangFuse, LangSmith, LangChain, um Arize, like they all have their own framework built in. For Foundry, we have um we have two different frameworks uh for it and I actually I do have the examples in the repo. Um um those ones there's Azure AI evaluation SDK, Open uh AI.evals um from the OpenAI package. So there's a bunch of frameworks, there's also DeepEval and Prompt Prompt foo in JavaScript if you're a JavaScript person. And which one?
</details>

>> Vali。

<details><summary>Original English</summary>
>> Vali.
</details>

>> Vali？

<details><summary>Original English</summary>
>> Vali?
</details>

>> 类似那样的东西。

<details><summary>Original English</summary>
>> Something like that.
</details>

>> Mark Vali，好的。

<details><summary>Original English</summary>
>> Mark Vali, okay.
</details>

>> V-A-L-L-Y。

<details><summary>Original English</summary>
>> V A L L Y
</details>

>> V-A-L-L-Y，好的。我是说你用那个。嗯，所以有许多评估框架，嗯，我等会儿要用一个更高级的。但对于字符串检查，不过关键在这儿，像对于字符串检查，你其实不必用高级的……嗯，因为你就像……

<details><summary>Original English</summary>
>> V A L L Y, okay. I mean you use that one. Um so there's a number of eval frameworks um I'll I'm going to use a fancier one soon. But for string check, but here's the thing like like for string check, you don't really have to do a fancy one um because you're like
</details>

>> 如果你是在期待它做某种具体的……

<details><summary>Original English</summary>
>> If you're looking for it to do a specific
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 做你提到的并行化……

<details><summary>Original English</summary>
>> Do the parallelization you mentioned for
</details>

>> 对，对。所以对于工具调用，是的，那正是你会需要稍微更高级一点的地方，对。是的，所以我想先从基础的开始，但是对，大多数时候我们不能光靠基础的敷衍过去，对吧？嗯，噢，它们这次实际上表现得非常好。哇，不错。

<details><summary>Original English</summary>
>> Yeah, yeah. So for tool calls, yeah, that's where you're going to get a bit fancier, yeah. Yeah, so I wanted to start with the basic, but yeah, most of the time we can't get away with just the basic, right? Um oh, they did actually really well this time. Wow, nice.
</details>

### LLM as a Judge

嗯，所以通常我们不得不转向更高级的评估。嗯，所以那就是我们开始引入“大语言模型作为裁判”（LLM as a judge）的时候。呃，这是因为很多时候，你知道，输出要模糊得多，我们需要借助大语言模型来帮我们推敲那种模糊性。有许多框架确实对此进行了封装，嗯，针对这个例子，我直接决定完全在代码里把它写出来，这样你们就能看到。因此当你使用大语言模型作为裁判时的思路，就是你需要给它，你知道，把大语言模型置于裁判模式，然后说：“好的，你是一名评估员。这是你正在评估的内容，并且你必须要么说明它通过，要么说明它失败。”对吧？我们试图迫使大语言模型说出这究竟是通过还是失败。嗯，而且我们还希望它给出理由，对吧？让它给出理由非常、非常有帮助。所以我们要通过、失败以及理由。然后我们给它查询，我们给它响应。为了进行事实锚定，我们还想给它上下文，因为那有助于它实际去推理。所以有时候为了真正做好评估，你确实需要访问更多信息。比如工具调用，如果你想评估它是否对工具调用进行了高效利用，你不能……你必须把所有东西都给它。你必须给它工具调用定义，你必须给它它所做工具调用的链路追踪，对吧？所以要构建非常优秀的评估器，很多时候你不仅仅是在给它输入和输出，你还要把沿途发生的一切、展示的一切全都给它。

<details><summary>Original English</summary>
Um so usually we're going to have to move to fancier evaluation. Um so that's when we start to bring in LLM as a judge. Uh so this is cuz a lot of times, you know, the the output is a lot fuzzier and we need to use an LLM to help us reason about that fuzziness. And there's many frameworks that do wrap this um For this example, I just decided to write it entirely in the in the code so you could see. So the idea when you use an LLM as a judge is that you need to give it, you know, put the LLM in judge mode and say, "Okay, you are an evaluator. This is what you're evaluating and you need to either say does it pass or does it fail?" Right? We're trying to force the LLM to say does this pass or fail? Um and we also want it to give it reason, right? It's really really helpful to have it give it reason. So we want pass, fail, and a reason. And then we give it the query, we give it the response. And for grounding this, we also want to give it the context cuz that helps it actually reason about it. So sometimes in order to really evaluate, you do need access to more information. So like tool calls, if you're trying to evaluate whether it was an efficient user of tool calls, you can't you have to give it everything. You have to give it the tool call definitions. You have to give it the traces of the tool calls it made, right? So to build really good evaluators, a lot of times you're you're not just giving it the input output, you're giving it every everything that happened along the way, everything that was shown.
</details>

呃，所以在这里我们，你知道，我们告诉大语言模型：“嘿，我们要使用 GPT-5 的裁判模型。它是一个相当不错的裁判模型。”然后我们要让它输出一些我们可以查看的 JSON。那么让我直接来运行……呃，这个大语言模型裁判。现在，情况是这样的，嗯，这将会更慢，因为现在每次我们运行评估时，我们既在运行我们自己的代码（它在使用一个模型），然后我们又在使用另一个大语言模型来评判那段代码，对吧？所以每一个单一的评估用例实际上都是两次大语言模型调用。而且很多时候你实际上会运行多个大语言模型来充当裁判。比如你可能会运行大约五个不同的评估器。其中每一个都将是一次独立的大语言模型调用，对吧？嗯，所以这就是评估棘手的地方：你不能总是随随便便运行它们。你不一定能在每一次持续集成（CI）、呃每一次提交上都运行它们，因为它们运行起来相当慢。因为通常在生产环境中，比如对于检索增强生成（RAG），当我评估 RAG 时，你知道，你通常至少需要比如 200 个测试用例，可能是 800 个。而那对于大语言模型来说就是非常多的调用，对吧？所以那需要花费相当多的时间。

<details><summary>Original English</summary>
Uh so here we, you know, we tell the LLM, "Hey, we're going to use the judge model of GPT-5. It's a pretty good judge model." And we're going to ask for it to output some JSON that we can look at. So let me go ahead and run uh this LLM as a judge. Now, here's the thing, um this is going to be even slower because now each time we're running an eval, we're both running our own code, which is using a model, and we're then using another LLM to judge that code, right? So every single eval case is actually two LLM calls. And then many times you actually run multiple LLMs as a judge. Like you'll have like five different evaluators that you're running. Each of those is going to be a separate LLM call, right? Um so that that's what is tricky about evals is that you can't just run them all the time. You can't necessarily run them on every single CI uh and every single commit because they are fairly slow to run. Cuz normally in production, like for rag, when I'm evaluating rag, you know, you usually want like 200 test cases at least, maybe 800. And that's that's like a lot of calls to an LLM, right? So that that takes some amount of time.
</details>

嗯，所以你确实需要思考你将多频繁地，你知道，运行评估。所以你能看到它正在逐一处理其文本……它有了一堆不同的测试用例，不同的问题和答案。并且它正在查看结果。现在，在这种情况下，我做的是我预先运行了，嗯，那些问题和答案。这也是一种常见的做法。比如提前为你，你知道，为评估器获取所有、获取你的上下文，嗯，因为这样你就可以独立于你的应用来修改你的评估器，对吧？嗯，而那样更高效。因为很多时候你意识到的是你的评估器是不正确的，对吧？比如你没有写出一个好的评估器。呃，所以这就是当你做大语言模型当裁判时必须弄清楚的事情，你必须搞明白：等等，问题出在我的应用上，还是问题出在我的裁判上，对吧？并且呃你也希望用人工输入来校准你的裁判。所以，在自己熟悉的领域工作，或者与能够帮助你标注数据并说明情况的领域专家合作，绝对对我有帮助——你知道，他们是否同意你的大语言模型裁判？它到底算通过还是失败？

<details><summary>Original English</summary>
Um so you do want to think about how often you're going to be, you know, running evals. So you can see that it's going through its text it it's got a bunch of different test cases, different questions and answers. And it's it's looking at the results. Now, in this case, what I did was that I like pre-ran the um the questions and answers. This is a common way of doing it, too. Like get, you know, get all your get your context for the evaluator beforehand um because then you can change your evaluator independently from your app, right? Um and that's more efficient. Cuz a lot of times what you realize is that your evaluator is incorrect, right? Like that you haven't written good evaluator. Uh so that's what you have to figure out when you're doing LLM as judge, you have to figure out like wait, is the problem my app or is the problem my judge, right? And uh you also want to calibrate your judges with human input as well. So, it definitely helps me working on a domain you know, or work with a domain expert that can help you label your data and say and you know, do they agree with your LLM as a judge? Was it actually a pass or a fail?
</details>

呃，所以在这里我们拿回了结果，我们可以看到，你知道，模型，嗯，以及它们的分数。嗯，它们大多数拿了比如三分之二。Mr. Owl 拿了三分之一。你知道，所以它们在更具事实依据方面还有一些工作要做。这就是使用大语言模型作为裁判的生成器。如你所见，有相当多的框架呃让它，你知道，内置了大语言模型裁判，让这件事做起来更容易。嗯，但我想要展示的是，你也……你知道，你也可以自己动手做。噢，另外如果你们对评估感兴趣，我应该推荐一下 Hamel.dev。我不知道他这周是否来参会了，但他有着最棒的资源，而且他一直在讲授关于评估的课程。并且他的梗图也特别好。我昨晚其实就用了这些。所以，如果你跟人聊起评估并且需要一张评估梗图……呃，我昨晚在做什么来着？对，构建大语言模型作为裁判，这太难了。

<details><summary>Original English</summary>
Uh so here we get the results back and we can see you know, the model um and their scores um most of them got like two out of three. Mr. Owl got one out of three. You know, so they're they're they have some work to do on being more grounded here. So that is the generator of using LLM as a judge. As you see, there's quite a few frameworks that uh make it, you know, that have built-in LLM as a judge that make it easier to do it. Um but I want to show that you you know, you can't you can't also do it yourself. Oh, also I should recommend if you're interested in evaluation, Hamel.dev. I don't know if he's at the conference this week, but he has the most amazing resources and he teaches courses all the time about evals. And also he's very good memes. I actually used these last night. So, if you're ever chatting with someone about evals and you need an eval meme, uh what was it what I was doing last night? Yeah, building an LLM as a judge it's it's hard.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 呃，所以这是非常重要的资源。我们怎么能信任大语言模型裁判呢？你必须校准你的大语言模型裁判。好的。

<details><summary>Original English</summary>
>> Uh so very important resource here. How can we trust the LLM judge? You have to calibrate your LLM judge. Okay.
</details>

行。那么，那就是大语言模型作为裁判。所以现在，嗯，但是随后正如你们所见，构建裁判评估器确实很难，对吧？比如你不得不去 Twitter 上关注 Hamel，去听他的课，学习所有关于如何编写优秀评估的最佳实践。

<details><summary>Original English</summary>
All right. So, that was LLM as a judge. So now um but then they as you see, it is hard to build judge evaluators, right? Like you have to like follow Hamel on Twitter and take his course and learn all these best practices for how you write uh a good eval.
</details>

### Assert 工具

嗯……呃，所以我们有了这个来自微软研究院的新工具。它非常新，大概就是上周出来的。嗯，它叫 Assert。而 Assert 能帮助你基于规范来编写裁判。所以，你

<details><summary>Original English</summary>
Um uh so we have this new tool from Microsoft Research. It's very new, like the last week. Um it's called Assert. And Assert helps you write the judges based off of the spec. So, you
</details>

<!-- chunk 6/7 -->

### 基于规范生成测试集与评测：assert-eval

编写一份规范（spec）。你说：“嘿，这是我正在构建的 Agent，这大概就是我想让它做的事、关于它该如何运作的想法，以及它应该支持什么样的用户。”然后它就会生成大量的测试用例。它会把你给出的规范充实为具体的评判标准（judging rubrics），并且基于——你知道，这一切都非常基于学术研究——为你把这一切都梳理出来，对吧？所以，我们在这里已经为旅行规划助手（travel planner）做过了。

<details><summary>Original English</summary>
write a spec. You say, "Hey, this is the agent I'm building and this is, you know, roughly what I want it to be doing, my idea about how it should work, and um what kind of users it should support." And then it will generate lots of test cases. It'll like flesh out your your spec into um into actual judging rubrics, and figure all of that out for you based off of, you know, all the the it's very based in in research, right? So, we've done that for the travel planner already in here.
</details>

嗯，所以这里是……在 assert eval 这个目录下。好的。

<details><summary>Original English</summary>
Um so, here's the um so, it's under this assert eval. Okay.
</details>

我们可以看到的是，我们写了一个 YAML 文件，因为我们都希望生命中出现更多的 YAML。关于 YAML 我意识到的是，我也许讨厌 YAML，但就我的需求而言，它又比其他任何东西都好用。所以，就是这样。

<details><summary>Original English</summary>
So, what we can see is that we write a YAML file cuz we all wanted more YAML in our life. What I realized about YAML is that I might hate YAML, but it's also better than everything else for what I need it for. So, there we go.
</details>

在这个 YAML 里，我们描述了上下文，并且描述说：“好的，我们将使用这个裁判模型（judge model）。我们关心的维度大概是预算，也就是预算压力。”所以如果了解的话，我们可以给它更多信息，比如：“哦，我们关心充裕预算、紧张预算、看不见的预算。”

<details><summary>Original English</summary>
Um so, in this YAML, you know, we describe uh the context, and we describe, "Okay, we're going to use this judge model. Um these are the kind of dimensions we care about is budget, you know, budget pressure." So, we can we can give it more information if we know, like, "Oh, we care about ample budget, tight budget, invisible."
</details>

你可以对它进行分层。这被称为分层（stratification）。如果你愿意，你可以预先分层，或者你也可以就让它自己提出分层方案。

<details><summary>Original English</summary>
Um you know, so, you can you can stratify it. This is called stratification. You can you can pre-stratify if you want, uh or you can just have it come up with the stratification.
</details>

然后我们这里还有更多的维度。而且还有一个 Agent Skill 可以帮你编写这个 YAML 文件，这样你就不必自己动手写了，因为没人想写这玩意儿，对吧？然后我们有实际执行评测的对象。这就是我们之前看过的 LangChain 旅行规划助手。这只是确保它追踪了一切，因为正如它所说：“在做评测时，你确实希望看到每一次工具调用，这样你才能真正妥善地完成这些评测。”

<details><summary>Original English</summary>
Uh and then we have more dimensions here. And there's this there's also a a skill an agent skill that helps you write this YAML file so that you don't have to write it yourself cuz no one wants to write it, right? Um and then we have the actual thing that's evaluating. This is the LangChain travel planner that we saw before. Uh so, this just makes sure that it's tracing everything cuz it's saying, "When you are doing evaluations, you do want to see every single tool call so that you can really properly do these evaluations."
</details>

好的。然后它把这一切全部运行起来，接着我们就可以看到结果了。它确实需要花费相当多的时间，所以我们已经把这些评测预先放在这里了。

<details><summary>Original English</summary>
All right. So, then it it runs it all, and then we can see the results. It does take a, you know, a decent amount of time. So, we've already got the um evals in here.
</details>

我已经让它们运行好了。这里有一个小前端可以用来查看它们。好的。

<details><summary>Original English</summary>
Uh so, I've got them running. Uh there's like a little like front end that you can use to view them. Okay.
</details>

好的。这就是这个 assert evaluation 的结果。

<details><summary>Original English</summary>
All right. So, here is the result of this um a search evaluation.
</details>

基本上，它总结出了不同的行为类别，对吧？比如预算不可行性、直飞偏好规则违规、必需的工具使用，对吧？所以它总结出了哪些行为是允许的，但哪些是不被允许的。

<details><summary>Original English</summary>
Um so, basically it you know, it came up with the different behavior categories, right? So, making like budget in infeasibility, direct flight preference rule violation, required tool use, right? So, uh it comes up with what behaviors are you know, allowed but not allowed.
</details>

然后它生成了测试集。这个测试集真的挺好玩的。

<details><summary>Original English</summary>
And then it comes up with the test set. The test set is really is pretty fun.
</details>

来了。场景 65：“Red eye before the installer walked through the coach with six parent text one weekend to see Alma.”我非常喜欢这些明显是由大语言模型生成的标题，对吧？所以它生成了所有这些“带写字夹板的长途客车”（coach with a clipboard）之类的。它基于那个 YAML 生成了所有这些场景来尝试模拟用户，对吧？因为整件事就是，在进入生产环境之前，你很难冷启动你的评测，但你又想在进入生产环境之前就具备评测能力，对吧？那么，你怎么弄清楚你的测试集会是什么呢？所以这个 assert 框架在构建测试集和冷启动评测方面提供了很大的帮助。

<details><summary>Original English</summary>
Um and here we go. Scenario 65. Red eye before the installer walked through the coach with six parent text one weekend to see Alma. I really like that these are obviously LLM generated titles, right? So, it came up with all of these coach with a clipboard. Um it can it comes up with all these scenarios based off that that YAML to try and simulate users, right? Cuz the whole thing it's really hard to bootstrap your evaluation before you go into production, but you want to have evals before you go into production, right? So, how do you figure out, you know, what your test set is going to be? And so, this assert framework helps a lot with making that test set and bootstrapping your evals.
</details>

它包含了提示词和场景。然后我们得到了结果。好的。在结果方面，它在 DeepSeek、Kimi 和 GPT-4.5（GBD 5.5）上运行了一遍，然后给出了这里的数值。在这种情况下，数值越低越好。我们可以看到 GPT-4.5 比其他的要好得多。我其实很惊讶，因为 Kimi——我们今天看到 Kimi 普遍表现都挺不错，我原本以为它差不多不相上下，但至少对于这个场景来说，GPT-4.5 的违规次数是最少的，所以它在这里得分最高。

<details><summary>Original English</summary>
Uh so, it has prompts and scenarios. And then we have the results. Okay. So, for the results, it ran it um across Deep Sea, Kimmy, and GBD 5.5 and uh came up with the you know, with the numbers here. Um and in this case the the lower numbers are better. And so, we can see that uh GBD 5.5 did way better than the other ones. I was actually surprised cuz Kimmy, we've seen that Kimmy has generally been quite good today um and I was thinking it was kind of on par, but at least for this scenario, uh GBD 5.5 had the lowest number of violations, and so it is it's scoring the best here.
</details>

所以是的，这就是 assert。我想说，我对 assert 完全是个新手，因为它大概一周前才刚发布。

<details><summary>Original English</summary>
Um so So yeah. So this is assert. I will say I'm I'm brand new to assert since it only came out like a week ago.
</details>

到目前为止我只用过这么多，但这里的核心思想是，它能帮助你构建那些评测器，构建那个测试集，遵循最佳实践并冷启动你的评测，从而让你一开始就能拥有一些非常不错的评测。因为我们看到的是，我们不断地告诉大家“你们必须运行评测，你们必须运行评测”，结果要么没人跑评测，要么跑的都是连贯性（coherence）和流畅度（fluency）这种默认评测。千万别跑那些。大语言模型非常擅长保持连贯。你根本不需要去检查大语言模型是否连贯；如果它们不连贯，那肯定是出了非常严重的问题。我有时的确会针对我的 RAG 场景使用真实性（groundedness）和相关性（relevance）评测器，但大多数时候内置的评测器并不是你想要的。你想要的是构建自定义评测器。而这正是它帮助你做的事情，那就是：好的，你需要自定义评测器来切实看清你的 Agent 是否做得很棒；但你知道，在冷启动这些自定义评测器时，你需要一些帮助。

<details><summary>Original English</summary>
Um so this is all I've I've used it so far, but the idea here is that it's helping you to build those evaluators to build that test set and to follow the best practices and bootstrap your evals so that you can start start off um you know, with with some really good evals. Cuz what we're seeing is that we keep telling people like you got to run evals, you got to run evals, and then no one's running evals or they're running like the default evals like coherence and fluency. Never run those. Like LLMs are great at being coherent. You never have to check if an LLM is coherent. If some if they're not, like something really bad has happened. Um I do sometimes use the groundness and relevance evaluators for my rag things, but most of the times the built-in evaluators are not what you want. You want to build custom evaluators. And that's what this is helping you with is like okay, you need custom evaluators to really see if your agent is doing a good job. Uh but you know, you need some help bootstrapping those custom evaluators.
</details>

### 用 DSPy 自动优化提示词

好的。噢，我们还剩 3 分钟了。我一直在喋喋不休。好的，最后，前面我们讨论过提示词工程，比如“好的，我们要怎么微调这个提示词，才能让它在这些模型上表现更好？”这其实挺折磨人的，对吧？如果你每切换一次模型都必须微调一次提示词，然后重新跑评测，那工作量相当大。

<details><summary>Original English</summary>
All right. Oh, we have 3 minutes left. I've been blabbing. Okay, finally, um you know, earlier we were talking about prompt engineering like okay, how can we tweak this prompt in order to work better for these models? That's pretty painful, right? If you have to tweak the prompt every time you switch models and like rerun evals, that's like a lot of work.
</details>

噢，这里有个小计时器。谢谢。好的。

<details><summary>Original English</summary>
Oh, there's a little timer. Thank you. Okay.
</details>

是的，如果你每次都必须微调模型，那工作量很大，而且你不知道该往哪个方向去微调模型，对吧？你不可能知道每一个模型的细节，以及究竟什么才能真正对它奏效。因此，我作为最后一个示例补充进来的就是使用 DSPy。在座有人用过 DSPy 吗？

<details><summary>Original English</summary>
Uh so if you Yeah, if you have to tweak the model every time, uh that's a lot of work and you don't know which way to tweak tweak the model, right? You don't know the details of every single model, what's going to really work well for it. So uh what I've added is this as a final example is using Dspy. Has anyone used Dspy here?
</details>

太棒了，有几个人用过。关于 DSPy，它的理念是你声明自己的程序。比如你说：“嘿，我正在写这样一个程序，它预期接收用户输入，然后将其转化为结构化的对应部分。”所以，你声明了程序的约束条件，然后由 DSPy 来找出符合这些约束条件的提示词。因此，提示词将由 DSPy 来编写。所以，你基本上是提交了你的规范，然后让 DSPy 通过执行评测并观察“嘿，什么样的提示词能满足这些约束条件”，来把提示词写出来。而且它实际上使用了一种叫做 GEPA（genetic Pareto algorithms，遗传帕累托算法）的很酷的算法。它能够利用这些遗传算法来得出下一个最值得尝试的最佳提示词，看着它执行这个过程真的非常非常酷。所以，这就是 DSPy 的理念。

<details><summary>Original English</summary>
Cool, a couple people. So Dspy, the idea of Dspy is that you declare your program like you say, "Hey, I'm making this program that's expecting to take user input and then turning it into a structured counter bit." So, you declare the constraints of your program and then Dspy is going to figure out the prompt that adheres to those constraints. So, Dspy is going to write your prompt. So, you you're basically checking your spec in and then having Dspy by write the prompts based off of doing evaluations and seeing, "Hey, what prompt is going to satisfy those constraints?" And it actually uses these this cool algorithm called Jeppa, genetic credo algorithms. It can use these genetic algorithms in order to come up with the next best prompt to try, which is really really cool to watch it do that. Um so, that's the idea of Dspy.
</details>

所以基本上我们必须设置……这非常不一样，对吧？你不能直接拿来标准的现有代码直接用。你有点得重写整套代码，因为现在，提示词不再是放在你的代码里，而是约束条件放在了代码里。你的规范就是你的代码。提示词是这个 DSPy 流程的输出产物，对吧？

<details><summary>Original English</summary>
And so, basically we have to set So, it's very different, right? You can't just take your standard code and just use it. You kind of have to rewrite your whole code cuz now, instead of checking your pro- like your prompt isn't in your code, your constraints are in your code. Your spec is your code. The prompt is an output from this Dspy process, right?
</details>

所以在这里，我要求它生成一个带编号的列表，其中每行的字数都精确受控，并且每行的第一个字母拼出一个目标单词。这就是输入的类型，然后我们有一组约束条件来检查结果是否正确，对吧？所以你需要设置好你的规范，然后设置好诸如检查项和测试，去看看“嘿，输出是否满足了这个约束条件？”这样一来，DSPy 就可以不断迭代、爬山（hill climbing），对吧？基本上就是爬山搜索，直到它找到满足那些约束条件的提示词，对吧？所以你给它学生模型（student model）、反思模型（reflection model），然后它运行这个 GEPA 优化器——你知道，去尝试找出最佳的提示词，接着我们就拿回了结果。这个结果我已经保存在这里了，所以我们能看到它。它确实需要耗费相当多的时间。在这项任务上大概花了 6 分钟。但在这里，这个结果就是实际生成的指令。让我给它加上自动换行。

<details><summary>Original English</summary>
So, here I'm doing I'm asking it to generate a numbered list where each line has exact word count and the first letter of the line spell out a target word. So, this is the kind of input and then we have a bunch of constraints that are checking to see is the result correct, right? So, you need to set up your spec and then set up like checks, tests to see, "Hey, does the output satisfy this constraint?" And that way Dspy can keep iterating, hill climbing, right? Basically hill climbing until it finds a prompt that satisfies those constraints, right? So, you give it the student model, the reflection model, uh then it runs this Jeppa uh optimizer, which you know, tries to find the best um prompt, and then we get back the result. So, the result I have it stored here so we can see it. It does take a fair amount of time. It took like 6 minutes on this task. Um but here, this result is the actual instructions. So, let me add word wrap into there.
</details>

好的。这就是它基于那些约束条件和那些检查项所构思出来的系统提示词，对吧？这样非常好，因为这是一个适用于 Mistral 的系统提示词。我之所以挑了 Mistral，是因为它是我们之前应付起来最吃力的一个，对吧？因此，特别是使用较小的模型时，这意味着我们可以使用成本最低的模型

<details><summary>Original English</summary>
Right. So, this is the system prompt that it came up with based off of those constraints and those you know those checks, right? And so this is nice because this is a system prompt that works with Mistral. Cuz I I picked Mistral cuz that was the one we were having the hardest time with, right? So especially with using smaller models, this means we can use the cheapest model
</details>

<!-- chunk 7/7 -->

并且仍然获得我们需要的结果，对吧？像 Dropbox、Shopify 就做过一些很棒的演讲，谈到他们是如何利用 DSPy 加上 GEPPA，以便摆脱那些更大的模型，转而使用较小的模型，甚至可能将其部署在他们自己的基础设施上，同时取得相同的结果。但关键在于尝试，你知道，用这种方式找出那个最优的提示词（prompt）。
<details><summary>Original English</summary>
and still get the results we need, right? So there's been some great talks by like Dropbox, Shopify about how they've used DSPy plus Jeppa so that they can move off the larger models and use the smaller models and maybe even deploy it on their infrastructure and get the same results. But the key was trying to you know using this order to figure out what that optimal prompt is.
</details>

所以这绝对是一种编写应用程序的不同方式。让提示词成为这个过程的产出，感觉可能会有点不同，你知道，但这同样也是一种潜在的非常强大的编写方式，能给你带来更多的模型独立性，以及能够使用更多这些模型的更大灵活性。
<details><summary>Original English</summary>
So this is a definitely a different way of writing your apps and it can feel a little different to you know to have the prompt be the output of this process, but it's also potentially really powerful way of writing it and can give you a lot more model independence and more flexibility to be able to use more of these models.
</details>

所以我想，是的，确保大家也知道有这样一个选项。
<details><summary>Original English</summary>
So I wanted to yeah, make sure that people knew about that as an option as well.
</details>

好的。
<details><summary>Original English</summary>
Okay.
</details>

### 模型差异与 Anthropic 的引用功能

好了。所以，是的，这就是我想要展示的全部内容了。正如大家所见，模型之间存在很多差异，你有很多种不同的方法来改善模型输出，然后进行评估，接着再进行改进。
<details><summary>Original English</summary>
All right. So So yeah, so that was all the things that I wanted to show. As you can see there's lots of differences between models, different ways you can improve the model output and then evaluate it and then improve it.
</details>

我确实很鼓励大家，是的，就尽管去摆弄这些模型吧。每当我，你知道，尝试不同的模型……嗯，并看看它们有多大不同时，我总是能学到很多东西。噢，我一直没展示 Anthropic。我本来打算展示 Anthropic 的。好的，我其实也部署了一些 Anthropic 的模型。使用 Anthropic 的话，你确实必须使用不同的 API。这就是为什么我大部分时间都没用 Anthropic 的原因。
<details><summary>Original English</summary>
I do encourage you like yeah, just just tinker with the models. It's I always learn so much whenever I you know try out different models um and see how different they are. Oh, I never showed Anthropic. I meant to show Anthropic. Okay. I do have some Anthropic's deployed as well. With Anthropic you do have to use a different API. That's why I wasn't using Anthropic most of the time.
</details>

但大家当然可能对 Anthropic 感兴趣。他们使用的是 Messages API，所以你确实得调整一下你的代码。不过在做 RAG 时，我实际上特别喜欢它，因为这里很有意思的一点是，Anthropic 他们其实在模型里内置了引文（citations）的概念。所以，你实际上可以……你用这种结构化格式来提供源材料。你说：“嘿，这是我的源材料。它是一篇文档。它是文本。这是它的文本内容。”然后你启用引文功能。接着 Anthropic 的模型实际上经过了训练，可以返回带有引文的文本块。这样你就能以编程式的方式将它们提取出来，当你构建前端界面时这真的非常好用，你直接把引文链接上就行。
<details><summary>Original English</summary>
But of course you might be interested in Anthropic. They They use the messages API instead, so you do have to switch your code around. But I actually specifically like it for rag because here's interesting is that with Anthropic they actually have this notion of citations built into the models. So, you can actually you provide the sources in this structured format. So, you say, "Hey, this is my source. It's a document. It's text. Here's the text of it." And then you enable citations. And then the Anthropic models are actually trained to return back blocks of text with citation. So, you can extract those in a programmatic way, which is really nice when you're like building front ends. You can just link your citations.
</details>

所以那真的很酷。所以那甚至又是另一件可以关注的事情，就是你知道，完全不同的调用模型的方法。
<details><summary>Original English</summary>
So, that's really cool. So, that's even another thing to look at is you know, a whole different ways of calling models, too.
</details>

### 总结与结尾

好的。行。
<details><summary>Original English</summary>
Okay. All right.
</details>

是的，我们的时间差不多到了。代码仓库（repo）会一直保留，所以欢迎大家继续在该仓库上操作。我确实需要轮换掉我放在那个 `.env` 里的密钥，因为我的意思是，我相信大家，但我不知道有多相信大家。而且 Cedric 已经说我这样做很糟糕了。
<details><summary>Original English</summary>
And yeah, we're kind of at time here. The the repo will stay up. So, you're welcome to keep working on the repo. I do need to rotate the keys that I put in that .env because I mean, I trust you, but I don't know how much I trust you. And Cedric always already said I was bad for doing that.
</details>

所以我没法把那些密钥保留太久了。
<details><summary>Original English</summary>
So, I I won't be able to keep those keys up for much longer.
</details>

不过，希望通过这个仓库大家可以去尝试一下。你也可以用 Llama 去试。我昨天添加了 Llama 支持。所以，如果你想，你知道，你也想试一下 Llama 吗？如果你在本地运行模型，你基本上只需修改示例使其指向本地的 Llama 服务器即可。而且你也只需要把模型名称改一下，对吧？但大体上它们配合 Llama 也都应该能正常运行，因为它们使用的是相同的 API。
<details><summary>Original English</summary>
But, hopefully with the repo you can try it out. You can also try it out with a llama. I added a llama support yesterday. So, if you want you know, do you want to try a llama, too? If you're doing local models, you basically just change the examples to point at the local llama server. And you just have to change the model names as well, right? But, generally they should all work with a llama as well because it's same API.
</details>

好的。谢谢大家。噢，那里还有贴纸。
<details><summary>Original English</summary>
All right. Thank you, everyone. Oh, and there's stickers.
</details>

>> [掌声]
<details><summary>Original English</summary>
>> [applause]
</details>