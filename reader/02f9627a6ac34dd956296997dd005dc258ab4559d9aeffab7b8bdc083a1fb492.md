---
author: Dwarkesh Patel
date: '2024-06-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rl7B-LHiaNo
speaker: Dwarkesh Patel
tags:
  - general-intelligence
  - artificial-intelligence
  - llm-benchmarks
  - scaling-laws
  - reasoning-vs-skill
title: 大模型依赖记忆而非智能：解读Scaling Law下的核心误区
summary: 该讲稿探讨了通用智能与技能的本质区别，指出当前大型语言模型（LLM）主要擅长技能习得和基于模式匹配的“记忆式推理”，而非真正的通用智能。通过分析Scaling Law和基准测试，文章揭示了模型表现的提升更多源于记忆能力的增强，而非智能本身。它强调了区分记忆与推理的重要性，并指出虽然记忆是推理的基础，但真正的智能在于即时合成新解决方案的能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 智能与技能的本质区别：通用性非技能的简单叠加

演讲者首先阐述了**通用智能**（General Intelligence）的核心概念，并将其与**任务特定技能**（Task-Specific Skill）明确区分开来。通用智能并非将单一技能无限扩展，而是指一种能够快速掌握**任何**新技能、解决**任何**问题的能力，其关键在于能够利用**既有数据**（Valuable Old Data）来高效地面对未知挑战。这种能力使个体能够适应并即时学习（Learn on the Fly），这是“**通用性**”（Generality）的真正含义，而非简单地将特定技能“**规模化**”（Scaled Up）以覆盖更多领域。

<details>
<summary>Original English</summary>

general
 intelligence
 is
 not
 task


specific
 skill
 scaled
 up
 to
 many
 skills


because
 there
 is
 an
 infinite
 space of


possible
 skills
 general
 intelligence
 is


the
 ability
 to
 approach
 any
 problem
 any


skill
 and
 very
 quickly
 Master
 it
 using


Val
 old
 data
 because
 this
 is
 what
 makes


you
 able
 to
 face
 anything
 you
 might
 have


ear
 cont
 this
 is
 what
 makes
 uh
 uh
 this


this
 is
 the
 definition
 of
 generality


like
 generality
 is
 not
 specificity


scaled
 up
 it
 is
 uh
 the
 ability
 to
 apply


your
 mind
 to
 anything
 at
 all
 to


arbitrary
 things
 and
 this
 requires


fundamentally
 this
 requires
 the
 ability


to
 adapt
 to
 learn
 on
 the
 Fly
 efficiently

</details>

### “最大化主义”论点与Scaling Law的局限性

文章随后深入探讨了当前的“**最大化主义**”（Maximalist）论点，特别是其引用的“**Scaling Laws**”（LS）。这是一种在模型训练中观察到的经验性关系，描述了花费在训练上的**计算量**（Compute）与模型在**基准测试**（Benchmarks）中获得的**性能**（Performance）之间的关联。然而，核心问题在于如何衡量这种性能提升。演讲者强调，性能的衡量方式并非技术细节，它将直接**限定**我们提出的问题范围，进而**限制**我们寻找的答案。当前用于评估大型语言模型（LLMs）的基准测试，许多是**基于记忆**（Memorization-Based）的，有时甚至如同学校考试，仅需记忆一套固定的“**推理模式**”（Reasoning Patterns）并进行套用，而非真正的推理。

<details>
<summary>Original English</summary>

the
 scale
 uh
 a
 maximalist
 argument
 it


boils
 down
 to
 these
 people
 they
 refer
 to


scaling
 LS
 which
 is
 this
 this
 empirical


relationship
 that
 you
 can
 draw
 between


how
 much
 compute
 you
 spend
 on
 training


model
 and
 the
 performance
 you're
 getting


on
 benchmarks
 right
 and
 the
 the
 key


question
 here
 of
 course
 is
 well
 how
 do


you
 measure
 performance
 what
 it
 is
 that


you're
 actually


uh
 improving
 by
 adding
 more
 comput
 and


more
 data
 and
 well
 it's
 it's
 Benchmark


performance
 right
 and
 the
 thing
 is
 the


way
 you
 measure
 performance
 is
 not
 a


technical
 detail
 uh
 it
 it's
 it's
 not


it's
 not
 an
 afterthought
 because
 it's


going
 to
 uh
 narrow
 down
 the
 set
 of


questions
 that
 you're
 asking
 and
 so


accordingly
 it's
 going
 to
 narrow
 down


the
 set
 of
 answers
 that
 that
 you're
 that


you're
 looking
 for
 if
 you
 look
 at
 uh
 the


benchmarks
 we're
 using
 for
 LMS
 they're


all
 memorization
 based
 benchmarks
 like


sometimes
 they're
 literally
 just


knowledge
 based
 like
 like
 a
 school
 test


and
 even
 if
 you
 look
 at
 the
 ones
 that


are
 uh
 you
 know
 explicitly
 about


reasoning
 you
 realize
 if
 you
 look


