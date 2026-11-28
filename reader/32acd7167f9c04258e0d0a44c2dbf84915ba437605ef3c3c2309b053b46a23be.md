---
author: AI Engineer
date: '2026-09-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=eZ8WWZzoaR0
speaker: AI Engineer
tags:
  - tail-latency
  - network-transport
  - congestion-control
  - ai-workload
title: Homa：面向AI工作负载的低尾延迟数据中心传输协议
summary: 演讲者称AI工作负载正从大块传输转向对延迟敏感的小消息交换，TCP与RDMA在混合大小消息时尾延迟很高；他介绍斯坦福开发的Homa，并称其可将尾延迟降低一个数量级或更多。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 开场与演讲目标
<details>
<summary>Original English</summary>
[music]

Please welcome to the stage the professor emmeritus at Stanford University, John Sterhout.
</details>

[音乐]

有请斯坦福大学荣休教授 John Sterhout 上台。

<details>
<summary>Original English</summary>
Good morning. It's really great to be here to talk about the network side of AI applications and in particular to make the case that latency matters and it's probably going to be mattering more in the future. But I just want to say this is a talk is unusual for me. I've never before given a talk where there are fog generators in the auditorium. Just a really San Francisco experience, I guess.
</details>

大家早上好。很高兴来到这里，谈谈AI应用的网络层面，尤其是要论证：延迟很重要，而且未来可能会越来越重要。不过我想说，这次演讲对我来说不同寻常。我以前从没在有烟雾机的礼堂里做过演讲。我想，这真是很旧金山的体验。

<details>
<summary>Original English</summary>
So, it's it's well known that AI workloads depend on really great networking performance in order to achieve their own performance. And of course, that's because the workloads are so large that they have to be distributed across machines and then you have to communicate between the machines. But what I want to talk about today is that it seems that those workloads are changing. And so I hope to do three things over the next 15 or 20 minutes. First to convince you that in fact the workloads are changing and that whereas the workloads used to be completely dominated by large transfers where throughput is the key metric that matters that we're seeing more and more smaller transfers where the latency is crucial.
</details>

众所周知，AI工作负载要达到自身的性能，依赖于非常出色的网络性能。当然，这是因为这些工作负载规模太大，必须分布到多台机器上，机器之间就需要通信。但我今天想谈的是，这些工作负载似乎正在发生变化。所以我希望在接下来的15到20分钟里做三件事。第一，说服你们：工作负载确实在变化。过去它们完全由大块传输主导，吞吐量是关键指标；而现在我们看到越来越多的小规模传输，延迟至关重要。

<details>
<summary>Original English</summary>
The second thing I hope to do is to convince you that legacy protocols like TCP and RDMMA are poorly suited to this environment. They weren't designed for this environment and unfortunately they suffer from very high tail latency when you mix small messages with large ones. I'll talk a little bit about why that's the case. Then third, I'd like to introduce Homo which is a new protocol we've developed at Stanford that actually was designed in a clean slate redesign to handle data center workloads like these and in fact it does quite well on those workloads and can reduce tail latency by an order of magnitude or more. So I'll tell you a little bit about Homa. So let's dive in.
</details>

第二，我希望说服你们：TCP 和 RDMMA 这类传统协议并不适合这种环境。它们不是为这种环境设计的，不幸的是，当小消息和大消息混合时，它们的尾延迟会非常高。我会简单讲讲原因。第三，我想介绍 Homo（即 Homa），这是我们在斯坦福开发的一种新协议，它是通过推倒重来的全新设计，专门用来处理这类数据中心工作负载的；事实上它在这些工作负载上表现相当不错，可以把尾延迟降低一个数量级或更多。我会稍微讲一讲 Homa。那我们开始吧。

### 工作负载的变化
<details>
<summary>Original English</summary>
First, workloads. Historically, AI workloads have consisted of enormous transfers between machines, and that's all that really mattered. Gigabytes of data for things like weight gradients and and so on.

