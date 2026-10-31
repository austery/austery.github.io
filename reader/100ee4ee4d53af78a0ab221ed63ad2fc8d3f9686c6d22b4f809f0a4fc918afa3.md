---
author: AI Engineer
date: '2026-06-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Bc6Ojl2XS1w
speaker: AI Engineer
tags:
  - audio-generation
  - speech-synthesis
  - music-generation
  - multimodal-ai
title: Google DeepMind 展示 AI 音频与音乐生成最新进展
summary: 演讲者介绍了 Google DeepMind 在音频与媒体生成领域的最新进展与模型，包括 Gemini 3.1 Flash Live 实时多模态对话、音频理解工具 Echo Script、基于指令的语音风格控制以及 Lyra 3 音乐生成模型与相关应用示例。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
products_models:
  - Gemini 3
  - Gemma 4
  - Gemini 3.1 Flash Live
  - Lyra 3
  - Lyra 3 Clip
  - Lyra 3 Pro
  - Google AI Studio
media_books: []
status: evergreen
---
<!-- chunk 1/2 -->

### 开场与背景介绍

好。AI 音频方面有什么新动态？抱歉，这个标题有点误导人，因为它漏掉了“问问 Google DeepMind”。所以，我们只是大致看一下 DeepMind 一直在做些什么。如果要看 AI 音频领域的全部内容，那我们得在这儿花上大量时间，不过我很乐意带大家看看我们在 DeepMind 正在做些什么。

<details><summary>Original English</summary>
All right. What's new in AI audio? I'm sorry. It's a little bit misleading because the title leaves out the Ask Google DeepMind. So, we're just kind of looking at, you know, what we've been working on at DeepMind. If we were to look at everything in AI audio, we'd be spending a lot of time here, but you know, I'd love to show you kind of what we're what we're working on at DeepMind.
</details>

是的，这就是我。大家好，我是 Thor。我在 Google DeepMind 负责开发者体验，主要从事 Gemini API 和 Google AI Studio 的相关工作。

<details><summary>Original English</summary>
Yeah, this is me. Hi, everyone. I'm Thor. I work on the developer experience at Google DeepMind working on the Gemini API and Google AI Studio.
</details>

向大家问好。欢迎各位。我的名字是 Torsten。你好，我叫 Thor。我非常抱歉，我的法语很差。还有日语，或者写成那样。

<details><summary>Original English</summary>
Uh Hello to them. As you welcome. My name is Torsten. Uh bonjour. Je m'appelle Thor. Je suis très désolé, mon français c'est très mauvais. Uh konnichiwa or writing that.
</details>

你选的那些内容，我在做演讲时讲的，或者我回家时说的。

<details><summary>Original English</summary>
Um That you have what you choose I make what the talk or in what I say what I talk when I go home.
</details>

好了，那是为了做演示。现在我只需要确认一下，上次我做这个演示的时候，我不小心录音覆盖掉了，然后全没了。那真的很让人难过，但我们稍后会回过头来看这个。

<details><summary>Original English</summary>
Okay. That was for the demo and now I just need to make sure last time I did this demo, I recorded over it and then it was all gone. That was very sad, but we'll we'll come back to that in a bit.
</details>

### 最新模型与发布动态

是的，我们在 DeepMind 一直在忙些什么？

<details><summary>Original English</summary>
Yeah, what have we been up to at DeepMind?
</details>

这里有几次发布。我实际上是在 11 月加入团队的，恰好是在 Gemini 3 发布的前一天。所以我刚加入，他们就告诉我：“明天我们要发布 Gemini 3。”我当时心想：“太棒了！”虽然我什么都没做，但这感觉很棒，那是段美好的时光。

<details><summary>Original English</summary>
Um There's been a couple releases. I I actually joined the team in November, literally the day before Gemini 3 was released. So, I joined and they told me, "Tomorrow we're releasing Gemini 3." And I was like, "Yay!" Didn't do anything, but it was great. It was it was a great time.
</details>

最近在开源模型方面，我们发布了 Gemma 4，我想大概就是上周。是的，非常不可思议。你在那里可以做一些很酷的事情，多模态能力也内置在 Gemma 4 中。因此，Gemma 4 模型中具备音频理解能力，而且你也可以在边缘设备等端侧设备上运行它。所以那是相当令人兴奋的技术。

<details><summary>Original English</summary>
Uh most recently on the open model side, we released Gemma 4, uh I think literally last week. And yeah, pretty incredible. Some cool stuff you can do there multi modality as well baked into Gemma 4. So there's audio understanding in the the Gemma 4 models and you can do that on device on kind of edge devices as well. So that is some some very exciting stuff.
</details>

