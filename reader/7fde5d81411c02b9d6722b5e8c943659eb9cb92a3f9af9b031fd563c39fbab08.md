---
author: AI Engineer
date: '2026-06-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mFLlVpnGpds
speaker: AI Engineer
tags:
  - speaker-diarization
  - speech-recognition
  - speech-processing
  - multimodal-ai
title: pyannote关于对话理解与说话人归属转写的技术演讲
summary: pyannote联合创始人介绍了从基础语音转录走向对话理解的关键演进，重点探讨了说话人日志、副语言信息与时间戳对齐的价值，并演示了处理重叠语音的说话人归属转写及其实际评估挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - pyannote
  - OpenAI
  - Nvidia
products_models:
  - pyannote
  - Whisper
  - Parakeet
media_books: []
status: evergreen
---
<!-- chunk 1/3 -->

### 开场与背景介绍

大家早上好。感谢各位来到语音与视觉专场。我是 Banan，pyannote 的首席科学官兼联合创始人。今天我要和大家聊一聊对话理解，以及在转录之上还能做些什么。

<details><summary>Original English</summary>
Good morning everyone. Thanks for being here to the voice and vision session. Uh so I'm Banan, chief science officer and co-founder at pianoi. Uh so I'm going to talk to you uh today about um conversations understanding conversations and uh uh what you can do on top of uh transcription.
</details>

先简单介绍一下我自己。在两年前创办这家公司之前，我一直是一名全职学术研究员。哎呀抱歉，刚才怎么了？好的。总的来说，我一直从事“说话人日志”（speaker diarization）这个课题的研究。稍后我会为还不了解这个奇怪词汇的人稍作介绍，这个词对我来说发音也挺棘手的。但大体上，这些年来我开发了一个专注于说话人日志的开源工具包，名叫 pyannote。

<details><summary>Original English</summary>
Uh so a quick words about myself. So I've been an academic researcher all my life until two years ago when I started this company. Uh oops sorry. Uh what happened? Yeah. Uh so basically yeah I worked on this topic called speaker derization which I'll uh introduce a bit later for those of you who don't know this weird uh word that is tricky for me to pronounce uh but basically over the years I built an open source toolkit called pianut uh which focuses on speakerization
</details>

多年来它变得相当受欢迎，尤其是在 OpenAI 发布了 Whisper 开源语音转文本模型之后。可以说 Whisper 在语音转文本（STT）领域掀起了一场革命：它完全免费且效果极佳。但它并不提供说话人的具体姓名和标签，所以人们自然而然地转向 pyannote，将两者结合使用。

<details><summary>Original English</summary>
and that became quite popular over the years in particular since uh openai released whisper speechtoext open source models basically whisper was some kind of revolution in terms of ST uh the fact that it was free that it was very good and but it didn't provided the actual uh didn't provide the actual names and tags of the speaker so people naturally turned to pianut to combine the two
</details>

你可以从 GitHub star 历史的拐点上看出来。另外提一句，刚好再过一周我就满 45 岁了，我们在 GitHub 上的标星也快达到 1 万颗了。所以请大家送我一份生日礼物，直接去 GitHub 网站给项目点个星，这能让我过一个开心的生日。

<details><summary>Original English</summary>
and you can see that on the uh inflection points on the GitHub star history and uh just a few words I happen to turn 45 uh in just one week from now and we are almost at 10k uh stars on GitHub so please uh give give me a birthday gift by just going to the website and to the GitHub website and add your star. That will make my uh birthday. Um
</details>

### 从语音转录到说话人归属

那么，让我们进入演讲的核心内容。大家都知道什么是转录或语音转文本。本质上就是根据一段对话的录音或流式音频，回答“说了什么”这个问题。基本上就是输入音频，输出一个词语序列。例如 Whisper 做的就是这个。但是，如果没有说话人的具体名字，通常很难看懂转录文本里的对话。因此，转录之后的下一步，基本上就是为每一个词赋予一个说话人标签。这就是我在这里所说的“带说话人归属的转录”。

<details><summary>Original English</summary>
so um let's go to the to the core of the presentation. So you all know what transcription or a speech to text is. Basically that's answering the question what was said from the recording or a streaming of a a conversation. Basically you get from the audio and you get a sequence of words uh uh as output. Uh that's for instance what whispered as uh but uh without the actual uh names of the speaker the usually the conversations on the transcript are not really understandable. So the next step after transcription is basically to attribute uh a speaker tag to each uh of the words. So that's I called here a speaker attributed transcription.
</details>

它回答了“谁说了什么”的问题。对于某些应用来说，这已经足够了。比如对于会议记录工具来说，要生成一份会议总结，知道某句话是谁说的、另一句话是约翰说的，以便把待办事项分配给对应的人，可能就够用了。但要更深入地理解对话，我们可能希望做得更进一步。

