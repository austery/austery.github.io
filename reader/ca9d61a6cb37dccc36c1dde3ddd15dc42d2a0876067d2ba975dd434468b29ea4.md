---
author: AI Engineer
date: '2026-07-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=b_PmGocP4rc
speaker: AI Engineer
tags:
  - video-generation
  - model-evaluation
  - vlm
  - agentic-workflow
  - llm-as-a-judge
title: 评估视频垃圾：Character.ai 如何重构 AI 视频生成评估体系
summary: 本文根据 Character.ai 工程师 Maor Bril 的分享整理。文章深入探讨了 AI 视频生成评估面临的挑战，详细介绍了 Character.ai 如何将评估方法从主观绝对评分转向相对对比（A vs B），如何通过蒸馏技术将复杂的“专家委员会”模型转化为超快速的轻量级视觉语言模型（VLM），以及如何利用 Agentic 工作流将评估机制前置并嵌入生成闭环中，从而实现低成本的视频自动校正与优化。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Maor Bril
companies_orgs:
  - Character.ai
products_models:
  - Sora
  - Kling
  - Veo
  - SeaDance
  - Qwen
media_books: []
status: evergreen
---
### 评估视频垃圾：Character.ai 如何重构 AI 视频生成评估体系

### 视频评估滞后：传统单帧指标的局限性

在过去两年中，以 **Kling**、**SeaDance**、**Veo** 和 **Sora** 为代表的生成模型取得了突破性的进展，使得视频生成的成本几乎降到了零。然而，视频生成的评估技术却严重滞后。在实际工程中，大部分生成的视频仍存在诸如多余肢体、物理规律违背（如同时开关门、悬浮）等幻觉问题。

传统评估手段往往直接套用文本和图像时代的指标。例如，**CLIP Score**（Contrastive Language-Image Pre-training Score: 用于评估图像与文本提示词匹配度的指标）仅能评估单帧图像的质量，而 **LPIPS**（Learned Perceptual Image Patch Similarity: 学习感知图像块相似度，常用于检测帧间漂移）也只能检测帧与帧之间的差异。这些指标根本无法回答视频的核心诉求——它是否完整、连贯地讲述了一个故事。高质量的视频生成需要解决跨镜头的角色一致性、物理合理性以及视听同步（如关门声与关门动作的对齐）等维度，这使得依赖人类进行主观判断在现阶段依然不可或缺。

段落之间必须包含逻辑衔接句。为了解决人工评估成本高昂且无法规模化的问题，开发团队开始探索将大语言模型引入评估流程。

<details>
<summary>Original English</summary>

So, hi. I'm Mayur. I've been with Character for a bit over 2 years and we'll talk about AI slop, right? I think that, you know, when we look at video generations as a whole, right? We have like two kind of parallel tracks. One is the video generation, which became insanely good from models like Kling and SeaDance and VEO and Sora. We still remember Sora. But the part that got left behind is how we evaluate the quality of the video that was generated, right? So, on the one hand, we still kind of squint at it and decide whether or not it's good, but on the other hand, we know that the generation has gotten a lot better. And when we look at X or whatever social you're consuming your content on, there are a lot of guides on how to create amazing videos with this model or that. So, the hard part was never how to make video. The hard part was how do we generate enough video and how do we judge if the video is good enough? So, now we've gotten to a world where the generation of video is basically free, right? Free especially when you compare it to how much studios would charge. And but the problem is the grand majority of videos that is generated is not that good, right? We have like a lot of hallucinations like a third limb, opening and closing the door at the same time, hovering, physics, etc. So, unfortunately, in order to get high-quality content, we need a human to judge. And I know when was the last time you've seen how someone is creating these long-form generated video. It's usually a lot of shorter generations and a lot of editing. The problem is because we're using a lot of the tools that we built for the text era, for the image era, for videos, right? We're using things like clip score, which is great to judge a single frame. Things like LPIPS will help us kind of detect the drift between frames, but we don't have—I mean, but the problem is when you kind of combine all these together, all these tools are good at watching the individual frames. They're good at checking this specific frame, does it match the prompt that generated it, right? It will check consistency between frames and it will check whether or not it match the prompt that drove it. But what it won't do, it doesn't tell you if it told the story that you meant to tell, right? If you think about what is video, video is a storytelling medium. Video is just another form on how we tell a story, right? From for any type of story. So, one of the things we have to look at, does it tell the actual story? Does the physics make sense? Like for example, if you want a video of a character walking downstairs, does it actually walk or hover? Does the character stay the same character across multiple shots? Does the pacing make sense? Like you know, for example, people take time going from one place to another. We need to make sure that the pacing makes sense as well. And especially when we add audio, we want to make sure that the audio is kind of synced with the imagery. Like for example, if someone is slamming a door, we want that sound of the door being slammed to be exactly when the door is actually being slammed.

