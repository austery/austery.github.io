---
author: Veritasium
date: '2026-07-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tL9Lw250spc
speaker: Veritasium
tags:
  - scaling-law
  - metabolic-rate
  - fractal-geometry
  - allometry
title: 生物代谢率与质量的缩放律：从克莱伯定律到WBE分形理论的争论
summary: 文章探讨了生物代谢率如何随体型质量缩放。研究者从大象药物实验与心跳规律出发，介绍了基于表面积的三分之二比例、克莱伯定律的四分之三比例以及解释该现象的WBE分形网络理论。目前科学界就代谢缩放指数是否存在统一定律仍存分歧。
insight: ''
draft: true
series: ''
category: science
area: knowledge-meta
project: []
people:
  - Geoffrey West
  - Max Kleiber
companies_orgs:
  - Brilliant
products_models: []
media_books:
  - Scale
status: evergreen
---
<!-- chunk 1/4 -->

你知道，从生物学角度来说，我说——应该给大象吃多少LSD？

<details><summary>Original English</summary>
ou know, biologically, I said- How much LSD should

you give an elephant?
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

嗯，对于一个通情达理的人来说，正确的答案大概是一点都不给。

<details><summary>Original English</summary>
Well, to a reasonable person,

the correct answer is probably none.
</details>

但如果是为了科学实验必须这么做呢？

<details><summary>Original English</summary>
But what if you needed to do

it for a scientific experiment?
</details>

20世纪60年代，中央情报局正在进行一项名为“MKUltra”的绝密项目，其主要目标之一是查明如何利用像LSD这样的药物来改变人类行为。

<details><summary>Original English</summary>
In the 1960s, the CIA was working on

a top secret project known as MKUltra,

and one of their main

goals was to find out

how drugs like LSD could be

used to change human behavior.
</details>

大象就是在这个环节登场的，因为大象平时通常非常温顺，但有时它们会突然发狂。

<details><summary>Original English</summary>
And this is where elephants come in

because elephants are

normally quite docile,

but sometimes they just snap.
</details>

当时的一个假说是，这种行为变化可能是由它们大脑中天然产生的一种类似LSD的物质释放所引发的。

<details><summary>Original English</summary>
And the hypothesis was

that this change in

behavior might be triggered

by the release of an LSD-like substance

that naturally occurs in their brains.
</details>

所以，如果这是真的，那么给温顺的大象服用LSD或许就能重现这种行为。

<details><summary>Original English</summary>
So if that's true, then administering LSD

to a docile elephant might

reproduce that behavior.
</details>

因此，真正的问题是，你应该给大象服用多少LSD，才能使剂量既大到足以引起心理反应，又不至于大到造成伤害？

<details><summary>Original English</summary>
So the real question was

how much LSD should you give

an elephant so that the

dose is large enough

to cause a psychological reaction,

but not so large that it causes harm?
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

研究人员当时并不清楚，以前从未给这么大的动物用过LSD，但他们确实知道猫的安全剂量大约是0.3毫克。

<details><summary>Original English</summary>
Well, the researchers didn't

know, LSD had never been given

to an animal that big,

but they did know that

the safe dose in cats

was around 0.3 milligrams.
</details>

由于大象的质量大约是猫的一千倍，他们琢磨着：那就给它一千倍的剂量。

<details><summary>Original English</summary>
Now, since an elephant has around

a thousand times the mass of a cat,

they figured we'll give it

a thousand times the dose.
</details>

他们获准在塔斯科（Tusko）身上进行这项实验，它是俄克拉荷马州林肯公园动物园的一头亚洲象。

<details><summary>Original English</summary>
They received approval to

perform the experiment on Tusko,

an Indian elephant at the

Lincoln Park Zoo in Oklahoma.
</details>

在动物园里，他们给它注射了近300毫克的LSD。

<details><summary>Original English</summary>
And there they injected him

with nearly 300 milligrams of LSD.
</details>

然而不到五分钟，塔斯科便大声嘶鸣、瘫倒、重重地倒在右侧，出现排便，并陷入癫痫持续状态。

<details><summary>Original English</summary>
But within five minutes,

Tusko trumpeted, collapsed,

fell heavily onto his

right side, defecated,

and went into status epilepticus.
</details>

他们尝试注射了几种其他药物来抢救它，但塔斯科不久后便死去了。

<details><summary>Original English</summary>
They administered a few other drugs

in an attempt to revive him,

but Tusko died shortly thereafter.
</details>

他们犯的错误是假定安全药物剂量与质量呈线性比例缩放。

<details><summary>Original English</summary>
The mistake they made was to assume

that safe drug dosage

scales linearly with mass.
</details>

事实并非如此。

<details><summary>Original English</summary>
It does not.
</details>

而且事实证明，很多像这样的事物并不会按照你预期的方式进行缩放。

<details><summary>Original English</summary>
And it turns out there are

a lot of things like this

that don't scale in the way you'd expect.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

### 心跳与生命周期的缩放律

例如，以按质量计最小的哺乳动物伊特鲁里亚鼩鼱，和最大的陆生哺乳动物非洲草原象为例。

<details><summary>Original English</summary>
For example, take the

smallest mammal by mass,

the Etruscan shrew,

and the largest land mammal,

the African bush elephant.
</details>

你认为哪一个在整个一生中的心跳次数更多？

<details><summary>Original English</summary>
Which do you think has more heartbeats

over the course of its entire life?
</details>

其实，一头非洲象一生的心跳次数大约在10亿次左右，而一只伊特鲁里亚鼩鼱一生的心跳次数也是10亿次。

<details><summary>Original English</summary>
Well, an African elephant has

around a billion

heartbeats in its lifetime,

and an Etruscan shrew also has a billion

heartbeats in its lifetime.
</details>

那沙袋鼠呢？也是10亿次。

<details><summary>Original English</summary>
What about a wallaby?

Also a billion.
</details>

二趾树懒？又是10亿次。

<details><summary>Original English</summary>
A two-toed sloth?

A billion again.
</details>

几乎每一种哺乳动物，无论它们生活在什么环境中、体型有多大，甚至无论它们是活1年还是活100年，从出生到死亡的那天，它们的心跳总数大约都在10亿次左右。

<details><summary>Original English</summary>
Just about every mammal, no matter

what environment they live

in, how large they are,

or even whether they live

for one year or 100 years,

they all get around a billion heartbeats

between the day they're

born and the day they die.
</details>

- 为什么是10亿次？为什么不是100万次？为什么不是1000次？偏偏不是其他这些数字。

<details><summary>Original English</summary>
- Why a billion?

Why not a million?

Why not a thousand?

It's not these other numbers.
</details>

- 除了一种哺乳动物之外，所有哺乳动物都是如此。

<details><summary>Original English</summary>
- That is every mammal except one.
</details>

本视频在很大程度上基于杰弗里·韦斯特（Geoffrey West）所著的《规模》（Scale）一书。如果你想了解更多，我会在下方的简介里放一个链接。

<details><summary>Original English</summary>
This video is in large

part based on the book

Scale by Geoffrey West.

If you want to learn more,

I'll put a link to it

down in the description.
</details>

更令人好奇的是，仅仅通过知道一种哺乳动物的质量，你就能预测出数量惊人的生物特征，从它的脉搏率和繁殖产出，一直到它的总寿命。

<details><summary>Original English</summary>
What's even more curious is that

just by knowing a mammal's mass,

you can predict a staggering number

of biological traits from its pulse rate

and reproductive output

to its total lifespan.
</details>

同样的规律也适用于城市。如果你知道人口和地理位置，就能让你预测从平均工资、专利申请量，到犯罪率、疾病患病率，甚至行人行走的字面速度等方方面面。

<details><summary>Original English</summary>
The same pattern holds for cities.

If you know the population and location,

that allows you to forecast

everything from average wages

and patent filings to crime

rates, disease prevalence,

and even the literal speed

at which pedestrians walk.
</details>

那么这怎么可能呢？嗯，为此我们必须回到大象塔斯科的案例上。

<details><summary>Original English</summary>
So how is that possible?

Well, for that, we have

to go back to the case

of Tusko the Elephant.
</details>

研究人员假定安全药物剂量与质量成正比。质量翻倍，剂量翻倍。

<details><summary>Original English</summary>
Researchers assumed that safe drug dosage

is proportional to mass.

Double the mass, double the dose.
</details>

但事实表明，动物处理化合物的速度并不直接取决于它的质量，它更多取决于它的代谢率，也就是它在给定时间内消耗的卡路里数。

<details><summary>Original English</summary>
But it turns out that the

speed at which an animal

can process chemical compounds

doesn't depend directly on its mass.

It depends more on its metabolic rate.

That is the number of calories it uses

in a given amount of time.
</details>

- 你的身体里时刻在发生着很多事情。你的心脏在跳动，这需要能量；你在体内运送食物，消化需要能量；维持大脑运转需要能量，呼吸也是。你所做的一切都需要能量。

<details><summary>Original English</summary>
- There's a lot going on in your body.

Your heart is pumping, that takes energy.

You're moving food around.

Digestion takes energy.

Keeping your brain going

takes energy, breathing.

Everything that you do requires energy.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

### 代谢与散热：表面积定律

- [主持人] 就猫而言，单单一整天，它们就需要大约250千卡的热量，由它们数万亿个细胞共同消耗。

<details><summary>Original English</summary>
- [Host] For a cat, for a single day,

they require roughly 250

