---
author: AI Engineer
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=IEF842ZEU5A
speaker: AI Engineer
tags:
  - voice-processing
  - low-latency-ai
  - generative-ai
  - contact-center-ai
  - audio-analytics
title: AI驱动的联络中心革新：从杂乱音频到结构化洞察
summary: 本次分享深入探讨了联络中心在处理客户交互数据时面临的严峻挑战，特别是语音数据的高度非结构化和员工高压工作环境。演讲者提出了一种创新的低延迟AI架构，该架构能够实时捕获、转录、分析复杂的音频流，并从中提取结构化的业务洞察。通过优化语音捕获、提升语音转文本准确性、精细化生成式AI应用以及无缝数据同步，该系统显著减少了联络中心运营中的‘通话后工作’（ACW）时间，提升了数据质量，降低了员工压力，并为预测性人员配置、AI辅导和客户骚扰检测等未来应用奠定了基础。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Fujitsu
products_models: []
media_books: []
status: evergreen
---
### 联络中心困境：高压工作流与低效沟通

欢迎来到 AI Engineer 2026 在线论坛。我是 Deep Singh，在富士通北美地区领导新兴数据技术与 AI 架构的各项计划。今天，我将带大家深入探讨一个我们近期在联络中心遇到的，具体而极具影响力的工程挑战——如何从嘈杂的音频流中进行低延迟的智能信息提取。当我们在讨论**生成式AI**（Generative AI: 一种能够生成新内容（如文本、图像、音频等）的AI技术）时，我们常常聚焦于清晰的文本输入。然而，在现实世界，尤其是在客户服务或联络中心领域，数据并非一开始就是整洁的文本。它往往是杂乱的、重叠的，有时带有强烈的情感色彩，甚至可能包含多通道的音频流。今天，我们将探索构建一个能够捕获音频、以超低延迟进行处理，并利用生成式AI从中提取结构化、可操作的业务洞察所需的技术架构。

本次分享的路线图包括：首先，我们将阐述当前面临的挑战；理解现代联络中心的运营现实和集约化人力瓶颈，从而明白这项工程的重要性。其次，我们将深入分析解决方案和我们构建的高层架构，将其分解为四个关键组件，详细说明如何通过高级**摘要工作流**（Summarization Workflows: 利用AI技术自动为长文本或对话生成简短、概括性内容的过程）将原始音频转化为结构化 JSON 数据。第三，我们将审视这些技术实现如何转化为实际的投资回报（ROI）和运营影响。最后，我们将讨论未来的发展蓝图，坦诚当前面临的技术工程瓶颈，以及我们计划如何推动这项技术发展。

为了构建一个出色的解决方案，我们首先需要深刻理解问题本身。让我们审视联络中心运营的现状。联络中心是客户体验的第一线，但从结构上看，它们正承受着巨大的压力。行业数据显示，超过50%的联络中心将招聘、培训和生产力视为其最关键的障碍。这是因为这项工作极其困难。当我们分析员工选择离开的原因时，高压力是首要因素。操作员不仅要处理复杂客户的情绪，还要熟练导航多个客户数据平台或CRM系统，并同时完美记录所有信息。这导致了巨大的员工流失问题。我们陷入了一个负面循环：人员不足导致剩余操作员压力增大，进而导致高离职率，最终又加剧了人员不足。要打破这个循环，我们不能仅仅招聘更多人，而是必须从根本上通过工程手段消除工作流中的压力。

在这个工作流中，最明显且效率低下的环节是所谓的“**通话后工作**”（After Call Work, ACW），也就是我们即将讨论的内容。根据我们的基线研究，一次典型的联络中心通话平均时长约为6.5分钟。然而，平均的通话后处理时间，包括操作员记录笔记、总结通话内容和选择处理代码，却需要将近6.3分钟。这意味着，我们花费了几乎与通话本身同等长的时间进行管理性数据录入。此外，由于**摘要**（Summarization: 指提炼信息核心要点的过程）高度依赖于操作员的个人记忆和写作技巧，数据质量极不稳定。

我们核心的工程使命非常明确：利用AI来解决ACW问题。如果我们能够实现摘要和数据提取的自动化，理论上我们可以将通话后处理时间减少约50%甚至更多。这将促使企业将重心从仅仅处理呼叫转移到真正分析客户的“**客户之声**”（Voice of the Customer: 指企业收集和分析客户反馈、意见和行为，以了解客户需求和满意度的过程）来促进业务增长。

<details>
<summary>Original English</summary>

Right.
 Hello
 everyone.
 Welcome
 to
 the
 AI


engineer
 2026
 online
 track.
 Um
 good


morning,
 good
 afternoon,
 good
 evening


depending
 upon
 your
 time
 zone.
 My
 name


is
 Deep
 Singh
 and
 I
 lead
 the
 initiatives


in
 the
 emerging
 data
 technologies
 and
 AI


architecture
 at
 Fujitsu
 North
 America.


Um
 and
 today
 I
 will
 be
 uh
 giving
 you
 or


