---
author: TechButMakeItReal
date: '2026-05-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=b9s2vLK34qo
speaker: TechButMakeItReal
tags:
  - space-data-centers
  - ai-infrastructure
  - launch-costs
  - radiation-hardening
  - ai-decentralization
title: 太空港AI数据中心的严峻成本与未来前景
summary: 本文探讨了将AI数据中心部署至太空的巨大经济挑战与技术障碍。从太空发射成本、硬件的辐射防护与寿命限制，到能源、散热和通信等工程难题，都表明当前在太空建立AI基础设施并非经济可行的商业模式。尽管如此，其在AI去中心化和赋能发展中国家方面的潜在优势，预示着一个长期且渐进的发展方向。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - SpaceX
  - Google
  - Meta
  - Nvidia
products_models:
  - H100
  - Blackwell
  - Llama 3
  - TPU
media_books: []
status: evergreen
---
### 太空港AI数据中心的昂贵现实与地面挑战

一个500克的Nutella罐头，在Aremis 2任务中被镜头捕捉到，将其送入月球轨道竟然花费了约75,926美元。这笔计算的来源值得称赞，它也引发了一个关键问题：当一颗Nutella罐头进入月球轨道的成本如此之高时，我们为何还要认真讨论将数据中心设入太空？特别是数据中心需要成千上万的芯片、复杂的电力系统、屏蔽层、散热器以及网络设备，这些都将在弄清楚如何在地球上可持续地运行数据中心之前，被发射到轨道。本系列《AI的商业》最新一集将深入探讨太空数据中心的经济学、它们为何被推向太空，以及这是否真是一项经济上可行的业务。

AI数据中心在地球上运行，需要巨量的水、电力和土地。目前，这三者都已成为关键的瓶颈。首先是水：一个大型数据中心每天约需30万加仑水用于冷却，这足以供约一千户家庭使用。谷歌等超大规模数据中心每天的用水量可达500万加仑，亚利桑那州凤凰城附近的数据中心每年仅用于冷却就消耗3.85亿加仑水，这还不包括发电所需的水。随着AI数据中心的增长，用于冷却的用水量预计将激增870%。

其次是电力：AI数据中心在电力供应方面也遇到了类似的硬性限制。美国北弗吉尼亚州的情况尤为突出，那里拥有近600个数据中心，处理着全球约70%的互联网流量。2024年的一次电压波动几乎引发了区域性停电，导致60个数据中心与电网断开连接。当地公用事业公司和监管机构警告称，若无大规模新建输电线路，该地区的居民电费将攀升至每月380美元，因为家庭将与数据中心竞争同一电力资源。

第三是土地：这一瓶颈是关于寻找更多物理空间来容纳所有硬件。要容纳数吨重的设备，需要大量的土地，每个站点都需要数英亩。大多数最适合数据中心的地区，即气候凉爽、地质稳定、靠近光纤线路和发电站的区域，都已经饱和。曾经通过税收优惠来吸引数据中心的各级政府，如今不得不放缓脚步，因为农田被铺设成道路，住房项目停滞，居民们反对家门口出现蔓延的工业区。在越来越多的管辖区，兼具电网、水权和社区认可的最便宜土地，已无法满足AI建设者所需的大规模需求。因此，人们开始寻找其他地方，而这个“其他地方”就是地球之外。他们向上看，看到了太空——是的，水也是一个问题，我们稍后会谈到——但今天我们主要讨论太空。

<details>
<summary>Original English</summary>

Remember
 the
 can
 of
 Nutella
 that
 flashed


on
 camera
 during
 the
 Aremis
 2
 mission?
 A


$5
 500
 g
 jar
 of
 chocolate
 spread?
 To
 get


that
 thing
 into
 lunar
 orbit
 cost
 roughly


$75,926.


Thank
 you
 very
 much
 the
 author
 of
 this


post
 for
 the
 calculation.
 And
 I
 agree


with
 this
 comment.
 I
 really
 hope
 it
 was


worth
 every
 penny
 for
 the
 crew.
 But
 if
 a


single
 jar
 of
 Nutella
 costs
 76
 grand


just
 to
 hitch
 a
 ride
 around
 the
 moon,


how
 did
 we
 get
 to
 the
 point
 when
 we're


seriously
 saying,
 "Yeah,
 let's
 put
 data


centers
 in
 space."
 data
 centers
 with


thousands
 of
 chips,
 power
 systems,


shielding,
 radiators,
 networking
 gear,


tons
 of
 metal,
 all
 launched
 into
 the


orbit
 before
 we
 figured
 out
 how
 to
 make


data
 centers
 work
 sustainably
 on
 Earth.


All
 you
 need
 to
 know
 about
 the
 economics