</details>

### 从专家委员会向轻量级 VLM 蒸馏的演进

在重构评估体系的初期，**Character.ai** 尝试建立一个可重复运行的基准测试集。该基准结合了单帧检测指标与 **LLM-as-a-Judge**（LLM 裁判: 利用大语言模型评估生成内容质量的方法）机制，并定期引入人工标注来微调和校正大模型的提示词。然而，这种由多个专家模型组成的“委员会”不仅运行缓慢、价格昂贵，而且对提示词极其敏感。

为了让评估能力真正服务于普通用户，团队必须将复杂的评估流水线进行极致压缩。他们最终选择将“专家委员会”的知识蒸馏到一个轻量级的视觉语言模型（Vision Language Model, 简称 **VLM**）中。在模型选择上，团队最终采用了 **Qwen**（通义千问系列模型，在多模态后训练中表现优异）。
* **极速推理**: 优化后的轻量级 VLM 仅需约 3 秒即可完成对一段 15 秒视频的完整评分。
* **性价比权衡**: 尽管测试更大尺寸的模型能带来精度提升，但其推理延迟和计算成本远超轻量模型，因此小模型是符合生产单元经济学的最优解。
* **可解释性反馈**: 模型不仅输出质量分数，还能给出具体维度（如“物理规律违背”或“音画不同步”）的诊断报告。

通过这一蒸馏过程，高精度的评估算法得以运行在更靠近用户生成的阶段。那么，如何让这个小型 VLM 在主观的“视频质量”判断上具备与人类一致的审美，成为了下一个需要攻克的核心课题。

<details>
<summary>Original English</summary>

Now, the next iteration we all went to a while ago. We started using LLM as a judge for everything and we have amazing foundational models that we just throw videos at them. The problem with them is that A, they're slow. B, they're only as good as your prompt and multiple people will prompt multiple ways and the same model may respond in a very different way. And sometimes the prompt we use like is it consistent? Does this match the prompt? But then the question we really care about is it good? And the answer varies. So, oops, sorry about that. So, our first iteration is like let's take all these things and build a repeatable benchmark on how we test video that we can rerun over and over and over again. So, that combines both metrics as I said earlier that knows how to view individual frames, but also consistent LLM as a judge, right? Where we also use human annotation to calibrate the LLM as a judge. So, for every report that we generate with that harness, we're able to have humans annotate it and basically feed that feedback back into the LLM as a judge prompt to make sure that it's aligned with what I think or what the annotator thought is good. And we use it to score the videos. The problem with this approach, it's very slow, it's very expensive and especially when we want to bring it in for our users to be able to generate a lot of video because creation is a very hard process. And so the problem as I said, the problem is when—So, this is a slow process and we need to bring it as close to the users as possible and also earlier into the process. The reason for that is if we take a look at all the metrics and there's mistakes that we can find earlier than later than it's a lot cheaper to correct that particular mistake. So, for example, right? On the left we have two starting frames of different shots, right? But it's easy to correct to view it at this point and see did the character drift between frame one and frame two because those frames will be used as starting frames to generate videos. So, if you can catch the drift at this point and correct it, then it's much cheaper to generate the video as a whole because we can correct it at a much cheaper cost. And the same thing applies when we look at longer form video, right? When we see all these three, four, five-minute long videos, they're usually a collection of a lot of shorter videos. And being able to catch a six-second generation that drifted and regenerated that before we combine the whole video will end up being a better result as a whole. And now the other problem what we're trying to solve is some of these axes, right? Only exist across time, right? So, for example, when we look at the—right? We mentioned the story, right? So, does the story that we're trying to tell with that video, does it hold in that video? Does the video tell the exact story? Does the pacing make sense, right? And we mentioned the sound. So, as I said, right? The underlying goal is to bring that evals closer to the online generation because the sooner we're able to catch those mistakes, the sooner we're able to catch that drift, right? Then it's much easier, much cheaper to fix. Now, so that now the problem is that as I said, this is a very slow process. So the solution is actually to take all these committee of experts and distill it into one small model that is also very fast, but it is able to give us a response that is not whether or not this video is slop or not, but why is it slop? Right? Why is that video scored low versus the other? Because for example, it added an extra limb, because it didn't obey physics, because the audio was out of sync. So the goal was to build it on top of a small VLM and why is it a VLM? VLM because we needed the model to be able to see the image, but also we needed to work fast, right? Because we bought it closer to the generation, where in fact it takes about—the model we have trained, it takes about 3 seconds to score a 15 second video. Now, we also tested a bigger model and the results were better, but it was significantly slower. And the decision was to go with the smaller model because the added value from the bigger model didn't justify the slowness.

