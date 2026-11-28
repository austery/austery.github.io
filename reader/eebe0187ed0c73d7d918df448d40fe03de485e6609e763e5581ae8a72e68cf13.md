---
author: Latent Space
date: '2026-06-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=fpAthTtha8c
speaker: Latent Space
tags:
  - artificial-general-intelligence
  - reinforcement-learning
  - scaling-law
  - model-evaluation
  - pre-training
title: 与 OpenAI 首席研究官 Mark Chen 边做饭边聊：AGI、o1、模型评测与扩展定律
summary: OpenAI 首席研究官 Mark Chen 在烹饪对话中探讨了交易员背景对研究的影响、研究品味的培养、o1 等推理突破、计算资源分配机制，以及当前基准评测面临的饱和危机与未来研究范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mark Chen
companies_orgs:
  - OpenAI
products_models:
  - o1
  - ChatGPT
media_books: []
status: evergreen
---
### 开场与做汤轶事

**>>**: 是啊，我当时就觉得……
<details><summary>Original English</summary>
**>>**: Yeah,
 I
 was
 like
</details>

**>>**: 那一个是我知道的。[音乐]
<details><summary>Original English</summary>
**>>**: That
 one
 that
 [music]
 I
 know.
</details>

**>>**: 那感觉就像 Corey，我所处的那种处境。
<details><summary>Original English</summary>
**>>**: That
 feels
 like
 Corey,
 the
 situation
 I'm


in.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 干杯。
<details><summary>Original English</summary>
**>>**: Cheers.
</details>

**>>**: 干杯。
<details><summary>Original English</summary>
**>>**: Cheers.
</details>

**>>**: 大家好，欢迎来到 Latent Space 烹饪系列，在这个系列中我们邀请创始人与研究人员，[音乐] 让他们尽情发挥厨艺。今天我们迎来了一位非常特别的嘉宾，OpenAI 的首席研究官 Mark Chen。[音乐] 欢迎你，Mark。
<details><summary>Original English</summary>
**>>**: Hey
 guys,
 welcome
 to
 the
 Latent
 Space


cooking
 series
 where
 we
 invite
 founders


and
 researchers
 [music]


and
 just
 let
 them
 cook.
 Today,
 we
 have
 a


very
 special
 guest,
 the
 chief
 research


officer
 of
 OpenAI,
 Mark
 [music]
 Chen.


Welcome,
 Mark.
</details>

**>>**: 谢谢你的邀请，Alan。
<details><summary>Original English</summary>
**>>**: Thanks for
 inviting
 me,
 Alan.
</details>

**>>**: 好的，感谢你的到来。我想，首先这一切源于一个灵感，之前听说过一个故事，Mark Zuckerberg 会做汤试图挖走研究人员，作为回应，你也给研究人员送去了汤。这是真的吗？这事真的发生过吗？起作用了吗？
<details><summary>Original English</summary>
**>>**: Yeah,
 thank
 you
 for
 coming.
 I
 mean,
 to


begin,
 this
 all
 started
 from
 the


inspiration
 after
 hearing
 the
 story
 that


Mark
 Zuckerberg
 would
 make
 soup
 to
 try


to
 poke
 researchers
 and
 in
 response,
 you


brought
 soup
 to
 researchers.
 Is
 this


true?
 Did
 this
 happen?
 Did
 it
 work?
</details>

**>>**: 哦，你知道的，这绝对是个真实的故事。我也确实给我们自己的研究人员送过汤。我认为那件事后来稍微平息了一些。我觉得我们最终占了上风，不过是的，在 AI 涉及的种种疯狂事情中，这依然是一个非常有趣的故事。
<details><summary>Original English</summary>
**>>**: Oh,
 you
 know,
 it's
 absolutely
 a
 true


story.
 And
 I
 have
 brought
 soup
 to
 our


own
 researchers.
 I
 think
 that
 matters


calmed
 down
 a
 little
 bit.
 I
 think
 we


came
 out
 on
 top,
 but


yeah,
 still
 a
 very
 funny
 story
 in
 the


craziness
 of
 how
 AI
 is
 involved.
</details>

**>>**: 你平时经常做饭吗？这是你熟悉的事情吗？
<details><summary>Original English</summary>
**>>**: How
 often
 do
 you
 cook?
 Is
 it
 something


you're
 familiar
 with?
</details>

**>>**: 哎呀，你知道的，我确实喜欢做饭，但我没有经常做饭的奢侈条件。所以我平时工作日每天晚上基本上都有工作晚餐，而且，可能到了后 AGI 时代，这会成为我的爱好吧。我一直开玩笑说，一旦一切尘埃落定，我就要去开个面条摊。
<details><summary>Original English</summary>
**>>**: Well,
 you
 know,
 I
 I
 do
 enjoy
 cooking,


but
 I
 don't
 have
 the
 luxury
 of
 doing


that
 so
 often.
 So,
 I
 uh
 usually
 have
 a


work
 dinner
 every
 night
 of
 the
 week
 and,


you
 know,
 maybe
 post
 AGI,
 this
 is
 going


to
 be
 my
 hobby.
 I've
 always
 joked
 that


I'm
 going
 to
 start
 a
 noodle
 stand
 once


once
 it's
 it's
 all
 over.
</details>

**>>**: 是啊是啊，后 AGI 时代，希望那个摊位还能在。太好了。我想看着我们面前摆着的这些材料，你大致能猜到我们要做什么吗？
<details><summary>Original English</summary>
**>>**: Yeah,
 yeah,
 you
 know,
 post
 AGI,


hopefully
 that'll,
 you
 know,
 still
 be


there,
 but
 great.
 And
 I
 guess
 looking
 at


what
 we
 have
 in
 front
 of
 us,
 do
 you
 have


an
 idea
 generally
 of
 what
 we're
 probably


making?
</details>

**>>**: 呃，韩式豆腐汤，也许？
<details><summary>Original English</summary>
**>>**: Uh
 Korean
 tofu
 soup,
 maybe?
</details>

**>>**: 对，对，大体上就是这个。我们就是从你给研究人员送汤的故事中获得的灵感。所以我们要煮一份韩式豆腐炖汤，而且还有我要煮的大虾。准备好开始了吗？
<details><summary>Original English</summary>
**>>**: Yeah,
 yeah,
 that's
 that's
 generally
 what


it
 is.
 So,
 we
 inspired
 off
 of
 the
 story


of
 you,
 you
 know,
 bringing
 soup
 to


researchers.
 So,
 we're
 making
 a
 tofu


Korean
 stew
 and
 we
 have
 prawns
 that
 I'll


be
 cooking.
 Are
 you
 ready
 to
 go?
</details>

**>>**: 好啊，来吧。我们开始吧。
<details><summary>Original English</summary>
**>>**: Yeah,
 let's
 do
 it.
 Let's
 do
 it.
</details>

**>>**: 太好了。好的，我们可能应该做的第一件事是先把蔬菜分开，然后切开。基本上，我们想要做的就是把带有泥土的脏部分切掉，然后把它们分开放好。
<details><summary>Original English</summary>
**>>**: Great.
 Okay,
 so
 the
 first
 thing
 we


should
 probably
 do
 is
 we'll
 separate
 the


veggies
 and
 then
 we
 can
 cut
 them.
 And


basically,
 what
 we
 want
 to
 do
 is
 just
 um


cut
 the
 dirty
 part
 off
 with
 the
 dirt
 and


then,
 yeah,
 separate
 that
 across.
</details>

**>>**: 这个我知道。
<details><summary>Original English</summary>
**>>**: that
 I
 know.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

### 交易员背景与研究能力的培养

**>>**: 好，行。然后就放在那里。你可以切那个。在切的同时，我想顺便多问问你的背景。在过去，你曾经做过交易员。甚至 Sam 我记得去年四月份也发过推文，说如果你是高频交易员，应该考虑加入 OpenAI 来构建 AGI。那么，你认为做交易员和做研究员之间有什么关联吗？还是说这只是一个非常硬核且竞争激烈的领域，能够涌现出很多优秀的员工？
<details><summary>Original English</summary>
**>>**: Yeah,
 okay.
 And
 then
 just
 have
 that


there.
 So,
 you
 can
 do
 that.
 And
 while


that's
 going,
 I
 guess
 I
 could
 ask
 more


about
 your
 background.
 So,
 in
 a
 previous


life,
 you
 were
 once
 a
 trader.
 And
 even


Sam,
 I
 think,
 last
 year
 in
 April
 also


tweeted
 about
 how
 if
 you're
 a
 high


frequency
 trader,
 you
 should
 consider


joining
 OpenAI
 because,
 you
 know,
 build


AGI.
 So,
 do
 you
 think
 there's
 a
 relation


between,
 you
 know,
 being
 a
 trader
 and


being
 a
 researcher,
 or
 do
 you
 think
 it's


just
 like
 a
 very
 technical
 and


competitive
 area
 where
 a
 lot
 of
 great


employees
 can
 come
 from?
</details>

**>>**: 我觉得最重要的一点是，有很多研究人员最初并没有接受过机器学习或 AI 研究的正式训练。我们一直非常坚信可以通过培养来让人胜任这项工作。我认为真正困难的事情在于创造性地解决问题以及跳出框架思考的能力。并不一定非得去读个博士，尽管读博确实能带来宝贵的技能。至于交易这个特定行业，我的意思是，我不知道它算不算特别特殊的职业。我的理解是，我们有优秀的数学家加入，也有优秀的物理学家加入，但交易属于那种非常无法投机取巧的事情。[清嗓子] 你无法在现实世界中作弊，对吧？这是一个很难去优化的指标。而且它还具有很多特征，比如在这个领域细节真的非常重要。这是一种极其严酷的优化，要榨干系统中的每一滴汁水。其中的一些技能是可以迁移过来的。
<details><summary>Original English</summary>
**>>**: I
 think
 really
 the
 most
 important
 thing


is
 there
 are
 a
 lot
 of
 researchers
 who


just
 started
 out
 without
 a
 formal


training
 in
 machine
 learning
 or
 AI


research.
 Um


we've
 very
 much
 believed
 in
 training


people
 up
 to
 do
 this.
 I
 I
 think
 the
 real


hard
 thing
 is
 the
 ability
 to
 creatively


solve
 problems
 and
 think
 outside
 of
 the


box.


It's
 not
 so
 much,
 you
 know,
 you
 have
 to


do
 a
 PhD,
 even
 though
 that
 does
 bring
 a


valuable
 skill
 set.
 Um


with
 trading
 in
 particular,
 I
 mean,
 I
 I


don't
 know
 that
 it's
 that
 special
 of
 a


profession.
 Like,


I
 kind
 of
 think
 of
 it
 as,
 you
 know,


we've
 had
 great
 mathematicians
 join,
 we


already
 had
 great,
 you
 know,
 physicists


join,
 but
 trading
 is
 something
 where,


you
 know,
 it's
 like


it's
 very
 unhackable.
 You're


[clears throat]
 um


how
 you
 you
 can't
 kind
 of
 cheat
 the
 real


world,
 right?


You
 know,
 it's


it's
 a
 hard
 metric
 to
 optimize.


And
 there's
 also
 a
 lot
 of


characteristics
 like


it's
 it's
 a
 field
 where
 attention
 to


detail
 really
 matters.
 And


um


you
 know,
 it's
 kind
 of
 the
 brutal
 hard


optimization
 and
 squeezing
 out
 the
 juice


of
 a
 system.
 Um
 and
 some
 of
 those


those
 skills
 transfer
 over.
</details>

**>>**: 明白了。对于想要进入研究领域、比如说没有博士学位的人，你认为他们可以通过学习哪些主要特质或事物来培养“研究品味”？因为我认为对于想进入这个领域的人来说，这可能是他们感到非常陌生的一大核心部分。
<details><summary>Original English</summary>
**>>**: Got
 you.
 Yeah,
 and
 I
 guess
 for
 people


who
 want
 to
 get
 into
 research,
 who
 let's


say
 don't
 have
 a
 PhD,
 what
 do
 you
 think


are
 the
 main
 attributes
 or
 things
 that


they
 can
 learn
 to
 develop
 research


taste?
 Because
 I
 guess
 that's
 the
 main


part
 of
 getting
 into
 this
 field
 that
 may


be
 very
 foreign
 to
 them.
</details>

**>>**: 是的，我想说这其实有点被高估了。它确实是需要培养的东西，但我发现培养它的最好途径其实就是复现。你应该挑选那些你非常钦佩的论文，然后尝试去完整复现它。在我的记忆中有很多这样的实践脱颖而出。比如在 2018 年，有像 ResNet、PixelCNN 这样的工作，我仅仅通过尝试完全复现它们的训练曲线，达到论文所提示的精确训练损失或困惑度，就学到了非常多的东西。你会看到很多人们平时不怎么谈论的技巧，但一旦你往下深挖几层，就能掌握那些技巧。而且，最初带我进入这个领域的契机是……
<details><summary>Original English</summary>
**>>**: Yeah,
 I
 mean,
 I
 think
 it's
 a
 little
 bit


overrated.
 It
 is
 something
 you
 have
 to


develop,
 but
 um
 the
 best
 mechanism
 I've


found
 for
 developing
 that
 is
 really
 just


replication.
 So,
 I
 think
 you
 should
 take


papers
 that
 you


really
 look
 up
 to
 and
 just
 try
 to
 fully


replicate
 it.


I
 like
 I
 I
 think
 a
 lot
 of
 applications


stood
 out
 in
 my
 my
 mind.
 Um
 you
 know,


back
 in


2018,


there
 is
 um


you
 know,
 like
 ResNet,
 there
 were
 Pixel


CNNs,
 and
 I
 I
 learned
 so
 much
 just
 um


trying
 to
 replicate
 the
 training
 curves


exactly,
 get
 to
 the
 exact
 amount
 of,
 you


know,
 like
 training
 loss
 or
 perplexity


that
 the
 papers
 um
 hinted
 towards.
 You


just
 see
 a
 lot
 of
 techniques,
 right,


that
 um
 people
 don't
 really


kind
 of
 talk
 about,
 but
 you
 know,
 once


once
 you
 dive
 in
 a
 couple
 of
 layers


deeper,
 um
 you
 learn
 those
 techniques.


And


um
 yeah,
 I
 think
 really
 the
 first
 thing,


too,
 that
 got
 me
 into
 the
 field
 was
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 当 AlphaGo 与李世乭对弈的时候。我觉得那对很多人来说都是一个转折点。它太令人鼓舞了。我真正全力以赴投入的第一个大项目，就是“我能不能把 DQN 跑通？”
<details><summary>Original English</summary>
**>>**: when
 AlphaGo
 played
 Lee
 Sedol.
 And
 you


know,
 I
 think
 that
 was
 a
 turning
 point