In these workloads, what you really care about is throughput, how many gigabits per second you can pump through the pipes. And these are relatively easy workloads for networks because if it takes a while to set up the connection and start the transfer, it doesn't matter. The transfers go on for so long that all that really matters is the throughput. And so in these environments, TCP and RDMA perform pretty well. Uh, by the way, when I say RDMA, what I really mean is Rocky RDMA over converged Ethernet, which is the underlying transport that's used by RDMA for most purposes today. So anyhow, the old workloads, big transfers, throughput matters, uh the legacy protocols work pretty well.
</details>

首先谈工作负载。历史上，AI工作负载由机器之间的巨大传输组成，真正重要的只有这一点：比如权重梯度之类的数据，规模达到千兆字节。

在这些工作负载中，你真正关心的是吞吐量，也就是每秒能通过管道推送多少吉比特。对网络来说，这些是相对容易的工作负载，因为建立连接、开始传输花点时间也无所谓。传输持续很长时间，真正重要的只有吞吐量。所以在这些环境中，TCP 和 RDMA 表现相当不错。顺便说一下，我说的 RDMA，实际指的是 Rocky，即 RDMA over converged Ethernet，它是目前 RDMA 在大多数用途中使用的底层传输。总之，旧的工作负载是大传输、吞吐量最重要，传统协议运行得相当好。

<details>
<summary>Original English</summary>
However, it appears that the workloads are changing. They're becoming more granular with smaller chunks of computation and smaller exchanges of data. And this seems to be particularly true in the world of inference and also in agentic workloads. Not so much for training workloads are still massive transfers. And so what's happening is that more and more there are small message exchanges typically for things like metadata and coordination such as checking to see if a particular entry is present in a KV cache that's distributed or doing barrier synchronization at the end of periods of compute. And for these workloads what really matters is latency. That is what's the roundtrip time to send some small piece of data across the network do a little bit of computation and get a small result back again. And in fact, it isn't just just latency or average latency that matters. What really matters is tail latency. That is, you'd like to know that if we send a whole lot of small messages, all of them will complete quickly. So, for example, we typically measure things like 99th percentile latency. And if we have high tail latency, that can limit the overall throughput of the system.
</details>

然而，工作负载似乎正在变化。它们变得更细粒度，计算块更小，数据交换也更小。这在推理领域和智能体（agentic）工作负载中似乎尤其明显；训练工作负载则不然，仍然是大规模传输。于是，越来越多出现的是小消息交换，通常用于元数据和协调，例如检查某个条目是否存在于分布式 KV cache 中，或者在计算阶段结束时做 barrier 同步。对这些工作负载，真正重要的是延迟，也就是把一小块数据通过网络发出去、做一点计算、再收回一个小结果的往返时间。事实上，重要的不仅仅是延迟或平均延迟，真正重要的是尾延迟。也就是说，你希望知道：如果我们发送大量小消息，它们都会很快完成。例如，我们通常测量第99百分位延迟。如果尾延迟很高，就可能限制系统的整体吞吐量。

<details>
<summary>Original English</summary>
So, here's an example.

Suppose a common thing is to take a workload and split it up across several nodes which do intensive computation using their GPUs for some period of time and then once they've all finished their computation you do some small exchange between the nodes exchange data meta data and then it'll go on to the next round of computation

and while that exchange is happening that synchronization is happening the GPUs are sitting idle

so if even one of those exchanges takes a long time. It turns out the whole process stalls. You need all of those exchanges to complete before you can go on to the next phase of computation.

Now, if the computation phase is say 5 seconds and it takes a few milliseconds for the exchange, you know, not a not a problem. And that's historically what it's been. But now with agentic workloads where you're trying to pump out tokens relatively rapidly at a regular rate, the periods of computation are getting down into sort of the millisecond time scale. And if it also takes milliseconds to do that synchronization, then you're wasting a significant fraction of your GPU resources waiting for the the synchronization to occur. So I'm curious. I'd like to just do a a quick audience poll here. Is there anybody here where you have reason to believe that the latency of small messages is impacting the overall throughput of your applications? If so, can you just raise your hand? See, is there anybody out there today? Actually, more hands than I expected. So quite a few people out there are raising their hands. I think this problem is likely to get worse as the trends continue.
</details>

举个例子。

常见的做法是把一个工作负载拆分到多个节点上，这些节点用各自的GPU在一段时间内做密集计算；等它们全部算完之后，节点之间做一次小的交换，交换数据和元数据，然后进入下一轮计算。

