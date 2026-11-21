---
author: Dwarkesh Patel
date: '2024-03-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=D_WsPbdJKUg
speaker: Dwarkesh Patel
tags:
  - ai-safety
  - intelligence-explosion
  - alignment-research
  - research-automation
  - generative-ai
title: AI自动化研究时代的挑战与人类的策略：从风险控制到加速进步
summary: 本文探讨了在AI研究日益自动化的背景下，人类扮演的“审计者”角色，以及应对AI潜在协同和失控风险的策略。作者提出，通过从弱系统入手、利用AI辅助对齐研究、构建严谨的反馈机制，人类仍有可能控制AI智能爆炸。文章通过AI生成合成数据、强化学习和自动化编程等具体案例，阐述了AI如何加速科学发现和技术进步，并强调了AI的成本效益和规模化应用的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models: []
media_books: []
status: evergreen
---
### AI驱动研究时代的挑战与人类的审计角色

在人工智能（AI）已显著自动化研究工作的当前阶段，人类面临着新的角色定位：成为“审计者”。这意味着要增加AI协同的难度，阻止其秘密串通、控制服务器、提取信息。我们的关键在于设计可验证的实验，以验证AI在阻止不良行为（如AI试图绕过人类监管）方面的有效性。之所以对人类有机会应对这一局面持相对乐观态度，原因有二：一是我们正从较弱的AI系统入手，随着AI能力增强，若不良动机在训练后期才出现，我们可能已有足够能力利用AI辅助来加强对抗性样本、提升AI检测器的鲁棒性，并揭示AI的“奖励劫持”（Reward Hacking）倾向和动机；二是即使早期系统出现不良动机，若我们能及时检测并找到规避方法，依然能取得胜利。

<details>
<summary>Original English</summary>

in
 in
 this
 incredibly
 scary
 late
 period


when
 AI
 has
 really
 automated
 research


humans
 do
 this
 uh
 this
 function
 of
 like


auditing
 uh
 making
 it
 more
 difficult
 for


the
 AIS
 to
 conspire
 together
 and
 root


the
 servers
 take
 over
 the
 process
 and


extract
 information
 from
 them
 within
 the


set
 of
 things
 that
 we
 can
 verify
 like


experiments
 where
 we
 can
 see
 oh
 yeah


this
 works
 at
 stopping
 an
 AI
 trained
 to


get
 a
 fast
 one
 past
 human
 Raiders


the
 reasons
 why
 I
 think
 we
 actually
 have


such
 a
 a
 relatively
 good
 chance
 of


handling
 that
 um
 are


twofold
 so
 one
 is
 has
 we
 approach
 that


kind
 of
 AI
 capability
 we're
 we're


approaching
 that
 from
 weaker
 systems
 if


the
 really
 bad
 uh
 sorts
 of
 uh


motivations
 develop
 relatively
 later
 in


the
 training
 process
 at
 least
 with
 all


our
 counter
 measures


then
 by
 that
 time
 we
 may
 have
 plenty
 uh


of
 ability
 to
 extract
 AI
 assistance
 on


further
 strengthening
 the
 quality
 of
 our


adversarial
 examples
 the
 strength
 of
 our


neural
 eye
 detectors
 the
 experiments


that
 we
 can
 use
 to
 reveal
 and
 elicit
 and


distinguish
 between
 different
 kinds
 of


reward
 hacking
 Tendencies
 and


motivations
 so
 yeah
 we
 may
 have
 system


that
 have
 just
 not
 developed
 bad


motivations
 in
 the
 first
 place
 and
 be


able
 to
 use
 them
 a


lot
 um
 in
 developing
 the
 incrementally


better
 systems
 in
 a
 safe
 way
 and
 we
 may


be
 able
 to
 even
 if
 some
 of
 the
 early


systems
 do
 develop
 these
 bad
 motivations


if
 we're
 able
 to
 detect
 that
 an


experiment
 and
 find
 a
 way
 uh
 to
 get
 away


from
 that
 then
 we
 can
 win
 even
 if
 these


sort
 of
 hostile
 motivations
 develop


early
</details>

### AI的增量贡献与智能爆炸的反馈回路