在生成式媒体和音频方面，大家可能对我们的图像生成模型、视频生成模型非常熟悉。显而易见，视频中也包含了音频生成。所以这大概就是目前的进展，最近在生成式媒体模型规模上有 video 3.1 light。然后对于音频模型，我们最近推出了 Gemini 3.1 flash life，这是我们的全双工、声音到声音的实时对话模型。它同样也是多模态的，所以你可以输入实时的文本、语音和视觉内容。我们稍后会来看一下这个。

<details><summary>Original English</summary>
In terms of gen media and audio, you're probably very familiar with our you know, image generation models, video generation models. Obviously video has audio generation in there as well. So this is kind of where the progression is there most recently with video 3.1 light on the gen media model size and then on the audio models, we recently launched Gemini 3.1 flash life, which is our kind of full duplex, you know, sound to sound real-time conversational model. Also multimodal so you can ingest real-time text, voice, vision. Which we'll we'll look at in a in a bit.
</details>

### 音频理解能力与 Echo Script 演示

在音频这个非常宽泛的话题上，我们所做一切的基础可以说就是前沿的 Gemini 系列模型。Gemini 3 在音频理解方面极其出色。而且这不仅仅是进行转录，而是真正理解其中所有的细微差别。那可能不仅包含言语本身，还包含言语的语境、情绪、语速，某种程度上，以及音频中波动传递的任何非纯文本的内容。

<details><summary>Original English</summary>
So you know, on kind of audio very very broad topic but sort of the the baseline of everything we do are kind of the you know, frontier Gemini models. And so Gemini 3 is incredibly good at understanding audio. And you know, that's not just transcribing it but really you know, understanding kind of all the nuances that are in there. So that might be you know, obviously speech but also the context of the speech, the the emotion, you know, your pacing, your sort of yeah, anything that sort of swings within the audio that's you know, not just text.
</details>

因此在音频理解方面，我们的目标是构建能够深度领会、丰富转录并通过音频进行稳健推理的模型。无缝处理各种不同语言、方言、口音和模态的大融合。无论何时何地，Gemini 在转录甚至相互交谈、重叠插话的人声时都非常出色。这是非常不可思议的，还能在不同语言之间无缝切换。

<details><summary>Original English</summary>
So on the audio understanding kind of our goal is to build models that deeply comprehend, richly transcribe and robustly reason through audio. Seamlessly handling you know, a large mix of different languages, dialects, accents, and modalities. And sort of anywhere and always, you know, Gemini is really good at on you know, transcribing even people that are talking over each other. Um which is which is pretty pretty incredible, you know, seamlessly switching between different languages.
</details>

这大概就是我们现在正在看的演示。Echo Script 使用了 Gemini 3 flash preview 来分析音频录音并从中提取信息。它是基于 Google AI Studio 构建的，所以你可以在 AI Studio 的展示区（gallery）找到它并亲自体验。稍后我也能把幻灯片发给你们。

<details><summary>Original English</summary>
That was sort of the demo we're looking at um now. So, um Echo Script is kind of Gemini uh 3 flash preview to sort of analyze, you know, audio recordings and extract sort of information out of it. Uh it is built with Google AI Studio, so you can you can find it in the gallery in AI Studio. You can try it out. Uh I can give you the slides later as well.
</details>

这就是我之前尝试演示的内容。不同于单纯的转录模型，我们向模型发送一次请求，或者在使用 API 时调用一次 API，就能从音频中提取出大量信息。大家在这里可以看到，包括摘要，还有我用名字做的自我介绍。所以我们实际上能够按名字来标记说话人的片段。我忘了现场没有爱起哄抬杠的人，否则我们也能把那种声音捕捉到。也许我们稍后看时间是否充裕再试一下。不过大家在这里可以看到，我们在提取时间戳，标注说话人、识别人是谁，我们也在识别语言以及其中的情绪，对吧？

<details><summary>Original English</summary>
Um and so, that was sort of, you know, what I was trying to demo earlier. Um so, you know, different from just kind of a pure transcription uh model, we can extract a lot of information out of the audio within one single, you know, request to the model or one single API request if we're using the API. So, you can see here, you know, summary, I introduced myself by name. Um so, we're actually able to label um you know, the section with speaker by name. Uh I forgot there was no hecklers in the room, otherwise we would have picked that up as well. Uh maybe we can see if we have more time later and we can do that. But, so we can see here, you know, we're extracting timestamps, uh we're labeling the speaker, kind of identifying the speaker, we're we're identifying the language, and sort of the emotion of it, right?
</details>