kilocalories of energy,

used by all of their trillions of cells.
</details>

但是猫的细胞并没有什么特殊之处。如果你取一些猫的细胞和大象的细胞放在显微镜下，你会发现它们大小相似，组成相似，并且执行着相同类型的功能。

<details><summary>Original English</summary>
But there is nothing

special about a cat's cells.

If you take a cat's cells

and an elephant's cells

and put them under a microscope,

you'll find they're a

similar size, similar makeup,

and they perform the

same sorts of functions.
</details>

对于其他动物也是如此。换句话说，动物的构成构件总大致是相同的。

<details><summary>Original English</summary>
The same is true for other animals.

In other words, the building blocks

of animals are always roughly the same.
</details>

因此，一头质量是一千倍的大象，拥有的细胞数量大约是一千倍。所以你会以为它需要一千倍的能量，即每天250,000千卡。

<details><summary>Original English</summary>
So an elephant that has

a thousand times the mass

has about a thousand times as many cells.

So you'd expect it would need a thousand

times as much energy.

So 250,000 kilocalories per day.
</details>

但这正是你遇到麻烦的地方。

<details><summary>Original English</summary>
But that is where you run into problems.
</details>

- 那么这里的问题是什么呢？如果我是一个生物体，一整天都在燃烧能量，那么这部分能量就会以体热的形式辐射出去。因此，我们一直在通过体表、通过皮肤向环境中散失热量。

<details><summary>Original English</summary>
- So what's the issue here?

If I'm an organism

and I'm burning up energy all day long,

that energy is radiated out

in the form of body heat.

So we're constantly losing

heat through our surface,

through our skin, to the environment.
</details>

- 为了说明为什么这很重要，让我们简化这个问题，做物理学家标准的做法：假设我们的动物都是完美的球体。

<details><summary>Original English</summary>
- To see why this matters,

let's simplify the problem

and do the standard physicist thing.

Let's assume our animals

are perfect spheres.
</details>

需要澄清的是，这并不是论证成立所必需的，但它确实让一切变得容易理解得多。

<details><summary>Original English</summary>
To be clear, this isn't necessary

for the argument to work,

but it does make everything

a lot easier to follow.
</details>

由于动物的体积与其质量成正比，我们这头3000千克重的大象的体积比我们3千克重的猫大一千倍。

<details><summary>Original English</summary>
Since the volume of an animal

is proportional to its mass,

our 3000 kilogram elephant

has a volume a thousand times

greater than our three kilogram cat.
</details>

因此它的半径必须大10倍。这是因为体积与半径的立方成正比。

<details><summary>Original English</summary>
So its radius must be 10 times larger.

That's because volume is

proportional to radius cubed.
</details>

但表面积的增长仅与半径的平方成正比。因此，大象的表面积仅仅增加了100倍。

<details><summary>Original English</summary>
But surface area only

grows as radius squared.

So the elephant's surface area

only increases by a factor of 100.
</details>

产生一千倍的热量，却只有一百倍的表面积来将其辐射散发出去，大象的结局将会非常悲惨。如果真是这种情况，它会被活活煮熟。

<details><summary>Original English</summary>
Generating a thousand times as much heat

while only having a hundred

times the surface area

to radiate it away would end very

poorly for the elephant.

If this were the case,

it would boil alive.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

因此在1838年，法国科学家提出了一种不同的缩放律。由于代谢产生热量，而热量通过表面辐射，所以代谢率即B，应该转而与表面积A成正比缩放。

<details><summary>Original English</summary>
So in 1838,

French scientists proposed

a different scaling law.

Since metabolism generates heat

and that heat is radiated

through the surface,

metabolic rate or B,

should scale in proportion

to the surface area, A, instead.
</details>

这被称为表面积定律。

<details><summary>Original English</summary>
This became known as the surface law.
</details>

现在，我们可以将其改写，看看代谢率是如何作为质量的函数进行缩放的。

<details><summary>Original English</summary>
Now, we can rewrite this to see

how metabolic rate scales

as a function of mass.
</details>

表面积与半径的平方成正比，所以我们可以将其替换进来；如果质量与半径的立方成正比，那么半径必与质量的三分之一次方成正比。

<details><summary>Original English</summary>
Surface area is proportional

to radius squared,

so we can swap that in,

and if mass is proportional

to radius cubed,

then radius must be proportional

to mass to the one-third.
</details>

将这代入R，我们发现代谢率应该与质量的三分之二次方成比例缩放。

<details><summary>Original English</summary>
Plugging that in for R,

we find that metabolic rate should scale

with mass to the two-thirds.
</details>

- 一个非常熟悉的例子来自烹饪的思考。

<details><summary>Original English</summary>
- Really familiar example would

come from thinking about cooking.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

也许你想为感恩节做一只大火鸡。人们通常会表述为：每磅需要多长时间？但你会意识到这是线性思维。

<details><summary>Original English</summary>
Maybe you want to make a

big turkey for Thanksgiving.

People commonly phrase it as

how long do I need per pound?

But that you realize is linear thinking.
</details>

真正重要的其实是禽鸟或烤肉的厚度，因为热量是通过烤箱的传导进来的，必须在肉内部进行热扩散。

<details><summary>Original English</summary>
The important thing is really

the thickness of the bird

or the roast, because

the heat is coming in

by conduction from the oven

and it's got to do thermal

diffusion into the meat.
</details>

扩散所需的时间将与特征长度（在这种情况下就是肉的厚度）呈比例缩放。它会与尺寸的平方相关，而肉的体积则与长度的立方相关，且这与禽鸟或烤肉的重量成正比。

<details><summary>Original English</summary>
The time for the diffusion will scale

like the characteristic length,

which in this case would be

the thickness of the meat.

It'll go like the dimension squared,

whereas volume of the meat is

going to be like length cubed,

and that's proportional to the weight

of the bird or the roast.
</details>

所以当你把这些结合在一起时，就会得出烤肉所需的特征时间与其质量的三分之二次方成正比。

<details><summary>Original English</summary>
So when you put those things together,

you'll get that the characteristic

amount of time needed

to cook the roast will go like its mass

to the two-thirds power.
</details>

- 那么如果我想烤一块重量是另一块烤肉两倍的肉，要多长时间？是2的三分之二次方倍的时间吗？

<details><summary>Original English</summary>
- So if I'm thinking about cooking a roast

that weighs twice as much as

another roast, how much longer?

Is that two to the two-thirds the time?
</details>

- 对，如果你想让重量翻倍，那么你只需要多煮大约60%的时间，而不是100%。

<details><summary>Original English</summary>
- Yeah, if you wanted

to double the weight,

then you only have to

cook it about 60% longer,

not 100% longer.
</details>

- [主持人] 同样，根据这种缩放关系，一头重量是一只猫一千倍的大象，应该只多消耗一百倍的卡路里。也就是25,000千卡，而不是250,000千卡。

<details><summary>Original English</summary>
- [Host] Similarly,

according to this scaling,

an elephant that's a thousand

times as heavy as a cat

should only burn a hundred

times as many calories.

So 25,000 instead of 250,000.
</details>

那么对塔斯科而言，适当的LSD剂量本应只有30毫克。

<details><summary>Original English</summary>
And the appropriate dose of LSD for Tusko

would've been just 30 milligrams.
</details>

这两个截然不同的预测源于关于代谢率如何作为质量的函数进行缩放的不同假设。

<details><summary>Original English</summary>
These two wildly different

predictions come from different

assumptions about how metabolic rate

scales as a function of mass.
</details>

但请注意，在这两种情况下，它都只是与质量的某个幂次成正比。

<details><summary>Original English</summary>
But notice in both cases,

it's just proportional

to mass raised to some power.
</details>

### 幂律与克莱伯定律

这种关系被称为幂律，所有的幂律都有一个特殊性质。

<details><summary>Original English</summary>
These kinds of relationships

are called power laws

and all power laws have

a special property.
</details>

如果你对X和Y的值取对数，就会得到一条直线。

<details><summary>Original English</summary>
If you take the logarithm

of the X and Y values,

you get a straight line.
</details>

而这条直线的斜率等于幂律的指数。这使得识别不同类型的幂律变得很容易。

<details><summary>Original English</summary>
And the slope of the line is equal

to the exponent of the power law.

This makes it easy to identify

different types of power laws.
</details>

如果斜率是1，那就是日常的线性缩放。如果小于1，就像表面积定律那样，这被称为次线性缩放。如果大于1，则被称为超线性缩放。

<details><summary>Original English</summary>
If the slope is one, that's

just everyday linear scaling.

If it's less than one,

like the surface law,

that is called sublinear scaling.

And if it's larger than one,

that is known as superlinear scaling.
</details>

在近一百年的时间里，生物学家普遍赞同表面积定律的三分之二指数对于代谢率是正确的。

<details><summary>Original English</summary>
For nearly a hundred years,

biologists generally agreed

that the two-thirds exponent

of the surface law was the

correct one for metabolic rate.
</details>

但随后在1932年，瑞士生物学家马克斯·克莱伯（Max Kleiber）决定对此进行检验。

<details><summary>Original English</summary>
But then in 1932, Swiss

biologist, Max Kleiber,

decided to put it to the test.
</details>

他选取了从150克的小鸽子到680,000克的大阉牛等不同动物的代谢率，然后在双对数坐标图上将它们与各自的质量绘制在一起。

<details><summary>Original English</summary>
He took the metabolic rates