将上述乐观因素与AI的潜在“第二道救赎”（second saving throw）相结合——即，即使早期AI系统产生不良动机，我们也能通过AI协助来解决剩余的对齐问题，例如提升**神经网络眼动检测器**（Neural Eye Detectors）的性能，速度甚至可能超过AI用于破坏的计算时间。这种“多汁”的AI能力，在于它能提供可观察、可验证的输出。例如，我们可以设计一个**气隙计算机**（Air-gapped Computer），让AI尝试进行“根目录攻击”（root the environment）并显示“蓝香蕉”（blue banana）——即使我们无法完全理解其利用的漏洞，看到结果也表明AI成功了。这种**丰富的经验反馈**（rich empirical feedback）能帮助我们识别AI的最佳努力，尤其是在AI的贡献开始**显著增长**（contributing significantly），甚至比人类研究员的贡献更大时。当AI能够将人类研究员的生产力提升50%到100%时，我们就能看到AI推动的**软件创新**（software Innovation），如发明**Transformer**模型、发现**Chinchilla 缩放定律**（Chinchilla scaling），或者优化计算如**FlashAttention**。AI无需自动化AI研究的全部过程，只需自动化部分，就能因其**成本低廉**（cheap）而产生海量应用。人类水平AI的出现标志着**智能爆炸**（intelligence explosion）的开始，而这一过程需要一个**反馈循环**（feedback loop），AI的贡献开始等同于甚至超越人类研究员。

<details>
<summary>Original English</summary>

when
 I
 combine
 the
 possibility


that
 we
 get
 relatively
 lucky
 on
 the


motivations
 of
 the
 earlier
 AI
 systems


systems
 strong
 enough
 that
 we
 can
 use


for
 some
 alignment
 research
 tasks
 and


then
 the
 possibility
 of
 getting
 that


later
 with
 AI
 assistance
 that
 we
 can't


trust
 fully
 where
 we
 have
 to
 have
 hard


power
 constraints
 and
 a
 number
 of
 things


to
 prevent
 them
 from
 doing
 this
 takeover


uh
 it
 still
 seems
 plausible
 we
 can
 get
 a


second
 saving
 throw
 where
 we're
 able
 to


extract
 work
 from
 these
 AIS
 on
 solving


the
 remaining
 problems
 of
 alignment
 of


things
 like
 neural
 ey
 detectors
 faster


than
 they
 can
 contribute
 in
 their
 spare


time


uh
 to
 the
 project
 of
 overthrowing


humanity
 hacking
 their
 servers
 and


removing
 the
 hard
 power
 and
 so
 if
 we


wind
 up
 in
 the
 situation
 where
 the
 AIS


are
 misaligned
 and
 then
 we
 need
 to


uncover
 those
 motivations
 change
 them


and
 align
 them
 then
 we
 get
 a
 very
 scary


situation
 for
 us
 um


because
 we
 might
 we
 need
 to
 do
 this


stuff
 very
 quickly
 we
 may
 fail
 but
 it's


a
 second
 chance
 where
 our
 work
 is
 just


evaluating
 outputs
 that
 the
 AI
 are


delivering
 having
 the
 hard
 power
 uh
 and


supervision
 to
 keep
 them
 from


successfully
 rooting
 the
 servers
 doing
 a


takeover
 during
 this
 process
 and
 have


them
 finish
 the
 alignment
 task
 that
 we


sadly
 failed
 uh
 to
 invest
 enough
 or


succeed
 in
 doing
 beforehand
 the


incredibly
 juicy
 ability
 that
 we
 have
 um


working
 with
 the
 AIS
 is


that
 we
 can
 have
 as
 an
 invaluable


outcome
 that
 we
 can
 see
 and


tell
 whether
 they
 got
 a
 fast
 one
 p
 past


us
 on
 an
 identifiable
 situation
 we
 can


have
 here's
 an
 air
 gap
 computer
 you
 get


control
 of
 the
 keyboard
 you
 can
 input


commands
 can
 you
 root
 the


environment
 uh
 and
 make
 a
 blue
 banana


appear
 on
 the
 screen
 even
 if
 if
 we
 train


the
 AI
 to
 do
 that
 and
 it
 succeeds
 we
 see


the
 blue
 banana
 we
 know
 we
 know
 it


worked
 even
 if
 we
 did
 not
 not
 understand


and
 would
 not
 have
 detected
 the


particular
 exploit
 that
 it
 used
 to
 do
 it


this
 can
 give
 us
 a
 rich
 empirical


feedback
 where
 we're
 able
 to
 identify


things
 that
 are
 even
 uh
 an
 AI
 using
 its