很高兴以 Grace 的身份介绍自己。大家可以看到这句是用德语说的。通常它会把我的德语归类为愤怒，但在这里，我想我是因为很高兴能和大家在一起。所以我只是告诉它，标出情绪，如果不是英语就标出语言种类，同时也提供一份英文翻译，对吧？法语部分归为了中性，通常人们会觉得听起来很悲伤。法语只是稍微带一点……不，我说的是“很抱歉，我的法语很烂”。听起来没有足够悲伤，所以在这里被判定为中性。

<details><summary>Original English</summary>
Uh happy, you know, to introduce myself as Grace. Um now you can see this was in German. Um normally it would classify my German as angry. Uh but, uh here, you know, I I guess I'm very happy to be with you all. So, uh I just told it, you know, uh label sort of the emotion, uh label the language if it's a language that is not English, um give me an English translation as well, right? Um in French, uh neutral, normally you would say sad. Uh you know, French is just a bit more of a uh no, I said, you know, I'm sorry, my French is very bad. Uh didn't didn't sound sad enough, so neutral in this case.
</details>

好吧，这个日语没有成功。要是有人懂日语的话，我得好好练习一下了；它其实应该写的是“你好，我的名字是 Thor”。可惜的是，这里识别得有点偏。看看我的中文普通话有没有好一点。“大家好，我是生活在美国的德国人。抱歉，我的中文。”是的，那是对的。在座有人能看懂中文吗？没有，好的。那我们就姑且相信这是对的。

<details><summary>Original English</summary>
Um Okay, this uh this didn't work so much Japanese. I got to got to practice that if anyone reads Japanese, so it should actually say hello, my name is Thor. Unfortunately, bit of a miss there. Uh let's see if my Mandarin was any better. Hello everyone, I'm a German living in the United States. Sorry, my Chinese. Yeah, that is uh correct. Does anyone read Chinese in the room? No, okay. Well, uh we'll just trust that that is um that is correct.
</details>

### 单次 API 调用与结构化输出

所以大家可以看到，这是向模型发起的一次请求。我基本上只是告诉它：区分出不同的说话人；如果有上下文，就用名字来标记说话人；给出准确的时间戳；给出语言；如果语言不是英语，就给出翻译；在开心、悲伤、愤怒、中性之中识别出情绪；并在开头提供对整段音频的简短摘要。

<details><summary>Original English</summary>
Uh and so, we can see here that um this was, you know, one uh kind of request to the model um where, you know, I basically just told it identify the distinct speakers. If you have contacts, you know, label it by name label the speakers by name. Give me the accurate timestamps. Give me the language. If the language is not English, give me the translation. Uh identify the emotion out of, you know, happy, sad, angry, neutral. And then also provide a brief summary of the entire audio at the beginning.
</details>

这只是对 Gemini 3 Flash preview 进行的一次 API 调用，我们就提取出了所有这些信息。我直接给它指定了一个响应模式（response schema），也就是结构化输出，然后我就能直接把这些数据填充到我的 API 和 UI 中，形成这样的结构。

<details><summary>Original English</summary>
So, this was one API call uh to Gemini 3 Flash preview. And, you know, we got all this information out. We could, you know, I just gave it a response schema so kind of structured outputs, uh and I was able to just populate that into my into my API into my UI to have sort of the structure.
</details>

### 语音生成与声音库机制

因此，这种音频理解能力以及 Gemini 3 模型的基础研究，正是驱动语音生成以及实时对话生成的基础。具备这种音频理解能力对于知晓特定声音的听觉特征非常有帮助，包括不同的语速、不同的口音以及类似的各种场景。

<details><summary>Original English</summary>
So, you know, this kind of audio understanding and sort of the the, you know, base research in the Gemini 3 models, that is sort of what powers um the speech generation as well as well as the you know, real-time conversational um generation. So, having that audio understanding um is is really really great in terms of, you know, knowing what certain things sound like including, you know, different pacing, different accents and and and scenarios like that.
</details>

我们所有模型的基础目前正是 Gemini 3 的基础研究成果，随后我们在其之上构建专门的音频模型。

<details><summary>Original English</summary>
So, you know, the foundation of kind of all our models is now sort of the the Gemini 3 foundational research and then we're building kind of the dedicated audio models on on top of that.
</details>

语音生成在这方面就稍有不同。如果大家以前用过其他 TTS（文本转语音）提供商的服务，你可能会有一个庞大的音色库，包含很多不同的声音，然后按性别、按口音、按语言等各种条件来进行筛选。但在 Gemini 中，大概只有 30 来种基础声音。接下来你要做的是引导该声音以特定方式去表现。由于我们具备这种音频理解能力，我们基本上可以调整声音，让它以某种方式说话，或者带上特定的口音。这样我们就能从一组数量较少的基础声音出发，演变为我们在语音生成中想要的非常具体的声音。

