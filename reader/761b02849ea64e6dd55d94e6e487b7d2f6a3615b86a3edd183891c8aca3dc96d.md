---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0PqGT2L6cZM
speaker: AI Engineer
tags:
  - document-parsing
  - rag
  - vertical-ai
  - build-versus-buy
title: Datasite为何停止自研文档解析：垂直AI落地与买建权衡
summary: Datasite全球CTO Raj Bakhru与Reducto联合创始人Adee对谈，分享了Datasite及前身Blue Flame如何权衡自研与采购，停止内部维护复杂的文档解析管线转而采用Reducto，以及结合专有虚拟数据室（VDR）数据构建垂直AI应用与评测基准VDR bench的实践经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Raj Bakhru
  - Adee
companies_orgs:
  - Datasite
  - Reducto
  - Blue Flame
products_models:
  - VDR bench
  - Turbo Buffer
media_books: []
status: evergreen
---
### 背景介绍与对话开场

>> 我个人对这次对话非常期待。简单做个自我介绍，我是 Adee，Reducto 的联合创始人兼 CEO。不过最重要的是，今天现场有 Datasite 的全球首席技术官 Raj。我感到兴奋的原因在于，我认为 Raj 对 AI 有着极其独到的视角，因为他在垂直 AI 领域很早就创立了公司，随后被 Datasite 收购，进而既能观察 Datasite 旗下的子公司，又能纵观 Datasite 整体。在这次对谈前我拿到了一些关于 Raj 的数据，比如超过 1 亿美元的交易中，大约有 60% 是通过 Datasite 完成的。
<details><summary>Original English</summary>
>> I'm
 personally
 really
 excited
 about
 this


talk.
 Uh,
 just
 by
 way
 of
 quick
 intro,


I'm
 Adee,
 I'm
 co-founder
 and
 CEO
 at


Reducto,
 uh,
 but
 most
 importantly,
 we


have
 Raj
 here
 who
 is
 the
 global
 chief


technology
 officer
 at
 Datasite.
 Um,
 the


reason
 why
 I'm
 excited,
 uh,
 is
 I
 think


Raj
 has
 probably
 one
 of
 the
 most


interesting
 viewpoints
 for
 AI
 in
 that
 he


founded
 company
 very
 early
 on
 in
 the


vertical
 AI
 space.
 Um,
 got
 acquired
 into


Datasite
 and
 then
 got
 to
 see
 both
 like


subsidiary
 within
 Datasite
 to
 think


about
 Datasite
 as
 a
 whole.
 Um,
 I
 got


some
 of
 Raj's
 stats
 before
 this
 talk,


um,


where
 something
 like
 60%
 of
 all


transactions
 over
 $100
 million
 happen


through
 Datasite.
</details>

>> 没错，确实如此。
<details><summary>Original English</summary>
>> That's
 correct,
 yeah.
</details>

>> 好。如果要列个排行榜的话，每年消耗超过万亿级别的 token，我相信你还有很多其他亮眼的数据。不过今天交流的目标是保持对话形式。我们会聊聊 Raj 的经历、他遇到过的一些难题，然后尽量留出时间进行问答，解答大家好奇的内容。听起来可以吗？

太棒了。

或许一开始，你愿意先梳理一下这段历程，聊聊幕后具体是什么样的吗？
<details><summary>Original English</summary>
>> Okay.
 Um,
 if
 we're
 making
 a
 leaderboard,


trillion
 plus
 tokens
 per
 year,
 I'm
 sure


you
 have
 plenty
 of
 other
 cool
 numbers,


um,
 but
 the
 goal
 for
 today
 is
 to
 make


this
 conversation.
 We'll
 talk
 a
 bit


about
 Raj's
 journey,
 um,
 some
 of
 the


problems
 he's
 gone
 through,
 and
 then


we'll
 try
 to
 open
 it
 up
 for
 Q&A
 as
 well


for
 whatever
 you
 all
 are
 curious
 about.


Sound
 good?


Cool.


Um,
 maybe
 to
 start,
 do
 you
 want
 to
 just


walk
 through
 that
 arc
 and
 what
 it
 looked


like
 behind
 the
 scenes?
</details>

### 从 Blue Flame 到 Datasite：垂直 AI 的起步与收购

>> 好的，完全没问题，谢谢。很高兴认识大家，我是 Raj Bakhru。我的背景是一名技术人员，整个职业生涯都专注于研发，起步于高盛（Goldman）、Highbridge、Kepos Capital，主要为量化基金构建研究和交易系统，做了很多有意思的事情。之后我创办了一家安全公司，卖给了一家私募股权支持的企业，后来在他们那里负责并购（M&A）和企业战略。之后我们在并购领域创办了名为 Blue Flame 的垂直 AI 解决方案，因为我们预料到非结构化数据将受到巨大的冲击。我们大概搭建了一年到一年半左右，随后 Datasite 联系我们商讨收购事宜。实际上在我们还是独立公司时、在 Datasite 收购我们之前，就已经开始与 Reducto 合作了。

当时我们是一家小型初创公司，非常精打细算，自己搭建了大量的解析、文档处理流水线（Doc Pipeline）和数据摄入管线（ingestion pipeline）。我们拥有一支优秀的团队，有出色的 CTO 和联合创始人。我们尽一切可能节省成本。当我们把这一切搭建起来时，觉得“太棒了，运转很正常”。直到后来遇到了瓶颈。稍后我会多聊聊那段历程。

后来我们被并入 Datasite，显然被收购时我们还处于非常早期的阶段，团队大概只有 50 人左右。Datasite 想让我们做的第一件事，就是接入他们所有的数据室（data rooms）。如果大家不熟悉数据室这个概念，数据室基本上就是企业出售过程中存放所有交易文档的地方。就像刚才 Adee 提到的，所有达到一定规模门槛（比如 1 亿美元以上）的交易中，约有 60% 是在 Datasite 上进行的。它主要是一个银行家与私募股权公司共享所有这些数据的平台。这意味着 Datasite 上存在着海量的非结构化数据，数十亿页的内容。每家主要银行都在使用它，每家私募股权公司都在使用它，每家尽调服务商都在使用它。Datasite 上有超过 50 万的月活跃用户在访问这些内容。这意味着，为平台引入 AI 解决方案显然成了董事会以及平台所有访问者最关心的议题。用户每天都在提出这类需求。

从我与 CTO 联合创始人草凑着搭建摄入管线的日子起，我们就拥有一支优秀的现代数据科学团队。后来我们显然转向了 Reducto，因为我们意识到在自研情况下，无法达到使用 Reducto 所能获得的质量水平、速度、召回率和成本。我可以讲讲促成我们做出该决定的一些数据，以及为什么这一选择在如今 Datasite 的体量下得到了验证。

但我们需要快速构建。我们需要将 Datasite 拥有的所有数据室（每年达 55,000 个数据室）进行解析，摄入到我们的向量数据库中，以便构建 Graph RAG 平台，并在数据室内大规模回答用户提交的问题。