best
 efforts
 uh
 to
 get
 past
 our


interpretability
 Methods
 at
 what
 point


would
 it
 be
 the
 case
 that
 the
 AI
 is


contributing
 significantly
 in
 the
 sense


that
 it
 would
 almost
 be
 the
 equivalent


of
 having
 additional
 researchers
 to
 AI


progress
 and
 softare
 the
 thing
 to
 look


for
 uh
 is
 when
 is
 it
 the
 case
 that
 the


the
 contributions
 from
 AI
 are
 starting


to
 uh
 become
 as
 large
 or
 larger
 as
 the


contributions
 uh
 from
 humans
 so
 like
 uh


when
 this
 is
 boosting
 their
 effective


productivity
 by
 50
 or
 100%
 And
 you
 like


if
 you
 then
 go
 from
 you
 eight
 month


doubling
 time
 say
 for
 Effective
 compute


from
 software
 Innovation
 things
 like


like
 inventing
 the
 Transformer
 or


discovering
 chinchilla
 scaling
 and
 do
 it


in
 your
 training
 runs
 more
 optimally
 or


creating
 flash
 attention
 it
 doesn't
 have


to
 have
 been
 able
 to
 automate
 everything


involved
 in
 the
 process
 of
 AI
 research


it
 can
 be
 it's
 automated
 a
 bunch
 of


things
 and
 then
 those
 are
 being
 done
 in


extreme
 profusion
 because
 any
 I
 think
 a


thing
 that
 a
 AI
 can
 do
 you
 have
 it
 done


much
 more
 often
 because
 it's
 so


cheap
 uh
 and
 so
 it's
 not
 a
 threshold
 of


this
 is
 human
 level
 AI
 it
 can
 do


everything
 a
 human
 can
 do
 with
 no


weaknesses
 in
 any
 area
 it's
 that
 even


with
 its


weaknesses
 it's
 able
 to
 bump
 up
 the


performance
 tens
 of
 millions
 of


gpus
 each
 is
 doing
 the
 work
 of
 maybe
 40


maybe
 more
 uh
 of
 these
 kind
 of
 existing


workers
 this
 like
 going
 from
 a
 Workforce


of
 tens
 of
 thousands
 to
 hundreds
 of


Millions
 you
 immediately
 make
 all
 kinds


of
 discoveries
 then
 you
 immediately


develop
 all
 sorts
 of
 tremendous


Technologies
 so
 human
 level
 AI
 is
 deep


deep
 into
 an
 intelligence
 explosion
 the


intelligence
 explosion
 has
 to
 start
 with


something
 weaker
 than
 that
 yep
 yep
 yep


what
 is
 the
 point
 of
 which
 that
 feedback


loop
 starts
 where
 you
 can
 even
 you're


not
 just
 doing
 the
 05%
 increase
 in


productivity
 that
 a
 sort
 of
 AI
 tool


might
 do
 but
 is
 actually
 the
 equivalent


of
 a
 researcher
 or
 close
 to
 it
 so
 so
 I


think
 maybe
 a
 way
 uh
 to
 look
 at
 it
 is
 to


give
 some
 illustrative
 examples
 of
 like


the
 kinds
 of
 capabilities
 that
 you
 might


see
 what
 we'll
 we'll
 have
 is
 intense


application
 of
 the
 ways
 in
 which
 AIS


have


advantages
 partly
 offsetting
 their


weaknesses
 and
 so
 AIS
 are
 cheap
 we
 can


call
 a
 lot
 of
 them
 uh
 to
 do
 many
 small


problems
 uh
 and
 so
 you'll
 have


situations
 where
 you
 have
 Dumber
 AIS


that
 are
 deployed
 thousands
 of
 times
 uh


to
 equal
 say
 one
 human


worker
 uh
 and
 they'll
 be
 doing
 things


like
 um
 these
 voting
 algorithms
 where


you
 with
 an
 llm
 you
 generate
 a
 bunch
 of


different
 responses
 uh
 and
 take
 a


majority
 vote
 among
 them
 that
 improves


performance
 sum
 uh
 you'll
 have
 things


like
 the
 uh
 alphao
 kind
 of
 approach
 um


where
 you
 use
 the
 neural
 net
 to
 do


search
 uh
 and
 you
 go
 deeper
 with
 the


search
 by
 plowing
 in
 more
 compute
 which