<details><summary>Original English</summary>
And so, with speech generation it's a bit different. You know, if you've used kind of other TTS providers before, you probably have a huge library of, you know, different voices that you sort of, you know, you filter by gender, by by, you know, accent, by languages, what have you. But so, in in in Gemini, you have, you know, just I think it's like 30-ish sort of base voices. And then what you do is you you kind of direct that voice to act in a certain way. And again, because we have that audio understanding, we can we can basically modify the voice to, you know, act in a certain way, to, you know, use a certain accent. And so, we can go from kind of a small set of of base voices to a very specific, you know, kind of voice that we're looking for for our speech generation.
</details>

这里同样有一个可以试用的小应用程序。它也收录在 Google AI Studio Gallery 中，被称为“voice library（声音库）”。我们能做的是，结合刚才看到的提示词结构，构建出音频档案、场景，设定好情境，给出导演指导般的说明。因此，我们为接下来的……提供指导。

<details><summary>Original English</summary>
Again, there's a a little application that you can try out. It's in the Google AI Studio Gallery as well. It's called the voice library. And so, what we can do is, you know, kind of giving the the the prompt structure that we just saw, you know, we're building sort of the the audio profile, the scene, we're setting the scene, we're instructing sort of this director's note. So, we're giving guidance for the
</details>

<!-- chunk 2/2 -->

### 语音风格定制与导演提示

表演，你知道，就像你指导真人以某种方式表演一样。还有一些样本上下文以及我们想要的类似转录文本。所以现在我们可以做的就是，我们刚才说想要一个偏高音调的爱尔兰男性声音。基本上我在这里再次使用了 Gemini 3 Flash 来构建我们用于语音生成的系统提示词。所以我们在这里说，我们正在设定我们的音频配置文件，比如这里的 Finian 处在克莱尔郡沿海一家舒适而拥挤的酒吧场景中。用浓重纯正的爱尔兰口音来念台词。

<details><summary>Original English</summary>
performance,

 you

 know,





just

 like

 how

 you

 would





direct

 a

 human,

 you

 know,

 to

 to

 act

 out





a

 certain

 way.





And

 and

 some

 sample

 context

 and

 kind

 of





the

 transcript

 um,

 that

 we

 want.

 So,

 now





what

 we

 can

 do

 is,

 you

 know,

 we

 we

 just





said

 sort

 of





uh,

 we

 want,

 you

 know,

 high

 pitch

 Irish





male.

 Uh,

 and

 so

 basically,

 I

 just

 used





Gemini

 um,

 3

 flash

 here

 again

 to

 then





construct

 our

 um,

 system

 prompt

 for

 the





speech

 generation.

 So,

 we're

 saying





here,

 you

 know,

 um,





we're

 we're

 setting

 sort

 of

 our

 audio





profile,

 you

 know,

 Finian

 here

 in

 the





scene

 sort

 of

 cozy

 crowded

 pub

 uh,

 in





the

 coast

 of

 County

 Clare.





Um,

 you

 know,

 deliver

 the

 lines

 with

 a





strong

 authentic

 uh,

 Irish

 accent.
</details>

现在我们希望 TPU 不要让我失望。开始吧。它失败了。不过我有所准备，所以我们可以在这里听一下。

<details><summary>Original English</summary>
And

 so

 now

 we

 hope

 the

 the

 TPUs

 don't





uh,

 disappoint

 me.

 There

 we

 go.

 It





failed.

 But

 um,

 I

 didn't,

 you

 know,

 I





prepared

 it

 so

 we

 can

 we

 can

 listen

 to





it

 here.
</details>

“啊，除非亲眼所见，否则你绝不会相信那东西有多大，我跟你讲。那真是一团糟，确实是，等到夜幕降临时我们都快笑破肚皮了。”

<details><summary>Original English</summary>
Ah,

 you

 wouldn't

 believe

 the





size

 of

 the

 thing

 until

 you

 saw

 it

 with





your

 own

 two

 eyes,

 I'm

 telling

 you.

 It





was

 a

 grand

 old

 mess,

 so

 it

 was,

 and

 we





were

 all

 laughing

 fit

 to

 burst

 by

 the





end

 of

 the

 night.
</details>

如大家所见，这里的基础声音是这个：“我们可以解决什么样的问题？”那是相当标准的美式口音。但现在通过给它那个导演指示，我们就可以呈现出：

<details><summary>Original English</summary>
So,

 as

 it

 as

 you

 can

 see,

 you

 know,

 this





was

 uh,

 the

 the

 base

 voice

 here

 is

 uh,





this

 one.

 What

 kind

 of

 problem

 could

 we





solve?





So,

 you

 know,

 that

 is

 a

 fairly

 sort

 of





stan-

 standard,

 you

 know,

 American