在这次交换、也就是同步进行的时候，GPU是闲置的。

所以哪怕其中一次交换耗时很长，整个过程也会停滞。你需要所有这些交换都完成，才能进入下一阶段的计算。

现在，如果计算阶段是比如5秒，而交换只需几毫秒，那不成问题，历史上一直就是这样。但现在有了智能体工作负载，你要以相对较快的固定速率输出 token，计算周期已经降到毫秒级的时间尺度。如果做同步也要几毫秒，那么你就会把相当大一部分GPU资源浪费在等待同步完成上。我很好奇，想在这里快速做个观众调查：在座有没有人有理由相信，小消息的延迟正在影响你们应用的整体吞吐量？如果有，能不能举一下手？看看今天在场有没有人。其实举手的比我预期的多，相当多的人举了手。我认为，随着这些趋势继续，这个问题很可能会变得更糟。

### 为什么尾延迟差：incast 与发送端拥塞控制
<details>
<summary>Original English</summary>
So what's going on? Why is tail latency bad? Well, typically the cause is congestion resulting from incast. So incast is when several nodes all decide simultaneously to transfer data to some destination node. And if they all send large messages, well, the links are the same everywhere in the network. So three nodes can transfer three times as fast as one node can possibly receive. And so what happens is that packets accumulate at the last hop going to that destination in the top of rack switch at its egress port for the destination node.

Then if some other node decides it wants to send a short message to that same destination, the short message gets stuck behind the long ones in the queue there. And actually that causes delay and in the worst case so many packets arrive that the switch runs out of buffer space that it has to drop packets and then there are you timeouts and retransmissions that make everything even worse.
</details>

那么到底怎么回事？为什么尾延迟这么差？通常原因是 incast 造成的拥塞。incast 是指多个节点同时决定向某个目的节点传输数据。如果它们都发送大消息，而网络中各处的链路都是一样的，那么三个节点发送的速度可以达到一个节点所能接收速度的三倍。结果就是数据包在通往该目的地的最后一跳堆积，也就是在机架顶部交换机上、目的节点对应的出口端口。

然后，如果另一个节点想向同一个目的地发送一条短消息，这条短消息就会卡在那里队列中的长消息后面。这实际上会造成延迟；在最坏的情况下，到达的数据包太多，交换机缓冲空间耗尽，不得不丢包，随后就会出现超时和重传，让一切更加糟糕。

<details>
<summary>Original English</summary>
So somehow we need some way to reduce the congestion in those cues. Somehow we have to get the sending nodes to stop sending so fast so the cues don't just build up without limit.

So the way this is done historically virtually all network protocols before HOMA including TCP and RDMA congestion control is the responsibility of the sender. So senders somehow have to figure out that congestion is happening and they have to slow down their rate of transmission. Now you you might wonder why are senders doing it? because the congestion is way over at the other end of the data center network. How does the the sender find out? Well, in the in the old really old days, the way they would find out is the cues would overflow and packets would get dropped. The sender would detect the packets got lost because it wouldn't get acknowledgements back and it would assume that means there's congestion and then slow down its rate of transfer.
</details>

所以我们需要某种办法来减少这些队列里的拥塞。我们得想办法让发送节点不要发得那么快，这样队列就不会无限堆积。

历史上的做法是：在 HOMA 之前，几乎所有网络协议，包括 TCP 和 RDMA，拥塞控制都是发送端的责任。发送端必须设法弄清楚拥塞正在发生，并且降低自己的发送速率。你可能会问，为什么由发送端来做？因为拥塞发生在数据中心网络的另一头，远在那边。发送端怎么知道？在很早很早以前，它们得知的方式是队列溢出、数据包被丢弃。发送端发现包丢了，因为收不到确认，就假定这意味着存在拥塞，然后降低传输速率。

<details>
<summary>Original English</summary>
That's really expensive. So today there are better techniques that mostly involve the switches providing information. So a top of rack switch when it sees that the Q length for an ingress port has reached some threshold starting to fill long before the queue overflows it starts marking all of the packets that pass through with what's called early congestion notification ECN marking. And so when those packets pass through to the receiver, the receiver sees the marking in the packets. And then when it communicates back to the sender next, for example, to send an acknowledgement, then it includes that marking that goes back to the sender. And now the sender sees that the sender realizes, oh, there's congestion someplace. I've got to slow down my rate of transmission.
</details>