helps
 to
 offset
 the
 inefficiency
 and


weaknesses
 of
 the
 model
 on
 its
 own
 uh


you'll
 do
 things
 that
 would
 just
 be


totally
 impractical
 um
 for
 humans


because
 of
 the
 sheer
 number
 of
 steps
 and


so
 an
 example
 of
 that
 would
 be
 designing


synthetic
 training
 data
 uh
 so
 humans
 do


not
 learn
 by
 just
 going
 into
 the
 library


and
 opening
 books
 at
 random
 Pages
 um


it's
 actually
 much
 much
 more
 efficient


uh
 to
 have
 things
 like
 schools
 and


classes
 uh
 where
 they
 teach
 you
 things


in
 a
 an
 order
 that
 makes
 sense
 that's


focusing
 on
 the
 skills
 that
 are
 more


valuable
 to
 learn
 uh
 they
 give
 you
 tests


and
 exam
 they're
 designed
 to
 try
 and


elicit
 the
 skill
 they're
 actually
 trying


to
 teach
 um
 and
 right
 now
 we
 don't


bother
 with
 that
 because
 we
 can
 hoover


up
 more
 data
 from
 the
 internet
 we're


getting
 towards
 the
 end
 of
 that
 but
 yeah


as
 the
 AIS
 get
 more
 sophisticated


they'll
 be
 better
 able
 to
 tell
 uh
 what


is
 uh
 a
 useful
 kind
 of
 skill
 to
 practice


and
 to
 generate
 that
 and
 we've
 done
 that


in
 other
 areas
 so


alphao
 the
 original
 Al
 version
 of
 alphao


was
 booted
 up
 with
 data
 from
 Human


goplay
 uh
 and
 then
 improved
 uh
 with


reinforcement
 learning
 and
 mon
 Carlo


research
 uh
 but
 then
 Alpha
 zero
 with
 a


somewhat
 more
 sophisticated
 model
 uh


benefited
 from
 some
 some
 other


improvements
 um
 but
 was
 able
 to
 go
 from


scratch
 uh
 and
 it
 generated
 its
 own
 data


through


self-play
 uh
 so
 which
 getting
 data
 of
 a


higher
 quality
 than
 the
 human
 data


because
 there
 are
 no
 human
 players
 that


good
 uh
 available
 in
 the
 data
 set
 and


also
 a
 curriculum
 so
 that
 at
 any
 given


point
 it
 was
 playing
 games
 against
 an


opponent
 of
 equal
 skill
 itself
 uh
 and
 so


it
 was
 always
 in
 an
 area
 when
 it
 was


easy
 to
 learn
 if
 you're
 if
 you're
 just


always
 losing
 no
 matter
 what
 you
 do
 or


always
 winning
 no
 matter
 what
 you
 do


it's
 hard
 to
 distinguish


uh
 which
 things
 are
 better
 and
 which
 are


worse
 and
 when
 we
 have
 somewhat
 more


sophisticated
 AIS
 that
 can
 generate


training
 data
 and
 tasks
 for
 themselves


for
 example
 if
 the
 AI
 can
 generate
 a
 lot


of
 unit
 tests
 and
 then
 can
 try
 and


produce
 programs
 that
 pass
 those
 unit


tests
 uh
 then
 The
 Interpreter
 is


providing
 a
 training
 signal
 and
 the
 the


AI
 can
 get
 good
 at
 figuring
 out
 what's


the
 kind
 of
 programming
 problem
 that
 is


hard
 for
 AIS
 right
 now
 that
 will
 develop


more
 of
 the
 skills
 that
 I


need
 uh
 and
 then
 do
 them
 and
 now
 you're


not
 gonna
 have
 you
 know
 employees
 at


open
 AI
 right
 like
 a
 billion
 programming


problems
 that's
 just
 not
 going
 to
 happen


uh
 but
 you
 are
 going
 to
 have
 AIS
 given


the
 task
 of
 producing
 the
 enormous


number
 of
 programming
 challenges
</details>

### AI驱动的科研加速机制与范式转变

