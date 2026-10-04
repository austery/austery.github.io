---
author: AI Engineer
date: '2026-05-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CrqPcIZOOXA
speaker: AI Engineer
tags:
  - ai-pricing
  - hybrid-pricing
  - value-based-pricing
  - billing-infrastructure
  - revenue-growth
title: AI定价策略：Stripe 如何赋能AI公司实现敏捷与灵活的营收增长
summary: 本视频探讨了AI经济的快速增长带来的定价挑战，包括利润波动、用户理解障碍及产品快速迭代。Stripe的Mayank Pant分享了识别客户价值、选择计费指标、采用混合定价模型、设置价格护栏以及持续迭代的关键五步框架。强调了灵活的计费基础设施对企业竞争力的重要性，并介绍了Stripe如何通过其全面的解决方案支持AI公司的营收增长。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mayank Pant
companies_orgs:
  - Stripe
  - OpenAI
  - Eleven Labs
  - Intercom
  - Tropic
  - Lovable
  - Anthropic
products_models:
  - Stripe Billing
  - Metronome
media_books: []
status: evergreen
---
### AI经济的爆炸式增长与定价的严峻挑战

Mayank Pant，Stripe的计费解决方案架构师，就AI定价的复杂性展开了深入探讨。他指出，AI经济正以前所未有的速度增长，是传统SaaS的三倍，头部AI公司实现2000万美元ARR的速度是SaaS公司的近三倍。然而，这种爆炸式增长也带来了严峻的挑战。AI公司的规模化速度极快，走向全球和扩展业务的步伐都远超以往，这使得**AI定价**变得异常困难。

传统SaaS定价模式通常拥有稳定且高企的毛利率（80-85%），但AI业务的特点是**利润较低**，且容易受到**算力消耗**和**用户行为**的影响。特别是“能力用户”（power users），他们可能仅占总用户的5-10%，却消耗了80%的计算资源，直接挤压利润空间。此外，**外部成本**如基础设施定价难以预测，可能严重损害利润。

更深层次的挑战在于**用户对定价的理解**。对于产品公司而言，以“tokens”或“API调用次数”为计费单位可能很自然，但对于终端用户来说，这种技术化的度量标准往往难以理解。例如，用户在使用Gamma这类AI工具时，更关心的是能生成多少演示文稿或幻灯片，而不是底层的API调用数量。同时，**产品迭代速度**远超定价更新速度，今天的高级功能可能在几个月后就成为标配，导致定价策略难以跟上产品演进的步伐。Stripe的研究显示，33%的AI公司担心不可预测的计算成本，41%的公司认为定义产品价值是挑战，而84%的公司则指出定价未能跟上产品推出速度。

<details>
<summary>Original English</summary>

>> Hello.
 Hi.


I'm
 Mayank.
 I'm
 from
 Stripe
 and
 I'm
 the


billing
 solution
 architect
 working
 in


Stripe.


And
 today
 we
 want
 to
 talk
 about
 AI


pricing.
 So
 we've
 got
 a
 billing
 engine


and
 a
 lot
 of


nowadays
 a
 lot
 of
 AI
 companies
 come
 to


us
 talk
 about
 how
 they
 want
 to
 do


billing,
 how
 we
 can
 help
 them
 with
 their


AI
 pricing.
 So
 based
 on
 the
 research


that
 our
 Stripe
 team
 has
 done
 on
 in
 the


over
 the
 last
 2
 years
 and
 based
 on
 our


experience,
 we
 want
 to
 share
 some
 of
 the


learnings
 with
 you
 guys.


So
 as
 we
 all
 know,
 AI
 economy
 is
 growing


at
 a
 record
 pace.


They
 they
 are
 growing
 three
 x
 faster


than
 traditional
 SaaS
 and
 based
 on


uh
 Stripe
 data,


this
 is
 what
 we
 see,
 right?
 The
 top
 100


AI
 companies


took
 20
 months
 to
 get
 to
 20
 million
 ARR


versus
 the
 top
 100
 SaaS
 companies
 which


took
 65
 months.
 So
 basically
 we
 are


growing
 at
 three
 x
 faster
 rate
 than
 what


we've
 seen
 before.


And
 though
 this
 is
 great,
 this
 is


exciting,
 but
 this
 is
 bringing
 new


challenges.
 The
 speed
 of


movement
 is
 so
 great
 that
 the
 companies


are
 now
 going
 global
 faster.
 They
 are


scaling
 up
 faster
 and


pricing
 that


pricing
 AI
 is
 becoming
 incredibly


challenging
 because
 of
 the
 speed
 that
 we


see.


So


we
 know
 that
 earlier
 it
 was
 traditional


SaaS
 pricing.
 Basically
 we
 had
 80
 85%


gross
 margins.
 They
 were
 not
 changing,


right?
 But
 with
 AI
 it's
 completely
 a


different
 thing,
 right?
 The
 margins
 are


low
 and


the
 margins
 get
 impacted
 based
 on
 how


many
 users
 are
 using
 your
 system.


So
 neither
 pure
 subscription
 nor
 pure


usage-based
 model
 offer
 us
 a
 complete


answer,
 right?


And
 the
 simple
 reason
 is
 we
 have
 margin


risk
 from
 power
 users.
 5
 to
 10%
 of
 your


users
 can
 use
 80%
 of
 your
 compute.


Uh
 external
 costs
 are
 unpredictable,


that
 is
 your
 infrastructure
 pricing,


right?
 Which
 can
 really
 hurt
 your


margins.


Technical
 pricing
 may
 overwhelm
 users.


What
 we
 mean
 by
 that
 is


for
 a
 product
 company
 talking
 in
 terms


of
 tokens,
 API
 calls
 might
 seem
 very


uh
 normal,
 but
 people
 on
 the
 other
 side


do
 not
 understand
 that
 technical


pricing.
 For
 me,
 for
 example,
 if
 I
 go


into
 Gamma,


I
 don't
 really
 mind
 how
 many
 API


calls
 am
 I
 using.
 I
 want
 to
 see
 how


many
 slides
 or
 how
 many
 decks
 did
 I


uh
 was
 I
 able
 to
 get
 out
 of
 the
 price


that
 I'm
 paying,
 right?


And


pricing
 is
 not
 able
 to
 keep
 up
 with
 the


product
 velocity.
 What
 might
 be
 a


premium
 feature
 today
 in
 6
 months
 maybe


a
 standard
 feature
 across.
 So
 are
 you


able
 to
 keep
 up
 with
 that
 pricing?


Uh
 so
 what
 we
 see
 at
 33%
 of
 our


AI-powered
 business
 site
 unpredictable


compute
 costs
 as
 their
 concern.


41%
 say
 that
 defining
 the
 value
 that
 is


being
 delivered
 is
 is
 a
 concern,
 right?


And
 84%
 of
 them
 talk
 about
 that
 we
 are


rolling
 out
 products
 faster,
 but
 we
 are


pricing
 is
 not
 keeping
 up
 with
 it.


So
 that
 is
 why
 what
 we
 say
 in
 iteration


is
 a
 competitive
 advantage.


The
 first
 price
 that
 you
 put
 in


is
 is
 a
 hypothesis.
 It
 is
 not
 a


commitment
 because
 you
 are
 bringing
 in


new
 features
 every
 week,
 every
 month
 and


with
 those
 new
 features
 and
 maybe
 the


old
 premium
 features
 are
 becoming


standard.
 So
 the
 pricing
 has
 to
 evolve


with
 the
 feature
 that
 you
 put
 in,
 right?


So
 frequent
 pricing
 change
 is
 a
 signal


of
 growth,
 right?
 You
 build
 the
 infrast-


infrastructure,
 you
 put
 your
 pricing
 in


the
 infrastructure
 that
 can
 iterate
 that


allows
 you
 to
 iterate
 rapidly,
 right?


So


this
 chart
 is
 one
 of
 my
 favorite.
 It


shows
 that
 hypergrowth
 companies
 which


are
 giving
 100%
 plus
 year
 on
 year


growth,
 they
 are
 changing
 their
 pricing


three
 plus
 times
 in
 the
 last
 2
 years.


They
 are
 not
 standing
 with
 their


pricing.
 49%
 is,
 you
 know,
 high
 growth.


They
 are
 they've
 changed
 three
 plus
 and


the
 low
 growth
 companies


are
 only
 22%
 who
 have
 changed
 it.
 And


that
 means
 that
 those
 low
 growth


companies
 have
 a
 static
 product,
 right?


And
 that
 is
 not
 where
 you
 want
 to
 be
 in


today's
 age.


So
 now
 where
 are
 these
 companies
 moving,


right?
 If
 you
 look
 at
 it,


hybrid
 pricing
 which
 was
 only
 6%
 in
 2024


is
 41%.


Outcome-based
 pricing
 is
 5%,
 right?
 And


where
 it
 has
 it
 picked
 up
 from?
 Se-


seat-based
 pricing,
 SaaS
 pricing,


subscription
 pricing
 is
 all
 declining


because
 the
 models
 are
 changing.


So
 as
 I
 said,
 hybrid
 pricing
 seven
 x


increase


and
 now
 56%
 of
 AI
 company
 leaders
 are


using
 hybrid
 pricing.
 Like
 we
 talked
 to


all
 the


all
 the
 companies
 such
 as
 Intercom,


Lovable,
 Eleven
 Labs,
 OpenAI
 and
 Tropic,


they
 are
 all
 building
 on
 Stripe,
 billing


on
 Stripe
 and
 all
 of
 them
 are
 using


hybrid
 pricing
 and
 I've
 also
 talked
 with


companies
 who
 were
 SaaS
 companies
 so
 far


which
 used
 to


uh
 help
 customer
 build
 workflows
 and