这代价非常高。所以今天有更好的技术，主要是由交换机提供信息。机架顶部交换机看到某个入口端口的队列长度达到某个阈值、也就是在队列溢出之前很早就开始变满时，会给所有经过的数据包打上所谓的早期拥塞通知（ECN）标记。这些数据包到达接收端时，接收端看到包中的标记。然后，当它接下来向发送端通信时，例如发送确认，就会把这个标记带回给发送端。这时发送端就意识到：哦，某个地方有拥塞，我得降低发送速率。

<details>
<summary>Original English</summary>
So that's the basic idea. Unfortunately, getting this right is really hard. Really hard. It's very hard for the congesture to figure out exactly how to set its rates because it gets one bit of information. There's congestion someplace and there are multiple senders all sending to the same destination. They're all trying to make adjustments simultaneously. How much do you cut back and how do I know when I can ramp up again? And even worse, it's really hard to do this in a way that's stable because there's control lag. That is, it takes time before the sender finds out that there's congestion. And in fact, using this process, it typically takes several round trips for the sender to gradually adjust its rate to get just the right rate to match the available bandwidth. But by the time you do that in a network that things have changed, new transmissions have started or old ones have finished. And so these systems tend to never stabilize. They're constantly oscillating between sending too much and and sending too little.
</details>

这就是基本思路。不幸的是，把它做对非常难，真的非常难。发送端（原文为 congesture）很难精确判断该如何设定速率，因为它只得到一个比特的信息：某个地方有拥塞，而且有多个发送端都在向同一个目的地发送，它们都在同时尝试调整。要削减多少？我怎么知道什么时候可以再提速？更糟的是，很难以稳定的方式做到这一点，因为存在控制滞后。也就是说，发送端要过一段时间才会发现拥塞。事实上，使用这个过程，发送端通常需要几个往返才能逐步调整速率，达到与可用带宽相匹配的恰当速率。但等你做完这些，网络里情况已经变了，新的传输已经开始，或旧的已经结束。所以这些系统往往永远无法稳定，不断在发得太多和发得太少之间震荡。

<details>
<summary>Original English</summary>
Now, this problem's been around for a long time. It's been known in the research community for more than 20 years now. There have been tons of papers published on it. There have been some improvements made. That's undeniable, but we're still a long ways from anything that works well. And the problem is is with the fundamental nature of it doing the the congestion control on the center side. It just doesn't work very well. So you end up with a lot of Q buildup. And in fact, you can see the only way to find out that there's congestion is if there's cues and so by that point, we're already experiencing delays. So that's a problem. There's one other problem with TCP and RDMA also is that their their basic data model is a bite stream just a stream of bytes with no differentiation in it.
</details>

这个问题已经存在很久了，研究界知道它已经超过20年。发表了大量论文，也取得了一些改进，这是不可否认的，但距离真正好用的东西还很远。问题在于，在发送端做拥塞控制，这一根本性质使它效果不好。所以最终会有大量队列堆积。事实上，你能发现拥塞的唯一途径是出现了队列，所以到那个时候，我们已经在经历延迟了。这是个问题。TCP 和 RDMA 还有另一个问题：它们的基本数据模型是字节流，就是一串没有区分的字节。

<details>
<summary>Original English</summary>
So if you send a series of messages say through a TCP socket they get serialized into that stream and on this slide I've you know I've shown the messages appear like they have different colors in the stream. Well there are no colors in real life. TCP has no idea where the message boundaries are. And that also makes life hard. For example, you don't know how much more data is coming. If you knew how big the message was, you know how much more is coming. And you can't prioritize short messages, which we'd really like to do. Get the short messages through faster. And you can end up with what's called head of line blocking where somebody sends a series of messages to the same destination and they send two really large ones and then a small one after that that gets stuck behind them in that stream and so it gets delayed and again you have tail latency issues.

So all in all, TCP and RDMMA are just not well suited to this environment.
</details>