closely
 that
 it's
 uh
 in
 order
 to
 solve


them
 it's
 enough
 to
 memorize
 uh
 a
 finite


set
 of
 uh
 uh
 resoning
 patterns
 uh
 and


then
 you
 just
 reapply
 them

</details>

### LLMs的“推理”：程序获取而非动态合成

当前的大型语言模型（LLMs）在处理这些基准测试时，表现得像是在执行“**程序获取**”（Program Fetching）。模型能够记忆并检索大量“**静态程序**”（Static Programs）或“**解决方案程序**”（Solution Programs），当面对新问题时，它们会从中“**提取**”（Fetch）最相关的程序并应用。这种模式看起来像是推理，但实际上并未涉及“**即时程序合成**”（On-the-Fly Program Synthesis）——即根据现有知识片段动态创建新解决方案的能力。

<details>
<summary>Original English</summary>

they
 they're


like
 static
 programs
 llms
 are
 very
 good


at
 memorizing
 CTIC
 programs
 small
 CTIC


programs
 and
 and
 they've
 got
 this
 sort


of
 like
 Bank
 of
 uh
 solution
 programs
 and


when
 you
 give
 them
 a
 new
 puzzle
 uh
 they


can
 just
 fetch
 the
 appropriate
 program


apply
 it
 and
 it's
 looking
 like
 it's


reasoning
 but
 really
 it's
 not
 doing
 any


sort
 of
 on
 thefly
 program
 synthesis
 all


it's
 doing
 is
 program
 fetching
 so
 you


can
 actually
 solve
 all
 these
 benchmarks


with
 memorization

</details>

### 技能提升不等于智能增长：理解记忆与智能的混淆

当我们增加模型的**数据库规模**（Size of your database）并填充更多知识和模式时，其在记忆型基准测试上的性能会随之提升，这一点显而易见。然而，这**并未**在任何程度上增加系统的**智能**（Intelligence）本身。模型能力的增长体现在“**技能**”（Skill）的提升——即其**有用性**（Usefulness）和**适用范围**（Scope of Applicability）的扩大，而非智能水平的提高。演讲者强调，**技能并非智能**，这是导致混淆的“**现象性困惑**”（Phenomenal Confusion），人们常常将两者混为一谈。这种混淆源于对模型“**内插**”（Interpolation）能力的误解，即模型在已知数据点之间进行插值，而非真正的理解和泛化。

<details>
<summary>Original English</summary>

and
 so
 what
 what


you're
 scaling
 up
 here
 like
 if
 you
 look


at
 the
 models
 they
 are
 uh
 big
 parametric


curves
 uh
 fitted
 to
 a
 data
 distribution


I
 descent
 so
 they
 are
 basically
 these


big
 interpolative
 uh
 databases


interpolative
 memories
 and
 of
 course
 if


you
 scale
 up
 the
 size
 of
 your
 database


and
 you
 cram
 into
 it
 uh
 more
 knowledge


more
 patterns
 and
 so
 on
 uh
 you
 are
 going


to
 be
 increasing
 its
 its
 performance
 as


measured
 by
 memorization
 Benchmark


that's
 that's
 kind
 of
 obvious
 but
 as


you're
 doing
 it
 you
 are
 not
 increasing


the
 intelligence
 of
 the
 system
 one
 bit


you
 are
 increasing
 the
 skill
 of
 the


system
 you
 you
 are
 increasing
 ining
 its


usefulness
 its
 uh
 scope
 of
 applicability


but
 not
 its
 intelligence
 because
 skill


is
 not
 intelligence
 and
 that's
 the


phenomal
 confusion
 um
 that
 that
 that


people
 run
 into
 is
 that
 they're


confusing
 skill
 and
 intelligence
 as
 far


as
 the
 interpolation
 goes

</details>

### 数学基准测试的启示：区分推理的定义

为了具体说明这一点，演讲者举了一个“**GSS 8K**”数学基准测试的例子。该测试包含的题目，如一道关于班级学生年龄分布的数学题，对于一个“**聪明的や学の生徒**”（Smart High Schooler）来说本应是可以解决的。模型在此类测试上能达到95%的准确率，但这仍是基于记忆。演讲者提出了**推理**的两种定义：第一种，即**拥有一个程序模板库**，识别问题的结构后**匹配并套用**记忆中的模板来生成解决方案；第二种，也是更困难的一种，即在**没有现成程序**可供套用时，能够**动态地合成**（Synthesize on the Fly）一个全新的程序，这需要将现有程序的片段重新组合。后者才是真正困难的，而模型目前擅长的是前者。

<details>
<summary>Original English</summary>

so
 okay
 let's
 look
 at
 one
 of
 the
 benchmarks
 here


there's
 there's
 one
 Benchmark
 that
 does


great
 school
 math
 and
 these
 are
 problems


that
 like
 a
 smart
 high
 schooler
 would
 be


able
 to
 solve
 um
 it's
 called
 GSS
 8K
 and


these
 models
 get
 95%
 on
 these
 like