maybe
 provide
 you
 a
 deep
 dive
 into
 a


very
 specific
 but
 a
 very
 highly


impactful
 engineering
 challenge
 uh
 which


we
 have
 encountered
 in
 our
 uh
 contact


center.
 So
 with
 that,
 let
 me
 just
 quickly


share
 my
 screen
 and
 get
 this
 going.


Right.
 So
 um


um
 this
 is
 the
 topic
 of
 the
 discussion


voice
 opsy
 low
 latency
 intelligence


extraction
 from
 uh
 messy
 audio
 streams.


Uh
 when
 we
 talk
 about
 you
 know


generative
 AI
 we
 often
 you
 know
 focus
 on


uh
 clean
 text
 inputs.
 But
 if
 you
 go
 into


the
 real
 world
 specifically
 in
 the


customer
 service
 or
 or
 maybe
 contact


centers
 specifically
 um
 the
 data
 does


not
 start
 as
 a
 clean
 text
 right
 it


starts
 as
 messy
 quite
 overlapping


um
 sometimes
 emotionally
 charged
 and
 and


it
 it
 may
 have
 multi-
 channelannel
 audio


streams
 also
 within
 that
 right
 and
 and


today
 we
 will
 explore
 the
 technical


architecture
 which
 is
 required
 ired
 to


capture
 that
 audio,
 process
 it
 with


ultra
 low
 latency
 and
 use
 the
 generative


AI
 to
 extract
 structured
 actionable
 uh


business
 intelligence
 out
 of
 it.
 So
 with


that,
 let's
 get
 started
 with
 this.


So
 here
 is
 our
 road
 map
 for
 the
 next
 25


minutes.
 Um
 first
 we
 will
 stage
 the
 um


um
 stage
 with
 what
 the
 current


challenges
 are.
 Uh
 we
 have
 to
 understand


the
 operational
 realities
 and
 the


intense
 human
 bottlenecks
 in
 in
 the


modern
 contact
 centers
 to
 understand
 why


this
 engineering
 matters.
 Uh
 second
 we


will
 walk
 through
 the
 solution
 which
 is


provided.
 I
 will
 break
 down
 our


highlevel
 architecture
 into
 four
 key


components.


um
 detailing,
 how
 we
 move
 from
 raw
 audio


to
 a
 structured
 JSON
 using
 advanced


summarization
 workflows.


Thirdly,
 we
 will
 look
 at
 the
 key


outcomes
 specifically,
 like
 how
 these


technical
 implementations
 they
 translate


into
 hard
 ROI
 and
 operational
 impacts.


And
 finally,
 we
 will
 discuss
 the
 um
 road


map
 ahead
 and
 and
 being
 transparent


about
 the
 current
 tech
 uh
 engineering


constraints
 which
 we
 face
 uh
 now
 and


then
 and
 where
 we
 are
 taking
 this


technology
 and
 the
 road
 map
 ahead.


So
 to
 engineer
 a
 great
 solution,
 we
 first


need
 to
 deeply
 understand
 the
 problem.


So
 let's
 look
 at
 the
 current
 state
 of


the
 contact
 center
 operations.


So
 contact
 centers
 they
 are
 the
 front


lines
 of
 the
 customer
 experiences
 but


structurally
 they
 are
 breaking
 under
 the


pressure.
 If
 we
 look
 at
 the
 industry


data
 um
 over
 50%
 of
 the
 contact
 centers


they
 identify


uh
 hiring,
 training
 and
 productivity
 as


their
 most
 critical
 barriers.
 Why?


because
 the
 job
 is
 incredibly
 difficult.


When
 we
 analyze
 the
 reasons
 why
 the


operators
 they
 leave
 for
 the
 other


professions,
 high
 stress
 is
 the
 number


one
 factor
 as
 part
 of
 it.
 Now,
 operators


are
 expected
 to
 handle
 complex
 customer


emotions,
 navigate
 the
 um
 multiple
 uh


customer
 data
 platforms
 or
 the
 CRM


systems
 involved
 into
 it
 and
 and
 also


document
 everything
 perfectly.
 So
 if
 you


think
 about
 this,
 this
 leads
 to
 a


massive
 retention
 problem,
 right?
 uh
 we


are
 caught
 in
 a
 negative
 spiral
 um
 where


understaffing
 leads
 to
 higher
 stress
 for


the
 remaining
 operators


um
 which
 leads
 to
 a
 high
 turnover
 and
 uh


that
 ultimately
 implies
 to
 more


understaffing,
 right?
 So
 to
 break
 this


cycle,
 we
 just


um
 cannot
 hire
 more
 people.
 We
 have
 to


fundamentally
 engineer
 the
 stress
 out
 of


the
 workflow.


And
 the
 most
 glaring
 inefficiency
 in


this
 workflow
 is
 something
 called
 um


after
 call
 workflow
 or
 ACW,


uh
 which
 we
 are
 going
 to
 discuss
 as
 part


of
 this
 slide.
 Um
 according
 to
 our


baseline
 studies,
 the
 average
 contact