所以，如果你通过比如 TCP 套接字发送一系列消息，它们会被串行化进那条流里。在这张幻灯片上，我把消息画成在流里有不同的颜色，但现实中并没有颜色。TCP 不知道消息边界在哪里。这也让事情变得困难。例如，你不知道后面还有多少数据要来；如果你知道消息有多大，就知道还有多少要来。而且你无法优先处理短消息，而我们真的很想这么做，让短消息更快通过。还可能出现所谓的队首阻塞：有人向同一个目的地发送一系列消息，先发了两个很大的，然后是一个小的，这个小的就卡在流中它们后面，于是被延迟，又出现了尾延迟问题。

总的来说，TCP 和 RDMMA 就是不太适合这种环境。

### Homa 的设计
<details>
<summary>Original English</summary>
So what do we do? Well, what I'd like to do next is tell you about a new protocol called HOMA that we've developed at Stanford, which was based on a completely clean slate redesign for network transport. If you could start from scratch and rethink how you do transport for data centers, how would you do it? And it turns out in home of virtually every major design decision is different from TCP and RDMA. TCP for all the amazing things it's done is just not a good match to today's data centers nor RDMA.

So what Homa does particularly well is to manage the combination of large and small messages and to make sure that the messages have short messages have really low latency.
</details>

那我们该怎么办？接下来我想介绍我们在斯坦福开发的一种新协议 HOMA，它基于对网络传输的完全推倒重来的重新设计。如果你可以从零开始，重新思考如何为数据中心做传输，你会怎么做？结果是，在 Homa 中，几乎每一项主要设计决策都与 TCP 和 RDMA 不同。TCP 尽管成就惊人，但与今天的数据中心并不匹配，RDMA 也一样。

所以 Homa 特别擅长的是管理大消息和小消息的混合，并确保短消息具有非常低的延迟。

<details>
<summary>Original English</summary>
So this started off as a PhD dissertation for one of my students, Benam Montazeri, and then the results were so great that I decided to make it my personal project to see if we could get it out of the lab and into production. Uh, as you may know, I'm I'm not like most professors and that I love to code. And so I turned this into my my own programming project. I have created a kernel module for Linux. I'm currently working through the process of getting that upstreamed into the kernel. It's available on GitHub for download. So let me tell you just a little bit about how Homa works. I want to mention three things. First, it's messagebased, not streambased.
</details>

这最初是我的一位学生 Benam Montazeri 的博士论文，后来结果非常好，所以我决定把它作为我的个人项目，看看能否把它从实验室推向生产环境。你们可能知道，我和大多数教授不一样，我热爱写代码。所以我把它变成了我自己的编程项目。我为 Linux 编写了一个内核模块，目前正在推进把它合入（upstream）内核的流程。它可以在 GitHub 上下载。下面我简单讲讲 Homa 是如何工作的。我想提三点。第一，它基于消息，而不是基于流。

<details>
<summary>Original English</summary>
[clears throat] In fact, the fundamental unit at Homa is a remote procedure call which consists of two things. A request message sent from a client to a server and then a response message returned back from the server to the client. So the key thing here is that Homa knows about message lengths. They're buried in the transport all the way down to the bottom. And this has a bunch of advantages. First, it allows us to predict the future. As soon as a receiver gets the first packet of a message, it knows exactly how much more data the sender wants to send. And that's so has so much more information for doing congestion control.

Second, Home Prioritizes shorter messages. It uses SRPT, shortest remaining processing time first to try and prioritize shorter messages. And third, because messages are all independent, they're not serialized into a stream. Every message is independent. Shorter messages can bypass long ones so they don't get cued behind long messages.
</details>

事实上，Homa 的基本单位是远程过程调用（RPC），由两部分组成：从客户端发给服务器的请求消息，以及从服务器返回给客户端的响应消息。关键在于，Homa 知道消息长度，这些信息一直贯穿到传输层的最底部。这有一系列好处。第一，它让我们能够预测未来：接收端一收到消息的第一个数据包，就确切知道发送端还想发送多少数据。这为做拥塞控制提供了多得多的信息。

第二，Homa 优先处理较短的消息。它使用 SRPT，即最短剩余处理时间优先，来尝试优先处理较短的消息。第三，因为消息都是独立的，不会被串行化进一个流里，每条消息都是独立的，所以较短的消息可以绕过长消息，不会排在长消息后面。