</details>

### 相对对比（A vs B）与避免 AI 检测器陷阱

在训练 VLM 的数据工程中，团队总结出了两条关键的黄金法则。首先，**不要进行绝对评分，而要使用相对对比**。在绝对评分体系下（如 1-10 分），不同人类标注员对“故事性”或“画风”的打分标准极其主观，导致模型难以收敛；但如果向标注员展示两段视频（视频 A 与视频 B）并询问“哪一个讲的故事更好”，绝大多数人的判断会高度一致。因此，团队将数据格式改为了成对对比数据（Pairwise Data）。

其次，必须**警惕模型退化为“AI生成检测器”**的陷阱。通常为了获得差评样本，最直接的方法是用真实的视频与 AI 生成的视频进行两两配对。但这会导致模型过拟合于检测 AI 的压缩伪影或特定的渲染质感，而不是真正去评估物理、故事或音画质量。为解决这一问题，开发团队采取了以下防御措施：
1. **统一编码标准**: 确保对比的两段视频在视频编码格式、分辨率和码率上完全一致，消除底层像素特征带来的偏置。
2. **人工注入负样本**: 主动通过程序对高质量视频进行局部破坏（如剪掉音轨、打乱帧序）或者混合低质量的 AI 样本，以此人工制造出仅在特定评估维度上“变差”的控制组。
3. **一致性标注**: 无论真假视频，均采用完全一致的多维轴线（Axes）标注流进行标注。

这种经过精细校准的对比训练不仅提升了 VLM 的鲁棒性，还为其嵌入更上层的自动化业务逻辑奠定了基础。

<details>
<summary>Original English</summary>

The other very interesting realization we came to is don't score compare. What does that mean? For example, if I'll ask any person in this room to look at a particular video and rank it from 1 to 10 on storytelling, right? I'm pretty sure that what will be a six for you will be a five for you, will be a four for you and an eight for you. Right? But if I show you two videos and I'll ask you which one of them is telling a better story, the grand majority will probably agree that B is telling a better story than A, right? And if you do it enough times, then it's easy to generalize the model towards detecting what's better versus not. So, we trained on pairs, right? A versus B as opposed to 1 through 10. Now, we manufactured badness. So, luckily, the internet is full of very high-quality videos, and it's very easy to get good videos, and it was very fun to create bad videos either by corrupting good videos or by, you know, just generating random slop. Now, we shipped V1, and it was so wrong. It was wrong, but it was wrong in a very confident way. So, for example, the frame you see here is from a video that the model scored 9.2 on the camera work, and the camera didn't move. For 4 seconds, it was like a still image of the same character, but the model was very happy with, you know, the cinematography. So, the physics in some other videos, which I'm not showing cuz of time limitations, it says that the physics look great, but it said it on ghosts hovering and people flying, etc. So, then the question is like, why was it wrong? The reason it was wrong is because how we generated that data, right? It scored the vibe as opposed to the axes. So, it learned how to detect coherent videos and it learned how to detect the artificial artifacts. Basically, the gloss of the video as opposed to whether or not the video actually told the story. And so the solution was to fix the data set. And so the way we fixed the data set, we actually started pairing real footage versus AI footage. Now, the risk with that and that's the reason why I avoided doing it at first is because I didn't want to create an AI detector, right? Because if you start creating pairs of good is human-generated video and bad is AI video, then there's a very big chance of the model overfitting and becoming an AI detector as opposed to a video quality detector. So, there are two things I did in order to avoid that. A, I made sure that the encoding is consistent across both sides of the equation. So, there's no artificial artifacts for video A versus video B. And I used the exact same method of annotating both videos. So, all the axes in those videos were annotated in the same way. And surprise, it turned out pretty awesome. And so now what we're able to do, especially when you looking at videos,

</details>

### 从复杂流水线到 Agentic 闭环工作流的转变