<details><summary>Original English</summary>
And so that that answer the question who said what. But for some application that's enough like for instance uh for maybe for meeting note takers to make a summary of a of of a meeting that might be enough to assign an action point to the right people to to know exactly that air said that and John said said this this other thing but we to understand the conversation uh a bit better uh we we might want uh to go slightly uh better.
</details>

抱歉，我忘了这张幻灯片。实际上在很多场景下，知道“谁说了什么”和“说了什么”同样重要。我这里列举了几个例子：比如视频配音，在自动视频配音中，知道谁说了什么其实非常关键，这样才能把正确的声音匹配给正确的说话人。如果你想把一段视频自动翻译成另一种语言，你也希望不同声音之间保持一致。为此，你必须知道谁在什么时候说了话。会议记录工具也是同理。还有其他应用，比如我所谓的“播客智能”——能够在不同的播客单集或不同节目之间追踪同一位说话人，在多档播客中找到同一位嘉宾。

<details><summary>Original English</summary>
Uh sorry I forgot about this slide. So basically uh there are many cases where um knowing who said what is as important as what was said actually. So I have here a few examples like for instance uh video dubbing automatic video dubbing um uh knowing who said what is actually really important to put the actual uh uh good correct voice to the right speaker. So if you want to automatically translate uh um a video from one language to another, you want the voices to be consistent as well. So for that you need uh to know who's uh who who spoke when. Same for medic note takers. And there are other applications like for instance podcast what I call podcast intelligence like being able to track a speaker across different uh episodes of a podcast or across different podcasts finding uh the same guest across multiple podcast.
</details>

### 时间戳与副语言信息

不过正如我刚才提到的，仅仅知道谁说了什么，有时并不足以真正理解对话是如何推进的。实际上，知道“谁在什么时候说了什么”能带来更多信息。比如在这个例子中，如果不确切知道每个词的发音时间，你就无法察觉黑方说话人其实打断了绿方说话人。

<details><summary>Original English</summary>
But yeah, so I was a bit over just before, but the just knowing who said what is sometimes not enough to really understand the conversation the conversation how it goes. So knowing who said what and when actually uh brings even more information. For instance, in this example u uh without knowing exactly when each words were pronounced, you can't detect that actually the black speaker interrupted uh the green one.
</details>

你也无法真正察觉到，黑方说话人在绿方说话人讲话期间所发出的简短附和反馈。如果忽略了这一点，你基本上就无法真正理解黑方说话人可能是在表示赞同、在对绿方说话人所讲的内容点头。因此，确切知道这个简短词汇是在何时说出的，非常重要。

<details><summary>Original English</summary>
you can't really detect that uh maybe this small back channel that the the the green the sorry the black speaker um does during the speech of the of the green speaker if you miss it basically you you don't really understand that maybe the black speaker is actually agreeing nodding uh at what the the green speaker says so knowing exactly when this small word has been pronounced uh is very important
</details>

同样，如果没有精确的时间戳，你就无法确切知道我是否在两轮发言之间进行了停顿，而停顿可能会传达出关于我的心境、或者我在对话中试图表达的观点的额外信息。

<details><summary>Original English</summary>
and same without precise time stamps you can't really know whether I made a I make a pose in between two speech terms which might convey additional information about my state of mind, my I don't know the the the point that I'm trying to to make in the conversation.
</details>

我们还可以更进一步：我们可能想知道谁在什么时候说了什么，以及他们是“如何”说的。我这里列举了几个例子：如果你们有人在某个时刻笑了，是因为我说了什么蠢话，还是因为我确实很幽默？咳嗽也是同理。也许是对话中的某些内容让我感到不适，而我出于某种原因通过咳嗽来加以掩饰。

<details><summary>Original English</summary>
And we can go even a step further like we we might want to know who said what and when and how they said it. Like I have a few examples here. If uh some of you are laughing at some point, is it because I don't know I said something stupid or I was actually funny? Uh same for coughing. Uh maybe there's something in the conversation that makes me uh uncomfortable and uh I'm coughing for some reason to to hide be behind that.
</details>

是的，我还提到了重音、不流畅现象和韵律。一句话中我对特定词语施加重音，可能会完全改变句子的含义。我想到了这样一个例子：比如句子“狗吃了蛋糕”。如果你在和小孩说话，小孩告诉你“狗吃了蛋糕”、“狗吃了蛋糕”或“狗吃了蛋糕”，含义可能会略有不同。因此，强调特定的词语、让语音 AI 能够真正理解这种重音以及这类底层细节，可能会为你在完成这第一步富文本转录之后所使用的下游 LLM 或任何工具带来更多信息。