<details>
<summary>Original English</summary>
The second thing about Homa that's different is that it controls congestion from the receiver. Now, when you think about it, this makes sense because the congestion happens primarily at that last down link to the receiver. And so, the receiver has way more information. In fact, with Homer, as soon as it gets the first packet of a message, it knows exactly how much more is coming. So, it has essentially complete information about congestion and it can therefore respond to congestion much more quickly and much more precisely.
</details>

Homa 不同的第二点是，它从接收端控制拥塞。仔细想想，这是有道理的，因为拥塞主要发生在通往接收端的最后那一段下行链路上。所以接收端掌握的信息要多得多。事实上，用 Homa，接收端一收到消息的第一个数据包，就确切知道后面还有多少要来。因此它基本上拥有关于拥塞的完整信息，所以能更快、更精确地响应拥塞。

<details>
<summary>Original English</summary>
The way things work with HOMA is that when a sender has a message to send, it breaks it up into packets, but it only transmits the first few packets, those are called unscheduled packets, to the receiver. Packets after that are called scheduled packets and they only get transmitted when the receiver asks for them. So the receiver will send grant packets back. It'll paste them out and send those back to the sender over time telling the sender it's now time for you to send me the next chunk of data. And the receiver can delay those grants. So for example, if the receiver has 10 messages that are incoming, there's no point in sending grants to all 10 of them because then you'll just get congestion in the in the top of wrap cues. So it can use the grants to reduce congestion and then it can also use the grants to give preference to its most favorite messages which would be the shorter ones. So it's a way of of implementing SRPT by favoring short messages.
</details>

Homa 的工作方式是：发送端有消息要发送时，把它拆成数据包，但只向接收端发送最前面的几个数据包，这些叫作非调度（unscheduled）数据包。此后的数据包叫作调度（scheduled）数据包，只有在接收端请求时才会发送。接收端会把授权（grant）数据包发回去，随着时间推移把它们逐个发给发送端，告诉发送端：现在轮到你把下一块数据发给我了。接收端可以延迟这些授权。例如，如果接收端有10条消息正在到来，没必要给这10条全都发授权，否则就会在机架顶部交换机的队列里造成拥塞。所以它可以用授权来减少拥塞，也可以用授权来偏向它最喜欢的消息，也就是较短的那些。这是通过偏向短消息来实现 SRPT 的一种方式。

<details>
<summary>Original English</summary>
The third aspect of Homa is that it takes advantage of the priority cues in modern switches. So modern data center switches have more than one Q at each egress port typically eight and they can be used in a priority mechanism where packets get transmitted preferentially from the highest priority Q. So I've shown only two cues on the slide here but typically there's more than that you can specify in packets using the various fields of the packet you can specify which queue it should go into and so Homa dynamically makes those choices in a way to give priority to shorter messages. So if we go back to the incast example from a few slides ago, all of those long messages will pile up in the lowest priority queue. But if there's a short message coming, it will use a higher priority queue. And so it will immediately bypass all of the cued packets from the short from the uh the longer messages and get through to the destination more quickly.
</details>

Homa 的第三点是，它利用了现代交换机中的优先级队列。现代数据中心交换机在每个出口端口上有不止一个队列，通常是八个，可以用于优先级机制，使数据包优先从最高优先级的队列发送。我在幻灯片上只画了两个队列，但通常不止这些。你可以利用数据包的各个字段，指定它应该进入哪个队列，而 Homa 会动态地做这些选择，以便给较短的消息优先级。所以回到前面几张幻灯片的 incast 例子，所有那些长消息都会堆积在最低优先级队列中；但如果有短消息到来，它会使用更高优先级的队列，于是会立刻绕过较长消息排队的所有数据包，更快地到达目的地。

