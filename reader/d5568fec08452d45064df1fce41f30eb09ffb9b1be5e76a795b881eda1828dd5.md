---
author: Veritasium
date: '2021-05-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=OxGsU8oIWjY
speaker: Veritasium
tags:
  - infinity
  - hilbert-hotel
  - set-theory
  - countable-uncountable
  - cantor-diagonalization
title: 希尔伯特旅馆悖论：无穷的数学奥秘与层级
summary: 本视频通过希尔伯特旅馆的经典思想实验，生动解释了无穷的概念及其不同层级。从可数无穷如何容纳新客人，到不可数无穷如何超越可数无穷的极限，视频揭示了集合论中关于无穷大小的深刻洞见，并引入了康托尔对角线论证，阐明了为何无穷并非单一概念，以及不同无穷之间的层级差异。
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
### 希尔伯特旅馆：可数无穷的接待之道

想象一间拥有**无穷个客房**（Infinite Rooms）的旅馆，其房间号从1开始，依次递增至无穷。这家**希尔伯特旅馆**（Hilbert's Hotel）的**经理**（Manager），尽管看上去面临巨大的接待压力，却总有办法容纳下任何数量的客人。这里的关键在于理解**无穷**（Infinity）的概念，它并非简单的“多”，而是具有可扩展的数学特性。

起初，旅馆内每个房间都住着一位**客人**（Guest），所有**无穷个房间**（Infinite Rooms）都已满员。此时，如果来了一位新客人，传统的思维可能会认为无处可住。但对于熟悉**无穷**（Infinity）的经理而言，只需一个简单的广播就能解决问题：命令所有现有客人从当前的**房间号**（Room Number） `n` 搬到 `n+1` 号房间。这样，1号房间就空了出来，新来的客人得以入住。

这一策略还能扩展到更复杂的情况。例如，当一辆载有**100名客人**（100 Guests）的巴士抵达时，经理可以让每位现有客人从房间 `n` 搬到 `n+100` 号房间。这样，1号到100号房间就会腾空，为巴士上的所有乘客提供空间。

更具挑战性的是，当一辆**无穷长的巴士**（Infinitely long bus）载着**无穷个人**（Infinite Guests）到来时，问题似乎更加棘手。但经理依然有办法。这次，他要求现有客人从房间 `n` 搬到 `2n` 号房间。这意味着所有奇数号的房间都将空出来。由于**奇数**（Odd Numbers）本身也构成了一个**可数无穷**（Countable Infinity）的集合，巴士上的每位客人都可以被分配到一个独一无二的奇数房间。这个过程展示了**可数无穷**（Countable Infinity）的强大扩展性，证明了它能够容纳新来的、同为**可数无穷**（Countable Infinity）数量的群体。

### 派对巴士悖论：不可数无穷的极限

当情况变得更为复杂，比如出现了**无穷辆**（Infinitely many buses）载着**无穷个人**（Infinite Guests）的巴士时，旅馆经理需要更巧妙的方法。他可以构建一个**无穷×无穷的表格**（Infinite x Infinite table），其中行代表巴士，列代表座位，并将每个**巴士编号**（Bus Number）和**座位号**（Seat Number）的组合映射到一个唯一的**房间号**（Room Number）。通过一个巧妙的路径（如同在左上角开始，在表格中来回画一条不间断的线），可以将这张二维的无穷表格“拉直”成一根**无穷长的线**（An infinitely long line），从而为所有这些新的客人分配到独一无二的房间。这再次说明，**可数无穷**（Countable Infinity）的集合（所有巴士和座位的组合）是能够被酒店容纳的。

然而，故事并未就此结束。旅馆来了一辆特殊的**派对巴士**（Party bus），车上载有**无穷个人**（Infinite Guests），他们的名字并非数字，而是由字母**A**和**B**组成的**无穷长序列**（Infinitely long sequences）。例如，一位客人可能名叫 **ABBAAAAAAAAA...**（Infinite A's），另一位可能名叫 **ABABABAB...**。这代表了所有可能由**A**和**B**组成的**无穷序列**（Any infinite sequence），这是一个比**正整数**（Positive Integers）集合更“大”的无穷。

经理此时不得不告知派对巴士的代表：“我没法让你们全车的人统统住进旅馆。”尽管看起来旅馆有**无穷个房间**（Infinite Rooms），但这次的**乘客数**（Number of passengers）是**不可数无穷**（Uncountable Infinity），它超出了旅馆**可数无穷**（Countable Infinity）的容量。

为了证明这一点，经理使用了类似康托尔对角线论证（**Cantor's Diagonalization**）的方法。他设想，即使将所有派对巴士的乘客（每个人名都是一个无穷的AB序列）一一列在**无穷长的表格**（Infinite table）中，他也总能构造出一个新的、不在列表中的名字。这个新名字的生成方式是：取列表中第一个名字的第一个字母，将其**颠倒**（Flipped，A变B，B变A）；取第二个名字的第二个字母，同样颠倒；依此类推，沿**对角线**（Diagonal）上的字母进行操作。这样生成的新名字，必然与表格中的任何一个名字都至少在某一位上不同，因此这个新名字代表的乘客无法在旅馆中找到对应的房间。

这个悖论揭示了**无穷**（Infinity）并非一个单一的概念，而是存在不同“大小”的层级。**可数无穷**（Countable Infinity）的集合，如**正整数**（Positive Integers）或**所有巴士和座位号的组合**，其基数与自然数相同。而**不可数无穷**（Uncountable Infinity）的集合，如所有可能的**A/B无穷序列**，其基数则更大，无法与**正整数**（Positive Integers）一一对应。这深刻的数学探讨，甚至催生了我们今天观看视频的设备，展现了**无穷的大小**（Size of infinity）所蕴含的巨大理论力量。