<details><summary>Original English</summary>
And um yeah, so I also mentioned stress, disfluency, proity. Um the fact that I stress on particular words in a sentence might actually change completely the meaning of the sentence. Uh I have this example in mind like uh I don't know in the sentence the dog uh ate uh the cake. If uh I don't know you're talking to a child and the child tells you the dog ate the cake or the dog ate the cake or the dog ate the cake the meaning might be slightly different. So stressing particular words, being able to have a a voice AI actually understand this stress and and this kind of of low-level details might bring some more uh information to the to any downstream LLM or or whatever tools that you use after this first uh enrich transcription step.
</details>

### 上下文与声学环境

如果我们再退一步看，了解谁在对谁说话：在这个例子中，我大概可以被看作是这个正在对大家所有人讲话的灰色说话人；但在某个时刻，如果演讲结束时你们有问题，那我可能就是那个正在对某一个人说话、回答特定问题的绿色说话人。所以了解这一点、对对话拥有更高层级的全貌认知，也会开启大量全新的应用。

<details><summary>Original English</summary>
And if we take even a step a step back uh um knowing who's uh talking to who uh am I uh here in this example I'm probably can be seen as this gray speaker addressing to all of you but at some point if at the end of this talk I you do have questions then I will be probably the the green one talking to one particular person answering the particular question. So knowing that having a higher level view of the conversation he also opens up a new bunch of um applications
</details>

而且这一切都发生在特定的声学环境中，它会为你提供关于上下文的信息——无论目前是在这个安静的房间里，还是在嘈杂的街头，这都为整个场景带来了更多语境，让你能对正在发生的事情做出更准确的判断，明白一个人为什么会说出他们所说的那些话等等。以上所有这些，基本上就是我们在 pyannote 努力攻关的方向。但我们最初是从一个较小的问题切入的，那就是说话人日志，这正是今天我想重点探讨的内容。

<details><summary>Original English</summary>
and all of this also happens in a acoustic environment that gives you information about the context whether it's in this quiet room uh for now uh or if I'm in the street u this bring more context to to to the game and you can actually uh take a better decision ision about what's going on, why a person is actually saying what what they're saying and and etc. So all of this is basically the what we are trying to work on at the piano. But we uh started with a smaller problem called speaker dorization and that's really what I want to talk about today.
</details>

### 说话人日志的概念与步骤

关于这张幻灯片，我原本想说的其实是：知道“谁说了什么”通常和“说了什么”同样重要。大家可以看看 Hugging Face 模型库，筛选出其中带有音频标签的所有模型。我当时就是这么做的，然后按下载量进行排序。基本上在排名前七的模型中，排名前三的模型实际上都与说话人身份识别和说话人日志相关，剩下的则是语音转文本模型。这也从一个侧面证明了说话人日志在社区中确实相当重要。

<details><summary>Original English</summary>
So speaker derization is the I I yeah is is usually what what I wanted to say about this slide is that who said what is usually just as important as what was said and you can tell by instance by going through to the face uh model repository and filter um all the models there uh with the ones that have the audio tag uh where is maras here. So this is what I did and then you saw them by uh by number of downloads and basically uh the among the the top uh here seven models that uh are at the top of this list. Three of them the the first three are actually related to speaker identity and speakerization and the the other ones are ST. So that's one way of showing that speakerization is actually quite quite important on on in the community.
</details>

接下来深入讲讲什么是说话人日志。正如我之前所说，它回答的是“谁在何时说话”的问题。从一段对话的录音开始，人们通常做的第一步是基础的语音活动检测（VAD），基本上就是判断某个时刻是否有人在说话，是否有任何人在某个时间点发言。然后你可以更进一步，将那些语音区域切分成更小的语音轮次。

<details><summary>Original English</summary>
So uh going uh into a bit more detail about what speakerization is. So as I said it's answering the question who speaks when. So starting from the recording of a conversation. Uh basically the first step that people usually do is basic voice activity detection. So you basically tell whether someone is speaking at at one time or not. Anyone is speaking at at one time or not. And then you can go a step further. uh you can actually segment those speech regions into smaller speech turns.
</details>

这就是我所谓的“切分”，它包括在那些长语音区域中找出说话人的更替点——在那些长语音片段中，你可能会发现说话人转换点；同时还要找出人们实际发生互相打断的区域，比如在第一个例子中，显然存在……

<details><summary>Original English</summary>
Um so this is what I call segmentation and it includes finding uh speaker change points between uh into those long uh in those long speech regions you might find you know a speaker change point and uh also find regions where people are actually interrupting each other like in in the first example here there's definitely
</details>

<!-- chunk 2/3 -->