所以摆在面前的难题是：我们如何将其构建到虚拟数据室（VDR）中？他们以前从未做过类似的事情，也从未将数据和内容移出过他们的 Azure 平台。在历史上，你可以想象，围绕数据室的防线是非常高的。这是世界上最敏感的数据，所有最重要的实质性非公开信息（MNPI）都存放在 Datasite 的虚拟数据室中。因此，我们必须找到一种安全可靠的方法来实现这一点。我们必须确保它符合客户所具备并传递给我们的所有合规制度，以及我们所拥有的全部认证（包括各类 ISO 认证等）。所以我们花了很多时间与 Adee 的团队探讨如何实现目标，如何确保所有内容始终受到保护和安全，并让我们对采用 Reducto 的工具感到踏实放心。
<details><summary>Original English</summary>
>> Yeah,
 for
 sure,
 appreciate
 that.
 Um,


good
 to
 meet
 everyone,
 Raj
 Bakhru.
 Uh,


my
 background's
 as
 a
 technologist,
 so
 I


spent
 my
 entire
 career
 in
 development,


started
 my
 career
 at
 Goldman,


Highbridge,
 Kepos
 Capital,
 was
 building


research
 and
 trading
 systems
 for
 quant


funds
 and
 all
 sorts
 of
 fun
 things.


Started
 a
 security
 firm
 that
 I
 sold
 to
 a


private
 equity
 back
 firm,
 ended
 up


running
 M&A
 and
 corporate
 strategy
 for


them.
 And
 then
 started
 this
 vertical
 AI


solution
 called
 Blue
 Flame
 in
 the
 M&A


space,
 um,
 because
 we
 sort
 of
 knew
 that


the
 impact
 to
 unstructured
 data
 was


going
 to
 be
 pretty
 pretty
 big.
 Um,
 so
 we


were
 building
 out
 for
 about
 a
 year,
 year


and
 a
 half,
 and
 then
 Datasite
 approached


us
 to
 acquire
 us.
 Um,
 and
 we
 started


working
 with
 Reducto
 actually
 while
 we


were
 separate,
 um,
 so
 before
 Datasite


had
 acquired
 us,


um,


we
 were
 small
 startup,
 we
 were
 scrappy,


uh,
 we
 built
 a
 lot
 of
 our
 own
 parsing


and
 Doc
 Pipeline
 and
 ingestion
 pipeline.


Um,
 had
 a
 great
 team,
 a
 great
 CTO,


co-founders.
 We
 were
 trying
 to
 save


every
 dollar
 we
 could.
 Um,
 so
 we
 when
 we


built
 all
 of
 that,
 we're
 like,
 "This
 is


great.
 It's
 working."
 Until
 it
 did.
 I


mean,
 I'll
 talk
 a
 little
 bit
 about
 that


journey.


Um,
 and
 then
 as
 we
 got
 brought
 into


Datasite,
 we
 were
 acquired
 obviously


very
 early
 on.
 Our
 team
 was
 about
 50


people
 at
 the
 time
 we
 got
 acquired.
 Um,


the
 first
 thing
 that
 Datasite
 wanted
 to


do
 with
 us
 was
 bring
 us
 into
 all
 of
 the


data
 rooms.
 And
 if
 you
 guys
 aren't


familiar
 with
 the
 data
 room
 concept,
 um,


data
 rooms
 are
 basically
 where
 all
 of


the
 transaction
 documents
 get
 stored


when
 you're
 selling
 a
 company.
 So,
 as
 I


deep
 mention,
 something
 like
 60%
 of
 all


transactions
 above
 a
 reasonable
 size


threshold,
 100
 million,
 happen
 on


Datasite.
 It's
 a
 place
 where
 people,


bankers
 primarily,
 are
 sharing
 all
 of


that
 data
 with
 private
 equity
 firms.
 Um,


so
 it
 means
 that
 there's
 a
 massive


unstructured
 data
 on
 Datasite,
 right?


Billions
 of
 pages
 of
 content.
 Every


major
 bank
 is
 using
 it.
 Every
 private


equity
 firm
 is
 using
 it.
 Every
 diligence


provider
 is
 using
 it.
 Over
 500,000


monthly
 active
 users
 on
 Datasite


accessing
 that
 content.
 Um,
 and
 that


meant
 that
 adding
 AI
 solutions
 was


obviously
 top
 of
 mind
 for
 the
 board
 and


everyone
 else
 who
 was
 accessing
 the


platform.
 Users
 were
 asking
 for
 it
 all


uh
 day
 and
 day
 out.


We
 had
 a
 great
 data
 science
 team
 um
 from


the
 days
 where
 my
 CTO
 co-founder
 and
 I


sort
 of
 scrapily
 built
 the
 ingestion


pipeline.
 We
 had
 obviously
 moved
 on
 to


Reducto,
 recognizing
 that
 we
 weren't


going
 to
 have
 the
 level
 of
 quality,


speed,
 um,
 recall,
 cost
 that
 we
 could


get
 with
 Reducto.
 And
 I
 can
 talk
 about


some
 of
 the
 numbers
 that
 led
 us
 to
 that


that
 decision.
 Um,
 and
 why
 that
 panned


out
 today
 with
 Datasite
 scale.


But
 we
 needed
 to
 build
 fast.
 We
 needed


to
 get
 all
 of
 the
 data
 rooms
 that


Datasite
 had,
 55,000
 data
 rooms
 a
 year,


um,
 parsed,
 ingested
 into
 our
 vector


database
 so
 that
 we
 could
 build
 out
 our


graph
 rank
 platform
 and
 answer
 questions


within
 the
 data
 room
 uh
 that
 users
 were


submitting
 at
 scale.


Um,
 so
 that
 was
 a
 problem
 at
 hand.
 How


How
 How
 do
 we
 build
 this
 into
 the
 VDR?


They'd
 never
 done
 anything
 like
 this.


They'd
 never
 taken
 their
 data
 their


content
 out
 of
 their
 Azure
 platform.


Historically,
 it's
 you
 know


the
 walls
 were
 high
 around
 the
 data


rooms
 as
 you
 can
 imagine.
 It's
 the


world's
 most
 sensitive
 data.
 All
 of
 the


most
 material
 material
 non-public
 info


out
 there
 sitting
 in
 data
 sites
 virtual


data
 rooms.
 Uh
 so
 we
 had
 to
 figure
 out
 a


way
 to
 do
 this
 securely.
 We
 had
 to


figure
 out
 a
 way
 to
 do
 it
 um
 in
 a


place
 that
 it
 uh


complied
 with
 all
 the
 regulatory


compliance
 regimes
 that
 our
 clients
 have


and
 pass
 on
 to
 us.
 All
 of
 the


certifications,
 the
 ISO
 certifications


and
 so
 on
 that
 that
 we
 had.
 Um
 so
 we


spent
 a
 lot
 of
 time
 with
 the
 Deeds
 team


in
 figuring
 out
 how
 to
 get
 there,
 how
 to


make
 sure
 that
 it
 all
 of
 the
 content


remained