of
 space
 data
 centers,
 why
 we're
 getting


them
 into
 space
 in
 the
 first
 place,
 and


whether
 it's
 an
 economically
 viable


business
 to
 begin
 with
 in
 the
 new


episode
 of
 the
 series,
 The
 Business
 of


AI.
 Let's
 dive
 in.


Terrestrial
 AI
 data
 centers
 need
 three


things
 in
 gigantic
 quantities.
 Water,


electricity,
 and
 land.
 All
 three
 are
 now


critically
 constrained.
 Starting
 with


water.
 A
 typical
 large
 data
 center
 needs


about
 300,000
 gallons
 of
 water
 per
 day


for
 cooling.
 This
 amount
 of
 water,
 for


context,
 can
 suffice
 for
 about
 a


thousand
 households.
 The
 largest
 data


centers
 for
 hyperscalers
 at
 Google
 can


use
 up
 to
 5
 million
 gallons
 of
 water
 per


day.
 The
 ones
 around
 Phoenix,
 Arizona


use
 385
 million
 gallons
 per
 year
 for


cooling.
 And
 this
 is
 not
 counting
 the


water
 required
 to
 generate
 the


electricity.
 As
 AI
 data
 centers
 grow,


water
 used
 for
 cooling
 is
 projected
 to


skyrocket
 by
 870%.


The
 second
 thing
 is
 electricity.
 AI
 data


centers
 are
 hitting
 similar
 hard
 limits


on
 the
 power
 side.
 The
 case
 of
 Northern


Virginia
 is
 probably
 the
 most
 staggering


case
 of
 the
 system
 reaching
 its
 limit.


Northern
 Virginia
 hosts
 nearly
 600
 data


centers
 and
 handles
 approximately
 70%
 of


the
 world's
 internet
 traffic.
 A
 voltage


fluctuation
 in
 2024
 almost
 triggered
 a


regional
 blackout
 and
 caused
 60
 data


centers
 to
 disconnect
 from
 the
 power


grid.
 Local
 utilities
 and
 regulators


warned
 that
 without
 massive
 new


transmission
 lines,
 residential


electricity
 bills
 in
 the
 region
 can


climb
 toward
 $380
 per
 month
 because


households
 will
 be
 competing
 with
 data


centers
 for
 the
 same
 power.
 And
 number


three,
 land.
 This
 specific
 bottleneck
 is


simply
 about
 finding
 more
 physical
 space


to
 put
 all
 this
 hardware
 in.
 To
 house


tons
 of
 metal,
 you
 need
 a
 lot
 of
 real


estate,
 acres
 per
 site.
 Most
 regions


that
 are
 best
 suited
 for
 data
 centers


with
 cool
 climates
 and
 stable
 geology,


proximity
 to
 fiber
 routes
 and
 power


plants
 have
 already
 been
 used.
 and
 local


governments
 that
 once
 competed
 to


attract
 data
 centers
 with
 tax
 breaks,


for
 example,
 are
 hitting
 pause
 because


farmland
 is
 paved
 over,
 housing
 projects


are
 stopped
 and
 residents
 push
 back


against
 sprawling
 industrial
 jungles
 on


their
 doorstep.
 In
 more
 and
 more


jurisdictions,
 the
 cheapest
 land
 that


also
 has
 grid,
 water
 rights,
 and


community
 approval
 simply
 no
 longer


exists
 at
 the
 scale
 that
 AI
 builders


wanted
 to.
 And
 so
 people
 started
 looking


elsewhere
 and
 that
 elsewhere
 is
 off
 the


planet
 earth.
 They
 looked
 down
 and
 saw


the
 water
 which
 yes
 is
 a
 thing
 as
 well.


We're
 going
 to
 talk
 about
 it
 a
 little


bit
 later
 but
 today
 is
 about
 looking
 up


the
 space.
 Why
 put
 a
 data
 center
 in


space?
 Let's
 come
 back
 to
 the
 three


things
 that
 data
 centers
 need
 in


gigantic
 quantities.
 Water.
 Space
 is
 the


only
 place
 where
 water
 supply
 is
 not


part
 of
 the
 equation.
 In
 orbit,
 heat
 can


be
 rejected
 directly
 into
 the
 vacuum


through
 large
 radiator
 panels.
 This


doesn't
 make
 cooling
 easy
 because
 those


radiators
 must
 be
 huge
 and
 very


carefully
 engineered,
 but
 instead
 it


breaks
 the
 dependency
 on
 household
 or


farmers
 fighting
 for
 the
 same
 rivers
 and


water
 sources.
 electricity.
 Solar
 power


in
 orbit
 doesn't
 care
 about
 heat
 waves


or
 winter
 storms
 or
 regional
 power


grids.
 A
 satellite
 in
 orbit
 sees
 the
 sun