of different animals from

a small dove at 150 grams

to a large steer at 680,000 grams,

and then he plotted

them against their mass

on a log log plot.
</details>

正如所预期的，所有的数据点确实落在了一条直线上。但斜率并不是三分之二，而是大约四分之三。

<details><summary>Original English</summary>
And as expected, all the data

did fall on a straight line.

But the slope wasn't two-thirds.

Instead, it was about three quarters.
</details>

这后来被称为克莱伯定律。

<details><summary>Original English</summary>
This became known as Kleiber's Law.
</details>

它意味着，如果让动物的质量翻倍，代谢率大约会增加到1.68倍，增加了68%，而不是三分之二缩放律所预测的59%。

<details><summary>Original English</summary>
It implies that if you

double an animal's mass,

metabolic rate goes up by about 1.68,

an increase of 68% instead of the 59%,

which would be predicted by

the two-thirds scaling law.
</details>

因此，根据克莱伯定律，一头大象消耗的卡路里大约是一只猫的178倍，即大约45,000千卡。

<details><summary>Original English</summary>
So according to Kleiber's Law,

an elephant burns roughly 178 times

as many calories as a cat,

or about 45,000 kilocalories.
</details>

而塔斯科实际本应接受的LSD剂量是53毫克，大约是研究人员给它的剂量的六分之一。

<details><summary>Original English</summary>
And the actual LSD dose

Tusko should have received

was 53 milligrams, which is

around a sixth of the dose

the researchers gave him.
</details>

这就解释了大象塔斯科身上的用药灾难。

<details><summary>Original English</summary>
So that explains the dosing catastrophe

with Tusko The Elephant.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

克莱伯最初的研究是基于一个较小的数据集，主要是由哺乳动物构成的。

<details><summary>Original English</summary>
Kleiber's original work was

based on a small data set,

primarily made up of mammals.
</details>

但如果你将更广泛的哺乳动物以及鸟类、爬行动物和鱼类等其他动物的数据绘制出来，你会发现它们都大致遵循相同的缩放关系。

<details><summary>Original English</summary>
But if you plot the data for

a larger range of mammals,

as well as for other animals

like birds, reptiles, and fish,

you find that they all follow

roughly the same scaling relationship.
</details>

由于温血动物的基础代谢率高于冷血动物，它们并非全都完美地落在同一条线上，但它们全都按照相同的幂律（质量的四分之三次方）进行缩放。

<details><summary>Original English</summary>
Now, they don't all fit

perfectly onto the same line

because the base metabolic rate

for warm-blooded animals is higher

than for cold-blooded ones,

but they all scale according

to the same power law,

mass raised to the three-quarters.
</details>

有人认为，这种关系一直延伸到单个细胞及其内部的分子机器。

<details><summary>Original English</summary>
Some argue that this relationship

expands all the way down

to single cells and the molecular

machines inside of them.
</details>

如果是真的，那么克莱伯定律所统治的生命跨越了超过25个数量级。

<details><summary>Original English</summary>
If that's true, Kleiber's Law governs life

spanning more than 25 orders of magnitude.
</details>

但接下来的问题是，如果一头大象拥有多得多的细胞，且每个细胞的大小与较小生物体内的细胞相似，然而它所消耗的能量却按比例更少——就好像它每磅、每千克或每个细胞的代谢率更低——这实际上是在说那些细胞在以少得多的能量运转。

<details><summary>Original English</summary>
But then the question is,

if an elephant has so many more cells

and each cell is a similar size

to a cell in a smaller creature,

and yet it's using

proportionately less energy,

like it's got a lower

metabolic rate per pound

or per kilo or per cell,

that's really saying that those cells

are functioning with much less energy.
</details>

- 好像体型大具有某种效率，但很难理解其中的原因。究竟是细胞在互相提供什么，以某种方式进行协作呢？

<details><summary>Original English</summary>
- It's like there's some

efficiency to being big,

and it's hard to understand why.

What is it that the cells

are providing to each other,

somehow cooperating in some way?
</details>

- 我刚才在计算器里输入了100的四分之三次方，所以如果你有一个体型大100倍的生物体，按照这个规律，代谢率只有31.6倍。所以这似乎是一笔巨大的节省。

<details><summary>Original English</summary>
- I just put in my calculator

100 to the three quarters,

so if you got an organism

that's 100 times bigger,

then according to this, only 31.6

times the metabolic rate.

So it seems like a big savings.
</details>

- 这是一个巨大的提升，对吧？这是一笔巨大的节省。这是一个生物学事实，但一个世纪以来，人们一直在争论究竟是什么导致了这四分之三。

<details><summary>Original English</summary>
- It's a massive improvement, right?

It's a big savings.

It's a biological fact,

but people have been

arguing now for a century

what accounts for this three quarters.
</details>

（柔和的音乐）

<details><summary>Original English</summary>
(mellow music)
</details>

- 在克莱伯提出这一观察后的几十年里，这个谜团只增不减。

<details><summary>Original English</summary>
- In the decades following

Kleiber's observation,

the mystery only deepened.
</details>

研究人员发现，大脑大小也大致按照质量的四分之三次方进行缩放，动物的生长速度以及每分钟泵出的血量同样如此。

<details><summary>Original English</summary>
Researchers discovered that

brain size also roughly scales

as mass to the three quarters,

and so does an animal's growth rate

and the amount of blood pumped per minute.
</details>

但并非所有属性都按质量的四分之三次方进行缩放。

<details><summary>Original English</summary>
But not every property scales

as mass to the three quarters.
</details>

- 如果你问一个生物、一只哺乳动物能活多久，那往往与其质量的四分之一次方成正比。是四分之一，而不是四分之三。

<details><summary>Original English</summary>
- If you ask how long a

creature will live, a mammal,

that tends to be proportional to its mass

to the one quarter power.

One over four, not three over four.
</details>

- [主持人] 所以这意味着如果你把哺乳动物的质量翻倍，那么平均而言，它的寿命大约会长19%左右。同样，血液循环时间也按比例缩放

<details><summary>Original English</summary>
- [Host] So that means if you

double the mass of a mammal,

then on average, its lifespan

is around 19% longer.

Similarly, blood

circulation time also scales
</details>

<!-- chunk 2/4 -->

大致与质量的四分之一次方成正比，而呼吸频率和心率则都与负四分之一次方成比例。它们并不全都是四分之三幂律，但它们都是四分之一的倍数。所以每个人心中的疑问都是，这些四分之一幂标度律到底是从何而来的？

<details><summary>Original English</summary>
as roughly mass to the one

quarter, while breathing rate

and heart rate both scaled

to the negative one quarter.

They're not all three quarters power laws,

but they are all multiples of a quarter.

So the question on everyone's mind was

where are these quarter power

scaling laws coming from?
</details>

- 20世纪90年代出现了一种流行的理论。

（悠扬的音乐）

布莱恩·恩奎斯特当时正在攻读生物学学士学位。

<details><summary>Original English</summary>
- One popular theory emerged in the 1990s.

(mellow music)

Brian Enquist was studying

for an undergraduate degree in biology.
</details>

- 你当时上的大多数生物学课程，都是学习三羧酸循环，然后你必须死记硬背花朵的所有不同组成部分，然后所有……对于每样东西他们都有一套不同的专业术语。

<details><summary>Original English</summary>
- Most of the biology

classes then that you take,

you learn about the Krebs Cycle

and then you have to memorize

all the different parts

of a flower and then all...

They have a different

terminology for everything.
</details>

- [Henry] 但后来有一天他上了一节动物学课，课上向他展示了那些四分之一幂标度图。

<details><summary>Original English</summary>
- [Henry] But then one day

he took a zoology class

where they showed him those

quarter power scaling plots.
</details>

- [Brian] 我简直不敢相信。我当时心想：“你一定是在开玩笑吧。”你看，这某种程度上就像是构成了生物多样性基础的核心本质。就在那一刻，我立刻意识到，我想放弃我那种专门化的植物生理学研究，去从事一些与标度相关的工作。

（悠扬的音乐）

<details><summary>Original English</summary>
- [Brian] I just couldn't believe it.

I was like, "You got to be kidding me."

You know, this is kind of

like something fundamental

that's kind of like underlying

biological diversity.

And there I knew immediately that I wanted

to kind of quit my specialized

kind of plant physiology research

and do something associated with scaling.

(mellow music)
</details>

- [Henry] 于是恩奎斯特开始在詹姆斯·布朗教授手下攻读博士学位，布朗教授多年来一直在思考标度律。他们知道，当幂律出现时，底层系统中往往存在某种形式的自相似性。因此他们想知道，那种自相似性可能是什么？他们推测，这可能与资源在体内运输的方式有关，具体来说，就是负责这一功能的网络。他们拥有生物学直觉，但要获得一个完整的理论，他们需要一个正式的数学框架。换句话说，他们需要一位数学家或理论物理学家。

<details><summary>Original English</summary>
- [Henry] So Enquist started

studying for his PhD,

under Professor James Brown,

who had been thinking about

scaling laws for years.

So they knew that often

when power laws appear,

there's some form of self-similarity

in the underlying system.

So they wondered, what could

that self-similarity be?

And they suspected that it

might have something to do

with the way resources are

transported through the body,

specifically the networks that do this.

They had the biological intuition,

but to get a complete theory,

they needed a formal

mathematical framework.

In other words, they

needed a mathematician

or a theoretical physicist.
</details>