AI不仅能协助解决复杂的对齐问题，还在加速科学研究方面展现出巨大潜力。AI能够通过多种方式提升效率：首先，大量廉价AI的部署，例如成千上万次调用AI来执行诸如**投票算法**（voting algorithms）之类的任务，或通过**大型语言模型**（LLM）生成响应并进行多数投票，从而提升性能。其次，借鉴**AlphaGo/AlphaZero**的模式，利用神经网络进行搜索，并通过投入更多计算资源来加深搜索，以弥补模型本身的低效率和弱点。一个关键的应用是**设计合成训练数据**（designing synthetic training data）。与人类通过学校和课程系统学习不同，AI可以生成有序、聚焦关键技能的训练任务和测试，如**AlphaZero**从零开始，通过**自我对弈**（self-play）生成比人类数据质量更高、包含课程学习体系的训练数据。它能通过生成大量单元测试，并让AI尝试编写能通过这些测试的程序，从而获得由**解释器**（Interpreter）提供的训练信号。AI还能识别当前对AI而言棘手的编程问题，从而促进自身所需技能的发展。这种能力并非是要取代**OpenAI**等机构中的人类员工来解决数十亿个编程问题，而是将AI作为生成海量编程挑战的任务执行者，推动整个AI研究生态的指数级进步。

<details>
<summary>Original English</summary>

so
 yeah
 we
 may
 have
 system


that
 have
 just
 not
 developed
 bad


motivations
 in
 the
 first
 place
 and
 be


able
 to
 use
 them
 a


lot
 um
 in
 developing
 the
 incrementally


better
 systems
 in
 a
 safe
 way
 and
 we
 may


be
 able
 to
 even
 if
 some
 of
 the
 early


systems
 do
 develop
 these
 bad
 motivations


if
 we're
 able
 to
 detect
 that
 an


experiment
 and
 find
 a
 way
 uh
 to
 get
 away


from
 that
 then
 we
 can
 win
 even
 if
 these


sort
 of
 hostile
 motivations
 develop


early
 when
 I
 combine
 the
 possibility


that
 we
 get
 relatively
 lucky
 on
 the


motivations
 of
 the
 earlier
 AI
 systems


systems
 strong
 enough
 that
 we
 can
 use


for
 some
 alignment
 research
 tasks
 and


then
 the
 possibility
 of
 getting
 that


later
 with
 AI
 assistance
 that
 we
 can't


trust
 fully
 where
 we
 have
 to
 have
 hard


power
 constraints
 and
 a
 number
 of
 things


to
 prevent
 them
 from
 doing
 this
 takeover


uh
 it
 still
 seems
 plausible
 we
 can
 get
 a


second
 saving
 throw
 where
 we're
 able
 to


extract
 work
 from
 these
 AIS
 on
 solving


the
 remaining
 problems
 of
 alignment
 of


things
 like
 neural
 ey
 detectors
 faster


than
 they
 can
 contribute
 in
 their
 spare


time


uh
 to
 the
 project
 of
 overthrowing


humanity
 hacking
 their
 servers
 and


removing
 the
 hard
 power
 and
 so
 if
 we


wind
 up
 in
 the
 situation
 where
 the
 AIS


are
 misaligned
 and
 then
 we
 need
 to


uncover
 those
 motivations
 change
 them


and
 align
 them
 then
 we
 get
 a
 very
 scary


situation
 for
 us
 um


because
 we
 might
 we
 need
 to
 do
 this


stuff
 very
 quickly
 we
 may
 fail
 but
 it's


a
 second
 chance
 where
 our
 work
 is
 just


evaluating
 outputs
 that
 the
 AI
 are


delivering
 having
 the
 hard
 power
 uh
 and


supervision
 to
 keep
 them
 from


successfully
 rooting
 the
 servers
 doing
 a


takeover
 during
 this
 process
 and
 have


them
 finish
 the
 alignment
 task
 that
 we


sadly
 failed
 uh
 to
 invest
 enough
 or


succeed
 in
 doing
 beforehand
 the


incredibly
 juicy
 ability
 that
 we
 have
 um


working
 with
 the
 AIS
 is


that
 we
 can
 have
 as
 an
 invaluable


outcome
 that
 we
 can
 see
 and


tell
 whether
 they
 got
 a
 fast
 one
 p
 past


us
 on
 an
 identifiable
 situation
 we
 can


have
 here's
 an
 air
 gap
 computer
 you
 get


control
 of
 the
 keyboard
 you
 can
 input


commands
 can
 you
 root
 the


environment
 uh
 and
 make
 a
 blue
 banana


appear
 on
 the
 screen
 even
 if
 if
 we
 train


the
 AI
 to
 do
 that
 and
 it
 succeeds
 we
 see