protected
 um
 and
 secured
 and
 get
 us
 all


comfortable
 with
 leveraging
 uh
 Reducto's


tooling.
</details>

### 自研解析的困境：无休止的边缘用例与“买还是建”

>> 正如我刚才提到的，我们之所以选择 Reducto 的工具，原因在于：其一，我们必须快速行动；其二，我们的数据科学团队围绕自己草凑搭建的提取、解析和摄入工具进行了大量基准测试。谈到那个领域的现状，我想说的是：里面全都是边缘用例（edge cases）。几乎字面意义上的所有东西都是边缘用例。我记得在搭建完成后，我们与一些全球最大的私募股权公司合作，他们会发来我们 RAG 平台回答错误的示例。这里的 Carlos 应该还会记得其中的一些场景。
<details><summary>Original English</summary>
The
 reason
 that
 we
 went
 with
 Reducto's


tooling
 as
 I
 sort
 of
 alluded
 to
 is
 we


basically
 had
 to
 one
 move
 fast,
 but
 two


we
 did
 a
 whole
 bunch
 of
 benchmarking


actually
 with
 our
 data
 science
 team


around
 sort
 of
 our
 scrappily
 built


tooling
 for
 extraction
 and
 parsing
 and


ingestion.
 And
 what
 I
孔say
 about
 sort


of
 that
 landscape
 is
 that
 um
 it's
 all


edge
 cases.
 Like
 literally
 is
 everything


is
 an
 edge
 case.
 I
 remember
 getting,
 you


know,
 after
 we
 had
 built
 this
 we
 were


working
 with
 some
 of
 the
 world's
 largest


private
 equity
 firms
 and
 they
 would
 send


to
 us
 um
 examples
 where
 our
 reg
 platform


got
 a
 question
 wrong.
 And
 actually


Carlos
 here
 will
 will
 remember
 some
 of


these.
</details>

>> [笑声]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 你深入排查之后会发现，回答之所以出错，是因为这个饼图图例上的蓝色阴影没有完全对应上，即便我们使用了全球顶尖的视觉模型，大语言模型（LLM）还是读错了。而实际上，如果你把同样的内容以条形图而不是饼图传给同一个模型，它就能答对。细节决定成败，全都是这类繁杂的问题。在 Excel 表格方面，我们不得不处理合并单元格。大家也知道，金融电子表格是世界上最复杂的文档，人类要读懂这些东西都非常费劲。因此，让模型真正理解解析这部分内容并理解其含义的方法，是极其困难的。于是我们发现，自己耗费了海量的支持和排查时间来处理所有这些边缘用例。

如果我思考一下自研还是采购（buy versus build）之间的权衡取舍：我希望有限的高素质工程师把精力放在什么地方？绝不是为了确保内容能被正确提取而去处理那些技术支持用例，尤其是当这块问题已经被外部解决的时候。重新发明轮子没有任何意义。因此，当我们决定“把这个包袱交给 Reducto 吧”，我们获得了巨大的收益和杠杆。让我们的工程师去解决具有高附加值、能产生营收的业务问题；专注于构建客户真正在意的 Agent，优化界面交互与 RAG 平台。

对我们来说，构建 Graph RAG 是一件大事，我们在该流程中充分利用了 Reducto 的输出结果。所以我们希望数据科学团队专注于此，而不是把精力浪费在“如何从电子表格中准确提取数据”以及处理随之而来的各种痛苦上。紧接着你还会遇到诸如带宏的 XLSB 文件、模板文件等让人头疼的问题，简直没完没了，边缘用例真的是无穷无尽。所以我们非常感激 Reducto 为我们解决了其中的大量难题。
<details><summary>Original English</summary>
>> Um
 you'll
 dive
 into
 it
 and
 be
 like,
 well


I
 got
 it
 wrong
 because
 the
 shade
 of
 blue


on
 the
 legend
 of
 this
 pie
 chart
 didn't


correlate
 perfect
 perfectly
 and
 the
 LLM


just
 read
 it
 wrong
 even
 though
 we
 used


the
 best
 vision
 model
 in
 the
 world.
 And


actually
 if
 you
 were
 to
 pass
 that
 same


thing
 as
 a
 pie
 chart
 or
 that
 pie
 chart


um
 as
 a
 bar
 chart
 to
 that
 same
 model
 it


would
 have
 gotten
 it
 right.
 It
 just


the
 devil's
 in
 the
 details
 on
 all
 of


this
 stuff.
 Um
 on
 Excel
 sheets,
 we
 had


to
 deal
 with
 merged
 cells.
 And
 as
 you


guys
 know,
 finance
 spreadsheets
 are
 the


most
 complicated
 documents
 in
 the
 world.


Like
 it
 is
 hard
 for
 a
 human
 to


understand
 these
 things.
 Um
 so
 getting


the
 models
 to
 actually
 understand
 the


way
 to
 parse
 this
 this
 content
 out
 and


understand
 the
 content
 was
 very
 very


difficult.
 Um
 so
 we
 found
 that
 we
 were


just
 spending
 an
 enormous
 amount
 of


support
 time
 dealing
 with
 all
 these
 edge


cases.
 And
 if
 I
 sort
 of
 think
 about
 the


buy
 versus
 build
 trade-off,
 what
 do
 I


want
 my
 limited
 set
 of
 high-quality


engineers
 working
 on?
 It
 is
 not
 the


support
 cases
 of
 making
 sure
 that
 we're


extracting
 extracting
 content
 properly


um
 when
 that's
 already
 been
 solved.
 Like


you
 know,
 rebuilding
 the
 wheel
 doesn't


make
 sense.
 Um
 so
 we
 we
 got
 a
 tremendous


amount
 of
 benefit
 and
 leverage
 out
 of


saying
 let's
 let's
 pass
 that
 on
 to


Reducto.
 Let's
 let
 our
 engineers
 work
 on


value-add
 revenue-generating
 business


problems.
 Focus
 on
 building
 agents
 that


our
 clients
 care
 about
 executing
 on
 the


interface
 and
 the
 rag
 platform.
 Um


building
 out
 graph
 rag
 was
 actually
 a


big
 thing
 for
 us
 and
 we
 leveraged
 the


outputs
 of
 Reducto
 in
 that
 process.
 So


we
 wanted
 our
 data
 science
 team
 focused


on
 that,
 not
 on
 how
 do
 I
 get
 the
 right


data
 out
 of
 a
 spreadsheet
 um
 and
 dealing


with
 all
 of
 the
 pains
 that
 we


experienced
 on
 that.
 Then
 you
 you
 run


into
 the
 pains
 of
 like
 if
 it's
 an
 XLSB


file
 um
 macro-enabled,
 if
 it's
 a


template
 file,
 it
 just
 it's
 endless.


Literally
 the
 end
 edge
 cases
 are


endless.
 So
 we're
 very
 thankful
 to


Reducto
 for
 solving
 a
 lot
 of
 those


problems
 for
 us.
</details>

### 早期垂直 AI 赛道探索与加入 Datasite 的契机