they
 were
 in
 SaaS
 pricing,
 but
 now
 as


soon
 as
 they
 bring


uh
 LLM
 AI
 into
 their
 product,
 then
 they


are
 also
 planning
 to
 move
 on
 to
 hybrid


pricing
 because
 SaaS
 pricing
 then
 starts


eroding
 their
 margins,
 right?


So
 to
 if
 if
 this
 is
 where
 we
 are
 going,


then


how
 do
 we
 start
 thinking
 about
 pricing?


How
 do
 we
 come
 to
 a
 right
 price?
 How
 do


we
 define
 our
 price?
 And
 how
 then
 do
 we


iterate
 it?


So
 the


we've
 got
 a
 five-step
 uh


a
 five-step
 framework
 for
 this
 and
 the


step
 one
 of
 that
 framework
 is
 you
 define


your
 value,
 right?


So
 what
 type
 of
 value
 can
 my
 product


provide?
 But
 not
 what
 your
 product
 is


doing,
 but
 what
 the
 what
 the
 customer


perceives
 your
 product
 to
 do.
 Like


again,
 like
 I
 took
 an
 example
 of
 Gamma.


For
 me
 as
 a
 customer,
 I
 need
 that


product
 to
 give
 me
 my
 presentation,
 my


decks.
 I
 don't
 care
 underneath
 how
 many


API
 calls
 is
 it
 making,
 where
 is
 it


going.
 My


uh
 for
 the
 for
 the
 customer
 it
 is
 the


quality
 of
 the
 deck
 and
 the
 relevancy
 of


that
 deck
 deck.


So
 53%
 of
 hypergrowth
 companies
 have


offered
 clear
 value-based
 pricing
 that


the
 customer
 understands


versus
 just
 26%
 of
 low
 growth
 peers.


And
 the
 way
 we
 look
 at
 it
 is


uh
 there
 are
 four
 broad
 frameworks
 on


which
 the
 first
 kind
 of
 these
 companies


are
 the
 company
 that
 are
 providing


automation.
 Like
 like
 I
 uh
 as
 a
 company


I'm
 helping
 them
 to
 save
 time
 and
 as
 a


customer
 what
 they
 are
 looking
 at
 it
 is,


okay,
 with
 the
 time
 saved
 I'm
 saving
 on


the
 cost,
 right?


Second
 is
 augmentation.


The
 number
 of
 people
 remain
 the
 same,


but
 the
 quality
 that
 they
 come
 out
 with


is
 much
 better.
 Like
 they
 can
 produce


images
 better.
 Probably
 for
 a
 campaign


provider
 they
 can
 build
 in
 better


campaigns
 more
 quicker.
 So
 they
 uh
 those


kind
 of
 augmentation
 the
 company
 looks


at
 it
 is,
 okay,
 I
 have
 the
 same
 number


of
 people,
 but
 they
 are
 more
 efficient,


they
 can
 deliver
 more
 value,
 right?


Third
 is
 the
 enhanced
 service.
 Maybe
 it


gives
 you
 an
 access
 to
 a
 proprietary


software


or
 some
 new
 uh
 data
 set
 that
 you


wouldn't
 have
 access
 otherwise,
 right?


For
 example,
 if
 you
 look
 at
 it
 look
 at


Stripe
 and
 our
 payment
 infrastructure,


we
 can
 uh
 do
 fraud
 recognition
 much


better
 because
 of
 the
 volume
 that
 flow


through
 us,


right?


And
 finally,
 the
 fourth
 kind
 of
 one
 is


the
 which
 gives
 you
 an
 improved
 results.


Like
 for
 example,
 company
 like
 Intercom


who
 says,
 I
 will
 price
 you
 based
 on
 the


number
 of
 tickets
 that
 I
 solved
 without


human
 need.
 So
 that
 is
 impacting
 the


direct
 bottom
 line.
 So
 once
 we
 realize


how
 we
 are
 helping
 the
 customers,
 how


our
 customer
 perceive
 it,
 that
 is
 when


we
 know
 the
 value
 and
 we
 know
 the
 price


that
 we
 can
 command
 in
 the
 market.


Once
 we've
 understood
 this
 is
 the
 value


that
 we
 are
 providing,
 then
 you
 define


your
 charge
 metric.


Like
 what
 is
 the
 billable
 unit
 that
 is


best
 representing
 my
 value,


right?
 And
 then
 you
 build
 features
 into


a
 currency
 that
 customers
 understand.


For
 example,
 is
 it
 consumption-based?


Like
 for
 an
 infrastructure
 company,


consumption-based
 might
 be
 the
 right


one.
 Like
 how
 many
 API
 calls
 did
 I
 help


you
 to
 make,
 right?


And
 this
 aligns
 to
 the
 cost
 of
 the


company
 that
 is
 providing
 that
 service.


Second
 could
 be
 the
 workflow-based.


Like
 how
 many
 images
 that
 was
 I
 able
 to


generate?
 How
 many
 documents
 was
 I
 able


to
 summarize?
 And
 this
 aligns
 to
 the


product,


and
 the
 third
 is
 the
 outcome-based
 as
 I


said.


How
 many
 business
 results
 did
 I


generate?
 So
 if
 if
 I
 am
 helping
 the


company
 to
 hire
 people,
 how
 many


uh
 candidate
 that
 I
 have
 put
 forward?


How
 many
 candidates
 were
 hired
 out
 of


those
 candidates
 resulting
 in
 saving


time?
 Or
 how
 many
 qualified
 leads
 did
 I


generate?
 Right?
 So,
 this
 aligns
 to
 your


customer
 ROI.


So,
 now
 that
 you've
 understood
 the
 value


that
 you're
 providing
 and
 you've
 decided


your
 charge
 metric
 against
 it,


we
 will
 we
 will
 see
 how
 they
 change
 it,


right?
 Like
 if
 you
 move
 from


consumption-based
 to
 outcome-based,
 it


is
 definitely
 easier
 to
 implement


consumption-based
 is
 much
 easier
 to


implement.
 But,
 it
 is
 harder
 to
 align
 to


value.
 Like
 if
 I
 if
 some
 company
 tells


me
 and
 says,
 "I
 allowed
 you
 1,000
 API


calls.
 I
 do
 not
 know
 what
 those
 1,000


API
 calls
 mean.
 I
 want
 to
 see
 how
 many


decks
 I
 generated
 as
 in
 my
 previous


example."


But,
 if
 you
 go
 from
 outcome-based
 to


consumption-based,


it
 is
 easier
 to
 sell.
 Like
 I
 can


definitely
 go
 to
 a
 customer
 and
 say,


"I
 will
 increase
 your
 outcome.
 I'll


increase
 your


uh
 candidate
 hired,
 but
 to
 attribute


value
 is
 difficult."


So,
 that
 is
 where
 the
 balance
 has
 to
 be


made
 and
 data
 is
 required
 to
 satisfy
 and


to
 make
 your
 case.


One
 of
 the
 pro
 tip
 is
 to
 translate
 value


with
 credit.
 Like
 bundle
 the
 features


into
 credits.
 Say
 that


"I
 am
 giving
 you
 100
 credits
 for
 the


month.
 And
 then
 beneath
 under
 the
 hood


of
 the
 credits,
 you
 can
 have
 your
 own


models
 how
 you
 get
 to
 that."
 But,
 that


helps
 the
 customer
 to
 understand,
 "Okay,


100
 credits
 and
 it
 will
 translate
 to
 uh


this
 particular
 ROI."


Once
 you've
 done
 that,


then
 that
 is
 where
 you
 pick
 your
 pricing


model.
 Now,
 is
 it
 a
 subscription
 fee?


The
 usefulness
 of
 subscription
 fee
 or


SaaS
 fee
 is
 predictable
 revenue.


It
 gives
 you
 a
 committed
 customer


relationship.
 Right?


How
 And
 then
 the
 second
 could
 be
 the


usage
 fee,


which
 scales
 with
 customer
 with
 protects


margins.
 But,
 the
 downside
 as
 I
 said
 is


for
 the
 SaaS
 fee,


uh
 your
 power
 users
 might
 burn
 your


margins.
 And
 for
 a
 usage
 fee,


uh
 the
 customer
 might
 be
 hesitant
 in


experimenting
 with
 your
 product.
 Like


going
 full
 deep
 because
 they
 do
 not
 know


what
 kind
 of
 a
 invoice
 will
 they
 uh


expend
 on
 this.


So,


pure
 subscription,
 pure
 usage-based
 was


a
 thing
 of
 the
 past.
 Now,
 as
 we
 saw
 in


the
 previous
 slides
 as
 well,
 everybody


is
 moving
 into
 the
 hybrid
 model.


So,
 what
 is
 the
 hybrid
 model?
 A
 hybrid


model
 will
 have
 a
 base
 fee
 and
 it
 will


have
 a
 scaling
 fee.


The
 base
 fee
 basically
 helps
 you
 to


establish
 a
 relationship
 with
 your


customer.


And
 the
 scaling
 fee
 or
 the
 usage
 fee
 on


top
 of
 it
 will
 allow
 them
 to
 experiment


as
 much
 as
 they
 want
 and
 then
 to
 pay
 for


the
 value
 that
 they
 derive
 out
 of
 your


platform.


So,
 you
 are
 not
 alienating
 any
 of
 the


user
 any
 category
 of
 the
 users.


Once
 you've
 established
 your


uh


pricing,


then
 you
 build
 in
 the
 guardrails
 because


a
 wrong
 bill
 can
 erode
 a
 lot
 of
 customer


trust.
 You
 might
 be
 doing
 great
 for
 the


three,
 four,
 five
 months,
 but
 if
 the
 on