这里有人在打断其他人，而且这里可能也是某种反馈通道（backchannel），比如有人在点头，或者说“嗯”、“好的”之类的。这类简短的话轮（speech turn）是你不想错过的，因为有时它们实际上承载着整场对话中最关键的信息。如果这里有一声轻微的“对”，而你漏掉了，那么你完全无法了解这位说话者的心理状态。但那还算不上说话人分离（speakerization/diarization）；说话人分离要一直做到真正为每一个话轮分配说话人身份。

<details><summary>Original English</summary>
here someone interrupting someone else and it's possibly here some kind of back channel where someone is actually uh nodding or sayinghm okay this kind of stuff and this is the kind of small speech turn that uh you don't want to miss because sometimes they actually convey uh the most important information of the conversation if it's a small yes here uh and if you miss it uh then uh you you have no idea what's the the state of mind of this speaker but that's not yet speakerization speakerization goes all the way to actually assigning a speaker identity to uh each uh speech turn.
</details>

在这个例子中，说话人分离系统自动检测出了有两位说话人，绿色那个和黑色那个。但通常我们对对话中实际的说话人数量没有任何先验知识。你可能会有一些指引，比如假设你是一名会议记录员，手头有参会者名单，因此你可能对受邀人数有个概念；但这并不意味着两个人不会从同一个通道加入，或者未受邀的参会者最终不会参会。这就使得这个问题变得相当困难，因为与其它经典的机器学习问题相反，我们事先并不知道应该检测多少个类别；而且我们也不知道应该分离出的说话人的身份，因为说话人分离并不会真正输出“约翰”或者“杰克”，基本上它更像是“说话人一”、“说话人二”、“说话人三”。它们是可以置换的，并且结果依然正确。例如在这个例子中，如果我只是把绿色换成黑色，黑色换成绿色，从我稍后要讲的评估指标的角度来看，以及从实际的说话人分离任务来看，分离结果依然完全一样。

<details><summary>Original English</summary>
And um so here in this example, the the speakerization system automatically detected that there are two speakers, the green one and the black one. Um but uh we usually don't have any prior knowledge on the actual number of speakers in the conversation. you might have some kind of uh guidance on I don't know if if you are a meeting note taker for instance you you have the list of attendees uh so you might have an idea of the number of people that were invited but that doesn't mean that uh someone um two people joined from the same channel or or that an attendee that was not invited actually join in finally and uh so that that makes the problem uh kind of difficult in the sense that we don't know in advance the number of classes that we're supposed to detect contrary to other let's say classical machine learning problems and also we don't know the identity of the speaker that we're supposed to uh diorize in the sense that speakerization does not really output uh John and uh and and Jack uh but basically it's more like speaker one speaker two speaker three and they can be permutated and it's still correct for example in this example if I just change green into black and black into green. The derization is still exactly the same from the point of view of the evaluation metrics that I'm going to talk about and uh from the point of view of the actual speakerization task.
</details>

所以这使得这个问题相当困难，这也是为什么尽管整个社区在这个课题上研究了很长时间，它目前仍未解决。还有其他原因，例如我们必须检测重叠语音并处理重叠语音；我们必须考虑非常短的话轮；必须考虑对话中多个说话人发言时间的不均衡。所有这些都让问题变得棘手，此外还要面对任何语音处理任务都必须应对的常规声学环境等问题。

<details><summary>Original English</summary>
So that makes the uh this problem kind of difficult and that's why even though the community has been working on this topic for a long time now it's still not solved. Uh there are other reasons like the fact that we have to detect overlapping speech to handle overlapping speech. Uh that we have to uh take into account very short speech turns that have to take into account imbalance between the speech time of multiple speakers in the in the conversation. All of that makes the problem difficult on top of the usual acoustic conditions problems and everything that any speech processing uh um task have to deal with.
</details>

### 评估与演示

那么，我要切换到一个演示，进一步向大家展示分离系统是如何评估的。也许当你们偶然看到基准测试时，会发现 DER 这个缩写，DER 代表说话人日志错误率（Diarization Error Rate）。希望演示能顺利运行。我这里有一个为本次演讲准备的 Python 笔记本，其实已经在 GitHub 上公开了。演讲结束时我会分享二维码，大家可以去试用。在这个例子中，我有一段两位女性通过电话交谈的对话。

<details><summary>Original English</summary>
So uh I'm going to switch to a demo to to show you a bit more how dorization system are evaluated. Um maybe when you you you stumble into benchmark you find this D acronym which is D stands for diorization error rate and uh so hopefully um this will work. So I have here a Python notebook uh that I've prepared for for this talk. It's actually already available on GitHub. I'll share you the the QR code at the end of the presentation so you can play with it. But so in this example, I have a conversation between two women uh talking over the phone.
</details>

>> 喂，你好。

<details><summary>Original English</summary>
>> Hello. Hello.
</details>