center
 call,
 it
 typically
 last
 about
 like


6.5
 minutes.
 However,
 the
 average


post-processing
 time
 where
 the
 operator


types
 up
 the
 nodes,
 summarizes
 the
 call


and
 selects
 the
 disposition
 codes,
 it
 it


takes
 like
 almost
 6.3
 minutes.
 So,
 this


is
 nearly
 like
 1
 is
 to
 1
 ratio
 we
 are


talking
 about.
 Um
 and
 and
 this
 also


implies
 operators
 are
 spending
 almost
 as


much
 time
 doing
 administrative
 data


entry
 as
 they
 are
 actually
 talking
 to


the
 customers.
 Um
 furthermore,
 because


the
 summarization
 relies
 on
 an


individual
 operator's
 memory
 and
 the


writing
 skills,
 the
 data
 quality
 is


highly
 inconsistent.


Um
 our
 core
 engineering
 mission
 here
 was


clear,
 like
 use
 AI
 to
 target
 the
 after


call
 work,
 which
 is
 ACW.
 Um
 if
 we
 can


mechanize
 the
 summarization
 and
 the
 data


extraction,
 uh
 theoretically,
 we
 can


reduce
 the
 post
 processing
 time
 um


almost
 by
 50%
 or
 even
 more.
 And
 and
 this


shifts
 the
 enterprise,
 you
 know,
 focus


from
 merely
 just
 handling
 the
 calls
 to


actually,
 you
 know,
 analyzing
 the
 voice


of
 the
 customers
 for
 the
 business
 growth


which
 we
 are
 looking
 out
 every
 now
 and


then.
</details>

### 技术解决方案：低延迟AI管道
我们如何实现这种转变？让我们深入研究我们为解决此问题而构建的技术解决方案和架构。我们设计了一个四阶段的低延迟管道，可在最少的人工干预下，将对话音频转化为结构化的业务智能。

这个过程始于**语音捕获**（Voice Capture: 捕获原始音频数据的过程），即接入电话系统以提取原始、高保真的音频流。接着，音频流进入我们的**语音转文本引擎**（Speech-to-Text Engine, STT），该引擎负责高精度的转录。然后是系统的核心——**生成式AI引擎**，这是我们进行意图识别和摘要处理等繁重工作的关键部分。最后是**客户数据同步层**，它将AI洞察转化为API调用，自动更新客户数据或CRM数据。

让我们详细了解这些组件的底层工程实现。

#### 语音捕获：数据纯净是基石

在AI领域，一条基本法则便是“垃圾进，垃圾出”（Garbage in, garbage out）。如果音频输入存在缺陷，**LLM**（Large Language Model: 大型语言模型，一类能够理解和生成人类语言的AI模型）后续就可能产生“**幻觉**”（Hallucination: AI模型生成不准确或虚假信息的现象）。我们进行实时音频输入，通过应用**降噪滤波器**（Noise Filters: 用于去除音频信号中不希望存在的噪声的算法或技术）来过滤掉背景杂谈或任何会产生衰减的干扰。音频电平的**归一化**（Normalization: 将音频信号的幅度调整到特定范围内的过程）对我们至关重要。

至关重要的是，我们必须执行**声道映射**（Channel Mapping: 将多声道音频（如立体声）分离成独立声道并分配给特定发言者（如客服代表或客户）的过程）。我们必须将立体声音频分割开，将客服代表隔离在一个声道（例如左声道），将客户隔离在另一个声道（例如右声道）。如果我们将其混合成单个单声道音轨，相互重叠，AI将难以辨别谁说了什么，从而破坏整个下游摘要的准确性。因此，确保声道映射的完整性，并区分谁在说什么至关重要。最后，我们应用了一个**安全层**，因为有时音频流可能包含信用卡号、密码或其他任何**个人身份信息**（Personally Identifiable Information, PII）。我们采用**缓冲区管理**（Buffer Management: 管理数据在内存中的存储和流动）和早期**PII屏蔽技术**（PII Masking: 在数据进入处理流程的早期阶段，对敏感个人信息进行匿名化或移除的技术），以确保敏感数据在数据流向后续处理阶段（如LLM内存）时，绝不会触及其内存库。

#### 语音转文本：追求高精度转录

接下来，音频进入**语音转文本引擎**，供生成式AI或LLM进行有效的数据摘要或响应生成。我们发现，语音转文本（STT）的准确率必须高于90%。我们利用先进的**声学模型**（Acoustic Modeling: 语音识别中，将声学信号映射到语音单元（如音素）的模型）来匹配**音素**（Phonemes: 语言中最小的语音单位）并过滤掉任何区域性方言。然后，我们利用特定领域的词典来应用语言逻辑。例如，如果处理的是一位保险代理人的通话，STT引擎需要区分“term life”（定期寿险）和“turn”（回合/轮次）。这两个词发音非常接近，但它们之间必须有明确的区别。最后，**后处理**（Post-processing: 对STT结果进行进一步优化，如添加标点、纠正格式等）同样至关重要。我们使用**逆文本标准化**（Inverse Text Normalization, ITN）和**自动标点**（Auto-punctuation）。例如，如果客户说“五千美元”（$5,000），STT引擎必须将其输出为数字形式。这种数值格式极大地提高了LLM在后续阶段提取实体的能力。