the
 sixth
 month
 your
 bill
 goes
 wrong,


bill
 goes
 very
 high,
 then
 that
 those


customers
 go
 and
 then
 you
 work
 so
 hard


to
 retain
 those
 customers,


but
 then
 they
 leave
 you.


So,
 what
 safety
 feature
 do
 you


consider?


Like
 you
 are
 giving
 them
 flexible


pricing.


Now,
 you're
 building
 guardrails
 around


it,
 right?
 As
 the
 design
 principle
 is


fair
 it's
 simple
 here.
 Build
 fair


pricing,


but
 then
 do
 not
 surprise.


So,
 what
 what
 we
 what
 we
 advise
 people


to
 do
 is


put
 in
 usage
 caps.


Like
 I
 paid
 $20
 and
 then
 I've
 been
 given


100
 credits.


I
 say
 that
 after
 100
 credits,
 I've
 built


in
 a
 usage
 cap.
 You
 either
 pay
 more
 to


go
 ahead
 or
 we
 will
 stop
 and
 you
 wait


for
 the
 next
 month.
 So,
 that
 the


it
 is
 the
 customer
 that
 has
 remained
 in


control
 of
 their


uh
 usages.
 Right?


You
 build
 an
 automated
 notification.
 You


tell
 them
 when
 they've
 used
 50%,
 70%,


90%
 of


uh
 of
 their
 allocated
 limits
 because


this
 is
 building
 trust
 with
 the


customer.
 We
 are
 not
 trying
 to


uh
 cheat
 them.
 We
 are
 there
 trying
 to


inform
 them
 that
 this
 is
 what
 you've


used.
 These
 are
 the
 uh
 thing
 that
 you


can
 go
 ahead
 with
 now.
 You
 can
 top
 up.


You
 can
 do
 a
 manual
 top
 up.
 You
 can
 do


an
 auto
 top
 up.
 Or
 you
 can
 pause
 and


then
 start
 the
 next
 month
 when
 fresh


credits
 gets
 allocated
 to
 you.


And
 then
 you
 set
 rate
 limiting
 so
 that


no
 wrong
 code
 is
 burning
 through
 the


limits,
 right?
 So,
 this
 will
 protect
 you


and
 your
 customers
 both.


Once
 you've
 done
 these
 step
 one
 to
 four,


then
 the
 step
 five
 is
 you
 iterate,


right?
 You
 keep
 iterating.


84%
 agree
 that
 fast
 pricing
 adaptation


is
 a
 key
 competitive
 advantage.


As
 I
 said,


your
 first
 model
 is
 a
 hypothesis
 and
 you


keep
 building
 on
 that
 pricing
 as
 your


product
 keeps
 evolving.


You
 prioritize
 speed.
 You
 do
 not
 wait


for
 the
 right
 price
 right
 price
 point


and
 wait
 for
 a
 year
 before
 you
 put
 it.


You
 put
 a
 price
 point
 there
 which
 you


think
 is
 the
 right
 price
 point
 and
 then


you
 iterate.
 You
 talk
 to
 your
 customers.


Those
 guys
 who
 churn,
 you
 talk
 to
 them


and
 ask
 them
 why
 they
 are
 churning.
 Is


it
 a
 product-market
 fit?


Which
 is
 then
 you
 work
 on
 your
 product.


But,
 is
 it
 high
 price?
 Then
 you
 work
 on


your
 pricing.
 Right?


If
 they
 upgrade,
 you
 ask
 the
 same


questions.
 You
 run
 AB
 tests
 on
 pricing


to
 find
 the
 optimum
 point,
 but
 you


prioritize
 speed
 and
 you
 keep
 iterating.


And
 then
 you
 continuously
 realign
 to


your
 value.


Now,
 realigning
 to
 the
 value
 means
 as


you
 are
 rolling
 out
 new
 features,


you've
 already
 given
 them
 hybrid


pricing.
 You've
 already
 put
 in
 number
 of


credits.
 Under
 the
 hood,
 you
 can
 keep


changing
 what
 those
 credits
 means.
 Do
 do


those
 100
 credit
 that
 you've
 given
 them


means
 five
 API
 calls
 of
 a
 certain


category,
 10
 image
 generation
 of
 a


certain
 category?
 Whatever.
 So,
 under


the
 hood
 you
 can
 keep
 changing
 them.


But,
 you
 constantly


realign
 the
 value.


So,
 this
 is
 how
 all
 the
 companies
 have


been
 thinking
 about
 pricing.


This
 is
 how
 we've
 been


uh
 trying
 to
 help
 them.
 But,
 what
 is


most
 important
 in
 all
 this
 is


what
 kind
 of
 an
 infrastructure
 do
 you


have
 for
 your
 billing,
 for
 your
 pricing


that
 is
 helping
 you
 to
 do
 this?
 If
 every


change
 costs
 you


three
 months,
 four
 months,
 and
 a
 lot
 of


engineering
 effort,


then
 it
 is
 not
 worth
 it.
 So,


that
 is
 why
 it
 the
 infrastructure
 you


choose
 determine
 how
 fast
 you
 can


iterate.


And


uh
 from
 our
 side,
 the
 most
 flexible
 and


complete
 billing
 solution
 in
 market


is
 we've
 got
 Stripe
 and
 it
 is
 not
 us


that
 is
 saying
 it.


78%


of
 AI
 companies
 are
 building
 on
 Stripe,


which
 is
 a
 testimony
 in
 itself.


Most
 of
 the
 AI
 companies
 that
 you
 see


here


are
 building
 on
 Stripe
 like
 I
 said,


Anthropic,
 OpenAI,
 Lovable,
 Eleven
 Labs,


Intercom.
 They're
 all
 launching
 their


billing
 and


pricing.
 You
 might
 have
 associated


Stripe
 with


payments
 only,
 but
 in
 the
 last
 two,


three
 years
 we've


uh
 we've
 invested
 a
 lot
 into
 AI
 billing.


So,
 we've
 got
 Stripe
 Stripe
 billing


which
 allows
 you
 to
 go
 with
 subscription


pricing,
 usage
 pricing,
 hybrid
 pricing.


And
 as
 these
 companies
 are
 so
 quickly


within
 10
 to
 15
 months
 now
 starting
 with


the
 retail
 PLG
 motion
 going
 to


enterprises,
 we've
 got
 Metronome
 that


allows
 you
 to
 build
 all
 the


all
 the
 dif-
 difficult
 and
 complicated


contracts
 with
 the
 enterprises
 having


minimum
 commitments,


uh


pre-commitments,
 uh
 overage
 prices.
 So,


we've
 got
 that
 and
 we've
 got
 the
 whole


platform
 that
 allows
 you
 to
 do
 uh


payments,
 tax,
 invoicing,
 revenue


recognition


on
 this
 AI
 pricing.


So,


yeah,
 this
 is
 where
 we
 are
 right
 now


helping
 all
 our
 AI
 companies
 in
 the


market.


So,
 yeah,
 this
 this
 is
 me
 happy
 for
 any


questions


that
 you
 have.


Yes,
 please.


This
 is
 super
 interesting.


With
 the
 advice
 around
 changing
 your


pricing
 model
 fairly
 often,


one
 of
 the
 risks
 is
 that
 that
 can
 cause


frustration
 with
 customers
 and
 then
 they


might
 churn
 because
 of
 the


sort
 of
 the
 instability
 and
 it's
 less


predictable
 for
 them
 what
 their
 cost


structure
 is
 going
 to
 be.


So,
 have
 you
 got
 any
 advice
 around
 like


how
 to
 Yeah,
 so
 so
 what
 what
 people
 are


doing
 and
 what
 we
 also
 enable
 them
 to
 do


is
 they
 sell
 credits,
 right?
 But,
 what


do
 those
 credits
 mean?
 Like
 you
 got
 in


let's
 say


today
 in
 January
 you
 had
 one
 feature


that
 was
 your
 premium
 feature.
 It
 was


not
 replicated
 anywhere
 in
 the
 market


and
 you
 had
 assigned
 five
 credits
 for


that
 feature
 under
 the
 hood,
 right?


In
 six
 months,
 that
 feature
 becomes


standard
 feature.
 The
 pricing
 had


dropped
 and
 in
 the
 meanwhile
 you
 brought


in
 new
 features
 because
 you
 are
 also


competing
 in
 the
 market,
 right?
 So,


for
 the
 customer,
 he
 just
 see
 100


credits.


Under
 the
 hood,
 you
 are
 changing
 these


these
 calls
 or
 permutations
 like
 what


feature
 means
 how
 many
 limits.
 So,
 the


it
 is
 remain
 transparent
 for
 the


customer,
 it
 remains
 fair
 for
 the


customer,
 but
 based
 on
 your
 product


feature,
 you
 can
 keep
 changing
 pricing.


Plus,
 we
 can
 we
 also
 have
 features
 where


it
 allows
 you
 to
 grandfather
 pricing


like
 you
 bring
 in
 a
 new
 version.


I
 who
 have
 been
 using
 it
 still
 keeps


getting
 it
 on
 the
 same
 price,
 but
 the


new
 users
 have
 to
 pay
 more.


Yes,
 please.
 At
 what
 ACV
 do
 you
 start
 to


get
 better
 rates
 and
 more
 of
 an


enterprise
 management
 structure?
 Like,


how
 how
 much
 payment
 volume
 do
 I
 have
 to


do
 before
 I
 can
 start
 to
 get
 better


discounts?
 So,
 again,
 more
 on
 the
 sales


side,


but
 it
 depends
 on
 the
 volume
 like
 your


payment
 volume
 and
 your
 billing
 volume.


Basically,
 we
 like
 we
 we
 have
 a


platform.