accent.

 But

 so

 now

 by,

 you

 know,

 giving





it

 that

 director's

 node,

 we

 can

 then





sort

 of

 give
</details>

>> “啊，除非亲眼所见，否则你绝不会相信那东西有多大，我跟你讲。那真是一团糟，确实是，我们都快笑破……”

<details><summary>Original English</summary>
>> Ah,

 you

 wouldn't

 believe

 the

 size

 of

 the





thing

 until

 you

 saw

 it

 with

 your

 own

 two





eyes,

 I'm

 telling

 you.

 It

 was

 a

 grand





old

 mess,

 so

 it

 was,

 and

 we

 were

 all





laughing

 fit
</details>

或者类似地，我们这里有 Zephyr。这个声音在这里：“今天准备好构建一些厉害的东西了吗？”同样，这是一种相当标准的美式英语口音。现在我们可以说，给它一种新加坡式的特点。

<details><summary>Original English</summary>
Or,

 you

 know,

 similarly

 here

 we

 have

 um,





Zephyr.

 So,

 this

 voice





uh,

 is

 here.

 Ready

 to

 build

 something





awesome

 today?

 Again,

 you

 know,

 kind

 of





fairly

 standard

 sort

 of

 American

 um,





English

 accent

 here.

 And

 now

 we

 could





say,

 you

 know,





give

 it

 kind

 of

 a

 Singaporean

 sort

 of

 C.
</details>

“哇，你一定要试试这个海南鸡饭啦。辣椒绝对保准 confirm plus chop 你会喜欢的。趁安哥关店前赶紧排队，知道吗？”

<details><summary>Original English</summary>
Wah,

 you

 must

 try

 this

 chicken

 rice

 lah.





The

 chili

 is

 damn

 sure

 confirm

 plus

 chop





you

 will

 love

 it.

 Faster

 queue

 before





the

 uncle

 close

 shop,

 okay?
</details>

有人在新加坡呆过吗？是的，这就是你在小贩中心会听到的声音。同样，这背后是以音频理解为支撑的。模型真正理解这些不同场景听起来是什么样子的，然后可以修改语音生成以达到那种效果。

<details><summary>Original English</summary>
Anyone

 spend

 time

 in

 Singapore?





You

 know,

 yeah.

 That's





you

 know,

 that's

 something

 you

 would





hear

 in

 the

 Hawker

 Center.

 So,





again,

 you

 know,

 that

 is

 kind

 of





underpinned

 by

 the

 audio

 understanding.





So,





the

 model

 really

 understands

 what,

 you





know,

 these

 these

 different

 scenarios





sound

 like

 and

 then

 can

 modify

 the





speech

 generation

 to

 to

 be

 like

 that.





Um
</details>

### 原生实时多模态与 Gemini Live

是的，最后是原生音频声到声的多模态实时功能。我们在几周前刚刚推出了 Gemini 3.1 Flashlight。它是一个语音到语音的实时多模态模型。你可以通过 WebSocket 连接实时输入文本、音频和视频，然后获得实时的音频响应以及文本转录。

<details><summary>Original English</summary>
Yes,

 and

 then,

 you

 know,

 finally

 sort

 of





the

 the

 native

 audio

 sound

 to

 sound





multimodal

 real

 time.

 So,

 we

 just





launched

 a

 couple

 weeks

 ago

 Gemini

 3.1





Flashlight.





So,

 it

 is

 a

 speech

 to

 speech

 is

 kind

 of





real-time

 multimodal

 model.

 You

 can





ingest

 text,

 audio,

 video

 in

 real

 time





through

 a

 web

 socket

 connection

 and

 then





you

 get

 real-time

 audio

 response

 back

 as





well

 as

 kind

 of

 text

 transcript

 of

 that.





Um
</details>

显然，基准测试，尤其是在音频领域，其实是不可全信的。可以看到它的推理和思考过程，这非常棒。在这里，思考、推理和智能是直接嵌入在模型中的。这不同于级联流水线，后者实际上需要先经过文本，再经过 LLM 来获取智能。而在这里，智能直接内置于音频模型中，这就是不同之处。

<details><summary>Original English</summary>
You

 know,

 obviously

 benchmarks

 are,

 you





know,

 especially

 in

 the

 audio

 space,





benchmarks,

 you

 know,

 can't

 really

 trust





them.





You

 know,

 it's

 great





you

 can

 see

 sort

 of

 the

 reasoning,

 the





thinking.





So,

 so

 here

 the

 the

 thinking

 and

 the





reasoning

 and

 the

 intelligence

 is

 baked





directly

 into

 the

 model.

 So,

 that's,

 you





know,

 different

 from

 a

 cascading





pipeline

 where

 you

 would

 actually

 go