for
 so
 many
 people.
 And
 yeah,
 I
 mean,
 it


was
 it
 was
 it
 was
 inspirational.
 And
 it


it
 the
 the
 first
 big
 project
 that
 I
 I


really
 went
 after
 was
 um
 can
 I
 get
 a
 DQN


working?
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

### 从“第37手”到长程智能体与强化学习边界

**>>**: 是啊，确实如此。我想在那几盘棋里，好像是第 37 手，看着它发生以及见证所有那些进展真是太不可思议了，再看到我们今天所达到的位置，尤其是在研究方面。
<details><summary>Original English</summary>
**>>**: Yeah.
 Yeah,
 that's
 true.
 I
 think
 it
 was


move
 37
 or
 something
 like
 one
 of
 the


games
 that
 was
 pretty
 uh
 insane
 watching


it
 happen
 and
 seeing
 all
 that


development
 and
 seeing
 also
 where
 we


have
 gotten
 to
 today,
 especially
 with


the
 research.
</details>

**>>**: 如今在几乎每一个领域都能看到类似“第 37 手”的表现，这难道不是很疯狂吗？数学领域有第 37 手，计算机科学和编程里也有。甚至感觉很多人在今年年初醒来时都惊呼：天哪，智能体已经在我的行业里起效了。他们基本上意识到，这些模型可以为他们完成长程且有意义的工作。
<details><summary>Original English</summary>
**>>**: I
 mean,
 isn't
 it
 crazy
 that
 you're


seeing
 move
 37s
 in
 almost
 every
 field


now?
 It's
 like
 there's
 move
 37s
 in
 in


math,
 there's
 uh
 in
 computer
 science
 and


coding.
 Um


I
 think


even
 yeah,
 just
 it
 feels
 like
 a
 lot
 of


people
 woke
 up
 at
 the
 start
 of
 this
 year


and
 were
 like,
 man,
 agents
 are
 working


in
 my
 profession.
 And
 um


you
 know,
 they're
 they're
 essentially


realizing
 that
 these
 models
 can
 just
 do


long
 horizon
 meaningful
 work
 for
 them.
</details>

**>>**: 是的，一点没错。看到这些确实非常震撼，我自己工作里也都在用它。好的，我们接下来的步骤很简单，切洋葱就行。这里我们需要做的就是把它切成丁。你认为是否存在某些职业，强化学习（RL）可能更难切入？比如编程可能相对容易，因为无论是通过代码库还是你要完成的任务，大量上下文都是可以直接获取的；但如果要去做初级顾问的工作，所有的背景信息都有些分散，可能就会更困难。你怎么看待这些不同的场景？是否有某种评估正确途径的方法？
<details><summary>Original English</summary>
**>>**: Yeah,
 no,
 that's
 true.
 It
 is
 it
 is
 very


impressive
 to
 see,
 like
 I'm
 even
 just


using
 it
 in
 my
 own
 work.
 But
 okay,
 the


next
 thing
 we
 could
 do
 is
 just
 as
 simple


as
 cutting
 the
 onion.
 So,
 what
 we
 have


to
 do
 here
 is
 just
 like
 dicing
 it.
 Do


you
 think
 um


there's
 jobs
 that
 RL
 maybe
 will
 have


like
 a
 much
 harder
 time
 to
 kind
 of
 break


into?
 So,
 for
 example,
 coding
 maybe


easier
 since
 a
 lot
 of
 context
 is


accessible
 either
 through
 the
 code
 bases


or
 even
 the
 work
 you're
 trying
 to
 do,


but
 let's
 say
 if
 you're
 trying
 to
 do
 the


job
 that
 a
 junior
 consultant
 may
 do,


where
 all
 the
 context
 is
 a
 little


scattered,
 maybe
 it
 more
 difficult.
 How


do
 you
 view
 through
 like
 those
 different


scenarios?
 Is
 there
 a
 way
 that
 you
 kind


of
 assess
 what
 can
 be
 the
 right


approach?
</details>

**>>**: 是的，我认为在传统意义上，当涉及到主观多于客观的领域时，RL 往往会遭遇阻力。如果想找一个例子，那就是创意写作。
<details><summary>Original English</summary>
**>>**: Yeah,
 I
 mean,
 I
 I
 think
 it's
 RL's


traditionally
 had
 um


headwinds
 when
 it's
 come
 to
 fields
 that,


you
 know,
 it's
 more


um


kind
 of


subjective
 than
 objective.
 So,
 if
 you


kind
 of
 think
 of
 you
 know,
 one
 one
 kind


of


you
 know,
 uh


example
 of
 this
 is
 creative
 writing.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 拿两篇创意写作作品来说，两位专家可能会有截然不同的看法。
<details><summary>Original English</summary>
**>>**: Where,
 you
 know,
 you
 could
 take
 two


pieces
 of
 creative
 writing
 and
 two


experts
 can
 have
 wildly
 different


opinions.
</details>

**>>**: 确实。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 所以在这些难以评分的领域，RL 直接应用的空间是最小的。我知道很多人正在开发将 RL 应用到这些场景的技术，但就目前而言，只有在存在不容置疑的事实依据的地方，比如数学和计算机科学，你可以明确证明对或错，在那些地方你才会看到它真正腾飞。
<details><summary>Original English</summary>
**>>**: So,
 it's
 these
 fields
 where
 things
 are


hard
 to
 grade.
 Um


where


you
 know,
 RL
 has
 the
 least
 amount
 of


ability
 to
 kind
 of
 go
 and
 um
 and


directly
 apply
 there.
 I
 know
 a
 lot
 of


people
 are
 developing
 techniques
 to


apply
 RL
 in
 these
 um
 these
 settings,
 but


um
 for
 now,
 it's
 just
 where
 there's
 cold


hard
 truth,
 things
 like
 math
 and


computer
 science,
 where
 you
 can
 prove
 it


correctly
 or
 wrong.
 Um
 that's
 where
 you


kind
 of
 see
 it
 really
 taking
 off.
</details>

**>>**: 是的。这其实引出了一个关于评估这些领域的思考。随着模型变得越来越强大，甚至在诸如解决国际数学奥林匹克（IMO）竞赛题上达到饱和……
<details><summary>Original English</summary>
**>>**: Yeah.
 No,
 that
 actually
 brings
 up
 a


thought
 on
 in
 terms
 of
 evaluating
 those


fields.
 So,
 um
 you
 know,
 as
 models
 get


much
 much
 more
 powerful
 and
 even


saturate,
 for
 example,
 solving
 like
 the


IMO
 questions.
</details>

**>>**: 是的，对。
<details><summary>Original English</summary>
**>>**: Yeah,
 yeah.
</details>

**>>**: 你怎么看待评估超人类智能？比如当它变得如此厉害，甚至连前 0.01% 的顶尖人类都难以企及的时候，我们该如何拓展智能的前沿？
<details><summary>Original English</summary>
**>>**: Um
 how
 do
 you
 view
 evaluating
 like


superhuman
 intelligence?
 Like
 it
 gets
 to


a
 point
 where
 it's
 so
 good
 at
 things


that
 even
 the
 top
 what,
 0.01%
 of
 humans


can
 do,
 that
 like,
 you
 know,
 how
 can
 we


push
 past
 that
 frontier
 of
 intelligence?
</details>

**>>**: 这确实很不可思议，我觉得很多关键点集中在与真实世界的交互上。过去当我们思考如何超越编程竞赛这类测试时，我们最初采取的主要方向是转向真实世界的研究，对吧？我们看到模型在发现全新定理以及推进硬科学前沿方面做得越来越好了。但即使在今天，这也已经不再令人惊讶了。我们现在几乎觉得模型能解决极其困难的问题是理所当然的，它们能够做出贡献，甚至在不同领域之间建立新颖且深刻的联系。因此，我们把编程协同工作视作一个能检验模型是否能在高上下文环境和真实长程环境中学习的领域。
<details><summary>Original English</summary>
**>>**: No,
 it's
 kind
 of
 it's
 kind
 of
 crazy,
 and


I
 feel
 like
 um
 a
 lot
 of
 it
 centers
 in
 on


in
 on
 kind
 of
 interfacing
 with
 the
 real


world.
 And
 um
 when
 when
 we've
 thought


about
 how
 to
 evolve
 past
 things
 like


programming
 contests
 in
 the
 past,
 um


I
 think
 a
 lot
 of
 the
 initial
 direction


we
 took
 was
 you
 should
 move
 it
 to


real-world
 research,
 right?
 And
 we've


seen
 that
 the
 models
 uh
 they've
 gotten
 a


lot
 better
 at
 uh
 just
 kind
 of


discovering
 novel
 theorems
 and
 uh


pushing
 the
 frontiers
 of
 of
 hard


sciences.
 But
 even
 today,
 right?
 That's


no
 longer
 a
 surprise.
 I
 think
 like
 you


we
 almost
 take
 it
 for
 granted
 now
 that


these
 these
 models
 can
 solve
 very
 very


difficult
 problems.
 They
 can
 make


contributions
 and
 even
 kind
 of
 draw


relationships
 between


um
 fields
 that,
 you
 know,
 that
 are
 that


are
 novel
 and
 insightful.
 So,
 I
 think


you
 know,
 we
 we
 think
 of
 coding


co-working


as
 really
 a
 domain
 for
 that
 that
 tests


whether
 our
 models
 can
 learn
 in


high-context
 settings
 and
 in
 real-world


long-horizon
 settings.
</details>

### 烹饪翻炒与扩展定律信仰

**>>**: 明白了。好的，这很有道理。既然你把所有蔬菜都切好了，我们现在可以进行下一步，也就是翻炒。我们可以用这个脉冲炉，之前见识过，非常强劲。我把它打开。我们倒点油炒一下。把锅放在前面的炉头上，然后……
<details><summary>Original English</summary>
**>>**: Got
 you.
 Okay.
 Yeah,
 that
 makes
 sense.


And
 since
 you're
 done
 with
 all
 the


vegetables,
 we
 can
 now
 do
 the
 next
 step,


which
 is
 sauteing
 it.
 So,
 yeah,
 we
 can


use
 the
 impulse
 stove,
 which
 we've
 seen


before
 and
 very
 powerful.
 Let
 me
 just


turn
 it
 on.
 Um
 and
 yeah,
 so
 we'll
 just


saute
 it
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Great.
</details>

**>>**: 加点油。把锅放在前面的炉头上，然后……
<details><summary>Original English</summary>
**>>**: with
 some
 oil.
 So,
 yeah,
 put
 the
 pan
 in


the
 front
 burner
 and
 then
</details>

**>>**: 这些炉子真酷。
<details><summary>Original English</summary>
**>>**: These
 are
 cool
 stoves.
</details>

**>>**: 是的，倒点油进去。倒一大勺就行。完美。然后我们可以打开炉子。按一下，然后转动旋钮。太棒了，完美。等锅热起来的时候，我们可以稍微等一下，[清嗓子] 然后把蔬菜放进去。不过回到对研究的看法上，是否存在一些普遍被接受、但你并不认同的观点？比如“预训练已死”，或者“语言模型永远无法带我们走向 AGI”。外面有许多观点非常含糊，显然也尚未得到证实。从你在 OpenAI 主导研究的角度来看，对于这类观点你怎么看？
<details><summary>Original English</summary>
**>>**: Yeah,
 you
 can
 use
 oil
 to
 pour
 some
 in.


And
 then,
 you
 can
 also


Yeah,
 just
 a
 good
 dollop.
 Perfect.
 And


yeah,
 and
 then
 we
 can
 turn
 on
 the
 stove.


So,
 just
 press
 it.
 And
 then,


yes,
 spin
 the
 knob.


Great.
 Perfect.
 And
 then
 while
 that


heats
 up,
 we
 can
 just
 wait
 and


[clears throat]
 then
 add
 the
 vegetables.


But
 yeah,
 I
 guess
 more
 so
 on
 views
 for


research,
 are
 there
 I
 guess,
 you
 know,


commonly
 accepted
 ideas
 that
 are,
 you


know,
 you
 disagree
 with,
 whether
 it
 be


like
 pre-training
 is
 dead
 or
 language


models
 will
 never
 get
 us
 to
 AGI.
 I
 think


there
's
 a
 lot
 of
 takes
 out
 there
 that


are
 very
 ambiguous
 and
 obviously
 haven't


proven
 out
 yet.
 And
 I
 guess
 from
 your


perspective
 as
 like
 the
 research
 like


leading
 things
 in
 OpenAI.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 比如像那些看法？
<details><summary>Original English</summary>
**>>**: Like
 things
 like
 those?
</details>

**>>**: 我坚信指数级增长和扩展定律（scaling laws）。所以对于任何看空的论调，我都相当强烈地反对。关于“预训练已死”，有趣的是这种论调在过去一两年左右才开始更广泛地传播开来，对吧？在大语言模型的发展历史中，很多人曾多次说过类似的话。大家总会指出某些瓶颈，说“因为这个瓶颈，你无法再扩大规模了”。但我们总能找到某种技术，无论是更好的工程实践，还是新的研究洞见，帮助我们冲破边界。因此我认为这只是在不断重复同样的事情：更精细的研究工程、更精细的数据工程、更精细的规模扩展。它总能解锁下一步扩展的能力。它已经持续适用了近 10 个数量级，没有任何理由认为它不会继续生效。
<details><summary>Original English</summary>
**>>**: I
 mean,
 I


I
 firmly
 believe
 in
 exponent
 being
 on


the
 exponential
 and
 in
 scaling
 laws.
 So,


I
 think
 any
 of
 these
 bear
 takes,


I


fairly
 strongly
 disagree
 with.
 Um
 you


know,
 when
 when
 it
 comes
 to
 pre-training


is
 dead,
 I
 I
 mean,
 I
 think
 the
 the
 funny


thing
 is
 this
 narrative
 only
 started


spreading
 more
 widely
 after,
 let's
 say,


the
 last
 one
 or
 two
 years
 or
 so.
 Right?


In
 many
 times
 uh


in
 the
 history
 of
 uh
 developing
 LLMs,


people
 have
 been
 saying
 this,
 right?
 And


you
 know,


um


there
 there've
 always
 been
 some
 some


bottlenecks
 that
 people
 will
 Well,
 you


can't
 scale
 past
 this
 because
 of
 this


bottleneck.
 Um
 and
 we've
 always
 found


some
 kind
 of
 technique,
 whether
 it
 be


better
 engineering
 or
 some
 new
 research


insight
 that
 helps
 you
 break
 past
 the


boundary.
 And
 so,
 I
 think
 it's
 just
 more


and
 more
 of
 the
 same,
 right?
 Like
 more


careful
 research
 engineering,
 more


careful
 data
 engineering,
 more
 careful