### 基准测试结果
<details>
<summary>Original English</summary>
So how much of a difference does this make? Here's a this slide. I've got one sample benchmark that I use as part of my tuning and evaluation of Homa. It consists of a workload of a bunch of machines on a network that are exchanging messages back and forth of different sizes ranging from very small to very large. And on this graph you can see on the x-axis is the message length from about 50 bytes up to a megabyte. The yaxis shows you the roundtrip time for messages of that length. So this request this uses request and response messages that are the same length. You can see TCP in green, Homa in blue, and the Y-axis is is roundtrip time. So lower is better. And for each protocol, I've got two curves. One curve is the P50 curve. That's the median latency for messages of this length. And then P99 is the 99th percentile, i.e. tail latency for messages of this length. So I want to point out two things. First, the P99 for short messages is dramatically better for HOM. So with TCP it's more than a millisecond tail latency. Home is less than 100 microsconds about 13 times faster.
</details>

那么这能带来多大差别？这张幻灯片上有一个示例基准测试，是我调优和评估 Homa 时用的。它的工作负载是网络上的一批机器来回交换不同大小的消息，从很小到很大。在这张图上，x 轴是消息长度，从大约50字节到1兆字节；y 轴显示该长度消息的往返时间。这里使用的请求消息和响应消息长度相同。你可以看到绿色是 TCP，蓝色是 Homa，y 轴是往返时间，所以越低越好。每种协议我画了两条曲线：一条是 P50 曲线，即该长度消息的中位延迟；P99 则是第99百分位，也就是该长度消息的尾延迟。我想指出两点。第一，对短消息来说，Homa 的 P99 要好得多。TCP 的尾延迟超过一毫秒，而 Homa 低于100微秒，大约快13倍。

<details>
<summary>Original English</summary>
Second interestingly you might think that because Homa favors shorter messages that long messages suffer and get worse performance. It turns out that's actually not the case. Even on the longest messages, Hom is almost a factor of two better than TCP. I don't have time to explain that today, but it has to do with the fact that HOMA uses run to completion approaches which are much more effective than fair than the fair scheduling used by TCP.
</details>

第二，有意思的是，你可能会认为，因为 Homa 偏向较短的消息，长消息会吃亏、性能变差。结果事实并非如此。即使是最长的消息，Homa 也比 TCP 好近两倍。我今天没时间解释这一点，但这与 Homa 采用运行至完成（run to completion）的方式有关，这种方式比 TCP 使用的公平调度有效得多。

### 总结与邀请
<details>
<summary>Original English</summary>
So, just to wrap up, the role of short messages in AI appears to be increasing. I think I think it's likely that it's going to continue to increase. We'll see over the next year or two if that happens. And I just want to pose a question to you. You know, as you're running your applications and measuring performance and seeing what the bottlenecks are, ask yourself, is high latency for short messages affecting your throughput? If the answer is yes, then just know there is a solution available. You should give HOMA a try. You can probably reduce your tail latency by an order of magnitude or more. And by the way, this is Home is basically my life mission right now. I'm sort of semi-retired from Stanford. The reason I did that is so I can spend 100% of my time hacking on Homa. So I'd be delighted to work with you and help you if you decide you want to experiment with Homa. If you need help getting started, answer questions, bug fixes, whatever, you know, I'd be happy to work with you to try and make you successful with it. So if that is interesting, feel free to contact me. My email is on the slide or you can Google me too and find me over the internet. So thanks very much for listening and hope to hear from some of you.
</details>

最后总结一下，短消息在AI中的作用似乎在增加。我认为它很可能会继续增加，未来一两年我们会看到是否如此。我想向你们提一个问题：当你们运行应用、测量性能、查看瓶颈时，问问自己，短消息的高延迟是否在影响你的吞吐量？如果答案是肯定的，那就请知道，有一个可用的解决方案。你们应该试试 HOMA，你们大概可以把尾延迟降低一个数量级或更多。顺便说一下，Homa 基本上就是我现在的人生使命。我从斯坦福半退休了，这样做的原因是我可以把100%的时间都用来钻研 Homa。所以如果你们决定想试验 Homa，我会很乐意与你们合作并提供帮助。如果你需要入门帮助、答疑、修 bug 之类的，我都乐意与你合作，努力让你们用得成功。如果这让你感兴趣，欢迎联系我。我的邮箱在幻灯片上，你也可以在网上搜索我找到我。非常感谢大家聆听，希望能收到你们中一些人的来信。

<details>
<summary>Original English</summary>
>> [music]
</details>

>> [音乐]