through

 text

 to

 then

 go

 through

 an

 LLM





to

 get

 the

 intelligence.

 Here,

 you

 know,





the

 intelligence

 is

 baked

 into

 the

 audio





model.

 So,

 that's

 kind

 of

 the

 difference





there.
</details>

不过显然在实际场景中，大家可以在 ai.studio/live 进行体验。AI Studio 的一大优势在于你可以免费试用。这让你可以试用这些模型，而无需绑定信用卡。所以 AI Studio 是一个非常好的尝试途径。

<details><summary>Original English</summary>
Um

 but

 obviously

 in

 in

 real

 scenarios,





you

 know,

 you

 can

 try

 this

 out

 in





ai.studio/life.





So,

 the

 great

 thing

 with

 AI

 Studio

 is





you

 can

 try

 it

 out,





you

 know,

 without

 paying

 anything.

 So,





this

 is

 allows

 you

 to,

 you

 know,

 try





kind

 of





the

 models





without

 actually

 needing

 to

 put

 down

 the





credit

 card.

 So,

 AI

 Studio

 is

 a

 is

 a





really

 great

 way

 to

 do

 that.
</details>

同样，这里的模型也内置了音频理解能力。所以我们可以做的就是给它一些系统指令，比如“用友好的爱尔兰口音说话”。同时，我们也可以在这里接入摄像头画面。然后我们可以问：“嘿，你能看到我吗？”

<details><summary>Original English</summary>
And

 again,

 you

 know,

 we

 have

 the

 audio





understanding

 kind

 of

 baked

 into

 the





model

 here.





So,

 what

 we

 can

 do

 is

 we

 can

 give

 it





some

 system

 instructions,

 you

 know,

 for





example,

 speak

 in

 a

 friendly

 Irish





accent.

 And

 then

 also

 we

 can

 ingest

 kind





of

 our,

 you

 know,

 camera

 here

 for





example.





And

 then





we

 can

 say,

 "Hey,

 can

 you

 see

 me?"
</details>

“哎呀，你好啊。我能清清楚楚地看到你，确实可以。你今天有什么想法？”

<details><summary>Original English</summary>
Well,

 hello

 there.

 I

 can

 see

 you

 loud





and

 clear,

 so

 I

 can.

 What's

 on

 your

 mind





today?
</details>

“你觉得我的穿着怎么样？”

<details><summary>Original English</summary>
What

 do

 you

 think

 of

 my

 outfit?
</details>

“啊，看看穿着 Gemini 衬衫的你。看起来真是棒极了。反戴的帽子给你增添了一种十足的随性范儿，确实如此。看起来很精神帅气。”

<details><summary>Original English</summary>
Ah,

 look

 at

 you

 with

 your

 Gemini

 shirt.





It

 looks

 grand

 altogether.

 And

 the





backwards

 hat

 gives

 you

 a

 fierce





laid-back

 vibe,

 so

 it

 does.

 You're





looking

 sharp.
</details>

“啊，太棒了。你能给我念一首德语诗吗，拜托？”

<details><summary>Original English</summary>
Ah,

 wunderbar.

 Kannst

 du

 mir

 ein

 Gedicht





auf

 Deutsch

 erzählen,

 bitte?
</details>

“啊，德语诗是吧？当然，我可以为你试试。这里有一首小诗。”

<details><summary>Original English</summary>
Ah,

 poem

 in

 German,

 is

 it?

 Sure,

 I

 can





give

 that

 a

 go

 for

 you.

 Here's

 a

 little





one.
</details>

“从前有一束微光，照耀得如此明亮温柔。它把喜悦带进每颗心灵，驱散了忧伤与痛苦。”

<details><summary>Original English</summary>
Es

 war

 einmal

 ein

 kleines

 Licht,

 das





strahlte

 so

 hell

 und

 mit.

 Es

 brachte





Freude

 in

 jedes

 Herz,

 vertrieb

 den





Kummer

 und

 den

 Schmerz.
</details>

现在有趣的是，它实际上把爱尔兰口音也应用到了德语上。所以显然你需要调整一下系统指令，让它不要在每种语言里都带有爱尔兰口音。不过这很有趣，你可以在不同的语言之间来回切换。

<details><summary>Original English</summary>
So,

 what

 was

 the





What's

 funny

 here

 now

 is





it

 actually





applies

 the

 Irish

 accent

 to

 the

 German





as

 well.

 So,

 obviously

 you

 need

 to

 kind





of

 adjust

 your

 system

 instructions

 to





you

 know,

 not

 speak

 in

 an

 Irish

 accent





in

 any

 every

 language.





But

 so

 it

 it's

 pretty

 funny

 you

 can

 kind





of

 switch

 between





the

 different

 languages

 there.