for
 roughly
 95%
 of
 the
 time,
 regardless


of
 clouds,
 day
 or
 night,
 or
 atmospheric


losses.
 What
 this
 means
 is
 that
 you
 get


far
 more
 usable
 energy
 out
 of
 solar


panels
 in
 space
 rather
 than
 on
 the


ground.
 And
 again,
 this
 also
 removes
 the


competition
 for
 power
 plants
 with


factories
 or
 homes
 or
 farms
 or
 electric


vehicles
 for
 a
 share
 of
 an
 already


strained
 grid
 and
 land.
 Yeah,
 it's
 kind


of
 obvious
 that
 land
 is
 unlimited.
 But


what's
 even
 more
 important
 is
 the


absence
 of
 politics
 around
 the
 land.
 On


Earth,
 every
 new
 data
 center
 is
 a


political
 fight
 over
 zoning,
 noise,


views,
 jobs,
 tax
 breaks.
 But
 in
 space,


you
 don't
 need
 acres
 of
 flat
 and
 cool


fiber
 cooling
 and
 power
 adjacent
 land.


So
 let's
 see
 what
 it
 takes
 to
 build
 an


orbital
 data
 center
 step
 by
 step.
</details>

### 关键组件与太空挑战：辐射、磨损与极端环境

要建造一个飞行的、自带电力生成、计算集群、冷却系统和通信网络的“飞行数据中心”，核心是构建一个**卫星**。与地球上的数据中心一样，卫星内部也将存储AI芯片集群。然而，将当前生产的地面芯片送入太空会遇到几个严重问题。

首要问题是**宇宙辐射**引起的**比特翻转**。地球的大气层和磁场能阻挡绝大多数高能宇宙射线和太阳粒子，但高于500公里（SpaceX卫星的最低轨道高度）的太空则没有这种保护。高能粒子会直接撞击芯片电路。当带电粒子击中存储单元时，可能将一个比特从0翻转为1，或从1翻转为0。例如，一块存储数字22（二进制为10110）的芯片，若被宇宙射线击中并翻转了一个比特，该数字可能变为150（二进制为10010110），这就是比特翻转。这种硬件层级的微小错误会不受控制地在整个神经网络中传播，且不会触发任何可见的错误标记。Meta曾尝试在地球上训练Llama 3，期间在54天内经历了419次意外中断，平均每隔几分钟就发生一次故障，而这还是在受完全保护的地面环境中。在轨道上，系统将面临所有这些故障以及辐射诱导的比特翻转。

虽然存在**抗辐射芯片**（通常用于军事卫星、核电站、太空探测器），但它们通常体积更大、技术更老旧。它们天生对辐射有更强的抵抗力，因为晶体管物理尺寸更大，粒子更难击中。然而，这些芯片比当前领先的AI芯片落后数代。最新的先进抗辐射芯片通常包含5亿到20亿个晶体管，而英伟达旗舰H100芯片包含800亿个晶体管，Blackwell芯片则有2000亿个。

解决此问题的方案可能包括**三模冗余（TMR）**，即运行至少三个并行计算管道并比较输出以捕获错误；**辐射容忍封装**；以及各层级的**纠错内存**和为高辐射环境设计的**新型固件**。但三模冗余意味着需要发射三倍数量的芯片，三倍的冷却成本，以及三倍的发射费用，这使得经济模型难以成立。谷歌曾测试其Trillium TBU芯片，地面测试表明其可靠的轨道运行寿命仅为五年。但地面辐射仅暴露芯片于一种粒子类型，而太空则持续受到能量范围更广的宇宙射线的轰击。

第二个大问题是**芯片磨损且无法更换**。在地球上，数据中心通常每两到三年就会更换一次GPU，因为它们会因使用而退化或被更新一代的产品取代。在轨道上，你无法更换芯片，不可能搭乘火箭飞上去然后取出它们。芯片是一次性的旅行，它们在那里运行约5年后，随着太阳能电池板和芯片开始退化，最终会烧毁。卫星无法返回地球。相比之下，地面数据中心的老旧芯片可以获得第二次甚至第三次生命，可以分配给更轻的负载，或出售给小型云服务提供商，二手芯片市场相当活跃。但在太空，回收和翻新这些芯片需要一整类新的载具，如太空拖船或载货返回舱，而这些目前都未大规模部署。

移动到第二个组件——**电力**。地球上的太阳能发电厂的光照会受到大气层过滤，并且只在太阳升起且无云时工作。在太空中，阳光照射时间约占95%，而地球上的太阳能电池板约30%。这听起来不错，但风险在于，在太空产生电力需要非常庞大的太阳能电池板系统来供给庞大的芯片集群。我们谈论的是相当于一个足球场大小的太阳能结构，需要折叠进火箭，然后能自主展开成170米宽的翼展。这些结构还必须能承受数千次零下120摄氏度到零上120摄氏度的温度波动。