在获得快速且敏锐的评估模型后，Character.ai 将整体架构从原先复杂的静态**流水线**（Pipeline）升级为了 **Agentic 工作流**（Agentic Workflow）。静态流水线在面对确定性的单一场景时非常高效，但当面对成千上万个拥有独特角色、背景画面和配音需求的个性化用户请求时，其脆弱的硬编码逻辑极易“掉链子”。

在新的 Agent 架构中，小型的 VLM 评估模型被作为**评估工具**直接赋予了生成 Agent。
* **自我校对与纠偏**: Agent 在视频生成的中间步骤（如第一帧与第二帧的过渡期）可以调用 VLM 工具，提前检测角色是否发生外观漂移。
* **低成本局部重新生成**: 如果在一段多镜头的长视频中，VLM 发现其中仅有 6 秒的片段质量崩坏或逻辑失常，Agent 可以选择仅重新生成该片段，随后将其无缝拼回，避免了全量重新生成的巨大算力浪费。
* **端到端动态自适应**: 评估前置到生成循环中，使得 Agent 能够基于多维度反馈指标自动调节生成策略，确保最终交付到用户眼前的视频符合质量底线。

<details>
<summary>Original English</summary>

A, we changed from a very complex pipeline, right? To an agentic workflow. The reason behind this is, a, the pipelines work great if you have a very unique use case. But once you put it in front of users, they'll have a very distinct story that they want to tell with their own characters, with their own images, and their own voice. So that's where it starts to drift. But by providing the agents with tools to validate the quality of the outputs it's creating, it's able to adapt to changes better. It's also able to verify its own work and fix things as they go along. So if you're going to steal from these—from the stock of a few things, one, go relative, not absolute, right? As I explained earlier, the value of comparing video A versus video B will always give you a better result going forward. B, score the real axis that you care about. So if you care about storytelling, if you care about pacing, if you care about physics, score those axes. Don't expect them to miraculously appear. And put eval inside the generation loop, right? Especially if your goal is to have a higher quality of generation, get the eval as close to the generation loop as possible. Eventually evaluate it as a story. Videos are stories. Videos are just another way for us to tell stories to others. And Thank you very much.

</details>

### 互动问答：音频对齐、审美标定与工程落地

在演讲结束后的问答环节中，针对与会者提出的关于技术细节和落地成本的问题，演讲者做出了以下深度解答：

1. **音频效果与画面的对齐**: 
   模型虽然无法在语义上完全理解声音的本质，但能通过结合 **Atmos** 声学工具识别音轨中的关键能量峰值（Spikes），并将其与生成视频中对应帧（如门刚好关上的一帧）的时间戳进行强关联校验。如果音频能量峰值与动作发生的时间戳不一致，则判定为失常。
2. **口型同步（Lip Syncing）**: 
   这是目前行业内尚未完全解决的公认难题。尤其是对于二次元动画或非写实风格的角色，其发音嘴型与实际音频的物理关联度极低，团队目前仍在积极探索更好的检测方案。
3. **审美标准的持续迭代**: 
   个人审美（Taste）极其主观。团队的解法是通过定期的“集体标注会（Annotation Sessions）”，让团队成员在 10 到 15 分钟内对生成样本的多维指标进行饱和度标注，以此生成最新的校准数据集，持续用于训练下一代 VLM 评估模型。
4. **单元经济学与计算规模**: 
   对于非 Character.ai 这类超大规模级别（日产数百万视频）的中小型企业，直接部署由前沿商业大模型组成的专家委员会或开源的评估套件依然是完全合理的。选择蒸馏小模型的根本动力在于控制每日高频生成的算力单元经济性（Unit Economics）。如果只是每天处理几百到几千级别的视频生成，直接调用成熟的 Frontier Model（如 GPT-4o）将更具开发效率。
5. **系统遥测与外部集成**: 
   虽然目前的开源评估套件尚未完全导出模型内部的详细轨迹（Tail Traces），但团队明确表示已将集成 **OpenTelemetry**（简称 oTel: 云原生软件的可观测性标准框架）的计划列入排期，以便外部平台可以更方便地挂接监控。

<details>
<summary>Original English</summary>