scaling.
 And
 it
 always
 unlocks
 that
 next


ability
 to
 scale
 further.
 So,
 I
 I
 mean,


it's
 held
 for,
 you
 know,
 almost
 10


orders
 of
 magnitude,
 but
 there's
 no


reason
 it
 should
 not
 keep
 keep
 holding.
</details>

### 推理押注与 o1 诞生内幕

**>>**: 是的，非常有道理。在帮助你们实现超越的那些研究押注中，你是否还记得早期的某些具体想法，当时大家都在说“这根本行不通”？
<details><summary>Original English</summary>
**>>**: Yeah, that's
 a
 very
 fair
 point.
 I
 guess


on
 research
 bets
 that
 have
 helped
 you


scale
 beyond,
 were
 there
 specific
 ideas


that
 you
 can
 even
 remember
 in
 the
 early


days
 that
 everyone
 was
 was
 saying
 that


this
 is
 not
 going
 to
 work?
</details>

**>>**: 是的，我认为推理（reasoning）就是其中最大的例子之一。我们向全世界推出的第一个重大突破是 o1，但要让它启动并不容易，因为在当时我们所处的环境下，“预训练加后训练”给人的感觉是一条如此有前景的范式。
<details><summary>Original English</summary>
**>>**: Well,
 yeah,
 I
 mean,
 I
 think
 of
 reasoning


as
 one
 of
 the
 biggest
 examples
 of
 this.


Yeah,
 and
 um
 you
 know,
 the
 the
 first


breakthrough
 that
 we
 launched
 to
 the


world
 here
 was
 O1,
 but
 it
 wasn't
 easy
 to


get
 that
 off
 the
 ground
 cuz
 one
 the


world
 we
 were
 back
 living
 in
 back
 then,


it
 was
 one
 where
 pre-training
 plus


post-training,
 right?
 That
 felt
 like


such
 a
 promising
 paradigm.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 因此，即使在像 OpenAI 这样的公司里，人们自然也会质疑：既然眼前已经有一台运转良好的机器，为什么还要去做别的事？从根本上讲，这要归功于 Jakub、Ilya 以及许多在这一领域真正拥有信念和远见的人，我们才开始认真推进这项工作。即便如此，也花费了大量的引导与协调才让整个公司把这作为一项根本性的押注来全力支持。
<details><summary>Original English</summary>
**>>**: Um
 and
 so,
 even
 at
 a
 company
 like


OpenAI,
 you
 would
 have
 people
 ask


naturally,
 why
 do
 something
 when
 you


have
 a
 machine
 that
 works?
 And


fundamentally,
 you
 know,
 it's
 to
 the


credit
 of


you
 know,
 Yakub,
 Ilya,
 many
 of
 the


people
 who
 really
 had
 conviction
 and


vision
 in
 the
 space
 um
 that
 we
 started


pushing
 on
 this
 in
 earnest.
 And
 even


then,
 it
 took
 a
 lot
 of
 steering
 to
 get


the
 whole
 company
 behind
 this
 as
 a
 as
 a


fundamental
 bet.
</details>

**>>**: 明白了。
<details><summary>Original English</summary>
**>>**: Got
 you.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

### 研究文化与自下而上的路线图

**>>**: 你是如何培养激励研究人员的能力的？因为我认为做很多押注必然伴随着一些尝试的失败，但依然要在团队中建立信任，让他们知道最终某些押注会产生幂律效应。
<details><summary>Original English</summary>
**>>**: And
 how
 do
 you
 kind
 of
 develop
 that


ability
 to
 motivate
 researchers?
 Cuz
 I


assume
 that's
 a
 big
 part
 of
 you
 know,


taking
 a
 lot
 of
 bets
 and
 some
 won't
 pan


out,
 but
 still
 building
 the
 trust
 in
 the


team
 to
 know
 that
 eventually
 some
 of


these
 will
 actually
 have
 no
 power
 law


effects.
</details>

**>>**: OpenAI 非常酷的一点在于，研究氛围让人感觉是一个英才体制（meritocracy）。很多时候，研究管理者本身就是过去做出最顶尖研究的人。所以我认为很多方向指引可以自顶向下推行。比如如果你的经理说：“看，我真的确信这是一条可行的道路”，大家通常都会认真考虑，毕竟这是一个你在研究品味和执行力上敬重了很久的人，而他现在对这个想法非常兴奋，这绝对是大家会重视的因素。所以存在良好的自上而下的引导。同时，OpenAI 另一个非常棒的地方是有自下而上的机制。我们很乐意被证明是我们错了，只要有人能拿出确凿的实证。很多类似的事情最终变成了我们研究路线图的核心部分。那些原本没有人在刻意主导的方向，某个一线研究员对其抱有强烈的信念，看到这样的突破也是一件非常令人欣喜的大事。
<details><summary>Original English</summary>
**>>**: You
 know,
 what's
 what's
 really
 cool


about
 OpenAI
 is
 um
 research
 it
 feels


like
 a
 meritocracy.
 So,
 um


often
 times
 the
 research
 managers
 are


the
 people
 who


um


do
 the
 actual
 have
 done
 the
 best


research
 in
 the
 past.
 And
 so
 I
 think
 a


lot
 of
 steering
 can
 come
 top-down,


right?
 Like
 if
 your
 manager
 says,
 "Hey,


you
 know,
 I'm
 like
 really
 convinced
 this


is
 the
 path
 forward."
 Um,
 generally


people
 will
 take
 that
 into
 heavy


consideration,
 right?
 It's
 like,
 you


know,
 this
 person
 who
 you've
 respected


for
 their
 research
 taste
 and
 execution


for
 so
 long
 is
 like
 now
 very
 excited
 by


this
 idea.
 Um,
 it's
 it's
 definitely


something
 that
 uh


that
 um
 yeah,
 you
 you
 you


people
 take
 into
 account.
 So,
 I
 think


there
 there's
 good
 top-down
 steering.
 At


the
 same
 time,
 you
 know,
 I
 think
 one


really
 cool
 thing
 about
 OpenAI
 is
 um


there
 bottom-up
 elements.
 Like
 we
 like


to
 be
 convinced
 that
 um


uh


you
 know,
 that
 we're
 wrong,
 right?
 And


and
 someone
 can
 just
 come
 with
 cold,


hard
 evidence.
 And
 many
 things
 like
 that


have
 turned
 into


core
 parts
 of
 our
 research
 roadmap.
 Just


things
 that
 no
 one
 was
 really
 kind
 of


trying
 to
 steer,
 but
 some
 researcher
 on


the
 ground
 had
 a
 heavy
 conviction
 in.


Um,
 and
 and
 that's
 also
 a
 really
 good


big
 delight
 to
 see.
</details>

**>>**: 是的，完全赞同。我最近在你接受的另一次采访中听到，即使在我们见证了模型发展以及其他公司的诸多动向之后，你们内部的研究路线图其实并没有真正改变。你们多长时间重新评估一次，甚至主动做出调整？我想随着周围的一切不断进步，这应该不是很多被动式的决策，但你们是如何思考这一过程的？
<details><summary>Original English</summary>
**>>**: Yeah,
 no,
 absolutely.
 I
 heard
 in
 a


recent
 interview
 that
 you
 gave
 that
 your


internal
 research
 roadmap
 hasn't
 really


changed
 um
 even
 through
 all
 that
 we've


seen,
 you
 know,
 with
 model
 development


and
 even
 other
 companies.
 Yeah.
 I
 guess


how
 often
 do
 you
 guys
 assess
 that,


reassess
 that,
 even
 like
 act


proactively?
 I
 assume
 it's
 not
 a
 lot
 of


reactive,
 you
 know,
 decision-making
 as


like
 other
 models
 come
 out.
 But
 how
 do


you
 like
 think
 through
 that
 process,


especially
 as
 everything
 around
 you
 just


continues
 to
 get
 better?
</details>

**>>**: 是的，我认为高层次的研究路线图应该是稳定的，人们需要有所依托，需要看到通向我们目标的路径。我很庆幸我们坚持了这个方向相当长的一段时间。但具体的实现细节会随着时间而变化。排期的先后顺序非常重要，相对资源的分配非常重要，一线具体的实施步骤也非常重要。我们会有促使我们重新审视这些问题的时间节点。其中一个例子就是进行算力分配的时候。
<details><summary>Original English</summary>
**>>**: Yeah,
 so
 I
 think
 the
 thing
 is
 um
 the


high-level
 research
 roadmap
 should
 be


stable,
 right?
 I
 think
 people
 need


something
 to
 ground
 in.
 People
 need
 to


see
 a
 path
 to
 what
 we're
 building.
 Um,


and
 I've
 been
 very
 happy
 that
 we
 stayed


the
 course
 for
 for
 a
 while.
 But
 the


implementation
 details
 can
 change
 over


time,
 right?
 And
 I
 think
 um


it's
 important
 to
 kind
 of
 like
 the
 the


sequencing
 will
 matter,
 right?
 The


relative
 resourcing
 will
 matter.
 And
 the


kind
 of
 exact
 steps
 on
 the
 ground
 will


matter.
 So,
 what
 we
 do
 is
 um
 I
 think
 we


have


kind
 of
 points
 in
 time
 that
 force
 us
 to


reconsider
 these
 things.
 So,
 uh
 one


example
 is
 when
 we
 do
 compute.
</details>

**>>**: 明白。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 这份工作的一部分就是弄清楚如何给各个项目分配算力。这是一个质疑和反思的时刻：我们是否真的把算力和人力用在了最高优先级的押注上？
<details><summary>Original English</summary>
**>>**: Um,
 one
 of
 the
 parts
 of
 the
 job
 is
 just


figuring
 out
 how
 to
 allocate
 computer


projects.
 And
 um


it's
 it's
 a
 time
 to
 kind
 of
 question


like
 are
 we
 really
 putting
 compute
 to


use
 and
 people's
 use
 at
 the
 highest


priority
 bets?
</details>

**>>**: 是的。你能进一步澄清一下你所说的高层次与更具体的实现细节之间的区别吗？比如高层次是指像“AGI 是我们的北极星”这样宽泛，还是比这更具体一些？顺便说一句，我一直在不停加油。
<details><summary>Original English</summary>
**>>**: Yeah.


And
 I
 guess
 could
 you
 clarify
 more
 what


you
 mean
 by
 Oh
 yeah.
 Yeah,
 I
 was
 like


I'm
 constantly
 adding
 oil.
 But
 clarify


what
 you
 mean
 by
 higher
 level
 versus


like
 the
 more
 implementation
 detail.


Like
 is
 high
 level
 as
 general
 as
 like


AGI?
 That's
 like
 our
 North
 Star
 or
 is
 it


more
 like
 granular
 than
 that?
</details>

### 组织架构与算力分配

**>>**: 在最高层面，我们有专注于预训练的组织，旨在赋予模型大量的世界知识；我们专注于 RL，教模型如何利用这些知识进行推理，把零散的洞见串联起来；最后是对齐和后训练。在这些领域中，我们始终在探索如何扩展主线，同时也在探索从根本上解锁不同扩展属性或更激进扩展属性的新押注。
<details><summary>Original English</summary>
**>>**: Um
 well
 yeah,
 I
 mean
 at
 the
 very
 highest


level,
 right?
 We
 have
 an
 org
 that


focuses
 on
 pre-training,
 right?
 Which
 is


you
 know
 giving
 models
 a
 lot
 of
 world


knowledge.
 We
 focus
 on
 RL
 like
 teaching


the
 models
 how
 to
 reason
 with
 that


knowledge,
 how
 to
 chain
 the
 little


insights
 together.
 Yeah.
 And
 then


finally
 um
 alignment
 and
 post-training,


right?
 And


um


we're
 always
 looking
 at
 both
 like
 how
 to


scale
 the
 mainline
 in
 each
 of
 these


domains
 and
 also
 new
 bets
 that


fundamentally


unlock
 either
 like
 different
 scaling


properties
 or
 more
 aggressive
 scaling


properties.
</details>

**>>**: 明白了。
<details><summary>Original English</summary>
**>>**: Got
 you.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 我听说每隔一到两个月，你们就会梳理大约 300 个可以推进的研究项目？当你决定真正对哪些项目加码、对哪些不加码时，是否有某种方法来磨练决策能力？毕竟肯定有许多才华横溢的研究人员提出了各种可行的研究想法。
<details><summary>Original English</summary>
**>>**: And
 so
 even
 in
 that
 I
 heard
 that
 every


one
 to
 two
 months
 you
 go
 through
 what?


Like
 300
 projects
 like
 research
 projects


that
 could
 be


uh
 you
 know
 followed
 through
 on.
 Is


there
 a
 way
 that
 you
 kind
 of
 hone
 that


decision
 making
 I
 assume
 as
 you
 like


decide
 what
 to
 actually
 double
 down
 on


and
 what
 not
 to
 since
 I
 assume
 there's
 a


lot
 of
 talented
 researchers
 who
 provide


possible
 ideas
 to
 pursue.
</details>

**>>**: 这完全是出于聚焦的精神。你可能听过这样一种说法，我们在 OpenAI 正在高度聚焦我们的押注，同时我们也在尝试进行更有针对性的指令式算力分配。我不喜欢对经理们进行微观管理。我认为赋予他们权力非常重要，直接把大块算力划拨给你想要支持的核心大押注。
<details><summary>Original English</summary>
**>>**: so
 I
 think
 really
 in
 the
 spirit
 of


uh
 focus.
 So
 one
 one
 narrative
 you
 might


have
 heard
 is
 you
 know
 we're
 we're


really
 focusing
 our
 bets
 at
 OpenAI
 and


um


we're
 also
 trying
 to
 do
 a
 little
 bit


more
 uh
 directive
 computer
 allocation
 as


well.
 So
 um
 I
 don't
 like
 micromanaging


my
 managers.
 I
 think
 one
 important
 thing


is
 to
 empower
 them
 but
 to
 just
 kind
 of


give
 compute
 big
 [clears throat]
 swaths


of
 compute
 to
 the
 big
 bets
 you
 want
 to


make.
</details>

**>>**: 这就是你说的指令式分配的意思吗？
<details><summary>Original English</summary>
**>>**: And
 then
 is
 that
 what
 you
 mean
 by


directive
 like
</details>

**>>**: 是的。但同时也给他们灵活的算力池，他们可以自由分配给他们相信的事情，或者根据我们规定的分配进行微调。我认为就是把每个组织少数几个（比如三到五个）押注绑定到核心研究路线图上，然后让经理和部门负责人放手去推进。
<details><summary>Original English</summary>
**>>**: Yeah,
 yeah,
 yeah.
 But
 but
 then
 also
 give


them
 kind
 of
 flexible
 pools
 of
 compute


which
 they
 can
 you
 know
 freely
 allocate


