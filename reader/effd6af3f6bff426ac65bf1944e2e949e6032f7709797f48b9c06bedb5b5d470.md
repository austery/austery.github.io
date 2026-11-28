---
author: Veritasium
date: '2026-05-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kS-CGkiPetQ
speaker: Veritasium
tags:
  - shortest-path-algorithm
  - graph-theory
  - navigation-system
  - pathfinding
  - computational-efficiency
title: 路径计算的演进：从 Dijkstra 到现代导航系统
summary: 本文详细解析了从经典的 Dijkstra 算法到现代地图导航系统所采用的各类路径查找算法的演进历程。文章深入探讨了 Dijkstra 算法的核心机制及其在处理大规模地理网络时的局限性，并介绍了 A* 搜索、双向搜索、分层路径处理及定制化收缩层次技术，解释了现代导航应用如何实现海量数据下的毫秒级路径计算。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - Apple
  - OpenStreetMaps
products_models:
  - Google Maps
  - ARMAC
media_books: []
status: evergreen
---
### 路径计算的起源与 Dijkstra 的构想

从纽约到旧金山，如何计算绝对最短路径？北美道路系统拥有超过 6400 万个交叉路口，这意味着可能的路线数量高达 10 的 220 次方。即使每秒能测试 10 亿条路线，也需要超过 10 的 200 次方年。这不仅是导航软件的问题，任何机器人或视频游戏角色在迷宫中导航时，都面临同样的困境。然而，Google 或 Apple 地图却能在四秒内找出路线，这背后的算法演进要追溯到 1956 年阿姆斯特丹的一次购物旅行。

Edsger Dijkstra 当时正在为 **ARMAC**（荷兰数学中心开发的早期计算机）编写软件。为了在那个公众认为计算机几乎毫无用处的年代展示 ARMAC 的强大，他需要一个非数学家也能理解的问题陈述及其答案。他想到了一个完美的问题：“从鹿特丹到格罗宁根的最短路径是什么？”这就是最短路径算法的诞生。

<details>
<summary>Original English Source</summary>