We
 allow
 you
 to
 use
 as
 much
 of
 a


platform
 as
 you
 want
 or
 as
 little
 of
 it


as
 you
 want,
 right?
 And
 then
 depending


on
 the
 volume
 that
 is
 coming
 and
 we
 we


bring
 in
 all
 together.
 Let's
 say
 you
 are


using
 uh
 payment
 and
 billing
 together


but
 not
 using
 tax,
 that
 is
 fine.
 You


bring
 your
 payment
 and
 billing
 and
 then


our
 sales
 people
 start
 getting
 into
 it.


The
 sticker
 price,
 of
 course,
 is
 there


for
 everybody
 to
 see.


I'm
 not
 really
 sure
 on
 what
 is
 the


threshold
 that
 you
 know,
 start
 bringing


the
 price
 down
 because
 that's
 more
 on


the
 sales
 side,
 but
 do
 come
 over
 to
 our


uh
 booth.
 We've
 got
 some
 sales
 people


there.
 They'll
 be
 able
 to
 give
 you
 a


better
 answer
 to
 this.
 I've
 explained


you
 the
 mechanism,
 but
 the
 threshold


they'll
 be
 able
 to
 answer.


Yes,
 please.


Your
 thoughts
 on
 the
 presentation
 was


really
 interesting.
 Thank
 you.
 And
 one


thing
 I'm
 wondering,


how
 does
 for
 example
 the
 pricing
 model


of
 like
 big
 AI
 labs
 relate
 to
 this


iterative
 pricing?


I
 feel
 like


AI
 labs
 often
 have
 like
 multiple
 plans


which
 have
 like
 very
 constant
 pricing.


And
 then


like
 the
 roll
 out
 of
 features
 always


happen
 first
 on
 the
 expensive
 plans
 and


then
 they
 trickle
 down
 to
 like
 That
 is


true.
 the
 lower
 pricing.


And
 I
 don't
 really
 see
 like
 they
 don't


really
 use
 like
 iterative
 pricing
 in


their
 pricing.
 No,
 no,
 they
 they
 use
 it


under
 the
 hood.
 So,
 for
 them,
 for
 you,


like
 even
 if
 you
 go
 to
 11
 Labs,
 you'll


see
 four
 kind
 of
 plans
 there,
 right?
 Uh


let
 me
 call
 it
 good,
 better,
 best,
 and


then
 enterprise,
 right?
 You
 will
 just
 go


for
 you
 go
 for
 the
 best,
 right?
 They


will
 keep
 adding
 features
 or
 removing


features
 from
 one
 plan
 to
 the
 other.
 The


pricing
 will


They
 will
 try
 to
 remain
 constant
 with


the
 pricing
 for
 you,
 but
 inside
 it
 the


features
 will
 keep
 moving
 and
 that
 is


why
 they
 want
 to
 give
 it
 give
 you


credits
 or
 we
 advise
 that
 you
 give


credit
 to
 the
 customer
 so
 that
 the


all
 these
 features
 doesn't
 start


interacting
 with
 pricing.
 Okay,
 like
 the


customer
 facing
 prices
 stay
 stay


constant
 but
 linked
 to
 which
 plan?
 Yes,


they
 they
 let
 me
 say
 not
 the
 pricing
 the


customer
 facing
 plan
 remains
 constant,


right?
 Price
 might
 change
 again,
 but
 the


features
 will
 keep
 changing
 because
 it


has
 been
 abstracted
 by
 credits
 on
 the


top.
 Okay.
 Right,
 that's
 it.
 Yeah,
 you


had
 a
 question,
 sorry.
 Um


Yes,
 sir.


My
 question
 is
 does
 your
 platform


provide
 like
 a
 way
 to


record
 every
 transaction
 in
 your


system
 like


>> Every
 transaction.


Uh


that
 costs
 something
 and
 the
 user
 we
 can


track
 it.
 Yeah,
 so
 what
 what
 we
 do
 is


like


if
 the
 prompted
 like
 you
 make
 a
 prompt,


uh
 the
 customer
 is
 ingesting
 some
 uh


calls,
 you
 will
 send
 those
 calls
 to
 us.


You
 will
 tell
 us
 like
 we
 have
 all
 kind


of
 pricing
 in
 there.
 Tiered
 pricing,


dynamic
 pricing,
 uh
 dimension-based


pricing.
 You
 tell
 us
 what
 kind
 of


pricing
 does
 it
 go
 and
 then
 it
 it
 comes


in,
 we
 are
 able
 to
 rate
 it
 and
 price
 it


for
 you.
 And
 then
 you
 can
 get
 the
 whole


report
 on
 exactly
 why


why
 the
 invoice
 is
 what
 it
 is
 so
 we
 can


give
 you
 all
 the
 detailed
 pricing.


Right?


Thank
 you.


All
 right,
 if
 you
 have
 any
 other


question,
 then
 please
 feel
 free
 to
 come


to
 our
 booth,
 floor
 three,
 right?
 Thank


you
 so
 much.


>> [applause]


[music]

</details>

### 拥抱迭代：将定价视为持续进化的竞争优势

面对AI领域的高速发展，Mayank Pant强调**迭代是核心的竞争优势**。最初设定的价格是一个“假设”，而非“承诺”。随着新功能的每周、每月发布，尤其是当过去的高级功能成为标准时，定价必须随之演进。频繁的价格调整应被视为增长的信号。企业需要建立能够快速迭代的**计费基础设施**，而不是依赖僵化的系统。

他通过一个图表展示，年增长率超过100%的“超高速增长”公司，在过去两年内进行了三次或更多次定价调整。相比之下，低增长公司的定价则相对静态。这表明，静态产品和静态定价在当今时代已不再是理想的生存状态。

这种变化体现在市场趋势上：2024年，**混合定价**（hybrid pricing）的采用率从6%激增至41%，而基于座位、SaaS和订阅的传统定价模式则在下滑。目前，56%的AI公司领导者正在采用**混合定价**。许多企业，如Intercom、Lovable、Eleven Labs、OpenAI和Tropic，都选择在Stripe上构建其计费系统，并普遍采用混合定价。即使是过去主要依赖SaaS定价的公司，在引入AI和LLM技术后，也开始转向混合定价，以避免SaaS模式侵蚀利润。

<details>
<summary>Original English</summary>

So
 that
 is
 why
 what
 we
 say
 in
 iteration


is
 a
 competitive
 advantage.


The
 first
 price
 that
 you
 put
 in


is
 is
 a
 hypothesis.
 It
 is
 not
 a


commitment
 because
 you
 are
 bringing
 in


new
 features
 every
 week,
 every
 month
 and


with
 those
 new
 features
 and
 maybe
 the


old
 premium
 features
 are
 becoming


standard.
 So
 the
 pricing
 has
 to
 evolve


with
 the
 feature
 that
 you
 put
 in,
 right?


So
 frequent
 pricing
 change
 is
 a
 signal


of
 growth,
 right?
 You
 build
 the
 infrast-


infrastructure,
 you
 put
 your
 pricing
 in


the
 infrastructure
 that
 can
 iterate
 that


allows
 you
 to
 iterate
 rapidly,
 right?


So


this
 chart
 is
 one
 of
 my
 favorite.
 It


shows
 that
 hypergrowth
 companies
 which


are
 giving
 100%
 plus
 year
 on
 year


growth,
 they
 are
 changing
 their
 pricing


three
 plus
 times
 in
 the
 last
 2
 years.


They
 are
 not
 standing
 with
 their


pricing.
 49%
 is,
 you
 know,
 high
 growth.


They
 are
 they've
 changed
 three
 plus
 and


the
 low
 growth
 companies


are
 only
 22%
 who
 have
 changed
 it.
 And


that
 means
 that
 those
 low
 growth


companies
 have
 a
 static
 product,
 right?


And
 that
 is
 not
 where
 you
 want
 to
 be
 in


today's
 age.


So
 now
 where
 are
 these
 companies
 moving,


right?
 If
 you
 look
 at
 it,


hybrid
 pricing
 which
 was
 only
 6%
 in
 2024


is
 41%.


Outcome-based
 pricing
 is
 5%,
 right?
 And


where
 it
 has
 it
 picked
 up
 from?
 Se-


seat-based
 pricing,
 SaaS
 pricing,


subscription
 pricing
 is
 all
 declining


because
 the
 models
 are
 changing.


So
 as
 I
 said,
 hybrid
 pricing
 seven
 x


increase


and
 now
 56%
 of
 AI
 company
 leaders
 are


using
 hybrid
 pricing.
 Like
 we
 talked
 to


all
 the


all
 the
 companies
 such
 as
 Intercom,


Lovable,
 Eleven
 Labs,
 OpenAI
 and
 Tropic,


they
 are
 all
 building
 on
 Stripe,
 billing


on
 Stripe
 and
 all
 of
 them
 are
 using


hybrid
 pricing
 and
 I've
 also
 talked
 with


companies
 who
 were
 SaaS
 companies
 so
 far


which
 used
 to


uh
 help
 customer
 build
 workflows
 and


they
 were
 in
 SaaS
 pricing,
 but
 now
 as


soon
 as
 they
 bring


uh
 LLM
 AI
 into
 their
 product,
 then
 they


are
 also
 planning
 to
 move
 on
 to
 hybrid


pricing
 because
 SaaS
 pricing
 then
 starts


eroding
 their
 margins,
 right?

</details>

### AI定价的五步框架：从价值定义到持续迭代

为了应对AI定价的复杂性，Stripe提出了一个五步框架，指导企业如何科学地制定和演进其定价策略。