- 当时，吉姆与圣菲研究所有联系，他开始向周围打听：这里有谁对这些生物标度关系感兴趣吗？当时的主席说：“你猜怎么着？我认识一位物理学家，人在洛斯阿拉莫斯，他之前一直在谈论生物标度关系。”于是我们见到了杰弗里，那一瞬间的感觉就像是，我们就像是多年来一直在谈论同样的事情。就像是，你知道的，找到了一个一直讲着和你相同语言的人，而以前却没有人能听懂你。

<details><summary>Original English</summary>
- And at the time, Jim was associated

with the Santa Fe Institute,

and he started asking around with,

is there anyone up here

that's interested in these

biological scaling relationships?

And then the president at the

time said, "You know what?

I know of this physicist

who's up at Los Alamos

who was talking about biological

scaling relationships."

And so we met Geoffrey and

it was like immediately,

it's like we'd been talking

about the same things

for like years.

It's like, you know, finding,

someone who's been like

speaking your language,

but no one could understand you.
</details>

- [Henry] 于是韦斯特、布朗和恩奎斯特联手，试图为克莱伯定律寻找一个令人信服的解释。

<details><summary>Original English</summary>
- [Henry] So West, Brown

and Enquist teamed up

to try and find a compelling

explanation for Kleiber's Law.
</details>

### WBE理论的三个前提与分形网络假设

- 他们首先假设了三个简单的前提。第一个前提是，分配资源的网络是空间填充的，因为它们需要到达体内的每一个细胞。第二个前提是，这些网络的末端单元，即输送系统外围最薄的管段，无论生物体的大小如何，都具有相同的宽度。也就是说，向大象皮肤细胞输送营养的最外层血管，其粗细程度与小鼠体内的血管大致相当。只是大象拥有的数量要多得多。第三个前提是，随着时间的推移，进化推动了这些运输网络走向高效的设计。那么，这样的网络应该是什么样子的呢？

（悠扬的音乐）

<details><summary>Original English</summary>
- They started by assuming

three simple premises.

The first premise is that the networks

that distribute resources

are space-filling,

since they need to reach

every cell in the body.

The second premise is

that the terminal units

of those networks, the thinnest segments

on the outer periphery

of the delivery system,

have the same width regardless

of the size of the organism.

That is the outermost blood

vessels that carry nutrients

to an elephant's skin

cells are about as thick

as the ones in a mouse.

The elephant just has many more of them.

And the third premise is that over time,

evolution has driven

these transport networks

toward an efficient design.

So what should such a network look like?

(mellow music)
</details>

直观地说，为了尽可能高效地将燃料从一个地方运送到另一个地方，你会希望路径尽可能短。所以基本上就是一条直线。但由于燃料需要到达身体的每一个部位，你也会需要许多不同的路径。而随着生物体越来越大，内部的网络需要覆盖越来越大的体积。实现这一点的一种方法是拉长所有路径，以匹配动物的生长。在这种情况下，动物的体积应当与这些内部路径长度的立方成比例。或者换个形式表述，内部路径长度应该与体积的三分之一次方成比例，就像动物的整体身长一样。

<details><summary>Original English</summary>
Well, intuitively, to get

fuel from one place to another

as efficiently as possible,

you want the path to be

as short as possible.

So basically a straight line.

But because fuel needs to

reach every part of the body,

you would also need many different paths.

And as you go to larger

and larger organisms,

the networks inside need to

reach a larger and larger volume.

One way to do this is

to stretch all the paths

and match the growth of the animal.

In this case, the volume of the animal

should scale as these

internal path lengths cubed.

Or if we rearrange that,

internal path length should scale

as volume to the one-third,

just like the overall

length of the animal does.
</details>

但这种设计极具浪费性。以这两个区域为例。将血液输送到这里的两条血管在体内走过了几乎相同的路径，并且仅在到达目的地之前才分开。如果相反，我们在此之前只使用一根血管，仅在路径需要分叉时才将其分开，那么我们就可以用少得多的血管材料和少得多的充盈血管的血液来为这两个区域提供服务。当然，你可以将这个逻辑推广到体内的所有血管，最终得到一个分支血管的高效得多的设计。

<details><summary>Original English</summary>
But this design is incredibly wasteful.

Take these two regions.

The two vessels that

are bringing blood here

go through almost the

same path in the body,

and they only split up just

before they reach their destinations.

If instead we had just one

vessel up to this point

and split it only when the

paths needed to diverge,

we could serve the two regions

using a lot less vessel material

and a lot less blood to fill the vessels.

Of course, you can extend this logic

for all the blood vessels in the body,

and you end up with a

much more efficient design

of branching blood vessels.
</details>

但现在我们遇到了另一个问题，因为每个分叉点都为部分血液的反弹提供了机会，也就是反射。如果有许多次反射，那就意味着泵送血液需要在能量上有显著更高的消耗。因此接下来，他们主张自然界应当青睐使反射最小化的结构。事实证明，如果血管分叉前后的横截面积保持不变，这种情况就会发生。因此，如果主血管的横截面积为两平方厘米，那么两根分支血管各自的面积都需要为一平方厘米，至少对于大血管而言是这样。对于较小的血管，子分支可以稍微粗一些，以便血液减速并与所到达的组织交换资源。如果你在整个网络中不断重复这种模式，最终得到的就是这个：一个自相似的分形分支。如果你观察循环系统的实际形状，它就具备这种几何结构。因此，他们似乎切中了某些关键。

<details><summary>Original English</summary>
But now we run into another issue

because each branching point

provides an opportunity

for some of the blood to

bounce back, that is reflect.

If you have many reflections,

that would mean it

costs significantly more

energy to pump blood around.

So next, they argue that

nature should favor structures

that minimize reflections.

And as it turns out, this happens

if the cross-sectional area of the vessels

stays the same before

and after the branching.

So if you've got a cross-sectional area

of two centimeters squared

for the main vessel,

then each of the two

branches need to have an area

of one centimeter squared each,

for large vessels at least.

For smaller ones, daughter

branches can be a bit thicker

to allow blood to slow down

and exchange resources with

the tissue it's reaching.

If you keep repeating this

pattern across the network,

you end up with this, a

branching self-similar fractal.

And if you look at the actual shape

of the circulatory system,

it has this geometry.

So it seemed like they

were onto something.
</details>

### 豪斯多夫维度与四分之三幂律的推导

- 但你如何从这一点走向四分之一幂标度律呢？数学家费利克斯·豪斯多夫发现，自相似分形具有一个有趣的特性。

（悠扬的音乐）

以一条直线段为例。它是完全一维的，根本不是分形。豪斯多夫给这条线段赋予了1.0的值。但现在想象一下给它增加几处弯曲，并在这些弯曲上增加更多的弯曲。如果你一直这样做，这条线就会变得越来越像分形。最终，如果你持续施加合适形式的扭曲，那个一维线段就会填满二维平面的整个区域。豪斯多夫为这些空间填充的分形曲线赋予了2.0的值，对应于它们的维度。同样的思想也适用于二维表面。

<details><summary>Original English</summary>
- But how do you get from this

to quarter power scaling laws?

Well, mathematician Felix

Hausdorff discovered

that self-similar fractals

have an interesting property.

(mellow music)

Take a straight line segment.

It's completely one-dimensional

and not a fractal at all.

Hausdorff assigned this

line segment a value of 1.0.

But now imagine adding a few bends

and more bends to those bends.

If you keep doing this,

the line becomes more

and more fractal-like.

Eventually, if you keep applying

the right kind of contortions,

that one-dimensional line segment fills up

an entire region of the 2D plane.

Hausdorff assigned these

space-filling fractal curves

a value of 2.0, corresponding

to their dimensionality.

The same ideas apply to a 2D surface.
</details>

- 试想一张纸，对吧？二维的。分形网络所做的全部事情就是揉搓那张纸，它实际上就填满了一个球体的体积。所以你现在可以把那张纸描述为一个球体，而不是一张二维的纸。

<details><summary>Original English</summary>
- So think about a piece of paper, right?

Two-dimensional.

All then the fractal network

is doing is crumpling up

that sheet of paper,

and it effectively fills

a ball of volume.

So you can now describe

that sheet of paper

as a sphere instead of a

two-dimensional sheet of paper.
</details>

- [Henry] 在越来越小的尺度上重复合适的折叠模式，一个二维表面就会填满越来越多的三维体积。在数学极限下，它变成空间填充的，其豪斯多夫维度为3.0。

<details><summary>Original English</summary>
- [Henry] Repeat the

right pattern of folds

at smaller and smaller

scales, and a 2D surface

fills more and more of a 3D volume.

In the mathematical limit,

it becomes space filling

with Hausdorff dimension of 3.0.
</details>

- [Brian] 你知道，从生物学上讲，我说：“那么，这意味着什么呢？”这使得给定大小的生物体能够塞入比预期更多的这种代谢表面积。正是由于这种类似分形的结构，使得你能够把所有这些褶皱和回旋叠合在一起塞进去，从而塞入数量巨大的膜表面。

<details><summary>Original English</summary>
- [Brian] You know, biologically, I said,

"Well, what does that mean?"

That enables an organism for a given size

to pack in more of these

metabolic surface areas

than would be expected.

And it's because of this

fractal-like structure

that enables you then to pack

in and have all of these folds

and convolutions and on top of each other

to pack in an enormous

amount of membrane surfaces.
</details>