>> 哦，你好。我不知道你在。

<details><summary>Original English</summary>
>> Oh, hello. I didn't know you were there.
</details>

>> 我也不知道。

<details><summary>Original English</summary>
>> Neither did I.
</details>

>> 好吧。我以为，你知道，我听到了哔的一声。我是新泽西的黛安（Diane）。

<details><summary>Original English</summary>
>> Okay. I thought, you know, I heard a beep. This is Diane in New Jersey.
</details>

>> 我是得克萨斯的希拉（Sheila）。原籍芝加哥。

<details><summary>Original English</summary>
>> And I'm Sheila and Texas. Originally from Chicago.
</details>

>> 哦，我也原籍芝加哥。不过我现在在新泽西。

<details><summary>Original English</summary>
>> Oh, I'm originally from Chicago also. I'm in New Jersey now, though.
</details>

>> 好的。你们明白这个意思了，一段两位女性之间 30 秒的对话。这就是完美的说话人归属转写所期望的输出，这是人工标注的。现在我在这里要做的，实际上是在同一个文件上运行 pyannote 开源社区版 1 号模型。它现在其实正在我的 Mac 上运行，所以这里我使用的是这个 MPS PyTorch 后端。它的工作流程是，你首先用这行代码从 Hugging Face 下载模型，然后直接应用到音频文件上。现在已经完成了，这里有一个 prediction 变量，里面包含……抱歉，我应该在另一个标签页里操作的，因为那是已经处理过的，我本来想现场运行。那我们现在现场跑一次。它正在运行，接下来的步骤实际上就是可视化系统产生的错误。在顶部这里，大家可以看到参考标注，也就是分离的期望输出；而这里是开源免费使用的社区版 1 号说话人分离流程的输出。就像我说的，它会产生三类错误，比如这里的混淆错误（confusion），把说话人弄错了；它也可能产生虚警（false alarm），虚警是指真实标签中其实没有语音，但它检测到了语音；漏检（missed detection）则正好相反；漏检可能会发生，比如在重叠语音期间，我们这里实际上只检测到了两位说话人中的一位。

<details><summary>Original English</summary>
>> Okay. So, you you get the idea. a 30 seconds conversation between two women. So this is the expected output of a perfect speaker attributed transcription. This was manually labeled. And now what I'm going to to to do this here is actually run piano open source community one model on this same file. So it's actually running right now on my Mac. So that's why here I'm using this MPS pytorch back end. So how it works is that you first download the model from hugging face with this uh line of code. then simply uh apply it on on the audio file. So now it's finished and uh there's the this prediction variable that contains um uh sorry I should have done that on the other tab because this was the one that was already processed. I wanted to do it live. So let's do it live now. So it's running and so the the next step is to actually visualize the errors that uh this system made. So at the top here you have the reference annotation. So the expected output of dization and here is the output of a community one uh speaker derization pipeline uh that is open source and free to use. So it makes three kinds of mistake as I was saying like a confusion here. It got the speaker wrong. Uh it can also make false alarms. Uh so force alarm is when it detects speech when there's actually no speech in the ground truth and mis detection is the other way around and mis detection can actually uh happen for instance here during overlapping speech when we actually detect only one of the two speakers here
</details>

然后，一旦我们得到了这些虚警、混淆和漏检的基本错误，就可以实际计算说话人日志错误率了。这是借助这个名为 pyannote.metrics 的库完成的，在这个例子中，它基本上得出了 5% 的说话人日志错误率，本质上就是混淆、虚警和漏检之和除以该文件中语音的总时长。我们还有另一个模型，我目前正在运行，希望它能跑通。它现在正在我们的云端 API 上运行，基本上是一个比社区版 1 号更好的模型，我们称之为 Precision 2，正在这里运行。希望它能成功，但每个演示都有可能失败；没有，它成功了。这就是你可以得到的输出效果：大家可以看到，它在这里正确识别了说话人，在虚警和漏检方面的错误也略少一些，总体而言，在这个例子中我认为我们得到了 3% 的分离错误率。

<details><summary>Original English</summary>
and then once we have these uh basically errors of false alarm confusion and mis detection we can actually compute the dization error rate. Uh so this is with this library called piano metrics and uh basically it gives us in this example a 5% diorization error rate which is basically the sum of the confusion uh uh false alarm and mis detection divided by the the total duration of uh of speech in in this uh in this file and um so we have this other model that I'm currently running hopefully it work it works so it's running right now on our uh cloud API I uh basically it's it's a a better model that community one that we called precision 2 that is uh uh running here hopefully it will work but as for every demo it might fail if no it worked and this is the kind of output that you can get so you see that it got the the speaker right here and makes slightly less mistakes in terms of false alarm and mis detection and overall in this example I think we got 3% uh dization error here.
</details>