>> 非常感谢你的认可。到目前为止我们已经有大约一年的合作默契了，不过我认为你的历程中最有意思的一点在于，你非常早就进入了垂直 AI 应用领域。而你所攻克的问题极其棘手，不仅因为你刚才提到的那些原因，还包含更多层面。特别是早期的大模型技术格局下，我相信那种困难感甚至更为不可逾越。所以我想先听你多聊聊加入 Datasite 之前的那段经历：你是如何创办 Blue Flame 的、当时希望实现什么目标，以及加入 Datasite 对这些产生了怎样的改变？
<details><summary>Original English</summary>
>> I
 appreciate
 that.
 Um
 at
 this
 point


we've
 had
 like
 a
 year
 of
 context,
 but
 I


think
 one
 of
 the
 most
 interesting
 things


about
 your
 journey
 is
 that
 you
 were
 very


early
 to
 the
 vertical
 AI
 app
 space.
 Um


and
 the
 problems
 that
 you
 work
 on
 are


hard
 um
 for
 many
 of
 the
 reasons
 that
 you


mentioned,
 but
 also
 like
 things
 beyond


that.
 Um
 and
 especially
 earlier
 with
 the


model
 landscape
 as
 it
 existed,
 I'm
 sure


it
 felt
 even
 more
 insurmountable.
 Um


so
 I'd
 love
 to
 start
 maybe
 just
 by


hearing
 a
 bit
 more
 of
 the
 pre-data
 site


journey
 of
 like
 how
 you
 got
 started
 with


Blue
 Flame,
 what
 you
 were
 hoping
 to


achieve,
 um
 and
 how
 joining
 Data
 Site


has
 kind
 of
 changed
 that.
</details>

>> 好的。我们创办这家初创公司时，在此之前我们曾非常早地卖掉过一家公司。上一家网络安全初创公司，我们在成立一年时就出售了。所以在创办这家公司时我们说：这次我们不会轻易脱手，一定要坚持做到底。[笑声] 这将是一段漫长的旅程，我们要成为独角兽，去实现所有想做的有趣事情。

这就是最初的状态。我找来了很多以前合作过的同事。作为二次创业者，好处之一就是你熟知圈子，清楚自己想把哪些人带进来。

所以我们非常幸运能够吸引很多这样的人加入，与我们认识并信任的团队一同起步；我们彼此可以激烈争论，但到头来依然是非常要好的朋友。我们了解彼此的家庭等等，因此第二次创业的起步体验非常棒。
<details><summary>Original English</summary>
>> Yeah.
 Um
 so
 when
 when
 we
 launched
 our


our
 startup
 startup,
 we
 had
 started
 we


had
 sold
 the
 startup
 very
 early
 on


before.
 The
 last
 startup,
 cybersecurity


startup,
 we
 sold
 a
 year
 in.
 And
 we


started
 this
 one
 saying
 we
 are
 not
 going


to
 sell
 quickly.
 We
 are
 going
 to
 see


this
 out.
 [laughter]


And
 it's
 going
 to
 be
 a
 long
 time
 and


we're
 going
 to
 be
 a
 unicorn
 and
 do
 all


those
 fun
 things
 that
 we
 wanted
 to
 do.


Um


So,
 that
 was
 that
 was
 the
 the
 initial


state.
 I
 brought
 in
 a
 lot
 of
 folks
 that


we'd
 worked
 in
 worked
 with
 before
 and


that's
 one
 of
 the
 nice
 things
 of
 being
 a


second
 time


founder
 is
 you
 kind
 of
 know
 the
 network,


you
 know
 the
 people
 you
 want
 to
 bring


in.


So,
 we
 were
 very
 fortunate
 to
 bring
 in
 a


lot
 of
 those
 people
 and
 start
 with
 a
 lot


of
 the
 people
 that
 we
 knew
 and
 trusted


and
 we
 could
 yell
 at
 each
 other
 and


still
 be
 really
 good
 friends
 at
 the
 end


of
 the
 day.
 Um
 and
 we
 knew
 each
 other's


families
 and
 all
 that.
 So,
 that
 really


nice
 experience
 to
 start
 as
 a
 second


time.
</details>

>> [轻笑]
<details><summary>Original English</summary>
>> [snorts]
</details>

>> 此外，庆幸的是第二次创业我们在很大程度上具备自我注资的能力。因此我们自筹资金（bootstrap）了一段时间并开展研发。然而，这再次导致我们做出了某些可能过度对成本敏感、并非最优的决策，但作为初创公司、尤其是花自己的钱时，你往往就会这么做。

我们在推进那套方案时获得了极佳的体验。我们本来正准备进行第一轮风险投资（VC round），已经签署了投资意向书（LOI）和条款清单（term sheet）。我们经历了与各大 VC 的“接触相亲”过程，走遍了沙丘路（Sand Hill Road）以及纽约的所有投资机构。当时距离最终签字只剩一周左右，而该轮融资还有额外的认购额度，投资人建议说“你们应该去看看这些人有没有兴趣”。于是我们接触了 Datasite，问他们：“你们想在这轮跟投 500 万美元吗？”我们进行了产品演示，展示了我们正在做的事情，结果他们对我们说：“实际上，我们想买下整家公司。”

我们当时的反应是：好的。这整件事简直是在一顿晚餐间敲定的。

就像在办公室开完会，当晚共进晚餐，然后他们就把这个想法告诉了我们。

于是我们非常迅速地做出了决断。我们之所以认为这个提议极具吸引力，是因为——如果大家还记得的话，那是大概一年半前。在那个节点，Claude 和 Office 办公套件还没有全面爆发。你得回溯到一年半前的大环境，感觉恍如隔世，当时的世界完全不同。Agent 编程（Agentic coding）也远未达到如今的普及程度。

所以我们深知自己必须筹集巨额资金。我们在垂直 AI 领域的竞争对手（其中也有与 Reducto 合作的）筹集了数亿美元，毫不夸张。

因此我们清楚，如果要保持竞争力，我们就得去融资数亿美元，而这样做将承受巨大的股权稀释。同时我们也明白，与前沿基础模型竞争将变得愈发困难，尤其是当他们开始推行垂直行业战略时。在那个时候，面向金融服务的 OpenAI（OpenAI for FS）以及面向金融服务的 Claude（Claude for FS）虽然尚未正式发布，但市场上已有传闻，他们也释放了一些风声。我们清楚，仅仅为了保持竞争力和差异化，我们就必须引入新型数据。对我们而言，虚拟数据室（VDR）是一处价值惊人的专有数据金矿，世界上从未有人接触过这批数据，而当时我们将成为唯一拥有其访问权限的人。因此这具有极大的吸引力。

此外，Datasite 旗下还拥有一家名为 Grata 的私营企业数据库公司，其数据库包含约 2,000 万家私营企业，涵盖交易数据、联系人等，在私募股权和银行业中被广泛用于项目搜寻（sourcing）、业务拓展与项目源开拓（origination）。比如，“我该如何为我的平台型投资组合公司寻找追加收购（add-ons）标的？”这就是一个非常典型的 Grata 式查询。