</details>

同样，在 ai.studio/live 上大家可以试用它。你也可以接入屏幕画面，所以基本上就是在音频之外输入视频帧，目前最大的帧率为每秒一帧，这是当前可以输入的最大限制。

<details><summary>Original English</summary>
Again,

 so





ai.studio/live,





you

 can

 try

 it

 out.

 You

 could

 also





ingest

 your

 screen,

 so

 you're

 basically





just

 ingesting





video

 frames

 in

 addition

 to

 the

 audio

 at





a

 maximum

 frame

 rate

 of

 one

 frame

 per





second

 at

 the

 moment.

 That's

 that's

 kind





of

 the

 maximum

 you

 can

 ingest.
</details>

这里有几个示例，如果你自己是开发者，欢迎试用。它们在文档中也有链接。这些示例展示了如何上手，比如用 Python 建立服务器到服务器的连接，或者用 JavaScript 建立客户端到服务器的连接。大家可以在这里找到它们。

<details><summary>Original English</summary>
Um





there

 is

 a

 couple

 examples,

 you

 know,

 if





you're

 developer

 yourself,

 feel

 free

 to





try

 these

 out.

 They

 are

 linked

 from

 the





docs

 as

 well.

 These

 are,

 you

 know,

 just





some

 examples

 of

 how

 you

 would

 get





started

 say

 in

 Python

 for

 like

 a

 server





to

 server

 connection

 or

 in

 JavaScript





with

 kind

 of

 a

 client

 to

 server





connection.

 So,

 you

 can

 find

 those

 here.
</details>

另外也推荐 Gemini skills。我们为各类 Gemini API（包括 Live API）都发布了编程智能体技能。与实时音频打交道可能会更具挑战性一些。因此，使用这些智能体技能并将它们安装到你的编程智能体中，能切实帮助引导它们走在正确的方向上，并带来你所期望的结果。

<details><summary>Original English</summary>
Uh

 also

 recommend

 the

 Gemini

 skills.

 So,





we

 have

 published

 coding

 agent

 skills





for

 kind

 of

 all

 of

 the

 Gemini

 APIs





including

 the

 life

 API.

 So,





you

 know,

 real-time

 audio

 working

 with





real-time

 audio

 can

 just

 be

 a

 bit

 more





challenging.

 So,





uh

 using

 these

 agent

 skills

 and

 kind

 of





installing

 them

 in

 your





uh

 you

 know,

 coding

 agents

 can

 really





help

 steer

 them

 sort

 of

 in

 the

 right

 way





and

 give

 you

 sort

 of

 that

 result

 that





you're

 looking

 for.
</details>

### 音乐生成模型 Lyra 3 与 Live Jukebox

最后，我们还有——好的，我们还有一点时间。音乐，同样也是音频，所以我把它放到了这里。我们最近发布了 Lyra 3。是的，它是一个音乐生成模型。不过现在它实际上可以生成带有歌词的音乐。有两个独立的模型：一个是 Lyra 3 Clip，它是一个 30 秒短旋律生成模型；另一个是 Lyra 3 Pro，是完整长度的歌曲生成模型。

<details><summary>Original English</summary>
Um

 lastly,

 we

 have

 Okay,

 we

 have

 a

 bit





of

 time.





So,

 music.

 Uh

 you

 know,

 also

 audio.

 So,





I

 put

 that

 in

 here.

 Uh

 we

 recently





released

 Lyra

 3.





So,

 yeah,

 it's

 it's

 a

 music

 generation





model.

 Um





but

 so,

 it

 it

 now

 actually

 can

 generate





music

 with

 lyrics.

 There's

 two

 separate





models.

 There's

 a

 Lyra

 3

 clip

 which

 is

 a





30-second

 kind

 of

 jingle

 genera-





generation

 model

 and

 then

 a

 Lyra

 3

 Pro





is

 the

 full-length

 uh

 song

 generation





model.
</details>

把所有这些整合在一起，不知道大家是否还记得过去给广播电台打电话点歌的美好旧时光。所以我构建了这样一个名为 Live Jukebox 的应用程序。现在我们可以试用一下，我们实际上给实时 Gemini Live 模型提供了一个工具，用于调用 Lyra 来生成歌曲。让我们看看能否在这里实现。

<details><summary>Original English</summary>
Um

 and

 so,

 I

 you

 know,

 kind

 of

 bringing





everything

 together.

 I

 don't

 know

 if

 you





remember

 the

 good

 old

 days

 when

 you





would

 actually

 call

 the

 radio

 station





and

 wish

 for

 a

 song.





Um

 and

 so,

 I've

 I've

 kind

 of

 built

 this





application





um





called

 Life

 Jukebox.

 And

 so,

 we

 can

 now