**第一步：定义你的价值 (Define Your Value)**
核心在于理解客户如何感知你的产品所提供的价值，而非仅仅描述产品功能。例如，用户使用Gamma工具是为了获得演示文稿，而不是关心其背后的API调用。**价值定义**应关注客户能获得的实际结果，如**自动化**（节省成本）、**增强**（提高效率和质量）、**增强服务**（访问专有数据或软件）或**改进结果**（直接影响底线，如Intercom解决的工单数量）。研究表明，提供清晰、客户易于理解的价值定价是**超高速增长**公司的关键。

**第二步：定义计费指标 (Define Your Charge Metric)**
选择一个能最佳代表产品价值的可计费单位。这可以是**基于消耗的 (consumption-based)**（如API调用次数，与公司成本挂钩，易于实施但难与价值对齐），**基于工作流的 (workflow-based)**（如生成的图片数量，与产品产出挂钩），或是**基于结果的 (outcome-based)**（如带来的业务成果、招聘数量、合格线索，与客户ROI直接关联，易于销售但难精确归因）。一个重要的技巧是将价值**翻译成客户理解的“积分”或“信用”**，使客户能够掌握其花费并预估ROI。

**第三步：选择定价模型 (Pick Your Pricing Model)**
模型选择需平衡公司收益和客户体验。**订阅费/SaaS费**提供可预测收入和客户承诺，但可能被“能力用户”侵蚀利润。**使用费**可随客户使用量扩展并保护利润，但可能让客户因账单不确定性而犹豫尝试。因此，**混合模型 (hybrid model)**成为主流，它结合了**基础费用**（建立客户关系）和**可扩展/使用费用**（鼓励尝试，按实际价值付费），从而不疏远任何类别的用户。

**第四步：构建价格护栏 (Build Guardrails)**
确保计费的公平性和可预测性，避免因意外高额账单损害客户信任。关键措施包括：
*   **使用上限 (Usage Caps)**：设定明确的消费额度，超出部分需额外付费或暂停服务，让客户掌控消费。
*   **自动化通知 (Automated Notifications)**：在用户达到50%、70%、90%的额度时发送提醒，建立信任。
*   **速率限制 (Rate Limiting)**：防止错误代码或异常流量消耗过多的资源，保护双方。

**第五步：持续迭代与价值对齐 (Iterate and Realign to Value)**
定价是一个持续演进的过程。初始定价是假设，需要不断根据产品发展和客户反馈进行调整。**优先考虑速度**，快速推出定价并根据客户反馈（如流失原因、产品-市场契合度）进行迭代。通过AB测试优化定价点。同时，即便采用混合定价和积分模式，也可在“幕后”调整积分的实际含义，使定价始终与客户感知到的核心价值保持一致。

<details>
<summary>Original English</summary>

So
 to
 if
 if
 this
 is
 where
 we
 are
 going,


then


how
 do
 we
 start
 thinking
 about
 pricing?


How
 do
 we
 come
 to
 a
 right
 price?
 How
 do


we
 define
 our
 price?
 And
 how
 then
 do
 we


iterate
 it?


So
 the


we've
 got
 a
 five-step
 uh


a
 five-step
 framework
 for
 this
 and
 the


step
 one
 of
 that
 framework
 is
 you
 define


your
 value,
 right?


So
 what
 type
 of
 value
 can
 my
 product


provide?
 But
 not
 what
 your
 product
 is


doing,
 but
 what
 the
 what
 the
 customer


perceives
 your
 product
 to
 do.
 Like


again,
 like
 I
 took
 an
 example
 of
 Gamma.


For
 me
 as
 a
 customer,
 I
 need
 that


product
 to
 give
 me
 my
 presentation,
 my


decks.
 I
 don't
 care
 underneath
 how
 many


API
 calls
 is
 it
 making,
 where
 is
 it


going.
 My


uh
 for
 the
 for
 the
 customer
 it
 is
 the


quality
 of
 the
 deck
 and
 the
 relevancy
 of


that
 deck
 deck.


So
 53%
 of
 hypergrowth
 companies
 have


offered
 clear
 value-based
 pricing
 that


the
 customer
 understands


versus
 just
 26%
 of
 low
 growth
 peers.


And
 the
 way
 we
 look
 at
 it
 is


uh
 there
 are
 four
 broad
 frameworks
 on


which
 the
 first
 kind
 of
 these
 companies


are
 the
 company
 that
 are
 providing


automation.
 Like
 like
 I
 uh
 as
 a
 company


I'm
 helping
 them
 to
 save
 time
 and
 as
 a


customer
 what
 they
 are
 looking
 at
 it
 is,


okay,
 with
 the
 time
 saved
 I'm
 saving
 on


the
 cost,
 right?


Second
 is
 augmentation.


The
 number
 of
 people
 remain
 the
 same,


but
 the
 quality
 that
 they
 come
 out
 with


is
 much
 better.
 Like
 they
 can
 produce


images
 better.
 Probably
 for
 a
 campaign


provider
 they
 can
 build
 in
 better


campaigns
 more
 quicker.
 So
 they
 uh
 those


kind
 of
 augmentation
 the
 company
 looks


at
 it
 is,
 okay,
 I
 have
 the
 same
 number


of
 people,
 but
 they
 are
 more
 efficient,


they
 can
 deliver
 more
 value,
 right?


Third
 is
 the
 enhanced
 service.
 Maybe
 it


gives
 you
 an
 access
 to
 a
 proprietary


software


or
 some
 new
 uh
 data
 set
 that
 you


wouldn't
 have
 access
 otherwise,
 right?


For
 example,
 if
 you
 look
 at
 it
 look
 at


Stripe
 and
 our
 payment
 infrastructure,


we
 can
 uh
 do
 fraud
 recognition
 much


better
 because
 of
 the
 volume
 that
 flow


through
 us,


right?


And
 finally,
 the
 fourth
 kind
 of
 one
 is


the
 which
 gives
 you
 an
 improved
 results.


Like
 for
 example,
 company
 like
 Intercom


who
 says,
 I
 will
 price
 you
 based
 on
 the


number
 of
 tickets
 that
 I
 solved
 without


human
 need.
 So
 that
 is
 impacting
 the


direct
 bottom
 line.
 So
 once
 we
 realize


how
 we
 are
 helping
 the
 customers,
 how


our
 customer
 perceive
 it,
 that
 is
 when


we
 know
 the
 value
 and
 we
 know
 the
 price


that
 we
 can
 command
 in
 the
 market.


Once
 we've
 understood
 this
 is
 the
 value


that
 we
 are
 providing,
 then
 you
 define


your
 charge
 metric.


Like
 what
 is
 the
 billable
 unit
 that
 is


best
 representing
 my
 value,


right?
 And
 then
 you
 build
 features
 into


a
 currency
 that
 customers
 understand.


For
 example,
 is
 it
 consumption-based?


Like
 for
 an
 infrastructure
 company,


consumption-based
 might
 be
 the
 right


one.
 Like
 how
 many
 API
 calls
 did
 I
 help


you
 to
 make,
 right?


And
 this
 aligns
 to
 the
 cost
 of
 the


company
 that
 is
 providing
 that
 service.


Second
 could
 be
 the
 workflow-based.


Like
 how
 many
 images
 that
 was
 I
 able
 to


generate?
 How
 many
 documents
 was
 I
 able


to
 summarize?
 And
 this
 aligns
 to
 the


product,


and
 the
 third
 is
 the
 outcome-based
 as
 I


said.


How
 many
 business
 results
 did
 I


generate?
 So
 if
 if
 I
 am
 helping
 the


company
 to
 hire
 people,
 how
 many


uh
 candidate
 that
 I
 have
 put
 forward?


How
 many
 candidates
 were
 hired
 out
 of


those
 candidates
 resulting
 in
 saving


time?
 Or
 how
 many
 qualified
 leads
 did
 I


generate?
 Right?
 So,
 this
 aligns
 to
 your


customer
 ROI.


So,
 now
 that
 you've
 understood
 the
 value


that
 you're
 providing
 and
 you've
 decided


your
 charge
 metric
 against
 it,


we
 will
 we
 will
 see
 how
 they
 change
 it,


right?
 Like
 if
 you
 move
 from


consumption-based
 to
 outcome-based,
 it


is
 definitely
 easier
 to
 implement


consumption-based
 is
 much
 easier
 to


implement.
 But,
 it
 is
 harder
 to
 align
 to


value.
 Like
 if
 I
 if
 some
 company
 tells


me
 and
 says,
 "I
 allowed
 you
 1,000
 API


calls.
 I
 do
 not
 know
 what
 those
 1,000


API
 calls
 mean.
 I
 want
 to
 see
 how
 many


decks
 I
 generated
 as
 in
 my
 previous


example."


But,
 if
 you
 go
 from
 outcome-based
 to


consumption-based,


it
 is
 easier
 to
 sell.
 Like
 I
 can


definitely
 go
 to
 a
 customer
 and
 say,


"I
 will
 increase
 your
 outcome.
 I'll


increase
 your


uh
 candidate
 hired,
 but
 to
 attribute


value
 is
 difficult."


So,
 that
 is
 where
 the
 balance
 has
 to
 be


made
 and
 data
 is
 required
 to
 satisfy
 and


to
 make
 your
 case.


One
 of
 the
 pro
 tip
 is
 to
 translate
 value


with
 credit.
 Like
 bundle
 the
 features


into
 credits.
 Say
 that


"I
 am
 giving
 you
 100
 credits
 for
 the


month.
 And
 then
 beneath
 under
 the
 hood


of
 the
 credits,
 you
 can
 have
 your
 own


models
 how
 you
 get
 to
 that."
 But,
 that


helps
 the
 customer
 to
 understand,
 "Okay,


100
 credits
 and
 it
 will
 translate
 to
 uh


this
 particular
 ROI."