### 从分离到说话人归属转写

让我切换回幻灯片。刚刚介绍的是说话人分离模型的基准测试。我经常被问到，目前最顶尖的说话人分离技术表现到底有多好？这是一个很难回答的问题，因为完全取决于使用场景，结果可能会千差万别。例如在这个样本中，我们有电话交谈语音，就像我们刚才听到的那种，两个人通过电话交谈，我们可以降到 8% 的分离错误率，最好的系统能做到这一点。但如果大家现在身处一家餐馆，和许多朋友在一起，伴有大量的背景噪音，即使是最好的系统，分离错误率也会达到大约 41%。所以这远非一个已经解决的问题，但我们正在攻关。

<details><summary>Original English</summary>
So, let me switch back to the to the presentation. Uh, so this was about benchmarking a speakerization model. And I'm often asked how well does state-of-the-art speakerization works today. And it's a difficult question to answer because really depending on the use case, it might uh vary completely. For instance, in this example, we have a here conversation telephone speech like the one we just listened to like 2% over the phone and we we can go down to 8% dization rate. The best system does that. But if if you are now in a restaurant with many friends with lots of background noise, uh even the best system reaches like 41% dization rate. So it's far from being a solved problem. Uh but we we are working on that.
</details>

一旦有了说话人分离，并且有了转写，要真正得到带有说话人归属的转写应该没那么难，对吧？无非就是把词分配给说话人，或者把说话人分配给词。但实际上那并不容易，有许多原因导致它没那么简单。第一个原因在于，大多数语音转文字模型实际上都是在单人语音数据上训练的。一旦把它们应用到包含重叠、说话人切换以及各种混乱状况的多人语音数据上，它们就会彻底惨败。例如，当大家查看 Hugging Face 的 Open ASR 排行榜时，比如看一下我们在用的、我马上就会在演示中用到的英伟达 Parakeet，他们报告的字错误率是 11.4%；而当我们在我们这边将完全相同的模型应用到相同的 AMI 数据集上时，我们得到的却是 26%。那么问题来了，为什么会有差异？实际上在于那些基准测试的设置方式。例如在 AMI 数据集里，那是一批包含会议的数据集，我记得是在会议室里由四到五个人开会，基本上配备了像我现在戴的这种耳机麦克风，以及桌子中央的一个麦克风。Open ASR 排行榜上的那些数字是基于耳机麦克风得出的；而这里的那些数字则是基于中间的麦克风得出的。因此，一边是单人语音，另一边则是多人语音乃至远场麦克风语音。所以这就是为什么它

<details><summary>Original English</summary>
And um so once you have speakerization and you have transcription shouldn't be that hard to actually find a speaker attributed transcription right it's just a matter of you know assigning a word to a speaker to a word but actually that's not that uh easy and I'll um there are many reason why that's not that easy the first reason is that most uh speechtoext models are actually trained on single speaker data as soon as you apply them on multispeaker data with overlap with speaker change with all kind of mess they completely uh uh they fail miserably. So for instance when you look at the open ASR leaderboard from a hugging phase if we look for instance an Nvidia parakeet that we are using that that I will be using in a in a demo right after that they report 11.4 four uh person rate when we apply the very same model on the same ammy um on um on our side we we get 26%. So the question is why is there a difference actually it's in the way the those benchmark are set up here on the uh for for example in this ami data set that's a a meet um data sets with meetings uh between four to five people I think in meeting rooms and they are basically microphones like the one I'm I'm uh having here so headset microphone as well as one microphone in the middle of the the table and and uh those numbers here uh on the open a solid the board are based on the headset microphone. Those numbers here are based on the microphone that is in the middle. And so on one side you have a single speaker speech on the other side you have multis speaker and even distant microphone speech. So that's why it
</details>

<!-- chunk 3/3 -->

大幅下降。这就是我想在这张幻灯片上说明的观点。在进行说话人归属转写时，出现问题的原因要么是因为 ST 效果不佳——通常情况下，正如我所说，它们很难很好地泛化到多种录音场景中，比如远距离麦克风、说话人切换、串扰、打断等等，可能还有语码转换，即在句子中途切换语言。

<details><summary>Original English</summary>
degrades a lot. And so that that's that was my point of of this slide. So, uh, when doing speaker attributed transcription, the, um, the reason why it might go wrong is either because ST doesn't work great. And, um, it's usually the case that they don't generalize, uh, very well to multipe recordings for, as I was saying, distant microphone, uh, speaker change, cross talk, interruptions, you name it. Uh, maybe code switching as well when you change language in the middle of a sentence.
</details>