to
 things
 that
 that
 they
 believe
 in
 or


just
 kind
 of
 a
 fudge
 with
 the
 the


allocations
 that


that
 we
 prescribe.
 So,
 I
 think


yeah,
 I
 I
 think
 it's
 just


tying
 would
 say
 like
 a
 small
 number
 of


bets,
 say
 three
 to
 five
 bets
 from
 each


org


into
 the
 main
 research
 roadmap
 and
 then


really
 letting
 the
 the
 managers
 and
 org


leads
 take
 things
 from
 there.
</details>

### 研究潜质的甄别与研究人员的多样性

**>>**: 明白了，这很有道理。对于有潜力的新生代研究人员，在面试场景中，是否有特定的信号或方法让你识别出“这个人有潜力成为对组织产生特定影响的研究员”？还是主要看他们之前做过的研究，以此来决定他们是否能继续走下去？
<details><summary>Original English</summary>
**>>**: Got
 you.
 Okay,
 that
 makes
 sense.
 And
 I


guess
 for
 rising
 researchers,
 so


let's
 say
 in
 an
 interview
 setting,
 are


there
 specific
 tells
 or
 ways
 that
 you


can
 identify,
 okay,
 this
 person
 has


some,
 you
 know,
 potential
 of
 becoming
 a


researcher
 to
 impact
 an
 org
 in
 a


specific
 way
 or
 is
 it
 like
 just
 looking


at
 the
 previous
 research
 that
 they've


done
 and
 then
 that
 is
 what
 heavily


dictates
 whether
 they
 can
 actually


continue
 on?
</details>

**>>**: 在一个人来到 OpenAI 之前，这是一个很难判断的问题，确实如此。对于很多优秀的研究经理来说，他们随着时间推移与大量研究人员合作过，会形成一种直觉：比如他们说的话、他们提出的想法，是否切中要害，或者是否与你个人在思考的事情契合？所以存在这种直觉检验：他们的直觉是否与你的直觉一致？但一开始确实很难看准。通常在半年到一年内，谁的发展轨迹最强、谁能产生巨大影响力，就会变得非常清楚。所以老实说，这很难，但在 OpenAI 看到许多人经历研究成长之后，你就会对谁在哪些领域更有活力形成直觉。另外需要提到的一点是，并不是每个研究人员都是一样的，产生影响的方式有很多种。有的人拿到一个明确的想法，能比任何人都更快地落地实现；也有的人会提出那种看似过于疯狂、但其实又有道理的想法，能用全新的视角看待世界或开创完全不同的项目来打动你。产生影响力的方式有很多。
<details><summary>Original English</summary>
**>>**: Um,
 it's
 a
 hard
 problem
 before
 someone


comes
 to
 OpenAI.
 I
 think
 that's
 that's


genuinely
 true.
 Um,


I


I
 think
 for
 a
 lot
 of
 the
 best
 research


managers,
 you
 know,
 they


work
 with
 so
 many
 researchers
 over
 time


where
 you
 kind
 of
 develop
 an
 intuition


like
 you
 know,
 the
 things
 that
 they
 say,


the
 ideas
 that
 they
 bring
 up.


Are
 are
 those
 kind
 of
 do
 they
 hit
 hit


the
 same
 mark
 or
 like
 are
 they
 the


things
 that
 you
 would
 be
 thinking
 about


personally
 too?
 And
 so
 there's
 this
 gut


check
 of
 like,
 you
 know,
 does
 their


intuition
 match
 um


the
 same
 intuition
 that
 you
 have?
 Um
 but


it
 is
 really
 hard
 to
 tell
 out
 of
 the


gate.
 Usually
 in,
 you
 know,
 let's
 say


six
 months
 to
 a
 year,
 it's


pretty
 clear
 who
 who's,
 you
 know,
 has


the
 strongest
 trajectory
 and
 who's
 going


to
 make
 a
 lot
 of
 impact.
 Um,
 so
 yeah,


honestly
 um


I
 I
 I
 think
 it's
 a
 hard
 problem,
 but


just
 having
 seen
 a
 lot
 of
 people,
 you


know,
 go
 through


research
 development


at
 OpenAI,
 you
 develop
 an
 intuition
 for


you
 know,
 who's
 more
 peppy
 in
 different


areas.
 Yeah.
 And
 one
 thing
 to
 kind
 of


like
 just
 mention
 there
 is
 not
 every


researcher
 is
 the
 same.
 I
 think
 there's


a
 lot
 of
 different
 types
 of
 impact.


Yeah.
 There
 are
 the
 people
 who
 just
 take


an
 idea,
 it's
 very
 clear,
 and
 they'll


just
 implement
 it
 before
 anyone
 else.


They're
 also
 the
 people
 who
 just
 come
 up


with
 the
 kind
 of
 like
 crazy


almost
 too
 crazy,
 but


yeah,
 but
 somehow
 not
 that
 crazy
 and
 and


they
 they
 really
 convince
 you
 in
 a
 in
 a


different
 way
 of
 seeing
 the
 world
 or
 or


or
 another
 completely
 different
 type
 of


project.
 So,
 there's
 a
 lot
 of
 ways
 to


make
 an
 impact.
</details>

**>>**: 这很有帮助。进一步展开来说，你认为顶尖工程师与顶尖研究人员之间有相似之处吗？我常听说顶尖工程师（即使在小公司和初创企业）能把一个极其微小的想法一路推进到生产环境。我推测在研究中，是不是指把一个想法一路推进到通过产品交付给最终用户？还是说他们更纯粹地关注研究，而不考虑最终产品形态以及客户如何使用？
<details><summary>Original English</summary>
**>>**: Yeah.
 No,
 that's
 helpful.
 And
 so,
 I


guess
 elaborating
 on
 that,
 would
 you
 say


there
 are
 similarities
 that
 you
 would


see
 between,
 let's
 say,
 like
 top


engineers


and
 top
 researchers?
 Like
 I
 often
 hear


top
 engineers,
 even
 at
 like
 small


companies
 and
 startups,
 are
 ones
 who
 can


take
 an
 iota
 of
 an
 idea
 all
 the
 way
 to


production.
 I
 assume
 in
 research
 it's


like
 coming
 up
 the
 idea
 all
 the
 way
 to


how
 it's
 delivered
 to
 the
 end
 user


through
 like
 the
 product.
 Or
 do
 you


think
 it's
 more
 so
 they're
 focusing


solely
 on
 the
 research
 and
 not


considering
 like
 the
 end
 design,
 how


it's
 used
 by
 the
 customer?
</details>

**>>**: 研究的特点在于很多时候前方的道路是不明确的。区分研究人员的关键在于他们有多频繁地指向正确的方向，以及正如你所说的“品味”。在工程领域，有某些成熟的模式是行之有效的，比如想要构建一个某种形态的产品，工程原则通常非常相似。但对于研究而言，稍有不同的地方在于具备良好的研究品味、能够说服他人相信你所做的事情非常有前景，并将其整合进核心研究路线中。
<details><summary>Original English</summary>
**>>**: Well,
 I
 yeah,
 I
 mean,
 I
 guess
 the
 thing


about
 research
 is


many
 times
 the
 path
 forward
 is
 unclear.


And
 so,
 what
 differentiates
 researchers


is


how


often
 they're
 pointed
 in
 the
 right


direction
 and
 how
 like
 like
 you
 say


taste,
 right?
 I
 think
 in
 engineering


there
 are
 certain
 patterns
 that
 work.


Like,
 you
 know,
 if
 you
 want
 to
 build
 a


product
 that
 looks
 this
 way,


the
 engineering
 principles
 can
 be
 pretty


similar.
 Yeah.


But
 for
 research,
 I
 think
 the
 thing


that's
 slightly
 different
 is
 just
 this


ability
 to


you
 know,
 have
 good
 research
 taste
 to


convince
 other
 people
 that


what
 you're
 doing
 is
 promising.
 Um


and
 then,
 yeah,
 again,
 to
 just
 kind
 of


integrate
 it
 into
 the
 core
 research


room.
 Yeah.
</details>

**>>**: 明白了。
<details><summary>Original English</summary>
**>>**: Got
 you.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

### 基准刷榜与评测危机

**>>**: 太好了。看起来我们的蔬菜处理完了，现在需要同时进行多项操作了。
<details><summary>Original English</summary>
**>>**: Great.
 Okay,
 it
 seems
 like
 we're
 done


with
 the
 vegetables,
 so
 now
 we
 have
 to


multitask.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 我们要往锅里倒些水，作为汤的底汤。在右上角，对，就是这里。拧开盖子。我往这里倒一些。你也可以倒一些。在汤慢炖、加入蔬菜的同时，我们来煎大虾。好的。
<details><summary>Original English</summary>
**>>**: So,
 we're
 going
 to
 pour
 some
 water
 into


our
 pots
 to
 get
 the
 base
 of
 the
 soup


going.
 So,
 in
 the
 top
 right,
 yeah,
 here.


And
 then
 just
 twisting
 this
 off.
 So,
 I'm


going
 to
 pour
 some
 here.


And
 you
 can
 use
 some
 as
 well.


And
 while
 we
 have
 this
 simmer,
 and
 we'll


add
 the
 veg,
 we'll
 cook
 our
 prawns
 here.


Okay.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Um
</details>

**>>**: 让我快速清理一下。目前看起来一切顺利。洋葱和蘑菇煎出了一些焦色。把这个打开。一个看起来非常有趣的领域是评测（evals）。具体来说，是否有过这样的情况：仅仅凭感觉测试（vibe checks）觉得模型表现非常好，但在实际基准测试中表现却非常糟糕？还是说这两者高度相关，比如 SWE-bench Verified 分数高，感觉上它处理编程任务的能力也必定非常强？
<details><summary>Original English</summary>
**>>**: Yeah,
 so
 let
 me
 clean
 this
 up
 real


quick.


Looks
 like
 it's
 going
 great
 so
 far.
 I


feel
 like
 saute
 got
 some
 color
 on
 the


onions
 and
 and
 mushrooms.
 So,
 yeah,


let's
 turn
 this
 on.


I
 guess
 one
 aspect
 or
 area
 that
 seems


very
 interesting
 are
 evals.
 Um
 and
 more


specifically,
 have
 there
 been
 instances


where
 you've
 seen
 like
 through
 just
 vibe


checks
 that
 it
 was
 a
 really
 good,
 but
 on


the
 actual
 benchmark
 it
 like
 performs


very
 poorly?
 Or
 do
 you
 think
 it's
 like


heavily
 correlated
 that,
 you
 know,
 if


your
 Sweet
 Bench
 Pro
 is
,
 you
 know,
 a


high
 number,
 then
 it's
 like
 your
 vibe


check
 on
 it
 doing
 coding
 tasks
 is
 also


really,
 really
 high?
</details>

**>>**: 不，不是的，确实存在这种脱节的现象。在内部我们称之为“刷榜”（bench maxing），我不确定外界是否也这么用。你完全可以对某些特定分布过拟合，而这并不能反映真实的泛化能力。因为简单粗暴的做法就是针对基准找出一堆极为相似的样本，在这些样本上进行过度训练。除此以外，该领域另一个令人担忧的问题是，公认的黄金标准基准数量很少。
<details><summary>Original English</summary>
**>>**: No,
 no.
 I
 mean,
 I
 think
 there
 is
 this


phenomenon.
 Um
 you
 know,
 I
 I
 think


internally,
 I'm
 not
 sure
 if
 this
 is
 a


externally
 used
 word,
 but
 yeah,
 just


like
 bench
 maxing,
 you
 know?
 Um
 yeah,
 I


think
 I
 think
 you
 can
 kind
 of
 overfit


onto
 certain
 distributions.
 Um
 and


it
 won't
 be
 reflective
 how
 you
 how
 well


you
 generalize,
 right?
 Because
 um
 I


mean,
 easy
 ways
 to
 do
 this
 are,
 you


know,
 you
 take
 a
 benchmark
 and
 you
 just


find
 like
 very,
 very,
 very
 similar
 types


of
 instances
 to
 the
 benchmark
 and
 you


overtrain
 on
 these
 instances.
 Um
 So,
 I


think
 um


beyond
 that,
 the
 the
 other
 scary
 thing


in
 the
 field
 is
 the
 the
 number
 of


canonical
 gold
 standard
 benchmarks
 is


low.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 我们确实处在一场评测危机中，大家耳熟能详的所有优秀评测，比如 SAT 等等，全部都被彻底饱和了。我们急需找到对模型进行基准测试的好方法。像 Codex 这类工具的一大优势就是极大加快了评测的迭代速度，一个人就能快速搭建出高质量的评测集。此外，将模型实际部署出去也是一种有趣的评测方式，可以在用户使用时直接观察评测效果。在数学、编程和软件工程领域，你可以从这种广泛的实际部署中感知到模型在何处崩溃、能承受多长的任务周期。
<details><summary>Original English</summary>
**>>**: And
 we
 really
 are
 kind
 of
 in
 an
 evals


crisis,
 right?
 Where
 all
 the
 really


great


uh
 evals
 that
 we
 we
 all
 know
 like


growing
 up
 like
 taking
 the
 SAT
 or


those
 those
 are
 all
 fully
 saturated.
 And


um
 we
 really
 need
 to
 find
 good
 new
 ways


to
 benchmark
 the
 models.
 I
 think
 one


great
 thing
 about
 tools
 like
 Codex
 is


they
 really
 enabled
 the
 fast
 iteration


of
 of
 evals.
 Like
 we're
 able
 to
 just


kind
 of
 have
 one
 person
 just
 very


quickly
 put
 together
 a
 very
 high-quality


eval.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 另一个有趣之处就在于部署模型带来的直接反馈。在数学和编程这类任务中，你能了解它们执行任务的跨度上限。
<details><summary>Original English</summary>
**>>**: Um
 another
 kind
 of
 interesting
 thing
 of


just
 being
 able
 to
 deploy
 your
 models
 is


you
 can
 just
 see
 them
 eval
 as
 people
 are


doing
 things
 with
 them,
 right?
 Um,
 one


of
 the
 great
 things
 is,
 you
 know,
 in


math
 and
 coding
 and
 software,
 like


you
 get
 a
 sense
 for
 like
 where
 where


they
 fall
 over,
 what
 the
 task
 horizon


they
 can
 do
 from
 from
 this
 like
 general


very
 broad-based
 deployment.
 So.
</details>

### 评测团队与模型优化团队的机制隔离

**>>**: 是的，这很有启发。现在把虾放入热油中煎上色。进一步追问一下，你如何在取得优异基准成绩的同时，又不陷入你所说的“刷榜”？因为你希望保持真诚、不投机取巧，但如果得分比竞品低，消费者可能会觉得“你的分数不高，模型可能就没那么好”。你如何平衡这两者的冲突？
<details><summary>Original English</summary>
**>>**: Yeah,
 no,
 that's
 that's
 helpful.
 Now,