Once
 you've
 done
 that,


then
 that
 is
 where
 you
 pick
 your
 pricing


model.
 Now,
 is
 it
 a
 subscription
 fee?


The
 usefulness
 of
 subscription
 fee
 or


SaaS
 fee
 is
 predictable
 revenue.


It
 gives
 you
 a
 committed
 customer


relationship.
 Right?


How
 And
 then
 the
 second
 could
 be
 the


usage
 fee,


which
 scales
 with
 customer
 with
 protects


margins.
 But,
 the
 downside
 as
 I
 said
 is


for
 the
 SaaS
 fee,


uh
 your
 power
 users
 might
 burn
 your


margins.
 And
 for
 a
 usage
 fee,


uh
 the
 customer
 might
 be
 hesitant
 in


experimenting
 with
 your
 product.
 Like


going
 full
 deep
 because
 they
 do
 not
 know


what
 kind
 of
 a
 invoice
 will
 they
 uh


expend
 on
 this.


So,


pure
 subscription,
 pure
 usage-based
 was


a
 thing
 of
 the
 past.
 Now,
 as
 we
 saw
 in


the
 previous
 slides
 as
 well,
 everybody


is
 moving
 into
 the
 hybrid
 model.


So,
 what
 is
 the
 hybrid
 model?
 A
 hybrid


model
 will
 have
 a
 base
 fee
 and
 it
 will


have
 a
 scaling
 fee.


The
 base
 fee
 basically
 helps
 you
 to


establish
 a
 relationship
 with
 your


customer.


And
 the
 scaling
 fee
 or
 the
 usage
 fee
 on


top
 of
 it
 will
 allow
 them
 to
 experiment


as
 much
 as
 they
 want
 and
 then
 to
 pay
 for


the
 value
 that
 they
 derive
 out
 of
 your


platform.


So,
 you
 are
 not
 alienating
 any
 of
 the


user
 any
 category
 of
 the
 users.


Once
 you've
 established
 your


uh


pricing,


then
 you
 build
 in
 the
 guardrails
 because


a
 wrong
 bill
 can
 erode
 a
 lot
 of
 customer


trust.
 You
 might
 be
 doing
 great
 for
 the


three,
 four,
 five
 months,
 but
 if
 the
 on


the
 sixth
 month
 your
 bill
 goes
 wrong,


bill
 goes
 very
 high,
 then
 that
 those


customers
 go
 and
 then
 you
 work
 so
 hard


to
 retain
 those
 customers,


but
 then
 they
 leave
 you.


So,
 what
 safety
 feature
 do
 you


consider?


Like
 you
 are
 giving
 them
 flexible


pricing.


Now,
 you're
 building
 guardrails
 around


it,
 right?
 As
 the
 design
 principle
 is


fair
 it's
 simple
 here.
 Build
 fair


pricing,


but
 then
 do
 not
 surprise.


So,
 what
 what
 we
 what
 we
 advise
 people


to
 do
 is


put
 in
 usage
 caps.


Like
 I
 paid
 $20
 and
 then
 I've
 been
 given


100
 credits.


I
 say
 that
 after
 100
 credits,
 I've
 built


in
 a
 usage
 cap.
 You
 either
 pay
 more
 to


go
 ahead
 or
 we
 will
 stop
 and
 you
 wait


for
 the
 next
 month.
 So,
 that
 the


it
 is
 the
 customer
 that
 has
 remained
 in


control
 of
 their


uh
 usages.
 Right?


You
 build
 an
 automated
 notification.
 You


tell
 them
 when
 they've
 used
 50%,
 70%,


90%
 of


uh
 of
 their
 allocated
 limits
 because


this
 is
 building
 trust
 with
 the


customer.
 We
 are
 not
 trying
 to


uh
 cheat
 them.
 We
 are
 there
 trying
 to


inform
 them
 that
 this
 is
 what
 you've


used.
 These
 are
 the
 uh
 thing
 that
 you


can
 go
 ahead
 with
 now.
 You
 can
 top
 up.


You
 can
 do
 a
 manual
 top
 up.
 You
 can
 do


an
 auto
 top
 up.
 Or
 you
 can
 pause
 and


then
 start
 the
 next
 month
 when
 fresh


credits
 gets
 allocated
 to
 you.


And
 then
 you
 set
 rate
 limiting
 so
 that


no
 wrong
 code
 is
 burning
 through
 the


limits,
 right?
 So,
 this
 will
 protect
 you


and
 your
 customers
 both.


Once
 you've
 done
 these
 step
 one
 to
 four,


then
 the
 step
 five
 is
 you
 iterate,


right?
 You
 keep
 iterating.


84%
 agree
 that
 fast
 pricing
 adaptation


is
 a
 key
 competitive
 advantage.


As
 I
 said,


your
 first
 model
 is
 a
 hypothesis
 and
 you


keep
 building
 on
 that
 pricing
 as
 your


product
 keeps
 evolving.


You
 prioritize
 speed.
 You
 do
 not
 wait


for
 the
 right
 price
 right
 price
 point


and
 wait
 for
 a
 year
 before
 you
 put
 it.


You
 put
 a
 price
 point
 there
 which
 you


think
 is
 the
 right
 price
 point
 and
 then


you
 iterate.
 You
 talk
 to
 your
 customers.


Those
 guys
 who
 churn,
 you
 talk
 to
 them


and
 ask
 them
 why
 they
 are
 churning.
 Is


it
 a
 product-market
 fit?


Which
 is
 then
 you
 work
 on
 your
 product.


But,
 is
 it
 high
 price?
 Then
 you
 work
 on


your
 pricing.
 Right?


If
 they
 upgrade,
 you
 ask
 the
 same


questions.
 You
 run
 AB
 tests
 on
 pricing


to
 find
 the
 optimum
 point,
 but
 you


prioritize
 speed
 and
 you
 keep
 iterating.


And
 then
 you
 continuously
 realign
 to


your
 value.


Now,
 realigning
 to
 the
 value
 means
 as


you
 are
 rolling
 out
 new
 features,


you've
 already
 given
 them
 hybrid


pricing.
 You've
 already
 put
 in
 number
 of


credits.
 Under
 the
 hood,
 you
 can
 keep


changing
 what
 those
 credits
 means.
 Do
 do


those
 100
 credit
 that
 you've
 given
 them


means
 five
 API
 calls
 of
 a
 certain


category,
 10
 image
 generation
 of
 a


certain
 category?
 Whatever.
 So,
 under


the
 hood
 you
 can
 keep
 changing
 them.


But,
 you
 constantly


realign
 the
 value.


So,
 this
 is
 how
 all
 the
 companies
 have


been
 thinking
 about
 pricing.


This
 is
 how
 we've
 been


uh
 trying
 to
 help
 them.
 But,
 what
 is


most
 important
 in
 all
 this
 is


what
 kind
 of
 an
 infrastructure
 do
 you


have
 for
 your
 billing,
 for
 your
 pricing


that
 is
 helping
 you
 to
 do
 this?
 If
 every


change
 costs
 you


three
 months,
 four
 months,
 and
 a
 lot
 of


engineering
 effort,


then
 it
 is
 not
 worth
 it.
 So,


that
 is
 why
 it
 the
 infrastructure
 you


choose
 determine
 how
 fast
 you
 can


iterate.


And


uh
 from
 our
 side,
 the
 most
 flexible
 and


complete
 billing
 solution
 in
 market


is
 we've
 got
 Stripe
 and
 it
 is
 not
 us


that
 is
 saying
 it.


78%


of
 AI
 companies
 are
 building
 on
 Stripe,


which
 is
 a
 testimony
 in
 itself.


Most
 of
 the
 AI
 companies
 that
 you
 see


here


are
 building
 on
 Stripe
 like
 I
 said,


Anthropic,
 OpenAI,
 Lovable,
 Eleven
 Labs,


Intercom.
 They're
 all
 launching
 their


billing
 and


pricing.
 You
 might
 have
 associated


Stripe
 with


payments
 only,
 but
 in
 the
 last
 two,


three
 years
 we've


uh
 we've
 invested
 a
 lot
 into
 AI
 billing.


So,
 we've
 got
 Stripe
 Stripe
 billing


which
 allows
 you
 to
 go
 with
 subscription


pricing,
 usage
 pricing,
 hybrid
 pricing.


And
 as
 these
 companies
 are
 so
 quickly


within
 10
 to
 15
 months
 now
 starting
 with


the
 retail
 PLG
 motion
 going
 to


enterprises,
 we've
 got
 Metronome
 that


allows
 you
 to
 build
 all
 the


all
 the
 dif-
 difficult
 and
 complicated


contracts
 with
 the
 enterprises
 having


minimum
 commitments,


uh


pre-commitments,
 uh
 overage
 prices.
 So,


we've
 got
 that
 and
 we've
 got
 the
 whole


platform
 that
 allows
 you
 to
 do
 uh


payments,
 tax,
 invoicing,
 revenue


recognition


on
 this
 AI
 pricing.


So,


yeah,
 this
 is
 where
 we
 are
 right
 now


helping
 all
 our
 AI
 companies
 in
 the


market.


So,
 yeah,
 this
 this
 is
 me
 happy
 for
 any


questions


that
 you
 have.


Yes,
 please.


This
 is
 super
 interesting.


With
 the
 advice
 around
 changing
 your


pricing
 model
 fairly
 often,


one
 of
 the
 risks
 is
 that
 that
 can
 cause


frustration
 with
 customers
 and
 then
 they


might
 churn
 because
 of
 the


sort
 of
 the
 instability
 and
 it's
 less


predictable
 for
 them
 what
 their
 cost


structure
 is
 going
 to
 be.


So,
 have
 you
 got
 any
 advice
 around
 like