第三个组件是**冷却**。地球上的数据中心通过将热量排入空气或水来保持芯片凉爽。在太空中，既没有空气也没有水，所以这种方式行不通。唯一的选择是让硬件通过**红外光**将热量辐射到空旷的太空，使用大型散热板。问题在于尺寸：要散发数据中心的全部热量，这些散热板必须巨大，并且能在没有维护或有人修复的情况下工作数年。随着计算能力的增加，这些散热板必须越来越大。

第四个组件是**网络**。一个卫星集群要作为一个分布式数据中心运行，就需要相互通信，并将结果传回地球。卫星间的通信问题通过**激光链路**解决，即通过发射激光束在卫星间传输数据。然而，为了让这些激光能够承载足够用于AI计算的带宽，卫星必须保持数百米到几公里的编队飞行，以留在彼此的可见范围内。这意味着每颗卫星都必须精确保持相对于邻居的位置，或能够自主纠正其位置以维持连接。

<details>
<summary>Original English</summary>

You're
 going
 to
 need
 four
 primary


components.
 Component
 number
 one,
 the


satellite.
 To
 build
 a
 flying
 data
 center


with
 its
 own
 power
 generation,
 computing


cluster,
 cooling
 system,
 and


communications
 network,
 you
 need
 a


physical
 piece
 of
 equipment
 that
 would


house
 all
 of
 it,
 a
 satellite.
 In
 each


satellite,
 just
 like
 in
 a
 terrestrial


data
 center,
 we're
 going
 to
 store


clusters
 of
 AI
 chips.
 However,
 there's
 a


problem.
 If
 we
 send
 the
 chips
 that
 are


currently
 being
 produced
 for
 terrestrial


data
 centers,
 we
 will
 inevitably
 run


into
 several
 problems.
 Problem
 number


one,
 cosmic
 radiation
 causes
 bit
 flips.


On
 Earth,
 the
 atmosphere
 and
 magnetic


field
 block
 the
 vast
 majority
 of
 high


energy
 cosmic
 rays
 and
 solar
 particles


in
 orbit
 above
 500
 km,
 which
 is
 the


minimum
 altitude
 for
 Space
 X
 satellites.


As
 an
 example,
 there
 is
 no
 such


shielding.
 High
 energy
 particles
 fly


straight
 into
 the
 chip
 circuiting.
 When


a
 charged
 particle
 hits
 the
 memory
 cell,


it
 can
 flip
 a
 bit
 from
 0ero
 to
 one
 or


one
 to
 zero.
 Here
 is
 an
 example.
 Imagine


a
 chip
 storing
 the
 number
 22
 in
 binary.


Then
 a
 cosmic
 ray
 hits
 the
 chip
 and


flips
 a
 single
 bit
 from
 0
 to
 1.
 And


suddenly
 the
 number
 isn't
 22
 anymore.


It's
 150.
 This
 is
 the
 bit
 flip.
 One
 tiny


change
 at
 the
 hardware
 level
 can
 cause


completely
 different
 data.
 And
 this


error
 is
 going
 to
 propagate
 through
 the


entire
 neural
 network
 without
 triggering


any
 visible
 flag.
 For
 example,
 Meta's


training
 of
 Lama
 3
 on
 Nvidia
 H100's


experienced
 419
 unexpected
 interruptions


in
 54
 days
 on
 Earth.
 And
 these
 failures


were
 happening
 every
 few
 minutes
 in
 a


fully
 protected
 terrestrial
 environment.


In
 orbit,
 this
 system
 would
 face
 all


those
 failures
 plus
 radiation
 induced


bit
 flips.
 So,
 you
 may
 ask,
 why
 don't
 we


just
 use
 radiation
 hardened
 chips?


Radiation
 hardened
 chips
 do
 exist,
 and


they're
 typically
 used
 in
 military


satellites,
 nuclear
 power
 plants,
 space


probes,
 but
 they're
 typically
 much


larger
 and
 a
 lot
 older.
 They're
 more


resistant
 to
 radiation
 by
 nature
 because


the
 transistors
 are
 physically
 bigger


and
 harder
 for
 a
 particle
 to
 hit,
 but


instead,
 they
 lag
 generations
 behind


leading
 AI
 chips
 in
 compute
 power.
 The


latest,
 the
 most
 advanced
 Radhar
 chips


contain
 between
 500
 million
 and
 two


billion
 transistors.
 In
 contrast,


Nvidia's
 flagship
 H100's
 contain
 80


billion
 transistors
 and
 Blackwell
 chips