the
 blue
 banana
 we
 know
 we
 know
 it


worked
 even
 if
 we
 did
 not
 not
 understand


and
 would
 not
 have
 detected
 the


particular
 exploit
 that
 it
 used
 to
 do
 it


this
 can
 give
 us
 a
 rich
 empirical


feedback
 where
 we're
 able
 to
 identify


things
 that
 are
 even
 uh
 an
 AI
 using
 its


best
 efforts
 uh
 to
 get
 past
 our


interpretability
 Methods
 at
 what
 point


would
 it
 be
 the
 case
 that
 the
 AI
 is


contributing
 significantly
 in
 the
 sense


that
 it
 would
 almost
 be
 the
 equivalent


of
 having
 additional
 researchers
 to
 AI


progress
 and
 softare
 the
 thing
 to
 look


for
 uh
 is
 when
 is
 it
 the
 case
 that
 the


the
 contributions
 from
 AI
 are
 starting


to
 uh
 become
 as
 large
 or
 larger
 as
 the


contributions
 uh
 from
 humans
 so
 like
 uh


when
 this
 is
 boosting
 their
 effective


productivity
 by
 50
 or
 100%
 And
 you
 like


if
 you
 then
 go
 from
 you
 eight
 month


doubling
 time
 say
 for
 Effective
 compute


from
 software
 Innovation
 things
 like


like
 inventing
 the
 Transformer
 or


discovering
 chinchilla
 scaling
 and
 do
 it


in
 your
 training
 runs
 more
 optimally
 or


creating
 flash
 attention
 it
 doesn't
 have


to
 have
 been
 able
 to
 automate
 everything


involved
 in
 the
 process
 of
 AI
 research


it
 can
 be
 it's
 automated
 a
 bunch
 of


things
 and
 then
 those
 are
 being
 done
 in


extreme
 profusion
 because
 any
 I
 think
 a


thing
 that
 a
 AI
 can
 do
 you
 have
 it
 done


much
 more
 often
 because
 it's
 so


cheap
 uh
 and
 so
 it's
 not
 a
 threshold
 of


this
 is
 human
 level
 AI
 it
 can
 do


everything
 a
 human
 can
 do
 with
 no


weaknesses
 in
 any
 area
 it's
 that
 even


with
 its


weaknesses
 it's
 able
 to
 bump
 up
 the


performance
 tens
 of
 millions
 of


gpus
 each
 is
 doing
 the
 work
 of
 maybe
 40


maybe
 more
 uh
 of
 these
 kind
 of
 existing


workers
 this
 like
 going
 from
 a
 Workforce


of
 tens
 of
 thousands
 to
 hundreds
 of


Millions
 you
 immediately
 make
 all
 kinds


of
 discoveries
 then
 you
 immediately


develop
 all
 sorts
 of
 tremendous


Technologies
 so
 human
 level
 AI
 is
 deep


deep
 into
 an
 intelligence
 explosion
 the


intelligence
 explosion
 has
 to
 start
 with


something
 weaker
 than
 that
 yep
 yep
 yep


what
 is
 the
 point
 of
 which
 that
 feedback


loop
 starts
 where
 you
 can
 even
 you're


not
 just
 doing
 the
 05%
 increase
 in


productivity
 that
 a
 sort
 of
 AI
 tool


might
 do
 but
 is
 actually
 the
 equivalent


of
 a
 researcher
 or
 close
 to
 it
 so
 so
 I


think
 maybe
 a
 way
 uh
 to
 look
 at
 it
 is
 to


give
 some
 illustrative
 examples
 of
 like


the
 kinds
 of
 capabilities
 that
 you
 might


see
 what
 we'll
 we'll
 have
 is
 intense


application
 of
 the
 ways
 in
 which
 AIS


have


advantages
 partly
 offsetting
 their


weaknesses
 and
 so
 AIS
 are
 cheap
 we
 can


call
 a
 lot
 of
 them
 uh
 to
 do
 many
 small


problems
 uh
 and
 so
 you'll
 have


situations
 where
 you
 have
 Dumber
 AIS


that
 are
 deployed
 thousands
 of
 times
 uh


to
 equal
 say
 one
 human


worker
 uh
 and
 they'll
 be
 doing
 things


like
 um
 these
 voting
 algorithms
 where


you
 with
 an
 llm
 you
 generate
 a
 bunch
 of