try

 it

 out

 where





um

 we

 actually

 give

 the

 the

 real-time





Gemini

 Life

 model





uh

 a

 tool

 to

 then

 generate

 a

 song

 using





Lyra.

 And

 so,

 let's

 see

 if

 we

 can

 if

 we





can

 do

 that

 here.
</details>

“好了，您正在与点唱机 DJ 进行实时连线。太棒了。请问我是和哪位在通话，我们今天打算整出什么样的氛围？是地道的锐舞风格，还是来点别的……”

<details><summary>Original English</summary>
Right

 then,

 you're





live

 on

 air

 with

 the

 jukebox

 DJ.

 What

 an





absolute

 legend.

 Who

 am

 I

 speaking

 to





and

 what

 kind

 of

 vibe

 are

 we

 going

 to





cook

 up

 today?

 Is

 it

 a

 proper

 rave

 style





or

 something

 a

 bit

 more
</details>

>> “我们能来一首关于英国初创圈的德式 Techno 流行歌吗？”

<details><summary>Original English</summary>
>> we

 get

 maybe

 a

 German

 techno

 Schlager





about

 the

 UK

 startup

 scene?
</details>

“关于英国初创圈的德式 Techno 流行歌？朋友，这太有颠覆性了。我太喜欢了。好的，想象一下这个画面：强劲的 Techno 节拍，地道的汉斯·季默风格。”

<details><summary>Original English</summary>
German

 techno

 Schlager

 about

 the

 UK





startup

 scene?

 Mate,

 that

 is





revolutionary.

 I

 love

 it.

 Right,

 picture





this.

 Pounding

 techno

 beat,

 a

 proper





Hans

 Zimmer

 style.
</details>

>> “太棒了。开始吧，就这么整。”

<details><summary>Original English</summary>
>> great.

 Let's

 go.

 Let's

 do

 that.
</details>

“坐稳了，我们马上就好。只是为了确保它绝对是一首爆款神曲：歌词里有没有什么你特别想加入的英国初创圈流行热词或故事？而且你倾向于狂躁有力的能量，还是那种在 Techno 狂热中带点旋律感的东西？”

<details><summary>Original English</summary>
Hold

 on

 tight,

 we're

 almost

 there.

 Just





to

 make

 sure

 it's

 a

 certified

 banger.





Any

 specific

 buzzwords

 or

 stories

 from





the

 UK

 startup

 world

 you

 want

 in

 the





lyrics?

 And

 I'll

 be

 thinking

 manic





energy

 or

 something

 a

 bit

 more

 melodic





within

 that

 techno

 madness.
</details>

>> “狂躁的能量，歌词就给我个惊喜吧。”

<details><summary>Original English</summary>
>> manic

 energy

 and

 surprise

 me

 on

 the





lyrics.
</details>

“没问题，收到。准备好轰炸你的耳膜吧。狂躁的德式 Techno 流行歌，融入英国初创公司特色。正在为你打造一首地道的爆款曲目。来听听看。”

<details><summary>Original English</summary>
All

 right,

 you're

 on.

 Get

 ready

 to

 have





your

 eardrums

 blasted.

 Manic

 German





techno

 Schlager

 with

 a

 British

 startup





twist.

 Cooking

 up

 a

 proper

 banger

 for





you.

 Check

 this

 out.
</details>

好的，我就给大家展示到这里。如果大家不会德语，那很抱歉，不过非常感谢大家。感谢各位。

<details><summary>Original English</summary>
All

 right,

 I'll

 I'll

 leave

 you

 with





that.





If

 you

 don't

 speak

 German,

 sorry,

 but





thanks

 so

 much.

 Appreciate

 y'all.
</details>

完全不用客气。

<details><summary>Original English</summary>
No

 worries

 at
</details>

噢，对了，如果大家想要幻灯片，我可以倒回去。所有链接都在里面。如果这有帮助的话，大家可以直接在那里获取。太棒了，谢谢大家。祝大家享受接下来的会议。也特别感谢我们后方负责音频的朋友们，没有他们这一切都不可能实现。干杯！

<details><summary>Original English</summary>
Oh,

 yeah,

 and

 if

 you

 want

 the

 slides,





I

 can

 just

 rewind.

 There's

 like

 all

 the





links

 in

 there.





If

 that

 If

 that's

 helpful,

 you

 can

 you





can

 just

 grab

 them

 there.





Awesome.

 Thank

 you.





And

 yeah,

 enjoy

 the

 rest

 of

 the





conference.

 And

 big

 thank

 you

 as

 well

 to





our

 friends

 in

 the

 back

 on

 the

 audio,





you

 know,

 wouldn't

 be

 possible

 without





them.

 Cheers.
</details>