around
 200
 billion.
 The
 solution
 to
 this


would
 be
 a
 combination
 of
 triple
 modular


redundancy,
 running
 at
 least
 three


parallel
 computation
 pipelines
 and


comparing
 outputs
 to
 catch
 errors,


radiation
 tolerant
 wrappers
 around
 the


chip,
 error
 correcting
 memory
 at
 every


level,
 and
 new
 firmware
 designed


specifically
 for
 high
 radiation


environments.
 Triple
 redundancy
 means


launching
 three
 times
 as
 many
 chips,


three
 times
 the
 cooling,
 and
 three
 times


the
 launch
 cost.
 Meaning
 the
 economics


of
 this
 simply
 will
 not
 work.
 Google
 in


fact
 tested
 their
 trillium
 TBU
 chips
 on


the
 ground
 and
 projected
 only
 five
 years


of
 reliable
 orbital
 operation.
 But
 the


problem
 is
 that
 the
 ground
 radiation


exposes
 chips
 to
 only
 one
 particle
 type


while
 space
 has
 continuous
 hail
 of


cosmic
 rays
 at
 a
 far
 wider
 range
 of


energies.
 The
 second
 big
 problem
 is
 that


chips
 wear
 out
 and
 cannot
 be
 replaced.


On
 Earth,
 data
 centers
 swap
 out
 GPUs


every
 two
 to
 three
 years
 as
 those
 chips


degrade
 from
 use
 or
 as
 newer
 generations


arrive.
 In
 orbit,
 you
 can't
 swap
 out
 the


chips.
 You're
 not
 going
 to
 hop
 on
 a


rocket
 and
 magically
 fly
 up
 to
 the


satellite
 and
 take
 them
 out.
 Chips
 do


not
 get
 brought
 back.
 It's
 a
 one-way


trip.
 They
 run
 there
 for
 about
 5
 years


until
 solar
 panels
 and
 chips
 start
 to


degrade
 and
 then
 burn
 up.
 There's
 no


retrieval
 of
 satellites
 back
 to
 Earth.


In
 contrast,
 for
 terrestrial
 data


centers,
 old
 chips
 get
 a
 second
 and


sometimes
 third
 life.
 They
 can
 be


cascaded
 to
 lighter
 loads.
 They
 can
 be


sold
 to
 smaller
 cloud
 providers.
 The


secondhand
 market
 for
 chips
 is
 actually


quite
 big.
 But
 in
 space,
 recovering
 and


refurbishing
 those
 chips
 would
 require
 a


whole
 additional
 class
 of
 vehicles
 like


space
 tugs
 or
 cargo
 return
 capsules,


which
 nobody
 has
 at
 scale
 yet.
 Moving
 on


to
 the
 second
 component,
 power.
 A
 solar


plant
 on
 Earth
 receives
 sunlight


filtered
 through
 the
 atmosphere.
 Only


when
 the
 sun
 is
 up
 and
 only
 when
 there


are
 no
 clouds.
 In
 space,
 the
 exposure
 to


the
 sun
 is
 approximately
 95%
 compared
 to


roughly
 30%
 for
 a
 solar
 panel
 on
 Earth.


And
 it
 all
 sounds
 fine
 and
 dandy,
 but


the
 risk
 here
 is
 that
 generating
 power


in
 space
 requires
 very
 large
 systems
 of


solar
 panels
 to
 feed
 a
 sizable
 chip


cluster.
 We're
 talking
 solar
 structures


on
 the
 order
 of
 a
 football
 field
 folded


inside
 a
 rocket
 and
 then
 somehow


autonomously
 unfolding
 into
 170
 m
 wide


wing.
 These
 structures
 should
 also
 be


able
 to
 survive
 thousands
 of
 cycles


between
 minus
 120
 and
 plus
 120°
 Celsius


temperature
 fluctuation.
 Component


number
 three,
 cooling.
 On
 Earth,
 data


centers
 keep
 chips
 cool
 by
 pushing
 heat


into
 air
 or
 water.
 In
 space,
 there
 is


neither
 air
 nor
 water.
 So,
 that
 trick


doesn't
 work.
 The
 only
 option
 is
 to
 let


the
 hardware
 dump
 heat
 as
 in
 frared


light
 into
 empty
 space
 using
 big


radiator
 panels.
 The
 problem
 is
 the


size.
 To
 get
 rid
 of
 heat
 from
 a
 data


center,
 those
 panels
 have
 to
 be
 massive


and
 work
 for
 several
 years
 with
 no


maintenance
 or
 somebody
 being
 there
 to


fix
 them.
 As
 you
 add
 more
 compute,
 those


panels
 have
 to
 get
 larger
 and
 larger.


And
 component
 number
 four,
 networking.