- [Derek] Say you wanna drive
from New York to San Francisco.
How could you calculate
the absolute shortest path?
There are over 64 million intersections
in the North American road system,
so a simplified estimate gives around
10 to the 220 possible routes.
Even if you could check a
billion routes per second,
testing all of them
would still take over 10 to the 200 years.
And this isn't just a problem
for navigation software.
Any independent system like a robot
or a video game character
that needs to navigate a maze,
or obstacle course
faces this same problem.
And yet, Google or Apple
Maps will find you the route
in only four seconds.
So how is that possible?
Well, we teamed up with the channel 2swap,
who creates incredible
simulations and animations
to show you step by step,
how these algorithms work.
They trace their origins
back to a shopping trip
in Amsterdam in 1956.
(jaunty music)
Edsger Dijkstra needed a problem.
He was working on software for ARMAC,
an early computer developed
at the mathematical center
in the Netherlands.
And it was almost ready to debut.
But at the time, the general
public considered computers
to be practically useless.
So useless, in fact,
that Dijkstra ran into issues
filing his marriage license.
- [Casper's Dijkstra Impression] 
Dutch marriage rights require you
to state your profession,
and I said that I was a programmer.
But the municipal authorities
of the town of Amsterdam
didn't accept it on the ground
that there was no such profession.
And believe it or not, that
under the heading "profession,"
my marriage act shows
the ridiculous entry,
"theoretical physicist."
- [Derek] And so Dijkstra was
looking for a specific demo
to prove just how powerful ARMAC
was, even to the layperson.
- ['Dijkstra'] The problem of course,
is that for a demonstration
for non-computing people,
you have to have a problem statement
that non-mathematicians can understand.
And they have to understand the answer.
- [Derek] And during that shopping trip,
he thought of the perfect problem.
- ['Dijkstra'] What's the shortest way
to travel from Rotterdam to Groningen?
</details>

### Dijkstra 算法与最优路径保障

在图论中，城市是节点，道路是边。最简单的路径查找方式是 **广度优先搜索**（Breadth-First Search: 按步长顺序遍历图的算法），它先检查距离源点一步的所有节点，再检查两步的，以此类推。虽然它能找到最短路径，但它假设所有道路长度相同，这显然与现实不符。

为了处理加权路径，Dijkstra 设计了一个更有效的方法。他的核心逻辑是追踪从源点到每个节点的“最短距离”（即成本）。如果他能找到从源点到一个节点的最短路径，就能以此构建通往下一个节点的最短路径。初始时，源点成本为零，其他所有节点成本为“无穷大”。算法从源点出发，探索邻居，若发现更短路径，则更新节点的成本。通过始终探索未探索节点中成本最低的一个，Dijkstra 的算法保证了能找到通往任何目标的最短路径。这完全无需纸笔，是一个仅仅 20 分钟的“即兴发明”，其核心优势在于强制避免了一切可避免的复杂性。

<details>
<summary>Original English Source</summary>

- [Derek] In other words,
a shortest path algorithm.
Here's a simplified
graph of the Netherlands.
The nodes represent the cities,
and the edges connecting
them are the roads.
The simplest way to find the shortest path
from Rotterdam to
Groningen looks like this.
Starting from Rotterdam,
we're first going to
explore all its neighbors
looking for Groningen.
Since Groningen isn't one
of these neighboring nodes,
we'll mark Rotterdam as
explored, and keep searching.
So now we'll branch out
from these four nodes
to explore all of their neighbors.
And we keep branching out this way,
exploring all neighboring nodes,
until we stumble upon Groningen.
This algorithm is known
as Breadth-First Search.
It will always find the shortest path
because it checks all nodes one step away,
and then two steps away, and so on.
So if there were a path
from Rotterdam to Groningen
in four steps,
we would've found it on the
fourth iteration, but we didn't.
So the shortest path must be five steps.
But there's a problem with this approach.
I mean, the algorithm
considers all these roads
to be the same length,
which is obviously not true.
So let's add weights
to represent distances
between these nodes.
Now the shortest path is
much harder to figure out.
So Dijkstra needed a better method.
- ['Dijkstra'] One morning I
was shopping in Amsterdam
with my young fiance, and tired,
we sat down on the cafe terrace
to drink a cup of coffee.
And I was just thinking about
whether I could do this.
- [Henry] His idea was this.
First he wanted to keep track
of the shortest distance
from the source to each node.
This is also known as its cost.
His goal, well, if he could
find the shortest path
from the source to one node,
then he could build up
other shortest paths
starting from this new node,
and then the next, and on and on.
Now, the cost of the
starting node was zero.
But since he hadn't actually explored
the rest of the graph yet,
he set all the other nodes
to a cost of infinity.
Then just like breadth-first search,
Dijkstra started from the source,
and explored each of
its neighboring nodes.
At every step he'd ask,
"Is the current path to this node
the shortest we've seen so far?"
For example, this edge
only has a weight of one,
while the node's current cost is infinity.
So this path is the
shortest yet to that node.
So Dijkstra updated its cost to one.
Likewise, these nodes were
updated to three, two, and four.
After checking all of
Rotterdam's neighboring nodes,
Dijkstra marked it as explored.
Then since this node had the lowest cost
out of all the unexplored nodes,
Dijkstra explored it next.
Like before, he checked each of its edges
to reduce the neighbor's costs.
Dijkstra could update this neighbor
from infinity down to six,
a total path length of five plus one,
but he couldn't update this one.
The current path has a cost of five,
but the nodes' cost was three.
That meant there was
already a shorter path,
this one directly from the source.
So there was no need to update the cost.
The next node to explore is
this one with a cost of two,
which would update its neighbor to five.
Then this one with a cost of three
would update its neighbors, and so on.
Sometimes Dijkstra had to update
a node's cost a few times.
For example, he first reached
this node through this path
with edge weights four, and then three,
for a total cost of seven.
But later he found this path was cost six.
So he updated the nodes cost again.
(gentle music)
The first time Dijkstra reached Groningen,
it had a cost of 19.
But it didn't have the lowest cost
out of all the unexplored nodes.
There was still this
node with a cost of 16,
which could be hiding a
shorter path to our goal.
So he continued exploring
nodes in cost order,
and found this path with cost 18.
Now, out of all unexplored nodes,
Groningen had the next lowest cost.
So Dijkstra was confident that
he'd found the shortest path.
Here's why.
If the lowest cost among
the unexplored nodes is 18,
then Dijkstra must have
explored all the paths
with cost 16, 14, 13,
every path less than 18.
And none of those paths reached Groningen.
It's just like breadth-first search,
searching every step away from the source.
By exploring from lowest to highest cost,
Dijkstra's algorithm
guaranteed the shortest path
to any target.
- ['Dijkstra'] It was a 20-minute invention.
I designed it without pencil and paper.
I learned later that one of the advantages
of designing without pencil and paper
is that you are almost forced
to avoid all avoidable complexities.
</details>

### Dijkstra 算法的工业应用瓶颈

Dijkstra 的算法被誉为最优雅的最短路径算法之一。在 ARMAC 的落成典礼上，它演示了按城镇打印最短路径的能力，运行完美。尽管如此，Dijkstra 算法对于现代的大规模地图应用（如 Google Maps）来说，效率仍然不足。

以从纽瓦克机场到中央公园动物园的旅程为例，Dijkstra 算法会按距离逐步检查所有的节点，其搜索范围会覆盖庞大的区域，包括完全偏离目标的地点（如斯塔滕岛）。虽然在单个城市内其运行时间极快，但在北美这样的大型网络中，一个优化良好的 Dijkstra 算法平均需要约 7 秒才能求出一条路径，且需要探索大部分 6400 万个节点。面对数百万用户同时请求路径规划，即使拥有庞大的服务器集群，也难以在毫秒级完成任务。我们需要比 Dijkstra 快 7000 倍以上的算法。

<details>
<summary>Original English Source</summary>

- [Derek] During ARMAC's
official inauguration in 1956,
Dijkstra asked the audience
members for two towns
on a simplified map of the Netherlands.
ARMAC then printed the
shortest route town by town.
It ran perfectly.
The computer was such a success
that the center immediately
started the next generation.
And as for his algorithm, well,
it just sat in his papers for years.
Algorithms weren't respectable enough
for mathematics journals,
and there weren't very many
computing journals yet.
But in 1959, he published his
work in Numerische Mathematik,
or Numerical Mathematics,
a brand new German journal
that needed some help getting established.
And that was the beginning.
- ['Dijkstra'] Eventually,
that algorithm became,
to my great amazement, one of
the cornerstones of my fame.
I found it in the early '60s
in a German book on management science,
Das Dijktra'sche Verfahren.
Suddenly there was a
method named after me.
Dijkstra's algorithm is still regarded
as one of the most elegant,
shortest path algorithms.
But it isn't good enough for Google Maps.
Let's say I want to get from
Newark Airport in New Jersey
over to the Central Park Zoo.
First, Dijkstra's algorithm
checks all the 10-kilometer journeys,
and then all the 20 kilometer journeys,
and so on until it reaches
all the 28 kilometer journeys,
which includes the zoo.
The search frontier
covers over 65,000 nodes,
and includes places that are way off,
like Staten Island, and
large swaths of New Jersey.
But even though it searched
in a illogical directions,
the runtime was about a 10th of a second,
which is incredibly fast.
...
- [Derek] Now less than 100 milliseconds
seems pretty fast.
So what's the problem?
Well, things slow down a lot
with bigger and bigger graphs.
Like the North America network.
One way we can compare search algorithms
is by their average query speed.
First we pick lots of random points.
Then we run Dijkstra's
algorithm on each pair of points
and average all the runtimes.
On the North American network,
a well-tuned Dijkstra takes
around seven seconds per path.
And for a lot of these searches,
the algorithm has to explore
most of those 64 million nodes.
...
- [Henry] And while Google has a lot
of servers, there's a limit.
If we want Google Maps to
run in a couple of seconds,
we actually need the algorithm
to run in less than a millisecond,
something 7,000 times
faster than Dijkstra's.
</details>

### A* 搜索与启发式路径优化

Dijkstra 的问题在于它会朝目标相反的方向进行搜索。**A-star** (A*) 算法通过引入 **启发式函数** (Heuristic: 用于加速搜索的估算函数) 解决了这个问题。它不再盲目探索，而是利用经纬度计算节点到目标的直线距离，并将其作为估算成本。在 3D 可视化中，这就像将图拉伸，越远离目标的地形越高，算法自然会惩罚向反方向移动。

通过这种方式，修改后的 Dijkstra（即 A-star）会直接导向目标，显著缩小搜索边界。虽然它在最坏情况下与 Dijkstra 效率相当，但在大多数情况下，它能大幅减少搜索的节点数。然而，针对不同优化目标（如“最短地理距离”与“最短旅行时间”），启发式函数的效果截然不同。对于旅行时间，该函数往往会导致 A-star 的搜索效率降低，甚至不如优化后的 Dijkstra。

<details>
<summary>Original English Source</summary>

(whooshing sound)
Well, one problem with Dijkstra's
is it searches in the opposite
direction of the target.
So if we know the rough direction,
is there a way that we can
punish a illogical route?
Let's go back to our problem,
getting from Newark to
the Central Park Zoo.
We'd like to prioritize nodes
that are closer to the zoo.
So using longitudes and latitudes,
we can easily calculate
the straight line distance
between any node and our target.
We'll order the nodes by their cost,
plus this straight line distance.
A great way to visualize this
comes from the channel Polylog.
We can represent each node's
straight line distance
to the target as its height,
so the graph stretches into 3D space.
The further a node is from
the zoo, the higher it is.
So the algorithm penalizes
moves that climb up the graph.
That way nodes in the opposite direction
aren't explored early on.
So while Dijkstra's search frontier
spreads out in all directions,
this modified Dijkstra's,
also called A-star,
immediately heads toward the zoo.
It only checks around 7,000 nodes,
which is almost a 10 times
improvement over Dijkstra's.
And by changing this penalty,
also called a heuristic,
we can tweak how aggressively
A-star targets the zoo.
...
- If you wanna go for the shortest path
in the sense that shortest
geographic distance,
you will gain some
advantages using A-star,
compared to Dijkstra.
If you go for travel time, A-star,
from my experience, loses
against a well-tuned Dijkstra.
You explore fewer nodes,
but not that many.
But you now also have to
evaluate quite a few heuristics
that you would not need to evaluate
when doing pure Dijkstra.
And those heuristic contain a
nasty square root computation.
</details>

### 双向搜索与基于分层的人为直觉

为了进一步提升性能，可以使用 **双向搜索**（Bi-directional search），即同时从源点和目标点出发进行搜索。两者的搜索前沿会在中间重合，从而将单向搜索覆盖的区域减半，甚至根据图的特性实现更好效果。

尽管如此，单纯的算法依然无法感知道路网络的“分层”本质（即人类在开车时会经历：本地小路 -> 高速公路 -> 本地小路）。在 90 年代的车载 GPS 中，通过人工预先将道路分层（如：高速公路、主要干道、窄路），并让算法在分层候选区域内进行搜索，可以实现极大的效率提升。然而，这种方法的局限在于：如果候选区域划分不当，算法可能会遗漏最短路径，且手动维护分层极其困难。

<details>
<summary>Original English Source</summary>

- [Henry] On our New York City graph,
Dijkstra's algorithm explored
around 9.5 times more nodes
than A-star, to find the
shortest path by distance.
But if we switch that to
the shortest travel time,
the number of nodes
A-star explores triples,
while Dijkstra only increases by 10%.
And it only gets worse on larger graphs.
So Google Maps need something better
that works well for travel time.
What if we ran the search
in both directions?
From the source to the target,
and from the target to the source?
If two points are a distance R away,
Dijkstra searches most of the nodes
roughly within a circle
of area pi R-squared.
But with two searches,
the frontiers will
overlap around R over two,
and cover an area of half pi R-squared,
half that of the single search.
And depending on the graph,
it can sometimes be better than half.
A basic Dijkstra search from
Carnegie Hall to Wall Street
explored over 7,200 nodes.
But a bi-directional Dijkstra
explored a little over 2,600 nodes,
close to a three times improvement.
But even a bi-directional
search doesn't take advantage
of the logic built into road networks.
- They still do things
that you wouldn't necessarily conceive
as a good idea, right?
...
- When I think about how to
get from one place to another,
I know that I'm probably
gonna meander around
some local roads, then hop on a highway,
and then when I'm close to my destination,
I'm gonna hop off the highway and meander
around some more local roads.
There's a hierarchy to road networks,
but these algorithms can't
take advantage of them.
...
- So here was the basic idea.
Surveyors would go out and
take notes about a road.
...
- Once it had the maps,
GPS would run a bi-directional Dijkstra,
but there was a catch.
It first searched all the narrow roads
within a candidate area.
If it didn't find the target,
it mapped the path to the next hierarchy,
the major local roads.
Then search all of the major local roads
within the new candidate area.
If it still didn't find the target,
it moved up again to the highway level.
The two searches would
overlap at some point,
and return the final path.
This way, a little pre-processing
could reduce the search area
and take advantage of the road hierarchy.
- One obvious downside here is that
how do you correctly compute
those levels of hierarchy?
And how can you prove to
yourself that they're correct
in the sense that you are not
missing any shortest paths?
</details>

### 定制化收缩层次与嵌套解剖

现代地图应用通常采用 **定制化收缩层次** (Customizable Contraction Hierarchies: 一种基于分层重要性排序的最短路径优化算法)，结合了预处理和自动化的道路分层。该算法通过 **嵌套解剖** (Nested Dissection: 通过递归切割图结构来对节点进行重要性排序的技术) 自动识别瓶颈路口并排序。

算法首先对节点按重要性（例如：是否连接高速公路）进行分层，并预先计算“快捷方式”（Shortcuts），以此跨越那些只需经过低等级道路的节点。虽然预处理耗时，但一旦完成，其查询性能极高。在实际测试中，这种方法能在北美网络上达到毫秒级的查询速度，探索节点数减少了 4 万多倍。这不仅极大地提升了效率，还通过快捷方式保证了绝对的最短路径，而无需依赖不准确的手动分层。

<details>
<summary>Original English Source</summary>

- [Derek] If Google wanted to map the world,
they need a better routing algorithm.
...
- The idea is very similar
to the manual hierarchies,
but with two major changes.
First, we'll automatically
pre-process our graph
to order nodes by how important they are.
...
- [Henry] These are the
biggest bottlenecks.
Out of all the 64 million plus nodes,
these 102 get the highest
rank, so the biggest numbers.
Now let's find the next
most important nodes.
...
- This is called nested dissection.
This pre-processing step has two goals.
...
- [Henry] To speed up the runtime,
we limit the search space by
only moving up the hierarchy.
And that's why it's so important
to use a bi-directional Dijkstra.
...
- [Henry] Start from the lowest rank.
Does this node connect to
at least two higher nodes?
On this graph, node one
connects to three and eight.
This is called a lower triangle.
And while there's a chance this path
is actually the shortest between
node three and node eight,
our search will never consider it.
So we'll add a shortcut between
nodes three and node eight.
That's just the cost
of this lower triangle.
...
- [Derek] This entire algorithm is called
a customizable contraction hierarchy.
...
Finally, phase
three is the actual search.
Remember, for a long path on
the North American network,
a well-tuned Dijkstra needs to explore
most of the 64 million nodes
and takes around seven seconds per path.
For this contraction hierarchy,
the query runtime was
around 200 microseconds.
</details>

### Dijkstra 的持久遗产与简单之道

Dijkstra 算法依然是许多现代最短路径算法的基石，无论是从收缩层次的变化，还是最新的理论突破，都依然能见到其影子。其持久成功的部分原因在于它的简单性，正如 Dijkstra 本人所言：“简单性是可靠性的先决条件。”

他深思熟虑，直到动笔前都始终保持严谨。他希望留下这样一份遗产：当未来的程序员在编写“快速且草率”的代码时，能隐约意识到他在“俯视着他们”，并意识到“Dijkstra 不会喜欢这样”。这种精神激励着人们在自己的领域内，通过逻辑和严谨，追求优雅与简洁，不仅为了自己，也为了后来者。

<details>
<summary>Original English Source</summary>

- [Derek] ...But if you think about it,
its core search is still
Dijkstras, a 70-year-old algorithm.
Four decades after
Dijkstra publishes article,
Danish computer scientist Mikkel Thorup
said that all theoretical developments
in single source shortest paths
have been based on Dijkstra's algorithm.
And since 2000, many of the
newest shortest path algorithms
still use bits and pieces of Dijkstras.
From variations on
contraction hierarchies,
all the way to a recent
theoretical breakthrough
for an even faster
shortest path algorithm.
All of this, based on
a 20-minute invention.
Part of Dijkstra's enduring success
comes down to just how simple it is.
As he said, "Simplicity is
prerequisite for reliability."
Dijkstra thought deeply about problems
before ever touching a pen.
Because at the end of the
day, it would be a programmer
who is accountable for
their work, not the machine.
...
- [Derek] So with those two ideas,
he hoped to have one lasting legacy.
He said, "If 10 years from now,
when you're doing
something quick and dirty,
you suddenly visualize that I'm here,
looking over your shoulders,
and say to yourself,
'Dijkstra would not have liked this.'
Well, that'd be enough
immortality for me."
So even if you can only control
your little corner of the world,
you can still make it as elegant
and thoughtful as possible.
For you, and all the
people who come after.
</details>