#### 生成式AI核心：结构化与可信赖的智能提取

现在我们到达了**生成式AI核心**。我们并非简单地将原始转录稿丢给LLM，而是要求它进行摘要。我们采用了一种高度**协同的方法**（Orchestrated Approach: 指通过精心设计和协调多个AI模型或组件来完成复杂任务的方法）。在我们的**编排层**（Orchestration Layer: 负责协调和管理AI模型之间交互的组件），我们使用特定的**提示模板**（Prompt Templates: 预先设计的文本结构，用于指导LLM生成特定格式或内容的输出）。我们的设置表明，如果仅仅要求LLM总结一次通话，它会输出一个杂乱的叙述段落。因此，我们使用**少样本学习**（Few-shot Learning: 一种机器学习方法，模型仅需少量示例即可学习新任务）的技巧来指导LLM输出分离的**要点列表**（Bullet Points: 用于表示列表项的符号），一个列表用于客户咨询，另一个列表用于操作员的操作。

接下来是**推理层**（Reasoning Layer: AI模型进行逻辑分析、判断和决策的部分）。在这里，我们提取意图。我们为LLM提供一个预定义的客户**通话原因列表**（Call Reasons: 如取消、新申请、索赔状态等），并指示它对转录稿进行分类，并说明选择该特定分类的原因。

最后是**信任层**（Trust Layer: 确保AI输出的准确性、可靠性和安全性）。在此层，我们应用**令牌优化**（Token Optimization: 优化输入给LLM的文本量，以降低成本和延迟）来保持低延迟，并运行**自动化幻觉检查**（Automated Hallucination Checks: 自动检测并纠正AI生成内容中不准确之处的机制），以确保生成的摘要严格基于转录稿。

#### 客户数据同步：无缝对接业务系统

最后一个技术障碍是将这些优美的（结构化）数据反馈给业务部门。我们的**API网关**（API Gateway: 充当API的入口点，负责请求路由、协议转换、安全检查等）充当**模式映射器**（Schema Mapper: 将一种数据结构映射到另一种数据结构）。它接收LLM输出的JSON，并将诸如客户意图或解决状态等字段，直接映射到公司CRM系统或我们通过REST API布局的任何客户数据中的相应字段。

我们并未完全移除人工。我们在中间设置了一个**验证步骤**。操作员会看到AI生成的摘要自动填充在屏幕上。他们进行快速的视觉字段验证，根据需要进行一些小编辑，然后点击确认。同时，这些结构化数据会流入我们的**业务智能模型**（Business Intelligence Models: 用于分析和呈现业务数据的模型），汇总客户的“声音”数据用于管理仪表板，并自动标记新FAQ数据条目的候选。

<details>
<summary>Original English</summary>

So
 how
 do
 we
 engineer
 that
 shift?
 Let's


deep
 dive
 into
 the
 technical
 solution


and
 the
 architecture
 we
 built
 to
 solve


this.
 Um,


so
 we
 designed
 a
 four
 stage
 low
 latency


pipeline
 to
 transform
 the
 conversational


audio
 into
 a
 structured
 business


intelligence


um
 with
 minimal
 human
 intervention
 and


it
 starts
 with
 voice
 capture,
 which
 is


tapping
 into
 the
 telephon
 system
 to


extract
 raw,
 highfidelity
 audio
 streams


and
 that
 flows
 goes
 into
 our
 speechtoext


engine,
 ST,
 uh,
 which
 is
 responsible
 for


high
 accuracy
 transcription.


Um
 next
 is
 the
 brain
 of
 the
 system,
 the


generative
 AI
 core.
 This
 is
 where
 we
 do


the
 heavy
 lifting
 of
 the
 intent


recognition
 and
 summarization.


And
 finally,
 the
 customer
 data
 sync


layer,
 which
 translates
 those
 AI
 insights


into
 API
 calls
 to
 update
 the
 uh
 uh


customer
 data
 or
 CRM
 data
 automatically.


Um
 let's
 look
 at
 the
 engineering


under
 the
 hood
 for
 each
 of
 these
 components
 in


detail.


So
 the
 first
 component
 is
 the
 voice


capture
 in
 AI.
 Um
 the
 typical
 rule
 is


garbage
 in
 equals
 garbage
 out.
 So
 if


your
 audio
 intake
 is
 flawed,
 the
 LLM


will
 hallucinate
 later
 on.
 Um
 we
 do


realtime
 uh
 audio
 intake.
 So
 applying


noise
 filters
 to
 strip
 out
 the
 uh
 back


office
 chatter
 or
 um,
 you
 know,
 anything


of
 those
 sort
 which
 is
 creating
 an


attenuation


is
 important
 and
 normalize
 the
 audio


level
 is
 very,
 very,
 very
 important
 for