how
 to
 Yeah,
 so
 so
 what
 what
 people
 are


doing
 and
 what
 we
 also
 enable
 them
 to
 do


is
 they
 sell
 credits,
 right?
 But,
 what


do
 those
 credits
 mean?
 Like
 you
 got
 in


let's
 say


today
 in
 January
 you
 had
 one
 feature


that
 was
 your
 premium
 feature.
 It
 was


not
 replicated
 anywhere
 in
 the
 market


and
 you
 had
 assigned
 five
 credits
 for


that
 feature
 under
 the
 hood,
 right?


In
 six
 months,
 that
 feature
 becomes


standard
 feature.
 The
 pricing
 had


dropped
 and
 in
 the
 meanwhile
 you
 brought


in
 new
 features
 because
 you
 are
 also


competing
 in
 the
 market,
 right?
 So,


for
 the
 customer,
 he
 just
 see
 100


credits.


Under
 the
 hood,
 you
 are
 changing
 these


these
 calls
 or
 permutations
 like
 what


feature
 means
 how
 many
 limits.
 So,
 the


it
 is
 remain
 transparent
 for
 the


customer,
 it
 remains
 fair
 for
 the


customer,
 but
 based
 on
 your
 product


feature,
 you
 can
 keep
 changing
 pricing.


Plus,
 we
 can
 we
 also
 have
 features
 where


it
 allows
 you
 to
 grandfather
 pricing


like
 you
 bring
 in
 a
 new
 version.


I
 who
 have
 been
 using
 it
 still
 keeps


getting
 it
 on
 the
 same
 price,
 but
 the


new
 users
 have
 to
 pay
 more.


Yes,
 please.
 At
 what
 ACV
 do
 you
 start
 to


get
 better
 rates
 and
 more
 of
 an


enterprise
 management
 structure?
 Like,


how
 how
 much
 payment
 volume
 do
 I
 have
 to


do
 before
 I
 can
 start
 to
 get
 better


discounts?
 So,
 again,
 more
 on
 the
 sales


side,


but
 it
 depends
 on
 the
 volume
 like
 your


payment
 volume
 and
 your
 billing
 volume.


Basically,
 we
 like
 we
 we
 have
 a


platform.


We
 allow
 you
 to
 use
 as
 much
 of
 a


platform
 as
 you
 want
 or
 as
 little
 of
 it


as
 you
 want,
 right?
 And
 then
 depending


on
 the
 volume
 that
 is
 coming
 and
 we
 we


bring
 in
 all
 together.
 Let's
 say
 you
 are


using
 uh
 payment
 and
 billing
 together


but
 not
 using
 tax,
 that
 is
 fine.
 You


bring
 your
 payment
 and
 billing
 and
 then


our
 sales
 people
 start
 getting
 into
 it.


The
 sticker
 price,
 of
 course,
 is
 there


for
 everybody
 to
 see.


I'm
 not
 really
 sure
 on
 what
 is
 the


threshold
 that
 you
 know,
 start
 bringing


the
 price
 down
 because
 that's
 more
 on


the
 sales
 side,
 but
 do
 come
 over
 to
 our


uh
 booth.
 We've
 got
 some
 sales
 people


there.
 They'll
 be
 able
 to
 give
 you
 a


better
 answer
 to
 this.
 I've
 explained


you
 the
 mechanism,
 but
 the
 threshold


they'll
 be
 able
 to
 answer.


Yes,
 please.


Your
 thoughts
 on
 the
 presentation
 was


really
 interesting.
 Thank
 you.
 And
 one


thing
 I'm
 wondering,


how
 does
 for
 example
 the
 pricing
 model


of
 like
 big
 AI
 labs
 relate
 to
 this


iterative
 pricing?


I
 feel
 like


AI
 labs
 often
 have
 like
 multiple
 plans


which
 have
 like
 very
 constant
 pricing.


And
 then


like
 the
 roll
 out
 of
 features
 always


happen
 first
 on
 the
 expensive
 plans
 and


then
 they
 trickle
 down
 to
 like
 That
 is


true.
 the
 lower
 pricing.


And
 I
 don't
 really
 see
 like
 they
 don't


really
 use
 like
 iterative
 pricing
 in


their
 pricing.
 No,
 no,
 they
 they
 use
 it


under
 the
 hood.
 So,
 for
 them,
 for
 you,


like
 even
 if
 you
 go
 to
 11
 Labs,
 you'll


see
 four
 kind
 of
 plans
 there,
 right?
 Uh


let
 me
 call
 it
 good,
 better,
 best,
 and


then
 enterprise,
 right?
 You
 will
 just
 go


for
 you
 go
 for
 the
 best,
 right?
 They


will
 keep
 adding
 features
 or
 removing


features
 from
 one
 plan
 to
 the
 other.
 The


pricing
 will


They
 will
 try
 to
 remain
 constant
 with


the
 pricing
 for
 you,
 but
 inside
 it
 the


features
 will
 keep
 moving
 and
 that
 is


why
 they
 want
 to
 give
 it
 give
 you


credits
 or
 we
 advise
 that
 you
 give


credit
 to
 the
 customer
 so
 that
 the


all
 these
 features
 doesn't
 start


interacting
 with
 pricing.
 Okay,
 like
 the


customer
 facing
 prices
 stay
 stay


constant
 but
 linked
 to
 which
 plan?
 Yes,


they
 they
 let
 me
 say
 not
 the
 pricing
 the


customer
 facing
 plan
 remains
 constant,


right?
 Price
 might
 change
 again,
 but
 the


features
 will
 keep
 changing
 because
 it


has
 been
 abstracted
 by
 credits
 on
 the


top.
 Okay.
 Right,
 that's
 it.
 Yeah,
 you


had
 a
 question,
 sorry.
 Um


Yes,
 sir.


My
 question
 is
 does
 your
 platform


provide
 like
 a
 way
 to


record
 every
 transaction
 in
 your


system
 like


>> Every
 transaction.


Uh


that
 costs
 something
 and
 the
 user
 we
 can


track
 it.
 Yeah,
 so
 what
 what
 we
 do
 is


like


if
 the
 prompted
 like
 you
 make
 a
 prompt,


uh
 the
 customer
 is
 ingesting
 some
 uh


calls,
 you
 will
 send
 those
 calls
 to
 us.


You
 will
 tell
 us
 like
 we
 have
 all
 kind


of
 pricing
 in
 there.
 Tiered
 pricing,


dynamic
 pricing,
 uh
 dimension-based


pricing.
 You
 tell
 us
 what
 kind
 of


pricing
 does
 it
 go
 and
 then
 it
 it
 comes


in,
 we
 are
 able
 to
 rate
 it
 and
 price
 it


for
 you.
 And
 then
 you
 can
 get
 the
 whole


report
 on
 exactly
 why


why
 the
 invoice
 is
 what
 it
 is
 so
 we
 can


give
 you
 all
 the
 detailed
 pricing.


Right?


Thank
 you.


All
 right,
 if
 you
 have
 any
 other


question,
 then
 please
 feel
 free
 to
 come


to
 our
 booth,
 floor
 three,
 right?
 Thank


you
 so
 much.


>> [applause]


[music]

</details>

### Stripe的解决方案：构建灵活且完整的AI计费基础设施

Mayank Pant在回答关于定价模型演进和客户担忧时，着重强调了**灵活的计费基础设施**的重要性。他指出，如果每一次定价调整都需要数月甚至大量工程投入，那么这种模式将难以持续。因此，选择正确的计费基础设施是实现快速迭代和保持竞争力的关键。

Stripe凭借其在支付领域的深厚积累，已大力投资于**AI计费**领域，提供了一个“最灵活和完整的解决方案”。目前，78%的AI公司选择在Stripe上构建其计费系统，这本身就是一项有力的证明。众多知名AI公司，如Anthropic、OpenAI、Lovable、Eleven Labs和Intercom，都在使用Stripe进行计费和定价。

Stripe提供的解决方案包括：
*   **Stripe Billing**：支持订阅、使用量和混合定价模型。
*   **Metronome**：为企业提供复杂的合同管理能力，包括最低承诺、预付款和超额价格等。
*   **全面的平台**：支持支付、税务、发票和收入确认等一站式服务。

在Q&A环节，当被问及如何缓解频繁价格调整给客户带来的不确定性时，Mayank Pant解释说，公司通过**销售积分（credits）**来实现客户体验的稳定。客户看到的“100个积分”在内部可以代表不同的功能组合或API调用量，允许企业在不改变客户界面价格的情况下，根据产品迭代和价值变化调整后台的“积分含义”。这种方式确保了对客户的**透明和公平**。此外，Stripe还支持“**保留旧定价（grandfather pricing）**”策略，允许老用户继续享受原有价格，而新用户则采用新定价。

关于企业客户的**ACV（年合同价值）和折扣**，Mayank Pant表示这更多取决于**支付和账单的总体量**。Stripe平台本身允许客户按需使用，其销售团队可以根据具体情况提供更详细的折扣阈值信息。

对于大型AI实验室的定价模式，Mayank Pant解释说，它们同样在使用**迭代定价**，只是将其“置于幕后”。例如，Eleven Labs提供不同层级的套餐（Good, Better, Best, Enterprise），客户看到的是固定的套餐价格，但套餐内的**功能会随着产品演进而调整**，并通过积分系统进行抽象，以保持客户面前价格的稳定性。

最后，当被问及平台是否支持记录和追踪每一笔产生费用的交易时，Mayank Pant确认Stripe可以做到。无论是用户输入的提示（prompt）、API调用，还是其他计费动作，Stripe都能将其转化为**分级、动态或基于维度的定价**，并提供详细的**账单报告**，清晰展示每一笔费用的构成。