For
 a
 cluster
 of
 satellites
 to
 function


as
 a
 distributed
 data
 center,
 they
 need


to
 talk
 to
 each
 other
 and
 they
 need
 to


send
 results
 back
 down
 to
 Earth.
 This


satellite
 to
 satellite
 problem
 is
 solved


with
 laser
 links
 that
 are
 quite


literally
 shooting
 laser
 beams
 between


the
 satellites.
 However,
 for
 those


lasers
 to
 carry
 enough
 bandwidth
 for
 AI


computation,
 the
 satellites
 must
 fly
 in


formation
 from
 hundreds
 of
 meters
 to
 a


few
 kilometers
 apart
 to
 stay
 in
 each


other's
 area
 of
 visibility.
 That
 means


that
 every
 satellite
 must
 hold
 its
 exact


position
 relative
 to
 its
 neighbors
 or
 be


able
 to
 correct
 its
 position


autonomously
 to
 maintain
 connectivity.
</details>

### 太空数据中心的经济学：成本、发射与商业可行性

将数据中心部署到太空的成败，完全取决于将每公斤硬件送入低地球轨道的成本。发射成本决定了将轨道数据中心与地面替代方案竞争的可能性。无论如何解决辐射、冷却和电力问题，最终都需要将大量物质运往卫星：包括芯片、屏蔽层、散热器和结构件。负载越重，火箭消耗的燃料越多，飞行成本也越高。将设备送入太空，需要为你放入轨道的每一公斤付费，无论这一公斤是金质芯片还是钢制螺栓。

要将芯片送入轨道，需要三个要素：**火箭**、**卫星**和**有效载荷**。有效载荷即实际货物，如芯片、散热器、冷却器等，它们将安装在卫星上。火箭本质上是一辆送货卡车，它燃烧燃料来加速所载物品达到轨道速度。火箭通常有多级，每级在耗尽燃料后会被抛弃，只有顶级的火箭级加上有效载荷才能抵达轨道。卫星则是在火箭完成任务后，将留在轨道上的设备。卫星承载着结构、推进、电力、冷却、通信和计算硬件。当我们说“将H100芯片送入太空”时，字面意思是将H100的电路板安装在卫星内部，并将该卫星装载到火箭上。火箭由火箭公司提供，如SpaceX、Blue Origin，以及主要为美国军方和政府提供服务的United Launch Alliance。它们按公斤向你出售进入轨道的服务。

为了使太空数据中心的经济效益得以实现，每公斤的成本必须降至约200美元。为何是200美元？因为这个数字大致是地面成本和计算成本相抵消的临界点，届时其成本模型将类似于一个良好的地面数据中心。截至今日，SpaceX是唯一一家公开朝着每公斤200美元目标迈进的公司，并拥有相对可靠的实现计划。但即便如此，这仍是一个未来的预测。以目前的发射价格计算，太空能源的成本是地面的5到20倍，而每公斤的成本约为3000美元，这是最便宜的常用火箭的价格。

谁提供卫星？StarCloud、Axiom、ADA Space等公司。它们决定了芯片将安装在何种物理结构中，设计卫星的底盘、面板、散热器、推进器，并建造实际的卫星。那么，一颗兼容AI硬件的卫星成本是多少？目前没有公开的数字，但StarCloud在21个月内完成了StarCloud 1的设计、制造和发射，其融资额为300万美元的种子轮，这笔资金足以覆盖工程和制造成本。所以，建造类似卫星的成本大概在200万美元左右，还要加上GPU的成本。

谈到芯片，半导体制造商越来越有兴趣生产抗辐射芯片，因为这是一个庞大且不断增长的市场。谷歌的Suncatcher项目试图涉足有效载荷领域，他们设计了自家的抗辐射TPU芯片和太空计算概念，并与实际将硬件送入太空的发射服务提供商合作。这基本上就是太空数据中心成本的构成。

那么，我们是否即将看到AI基础设施进入太空？是的。起初，它将用于AI推理，并在未来10年内，很可能也会出现AI训练。但就目前而言，它并非一项有充分理由支持的业务，你看到这些数字，数学上无法成立。因此，这个行业不会一夜之间爆发，但我们正朝着这个方向稳步前进。

<details>
<summary>Original English</summary>

Everything
 about
 data


centers
 in
 space
 lives
 or
 dies
 on
 how


cheap
 it
 is
 to
 put
 each
 kilogram
 of


hardware
 into
 low
 Earth
 orbit.
 It's
 the


cost
 of
 the
 launch
 that
 determines


whether
 the
 effort
 to
 launch
 orbital


data
 centers
 can
 compete
 with


terrestrial
 alternatives.
 Whatever
 you


do
 to
 solve
 the
 radiation
 and
 cooling