这些数据也可以被引入 Blue Flame。如此一来，我们便拥有了这两个非常优秀的专有数据集来赋能垂直 AI 领域，而这是其他任何人都不具备的。这构成了极佳的差异化优势。事实证明，这一策略成效斐然。在过去的一年半里，我们将它们深度融合在一起。

将工程团队、数据和解决方案紧密整合，对我们而言是一段非常美妙的故事。我们还对此进行了基准测试。比如，将数据拉近模型侧这一事实本身，既节省了 token 成本，缩短了运行耗时，又提升了我们业务成果的质量。因此，亲眼见证这一论断得以验证，是一件非常欣慰的事。

显然，所有这些数据处理都需要具备规模扩展能力。这再次体现了 Reducto 的价值，它在海量数据的摄入处理等方面为我们提供了巨大帮助。自我们加入以来的这一年半中，Datasite 的营收规模增长了约 40%。

因此，进入平台的内容量增长得非常迅猛且极其庞大。用户对我们 AI 解决方案的需求不断攀升。如今用户不再仅仅满足于“针对文档提问”，Agent 显然在对这些文档进行迭代分析，执行精细得多的尽职调查分析，或是生成幻灯片演示文稿、投资委员会备忘录（IC memos）等。因此，他们借助整套解决方案所能达成的能力是相当全面和完善的。
<details><summary>Original English</summary>
>> We
 also
 had
 the
 ability
 thankfully
 to


fund
 ourselves
 to
 a
 large
 extent
 this


this
 second
 time.
 So,
 we
 bootstrapped


for
 a
 while
 and
 started
 building.
 Now,


that
 again
 made
 us
 do
 some
 things
 that


might
 have
 been
 a
 little
 excessively


cost-sensitive


and
 not
 the
 most
 optimal
 decisions,
 but


that's
 what
 you
 do
 as
 a
 startup


and
 when
 it's
 your
 own
 money
 especially.


So,
 we
 had
 a
 really
 great
 experience


building
 that
 out.
 Uh
 we
 were
 actually


going
 to
 do
 our
 first
 VC
 round.
 We
 had


our
 LOI
 signed,
 term
 sheet
 signed.


We
 had
 done
 sort
 of
 the
 dating
 process


with
 all
 the
 VCs
 out
 there,
 the
 Sand


Hill
 Road
 walk
 and
 all
 the
 New
 York
 ones


and
 we
 were
 you
 know,
 a
 week
 away
 from


sort
 of
 final
 final
 signatures
 and
 there


was
 additional
 capacity
 on
 our
 round


and
 they
 said
 you
 should
 go
 you
 know,


see
 if
 these
 folks
 are
 interested
 and
 so


we
 we
 approached
 Data
 Science
 and
 we're


like,
 do
 you
 guys
 want
 to
 put
 in
 5


million
 in
 this
 round?
 And
 we
 demoed
 and


showed
 them
 a
 bit
 of
 what
 we
 were
 doing


and
 they
 said
 to
 us
 actually,
 we
 just


want
 to
 buy
 the
 whole
 company.


We're
 like,
 okay
 and
 literally
 happened


over
 a
 dinner.


Um


Like
 whatever
 meeting
 in
 the
 office,


subsequent
 dinner
 that
 night
 and
 then


they
 told
 us
 that.


So,
 we
 we
 very
 quickly
 sort
 of
 figured


it
 out.
 And
 the
 reason
 that
 we
 thought


it
 was
 really
 compelling


was
 if
 you
 know,
 this
 was
 about
 a
 year


and
 a
 half
 ago
 now.
 At
 that
 point
 sort


Cloud
 and
 Office
 Suite
 hadn't
 taken
 off.


You
 sort
 of
 have
 to
 go
 back
 to
 remember


where
 we
 were
 a
 year
 and
 a
 half
 ago.
 It


feels
 like
 forever
 ago
 and
 the
 world
 was


entirely
 different.
 Agentic
 coding


hadn't
 taken
 off
 to
 the
 level
 it
 has


now.
 Um


So,
 we
 knew
 that
 we
 had
 to
 raise
 a


massive
 amount
 of
 money.
 Our
 competitors


in
 the
 vertical
 AI
 space,


Um,
 of
 whom
 worked
 with
 Reducto,
 had


raised
 hundreds
 of
 millions
 of
 dollars,


literally.


Um,
 so
 we
 kind
 of
 knew
 that
 if
 we're


going
 to
 remain
 competitive,
 we
 were


going
 to
 be
 raising
 hundreds
 of
 millions


of
 dollars,
 we
 would
 be
 taking
 masses


mass
 dilution
 in
 doing
 that.
 Um,
 we
 also


knew
 that
 staying
 competitive
 against


the
 frontier
 models
 was
 going
 to
 be


increasingly
 difficult,
 particularly
 as


they
 were
 starting
 to
 launch
 vertical


strategies.
 And
 at
 that
 point,
 sort
 of


OpenAI
 for
 FS
 and
 Cloud
 for
 FS
 hadn't


been
 fully
 announced,
 but
 there
 were


some
 rumors
 around
 it.
 They'd
 made
 some


some
 ins-
 insinuations
 about
 it.
 Um,
 and


we
 knew
 that
 just
 to
 remain
 competitive


and
 differentiated,
 that
 we
 would
 have


to
 bring
 in
 new
 types
 of
 data.
 And
 to


us,
 the
 VDRs
 were
 this
 incredible


valuable
 resource
 of
 prop
 data
 that
 had


never
 been
 opened
 up
 to
 anyone
 in
 the


world,
 and
 we
 would
 be
 the
 only
 ones


with
 access
 to
 it
 at
 that
 time.
 So,
 that


was
 super
 compelling.


Um,
 Datasite
 also
 owns
 a
 private
 company


database
 firm
 called
 Grata.
 Has
 about
 20


million
 private
 companies
 in
 its


database,
 has
 transaction
 data,


contacts,
 etc.
 Used
 very
 heavily
 in


private
 equity
 and
 banking
 worlds
 for,


um,
 sourcing
 and
 business
 development


and
 origination.
 So,
 how
 do
 I
 find


add-ons
 for
 my
 platform
 portfolio


company?
 Uh,
 very
 classic
 Grata
 type


query.


That
 data
 would
 be
 brought
 into
 a


BlueFlame
 as
 well.
 So,
 now
 we
 had
 these


two
 really
 nice
 proprietary
 data
 sets


feeding
 us
 in
 a
 vertical
 AI
 space
 where


no
 one
 else
 would
 have
 that.
 Really
 nice


and
 differentiated.
 And
 that's
 played


out
 really
 nicely.
 So,
 over
 the
 over
 the


course
 of
 the
 last
 year
 and
 a
 half,


we've
 been
 bringing
 those
 really
 tightly


together
 and
 um,


that's
 [snorts]
 that's
 been
 a
 really


nice
 story
 for
 us
 to
 combine
 engineering