- 结果就是，循环系统表面的豪斯多夫维度大致为3，这意味着它的表面积并非与其长度的平方成比例，而是与长度的立方成比例。既然代谢率取决于穿过该表面积交换资源的速度，那么它也必须与长度的立方成比例。但请记住，韦斯特、布朗和恩奎斯特想要解释的是克莱伯定律。因此，他们需要知道代谢率如何随质量成比例变化。

（悠扬的音乐）

既然每个细胞都需要由网络提供服务，这意味着网络周围的体积应该与动物的质量成正比。由于体积就是表面积乘以长度，而表面积与长度的立方成正比，这就意味着体积和质量都必须与长度的四次方成正比，这可以重新改写以表明长度与质量的四分之一次方成正比。如果你把这个代入代谢率的方程，你就会发现代谢率必须与质量的四分之三次方成正比，正如马克斯·克莱伯所发现的那样。韦斯特、布朗和恩奎斯特于1997年发表了他们的成果，很快根据他们姓氏的首字母被称为WBE理论。

<details><summary>Original English</summary>
- As a result, the Hausdorff

dimension of the surface

of the circulatory

system is roughly three,

meaning its surface area doesn't scale

as its length squared,

but it's length cubed.

And since the metabolic rate hinges on

how fast resources can be

exchanged across the surface area,

well, it must also

scale like length cubed.

But remember, West, Brown and Enquist

wanted to explain Kleiber's Law.

So they needed to know how

metabolic rate scales with mass.

(mellow music)

Since every cell needs to

be served by the network,

this means that the volume

around the network should be proportional

to the animal's mass.

And since volume is just

surface area times length

and surface area is

proportional to length cubed,

that means both volume and mass

must be proportional to

length to the fourth,

which can be rewritten to show

that length is proportional

to mass raised to the one quarter.

And if you plug that into the equation

for the metabolic rate,

you find that the metabolic rate

must be proportional to

mass to the three-quarters,

exactly as Max Kleiber had found.

West, Brown and Enquist

published their work in 1997,

and it soon came to be known

as WBE Theory, after their initials.
</details>

- 而且这个理论相当严格。它做出了非常具体的预测。这是严谨的科学。对吧？这是敢于承担风险，而且它是一个极其优美的理论。

（悠扬的音乐）

<details><summary>Original English</summary>
- And the theory is quite rigid.

It makes very specific predictions.

This is good science.

Okay?

This is sticking your neck out,

and it's an incredibly beautiful theory.

(mellow music)
</details>

- [Derek] 看看杰弗里·韦斯特书中这张表格。这些是WBE理论所预测的标度指数，包括许多不是四分之一倍数的指数，但都源自同一个理论。例如，动物主动脉的半径应该与其质量的八分之三次方（即0.375）成比例。它的肺部面积应该与质量的十二分之十一次方（即约0.92）成比例。这张图表总共做出了26个不同的预测。现在，这些是观察到的数据。主动脉半径，0.36。肺面积，0.95。

<details><summary>Original English</summary>
- [Derek] Take a look at this table

from Geoffrey West's book.

These are the scaling

exponents WBE theory predicts,

including many that are

not multiples of a quarter,

but all follow from the same theory.

For example, the radius

of an animal's aorta

should scale with its mass

to the three-eighths or .375.

And the area of its lungs

should scale with mass

to the 11-12ths or about 0.92.

In total, this chart makes

26 different predictions.

Now, these are the observed data.

Radius of the aorta, 0.36.

Lung area, 0.95.
</details>

- [Steven] 这就是他们所做的事情真正令人震惊的地方。他们有一张包含大约20或30个奇异指数预测的表格，而那正是你在数据中真实看到的。所以这一个理论不仅解释了代谢的四分之三次方，还解释了生物学家所测量的切实数十种其他事物。

<details><summary>Original English</summary>
- [Steven] That's the really shocking thing

about what they did.

They had a table with

something like, I don't know,

20 or 30 predictions of exotic exponents,

and that's what you

really see in the data.

So this one theory accounts not only

for the three-quarters

power of metabolism,

but for literally dozens of other things

that biologists have measured.
</details>

### 从代谢率推导心率与寿命

- 一旦你得到了代谢的四分之三定律，其中一些标度律就很容易解释了。以哺乳动物的心率为例。心率等于血流速率除以每次心跳的血量或容积。

（悠扬的音乐）

人们发现每搏输出的血量与动物的质量成正比。所以那就是M。那么血流速率呢？记住，代谢关乎营养如何在全身分配。因此大多数生物学家都认同代谢率与血流速率彼此成正比。所以心率应当与代谢率除以质量成比例变化。代入克莱伯发现的标度律，得到的是M的负四分之一次方，这意味着体型更大的动物心跳应该比体型较小的动物更慢。而这正是我们在自然界中所观察到的。世界上最小的哺乳动物伊特鲁里亚鼩鼱，其心率达到了非同寻常的每分钟1200次。那就是每秒20次心跳。而最大的陆生哺乳动物非洲草原象，其典型心率仅为每分钟30次。

<details><summary>Original English</summary>
- Some of the scaling

laws are easy to explain

once you've got the

three-quarters law for metabolism.

Take a mammal's heart rate, for instance.

Heart rate is equal to the blood flow rate

over the amount or volume

of blood in every beat.

(mellow music)

The volume of blood

per beat has been found

to scale in direct proportion

to an animal's mass.

So that's just M.

And the blood flow rate?

Well, remember that

metabolism is all about

how nutrients get

distributed around the body.

So most biologists agree metabolic rate

and blood flow rate are directly

proportional to one another.

So heart rate should scale

as metabolic rate over mass.

Swapping in the scaling

law Kleiber had found,

that gives us M to the minus one quarter,

meaning bigger animals should have slower

heartbeats than smaller ones.

And this is exactly what

we observe in nature.

The world's smallest

mammal, the Etruscan Shrew,

has an extraordinary heart

rate of 1200 beats per minute.

That's 20 beats per second.

Whereas the biggest land mammal,

the African bush elephant,

has a typical heart rate of

only 30 beats per minute.
</details>

我们可以对寿命做类似的事情。主要理论之一是动物的寿命取决于代谢损伤的累积。也就是说，随着生物体内的每一块组织在一段时间内处理营养，这会导致损伤累积，随着时间的推移，这会导致动物死亡。因此动物累积损伤的速率就是其单位质量的代谢率，其寿命应该是该速率的倒数。如果损伤累积得更快，它就死得更早。如果累积得更慢，它就活得更长。所以寿命与M除以B成正比，或者代入克莱伯定律，与M的四分之一次方成正比。因此寿命应当随质量增加。你在自然界中确实能看到这一点。

（悠扬的音乐）

一只鼩鼱在野外只能活一到两年，而一头强大的非洲象可以活到70岁。所以如果你是一只小型哺乳动物，你每分钟的心跳次数很多，但寿命相对较短。反之，如果你是一只体型较大的哺乳动物，你的心跳慢得多，寿命也长得多。

<details><summary>Original English</summary>
And we can do something

similar for lifespan.

One of the leading theories is

that an animal's lifespan is based on

the accumulation of metabolic damage.

That is, as each chunk

of tissue in an organism

processes nutrients over time,

this causes damage to accumulate,

and that over time

causes the animal to die.

So the rate at which an

animal accumulates damage

is its metabolic rate per unit of mass,

and its lifespan should be

the inverse of that rate.

If damage accumulates

faster, it dies sooner.

If it accumulates slower, it lives longer.

So lifespan is proportional to M over B,

or substituting in Kleiber's

Law, M to the one quarter.

So lifespan should increase with mass.

And you do see this in nature.

(mellow music)

A shrew only lives for one

to two years in the wild

while a mighty African elephant

can live up to 70 years.

So if you're a small mammal,

you have many heartbeats per minute,

but you live a relatively short life.

Conversely, if you're a larger mammal,

your heart beats much slower

and you live a lot longer.
</details>

- 所以这就是，你知道的，活得快、耗尽精力、英年早逝，对吧？或者是精打细算、活得非常长久。

<details><summary>Original English</summary>
- So it's the, you know,

live fast and burnout

and die young, right?

Or spend it frugally and

live a really long life.
</details>

- 但你可能还注意到了别的事情。

<details><summary>Original English</summary>
- But you might have also

noticed something else.
</details>

<!-- chunk 3/4 -->

### 心率、寿命与十亿次心跳法则

心率按 B 比 M 的比例缩放。

<details><summary>Original English</summary>

Heart rate scales as B over M.
</details>

所以它等于 B 除以 M 乘以某个常数。

<details><summary>Original English</summary>

So it equals B over M times some constant.
</details>

而寿命按 M 比 B 的比例缩放。

<details><summary>Original English</summary>

And lifespan scales as M over B.
</details>

它们互为倒数。

<details><summary>Original English</summary>

They're inverses of each other.
</details>

它们以相等且相反的方向缩放。

<details><summary>Original English</summary>

They scale in equal and

opposite directions.
</details>

现在，动物一生中的心跳总数，正好就是心率乘以寿命。

<details><summary>Original English</summary>

Now, the total number of

heartbeats in an animal's life

is just the heart rate

multiplied by the lifespan.
</details>

所以当你将这两项相乘时，它们相互抵消，只留给你一个常数。

<details><summary>Original English</summary>

So when you multiply these

two terms, they cancel out,

leaving you with just a constant.
</details>