<details>
<summary>Original English</summary>

And
 uh
 from
 our
 side,
 the
 most
 flexible
 and


complete
 billing
 solution
 in
 market


is
 we've
 got
 Stripe
 and
 it
 is
 not
 us


that
 is
 saying
 it.


78%


of
 AI
 companies
 are
 building
 on
 Stripe,


which
 is
 a
 testimony
 in
 itself.


Most
 of
 the
 AI
 companies
 that
 you
 see


here


are
 building
 on
 Stripe
 like
 I
 said,


Anthropic,
 OpenAI,
 Lovable,
 Eleven
 Labs,


Intercom.
 They're
 all
 launching
 their


billing
 and


pricing.
 You
 might
 have
 associated


Stripe
 with


payments
 only,
 but
 in
 the
 last
 two,


three
 years
 we've


uh
 we've
 invested
 a
 lot
 into
 AI
 billing.


So,
 we've
 got
 Stripe
 Stripe
 billing


which
 allows
 you
 to
 go
 with
 subscription


pricing,
 usage
 pricing,
 hybrid
 pricing.


And
 as
 these
 companies
 are
 so
 quickly


within
 10
 to
 15
 months
 now
 starting
 with


the
 retail
 PLG
 motion
 going
 to


enterprises,
 we've
 got
 Metronome
 that


allows
 you
 to
 build
 all
 the


all
 the
 dif-
 difficult
 and
 complicated


contracts
 with
 the
 enterprises
 having


minimum
 commitments,


uh


pre-commitments,
 uh
 overage
 prices.
 So,


we've
 got
 that
 and
 we've
 got
 the
 whole


platform
 that
 allows
 you
 to
 do
 uh


payments,
 tax,
 invoicing,
 revenue


recognition


on
 this
 AI
 pricing.


So,


yeah,
 this
 is
 where
 we
 are
 right
 now


helping
 all
 our
 AI
 companies
 in
 the


market.


So,
 yeah,
 this
 this
 is
 me
 happy
 for
 any


questions


that
 you
 have.


Yes,
 please.


This
 is
 super
 interesting.


With
 the
 advice
 around
 changing
 your


pricing
 model
 fairly
 often,


one
 of
 the
 risks
 is
 that
 that
 can
 cause


frustration
 with
 customers
 and
 then
 they


might
 churn
 because
 of
 the


sort
 of
 the
 instability
 and
 it's
 less


predictable
 for
 them
 what
 their
 cost


structure
 is
 going
 to
 be.


So,
 have
 you
 got
 any
 advice
 around
 like


how
 to
 Yeah,
 so
 so
 what
 what
 people
 are


doing
 and
 what
 we
 also
 enable
 them
 to
 do


is
 they
 sell
 credits,
 right?
 But,
 what


do
 those
 credits
 mean?
 Like
 you
 got
 in


let's
 say


today
 in
 January
 you
 had
 one
 feature


that
 was
 your
 premium
 feature.
 It
 was


not
 replicated
 anywhere
 in
 the
 market


and
 you
 had
 assigned
 five
 credits
 for


that
 feature
 under
 the
 hood,
 right?


In
 six
 months,
 that
 feature
 becomes


standard
 feature.
 The
 pricing
 had


dropped
 and
 in
 the
 meanwhile
 you
 brought


in
 new
 features
 because
 you
 are
 also


competing
 in
 the
 market,
 right?
 So,


for
 the
 customer,
 he
 just
 see
 100


credits.


Under
 the
 hood,
 you
 are
 changing
 these


these
 calls
 or
 permutations
 like
 what


feature
 means
 how
 many
 limits.
 So,
 the


it
 is
 remain
 transparent
 for
 the


customer,
 it
 remains
 fair
 for
 the


customer,
 but
 based
 on
 your
 product


feature,
 you
 can
 keep
 changing
 pricing.


Plus,
 we
 can
 we
 also
 have
 features
 where


it
 allows
 you
 to
 grandfather
 pricing


like
 you
 bring
 in
 a
 new
 version.


I
 who
 have
 been
 using
 it
 still
 keeps


getting
 it
 on
 the
 same
 price,
 but
 the


new
 users
 have
 to
 pay
 more.


Yes,
 please.
 At
 what
 ACV
 do
 you
 start
 to


get
 better
 rates
 and
 more
 of
 an


enterprise
 management
 structure?
 Like,


how
 how
 much
 payment
 volume
 do
 I
 have
 to


do
 before
 I
 can
 start
 to
 get
 better


discounts?
 So,
 again,
 more
 on
 the
 sales


side,


but
 it
 depends
 on
 the
 volume
 like
 your


payment
 volume
 and
 your
 billing
 volume.


Basically,
 we
 like
 we
 we
 have
 a


platform.


We
 allow
 you
 to
 use
 as
 much
 of
 a


platform
 as
 you
 want
 or
 as
 little
 of
 it


as
 you
 want,
 right?
 And
 then
 depending


on
 the
 volume
 that
 is
 coming
 and
 we
 we


bring
 in
 all
 together.
 Let's
 say
 you
 are


using
 uh
 payment
 and
 billing
 together


but
 not
 using
 tax,
 that
 is
 fine.
 You


bring
 your
 payment
 and
 billing
 and
 then


our
 sales
 people
 start
 getting
 into
 it.


The
 sticker
 price,
 of
 course,
 is
 there


for
 everybody
 to
 see.


I'm
 not
 really
 sure
 on
 what
 is
 the


threshold
 that
 you
 know,
 start
 bringing


the
 price
 down
 because
 that's
 more
 on


the
 sales
 side,
 but
 do
 come
 over
 to
 our


uh
 booth.
 We've
 got
 some
 sales
 people


there.
 They'll
 be
 able
 to
 give
 you
 a


better
 answer
 to
 this.
 I've
 explained


you
 the
 mechanism,
 but
 the
 threshold


they'll
 be
 able
 to
 answer.


Yes,
 please.


Your
 thoughts
 on
 the
 presentation
 was


really
 interesting.
 Thank
 you.
 And
 one


thing
 I'm
 wondering,


how
 does
 for
 example
 the
 pricing
 model


of
 like
 big
 AI
 labs
 relate
 to
 this


iterative
 pricing?


I
 feel
 like


AI
 labs
 often
 have
 like
 multiple
 plans


which
 have
 like
 very
 constant
 pricing.


And
 then


like
 the
 roll
 out
 of
 features
 always


happen
 first
 on
 the
 expensive
 plans
 and


then
 they
 trickle
 down
 to
 like
 That
 is


true.
 the
 lower
 pricing.


And
 I
 don't
 really
 see
 like
 they
 don't


really
 use
 like
 iterative
 pricing
 in


their
 pricing.
 No,
 no,
 they
 they
 use
 it


under
 the
 hood.
 So,
 for
 them,
 for
 you,


like
 even
 if
 you
 go
 to
 11
 Labs,
 you'll


see
 four
 kind
 of
 plans
 there,
 right?
 Uh


let
 me
 call
 it
 good,
 better,
 best,
 and


then
 enterprise,
 right?
 You
 will
 just
 go


for
 you
 go
 for
 the
 best,
 right?
 They


will
 keep
 adding
 features
 or
 removing


features
 from
 one
 plan
 to
 the
 other.
 The


pricing
 will


They
 will
 try
 to
 remain
 constant
 with


the
 pricing
 for
 you,
 but
 inside
 it
 the


features
 will
 keep
 moving
 and
 that
 is


why
 they
 want
 to
 give
 it
 give
 you


credits
 or
 we
 advise
 that
 you
 give


credit
 to
 the
 customer
 so
 that
 the


all
 these
 features
 doesn't
 start


interacting
 with
 pricing.
 Okay,
 like
 the


customer
 facing
 prices
 stay
 stay


constant
 but
 linked
 to
 which
 plan?
 Yes,


they
 they
 let
 me
 say
 not
 the
 pricing
 the


customer
 facing
 plan
 remains
 constant,


right?
 Price
 might
 change
 again,
 but
 the


features
 will
 keep
 changing
 because
 it


has
 been
 abstracted
 by
 credits
 on
 the


top.
 Okay.
 Right,
 that's
 it.
 Yeah,
 you


had
 a
 question,
 sorry.
 Um


Yes,
 sir.


My
 question
 is
 does
 your
 platform


provide
 like
 a
 way
 to


record
 every
 transaction
 in
 your


system
 like


>> Every
 transaction.


Uh


that
 costs
 something
 and
 the
 user
 we
 can


track
 it.
 Yeah,
 so
 what
 what
 we
 do
 is


like


if
 the
 prompted
 like
 you
 make
 a
 prompt,


uh
 the
 customer
 is
 ingesting
 some
 uh


calls,
 you
 will
 send
 those
 calls
 to
 us.


You
 will
 tell
 us
 like
 we
 have
 all
 kind


of
 pricing
 in
 there.
 Tiered
 pricing,


dynamic
 pricing,
 uh
 dimension-based


pricing.
 You
 tell
 us
 what
 kind
 of


pricing
 does
 it
 go
 and
 then
 it
 it
 comes


in,
 we
 are
 able
 to
 rate
 it
 and
 price
 it


for
 you.
 And
 then
 you
 can
 get
 the
 whole


report
 on
 exactly
 why


why
 the
 invoice
 is
 what
 it
 is
 so
 we
 can


give
 you
 all
 the
 detailed
 pricing.


Right?


Thank
 you.


All
 right,
 if
 you
 have
 any
 other


question,
 then
 please
 feel
 free
 to
 come


to
 our
 booth,
 floor
 three,
 right?
 Thank


you
 so
 much.


>> [applause]


[music]

</details>