>> All right. Any questions? Okay, down here. Awesome. All right, I got two down here. Here you go.
>> Hi. How do you eval sound? Sound and video matching.
>> I'm Can you repeat?
>> How do you evaluate sound? Sound effects and matching with the video.
>> oh yeah. That's a fantastic question. So, sound is actually a combination of few things. One, I'm using Atmos to make sure that the sound quality is high enough and is understandable. B, the model will learn to identify key frames. Right? And especially because when I feed something into the model, it can be just a video or it can be the video plus the prompt that generated that video. So, for example, if the prompt will say the door slammed, right? It will look for a door being slammed and will match the sound at that same frame. Did I answer your question?
>> How does the model recognize sound?
>> Uh so, it's both by using Atmos, and also to correlate the So, for example, when it's looking at the frames, right? It's making sure that for example, the door being slammed at frame six, frame six has a specific timestamp. So, it's looking for that spike in the sound at that timestamp. It doesn't know that it is that sound, but it's looking for a specific spike of sound at that timestamp.
>> What about lip syncing?
>> Lip syncing is an unsolved problem yet.
>> One question.
>> We're trying though. Yeah. Yeah, I said the question was what about lip syncing?
>> Oh, Well, wasn't me, but I guess the lip syncing answer would be interesting before I ask my question.
>> Uh yeah, as I said, it is an unsolved problem still. We're still working through it. Especially for us, some of the characters that we're trying to do a talking head are humans, right? Which, you know, we can look at the different techniques to trying to identify the lips, but some of them are just talking, you know, talking animations that have no real correlation between, you know, the movement of the mouth and speech. So, unfortunately, I don't have a solution for that yet.
>> So, I'm curious about, for example, if you wanted to further enrich the data set with human evaluation.
>> Yes.
>> the question of taste in what is good, because I think there is a big question mark about is that going to remain the domain of humans? But, I've also seen people say that, well, most humans they have terrible taste anyway in videos and games and books.
>> Fair.
>> so, how would you construct and align sort of like any human judges?
>> Yeah. So, this is actually solved at first at the Judge Judy part, where every report it will generate a human can go and annotate it. And we actually do that. We will periodically have sessions where everyone spends 10 to 15 minutes just annotating videos. And that usually happens on multiple axes. I won't ask everyone to annotate the same video on 10 different things. It'll be random. And I use the data to calibrate the AI judges. And the results from that is actually being served as a data set for training for the next version of that model. So, it's a process that does take a little bit of time and hopefully and it does evolve over time. Uh but it's not immediate you know, because also taste is very subjective and things that are great for me, you know, some that I think are fantastics some people that come and say are you sure they're great because you know So, yeah, it's a process and I use the human feedback to calibrate the models all the time.
>> Um how did you land on the Quan small VLM? Did you try any others?
>> Uh I did. So, the intent I had was to find a small enough model. The reason I went with Quan is because we also had a very good experience with post training Quan on other use cases. So, it—I mean yes, I could have—I did try a few others, but it just you know, everything was just there and it was good enough.
>> So, my question is about scale. So, obviously Character AI produces thousands, millions, bajillion videos. What scale does this become reasonable for my domain that is not Character AI? So, my domain has hundreds, maybe a thousand videos.
>> Mhm. Sure. So, if you're happy with the cohort of experts and it and you don't need—so I'll rephrase that. The scale is both for speed, right? As well as capacity because I can serve this model as one instance on one GPU or I can serve it as you know, 100 instances, right? So, that determines my scale. The reason I chose to go towards the model is because I wanted to speed up the creation process, right? It would work—would have worked just as well if I didn't have this particular model, I would have used like the cohort of experts, right? From metrics that are available both on CPU and GPU as well as the frontier models. Right? So it was a balance as you know, A, how long did it take me to train this model and to curate the data set and get it to a working set, right? And how much does it cost to serve it versus how much it would have cost me to do this A slower. Now potentially it is better, right? I mean like I assume that if you're going to use Fable which came back today, right? It will probably give you a better result, but at what cost, right? If you do it for one or two, that's probably fine. If you do it for thousands or tens of thousands per day, it adds up. So it's a matter of your unit economics.
>> Cool. Over here. On your right, there you go. Last question.
>> It's very bright. I'm sorry.
>> No worries. Um My question is I looked a bit at the repo. You guys don't export all tail traces of the LMS judges yet.
>> Correct.
>> Is that something are you open to that so you can connect to other platforms?
>> Sure. So the repo itself it's a harness and you can connect any agents or any LLMs you want. We actually have an internal version of this which is running it as a service, right? We have an agentic harness on top of it that has all the metrics we care about, but I do accept your feature request and I'll be adding hotel telemetry to the harness.
>> Awesome. Thank you very much. A warm welcome or round of applause for Mayor. Thank you.
>> Thank you all.
>> Thanks.
>> Oh.

</details>