这就表明，无论你说的是哪种哺乳动物，它都应该拥有大致相同的心跳次数。

<details><summary>Original English</summary>

So that suggests that no matter

what mammal you're talking about,

it should have roughly the

same number of heartbeats.
</details>

你只需代入一些例子就能得出那个数值。

<details><summary>Original English</summary>

You can find that number by

just plugging in some examples.
</details>

我们从小臭鼩开始。

<details><summary>Original English</summary>

Let's start with the Etruscan Shrew.
</details>

这种鼩鼱每分钟 1200 次的心跳乘以大约 1.5 年的寿命，在鼩鼱的一生中大约会有 9.5 亿次心跳。

<details><summary>Original English</summary>

The shrew's 1200 beats per

minute multiplied by a lifespan

of around 1.5 years gives you

around 950 million heartbeats

in the course of the shrew's life.
</details>

与此同时，一只非洲象每分钟 30 次的心跳乘以大约 65 年的寿命，得出的心跳次数略高于十亿次。

<details><summary>Original English</summary>

Meanwhile, an African

elephant's 30 beats per minute

multiplied by a lifespan

of around 65 years

gives you a little over

a billion heartbeats.
</details>

我们还可以继续列举下去。

<details><summary>Original English</summary>

And we could keep going.

(upbeat music)
</details>

但几乎对于你所观察的每一种哺乳动物，你最终都会落在同一个数字上，即大约十亿次心跳。

<details><summary>Original English</summary>

But for nearly every mammal you look at,

you keep landing at the same figure of

around a billion heartbeats.
</details>

这就是为什么几乎每一种哺乳动物，从小田鼠到瞪羚，从猎豹到河马，它们从出生到死亡的那一天，总共都获得大约十亿次心跳。

<details><summary>Original English</summary>

This is why nearly every

mammal from a tiny field mouse

to a gazelle, from a

cheetah to a hippopotamus,

they all get around a billion heartbeats

between the day they're

born and the day they die.
</details>

但有一个主要的离群者，有一种哺乳动物获得的心跳次数远远超过十亿次。

<details><summary>Original English</summary>

But there is one major outlier, one mammal

that gets significantly more

than a billion heartbeats.
</details>

那便是我们人类。

<details><summary>Original English</summary>

And that is us, humans.

(mellow music)
</details>

我们是幸运的那些。

<details><summary>Original English</summary>

We are the lucky ones.
</details>

三个世纪前，人类还要接近得多于十亿次心跳这一标准数值。

<details><summary>Original English</summary>

Three centuries ago,

humans were much closer

to the standard value of

one billion heartbeats.
</details>

但到了 1850 年代中期前后，细菌学说和更好的卫生方法得到广泛普及，导致儿童死亡率以及疾病死亡人数急剧下降。

<details><summary>Original English</summary>

But around the mid 1800s, germ theory

and better sanitation

methods became widespread,

causing a stark decrease in

the number of child mortalities

and deaths from disease.
</details>

于是预期寿命开始上升。随之而来的，是一生中心跳的平均次数。

<details><summary>Original English</summary>

So life expectancy began to climb up.

And with it, the average number

of heartbeats in a lifetime.
</details>

如果你仔细看，你也可以看到一些显著的下降，比如 1918 年西班牙流感大流行造成的这次下挫，或者在这一边，看起来像是第二次世界大战的影响。

<details><summary>Original English</summary>

If you look closely, you can

also see some significant drops

like this 1918 dip from

the Spanish flu pandemic

or over here, what appears to be

the impact of the Second World War.
</details>

但总的来说，趋势是明确的。

<details><summary>Original English</summary>

But overall, the trend is clear.
</details>

我们系统性地增加了我们在有生之年所能获得的心跳次数，以至于现在的普通人在去世前能获得接近三十亿次心跳。

<details><summary>Original English</summary>

We have systematically

been increasing the number

of heartbeats we get in

our lifetime to the point

where now the average human

gets nearly three billion

heartbeats before they die.
</details>

我不知道还有没有比这更有利于科学和技术的论据了。

<details><summary>Original English</summary>

I don't know if there's a

better argument for science

and technology than this.
</details>

它实实在在地赋予了普通人超过一整条额外的生命。

<details><summary>Original English</summary>

It has literally given the average human

more than a full extra life.
</details>

而且不仅是人类。其他哺乳动物在圈养环境下，当远离它们在野外自然会遭遇的危险时，也被观察到拥有长得多的寿命。

<details><summary>Original English</summary>

And it's not just humans.

Other mammals have been observed

to have much longer lives in

captivity when they're away

from the hazards they would

naturally encounter in the wild.
</details>

或者，如果你纯粹从我们获得的年数来看，我们现在的寿命堪比大得多的哺乳动物，介于大象和鲸鱼之间。

<details><summary>Original English</summary>

Or if you look at it purely

from the number of years we get,

we now have the lifespan

of a much larger mammal,

somewhere between an elephant and a whale.
</details>

但关于这种趋势，有一件耐人寻味的事。

<details><summary>Original English</summary>

But there is one curious

thing about this trend.

(mellow music)
</details>

看一看这张图表。它看起来与之前的那张图表惊人地相似。

<details><summary>Original English</summary>

Take a look at this graph.

It looks surprisingly similar

to the graph from before.
</details>

事实上，如果你把它们叠合在一起，它们看起来显著相似。

<details><summary>Original English</summary>

In fact, if you overlay them,

they look remarkably similar.
</details>

现在我想让你猜一猜这张图表是什么。

<details><summary>Original English</summary>

Now I want you to take a

guess at what this graph is.
</details>

你有答案了吗？

<details><summary>Original English</summary>

Have you got your answer?
</details>

它是生活在城市中的人口数量。

<details><summary>Original English</summary>

It is the number of

people living in cities.
</details>

对于这两张图表，我们使用的是英国部分地区的数据，那里的记录可以追溯到几个世纪前，但世界其他地区也遵循了类似的趋势。

<details><summary>Original English</summary>

For these two charts,

we're using data from parts

of the United Kingdom

where the record keeping

goes back several centuries,

but the rest of the world

has followed similar trends.
</details>

当然，这并不意味着城市导致人们活得更长，但它与将城市视为充满污染和疾病滋生地的看法相悖。

<details><summary>Original English</summary>

Of course, that doesn't mean

cities cause people to live longer,

but it goes against the

perception of cities

as being full of pollution and

breeding grounds for disease.
</details>

早在 1889 年，一位医生就写道：

“城市的有毒病菌和污染，其不洁的空气和水源，糟糕的下水道系统，以及无休止的公害。”

<details><summary>Original English</summary>

Already in 1889, a medical doctor wrote,

"The poisonous germs and

pollutions of the city,

it's impure air and water, bad sewage,

and endless nuisances."
</details>

那么你如何调和这两种观点呢？或者更具体地说，关于较小城市与较大城市相比究竟如何，是否存在任何定量数据？

<details><summary>Original English</summary>

So how do you reconcile these two views?

Or more specifically, is

there any quantitative data

on how smaller cities

compare to larger ones?
</details>

### 城市的缩放法则

- 事实证明，这是杰弗里·韦斯特（Geoffrey West）在与布朗（Brown）和恩奎斯特（Enquist）合作之后所探究的课题。他和路易斯·贝当古（Luis Bettencourt）等人等合作者一起研究了城市中的缩放法则。

<details><summary>Original English</summary>

- It turns out this is something

that Geoffrey West pursued

after his work with Brown and Enquist.

He and collaborators like

Luis Bettencourt and others

have looked at scaling laws in cities.

(mellow music)
</details>

- [主持人] 他们观察了随着城市人口增加，像犯罪量等不同属性是如何缩放的。他们发现，如果你在双对数坐标图上绘制严重犯罪，数据会聚集在一条斜率为 1.15 的直线周围，这意味着犯罪的增长快于线性，即超线性增长。

<details><summary>Original English</summary>

- [Host] They looked at

how different properties

like the amount of crime scale

as the population of the city increases,

and what they found is that if you plot

serious crimes on a log log plot,

the data clusters around a straight line

with a slope of 1.15,

meaning crime grows faster

than linear or super linear.
</details>

因此，城市人口每翻一番，你就会得到大约 2.2 倍的刑事案件，或者说大约多出 120% 的犯罪，而不是你天真以为的 100%。

<details><summary>Original English</summary>

So for every doubling

of a city's population,

you get around 2.2 times

as many criminal cases

or around 120% more crime

as opposed to the 100%

you might naively expect.
</details>

更糟糕的是，研究人员发现同样的总体模式也适用于废水量，甚至艾滋病病例数量。

<details><summary>Original English</summary>

To make matters worse, researchers found

that the same general pattern

holds for the amount of wastewater

and even the number of AIDS cases.
</details>

确切的指数略有不同，但总体而言，随着城市规模的扩大，这每一项你系统性地都会得到更多。

<details><summary>Original English</summary>

The exact exponents vary a little,

but overall, as cities grow larger,

you systematically get more of each.
</details>

所以看来那位医生确实说到了点子上。你可能会认为如果我们全都在小城镇生活，地球上的生活或许会更好，但情况可能并非如此。

<details><summary>Original English</summary>

So it seems like that medical

doctor was onto something.

And you might think life on

earth would be better off

if we all lived in small towns instead,

but that might not be the case.

(mellow music)
</details>

2006 年，德克·赫尔宾（Dirk Helbing）、克里斯蒂安·库纳特（Christian Kuhnert）和杰弗里·韦斯特研究了加油站数量如何作为人口的函数进行缩放。