and
 power,
 you
 still
 end
 up
 with
 a
 ton


of
 stuff
 that
 needs
 to
 be
 carried
 to
 the


satellite.
 Chips,
 shielding,
 radiators,


structures,
 propellants.
 The
 heavier
 the


load,
 the
 more
 fuel
 the
 rocket
 burns,


the
 more
 expensive
 the
 flight.
 To
 get
 it


into
 space,
 you
 have
 to
 pay
 for
 every


kilogram
 that
 you
 put
 into
 the
 orbit,


regardless
 of
 whether
 that
 kilogram
 is
 a


gold
 chip
 or
 a
 steel
 bolt.
 To
 deliver


the
 chips
 to
 the
 orbit,
 you
 need
 three


things:
 a
 rocket,
 a
 satellite,
 and


payload.
 Payload
 is
 the
 actual
 cargo,


the
 chips,
 the
 radiators,
 the
 coolers


that
 go
 on
 the
 satellite.
 The
 rocket
 is


basically
 a
 delivery
 truck.
 It
 burns


fuel
 to
 accelerate
 whatever
 it
 is


carrying
 to
 up
 to
 the
 orbital
 speed.
 The


rocket
 has
 multiple
 stages
 and
 each


stage
 fires,
 runs
 out
 of
 fuel
 and
 gets


dropped.
 Only
 the
 top
 stage
 plus
 the


payload
 make
 it
 to
 the
 orbit.
 The


satellite
 is
 what
 will
 stay
 in
 orbit


once
 the
 rocket
 is
 done.
 The
 satellite


carries
 the
 structures,
 propulsion,


power,
 cooling,
 communications,
 and


compute
 hardware.
 By
 compute
 hardware,


we're
 talking
 racks
 of
 GPUs
 or
 TPUs
 or


any
 other
 kind
 of
 chip.
 When
 someone


says
 put
 H100s
 in
 space,
 they
 literally


mean
 bolting
 H100
 boards
 inside
 a


satellite
 and
 putting
 that
 satellite
 on


a
 rocket.
 So
 the
 rocket
 carries
 the


satellite,
 the
 satellite
 carries
 the


chips,
 the
 chips
 sit
 on
 boards
 inside


the
 satellite.
 Now
 who
 supplies
 the


rocket?
 The
 rocket
 company.
 SpaceX,
 Blue


Origin,
 United
 Launch
 Alliance
 mainly


for
 US
 military
 and
 government
 or
 area


and
 space
 in
 Europe.
 They
 sell
 you


kilograms
 to
 orbit.
 Now,
 for
 the


economics
 of
 this
 to
 work
 in
 favor
 of


data
 centers,
 the
 cost
 per
 kilogram
 has


to
 go
 down
 to
 about
 $200.


Why
 $200?
 Because
 this
 number
 is
 roughly


the
 point
 where
 the
 cost
 of
 lodge
 stops


overpowering
 the
 cost
 of
 compute.
 And


the
 math
 starts
 to
 look
 similar
 to
 a


good
 terrestrial
 data
 center.
 As
 of


today,
 SpaceX
 is
 the
 only
 one
 openly


targeting
 $200
 per
 kilogram
 goal
 with


more
 or
 less
 promising
 plan
 on
 how


they're
 going
 to
 get
 to
 that
 number.
 But


again,
 it's
 a
 future
 projection.
 At


today's
 launch
 prices,
 space
 power
 costs


five
 to
 20
 times
 more
 than
 the
 ground.


And
 the
 cost
 per
 kilogram
 sits
 around


$3,000
 for
 the
 cheapest
 widely
 used


rocket.
 Who
 supplies
 the
 satellites?


StarCloud,
 Axiom,
 ADA
 Space.
 These
 guys


decide
 what
 the
 chips
 are
 going
 to


physically
 sit
 in.
 They
 design
 the


chassis,
 panels,
 radiators,
 thrusters,


and
 build
 the
 actual
 satellite
 with


those
 things.
 So,
 how
 much
 does
 a


satellite
 that
 would
 be
 compatible
 with


AI
 hardware
 cost?
 There's
 no
 publicly


disclosed
 number,
 but
 StarCloud
 raised


$3
 million
 precede
 and
 with
 that,
 they


designed,
 built,
 and
 launched
 StarCloud


1
 in
 21
 months.
 And
 the
 $3
 million


figure
 well
 covered
 the
 engineering
 and


manufacturing
 costs.
 So,
 speaking
 of
 how


much
 it
 costs
 to
 build
 a
 satellite
 like


that,
 we're
 talking
 in
 the
 ballpark
 of


$2
 million
 for
 a
 StarCloud
 class


satellite.
 But
 on
 top
 of
 that,
 add
 the