us.
 Crucially,
 if
 we
 perform
 these


channel
 mapping,
 uh,
 we
 absolutely
 must


split
 split
 the
 uh
 stereo
 audio
 to


isolate
 the
 agent
 on
 one
 channel,
 say
 on


the
 very
 left
 and
 the
 customer
 on
 the


other
 side,
 which
 is
 the
 very
 right.


Right?
 So
 if
 if
 you
 mix
 them
 into
 a


single
 monot
 track,
 um,
 like
 kind
 of


overlapping
 with
 each
 other,
 the
 AI
 will


struggle
 to
 figure
 out
 who
 said
 what
 and


and
 thereby,
 you
 know,
 ruining
 the
 entire


downstream
 summary.
 So
 um
 uh,
 it's


important
 that
 we
 have
 that
 channel


mapping
 intact
 and
 it
 separates
 which


who
 is
 what
 and
 who
 is
 saying
 what


right.
 Um
 finally,
 we
 apply
 a
 security


layer
 because
 sometimes
 the
 audio


streams
 can
 contain
 the
 credit
 card


numbers
 or
 maybe
 passwords
 or
 any


anything
 which
 is
 personally


identifiable
 information,
 PII.
 So
 we


utilize
 buffer
 management
 and
 early


stage
 PII
 masking
 technique
 uh
 so
 that


the
 sensitive
 data
 it
 never
 hits
 the
 LLM


memory
 banks
 whenever
 we
 are
 moving


ahead
 in
 the
 channel.


Now
 next,
 the
 audio
 it
 hits
 the
 um


speechtoext
 engine
 for
 generative
 AI
 or


the
 LLMs
 to
 summarize
 the
 um
 data


effectively
 or
 your
 response


effectively.
 We
 found
 that
 the
 speech
 to


text,
 the
 ST,
 um,
 accuracy
 must
 be
 above


90%.


uh
 we
 utilize
 advanced
 acostic
 modeling


to
 map
 the
 u
 phonemes
 and
 filter
 out
 any


regional
 dialects.
 We
 then
 apply
 the


language
 logic
 utilizing
 like
 domain


specific
 dictionaries.
 U
 just
 for


example,
 if
 it's
 an
 insurance
 agent,
 the


um
 speechtoext
 engine,
 ST
 needs
 to
 know


the
 difference
 between
 a
 term
 life
 and
 a


turn,
 right?
 Both
 of
 them
 are
 very
 close


to
 each
 other,
 but
 still
 there
 should
 be


a
 difference
 between
 them.
 Uh
 finally


post-processing
 is
 also
 vital.
 uh,
 we
 use


inverse
 text
 normalization
 and
 auto


punctuation.
 Uh
 for
 example,
 if
 if
 a


customer
 says
 $5,000,
 the
 speechtoext
 um


engine,
 it
 should
 must
 output
 that
 into


numerical
 fashion.
 And
 this
 numerical


formatting
 it
 it
 drastically
 improves


the
 LLM's
 ability
 to
 extract
 the


entities
 in
 later
 point
 in
 time.


Now
 we
 reach
 the
 generative
 AI
 core.
 We


are
 not
 just
 throwing
 a
 raw
 trans
 uh,
 raw


trans
 uh
 transcri
 script
 at
 a
 llm,
 but
 we


are
 also
 asking
 it
 to
 summarize
 it.
 like


we
 use
 a
 highly
 orchestrated
 approach
 in


this
 case.
 Um
 in
 our
 orchestration
 layer


we
 use
 specific
 prompt
 templates.
 Our


um
 setup
 showed
 that
 if
 if
 you
 just
 ask


an
 LLM
 to
 summarize
 a
 call,
 it
 outputs
 a


messy
 narrative
 paragraph.
 So
 instead
 we


use
 few
 short
 libraries
 to
 instruct
 the


LLM
 to
 output
 separate
 bullet
 points
 um


one
 list
 for
 customer
 inquiry,
 uh,
 and
 a


separate
 list
 for
 operators
 action.
 Uh


then
 comes
 the
 reasoning
 layer.
 In
 the


reasoning
 layer,
 we
 extract
 the
 intent.


We
 provide
 the
 LLM
 with
 a
 predefined


list
 of
 customer
 uh
 call
 reasons,
 like
 uh


cancellation
 or
 new
 application
 or
 any


kind
 of
 claim
 status,
 and
 instruct


it
 to
 classify
 the
 transcript
 and
 output
 the


reason
 why
 it
 choose
 that
 specific


classification.


And
 finally,
 the
 trust
 layer,
 where
 we


apply
 the
 token
 optimization
 to
 keep
 the


um
 latency
 low
 and
 runs
 the
 uh
 automated


hallucination
 checks
 to
 ensure
 the
 uh


generated
 summary
 is
 strict,
 um,
 and
 it
 is


grounded
 in
 the
 transcript.


Now
 the
 final
 technical
 hurdle
 is


getting
 this
 beautiful
 data
 back
 into


hands
 of
 the
 business.
 Our
 API
 gateway