<details><summary>Original English</summary>

In 2006, Dirk Helbing, Christian Kuhnert,

and Geoffrey West looked at how the number

of gas stations scales as

a function of population.
</details>

- 如果一座城市规模大一倍，它是否需要两倍那么多的加油站？因为，你知道，我们必须供应的虽不完全算是营养物，但也是能源、汽油，供所有那些汽车使用。

<details><summary>Original English</summary>

- If a city is twice as

big, does it need twice

as many gas stations?

Because, you know, we have to

supply not exactly nutrients,

but energy, gas, for all those cars.
</details>

- [主持人] 天真的预期是，如果汽车数量增加一倍，你就需要两倍的燃油量，因此加油站数量翻倍。

<details><summary>Original English</summary>

- [Host] The naive expectation is that

if you double the number of cars,

you're going to need to

double the amount of fuel,

so double the gas stations.
</details>

为了查明这是否属实，他们将数据绘制在双对数坐标图上，并发现了一条直线。

<details><summary>Original English</summary>

To find out whether this was true,

they plotted the data on a log log plot

and found a straight line.
</details>

但指数不是 1，而是大约 0.8。

<details><summary>Original English</summary>

But the exponent wasn't

one, it was about 0.8.
</details>

这意味着每一次翻倍，你只需要大约多出 74% 的加油站，这是一笔相当可观的节省。

<details><summary>Original English</summary>

This means that for every

doubling, you only need around 74%

more gas stations, which

is a decent savings.

(mellow music)
</details>

道路和电缆的数量也大致以相同的方式缩放。

<details><summary>Original English</summary>

The amount of roads and electrical cables

also scale in roughly the same way.
</details>

韦斯特在其书中给出的粗略数字是，它们的缩放指数都在 0.85 左右。

<details><summary>Original English</summary>

The rough figure that

West gives in his book

is that they all have scaling

exponents of around 0.85.
</details>

- 很有趣的是，有些东西我们是可以共享的，比如你可以在路上开车，我也可以。当属于共享资源时，是的，城市可以出奇地绿色环保。其论点在于，相比住在荒郊野外，城市甚至可以比你想象的还要环保。

<details><summary>Original English</summary>

- It is interesting

that some of the things

that we can share, like you can drive

on the road, but so can I.

When it's shared resources, yes,

cities can be surprisingly green.

The argument is that

cities can be even greener

than you might think than living out

in the middle of nowhere.
</details>

- 但城市拥有更大的益处。诸如总工资、GDP 和专利数量等事物都呈超线性缩放，其指数聚集在 1.15 左右，这意味着规模每翻一倍，每一项你就会多得到大约 120%。

<details><summary>Original English</summary>

- But cities have even bigger benefits.

Things like total wages, GDP,

and the number of patents

all scale superlinearly,

with exponents that cluster

somewhere around 1.15,

meaning that for every doubling in size,

you get around 120% more of each.
</details>

当你将一个比如 50,000 人的小镇与一个其规模 100 倍的城市进行比较时，所有这一切都会变得尤为显著，因为基础设施需求只需要增加大约 50 倍，而总工资、GDP、专利与发明，它们全部都会增加 200 倍。

<details><summary>Original English</summary>

All of this becomes especially significant

when you compare a small

town of say 50,000 people

to a city 100 times its size

because infrastructure needs

only need to go up by a factor

of about 50 while total wages,

GDP, patents and inventions,

they all go up by a factor of 200.
</details>

不幸的是，疾病和犯罪也同样按相同倍数上升。

<details><summary>Original English</summary>

Unfortunately, disease

and crime also go up

by the same factor.
</details>

或者这样来看，按人均计算，你只需要大约一半的基础设施，同时你能获得翻倍的所有社会经济因素。

<details><summary>Original English</summary>

Or look at it this way,

on a per person basis,

you'd only need about

half the infrastructure,

while you get double all

the socioeconomic factors.
</details>

所以城市不仅没有对世界有害，它们实际上可能是我们最伟大的发明之一，也是很多科学和技术进步的间接推动力。

<details><summary>Original English</summary>

So cities far from being

detrimental to the world,

they might actually be

one of our best inventions

and an indirect driver

of a lot of scientific

and technological progress.
</details>

也许这也是为什么人们常说城市里的生活感觉更快。

<details><summary>Original English</summary>

Perhaps this is also why people often say

that life in the city feels faster.
</details>

这种感觉似乎是有道理的，因为研究人员调查了人们在不同规模城市中的步行速度。他们发现，在较大的城市里，人们的步行速度确实更快。

<details><summary>Original English</summary>

A feeling that seems justified

because researchers looked at

how fast people walk in

cities of different sizes.

And they found that

people literally do walk

faster in larger cities.
</details>

- 事实证明那取决于城市规模。不仅仅是人行道拥堵与否的问题。就是那种氛围会让人们亢奋起来。他们在城市里行动得更快。

<details><summary>Original English</summary>

- That turns out to depend on city size.

It's not just that the

sidewalks are congested or not.

It's just like the vibe

gets people amped up.

They move faster in cities.
</details>

- 因此生活的节奏似乎正在加快，但这可能要付出代价，因为正如有人所说的那样：

“如今的一切都走向极端。无论在思想上还是在行动中，一切都在不断被超越。没有人再了解自己。年轻人在生命中过早地被煽动，随后被时代的浪潮卷走。财富与迅速是世人所崇拜的。”

<details><summary>Original English</summary>

- So the pace of life

seems to be increasing,

but that may come at a cost

because as one person put it,

"everything nowadays is ultra.

Everything is being

transcended continually

in thought as well as in action.

No one knows himself any longer.

Young people are stirred

up much too early in life

and then carried away in

the world of the times.

Wealth and rapidity are

what the world admires".
</details>

难道生活正在以人类无法跟上的速度加速吗？

<details><summary>Original English</summary>

Could it be that life

is accelerating so fast

that humans won't be able to keep up?
</details>

嗯，很可能不是，因为这段名言是沃尔夫冈·冯·歌德在 1825 年写的。

<details><summary>Original English</summary>

Well, probably not

because this quote was written in 1825

by Wolfgang von Goethe.
</details>

在过去的 200 年乃至可能更长的时间里，几乎每一代人都觉得生活在加速。然而每一代人都挺过来了。

<details><summary>Original English</summary>

For the past 200 years

and probably longer,

almost every generation has

felt like life was accelerating.

And yet every generation has managed.
</details>

所以我认为我们很可能会无限期地继续适应下去。随着城市规模的不断扩大，我们所有人都会继续获取规模经济的益处，这与哺乳动物从体型变大中获益的方式非常相似。

<details><summary>Original English</summary>

So I think it's likely we can continue

to adapt indefinitely.

And as cities continue to grow in size,

all of us will continue

to reap the benefit

of economies of scale in much the same way

that mammals benefit from being larger.
</details>

### 对标度理论与克莱伯法则的质疑

但是，虽然 WBE 理论似乎能预测生物缩放法则中的指数从何而来，对于城市而言，目前还没有普遍接受的解释性理论。

<details><summary>Original English</summary>

But while WBE Theory seems to predict

where the exponents in

biological scaling laws come from,

for cities, there is no widely accepted

explanatory theory yet.
</details>

试图解释那些 0.85 和 1.15 的指数从何而来，是理论家们的主要目标之一。

<details><summary>Original English</summary>

Trying to explain where

those exponents of 0.85

and 1.15 come from is one of

the big goals for theorists.
</details>

尽管即使是 WBE 理论也并非被普遍接受。

<details><summary>Original English</summary>

Although even WBE Theory is

not universally accepted.
</details>

其一，它预测出正确指数这一事实并不一定意味着该理论本身就是正确的。还有少数其他理论也能预测出部分相同的缩放指数，而且也存在一些其他的批评意见。

<details><summary>Original English</summary>

For one, the fact it

predicts the right exponents

doesn't necessarily mean the

theory itself is correct.

There are a few other

theories that predict

some of the same scaling exponents,

and there are also some other critiques.
</details>

- 有很多讨论。它看起来可能很有说服力。就我个人而言，我倾向于认为它非常令人印象深刻。但我有非常优秀的同行，比如佛蒙特大学的彼得·多兹（Peter Dodds），他认为很多数据分析要么做得并不完全正确，要么数据噪声太大，以至于你真的不应该对此太当真。

<details><summary>Original English</summary>

- There's a lot of discussion.

It may look convincing.

And personally, I tend to

think it is very impressive.

But I have very good

colleagues like Peter Dodds

at University of Vermont,

and he thinks that a

lot of the data analysis

is either not done exactly right

or that the data are so noisy

that you shouldn't really

take this so seriously.
</details>

- 多兹甚至认为克莱伯法则（Kleiber's Law）本身可能都不是真实的。

<details><summary>Original English</summary>

- Dodds even argues that Kleiber's Law

itself might not be true.

(mellow music)
</details>

- 在 1960 年代，有一个关于能量代谢的研讨会，类似于动物中的此类名称，在会议结束时，他们以 29 票对 0 票表决通过定为四分之三，对吧？因为，你知道，你总得定下一些规则。如果你回头去看数据，现在其实已经没人真正这么做了，对吧，数据是行不通的。就是行不通。

<details><summary>Original English</summary>

- In the 1960s, there's a

symposium on energy metabolism,