we'll
 just
 add
 the
 prawns
 to
 the
 oil
 and


get
 some
 color
 on
 it.
 Um.
 Yeah,
 and
 so
 I


guess
 double-clicking
 onto
 that
 um
 how


do
 you
 balance
 both
 doing
 well
 on
 these


benchmarks
 but
 also
 not,
 you
 know,
 like


benchmark
 maxing
 as
 you
 said.
 Cuz
 I


assume
 you
 want
 to
 be
 most
 honest
 and


like
 not
 kind
 of
 cheat
 the
 system.
 But


if
 you
 have
 like
 lower
 scores,
 let's


say,
 than
 a
 competitor
 or
 from
 other


models,
 to
 the
 consumer
 maybe
 like,


"Wait,
 your
 score
 isn't
 that
 great,
 so


the
 model
 just
 probably
 isn't
 that


good."
 Like
 how
 do
 you
 balance
 both
 of


those
 dichotomies?
</details>

**>>**: 关键在于必须基于具有代表性的混合评测集来运作，并且持续投入创建新的评测。有一种理念是：一个评测一旦公开发布到世界上，它就不再是一个好的评测了。另外一点是与外部机构合作构建评测。在很多高难度的数理评测中，我们与外部组织合作，由他们为我们打造黄金标准。有一种非常有趣的理念，就是把构建评测的团队与负责优化……
<details><summary>Original English</summary>
**>>**: Yeah,
 I
 mean,
 I
 think
 the
 thing
 is,
 you


just
 really
 have
 to
 operate
 over


representative
 mixtures
 of
 evals
 and


always
 investing
 in
 creating
 new
 evals.


And
 yeah,
 really
 just
 like
 there's
 this


philosophy
 of
 once
 an
 eval
 is
 out
 in
 the


world,


then
 it's
 it's
 just
 already
 not
 a
 good


eval.


And
 I
 think
 one


one
 thing
 is,
 also
 just
 kind
 of


partnering
 with
 external
 organizations


to
 create
 evals.
 So,
 you
 know,
 in
 in


many
 of
 the
 kind
 of
 hard
 math
 and


science
 evals,


we've
 partnered
 with
 external


organizations
 and
 they've
 been
 able
 to


kind
 of
 craft
 gold
 standards
 there
 for


us.
 So,
 yeah,
 I
 think
 um


there's
 a
 kind
 of
 interesting
 philosophy


of
 separate
 the
 teams
 that
 are
 creating


the
 evals
 from
 the
 teams
 that
 are


optimizing
</details>

**>>**: 构建，好的。
<details><summary>Original English</summary>
**>>**: building,
 okay.
</details>

**>>**: ……模型本身的团队彻底分开。这样双方的利益动机就不会混在一起。评测团队的目标就是构建对模型来说极难的评测。这形成了一种天然的对抗机制，避免了自我欺骗，两个团队之间的激励机制得到了正确的对齐。
<details><summary>Original English</summary>
**>>**: the
 models
 themselves.
 Because
 that
 way


you
 don't
 like
 coincentivize
 them,


right?
 Like
 the
 the
 way
 the
 evals
 team


can
 work
 is
 they're
 trying
 to
 build


evals
 that
 are
 hard
 for
 the
 models.
 So,


there's
 this
 inherently
 adversarial


process
 where


you're
 you're
 not
 kind
 of
 cheating


yourself.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 两个团队之间的激励在某种程度上以正确的方式对齐了。
<details><summary>Original English</summary>
**>>**: The
 the
 incentives
 are
 somewhat


aligned
 in
 the
 right
 way
 between
 the
 two


teams.
</details>

**>>**: 你们也会参与构思、甚至决定应该与第三方合作开发哪些评测吗？
<details><summary>Original English</summary>
**>>**: Yeah.
 Yeah.
 do
 kind
 of
 also
 contribute


and
 help
 in
 the
 ideation
 process
 or
 even


deciding
 what
 Evals,
 you
 know,
 you


should
 work
 with
 a
 third
 party
 on
 to


develop.
</details>

**>>**: 是的。我和 Jakub 的很多工作也包括引导评测的发展方向。我们会发现某些能力缺陷或我们渴望拥有的能力，而每一种能力的背面都是一项评测：你需要某种评测来衡量是否准确激发了你想要的能力，且激发得足够好。这需要大量的引导，让所有人在评测上达成共识也是一项艰难的工作。
<details><summary>Original English</summary>
**>>**: Yeah.
 Yeah.
 So,
 I
 mean,
 I
 think
 a
 lot
 of


the
 work
 that
 Yacoub
 and
 I
 do
 also


involves
 just
 kind
 of
 uh
 steering
 the


direction
 that
 Evals
 go.
 Yeah.
 I
 think


we'll
 notice
 certain
 gaps,
 right?
 Or


certain
 kind
 of
 capabilities
 um
 that
 we


want.
 And
 every
 capability
 on
 the
 foot


side
 is
 an
 Eval,
 right?
 You
 need
 some


kind
 of
 Eval
 that
 measures
 if
 you


elicited
 exactly
 what
 you
 want
 and
 you


want
 it
 well.
 So,
 yeah,
 I
 think
 uh


yeah,
 it's
 um


it's
 takes
 a
 lot
 of
 steering
 and
 just
 to


get
 everyone
 on
 the
 same
 page
 with
 Evals


is
 also
 a
 lot
 of
 tough
 work.
</details>

### 与 Jakub 的协作与“参差前沿”

**>>**: 确实如此。关于 Jakub，你在之前的采访中提到过他是一个非常幽默的人。关于和他共事，你有什么之前没分享过的趣事吗？你说过你们配合得非常默契，在研究上的讨论效率极高，推动前沿时帮助很大。除了幽默之外，还有其他趣事吗？
<details><summary>Original English</summary>
**>>**: Yeah.
 No,
 that's
 that's
 fair.
 I
 guess
 on


Yacoub,
 you
 said
 in
 a
 previous
 interview


that
 he's
 a
 very
 funny
 guy.


Do
 you
 have
 any
 fun
 stories
 that
 maybe


you
 haven't
 shared
 about
 working
 with


him?
 Cuz
 you
 also
 state
 that
 you
 guys


align
 very
 well.
 So,
 your
 discussions


even
 on
 research
 are
 very
 efficient
 and


help
 a
 lot
 when
 like
 driving
 towards
 the


frontier.
 I
 guess
 like
 on
 the
 opposite


side
 of
 being
 very
 funny,
 are
 there


things
 that
 you're
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 你问到趣事，他昨天跟我讲了个笑话，我觉得非常好笑。在很多方面我们共同管理着研究工作。据说有个研究员来找他说：“感觉我现在手下就像有一支由非常愚蠢的 IOI 形式主义者组成的军队。”Jakub 回复说：“感觉那正是我目前的处境。”
<details><summary>Original English</summary>
**>>**: You
 you
 asked
 about
 like
 a
 funny
 story.


Well,
 he
 told
 me
 this
 joke
 yesterday,


which
 I
 thought
 was
 very
 funny.
 I
 mean,


in
 many
 ways
 we
 kind
 of
 jointly
 manage


the
 the
 research
 efforts.
 And


you
 know,
 apparently
 some
 researcher


came
 up
 to
 him
 and
 was
 like,


you
 know,
 um


it
 feels
 like
 I
 now
 just
 have
 an
 army


of,
 you
 know,
 really
 dumb
 I
 O
 I
 like


formalists.
 Yeah.
 And
 Yacoub
 was
 like,


that
 feels
 like
 already
 the
 situation


I'm
 in.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 他就是有着极其犀利的讽刺和幽默感。
<details><summary>Original English</summary>
**>>**: You're
 like,
 so
 uh
 yeah,
 no,
 he's
 he's


just
 like
 brutally
 sarcastic
 and
 funny.


Yeah.
</details>

**>>**: 职场中有幽默感真棒，尤其是在推动重大工作前沿时能起到很好的调节作用。这也让我想起了一种奇怪的现象：模型在 IMO 甚至 IOI 上表现极佳，但在人类能轻松完成的某些日常平淡任务上却表现挣扎。对此你怎么看？
<details><summary>Original English</summary>
**>>**: Yeah,
 that's
 great.
 It's
 great
 to
 have


humor
 in
 the
 workplace
 and
 it's
 good
 to


bounce
 out,
 especially
 as
 you're
 pushing


the
 frontier
 on
 very
 important
 work.
 Um


but
 that
 also
 brings
 to
 mind
 one
 kind
 of


weird
 scenario
 of
 how
 models
 can
 perform


very
 well
 on,
 let's
 say,
 the
 IMO
 or
 even


the
 I
 O
 I,
 but
 may
 struggle
 with
 some


more
 mundane
 tasks
 that
 a
 human
 can


easily
 do.
 So,
 I
 guess
 how
 do
 you
 feel


about
</details>

**>>**: 对模型来说符合直觉的东西，往往对人类并不直观。关于“参差前沿”（jagged frontier）这个比喻讨论得很多，模型天然擅长某些事情，可能是基于它见过的数据，或者基于我们能更容易教会它的东西。我认为这很大程度上也归结为上下文。模型所拥有的上下文并不多。
<details><summary>Original English</summary>
**>>**: Yeah.
 Yeah.
 I
 mean,


ultimately,
 I
 think


what's
 intuitive
 for
 the
 models
 is
 often


not


um
 that
 intuitive
 for
 the
 humans.
 Like,


uh
 there's
 there's
 a
 lot
 of
 this


jagged
 frontier
 analogy
 where
 um
 there's


some
 things
 that
 the
 models
 just


inherently,
 you
 know,
 based
 on
 maybe
 the


data
 it
 sees
 or
 um


kind
 of
 the
 the
 things
 that
 we
 we
 can


teach
 it
 more
 easily,
 yeah,
 it's
 just


good
 at.
 Um
 I
 actually
 think,
 you
 know,


a
 lot
 of
 a
 lot
 of
 it
 boils
 down
 to
 also


just
 context,
 right?
 Um
 the
 models
 don't


have
 a
 lot
 of
 context
 that
 it
 can
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 当然，视觉对人类来说是更具生物学天然本能的。所以确实存在某些参差的能力是模型比人类更擅长的，反之亦然。但在上下文方面，能够从单一任务中吸取教训并应用到未来的任务中，这种能力是目前很多 AI 从业者正在努力攻克的，而对人类来说这非常自然。
<details><summary>Original English</summary>
**>>**: Um
 vision,
 of
 course,
 is
 something


that's
 more
 naturally
 biologically
 wired


for
 humans.
 Um


and
 so,
 yeah,
 I
 think
 there
 are
 there's


just
 certain
 kind
 of
 jagged
 capabilities


that
 models
 are
 better
 at
 than
 humans


and
 vice
 versa.
 Um
 but
 I
 also
 think,
 you


know,
 context,
 just
 um
 being
 able
 to


take
 a
 single
 task,
 learn
 lessons
 from


it,
 and
 apply
 them
 to
 future
 tasks,
 um


that
 capability
 is
 something
 that,
 you


know,
 a
 lot
 of
 people
 are
 in
 AI
 working


towards
 right
 now.
 Um


but
 it's,
 yeah,
 very
 natural
 for
 humans.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

### 上下文窗口与上下文压缩

**>>**: 关于上下文这一点，很多人常提到的唾手可得的方案就是单纯扩大上下文窗口，提供更多示例以提升模型表现。但实现它应该存在更多复杂性，因为即便有很大的上下文窗口和大量上下文，也可能会出现臃肿，甚至如大家所说的“上下文腐烂”（context rot）。你们是如何处理这个过程的？
<details><summary>Original English</summary>
**>>**: And
 on
 the
 context
 point,
 um
 a
 very


low-hanging
 fruit
 example
 that
 many


people
 will
 say
 is
 just
 to
 increase
 the


context
 window
 to
 provide
 more
 um


examples
 so
 the
 model
 can
 perform.
 But


do
 you
 think
 I
 assume
 there's
 more


complexity
 on
 how
 to
 actually
 enable,


since
 even
 with
 a
 large
 context
 window


and
 a
 lot
 of
 context,
 there
 could
 be


bloat
 or
 even
 just
 a
 lot
 of
 like
 context


rot,
 as
 people
 have
 said.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 你们如何经历这个过程……
<details><summary>Original English</summary>
**>>**: So,
 how
 do
 you
 go
 through
 that
 process


of
</details>

**>>**: 解决超长任务期学习的标准方法，通常就是天真地扩大上下文窗口，这可以理解。但正如你所说，实现长上下文与“把长上下文做好”之间存在很大差异。有许多大海捞针式的评估来衡量这一点。但除此之外，在工程和研究层面上也可以采用许多巧妙的捷径。例如，现在的很多编程产品都具备压缩（compaction）功能，你可以压缩提炼出的洞见或工作状态，这规避了单纯依赖原生超长上下文所需构建的极其困难且昂贵的基础原语。
<details><summary>Original English</summary>
**>>**: Yes,
 so
 I
 mean,
 I
 think
 there's
 kind
 of


the
 canonical
 way
 you
 would


solve
 for
 very
 long
 horizon
 learning,


which
 is,
 you
 know,
 you
 just
 naively


increase
 your
 context
 window,
 right?
 And


um
 I
 mean,
 that
 makes
 sense.
 I
 think


there's
 a
 difference
 between


implementing
 long
 context
 and


implementing
 long
 context
 well,
 like
 you


said.
 Um
 and
 there
 is
 a
 lot
 of
 kind
 of


like
 needle-in-a-haystack
 style


evaluations
 to
 measure
 that.
 Um
 but
 I
 do


think
 beyond
 that,
 um


there
 are
 also
 a
 lot
 of,
 in
 some
 sense,


like
 engineering
 and
 research
 shortcuts


that
 you
 could
 take.
 Um
 so,
 you
 like,
 uh


many
 many
 coding
 products
 today
 have


features
 like
 compaction,
 right?
 Where


um,
 you
 can
 compress
 kind
 of
 either


insights
 or
 working
 state
 and


stuff
 like
 that,
 you
 know,
 it
 just


shortcuts
 a
 lot
 of
 the
 the
 very
 brutally


difficult
 and
 expensive
 um,
 primitives


that
 you
 have
 to
 build
 with
 just
 native


long
 context.
</details>

**>>**: 明白了。
<details><summary>Original English</summary>
**>>**: Got
 you.
</details>

**>>**: 太好了。
<details><summary>Original English</summary>
**>>**: Great.
</details>

### 喷枪炙烤与通往 AGI 的重大押注