但这也可能是因为说话人日志与 ST 时间戳之间的实际对齐问题。虽然具体做法听起来可能很显而易见，但正如我之前所说，我希望在接下来的实时演示中再次证明，这绝非易事。因为 ST 无法很好地转写重叠语音；因为 ST 与说话人日志之间的时间戳不一致；还因为有时说话人日志检测到了语音，但转写系统却没有转写，反之亦然。

<details><summary>Original English</summary>
But also it's it might be because of the actual reconciliation between diorization and ST time stamps. Though it may sound uh uh obvious how to do that as I was saying I will hopefully show in this uh live demo once again that it's it's not such an easy problem because uh ST does not transcribe overlapping speech well uh because uh the time stamps disagree between ST and diorization and because sometimes diorization will detect speech that the transcription will not transcribe and the other way around.
</details>

### 演示：说话人归属转写与时间戳对齐

那么，演示的第二部分是关于说话人归属转写的。首先，我将应用英伟达的这个 Parakeet 模型，顺便说一句，它在转写这个音频样本上表现得非常出色，Parakeet 给我们提供了这样一种输出。我们得到了这个词序列，并且对于每个词，实际上都有对应的时间戳。好的，我可以快速播放一下。

<details><summary>Original English</summary>
So um second part of the demo uh about speaker attributed transcription. So uh first I'm going to apply uh this parakeet model from Nvidia that does a by the way a great job at transcribing uh uh this sample and so parakeit gives us this kind of output. So we have this sequence of words and for each word we actually have the the corresponding time stamps. Okay. So, uh, I can play it quickly.
</details>

>> 你好。

<details><summary>Original English</summary>
>> Hello.
</details>

>> 哦，你好。我不知道你在那儿。

<details><summary>Original English</summary>
>> Oh, hello. I didn't know you were there.
</details>

>> 我也不知道。

<details><summary>Original English</summary>
>> Neither did I.
</details>

>> 好的。我刚才还以为，你知道，听到了哔的一声。我是新泽西的戴安（Diane）。

<details><summary>Original English</summary>
>> Okay. I thought, you know, I heard a beep. This is Diane in New Jersey.
</details>

>> 好吧，大家明白意思了。那么问题是，现在我们有了效果最好的说话人日志结果，这里是 precision 2 的输出，这里是 Parakeet 的输出。现在的问题是，我们需要为每个词分配一个说话人。我们一步一步来看。比如在这个例子中，即使词的时间戳在左边这里有一点偏移，但显而易见，这个灰色的词很可能是黄色说话人说的。但是如果你看第三个词，现在成了这样：根据说话人日志，这里的这个“o”词正好介于这两个语音段之间。

<details><summary>Original English</summary>
>> Well, you you get the idea. And then, um, the question is, um, now we have our best dization. This is precision two output here. This is parakeet output here. And the question is now we need to assign a speaker to each word. So, let's do it step by step. for instance. Uh so in this example, even though the time stamps of the the words are a bit shifted uh on the left here, it's obvious that it's probably the yellow speaker who spoke the the gray word. But if you go just the third word, so now we have this. So we have this word, the word o here that is in between those two speech tones according to theation.
</details>

你应该把它分配给哪一个呢？我们可以听一下。

<details><summary>Original English</summary>
Which one do you assign it to? Um so we we I can listen to it.
</details>

>> 哦，你好。

<details><summary>Original English</summary>
>> Oh hello.
</details>

哦，你好。

<details><summary>Original English</summary>
Oh hello
</details>

>> 这不是很确定，而且还有很多其他位置也出现了这种情况。同样，这里有一个词。根据说话人日志，显然有两位说话人在讲话，但转写结果中却只有一个词。这就是为什么在 pyannote，我们提出了这种全新的 ST 编排功能，它基本上能施展其魔力并为你完成这项工作。这里我刚刚向我们的云端 API 提交了一个任务，同时使用 precision 2 说话人日志模型和 Parakeet 转写模型进行转写，并处理我所说的两者之间的对齐问题，最终你会得到这样的输出。

<details><summary>Original English</summary>
>> it's not quite quite sure and there are many other uh position where it happens here. Same there's a word here. Okay that apparently according to dization there are two speakers speaking and only only one word from the from the transcription. So that that's why at pianoi we came up with this uh new st orchestration thing that basically does uh its magic and and does the job for you. So here I I just submitted to our cloud API um a a job to transcribe and and and use both precision to derization model and parakit transcription model and take care of the what I call this uh reconciliation between the two and you end up with this kind of with this kind of output.
</details>

很棒的是，现在它已经为你完成了这项工作，尤其是我特别喜欢看这个具体的例子：即使在之前有语音重叠的地方，它实际上成功地将说话人的词交织穿插在了一起。让我播放一下这部分，重点关注一下这个区域：