teams,
 combine
 data,
 combine
 solutions.


Um,
 and
 then
 we
 actually
 benchmark
 that.


Like,
 the
 the
 ability
 or
 the
 the
 fact


that
 we
 brought
 the
 data
 closer
 to
 the


models
 saves
 on
 token
 costs,
 it
 saves
 on


run
 run
 times,
 um,
 and
 increases
 quality


of
 what
 we're
 doing.
 So,
 that's
 been
 a


that's
 been,
 um,
 quite
 a
 nice
 thesis
 to


see
 pan
 out.


Um,


all
 of
 that
 data,
 obviously,
 requires


scale.
 So,
 that's
 that's
 again
 where


Reducto
 comes
 in
 and
 helps
 us
 with
 a
 lot


of
 that.
 Ingestion
 processing
 and
 and
 so


on.
 Datasite
 over
 the
 course
 of
 the
 last


year
 and
 a
 half
 since
 we've
 joined
 them


has
 grown,
 I
 want
 to
 say
 about
 40%
 top


line.


Um
 so
 just
 the
 amount
 of
 content
 that's


coming
 into
 the
 platform
 is
 is
 growing


pretty
 quickly
 and
 pretty
 massively.
 Um


the
 demand
 on
 our
 AI
 solutions
 have
 gone


up.
 So
 now
 people
 aren't
 just
 saying
 I


want
 to
 ask
 questions
 against
 documents,


the
 agents
 are
 obviously
 iterating


against
 those
 documents,
 doing
 much
 more


fanciful
 diligence
 analysis,
 or


generating
 PowerPoint
 decks,
 IC
 memos,


and
 so
 on.
 Um
 so
 it's
 pretty
 fullsome


suite
 of
 what
 they
 can
 what
 they
 can


accomplish
 with
 the
 solution
 together.
</details>

### 研发资源分配与杠铃效应

>> 是的。身处这样的位置非常特别，我认为你拥有该行业中最具吸引力的数据集之一。现在你所处的位置显然拥有全球化的团队，我们刚才还聊到了各个不同的办事处等等，而且模型能力已经有了显著提升。从更宽泛的角度来看，在内部研发投资与外部构建及采购之间，你是如何考量的？另外，展望未来一年，你最关注的又是什么？
<details><summary>Original English</summary>
>> Yeah.
 Um


it's
 an
 interesting
 position
 to
 be
 in
 in


that
 I
 I
 I
 think
 you
 have
 one
 of
 the


most
 compelling
 data
 sets
 in
 the


industry.
 Um


you're
 in
 a
 position
 now
 where
 obviously


it's
 a
 global
 workforce.
 We
 were
 talking


about
 all
 the
 different
 offices
 and
 all


of
 that.
 Um
 and
 model
 capabilities
 have


gotten
 a
 lot
 better.
 Um
 so
 more
 broadly


like
 how
 do
 you
 think
 about
 what
 you


invest
 in
 internally
 versus
 what
 you


build
 uh


and
 buy
 externally
 as
 well?
 Um


and
 also
 just
 like
 what
 sorts
 of
 things


are
 top
 of
 mind
 as
 you
 think
 about
 the


coming
 year?
</details>

>> 问得很好。我们对“自研还是采购”进行了很多思考。我们与很多供应商合作，也在很多供应商身上投入了大量预算。

这是一个深思熟虑的决定。

如果思考我希望最顶尖的人才去做什么，那绝不是外部供应商能够轻易解决、并且每天都专注在解决的事情。

寻找极具素质的优秀工程师是非常困难的。现实情况是，市场上每个人眼下都在努力争夺顶尖的工程技术人才。因为我们所目睹的（大家可能也都在经历的）是：在 AI 编程时代，从 AI 编程中获得最大杠杆和价值的人，是那些对代码库拥有极强心智模型、深刻理解工程原则、并且浸淫此道很久的人。

有了 AI 和 Agent 编程，他们都在原本 10 倍效能的基础上再次实现了 10 倍放大。中间层表现平平。底层人员实际上获得了很大的助力，他们不再背负去翻阅那些根本不存在的技术文档的沉重负担，LLM 可以为他们动态生成这些内容。因此我们看到了某种“杠铃效应”：我们既想招募非常非常顶尖的人才，也想招募非常初级的人才并加以培养。

我希望这些人投入精力的地方，显然不是技术支持工单，不是那些已经被解决的问题，而是公司最棘手、最紧迫的业务难题。

在我们的体量下——Datasite 的年营收还没达到 10 亿美元，但大体处于 10 亿美元营收的区间。在我们的规模下，要实现每年增长 20%（这是我们以及董事会的宏伟目标），我们需要每年创造 2 亿美元的增量营收。如果你问自己打算如何做到这一点，答案必然是：向市场推出新的 AI 产品，把握住 token 流量，扩大向客户交付的解决方案矩阵。

重新发明轮子无疑会阻碍这一目标的实现。让内部团队去试图迭代现有已成熟的解决方案并承担技术支持负担，绝不是对我手头人才的最佳使用方式。我的团队大约有 250 名工程师。如果对我希望这 250 人聚焦的方向进行分配，我们在全公司有五项重大战略举措。那是我们要推出的五个产生营收的项目：新系统的搭建或工具整合、新的商业化变现模式等。

我希望这 250 人分配在这些项目上，并且尽可能少的人去从事底层支撑工作。如果我能将底层的所有组件全部外包出去，对我团队而言将是最理想的时间分配。
<details><summary>Original English</summary>
Yeah.
 Um
 great
 question.
 So


we
 think
 a
 lot
 about
 the
 build
 versus


buy,
 right?
 We
 we
 work
 with
 a
 lot
 of


vendors.
 We
 spend
 a
 lot
 with
 a
 lot
 of


vendors.


Um
 and
 that's
 an
 intentional
 decision.


Um


if
 [snorts]
 I
 think
 about
 what
 I
 want
 my


my
 most
 talented
 people
 working
 on,
 it's


not
 things
 that
 vendors
 can
 easily


handle
 and
 are
 dedicated
 to
 handling
 and


solving
 every
 day.
 Um


it's
 really
 hard
 to
 find
 really
 high


quality
 good
 engineers,
 right?
 The
 fact


of
 the
 matter
 is
 where
 everyone
 in


market
 is
 trying
 to
 hire
 the
 top
 tier


talent
 of
 engineering
 talent
 right
 now


because


what
 we're
 seeing,
 what
 you
 guys
 are
 all


probably
 seeing
 it
 is
 with
 AI
 coding,


the
 folks
 who
 get
 the
 most
 leverage
 and


value
 out
 of
 AI
 coding
 are
 the
 folks
 who


have
 really
 strong
 mental
 models
 of
 code


bases,
 really
 understand
 engineering


principles,
 have
 done
 it
 for
 a
 long


time.
 Um


so
 they've
 all
 been
 10xed,
 you
 know,


over
 their
 normal
 10x
 uh
 with
 AI
 with


agentic
 coding.
 The
 middle
 layer,
 so-so.