**>>**: 好了，现在我们要进入有趣的部分了。我们稍微调小一点火，往锅里再添一点油，然后用火枪炙烤一下虾，让它增添更多风味。
<details><summary>Original English</summary>
**>>**: Okay,
 now
 we're
 going
 to
 do
 the
 fun


part.
 So,
 um,
 let's
 lower
 the
 heat
 a


little
 bit
 and
 then
 add
 a
 little
 bit


more
 oil
 to
 the
 pan.
 Um,
 and
 then
 we'll


torch
 the
 the
 shrimp
 the
 prawns
 to
 get
 a


little
 more
 flavor
 in
 there.
</details>

**>>**: 好。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

**>>**: 我先在我的锅里示范一下。
<details><summary>Original English</summary>
**>>**: So,
 I'll
 first
 do
 it
 on
 on
 my
 pan
 to


show
 you
 what
 it
 looks
 like.
</details>

**>>**: 但是……
<details><summary>Original English</summary>
**>>**: But
</details>

**>>**: 单样本学习（One-shot learning）。
<details><summary>Original English</summary>
**>>**: One shot
 learning.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 确实。
<details><summary>Original English</summary>
**>>**: Yeah,
 indeed.
</details>

**>>**: 等等，我还没倒波旁威士忌呢。
<details><summary>Original English</summary>
**>>**: Wait,
 I
 I
 didn't
 pour
 any
 bourbon.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 好的，等等。我们倒大约四分之一杯。好的。倒进去，关火，然后用喷枪炙烤。
<details><summary>Original English</summary>
**>>**: Okay,
 wait.
 So,
 let's
 pour
 like


a
 fourth.


Okay.


And
 then


pour
 it
 in.
 Heat
 is
 off.


And
 then
 torch
 it.
</details>

**>>**: 太棒了。
<details><summary>Original English</summary>
**>>**: Awesome.
</details>

**>>**: 很好。
<details><summary>Original English</summary>
**>>**: Great.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: All
 right.
</details>

**>>**: 好了，我觉得我学会了。
<details><summary>Original English</summary>
**>>**: Okay,
 I
 think
 I
 got
 this.
</details>

**>>**: 行，你想自己试试吗？
<details><summary>Original English</summary>
**>>**: Okay,
 yeah.
 So,
 do
 you
 want
 to
 do
 it


your
 Yeah.
</details>

**>>**: 好啊，来。
<details><summary>Original English</summary>
**>>**: Yeah,
 yeah.
 And
</details>

**>>**: 倒大约四分之一杯的一半左右，弄好后我把喷枪递给你。
<details><summary>Original English</summary>
**>>**: So,
 pour
 it
 to
 like
 half
 of
 the
 fourth


cup
 and
 then
 once
 you
 have
 that,
 I
 can


give
 this
 to
 you.
</details>

**>>**: 完美。
<details><summary>Original English</summary>
**>>**: Perfect.
</details>

**>>**: 很好。关火了。关火之后你可以再点火。
<details><summary>Original English</summary>
**>>**: Great.
 So,
 it's
 off.


And
 then
 once
 that's
 off,
 you
 can
 turn


it
 back
 on.
</details>

**>>**: 完美，好的。
<details><summary>Original English</summary>
**>>**: Perfect.
 Okay.
</details>

**>>**: 现在你拿着这个，按一下这个按钮点火。
<details><summary>Original English</summary>
**>>**: And
 then
 now,
 do
 you
 want
 to


hold
 on
 this
 and
 just
 press
 this
 button
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

**>>**: 点着它。
<details><summary>Original English</summary>
**>>**: to
 fire
 it
 up.
 Yeah.
</details>

**>>**: 酷。完美。很好。我正在炙烤它。火稍微有点小，不过挺好。太棒了，然后我们可以重新开火。
<details><summary>Original English</summary>
**>>**: Cool.


Yeah,
 perfect.
 Great.
 Okay.


I'm
 burning
 it.


It's
 a
 little
 light,
 but
 yeah.


Great.
 And
 then
 we
 can
 turn
 on
 the
 heat


again.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 然后我们把酒精煮挥发掉。
<details><summary>Original English</summary>
**>>**: And
 then
 we'll
 just
 cook
 off
 the


alcohol.
</details>

**>>**: 好的，太棒了。
<details><summary>Original English</summary>
**>>**: Okay.
 Great.
 Great.
 Great.
</details>

**>>**: 太好了。感觉如何？
<details><summary>Original English</summary>
**>>**: Great.
 How
 How
 are
 you
 feeling?
</details>

**>>**: 你知道的……
<details><summary>Original English</summary>
**>>**: You
 know
</details>

**>>**: 太棒了。
<details><summary>Original English</summary>
**>>**: Great.
 Great.
</details>

**>>**: 基本上所有东西都快煮好了。
<details><summary>Original English</summary>
**>>**: Basically
 there
 cooking
 everything.
 So


Okay.
</details>

**>>**: 太棒了。关于研究方向与目标，你认为目前是否仍有大量唾手可得的成果，或者通过对现有工作进行细微优化就能获得很大提升？还是说现在必须做出大量完全全新的研究押注？
<details><summary>Original English</summary>
**>>**: Awesome.


Yeah,
 and
 I
 guess
 in
 terms
 of
 research


ideas
 and
 what
 to
 work
 towards,
 do
 you


think
 there's
 still
 a
 lot
 of
 low-hanging


fruit
 or
 ideas
 that
 can
 still
 be


improved
 a
 lot
 through
 just
 optimizing


small
 parts
 of
 already
 implemented
 work


or
 do
 you
 think
 right
 now
 there
 has
 to


be
 a
 lot
 of
 research
 that
 are
 completely


new
 bets
 that
 people
 take?
</details>

**>>**: 这是个非常好的问题。我觉得会有新的押注，但可能不会很多。从某种意义上说，希望大家能感受到 AGI 很快就要到来了。每个人都看到这些模型变得极其强大。如果认真去想象其背后的影响，我们正越来越接近一个模型能够自主提出更多创新的世界。
<details><summary>Original English</summary>
**>>**: Um
 yeah,
 that's
 a
 really
 great
 question.


I
 feel
 like


there
 are
 new
 bets,
 but
 probably
 not


that
 many.
 Yeah,
 um
 in
 some
 sense
 like


uh


hopefully
 you
 feel
 like,
 you
 know,
 AGI


is
 coming
 soon,
 right?
 And
 um
 I
 think


everyone
 sees
 that
 these
 models
 are


getting
 really
 capable,
 and
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 随着更多底层创新的涌现。
<details><summary>Original English</summary>
**>>**: with
 more
 of
 the
 innovation
 funder
 out.
</details>

**>>**: 是的，如果它们能够进行自我维持的研究，这是我们为研究工作设定的重大组织目标之一。
<details><summary>Original English</summary>
**>>**: Yeah,
 if
 they
 can
 kind
 of
 do


self-sustaining
 research,
 this
 is
 one
 of


the
 big
 or
 goals
 that
 we've
 set
 for
 for


our
 research
 work.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 所以我认为真正核心的是：在那一刻到来之前，是否存在重大的押注？
<details><summary>Original English</summary>
**>>**: And
 and
 so
 I
 think
 like


you
 know,
 what
 really
 matters
 is
 are


there
 big
 bets
 before
 that
 point
 in


time?
</details>

**>>**: 明白。
<details><summary>Original English</summary>
**>>**: Got
 it.
</details>

**>>**: 窗口期很短，但我们仍在尝试一些非常重要的想法。
<details><summary>Original English</summary>
**>>**: And
 um
 I
 I
 think
 the
 window
 is
 small,


but
 there
 are
 still
 like
 some
 pretty


significant
 ideas
 we're
 trying
 out.
</details>

**>>**: 有些研究人员表示，要实现 AGI，我们还需要两到三个重大突破，比如持续学习或其他构想。你赞同这一观点吗？还是认为过程并没有“提出三种完全不同的范式”那么激进？
<details><summary>Original English</summary>
**>>**: Yeah.
 I
 mean,
 there've
 been
 some


researchers
 who
 have
 stated
 that
 to
 get


to
 AGI,
 we
 still
 need,
 let's
 say
 like


two
 or
 three
 more
 breakthroughs,
 if
 you


like
 continual
 learning
 or
 some
 other


ideas.
 Um
 do
 you
 follow
 that
 same
 view


perspective,
 or
 do
 you
 think
 it's
 kind


of
 more
 so
 like
 not
 as
 drastic
 as
 coming


up
 with
 like
 three
 completely
 different


paradigms?
</details>

**>>**: 我不知道我是否持有同样的认知框架。持续学习确实是一个必须解锁的基本原语。技术路径有很多，我不确定何种程度算作突破，何种不算，但显然有很多射门尝试的机会，我非常确信它们会起作用。
<details><summary>Original English</summary>
**>>**: Um


yeah,
 I
 mean,
 I
 I
 don't
 know.
 I
 I
 don't


know
 if
 I
 have
 that
 same
 framing.
 Like


continual
 learning
 is
 a
 a
 basic


primitive
 that
 you
 have
 to
 unlock.
 Yeah.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 技术非常多，我们正在测试其局限性。我不知道什么才算作突破，但显然有很多射门尝试的机会，我非常确信它们会起效。
<details><summary>Original English</summary>
**>>**: Uh
 there's
 so
 many
 different
 techniques.


I
 I
 don't
 know
 um


that
 yeah,
 I
 think,
 you
 know,
 we're


we're
 trying
 a
 lot
 of
 in
 the
 limitations


of
 it.
 I
 don't
 know
 what
 would
 consider


as
 a
 breakthrough
 versus
 not,
 but
 I


think
 there
</details>

**>>**: 显然有很多射门机会，我很确定它们会成功。
<details><summary>Original English</summary>
**>>**: clearly
 many
 shots
 on
 goal,
 and
 I
 I
 I'm


pretty
 sure
 they'll
 work.
</details>

**>>**: 太好了，好的。
<details><summary>Original English</summary>
**>>**: Great.
 Okay.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 虾基本煮好了。
<details><summary>Original English</summary>
**>>**: Great.
 Okay,
 so
 the
 shrimp
 is
 basically


done.
</details>

**>>**: 太棒了。
<details><summary>Original English</summary>
**>>**: Awesome.
</details>

**>>**: 你想再炙烤一次让颜色更漂亮吗？
<details><summary>Original English</summary>
**>>**: Okay.
 So,
 do
 you
 want
 to
 do
 the
 flambé


thing
 again
 to
 get
 more
 color?
</details>

**>>**: 来吧，好的。
<details><summary>Original English</summary>
**>>**: Let's
 do
 it.
 Yeah.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 我来……
<details><summary>Original English</summary>
**>>**: I'll
 I'll
</details>

**>>**: 把火稍微开大一点，我再加点油。
<details><summary>Original English</summary>
**>>**: Turn
 on
 the
 heat
 a
 little
 bit,
 and
 then


let
 me
 get
 some
 more
 oil.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Great.
</details>

**>>**: 是的，因为想要上点深色。我的锅里已经上色了。给。太好了，希望这次能再来一个镜头。好的。
<details><summary>Original English</summary>
**>>**: Yeah,
 cuz
 you
 want
 to
 get
 like
 some
 dark


color.
 I
 think
 mine
 has.
 And
 here.


Great.
 And
 then
 we
 can
 hopefully
 get


another
 shot.


Okay.
</details>

**>>**: 完美。稍等一分钟。
<details><summary>Original English</summary>
**>>**: Perfect.
 minute.
</details>

**>>**: 好的，你想先来吗？
<details><summary>Original English</summary>
**>>**: Yeah.


Do
 you
 want
 Do
 you
 want
 to
 go
 first?
</details>

**>>**: 额……
<details><summary>Original English</summary>
**>>**: Um
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 一样多的酒？
<details><summary>Original English</summary>
**>>**: Same
 same
 amount
 of
 beer.
</details>

**>>**: 对。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 一样的量。
<details><summary>Original English</summary>
**>>**: Same
 amount.
</details>

**>>**: 我们希望火能烧起来，刚才火候好像不够……是的。
<details><summary>Original English</summary>
**>>**: We
 could
 hopefully
 get
 cuz
 I
 think
 the


heat
 wasn't
 as


Yeah.
</details>

**>>**: 好的，我觉得可以倒进去了。
<details><summary>Original English</summary>
**>>**: Okay.
 I
 think
 we
 put
 it
 in.
</details>

**>>**: 好的，成了，按按钮。
<details><summary>Original English</summary>
**>>**: Yeah.
 I
 think
 There
 we
 go.


Let's
 press
 the
 button.
</details>

**>>**: 太棒了。
<details><summary>Original English</summary>
**>>**: Great.
</details>

**>>**: 成了。
<details><summary>Original English</summary>
**>>**: There
 we
 go.
</details>

**>>**: 出来了。
<details><summary>Original English</summary>
**>>**: There
 it
 is.
</details>

**>>**: 质感很棒。
<details><summary>Original English</summary>
**>>**: It's
 good
 texture.
</details>

**>>**: 是的，确实。增添了很好的风味。让我尝尝，味道会很棒的。
<details><summary>Original English</summary>
**>>**: Yeah.


Indeed.


And
 it's
 like
 add
 some
 good
 flavor.


Here,
 let
 me
 try
 it.
 It'll
 be
 good.
</details>

**>>**: 好。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

**>>**: 来看看。太棒了。来看看最终成品会是什么样。
<details><summary>Original English</summary>
**>>**: Yeah,
 let's
 see.


Great.


All
 right,
 let's
 see
 what
 it's
 going
 to


look
 like.
</details>

**>>**: 哇，成了。好的。
<details><summary>Original English</summary>
**>>**: Ooh.


There
 it
 is.


All
 right.
</details>

**>>**: 我们进入最后冲刺阶段了。
<details><summary>Original English</summary>
**>>**: But
 we're
 in
 the
 final
 stretch.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 虾全煮熟了。
<details><summary>Original English</summary>
**>>**: shrimp
 all
 cooked.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

### 多模态架构与统一模型

**>>**: 过了火。现在稍微煮一下，然后我们应该把蔬菜加到汤水里。
<details><summary>Original English</summary>
**>>**: Some
 fire.
 So,
 now
 we
 can
 kind
 of


Yeah.
 Cook
 it
 off
 a
 little
 bit
 and
 then


um
 we
 should
 add
 our
 veg
 to
 the
 water.
</details>

**>>**: 你的多任务处理能力真让我佩服。我认为这也是我们希望模型能够改进的一点：它应该能够一边处理这样的任务线程，一边还能跟你聊天。
<details><summary>Original English</summary>
**>>**: I'm
 impressed
 by
 your
 multitasking


abilities.


You
 know,
 I
 think
 that's
 actually
 one