acts
 as
 a
 schema
 mapper.
 It
 takes
 the


JSON
 output
 from
 the
 LLM,
 uh,
 and
 maps
 the


field
 like
 customer
 intent
 or
 resolution


status,
 and
 and
 directly
 to
 some


corresponding
 fields
 in
 the
 um,
 um,
 based


on
 the
 company's
 CRM
 system
 or
 any


customer
 data
 which
 we
 have
 laid
 out
 via


some
 rest
 APIs.
 So
 we
 don't
 remove
 the


human
 entirely
 in
 this.
 We
 use
 a


verification
 step
 in
 between.
 Uh,
 the


operator
 it
 sees
 the
 AI
 generated


summary
 autopop
 populated
 on
 their


screen.
 Uh,
 they
 do
 a
 quick
 visual
 field


validation,
 make
 some
 minor
 edits
 if


necessary,
 and
 then
 just
 click
 the


confirm.
 Uh
 simultaneously,
 this


structured
 data
 it
 flows
 into
 our


business
 intelligence
 models


um
 aggregating
 the
 voice
 of
 the
 customer


data
 for
 management
 dashboards
 and


automatically
 you
 know,
 flagging
 the


candidates
 for
 new
 FAQ


um
 data
 entries.
</details>

### 成果、挑战与未来展望

要将此架构整合到实际的联络中心环境中，会产生什么样的成果？让我们审视其运营影响。此次实施带来的运营影响立竿见影且极易衡量。

首先看ACW时间。在手动操作下，平均通话后工作时间为6.3分钟。通过我们的人工智能工作流，这一时间骤降至3.1分钟，**处理时间缩减了近50%**。若将此节省规模化至拥有500个坐席、日处理数千个电话的联络中心，将产生巨大的运营节约，相当于仅从效率角度就可收回数十个全职人力。

其次是**数据录入质量**。从高度主观且变化不定的状态，转变为高度标准化、统一化的输出。查询分类或通话原因标记，从依赖操作员主观判断和记忆，转变为严格的逻辑驱动，最终形成了一套高度一致的客户“声音”数据集供管理层分析。最终，通过消除输入笔记等重复性的行政负担，我们**减轻了操作员的认知负荷**，从而稳定了运营，并直接对抗了与员工流失相关的压力。这最终也降低了我们在讨论之初就识别出的高离职率。

尽管成果斐然，工程工作永无止境。让我们谈谈我们面临的**约束**（Constraints: 限制项目进展或性能的因素）以及未来的发展蓝图。

当前，我们正应对三个主要约束：
1.  **语音转文本准确性**：整个生成式AI摘要的准确性完全依赖于转录稿。如果STT引擎未能捕捉到重度口音或音频质量不佳，LLM将无从下手。因此，STT优化是我们持续的战斗。
2.  **初始设置成本**：虽然长期**投资回报率**（Return on Investment, ROI: 衡量一项投资效益的指标）巨大，但API令牌的初始消耗，尤其是在对长达20分钟的转录稿运行复杂LLM推理时，成本可能很高。尤其在初始扩展阶段，这无疑是艰难的。我们正不断致力于令牌优化技术，以降低这一成本。
3.  **安全与合规**：在音频流中处理PII或任何敏感信息极为复杂。确保数据在到达云端终点前进行严格的屏蔽是必要的。这也增加了延迟，并从架构角度带来了额外开销。我们仍在探索如何减少这些额外层级，使其在组件层面更加稳健。

为了应对这些约束并拓展可能性的边界，我们的发展蓝图目前分为三个阶段：

**第一阶段**：专注于**可解释AI**（Explainable AI, XAI: 旨在使AI决策过程透明化、易于理解的技术）。我们希望超越简单的通话摘要，真正做到**辅导操作员**。我们正在构建系统，以便在通话后分析音频，并为操作员提供即时的、私密的反馈，无论是关于他们的软技能、同理心水平，还是信息准确性。

**第二阶段**：目标是**预测性人员配置**（Predictive Staffing）。通过利用我们现在捕获的海量分类意图数据，我们可以将这些数据输入时间序列分析。这将使**劳动力管理**（Workforce Management, WFM: 优化联络中心人员配置、调度和管理效率的流程）能够准确预测基于特定主题的呼叫量峰值，从而优化排班。

**第三阶段**：或许对人类福祉最为重要——**对抗客户骚扰**。联络中心代理经常面临日益增多的言语侮辱。我们正在开发一种低延迟的**情感和声学分析**（Sentiment and Acoustic Analysis: 分析文本或语音中的情感倾向和声音特征），以检测客户何时变得具有攻击性。最终，系统可以触发警报通知主管，或将呼叫无缝转接给AI语音代理，以保护人类操作员在面对此类困难对话时的心理健康。