Um
 the
 bottom
 layer
 is
 actually
 getting


a
 getting
 a
 lot
 of
 leverage
 and
 now
 they


don't
 they
 don't
 sort
 of
 uh
 have
 the


burden
 of
 trying
 to
 figure
 out


documentation
 that
 doesn't
 exist
 in
 all


of
 that.
 The
 LLMs
 can
 build
 that


dynamically
 for
 them.
 Um
 so
 we're
 seeing


sort
 of
 a
 barbell
 effect
 where
 we
 want


to
 hire
 really
 really
 strong
 talent
 and


really
 junior
 talent
 and
 build
 that
 up.


Um
 where
 I
 want
 those
 people
 working
 is


obviously
 not
 on
 support
 cases.
 It's
 not


on
 things
 that
 are
 already
 solved.
 Um


it's
 on
 the
 hardest
 and
 most
 pressing


problems
 for
 the
 business.


At
 our
 scale,
 so
 Data
 sites


not
 a
 billion-dollar
 top
 line,
 but


general
 range
 of
 a
 billion-dollar
 top


line.
 Um
 at
 our
 scale
 to
 grow
 20%
 a


year,
 which
 is
 our
 ambition
 or
 board's


ambition,
 uh
 we
 need
 to
 be
 generating


$200
 million
 of
 revenue
 incremental


revenue
 every
 year.
 And
 if
 you
 ask


yourself
 how
 you're
 going
 to
 go
 do
 that,


um
 it's
 going
 to
 be
 by
 putting
 new
 AI


products
 out
 in
 market,
 leveraging,


getting
 on
 top
 of
 token
 flow,
 expanding


solution
 set
 that
 you're
 delivering
 to


your
 clients.
 Um


reinventing
 the
 wheel
 is
 certainly
 going


to
 get
 in
 the
 way
 of
 that.
 Um


having
 internal
 teams
 trying
 to
 uh


iterate
 on
 some
 of
 the
 existing


solutions
 that
 are
 that
 are
 already
 out


there
 and
 deal
 with
 the
 support
 burden


of
 those
 is
 not
 the
 best
 use
 of
 my


talent.
 I
 have
 about
 250
 engineers
 in


the
 org.
 So
 if
 I
 allocate
 out
 where
 I


want
 those
 250
 focus,
 we
 have
 five
 major


initiatives
 across
 the
 firm.
 Um
 those


are
 five
 revenue-generating


projects
 that
 we're
 putting
 out,
 new
 new


builds
 or
 consolidations
 of
 tools,
 new


commercial
 or
 monetization
 models.


Um


I
 want
 those
 250
 people
 split
 across


those
 five
 and
 I
 want
 as
 few
 working
 on


the
 layers
 underneath
 that
 as
 possible.


And
 if
 I
 can
 outsource
 everything
 on
 the


under
 the
 layers
 underneath
 that,
 that's


an
 ideal
 um
 ideal
 split
 of
 time
 for
 my


my
 team.
</details>

### 当前痛点与多目标优化：质量、速度与成本

>> 明白。在把提问交给现场之前，我注意到我们还剩 2 分钟。最后想探讨的是：你觉得目前哪里还存在阻力？有哪些问题是你希望在座的各位能够帮你解决的？
<details><summary>Original English</summary>
>> Yeah.


Uh
 before
 I
 turn
 over
 for
 questions,
 I


realize
 we
 have
 2
 minutes.
 I
 guess
 maybe


one
 last
 thing
 is
 like
 where
 do
 you
 find


friction
 today?
 Um
 what
 are
 problems


that
 you
 would
 hope
 people
 in
 the


audience
 would
 solve
 for
 you?
</details>

>> 我们依然在为“如何让模型每次都严格按照我们的意图输出”而苦恼。

我们对所有模型进行了大量的实测与调优。如果回溯到接入 Reducto 之前的时期，我们浪费了大量时间去琢磨：哪种模型适合哪种类型的图表、适合传入的哪种文档。虽然我们已经摆脱了许多这方面的困扰，但在 Agent 层面仍然面临类似问题：比如在做基准测试时需要弄清，为什么 61 Soul 会出现工具调用刷屏（tool call spamming），而 Opus 55 就不会？但 61 Soul 价格又便宜得多，我们很想往这个方向切，正在努力让它达到预期表现。

因此，我们针对所关心的三个要素进行了大量的平衡优化：成本、速度和质量。在我们这个行业，质量对所有人而言都是重中之重。任何金融领域的客户为了获得最佳答案，都愿意支付任何代价。

所以我们必须确保始终在优先优化质量的前提下，努力兼顾解决另外两项。
<details><summary>Original English</summary>
Um


we
 still
 struggle
 with
 getting
 the


models
 to
 do
 exactly
 what
 we
 want
 all


the
 time.
 Um


we
 do
 a
 lot
 of
 working
 of
 all
 of
 the


models
 and
 actually,
 you
 know,
 if
 you


you
 back
 to
 pre-Reducto
 world,
 we
 wasted


a
 lot
 of
 time
 on
 trying
 to
 figure
 out


the
 right
 model
 for
 the
 right
 type
 of


chart
 for
 the
 right
 type
 of


uh
 document
 that
 we're
 passing
 in.
 So,


we've
 we've
 gotten
 rid
 of
 a
 lot
 of
 that,


but
 we
 still
 deal
 with
 it
 on
 the
 agent


front,
 trying
 to
 benchmark
 out,
 you


know,
 why
 is
 61
 Soul
 tool
 spam
 doing


tool
 call
 spamming
 when
 Opus
 55
 is
 not,


but
 then
 61
 Soul
 is
 so
 much
 cheaper
 that


we
 want
 to
 move
 in
 that
 direction,
 and


we're
 trying
 to
 get
 it
 to
 go
 to
 go


there.
 Um


so,
 we
 do
 a
 lot
 of
 sort
 of
 the


optimization
 of
 the
 three
 factors
 we


care
 about,
 which
 is
 cost,
 speed,
 and


quality.
 Quality
 is
 top
 top
 of
 mind
 for


everyone
 in
 our
 space,
 right?
 Like,
 any


finance
 user
 will
 pay
 any
 amount
 of


money
 to
 have
 the
 best
 answer.


Um
 so,
 we
 need
 to
 make
 sure
 we're
 always


optimizing
 on
 quality
 while
 trying
 to


solve
 the
 other
 two.
</details>

>> 确实很有道理。现场有什么问题吗？请讲。
<details><summary>Original English</summary>
>> Yeah.


Makes
 sense.


Any
 questions
 from
 the
 room?
 Yeah.
</details>

### 现场 Q&A：技术集成细节与专有评测基准 VDR bench

>> 能否稍微详细展开讲讲 Datasite 和 Reducto 之间的集成架构？
<details><summary>Original English</summary>
>> Can
 you
 zoom
 a
 little
 bit
 about
 the


integration
 between
 Data
 Science
 and


Reducto?
</details>