thing
 um
 we
 need
 our
 models
 to
 get


better
 at.
 Like
 it
 should
 just
 be
 able


to


do
 some
 thread
 like
 this
 and
 also
 just


have
 a
 conversation
 with
 you
 at
 the
 same


time.
</details>

**>>**: 是的，对。这也让我想起一个问题：你认为图像、音频、视频甚至文本都应该收归在同一个模型之下，还是会分化出专门的音频模型等特定模型？
<details><summary>Original English</summary>
**>>**: Yeah.
 Yeah.
 Yeah.


No,
 I
 I
 That
 also
 reminds
 me.
 Do
 you


think
 images
 and
 audio
 and
 video
 and


even
 text
 like
 that
 should
 all
 be
 one


under
 one
 model
 or
 do
 you
 think
 it'll


like
 break
 through
 like
 specific


specialized
 like
 audio
 model
 or
</details>

**>>**: 对一个研究实验室来说，统合在一个模型之下有很多优势。比如你只需要维护一套基础设施技术栈。同时维护并扩展多套基础设施技术栈的成本是不容低估的。因此只维护一套底层技术栈的好处很多，你在基础架构中所做的核心研究可以直接迁移到任何模态或任务中。所以我们有强烈的倾向，尽可能保持尽量少的基础架构种类。
<details><summary>Original English</summary>
**>>**: Well,
 yeah.
 I
 mean,
 I
 think


for
 for
 a
 research
 lab,
 I
 think
 there


are
 a
 lot
 of
 advantages
 for
 it
 to
 be


under
 one.


Um
 you
 just
 have
 to
 maintain
 one


infrastructure
 stack
 for
 instance.
 Um
 I


think


the
 cost
 of
 like
 maintaining
 and
 scaling


many
 infrastructure
 stacks
 at
 once.
 Um
 I


think
 that's
 something
 that


you
 shouldn't
 underestimate.
 So,
 I
 think


there
 are
 a
 lot
 of
 benefits
 to
 just
 like


you
 know,
 you
 do
 some
 core
 research
 in


in
 your
 like
 in
 your
 fundamental
 stack


and
 that
 just
 carries
 over
 to
 whatever


modality
 or
 whatever
 thing
 that
 you


want.
 So,


um


I
 I
 think
 there's
 a
 strong
 bias
 for
 us


to
 keep
 it
 in
 as
 as
 few
 different
 archi


architectures
 as
 possible.
</details>

**>>**: 明白了。
<details><summary>Original English</summary>
**>>**: Got
 you.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

**>>**: 太好了。这很有道理，架构确实是一个平时不常被充分考虑的极其重要的因素。另外一个经常出现的词，你之前也提到过的，就是“氛围感研究员”（vibe researcher）。我们当然已经有了“氛围感程序员”（vibe coders）。但对于氛围感研究，你认为终极形态是什么？其核心价值在于提出正确想法的研究品味，还是跟进并落实具体研究的执行力？
<details><summary>Original English</summary>
**>>**: Great.


No,
 that
 that
 makes
 a
 lot
 of
 sense.
 I


think
 like
 the
 architecture
 as
 well
 is


something
 that
 isn't
 often
 considered.


Yeah.


It's very
 important.
 But
 one
 also
 term


that
 I've
 been
 seeing
 a
 lot
 that
 you've


also
 kind
 of
 mentioned
 is
 a
 vibe


researcher.
 You
 know,
 we
 have
 vibe


coders
 obviously.


Yeah,
 yeah,
 yeah,
 yeah.


But
 I
 guess
 on
 vibe
 researching,
 what
 do


you
 think
 is
 like
 the
 end
 state?
 Do
 you


think
 the
 main
 value
 out
 of
 a
 vibe


researcher
 is
 just
 the
 research
 taste
 of


coming
 up
 with
 the
 right
 idea
 or
 do
 you


think
 it's
 more
 so
 the
 execution
 of


going
 through
 and
 following
 through
 on


the
 actual
 research?
</details>

### “氛围感研究员”与模型品味的演进

**>>**: 我觉得我们正非常迅速地迈向这个世界。无论在 OpenAI 还是其他实验室，你开始看到大量工作转变为以编排为中心：研究人员构思想法，而模型已经强大到可以独立完成实施与执行。在构思想法与执行的价值对比上，两者固然都很重要，但我感觉到市场正明显转向只要能提出大量想法、模型就能为你完成具体执行与编排的模式。这将是未来从事研究的常态。正如我们之前谈到的，模型目前还不完全具备良好的品味，所以依然需要研究人员来构思想法。教给模型出色的品味会很难，但就加速研究而言，实实在在的好处已经显现了。
<details><summary>Original English</summary>
**>>**: Um
 yeah,
 so
 I
 I
 I
 think
 we're
 actually


moving
 towards
 this
 world
 very
 quickly,


right?
 I
 think
 both
 that
 OpenAI
 and
 our


other
 labs,


you
're
 starting
 to
 see
 a
 lot
 of
 the
 work


become
 mostly
 orchestration-focused,


right?
 Like
 the
 researchers
 coming
 up


with
 the
 ideas


and
 the
 model's
 great
 enough
 to
 do
 the


implementation
 execution
 by
 itself.


So
 I
 think
 you
 know,
 when
 you
 when
 it


comes
 down
 to
 like
 you
 know,
 is


is
 the
 value
 of
 coming
 up
 with
 ideas


versus
 execution?
 Um


Yeah,
 both
 are
 still
 important,
 but
 I


just
 feel
 like
 there's
 there's
 this


market
 shift


towards
 just
 kind
 of
 being
 able
 to
 come


up
 with
 a
 lot
 of
 ideas
 and
 then


the
 model
 can
 actually
 do
 the
 the


execution
 and
 orchestration
 for
 you.
 So


I
 think
 going
 to
 be
 the
 future
 of
 doing


research.


Um


We
 also
 said
 earlier,
 you
 know,
 like
 the


models
 don't
 quite
 have
 the
 taste
 yet.


And
 um


that's
 why
 you
 still
 need
 the


researchers
 coming
 up
 with
 the
 ideas.


It's
 going
 to
 be
 hard
 to
 teach
 the


models
 good
 taste.
 We
 noticed
 that,
 but


in
 terms
 of
 actually
 accelerating
 the


research,
 there's
 clear
 tangible


benefits
 already.
</details>

**>>**: 你认为模型在研究品味上会有与人类并驾齐驱的一天吗？
<details><summary>Original English</summary>
**>>**: Yeah.
 Do
 you
 think
 they'll
 ever
 be


parity
 in
 terms
 of
 research
 taste
 with


models?
</details>

**>>**: 我认为会的。审视我们的三年路线图，我们希望达到的最终目标就是模型可以进行端到端的研究。这个难题的一部分就在于让模型具备出色的品味，你指着某个通用的基准测试，它就能找到正确的解决方案。
<details><summary>Original English</summary>
**>>**: I
 think
 so.
 I
 mean,
 when
 we
 look
 at
 our


kind
 of
 three-year
 roadmap,
 right?


The
 end
 goal
 that
 we
 want
 to
 reach
 is


one
 where


you
 know,
 the
 the
 models
 are
 just
 doing


end-to-end
 research
 and


um


I
 think
 a
 part
 of
 that
 problem
 is
 just


being
 able
 to
 have
 the
 model
 come
 up


with
 good
 taste.
 You
 point
 at
 some
 you


know,
 just
 generic
 benchmark
 or


something
 and
 it
 finds
 the
 right


solutions.
 Yeah.
</details>

**>>**: 很有启发。关于 OpenAI 人类研究员所做的研究，当一个研究押注结果不佳时，你们如何进行复盘？毕竟要承担如此多的重大押注，难免会有不顺利的时候。
<details><summary>Original English</summary>
**>>**: Yeah,
 no,
 that's
 helpful.
 And
 in
 terms


of
 research
 done
 by
 humans


at
 OpenAI,


how
 do
 you
 guys
 go
 about
 I
 guess
 the


postmortem
 process
 of
 let's
 say
 a


research
 bet
 that
 didn't
 turn
 out
 well?


Cuz
 I
 assume
 that
 a
 lot
 of
 it
 is
 taking


these,
 you
 know,
 vast
 bets
 and
 some


don't
 turn
 out
 well.
</details>

### 高风险押注、面对失败与经验沉淀

**>>**: 这正是 OpenAI 的超额收益（alpha）的核心组成部分。我们与其他实验室的不同之处在于，我们承担了大量高风险押注，这也是我们能长期持续保持在最前沿的原因。但这同时也意味着部分押注注定不会成功。一个必然的推论是，当一个押注未能如愿时，你不能自欺欺人地认为它迟早会起效，而是必须果断抽身。因此需要做出决断：回头审视并承认“这在当时是个有前景的想法，但实际上没有我们想象的那么重要”，或者“有其他更好的方法”，又或者“我们有了新的发现”。但这些工作中很多也是非常有成果的。我们意识到，即使有时人们在验证某项技术时失败了，他们的书面总结也极其重要，因为那往往是一个非常自然的想法，总结记录可以避免许多人经历同样的痛苦。
<details><summary>Original English</summary>
**>>**: Well,
 I
 would
 say
 that
 is
 a
 big
 part
 of


OpenAI's
 alpha
 because
 I
 think
 one


thing
 that
 differentiates
 us
 from
 other


labs
 is
 we
 take
 a
 lot
 of
 high-risk
 bets.


And
 I
 think
 that's
 what's
 allowed
 us
 to


stay
 at
 the
 frontier
 uh
 so
 consistently


over
 time.
 Um
 but
 it
 also
 means
 that


some
 of
 the
 bets
 are
 not
 going
 to
 pan


out.
 And
 um


a
 hard
 corollary
 of
 that
 is
 when
 a


when
 a
 bet
 doesn't
 pan
 out
 um


you
 have
 to


you
 know,
 not
 delude
 yourself
 into


thinking
 that,
 you
 know,
 this
 is


something
 that
 will
 work
 and
 and
 kind
 of


uh
 disconnect
 from
 it.
 So,
 I
 think
 there


are
 certain
 calls
 that
 you
 have
 to
 make,


right?
 Like
 uh
 kind
 of
 look
 back
 and
 be


like,
 well,
 um
 this
 was
 a
 promising
 idea


at
 the
 time,
 but
 actually
 it's
 less


important
 than
 we
 thought,
 you
 know,


it's
 uh
 there's
 some
 other
 approach
 that


works
 better
 or,
 you
 know,
 um


there's
 some
 other
 kind
 of
 some


something
 that
 we
 discovered.
 But
 I
 I


think
 many
 of
 that


much
 of
 that
 work
 is
 also
 very
 fruitful.


So,
 what
 we
 realized
 is
 like
 even


sometimes
 when
 people
 fail
 at
 um
 proving


out
 a
 technique,
 uh
 their
 write-ups
 are


very
 important
 important
 because
 um


they'll
 kind
 of
 a
 lot
 it
 it'll
 often
 be


a
 natural
 idea
 and
 you
 can
 perhaps
 save


a
 lot
 of
 people
 from
 going
 through
 the


same
 pain.
</details>

**>>**: 是的，很有帮助。
<details><summary>Original English</summary>
**>>**: Yeah.


Well,
 that's
 helpful.
</details>

**>>**: 既然对失败持有这种积极态度，那如何权衡这种情况：如果一个研究人员连续做了多次押注，结果全部落空怎么办？毕竟在某种程度上，相比于一直做出毫无成果的押注，你肯定希望研究员最终能做出真正有益的贡献。
<details><summary>Original English</summary>
**>>**: Yeah.
 So,
 I
 guess
 when
 it
 comes
 to
 this


positive
 view
 on
 failure,
 how
 do
 you


balance
 that
 with,
 you
 know,
 a


researcher,
 let's
 say,
 takes
 a
 lot
 of


bets,
 consecutive
 bets,
 and
 none
 of
 them


pan
 out?
 Cuz
 I
 assume
 at
 a
 certain
 point


you'd
 want
 a
 researcher
 to
 eventually


have
 contributions
 that
 are
 actually


beneficial
 compared
 to
 only
 taking
 bets


that
 maybe
 pan
 out
 to
 being
 not
 good


space.
</details>

**>>**: 从经验来看，我确实见过有人陷入这种困境。但我也经历过几次这样的情况：押注一个接一个地失败，就在你濒临沮丧的边缘时，突然迎来了一个超级大爆发。这种情况发生过多次，所以关键取决于想法本身是否站得住脚。它们可以雄心勃勃，但必须合乎逻辑。有这样一类人，他们会去尝试很多这类想法，这是可以接受的，因为他们处于风险更高的前沿。这可能很像交易员看世界的视角，但他们只要隔一段时间证明一次其价值就足够了。他们需要带来价值。
<details><summary>Original English</summary>
**>>**: Just
 through
 experience,
 I
 I've


definitely
 seen
 some
 people
 fall
 into


this.
 Um


but
 I've
 also
 had
 several
 cases
 where,


you
 know,
 like
 it's
 just
 like
 bet
 after


bet,
 it
 doesn't
 pan
 out,
 and
 just
 when


you're
 like
 at
 the
 brink
 of
 frustration,


you
 have
 something
 that
's
 like
 a
 mega


hit.
 And


um
 this
 happened
 enough,
 so
 it
 really


just
 depends
 on


kind
 of
 are
 are
 the
 ideas
 themselves


sound?
 Uh
 they
 could
 be
 ambitious,


but
 they
 still
 have
 to
 be
 sound.
 And


um
 there's
 a
 certain
 kind
 of
 person
 who


will


will
 just
 take
 a
 lot
 of
 those
 ideas,
 and


it's
 okay
 because
 they're
 somewhat
 on


the
 riskier
 frontier.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 但他们只需要隔一段时间证明一次就合理了，对吧？这可能带有很强的交易视角，但归根结底取决于期望值，他们必须创造价值。
<details><summary>Original English</summary>
**>>**: But,
 they
 only
 have
 to
 justify
 it
 once


in
 a
 while
 for
 it
 to
 make
 sense,
 right?


It
 may
 be
 like
 a
 very
 trading


like
 kind
 of
 lens
 on
 the
 world,
 but


yeah,
 it's
 it's
 just
 on
 our
 expectation,


right?
 Like
 they
 they
 need
 to
 add
 value.
</details>

### 成果品尝与被低估的研究方向

**>>**: 好的，太棒了。食材基本组装好了，现在做最后润色：你可以尝尝你的汤，如果不够咸就加点酱油；如果太咸，加点水调淡一点。来看看我们的最终成果。味道如何？
<details><summary>Original English</summary>
**>>**: Yeah,
 no,
 that's
 that's
 great.
 Okay,
 so


we're
 basically
 assembled,
 now
 it's
 the