通过将这些严谨的工程技术应用于杂乱的音频数据，我们可以将联络中心从高压的成本中心，转变为高效且智能的信息收集引擎，从而保护其员工。这就是这一切的意义所在。感谢您的时间。我已附上我的二维码，将在稍后展示，以便您通过LinkedIn与我联系。如果您希望进一步讨论我们今天所讲的架构或任何**提示工程**（Prompt Engineering: 设计和优化输入给AI模型（如LLM）的文本指令，以获得期望输出的学科）策略，请随时联系。我很高兴能与您交流并共同探讨。再次感谢您的聆听，祝您一切顺利。再见。

<details>
<summary>Original English</summary>

Now
 to
 tie
 the
 architecture
 together,


this
 is
 the
 linear
 workflow
 logic
 of
 the


data
 pipeline.
 We
 take
 the
 raw


transcript
 complete
 um,
 with
 the
 time


indexing
 uh,
 confidence
 scoring
 and


dinoising.
 We
 passes,
 we
 pass
 it
 through


the
 speaker
 separation
 because
 we
 split


the
 stereo
 channels
 um,
 in
 the
 step
 one.


Um
 we
 can
 easily
 stitch
 the
 dialogue


together
 logically,
 like
 customer
 said
 x


agent
 said
 y.
 Uh
 then
 we
 move
 to
 the


context
 deduct
 deduction
 where
 the
 LLM


spots
 the
 entities
 like
 account
 numbers


um
 or
 product
 name
 or
 customer
 name,
 run


the
 sentiment
 analysis
 and
 recognizes


the
 intent
 and
 the
 final
 state
 is
 the


structured
 output.
 So
 instead
 of
 a
 wall


of
 text,
 uh,
 the
 system
 it
 outputs
 like


clear
 uh,
 and
 a
 clean
 JSON
 schema


matching
 some
 predefined
 uh,
 customer


data
 or
 maybe
 CRM
 templates
 which
 we


have
 in
 the
 enterprise,
 and
 then


categorized
 neatly
 into
 bullet
 points


and
 and
 this
 strict
 formatting
 is
 what


turns
 an
 unstructured
 conversation
 into


a
 database
 ready
 asset.


So
 what
 happens
 when
 we
 deploy
 this


architecture
 in
 a
 real
 contact
 center


environment?
 Let's
 look
 at
 the
 outcomes.


The
 operational
 impacts
 out
 of
 the


implementation
 were
 quite
 immediate
 and


and
 highly
 measurable.
 Um
 look
 at
 the
 um


ACW
 time.
 um,
 under
 the
 manual
 operation


after
 average,
 after
 call
 work
 was
 6.3


minutes
 uh,
 powered
 by
 our
 AI
 workflow


that
 dropped
 to
 like
 3.1
 minutes,
 which


is
 like
 almost
 50%
 reduction
 in
 the


processing
 time.
 Um
 if
 you
 calculate


that
 across
 500
 seats
 handling
 thousands


of
 calls
 a
 day,
 you
 are
 looking
 at
 a


massive
 operational
 saving.
 The


equivalent
 of
 almost
 reclaiming
 dozens


of
 full-time
 headcounts
 purely
 from


efficiency
 standpoint.
 Um
 [snorts]


the
 next
 aspect
 is
 of
 data
 entry


quality.
 It
 it
 moved
 from
 a
 highly


subjective
 and
 a
 variable
 to
 highly


standardized
 and
 uniform
 output.


uh
 the
 inquiry
 categorization
 or
 the


call
 reason
 tagging
 uh,
 it
 moved
 from


being
 dependent
 on
 an
 operator
 mode
 or


memory
 um,
 to
 um,
 being
 a
 strictly
 logic


based,
 resulting
 in
 a
 highly
 consistent


voice
 of
 the
 customer
 data
 set
 for
 the


management
 and
 ultimately,
 by
 removing


these
 repetitive
 administrative
 burden


of
 typing
 out
 notes,
 we
 reduce
 the


cognitive
 load
 on
 the
 oper
 operators


thereby
 stabilizing
 the
 operations
 and


directly
 combating
 the
 stress
 which
 is


linked
 with
 the
 staff
 and
 and
 this


ultimately
 reduced
 the
 turnover
 we


identified
 um,
 at
 the
 very
 beginning
 of


our
 discussion.


While
 the
 results
 were
 fantastic,
 the


the
 engineering
 work
 is
 never
 done.
 Um


and
 and
 let's
 talk
 about
 the
 constraints


we
 face
 uh,
 and
 our
 road
 map
 for
 the


future.


Um


we
 are
 currently
 navigating
 three
 main


constraints.
 First
 is
 the
 um
 source
 to


source
 to
 text
 accuracy,
 ST
 accuracy.


the
 entire
 generative
 AI
 summary,
 it


relies
 on
 the
 transcript.
 So
 if
 the
 ST


engine
 uh,
 fails
 to
 pick
 up
 heavy
 accents


or
 poor
 audio
 quality,
 the
 LLM
 has


nothing
 to
 work
 with.
 So
 the
 ST


optimization
 is
 a
 continuous
 battle
 for


us.
 Uh
 second
 is
 the
 initial
 setup
 cost


while
 the
 long-term
 ROI
 is
 massive,
 the