<details><summary>Original English</summary>
Uh what's nice is that so now you it did the the job for you but in particular I I like to go to this particular example even where there was overlapping speech before it actually managed to uh interle the words from the speaker. Let me play the just this part and focus on this uh area maybe
</details>

>> 在新泽西。

<details><summary>Original English</summary>
>> in New Jersey.
</details>

>> 我是希拉（Sheila），在科技……

<details><summary>Original English</summary>
>> And I'm Sheila and tech
</details>

>> 这里实际上有一个“and”，或者说这里的“M”，其实是黄色女士在说话末尾发出的“hum”声，而蓝色说话人实际上打断了她。但她们实际上是在重叠说话的，而我们成功把它们处理对了。

<details><summary>Original English</summary>
>> and there's actually a end uh that uh or this is the M here that is actually the the the the yellow lady actually has this hum at the end of the her speech and the the blue one actually interrupts her. But they they actually overlapping and we managed to get them right.
</details>

### 问答环节

嗯，是的，我的演讲就到这里。我想给大家留几分钟。我还剩两分钟提问时间，但我只想说明一下，我做的这个演示已经可以在 pyannote-tutorials GitHub 仓库中获取了。在里面你将能够体验用于说话人日志的 pyannote 开源工具包，用于评估的 pyannote.metrics，用于我们实现的这个漂亮可视化小组件的 ipyannote——这里的“i”代表的可不是 iOS 或 iMac 之类的，而是真正代表交互式（interactive）——以及用于体验我们高级模型的 SDK。我就讲到这里，很乐意回答几个问题。我们还剩一分钟。

<details><summary>Original English</summary>
Um yeah, so this is the end of my talk. I I wanted to give you a few minutes. I have two minutes left for questions, but I want just wanted to say that this demo uh that I I did is already available on in the piano tutorials GitHub repo. So in there you you'll be able to play with piano open source toolkit for dization with piano matrix for evaluation with ipode for this nice uh visualization widget that we've uh implemented. I stands for not iOS, iMac or whatever, but really for interactive and uh also the SDK to to play with our premium models. And uh I'll stop here and u I'm happy to take a few questions. We have one more minute left.
</details>

>> 好的，请讲。

<details><summary>Original English</summary>
>> Yes, please.
</details>

>> 那么你们用来解决冲突的诀窍是什么？这是模型训练的一部分，还是你们采用的某种启发式规则来确定这个词应该归属给谁？

<details><summary>Original English</summary>
>> So what's the trick that you use to resolve the conflicts? So part of the model training or is it some sort of like heristics that you have around to identify who to attribute the word to?
</details>

>> 是的。问题是真正解决这种对齐问题的诀窍是什么。这是一个专有技巧，但我可以说的是，这个技巧的一部分已经在社区版 1 模型中提供了，我们称之为独占式说话人日志（exclusive diarization）。基本上，我们所做的是在出现重叠时，找到一种方法来实际选出两位说话人中最可能被 ST 模型转写的那一位。因此，这实际上简化了两者之间的对齐。这就是该方法的一个主要部分。

<details><summary>Original English</summary>
>> Yeah. So the question is what's the trick to actually solve this problem of a reconciliation. Uh so that that's a proprietary trick but what I can say is that we uh there's already part of this trick that is available in the community one model which we call exclusive derization. Basically uh what we do is that we find a way when there is overlap to actually select the most likely of the two speaker that will be transcribed by the ST model. So that simplifies actually the reconciliation between the two. So that that's one major part of the uh of the approach
</details>

>> 模型训练……就像几条你必须遵循的启发式规则……

<details><summary>Original English</summary>
>> of the model training is like a couple of huristics you have to
</details>

>> 是的。这个问题是关于……我重复一遍问题，因为有人告诉我必须重复问题。从我们确实计划支持任何类型的 ST 而无需更改 ST 模型本身的意义上来说，它不是模型训练的一部分。因此，它确实应该可以与任何 ST 配合使用，甚至包括你们内部可能拥有的、因为针对特定用例进行了微调而其他人都没有的优质模型。你可以像这样进行结合。

<details><summary>Original English</summary>
>> Yeah. So so the question is about I repeating because I've been told I need to repeat questions. Uh so it's not part of the model training in the sense that we really plan to support any kind of ST without having to change the ST model itself. So really it's supposed to work with any ST even fine ones that you might have internally for because you you fine-tune them for your particular use case and nobody has it. Uh you can combine it like that.
</details>

还有 18 秒。所以我想我们得结束了。非常抱歉。或许我们可以线下交流，不然他们就要把我赶下台了，我猜。非常感谢大家。不好意思。

<details><summary>Original English</summary>
18 seconds. So I guess we need to stop. I'm sorry. Maybe we can talk offline otherwise they'll they'll beat me I guess. Thank you very much. I'm sorry.
</details>