>> 好的。我们构建的环境中，Reducto 直接在我们的环境中针对我们全部的内容运行。我们有数十亿页的内容。当银行家上传大型数据集时，会出现非常集中的数据激增，随时可能瞬间涌入高达 1TB 的数据。因此我们拥有一套摄入流水线，接收所有这些数据并交由 Reducto 处理。拿到处理结果后，我们采用 Turbo Buffer 作为向量数据库，将其存入 Turbo Buffer。

随后我们在其上构建我们的 Graph RAG，并针对所有这些数据使用专有的 Python 代码执行所有的 Graph RAG 查询。

是的。
<details><summary>Original English</summary>
>> Yeah,
 so
 we
 have
 an
 environment
 where


Reducto's
 um


operating
 in
 our
 environment
 against
 all


of
 our
 content.
 We
 have
 bill-
 billions


of
 pages
 of
 content.
 We
 have
 very
 big


spurts
 of
 content
 when
 bakers
 are


dropping
 in
 large
 data
 sets,
 potentially


up
 to
 a
 terabyte
 of
 data
 can
 get
 dropped


in
 on
 a
 moment's
 notice.
 Uh
 so,
 we
 have


an
 ingestion
 pipeline
 that
 takes
 all
 of


that,
 passes
 it
 through
 Reducto.
 We
 get


that
 back.
 We
 We
 leverage
 Turbo
 Buffer


as
 our
 vector
 database,
 so
 we're
 passing


it
 off
 to
 Turbo
 Buffer.


Um
 and
 then
 we
 build
 our
 graph
 rag
 on


top
 of
 that.
 We
're
 executing
 all
 of
 our


graph
 rag
 queries


using
 Prop
 Python
 code
 against
 all
 of


that.


Yeah.
</details>

>> 我来自卖方机构。我们其实是 Datasite 的客户。
<details><summary>Original English</summary>
>> Um
 I'm
 on
 the
 sell
 side
 of
 things.
 Um


we're
 we
 are
 actually
 customers
 of
 Data


Science.
</details>

>> 卖方。
<details><summary>Original English</summary>
>> sell
 side
 is.
</details>

>> [笑声]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 我对 Reducto 很好奇。我们手头有很多交易数据——比如我们的文件系统里有海量的交易记录，我们希望将其提供给 Agent，但显然存在实质性非公开信息（MNPI）的问题。我们希望在数据进入类似 Reducto 这样的系统之前对其进行匿名化处理。
<details><summary>Original English</summary>
>> Um


curious
 about
 Reducto.
 So,
 we're
 sitting


on
 a
 transaction


like,
 we
 have
 a
 file
 system
 with
 a
 ton


of
 transactions,
 and
 we
 want
 to
 make


that
 available
 to
 agents,
 but
 there's
 a


way
 of
 obviously
 it's
 MNPI.
 We
 want
 to


anonymize
 that
 before
 it
 makes
 its
 way


into
 something
 like
 Reducto.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Hm.
</details>

>> 我们打算要么自研、要么采购，所以这次对话非常有启发。话虽如此，把数据交给 Agent 之前……你刚才提到你们构建了一套自定义评测（eval）。所以我很好奇你们是如何设计这套评测的。
<details><summary>Original English</summary>
>> We're
 going
 to
 either
 build
 this
 or
 buy


this,
 so


very
 helpful
 conversation.


That
 being
 said,


giving
 it
 to
 the
 agents


You
 You
 mentioned
 before
 that
 you
 built


a
 custom
 eval.


And
 so
 I
 I'm
 curious
 about
 how


Y'all
 went
 about
 this
 eval.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yep.
</details>

>> 未来有可能开源吗？不过我挺好奇你们是如何……
<details><summary>Original English</summary>
>> Potentially
 open
 sourced.


Um
 but
 like


curious
 about
 how
 you
 guys
</details>

>> 明白。关于我们的自定义评测：我们有几个不同的自定义评测，但与 Reducto 最紧密相关的是我们称为 VDR bench 的基准。我们目前尚未将其开源。实际上我们正在考虑开源，也正在考虑与 OpenAI 合作围绕它撰写一篇论文。在 VDR bench 中，我们基本上是选取一个包含数百份文档的典型虚拟数据室，针对该数据室提出几百个问题，并配有已知的标准答案集。

每当我们对系统做出改动时（几乎改动任何东西），我们都会运行该评测。我们期望它取得的分数要高于直接调用任何前沿实验室模型的分数。举例来说，如果你把同样的一组文件丢进 Claude Projects 或 OpenAI Projects 中，我们必须确保自己的表现能够击败它们。而我们能够胜出的一大原因在于，数据科学团队测得我们的召回率因为采用了 Reducto 解析而提升了 22%。

很大程度上是因为我们提取内容的方式。它实际上并不完全取决于后端的问答流程。很多人以为所有的工夫都要花在另一端（即生成回答端），但事实上大部分工作都集中在提取解析这一端。只要把提取解析做扎实，后续的一切才能顺理成章。
<details><summary>Original English</summary>
>> Yeah.


So
 our
 custom
 eval
 that's
 related
 to
 We


have
 a
 few
 custom
 evals,
 but
 the
 one


that's
 most
 relevant
 to
 Reducto
 is
 what


we
 call
 VDR
 bench.
 We
 haven't
 open


sourced
 it.
 We're
 actually
 thinking


about
 doing
 that,
 thinking
 about


partnering
 with
 OpenAI
 on
 a
 paper
 around


it.
 Um
 what
 we're
 doing
 with
 VDR
 bench


is
 we
 basically
 take
 a
 common
 virtual


data
 room
 of
 hundreds
 of
 documents,
 um


and
 we
 ask
 a
 few
 hundred
 questions


against
 that
 data
 room
 with
 the
 known


set
 of
 answers
 against
 those.


Um
 we
 run
 that
 every
 time
 we
 make


changes
 to
 to
 pretty
 much
 anything.
 Um


the
 scores
 on
 that
 we
 expect
 to
 be


higher
 than
 any
 of
 the
 uh
 frontier
 labs


directly.
 So
 if
 you
 were
 to,
 for


example,
 drop
 that
 same
 set
 of
 files


into
 cloud
 projects
 or
 OpenAI
 projects,


we
 need
 to
 make
 sure
 that
 we're
 beating


that.
 Um
 and
 a
 lot
 of
 the
 reason
 that
 we


beat
 that
 our
 data
 science
 team


benchmarks
 of
 our
 recall
 rate
 at,
 you


know,
 improving
 22%
 because
 of
 our


Reducto
 parsing.
 Um


you
 know,
 a
 lot
 of
 that's
 because
 of
 the


the
 way
 we
 pull
 out
 the
 content.
 It's


actually
 not
 the
 other
 side
 of
 it.
 A
 lot


of
 people
 think
 that
 sort
 of
 all
 the


work
 needs
 to
 be
 done
 on
 the
 other
 side,


the
 answering
 side,
 and
 most
 of
 the
 work


actually
 is
 on
 the
 extraction
 side.
 You


get
 that
 right,
 and
 everything
 else
 can


follow.
</details>