initial
 consumption
 of
 the
 API
 tokens


especially
 running
 complex
 LLM


reasonings
 on
 long
 20inut


uh
 transcripts
 can
 be
 costly,
 and
 uh


especially
 during
 the
 initial
 scaling


phases,
 those
 are
 tough
 ones,
 and
 and
 we


are
 constantly
 working
 on
 token


optimization
 techniques
 to
 bring
 this


number
 down.
 Uh
 the
 third
 is
 the


security
 and
 compliance.
 Um
 handling
 PII


uh
 per
 uh,
 any
 kind
 of
 sensitive


information
 in
 audio
 streams
 is
 very


complex.
 Um
 and
 ensuring
 robust
 masking


before
 the
 hit
 data
 hits
 the
 cloud


endpoint
 is
 a
 strict
 requirement.
 Um
 and


u
 because
 of
 this,
 we
 add
 some
 layers
 and


ultimately
 reduce,
 increases
 the
 latency


and
 also
 add
 some
 overhead
 from


architectural
 standpoint.
 So
 we
 are


still
 figuring
 it
 out
 how
 we
 can
 reduce


those
 extra
 layers
 and
 make
 it
 much
 more


robust
 component
 wise.


All
 right.
 So
 to
 address
 these


constraints
 um


and
 and
 push
 the
 boundaries
 of
 what's


possible,
 our
 road
 map
 is
 currently


broken
 down
 into
 three
 phases.
 Uh
 phase


one,
 it
 focuses
 on
 explainable
 AI.
 Um
 we


want
 to
 move
 beyond
 just
 summarizing


calls
 to
 actually,
 you
 know,
 coaching
 the


operators.
 We
 are
 engineering
 these


systems
 to
 analyze
 the
 audio
 post
 call


and
 provide
 operators
 with
 instant


private
 feedback
 on
 their
 uh,
 either
 soft


skills
 or
 empathy
 level,
 or
 any
 kind
 of


accuracy
 from
 a
 information
 standpoint.


The
 phase
 two,
 it
 targets
 the
 predictive


staffing.
 By
 taking
 the
 massive
 amount


of
 categorized
 intent
 data
 we
 are
 now


capturing,
 we
 can
 feed
 same,
 the
 same


exact
 data
 intent
 data
 into
 a
 time


series
 analytics.
 Um
 and
 and
 this
 will


allow
 the
 workforce
 management
 to


accurately
 forecast
 the
 call
 volumes


spikes
 based
 on
 those
 specific
 topics


and
 thereby
 optimizing
 the
 shiftuling.


Uh
 uh,
 the
 phase
 three
 is
 perhaps
 the


most
 important
 for
 human
 well-being.
 Uh


combating
 the
 customer
 harassment
 uh
 uh


contact
 center
 agents
 they
 mostly
 face


an
 increasingly
 amount
 of
 verbal
 abuse.


Um
 and
 we
 are
 developing
 uh,
 a
 low


latency
 sentiment
 and
 aostic
 analysis


that
 can
 detect
 um,
 when
 a
 customer


becomes
 abusive.
 Um
 ultimately,
 the


system
 can
 you
 know,
 trigger
 some


triggers
 uh,
 I
 mean,
 an
 alerts
 or


something
 which
 is
 important
 from


notification
 standpoint
 to
 a
 supervisor


or
 anyone
 who
 is
 there
 in
 the
 from
 the


management,
 upper
 management
 standpoint.


Um
 or
 or
 maybe
 seamlessly
 transfer
 the


call
 to
 an
 AI
 voice
 agent
 just
 to


protect
 the
 human
 operator
 uh,
 mental


health
 in,
 in
 case
 of
 these
 tough


conversations.


All
 right.
 Um
 so
 u
 by
 applying
 these


rigorous
 engineering
 uh,
 techniques
 to


the
 messy
 audio
 data,
 we
 can
 definitely


transform
 the
 contact
 centers
 from
 uh


cost
 centers
 of
 like
 high
 stress
 into
 a


highly
 efficient
 and
 intelligence


gathering
 engines.
 uh,
 that
 protect
 their


workforces.
 That's
 the
 whole
 idea
 of


having
 this
 right.
 Um
 thank
 you
 so
 much


for
 your
 time
 uh,
 and
 listening
 to
 me.
 Um


I
 have
 included
 my
 QR
 code
 which
 I
 will


just
 flash
 in
 here
 um,
 so
 that
 you
 can


grab
 me
 over
 LinkedIn.
 uh,
 and
 please


feel
 free
 to
 connect
 if
 if
 you
 would


like
 to
 discuss
 uh,
 the
 architecture
 or


any
 prompt
 engineering
 strategies


related
 to
 the
 discussion
 which
 we
 had


in
 here,
 and
 happy
 to
 connect
 and
 um,
 make


things
 uh,
 work
 things
 out
 between
 us
 and


we
 can
 have
 more
 conversations.
 So
 thank


you
 so
 much
 for
 listening
 to
 me,
 and
 have


a
 good
 one.
 Bye.
</details>