some name like this in animals,

and at the end of it, they vote 29 to zero

that it's going to be

three quarters, right?

Because, you know, you

got to set some rules.

If you go back and look at the data,

which no one is really

doing anymore, right,

the data does not work.

Like it doesn't work.

(mellow music)
</details>

- [亨利] 这是一张基于一项考察了 391 种哺乳动物的研究绘制的代谢率作为质量函数的图表，其范围远大于克莱伯的范围。看起来四分之三的斜率拟合得相当好。

<details><summary>Original English</summary>

- [Henry] This is a

graph of metabolic rate

as a function of mass based on a study

that looked at 391 species of mammals,

much larger than Kleiber's range.

And it looks like the three-quarter

slope fits quite well.
</details>

但这只是图表的顶部部分，即最大的哺乳动物。

<details><summary>Original English</summary>

But this is just the

top part of the chart,

the biggest mammals.
</details>

如果你缩小视图，你会看到其余的哺乳动物似乎落在一条更接近三分之二的线上。而在近期关于鸟类代谢的研究中，你也会发现斜率看起来更接近三分之二，而不是四分之三。

<details><summary>Original English</summary>

If you zoom out, you see that

the rest of the mammals appear

to fall on a line that's

closer to two-thirds.

And in recent studies of bird metabolism,

you also find a slope that appears closer

to two-thirds than three-quarters.
</details>

难道几个世纪前那些法国科学家是对的，代谢率真的仅仅与表面积成比例缩放吗？

<details><summary>Original English</summary>

Could it be that those French scientists

from centuries ago were right,

that metabolic rate really does

just scale with surface area?
</details>

嗯，别高兴得太早。

<details><summary>Original English</summary>

Well, not so fast.

(mellow music)
</details>

首先，许多近期针对冷血动物的研究发现，其斜率显著高于三分之二。

<details><summary>Original English</summary>

For one, many recent studies

of cold-blooded animals find slopes

that are significantly

higher than two-thirds.
</details>

更大的问题在于测量代谢率本身就很困难。

<details><summary>Original English</summary>

The bigger problem is that measuring

metabolic rates is difficult.
</details>

它通常涉及将动物放入容器中，并对其产热量或耗氧量进行非常精确的测量，同时还要确保该动物处于无压力、低活动的静息状态。

<details><summary>Original English</summary>

It generally involves putting

animals in a container

and taking very precise measurements

of their heat production

or oxygen consumption,

all while ensuring that the

animal is in an unstressed,

low activity resting state.
</details>

不出意料，这对于大型动物来说尤其难以实现。

<details><summary>Original English</summary>

Unsurprisingly, this is

particularly difficult

to pull off with large animals.
</details>

结果，许多研究发现的缩放指数，其误差线同时包含了三分之二和四分之三。

<details><summary>Original English</summary>

And as a result, many studies

have found scaling exponents

where the error bars include both

two-thirds and three-quarters.
</details>

今天，研究界存在分歧。许多人坚持克莱伯法则和四分之三的缩放关系，而另一些人则认为是三分之二。

<details><summary>Original English</summary>

Today, the research community is split.

Many uphold Kleiber's Law and

the three-quarter scaling,

while others think it's two-thirds.
</details>

但越来越多的人怀疑，并不存在贯穿所有生命的统一缩放指数。

<details><summary>Original English</summary>

But a growing number suspect

that there is no

universal scaling exponent

across all of life.
</details>

事实上，情况很可能确实是：较大哺乳动物的代谢率按其质量的四分之三次方缩放，而对于较小的哺乳动物，则是其质量的三分之二之方。

<details><summary>Original English</summary>

In fact, it may very well be the case

that the metabolic rate of larger mammals

scales as their mass

to the three-quarters,

while for smaller ones, it's

their mass to the two-thirds.
</details>

- 你知道，这就像科学中的一切一样，有人在争论，这挺好的。

<details><summary>Original English</summary>

- You know, it's like

everything in science

that there are people

arguing, and that's good.
</details>

- 我想更大的呼吁是有人去真正地测量它，漂亮地测量事物。你知道，我们身处 2026 年，不能只是某个动物园里的一头大象，需要再次被非常严谨地测量。

<details><summary>Original English</summary>

- I guess the bigger exhortation

would be someone to really measure it,

measure things beautifully.

You know, we're in 2026,

has to be not just one

elephant at one zoo,

it needs to be measured again really well.
</details>

- [主持人] 每个人确实都同意的是

<details><summary>Original English</summary>

- [Host] What everyone does agree on
</details>

<!-- chunk 4/4 -->

规模法则是真实存在的。

<details><summary>Original English</summary>
is that scaling laws are real.
</details>

- 生活并非总是线性的。

<details><summary>Original English</summary>
- Life is not linear all the time.
</details>

这其中是大有益处的。在现实生活中，往往存在背离正比例关系的情况，你必须意识到这一点。有时事物能够发挥超出其体量的作用，而且随着体型变大，效率也会变得更高。有时体型变大也会带来劣势。

<details><summary>Original English</summary>
There are deals to be had.

There's often in real life

departures from proportionality,

and you have to be aware of it.

Sometimes things punch above their weight,

and as you get bigger,

you get more efficient.

Sometimes there are detriments to size.
</details>

- 所以，了解事物如何按比例缩放是大有裨益的。

<details><summary>Original English</summary>
- So it pays to know how things scale.
</details>

显然，从能量效率的角度来看，动物体型更大是有好处的。同样地，更多人生活在更大的城市里，我们所有人可能也都有望从中获益。这可能会带来更多的发现与发明，并以此提高我们所有人的生活水平，甚至可能让我们在有生之年拥有更多的心跳次数。

<details><summary>Original English</summary>
Clearly from an energy

efficiency perspective,

animals benefit from being larger.

Similarly, all of us potentially stand

to gain from having more

people living in larger cities.

It could lead to more

discoveries and inventions,

and in doing so, improve

the standard of living

for all of us, which

might even give us more

heartbeats in our lifetimes.
</details>

从表面积定律到克莱伯定律，再到 WBE 理论，代谢率如何随质量成比例变化，数百年来一直是生物学界最大的争论之一。通过收集更优质的数据并仔细分析，下一代研究人员很有可能最终为这场争论画上句号。这可能是正在观看视频的你们中的一员，也可能是你认识的一名学生。

<details><summary>Original English</summary>
From the surface law to

Kleiber's law to WBE theory,

how metabolic rate scales with mass

has been one of biology's

biggest debates for centuries.

By collecting better data

and analyzing it carefully,

there's a good chance

that the next generation of

researchers could be the ones

to finally put this debate to rest.

It could be one of you watching

or a student that you know.
</details>

### 赞助商信息

今天的赞助商 Brilliant 正助力培养下一代研究人员，训练他们的思维，以应对未来将面临的重大问题。Brilliant 是一款前沿的个人导师工具，帮助任何学生在数学、科学和编程方面取得优异成绩。

<details><summary>Original English</summary>
And today's sponsor, Brilliant, is helping

to train the next

generation of researchers,

preparing their minds to solve the huge

questions they'll face.

Brilliant is a cutting edge personal tutor

that helps any student excel

in math, science, and coding.
</details>

说到学习，一对一辅导确实是黄金标准，但这可能费用昂贵且在安排上面临困难。作为替代方案，学生们常常转向人工智能寻求指导。但大多数 AI 平台只是直接给出答案，反而阻碍了学习。因此，Brilliant 的设计初衷则是通过提出启发性问题并一步步拆解问题，引导学生迎来属于他们自己的恍然大悟时刻。

<details><summary>Original English</summary>
When it comes to learning,

one-on-one tutoring really

is the gold standard,

but this can be expensive

and logistically difficult.

As a substitute, students

often turn to AI for guidance.

But most AI platforms hinder learning

by simply just giving away the answers.

So instead, Brilliant is

designed to guide students

to their own aha moments

by asking probing questions

and by breaking problems

down step by step.
</details>

例如，看看当我打开 Brilliant 关于旋转坐标的一堂课，并告诉它的辅导工具我遇到了困难时发生了什么。它向我提出了一个具体的跟进问题，甚至在图表上标出了相关点来给我提示。

<details><summary>Original English</summary>
For instance, check out what

happened when I launched one

of Brilliant's lessons

on rotating coordinates

and told its tutoring tool

that I was struggling.

It asked me a specific follow-up question

and even labeled relevant

points on the graph

to give me a nudge.
</details>

对于你生活中学习数学和科学的年轻人来说，Brilliant 是一件极好的辅助工具。这是我上学时就希望能拥有的一类工具。因此，点击下方链接或扫描二维码即可免费开始体验 Brilliant 的导师功能，或者升级至高级会员解锁所有课程。目前，Veritasium 的观众在 brilliant.org/veritasium 订阅年度会员可享 20% 的优惠折扣。

<details><summary>Original English</summary>
Brilliant is an excellent

aid for the young math

and science learners in your life.

It's the kind of tool I wish

I had when I was in school.

So click the link below

or scan the QR code

to get started with

Brilliant's tutor for free,

or upgrade to premium

to unlock all courses.

And right now, Veritasium

viewers can save 20% off

an annual subscription at

brilliant.org/veritasium.
</details>

所以我想感谢 Brilliant 赞助本期视频，也非常感谢大家的观看。

<details><summary>Original English</summary>
So I want to thank Brilliant

for sponsoring this video,

and I want to thank you for watching.
</details>