basically
 they
 always
 nail
 memorization


 okay
 let's
 talk
 about
 what
 that


means
 so
 here's
 one
 question
 about
 from


that
 Benchmark
 so
 30
 students
 are
 in
 a


class
 one/
 fifth
 of
 them
 are
 12
 year


olds
 1/3
 are
 13y
 old
 1110th
 are
 11
 year


olds
 how
 many
 of
 them
 are
 not
 11
 12
 or


13
 years
 old
 so
 I
 agree
 like
 this
 is
 not


rocket
 science
 right
 you
 can
 write
 down


on
 paper
 how
 you
 go
 through
 this
 problem


and
 a
 high
 school
 kid
 at
 least
 a
 smart


high
 school
 kid
 should
 be
 able
 to
 solve


it
 now
 when
 you
 say
 memorization
 it's


still
 has
 to
 reason
 through
 how
 to
 think


about
 fractions
 and
 what
 is
 the
 context


of
 the
 whole
 problem
 and
 then
 combining


the
 different
 calculations
 is
 doing
 it


depends
 how
 you
 how
 you
 want
 to
 Define


reasoning
 but
 there
 there
 are
 two


definitions
 you
 can
 use
 so
 one
 is
 I
 have


available
 uh
 a
 set
 of
 program
 templates


it's
 it's
 like
 the
 structure
 of
 the


puzzle
 which
 which
 can
 also
 generate
 its


solution
 and
 I'm
 just
 going
 to
 identify


the
 right
 template
 which
 is
 in
 my
 memory


um
 I'm
 going
 to
 input
 the
 new
 value
 into


the
 template
 run
 the
 program
 get
 the


solution
 and
 you
 could
 say
 this
 is


reasoning
 and
 I
 say
 yeah
 sure
 okay
 uh


but
 another
 definition
 you
 can
 use
 is


reasoning
 is
 the
 ability
 to
 when
 you're


faced
 with
 a
 with
 a
 puzzle
 given
 that


you
 don't
 have
 already
 a
 program
 in


memory
 to
 solve
 it
 you
 must
 synthesize


on
 the
 fly
 a
 new
 program
 based
 on
 bits


of
 pieces
 of
 existing
 programs
 that
 you


have
 you
 have
 to
 do
 on
 the
 Fly
 program


synthesis
 and
 it's
 actually
 dramatically


harder
 than
 just
 fetching
 the
 right


memorized
 program
 and
 replying
 it

</details>

### 人类学习的普遍性与模型的记忆基础

演讲者进一步指出，我们可能**高估**了人类在样本效率上的程度。人类学习数学，例如代数、几何、微积分，需要多年的系统性教学和练习，而非仅仅观看一个示例就能掌握。这种“**训练**”（Training）过程，涉及反复钻研特定的**推理路径**（Pathways of Reasoning），与模型通过大量数据“**钻取**”（Drill）训练的过程在概念上有相似之处。尽管如此，为了实现“**即时程序合成**”，模型确实需要“**可用的积木**”（Building Blocks）——即**知识**（Knowledge）和**记忆**（Memory）。因此，记忆并非与推理对立，而是**极大地重要**（Tremendously Important）的，是有效推理的基础。

<details>
<summary>Original English</summary>

I
 think
 maybe
 we
 are
 overestimating
 the


extent
 to
 which
 humans
 are
 so
 sample


efficient
 they
 also
 don't
 need
 training


in
 this
 way
 where
 they
 have
 to
 drill
 in


these
 kinds


of
 Pathways
 of
 reasoning
 through
 certain


kind
 of
 problems
 so
 let's
 take
 math
 for


example
 yeah
 it's
 not
 like
 you
 can
 just


show
 a
 baby
 the
 axum
 of
 SE
 Theory
 and


now
 they
 know
 math
 right
 so
 they
 when


they're
 growing
 up
 you
 had
 to
 do
 years


of
 teaching
 them
 pre-algebra
 then
 you


got
 to
 do
 a
 year
 of
 teaching
 them
 doing


d
 and
 going
 through
 the
 same
 kind
 of


problem
 in
 algebra
 then
 geometry


pre-calculus
 calculus
 absolutely
 so


training
 yeah
 but
 isn't
 that
 like
 the


same
 kind
 of
 thing
 where
 you
 you
 you


can't
 just
 see
 one
 example
 and
 now
 you


have
 the
 program
 or
 whatever
 you


actually
 had
 to
 drill
 it
 these
 models


also
 had
 to
 drill
 with
 a
 bunch
 of
 fruit


training
 data
 sure
 I
 mean
 in
 order
 to
 do


on
 the-fly
 program
 synthesis
 you


actually
 need
 uh
 building
 blocks
 to
 work


from
 so
 knowledge
 and
 memory
 actually


tremendously
 important
 in
 the
 process


I'm
 not
 I'm
 not
 saying
 it's
 memory


versus
 reasoning
 in
 order
 to
 do


effective
 reasoning
 you
 need
 memory

</details>