GPU
 costs.
 Speaking
 of
 chips,
 it
 is


increasingly
 becoming
 in
 the
 interest
 of


semiconductor
 manufacturers
 to
 start


producing
 radiation
 hardened
 chips


because
 it's
 a
 massive
 growing
 market.


Project
 Suncatcher
 is
 Google's
 attempt


to
 step
 into
 payload
 territory.
 They


design
 the
 rad
 hardened
 chips,
 their
 own


TPUs,
 and
 the
 space
 compute
 concept.
 And


then
 they
 partner
 with
 launch
 providers


that
 actually
 put
 that
 hardware
 into


space.
 And
 this
 is
 what
 the
 cost
 of
 a


space
 data
 center
 more
 or
 less
 comes


down
 to.
 So
 to
 sum
 it
 up,
 are
 we
 about


to
 see
 AI
 infra
 getting
 into
 space?
 Yes.


At
 first,
 it's
 going
 to
 be
 for
 AI


inference
 and
 then
 probably
 within
 the


next
 10
 years,
 we
 will
 most
 likely
 see


AI
 training
 as
 well.
 But
 as
 it
 stands,


it
 is
 not
 a
 justifiable
 business.
 You


can
 see
 the
 numbers.
 The
 math
 ain't


mathing.
 So
 the
 industry
 is
 not
 going
 to


blow
 up
 overnight.
 But
 it
 is
 something


that
 we're
 actively
 marching
 towards.
</details>

### 太空AI的去中心化潜力与未来展望

另一个将AI计算推向太空的重要原因，在于它有助于实现AI的**去中心化**。将数据中心置于太空，理论上能够让那些无力运行AI工作负载的国家，有机会构建自己的AI技术市场。在“全球北方”（Global North）地区，AI基础设施危机表现为长达7年的电网可用性限制。而在“全球南方”（Global South），问题则在于不稳定的电力供应、完全缺电，或是电力成本过高，以至于无法支撑计算密集型工作负载。

由此导致了所谓的“**计算荒漠**”（compute deserts）——即一些国家完全没有公共云AI硬件。与之相对的是“计算北方”，包括美国、中国和欧盟，这些地区拥有GPU数据中心；以及“计算南方”，即大部分发展中地区，在这里用户可以使用AI，但无法进行训练，并且需要以当地工资水平支付美国的云服务提供商的美元价格。

太空AI计算有望改变这一现状，但同样，这目前仍处于理论阶段。一个没有可靠电网但头顶有阳光的国家，理论上可以从轨道数据中心访问AI推理服务，并将结果传输回地面，从而绕过整个陆基基础设施的限制。

最终，我们将看到AI基础设施如何发展。正如我们一直希望的那样，这番解析对您有所帮助。下期《AI的商业》再见！

<details>
<summary>Original English</summary>

Another
 big
 reason
 why
 getting
 into


space
 would
 be
 a
 huge
 step
 towards


decentralization
 of
 AI
 is
 because


putting
 data
 centers
 in
 space
 would
 in


theory
 give
 countries
 that
 are
 unable
 to


run
 AI
 workloads
 an
 opportunity
 to
 build


their
 own
 AI
 tech
 market.
 AI


infrastructure
 crisis
 in
 the
 global


north
 is
 defined
 by
 7
 years
 of
 grid


cues.
 In
 the
 global
 south,
 the
 problem


is
 either
 unreliable
 power
 or
 no
 power


at
 all
 or
 power
 too
 expensive
 to
 run


compute
 heavy
 workloads.
 As
 a
 result,


we're
 dealing
 with
 what
 researchers
 call


compute
 deserts,
 countries
 where
 there


is
 no
 public
 cloud
 AI
 hardware
 at
 all,


compared
 with
 compute
 north,
 the
 US,


China,
 and
 the
 EU,
 where
 GPU
 data


centers
 live,
 and
 compute
 south,
 which


is
 most
 of
 the
 developing
 world,
 where


you
 can
 use
 but
 not
 train
 AI,
 and
 where


you
 pay
 US
 cloud
 providers
 the
 dollar


prices
 on
 local
 wages.
 Space-based
 AI


compute
 would
 change
 the
 situation,
 but


again,
 it
 would
 do
 so
 in
 theory.
 A


country
 with
 no
 functional
 grid,
 but
 sun


overhead
 could
 theoretically
 access
 AI


inference
 from
 an
 orbital
 data
 center,


beam
 results
 down,
 and
 bypass
 the
 entire


landbased
 infrastructure.
 So,
 let's
 see


where
 this
 goes.
 As
 always,
 we
 hope
 this


was
 helpful.
 We'll
 see
 you
 in
 the
 next


episode
 of
 the
 business
 of
 AI.
 Bye.
</details>