different
 responses
 uh
 and
 take
 a


majority
 vote
 among
 them
 that
 improves


performance
 sum
 uh
 you'll
 have
 things


like
 the
 uh
 alphao
 kind
 of
 approach
 um


where
 you
 use
 the
 neural
 net
 to
 do


search
 uh
 and
 you
 go
 deeper
 with
 the


search
 by
 plowing
 in
 more
 compute
 which


helps
 to
 offset
 the
 inefficiency
 and


weaknesses
 of
 the
 model
 on
 its
 own
 uh


you'll
 do
 things
 that
 would
 just
 be


totally
 impractical
 um
 for
 humans


because
 of
 the
 sheer
 number
 of
 steps
 and


so
 an
 example
 of
 that
 would
 be
 designing


synthetic
 training
 data
 uh
 so
 humans
 do


not
 learn
 by
 just
 going
 into
 the
 library


and
 opening
 books
 at
 random
 Pages
 um


it's
 actually
 much
 much
 more
 efficient


uh
 to
 have
 things
 like
 schools
 and


classes
 uh
 where
 they
 teach
 you
 things


in
 a
 an
 order
 that
 makes
 sense
 that's


focusing
 on
 the
 skills
 that
 are
 more


valuable
 to
 learn
 uh
 they
 give
 you
 tests


and
 exam
 they're
 designed
 to
 try
 and


elicit
 the
 skill
 they're
 actually
 trying


to
 teach
 um
 and
 right
 now
 we
 don't


bother
 with
 that
 because
 we
 can
 hoover


up
 more
 data
 from
 the
 internet
 we're


getting
 towards
 the
 end
 of
 that
 but
 yeah


as
 the
 AIS
 get
 more
 sophisticated


they'll
 be
 better
 able
 to
 tell
 uh
 what


is
 uh
 a
 useful
 kind
 of
 skill
 to
 practice


and
 to
 generate
 that
 and
 we've
 done
 that


in
 other
 areas
 so


alphao
 the
 original
 Al
 version
 of
 alphao


was
 booted
 up
 with
 data
 from
 Human


goplay
 uh
 and
 then
 improved
 uh
 with


reinforcement
 learning
 and
 mon
 Carlo


research
 uh
 but
 then
 Alpha
 zero
 with
 a


somewhat
 more
 sophisticated
 model
 uh


benefited
 from
 some
 some
 other


improvements
 um
 but
 was
 able
 to
 go
 from


scratch
 uh
 and
 it
 generated
 its
 own
 data


through


self-play
 uh
 so
 which
 getting
 data
 of
 a


higher
 quality
 than
 the
 human
 data


because
 there
 are
 no
 human
 players
 that


good
 uh
 available
 in
 the
 data
 set
 and


also
 a
 curriculum
 so
 that
 at
 any
 given


point
 it
 was
 playing
 games
 against
 an


opponent
 of
 equal
 skill
 itself
 uh
 and
 so


it
 was
 always
 in
 an
 area
 when
 it
 was


easy
 to
 learn
 if
 you're
 if
 you're
 just


always
 losing
 no
 matter
 what
 you
 do
 or


always
 winning
 no
 matter
 what
 you
 do


it's
 hard
 to
 distinguish


uh
 which
 things
 are
 better
 and
 which
 are


worse
 and
 when
 we
 have
 somewhat
 more


sophisticated
 AIS
 that
 can
 generate


training
 data
 and
 tasks
 for
 themselves


for
 example
 if
 the
 AI
 can
 generate
 a
 lot


of
 unit
 tests
 and
 then
 can
 try
 and


produce
 programs
 that
 pass
 those
 unit


tests
 uh
 then
 The
 Interpreter
 is


providing
 a
 training
 signal
 and
 the
 the


AI
 can
 get
 good
 at
 figuring
 out
 what's


the
 kind
 of
 programming
 problem
 that
 is


hard
 for
 AIS
 right
 now
 that
 will
 develop


more
 of
 the
 skills
 that
 I


need
 uh
 and
 then
 do
 them
 and
 now
 you're


not
 gonna
 have
 you
 know
 employees
 at


open
 AI
 right
 like
 a
 billion
 programming


problems
 that's
 just
 not
 going
 to
 happen


uh
 but
 you
 are
 going
 to
 have
 AIS
 given


the
 task
 of
 producing
 the
 enormous


number
 of
 programming
 challenges
</details>