finishing
 touches,
 so
 you
 can
 taste
 your


soup,
 and
 then
 we
 just
 add
 soy
 sauce
 if


it's
 not
 salty
 enough,
 and
 if
 it's
 too


salty,
 we
 can
 add
 some
 water
 to
 lower


this
 down.


But,
 let's
 see
 our
 final
 creation.


How
 is
 it?
</details>

**>>**: 相当不错。
<details><summary>Original English</summary>
**>>**: It's
 pretty
 good.
</details>

**>>**: 还可以吗？
<details><summary>Original English</summary>
**>>**: Good?
</details>

**>>**: 我觉得行，我的挺好。
<details><summary>Original English</summary>
**>>**: I'll
 take
 it.
 Mine
 is
 good.
</details>

**>>**: 我的需要加点水。你能把水递给我吗？
<details><summary>Original English</summary>
**>>**: Yeah,
 mine
 needs
 a
 little
 bit
 of
 water.


Could
 you
 pass
 me
 the
 water?
</details>

**>>**: 没问题，给你。
<details><summary>Original English</summary>
**>>**: yeah,
 absolutely.
</details>

**>>**: 感觉怎么样？
<details><summary>Original English</summary>
**>>**: Great.
 So,
 how
 was
 that?
 How
 did
 that


feel?
</details>

**>>**: 我觉得这是一次学生蒸馏过程。你在做饭上显然比我强多了。
<details><summary>Original English</summary>
**>>**: Um
 I
 think
 this
 is
 a
 student


distillation.
 Um
 you're
 clearly
 better


than
 I
 am
 at
 this.
</details>

**>>**: 没有没有。[笑声] 我觉得你做得非常好，尤其是虾和棕榈芯的部分。闻起来真香。听起来很不错。更宽泛地讲，我有点好奇，你认为目前有哪些研究或主题是被高估或低估的？你会把什么归入其中？
<details><summary>Original English</summary>
**>>**: No,
 no,
 no.
 [laughter]
 I
 feel
 like
 you


did
 a
 very
 good
 job,
 especially
 with


even
 with
 the
 shrimp
 and
 palm
 hearts.


Yeah.


Smells
 great.


Wow,
 okay,
 that
 sounds
 good.
 I
 guess


just
 more
 generally,
 I'm
 kind
 of


curious,
 are
 there
 any
 reason
 research


or
 topics
 that
 you
 think
 are
 right
 now


overrated
 and
 underrated?
 Like
 what


would
 you
 categorize
 under?
</details>

**>>**: 如果现在还持有“预训练已死”的世界观，我认为预训练绝对没有死，它是被低估的。坦白说，产品思维、思考最终用途，以及如何将研究中构建的所有原语与真实世界的智能体用例结合起来，这也是被低估的。你绝不能脱离实际、在真空中构建一切而不与实用性挂钩。
<details><summary>Original English</summary>
**>>**: Um


Well,
 I
 think
 if
 you
 still
 have
 a


pre-training
 is
 dead
 view
 of
 the
 world,


um


I
 think
 I
 think
 uh
 pre-training
 is


definitely
 uh
 yeah,
 yeah,
 yeah,
 not
 not


dead.
 It's
 it's
 um
 it's
 underrated.
 Um


Yeah,
 and
 honestly,
 um


I
 think


products
 and
 kind
 of
 thinking
 about
 end


uses
 and
 you
 know
 how
 you
 tie
 all
 the


primitives
 you
 build
 in
 research
 to


you
 know
 real
 agentic
 use
 cases
 in
 the


world.
 That's
 also
 underrated.
 I
 think


um
 you
 really
 can't
 just
 kind
 of
 build


everything
 in
 a
 vacuum
 and
 not
 connect


things
 to
 utility.
</details>

**>>**: 很好。
<details><summary>Original English</summary>
**>>**: Yeah.
 No,
 that's
 great.
</details>

### 外部评测与最终盲测裁决

**>>**: 太棒了，我想我们可以品尝了。来试试看？
<details><summary>Original English</summary>
**>>**: Yeah.
 Awesome.
 I
 think
 we
 are
 ready
 to


taste.
 So,
 do
 we
 want
 to
 give
 it
 a
 go?
</details>

**>>**: 开动吧。
<details><summary>Original English</summary>
**>>**: Let's
 do
 it.
</details>

**>>**: 我们可以把这个移开，应该准备装盘了。你想拿这个盘子过去吗？
<details><summary>Original English</summary>
**>>**: We can
 move
 this
 and
 I
 think
 there


should
 be
 some
 plating.
 Yeah,
 do
 you


want
 to
 take
 this
 plate
 over
 here?
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 虾看起来很棒。其他东西都在这里。我们可以直接用这些锅。大虾有了。
<details><summary>Original English</summary>
**>>**: Okay.
 Shrimp
 looks
 great.


But
 everything
 else
 is
 here.


Great.
 And
 then
 we
 could
 just
 use
 these


pots.


So,
 we
 have
 our
 shrimp.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yep.
</details>

**>>**: 你想尝尝吗？干杯。来看看。可能有点甜。有点太甜了。因为我们想办法调补了一下。
<details><summary>Original English</summary>
**>>**: Do
 you
 want
 to
 try
 it?
 Cheers.
 Cheers.


Let's
 see.
 Maybe
 a
 little
 sweet.


That's
 a
 little
 too
 sweet.


Cuz
 we
 found
 a
 way
 to
 make
 it
 up.
</details>

**>>**: 对我来说刚好，我喜欢甜食。
<details><summary>Original English</summary>
**>>**: for
 me.
 I
 like
 sweet
 things.
</details>

**>>**: 很好。Sean，你想过来尝尝我们的豆腐汤吗？
<details><summary>Original English</summary>
**>>**: It's
 good.
 Okay,
 great.
 Um
 Sean,
 do
 you


want
 to
 come
 and
 taste
 our
 truffle
 soup?
</details>

**>>**: 顺便说一句，味道太棒了。观众闻不到，但是……
<details><summary>Original English</summary>
**>>**: That
 was
 so
 good
 by
 the
 way.
 You
 guys


can't
 smell
 it,
 but
 um
</details>

**>>**: 我们假装你是一位想要晋升的研究员。
<details><summary>Original English</summary>
**>>**: We'll
 pretend
 you're
 a
 um
 researcher


that's
 trying
 to
 get
 a
 promotion.
</details>

**>>**: 我是 Zach，他想要……你想拿这边的勺子吗？
<details><summary>Original English</summary>
**>>**: And
 I'm
 Zach
 and
 he's
 a
 you
 know
 trying


to
 get
 you
 so
 do
 you
 want
 to
 grab
 the


spoon
 over
 here?
</details>

**>>**: 这碗汤的品质真的会动摇这里的晋升决定。
<details><summary>Original English</summary>
**>>**: soup
 is
 really
 going
 to
 sway
 the


decision
 here.
 The
 soup
 quality
 of
 soup.
</details>

**>>**: 是的，太好了。
<details><summary>Original English</summary>
**>>**: Yeah.


Great.
</details>

**>>**: 我来尝尝。
<details><summary>Original English</summary>
**>>**: I'll
 do
 it.
</details>

**>>**: 好的，这里的艺术指导方向是什么？
<details><summary>Original English</summary>
**>>**: All
 right.
 What
 was
 the
 artistic


direction
 here?
</details>

**>>**: 艺术指导方向？就是模仿。我认为模仿中有伟大的艺术。
<details><summary>Original English</summary>
**>>**: Um
 artistic
 direction.
 Well,
 it
 was


mimicry.
 I
 think
 there's
 great
 art
 in


mimicry.
</details>

**>>**: 是的，让他们尽情发挥。
<details><summary>Original English</summary>
**>>**: Yeah.
 Just
 letting
 them
 cook.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 不错。
<details><summary>Original English</summary>
**>>**: Good.
</details>

**>>**: 哇，是的。
<details><summary>Original English</summary>
**>>**: Wow.
 Yeah.
</details>

**>>**: 味道很浓郁。
<details><summary>Original English</summary>
**>>**: Strong.
</details>

**>>**: 我觉得有一点我非常喜欢，就是咸鲜和香辣融为一体，同时还带着海鲜的风味。
<details><summary>Original English</summary>
**>>**: I
 mean,
 I
 think
 um
 one
 thing
 I
 I


definitely
 like
 like
 savory
 and
 spice


that
 goes
 together,
 but
 then
 also
 like


the
 sort
 of
 sea
 seafoodness.
</details>

**>>**: 嗯。
<details><summary>Original English</summary>
**>>**: Mhm.
</details>

**>>**: 确实很入味。
<details><summary>Original English</summary>
**>>**: Um
</details>

**>>**: 是的，很好地融入了进去。
<details><summary>Original English</summary>
**>>**: Yeah.
 Kind
 of
 really
 goes
 into
 it.
</details>

**>>**: 太好了。
<details><summary>Original English</summary>
**>>**: Great.
</details>

**>>**: 好的，我这碗味道非常浓烈。
<details><summary>Original English</summary>
**>>**: Okay.
 Mine's
 mine's
 very
 dominant.
</details>

**>>**: 选出赢家了吗？
<details><summary>Original English</summary>
**>>**: winner
 or
 what?
</details>

**>>**: 不不不，你得先尝尝然后……
<details><summary>Original English</summary>
**>>**: No,
 no,
 no.
 You're
 you're
 supposed
 to


try
 it
 and
 then
</details>

**>>**: 不，你得选一个赢家。
<details><summary>Original English</summary>
**>>**: No, you
 do
 pick
 a
 winner.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 这就像是评测？
<details><summary>Original English</summary>
**>>**: This
 is
 like
 evals?
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yes.
</details>

**>>**: 对。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 代价高昂。
<details><summary>Original English</summary>
**>>**: So,
 it's
 expensive.
</details>

**>>**: 外部评测。
<details><summary>Original English</summary>
**>>**: External
 evals.
</details>

**>>**: 我得说，感觉这碗水放得有点多了。
<details><summary>Original English</summary>
**>>**: Okay,
 I
 got
 to
 say


I
 feel
 like
 there's
 too
 much
 water
 in


this.
 I
 think
 like
 the
 the
</details>

**>>**: 我觉得也是锅的原因，[笑声] 因为这是一个大锅。
<details><summary>Original English</summary>
**>>**: I
 [laughter]
 I
 think
 it's
 also
 a
 pot.


Cuz
 this
 is
 a
 big
 pot.
</details>

**>>**: 是的。等等，好吧。我得选这一碗。
<details><summary>Original English</summary>
**>>**: Yeah.
 Wait,
 okay.
 Um
 I
 I
 would
 say
 I
 I


have
 to
 go
 for
 this.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
 Okay.
</details>

**>>**: 尽管你是我们尊贵的客人，但我必须保持客观。
<details><summary>Original English</summary>
**>>**: Just
 like
 you're
 our
 respected
 guest,


but
 I
 want
 to
 be
 objective.
</details>

**>>**: 当然，当然，那是自然。
<details><summary>Original English</summary>
**>>**: Of
 course.
 Of
 course.
 Yes.
 Yes.
 Yes.
</details>

**>>**: 这种浓郁的风味确实……
<details><summary>Original English</summary>
**>>**: Um
 and
 like
 yeah,
 the
 density
 I
 think


really
 a
 flavor
 really
</details>

**>>**: 我应该加一半的水？一半的水量？
<details><summary>Original English</summary>
**>>**: I'll
 do
 half
 water?
 Half
 the
 water?
</details>

**>>**: 大概是这样。
<details><summary>Original English</summary>
**>>**: Probably.
</details>

**>>**: 好，听起来不错。
<details><summary>Original English</summary>
**>>**: Okay.
 That
 sounds
 good.
</details>

**>>**: 口味这东西其实是非常主观的，对吧？
<details><summary>Original English</summary>
**>>**: I
 mean
 I
 think
 it's
 very
 personal,


right?
</details>

**>>**: 是的，口味非常个人化。正如你刚才提到的品味……
<details><summary>Original English</summary>
**>>**: Yeah,
 I
 think
 it's
 also
 very
 personal.


Taste,
 you
 know,
 you
 were
 mentioning
</details>

**>>**: 你平时经常做饭吧。
<details><summary>Original English</summary>
**>>**: You
 do
 a
 lot
 of
 cooking.
</details>

**>>**: 品味。
<details><summary>Original English</summary>
**>>**: Taste.
</details>

**>>**: 不不不。
<details><summary>Original English</summary>
**>>**: No.
 No.
 No.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 我就知道几个食谱，而且严格照着做。如果让我稍微做点改变，我完全不知道该怎么弄，会彻底找不着北。
<details><summary>Original English</summary>
**>>**: Okay.
 I
 know
 a
 couple
 recipes.
 Um
 I


follow
 them
 to
 the
 T.
 I
 can't
 Like
 if


you
 tell
 me,
 "Oh,
 cook
 something


slightly
 different."
 I
 have
 no
 idea.
 I'm


completely
 lost.
</details>

**>>**: 对，确实。
<details><summary>Original English</summary>
**>>**: Right.
 Right.
</details>

**>>**: 忙着做饭。
<details><summary>Original English</summary>
**>>**: Yeah.
 There's
 busy
 cooking.
</details>

**>>**: GPT 可以教你。
<details><summary>Original English</summary>
**>>**: GPT
 can
 tell
 you.
</details>

**>>**: 嗯，是的。实话说，我中途确实查了好几次 ChatGPT。
<details><summary>Original English</summary>
**>>**: Mhm.
 Yeah.
 Yeah.
 Oh,
 I
 I'm
 not
 going
 to


lie.
 I
 kind
 of
 looked
 up
 in
 ChatGPT
 a


couple
 of
 times.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 对你来说那就像是提前做备课。不过……
<details><summary>Original English</summary>
**>>**: So
 for
 you,
 it's
 like,
 "Oh,
 just
 as


prep."
 But
</details>

**>>**: 没事，不过确实挺有意思。
<details><summary>Original English</summary>
**>>**: No
 worries.
 But
 yeah.
</details>

**>>**: 非常高兴能邀请到你。你一直以卓越的研究品味引领着这个领域，见证你们的工作非常棒。希望你玩得开心。
<details><summary>Original English</summary>
**>>**: It
 was
 It
 was
 great
 having
 you.
 I
 feel


like
 you're
 always
 leading
 the
 field


with
 a
 lot
 of
 research
 taste
 as
 well,


and
 it's
 great
 seeing
 your
 work.
 So


hopefully
 It
 was
 fun.
</details>

**>>**: 是的，非常开心，太感谢了。
<details><summary>Original English</summary>
**>>**: Yeah,
 a
 lot
 of
 fun.
 Thank
 you
 so
 much.
</details>