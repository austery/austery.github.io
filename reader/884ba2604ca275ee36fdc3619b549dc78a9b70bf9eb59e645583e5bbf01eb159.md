---
author: Dwarkesh Patel
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oIk3R-sMX5o
speaker: Dwarkesh Patel
tags:
  - chip-design
  - ai-hardware
  - systolic-array
  - clock-cycle
  - compute-communication
title: 从底层看芯片设计：Reiner Pope 深入解读AI芯片工作原理
summary: MatX CEO Reiner Pope 在访谈中深入探讨了AI芯片的工作原理，从逻辑门、乘加运算等基本单元开始，逐步构建到复杂的脉动阵列（Tensor Core）和芯片架构。他详细解释了AI芯片如何通过优化计算与通信的比例，实现高效的矩阵乘法，并比较了CPU、GPU和TPU在架构设计上的核心差异。访谈还涵盖了时钟周期的决定因素、FPGA与ASIC的商业权衡，以及芯片设计中非显而易见的挑战和取舍。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Reiner Pope
companies_orgs:
  - MatX
  - Nvidia
  - TSMC
products_models:
  - FP4
  - FP8
  - CUDA core
  - Tensor Core
  - TPU
  - FPGA
  - ASIC
  - CPU
  - GPU
media_books: []
status: evergreen
---
### AI芯片内部机制

**Dwarkesh**: 我再次邀请到 **MatX** 的首席执行官 **Reiner Pope**。上次我们讨论了数据中心内部发生的事情。现在我想了解 **AI 芯片**内部是如何运作的。芯片到底是如何工作的？顺便声明一下：我是 MatX 的天使投资人。所以我希望你们设计了一款好芯片。

<details>
<summary>Original English</summary>

**Dwarkesh**: I'm back with Reiner Pope, CEO of MatX, a new AI chip company. Last time we were talking about what happens inside a data center. Now I want to understand what happens inside an AI chip. How does a chip actually work? Full disclosure, by the way: I am an angel investor in MatX. So hopefully you have designed a good chip.

</details>

**Reiner Pope**: 希望如此。我将从芯片设计的最小基本单元开始，然后逐步讲解实际生产芯片的构成及其组件。在芯片的最底层，我们使用的基本单元是**逻辑门**，非常简单的东西，比如 **AND**、**OR** 和 **NOT**。这些逻辑门通过导线连接在一起，导线必须物理上作为金属走线铺设在芯片上。

<details>
<summary>Original English</summary>

**Reiner Pope**: Hope so. I'll start with the smallest fundamental unit of chip design, and we'll build up to what an actual production chip is and what its components are. At the very bottom level of a chip, the primitives we work with are logic gates, very simple things like AND, OR, and NOT. These are connected together by wires that have to be laid out physically as metal traces on a chip.

</details>

### 乘加运算：AI芯片的核心

**Reiner Pope**: AI 芯片想要计算的主要功能是**矩阵乘法**。在矩阵乘法中，基本操作是数字对的**乘加运算**。我们将通过手动演示这个计算过程，然后推断出它的电路会是什么样子。如果我用一个四位数字与另一个四位数字进行乘加运算，会更容易理解。最清晰的基本操作实际上是乘加运算。所以有两个项相乘，然后我们再加一个八位数字。

<details>
<summary>Original English</summary>

**Reiner Pope**: The main function that AI chips want to compute is the multiplication of matrices. Inside that, the fundamental primitive is a multiply-accumulate of pairs of numbers. We're going to demonstrate what that calculation looks like by hand, and then infer what a circuit would look like for that. It'll be easiest if I do a multiply-accumulate of a four-bit number with another four-bit number. The clearest primitive is actually multiply-accumulate. So there's a multiply of these two terms, and then we're going to add in an eight-bit number.

</details>

**Dwarkesh**: 我可以问一个澄清问题吗？为什么这是计算机内部所有计算的自然基本操作？

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I ask a clarifying question? Why is this the natural primitive for whatever computation happens inside a computer?

</details>

**Reiner Pope**: 有几个原因。它效率更高一些，但对于 AI 芯片来说，它之所以自然，是因为如果你看看矩阵乘法期间发生的事情……简而言之，什么是矩阵乘法？它是一个关于 i、j 和 k 的 **for 循环**：输出 [i, k] += 输入 [i, j] x 另一个输入 [j, k]。在矩阵乘法的每一步都会发生乘加运算。另一个观察是，累加步骤中的精度几乎总是高于乘法步骤中的精度。这对于 AI 芯片来说是特有的。你正在乘以**低精度**数字，然后当你累加时，误差会迅速累积，所以你在那里需要更高的精度。这就是我们选择进行四位乘法和八位加法的原因。

<details>
<summary>Original English</summary>

**Reiner Pope**: There are a few reasons. It's a little bit more efficient, but the reason it's natural for AI chips is that if you look at what's happening during a matrix multiply… What is a matrix multiply in short? There's a for-loop over i, over j, and over k, of output [i, k] += input [i, j] x other input [j, k]. A multiply-accumulate happens at every single step of a matrix multiply. The other observation is that the precision will almost always be higher in the accumulation step than in the multiplication step. This is specific to AI chips. You're multiplying low-precision numbers, and then when you accumulate, errors accumulate quickly, so you need more precision there. This is why we've chosen to do a four-bit multiplication and an eight-bit addition.

</details>

**Dwarkesh**: 我想确认我是否理解了。有两种理解方式。一种是值会比输入更大。另一种是如果它是**浮点数**，那会……也许那部分对我来说不太直观。但这也许是相同的原理？

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make sure I understood that. There are two ways to understand that. One is that the value will be larger than the inputs. The other is that if it was a floating-point number it would be… Maybe that part is less intuitive to me. But maybe it's the same principle?

</details>

**Reiner Pope**: 确实是相同的原理。另一个独立的原理是，当你累加这个数字时，你正在累加一堆数字，所以你有很多**舍入误差**在累积。而在这个例子中，链中只有一个乘法，所以乘法中没有很多舍入误差累积。

<details>
<summary>Original English</summary>

**Reiner Pope**: It really is the same principle. The separate principle is that as you're summing up this number, you're summing up a whole bunch of numbers, so you've got a lot of rounding errors accumulating. Whereas in this case, there's only one multiplication in the chain, so there aren't a lot of rounding errors accumulating in the multiplication.

</details>

**Dwarkesh**: 为什么你会累加一堆数字？那里只有两个数字。

<details>
<summary>Original English</summary>

**Dwarkesh**: Why are you summing up a whole bunch of numbers? There’s just two numbers there.

</details>

**Reiner Pope**: 这个求和重复了 j 很多次。任何误差都会累积。我明白了。

<details>
<summary>Original English</summary>

**Reiner Pope**: This summation is repeated j many times. Any errors accumulate. I see.

</details>

### 手动乘加运算与逻辑门

**Dwarkesh**: 那么我们如何手动执行这个计算呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: So how would we perform this calculation by hand?

</details>

**Reiner Pope**: 作为人类，我们可能会将其分成两部分，但我们可以使用**长乘法**一次性完成。对于乘法项，我们首先要将这个四位数字乘以另一个四位数字中的每个位。我们把它写出来。首先，1001 乘以这个位位置。那就是数字本身。然后向右移一位，我们乘以 0。这会给我们一个全 0 的数字。再向右移一位乘以 1，我们得到 1001。最后，对于最后一个位位置，我们再次得到一个全 0 的数字。这给了我们一堆需要相加的项进行乘法。在我们进行求和的同时，我们也可以将实际的累加项也加进去。所以我们直接复制过来。这就是我们想要计算的五项求和。

<details>
<summary>Original English</summary>

**Reiner Pope**: As a human, we would probably separate it into two, but we can do it all in one using long multiplication. For the multiplication term first, we're going to multiply this four-bit number by every single bit position in the other four-bit number. We write that out. First, 1001 multiplied by this bit position. That is the number itself. Then shifted across by one, we're multiplying by 0. That gives us an all-0 number. Shifted across one more to multiply by this one, we get 1001. Finally, for this last bit position, we get an all-0 number again. This gives us a bunch of terms that we have to add for the multiplication. While we're doing that summation, we might as well add in the actual accumulator term as well. So we just copy that directly across. So this is the sum. It's a five-way sum that we want to compute.

</details>

**Reiner Pope**: 到达这个中间步骤需要我们用到什么**逻辑门**？我们需要生成所有这 16 个**部分积**。我如何生成其中一个部分积呢？例如，我们取这个数字 1。我们通过将这个数字乘以这个数字来生成它。我们可以用一个 **AND 门**来生成它。如果这个位是 1 并且这个位是 1，那么这个数字就是 1。如果其中任何一个是 0，那么 0 乘以任何东西都是 0。为了生成所有这些，我们最终使用了 16 个 AND 门。在一般情况下，如果我进行 p 位乘法乘以 q 位乘法，这将是 p 乘以 q 个 AND 门。最后，我将它们求和。大部分工作将发生在求和中。

<details>
<summary>Original English</summary>

**Reiner Pope**: What logic gates did it take us to get to this intermediate step? We needed to produce all 16 of these partial products. How do I produce one of these partial products? Let's take this number 1, for example here. We produce it by multiplying this number by this one over here. We can produce that with an AND gate. This number is 1 if both this bit is 1 and this bit is 1. If either of them is 0, then the multiplication of 0 times anything is 0. To produce all of this, we ended up consuming 16 AND gates. In the general case, if I were doing a p bit multiply times a q bit multiply, this will be p times q many ANDs. Finally, I sum them. Most of the work is going to happen in the summing.

</details>

**Reiner Pope**: 让我描述一下我们在这里使用的另一种逻辑门。AND 门几乎是芯片上存在的最简单的逻辑门。它几乎是最小的。在另一个极端，你通常会使用的最大逻辑门叫做**全加器**。从软件的角度来看，你可能会认为全加器是将 32 位数字相加。在这种情况下，它只是将三个单比特数字相加，所以你可以把它想象成将 0、1 和 1 相加。当我将这些相加时，结果可以是 0、1、2 或 3，所以我可以用两个位来表示它。作为输入，它有三个位。作为输出，它有两个位。二进制数字 2 是 10。这也被称为 **3→2 压缩器**，因为它接收三个输入位并生成两个输出位。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let me describe the other logic gate that we use here. AND is almost the simplest logic gate that exists on a chip. It's almost the smallest. At the other extreme, the very largest logic gate you'll typically use is something called a full adder. Coming from software, you might think that a full adder adds 32-bit numbers together. In this case, it just adds three single-bit numbers together, so you can think of it as adding 0, 1, and 1 together. When I add these together, the result can be 0, 1, 2, or 3, so I can express that in binary using just two bits. As input, it has three bits. As output, it has two bits. The number 2 in binary is 10. This is also known as a 3→2 compressor because it takes three bits of input and produces two bits of output.

</details>

**Dwarkesh**: 只是为了确保我理解了：两个输入是 X 和 Y 值，然后是一个进位……

<details>
<summary>Original English</summary>

**Dwarkesh**: Just to make sure I understood: the two inputs are an X and a Y value and then some carry that came in…

</details>

**Reiner Pope**: 这三个输入都在相同的位位置上，就像这里的同一列中的三个位。两个输出，我在这里垂直绘制，在这里水平绘制，以匹配这种垂直与水平布局。这表示同一列中的事物处于相同的位位置，而相邻列中的事物则不同。这是一个进位输出，而这个是求和。所以如果全加器中的输入是 101，那么输出将是 10。如果是 111，则将是 11。如果是 000，则将是 00。如果是 010，它仍然是 01。

<details>
<summary>Original English</summary>

**Reiner Pope**: The three inputs are all bits in the same bit position, like three bits in a column here. The two outputs, I've drawn them vertically here and horizontally here to match this vertical versus horizontal layout. This expresses that things in the same column are in the same bit position, whereas things in adjacent columns are different. This is a carry out, whereas this was the sum. So if the inputs in the full adder were, say, 101, then the output would be 10. If it were 111, it'd be 11. If it were 000, it'd be 00. If it were 010, it'd still be 01.

</details>

**Dwarkesh**: 明白了。

<details>
<summary>Original English</summary>

**Dwarkesh**: Got it.

</details>

**Reiner Pope**: 是的。它本质上只是计数，并用二进制表示。这个电路捕捉了我们人类在沿着一列求和时自然会做的事情。我将展示一次使用全加器求和的迭代。我在这里求和的方式对人类来说会有些不自然。我们会沿着列求和然后记住进位，但我们不会记住进位，而是明确地写出来。我们从最右边的列向左边进行。在最右边的列，我们将 1 和 1 相加，结果是 0，进位是 1。我们在这个比特对上使用了这个全加器电路，并生成了一对比特作为输出。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. It's essentially just counting the number of things and expressing that in binary. This circuit captures what we as humans naturally do when we're summing along a column. I'll show one iteration of using the full adder to sum. The way I sum here is going to be a little unnatural for humans. We would sum along the column and then remember the carry, but instead of remembering the carry, we'll explicitly write it out. We proceed from the rightmost column toward the left. On the rightmost column, we sum the 1 and the 1, and that produces a zero here and a carry of one. We've used this full adder circuit on this pair of bits and produced a pair of bits as output.

</details>

**Reiner Pope**: 现在我们可以用这一列做同样的事情。我们有四位数字的一列，所以我们取前三个，对它们进行全加器运算，结果得到一个 0 和一个 0 作为输出。这些的求和是 00。这就是应用于所有这些比特的全加器。当我用完比特后，我将它们划掉，表示我已经处理过它们了。我们再继续进行一些。我取这三个数字，将它们相加，结果得到一个 1 和一个 0。我已经处理了这三个数字。现在我取这三个数字并相加，结果得到一个 1 和一个 0，我已经处理了这些数字。

<details>
<summary>Original English</summary>

**Reiner Pope**: Now we can do the same thing with this column. We have a column of four numbers, so we'll take the first three of them, run a full adder on them, and that gives us a 0 and a 0 as output. The sum of these is 00. That's the full adder applied to all these bits. As I've used up bits, I'll cross them out to indicate that I've handled them. Let's keep going a little bit more. I take these three numbers, I add them, and that gives me a 1 and a 0. I've dealt with these three numbers. Now I take these three numbers and add them, and that gives me a 1 and a 0, and I've dealt with these numbers.

</details>

**Reiner Pope**: 观察这个过程的方式是，我有一个需要相加的整个数字网格。我将继续对这里的所有比特应用全加器，不断地从一列中移除三个数字，并输出两个数字作为结果。一遍又一遍地重复，直到最终只得到一个数字。这种方法称为 **Dadda 乘法器**。这是使用全加器实现**面积高效乘法器**的标准方法。

<details>
<summary>Original English</summary>

**Reiner Pope**: The way to view this is that I have this whole grid of numbers that need to be added. I'm going to keep applying full adders to all the bits here, constantly removing three numbers from a column and writing out two numbers as output. Keep going over and over again until I eventually get just one single number coming out. This approach is called a Dadda multiplier. This is the standard for how you do area-efficient multipliers using full adders.

</details>

### 电路规模与乘加运算的优势

**Reiner Pope**: 让我们尝试量化这个电路的尺寸，以便我们了解事物的大小，并稍后进行比较。我使用了多少个全加器？我从多少个数字开始？我有 16 个部分积，这是所有这些项与所有这些项的乘积，再加上我在这里添加的八个项。我最初有 24 位。最终我输出了 8 位。在每一步中，我划掉了三个数字，并输出了两个数字。每次使用全加器都会消除这里的一个位。那么有多少个全加器呢？那一定是 24 减去 8，所以这个电路中有 16 个全加器。在一般情况下也是如此。这个电路中将有 p 乘以 q 个全加器。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's try to quantify the circuit size of this so we have a sense of how big things are and can compare them later. How many full adders did I use? How many numbers did I start with? I have the 16 partial products, which is a product of all of these terms with all of these terms, plus the eight terms that I'm adding here. I started off with 24 bits. Eventually I produced eight bits on the output. In every step, I was crossing off three numbers and writing two numbers out as a result. Every single use of a full adder eliminates one of the bits here. So how many full adders? It must be 24 minus 8, so there were 16 full adders in this circuit. This is true in the general case as well. There will be p times q many full adders in this circuit.

</details>

**Dwarkesh**: 让我确保我理解这个逻辑。输入位是 24，是 p 乘以 q，加上 p 加 q。输出位只是 p 加 q。所以 p 乘以 q 加上 p 加 q，减去 p 加 q 等于 p 乘以 q。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make sure I understand the logic of that. The input bits, 24, is p x q, plus p + q. The output bits are just p + q. So p x q plus p + q, minus p + q equals p x q.

</details>

**Reiner Pope**: 对。我认为这解释了，或者至少暗示了我们选择乘加运算的第二个原因。第一个原因是它出现在矩阵乘法中。第二个是它给了我们这个非常简洁、简单的 p 乘以 q，非常简单的代数。我们已经描述了整个过程。我在这里采取的每一个原子步骤都成为一个逻辑门，然后导线连接在一起。当我有这三个输入用于生成这两个输出时，如果我将这映射到物理设备，那么会有一根导线将所有这三件事连接到一个逻辑门，该逻辑门产生这个输出。这是 AI 芯片内部不同位宽的主要基本操作。我们将从这里开始，构建如何使用它来运行你可能想要的所有其他操作。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. I think this explains, or at least hints at, the second reason we chose to do a multiply-accumulate. The first reason is that it's what shows up in matrix multiplication. The second is that it gave us this very slick, simple p x q, very simple algebra. We've described this whole procedure. Every single atomic step that I took here becomes a logic gate, and then the wires are connected together. When I had these three inputs that I used to produce these two outputs, if I think of mapping this to a physical device, there would be a wire connecting all three of these things together into a logic gate that produced this output. This is the main primitive, at different bit widths, that's inside an AI chip. We're going to build up from here to how you would use it to run all the other operations you might want.

</details>

### FP4与FP8的权衡

**Dwarkesh**: 这可能不是提问的最佳时机，但每当 **Nvidia** 报告说某个芯片可以进行 X 个 **FP4** 或一半的 **FP8** 时，这似乎意味着这些电路是可互换的，没有专门的 FP4 或 FP8。但是你在这里的映射方式，看起来如果它必须映射到逻辑中，你将需要一个专门的 FP4 乘加器，然后是一个专门的 FP8 累加器。它们可以“互换”吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: This might be the wrong time to ask, but whenever Nvidia reports that this chip can do X many FP4 or half as many FP8, it seems to imply those circuits are fungible, that there's not a dedicated FP4 versus FP8. But the way you're mapping it out here, it seems like if it has to be mapped out in the logic, you would need a dedicated FP4 multiply-accumulate and then a dedicated FP8 accumulate. Can you "funge" them?

</details>

**Reiner Pope**: 从绘制来看，它们不是特别可互换。这实际上是设计芯片时必须做出的主要选择之一：我需要多少 FP4 和多少 FP8？有时我会从客户需求的角度考虑。另一个角度是平衡 FP4 和 FP8 之间的功耗预算。

<details>
<summary>Original English</summary>

**Reiner Pope**: As drawn, they're not particularly fungible. This is actually one of the main choices you have to make when designing a chip: how much of FP4 and how much of FP8 do I have? Sometimes I'll make that consideration from the point of view of the customer requirement. Another angle is to equalize the power budget between FP4 and FP8.

</details>

**Dwarkesh**: 当他们报告这些数字时，碰巧是 FP4 的数量是 FP8 的两倍，他们只是选择给所有浮点数提供相同的**芯片面积**，结果就是……？为什么比例恰好是 2 倍？

<details>
<summary>Original English</summary>

**Dwarkesh**: When they report those numbers and it just happens to be the case that it does 2x as many FP4 as FP8, they're just choosing to give equivalent die areas to all the floating points, and as a result it ends up being…? Why is the ratio exactly 2x?

</details>

**Reiner Pope**: 其中一部分原因是它肯定不会与芯片面积完全等效。存在**数据传输**的原因。我们稍后在查看它如何进出内存时可能会回到这一点。从软件层面来看，我可以将两个四位数字打包到与一个八位数字相同的存储空间中，这一点非常棒。当我将其存储到内存时，我在芯片内部连接的总线尺寸使得这一切运作得非常好。

<details>
<summary>Original English</summary>

**Reiner Pope**: Part of it is that surely it won't be exactly equivalent to die area. There's a data movement reason. We'll maybe come back to this when we look at how it goes into and out of memories. There's something really nice from a software level about the fact that I can pack two four-bit numbers into the same storage as an eight-bit number. When I store that to memory, the sizing of the buses that I wire out within the chip makes that work out really nicely.

</details>

**Reiner Pope**: 仔细想想，它不仅仅是 2 倍。它所占用的面积似乎与**位长**成二次方关系。这就是为什么更小的精度比你想象的更有利。这是一个非常重要的原因。事实上，Nvidia 做出了一项改变。从历史上看，直到 **B100** 或 **B200**，每次将位精度减半，**FLOP** 计数就会翻倍。由于你所说的原因，因为这种二次方缩放，这个比例实际上略有错误。你应该获得比你想象的更大的加速。Nvidia 的产品规格在 **B300** 及更高版本中已经开始承认这一点，其中 FP4 比 FP8 快三倍。尽管它应该是 4 倍。

<details>
<summary>Original English</summary>

**Reiner Pope**: Come to think of it, it's not just 2x. The amount of area it takes sounds like it's quadratic with the bit length. That's why smaller precision is even more favorable than you might think. This is a really big reason. In fact, Nvidia made a change. Historically, up until B100 or B200, every time you halved the bit precision, you doubled the FLOP count. For the reason you said, because of this quadratic scaling, that ratio is actually slightly wrong. You should get an even bigger speedup than you might otherwise think. Nvidia’s product specs have started acknowledging that in B300 and beyond, where the FP4 is three times faster than the FP8. Though it should be 4x.

</details>

**Reiner Pope**: 是的。我在这里展示的是整数乘法的最简单情况。当你处理 FP4 和 FP8 中的**浮点数**时，还有一个术语，即**指数**，它使计算复杂化。我们从中能看到什么？我认为你已经得出的一个重要观察是，位宽存在这种**二次方缩放**，这非常有效，也是**低精度算术**在神经网络中表现如此出色的唯一原因。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. What I've shown here is the simplest case of integer multiply. When you're dealing with floating point, as you do in FP4 and FP8, there's this other term, the exponent, that complicates the calculation. What can we see already from this? I think the big observation you've made is that there's this quadratic scaling with bit width, which is very effective and is the single reason low-precision arithmetic has worked so well for neural nets.

</details>

### 数据移动与计算单元的成本

**Reiner Pope**: 我们现在要做的另一件事是比较乘法本身所花费的面积与所有围绕它的电路。我们将回顾一下过去，看看 **Tensor Cores** 之前的 **GPU** 是如何工作的，这实际上与 **CPU** 的工作方式相同。我们将把这个乘加单元放在哪里？

<details>
<summary>Original English</summary>

**Reiner Pope**: The other thing we're going to do now is compare the area spent on the multiplication itself with all the circuitry around it. We'll walk back in time a little bit and see how GPUs prior to Tensor Cores worked, which is in fact the same way CPUs worked. Where do we stick this multiply-accumulate unit?

</details>

**Reiner Pope**: 笼统地说，我将描述一个 **CUDA core** 或一个 CPU。你将拥有一个**寄存器文件**，其中存储了一些条目，例如八个条目，在这种情况下是四位数字，但通常是 32 位数字。在 CUDA core 内部，我将有一个具有一定深度的寄存器文件，然后我将拥有我的乘加电路。它将从这个寄存器文件中获取三个任意寄存器，执行乘加运算，然后写回寄存器文件。它将写入这个寄存器，但它可以从这个、这个以及另一个随机寄存器中读取。它将接收三个这样的输入。这是许多处理器的核心**数据通路**。大多数处理器都是这样。你有一些寄存器组，然后你有一些逻辑单元，或者说 **ALU**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Generically, I'll describe a CUDA core or a CPU. You'll have some register file which stores some number of entries, maybe eight entries of, in this case, 4-bit numbers, but typically 32-bit numbers. Inside the CUDA core, I'll have some register file of some depth, and then I'll have my multiply-accumulate circuit. What it's going to do is take three arbitrary registers from this register file, perform the multiply-accumulate, and then write back to the register file. It's going to write to this one, but it was able to read from this one, this one, and another random one. It will take three inputs like this. This is the core data path of many processors. Most processors look like this. You've got some set of registers, and then you've got some set of logic units, or ALUs.

</details>

**Reiner Pope**: 我们想分析从寄存器文件到 ALU 再返回的数据移动成本。最终，会有一个电路说：“我并非总是必须选择这个。我可能在任何时间点选择任何一个寄存器。”第一个问题是：我如何构建一个电路？我要寻找的电路是**多路复用器**（**mux**）。在这种情况下，它将有八个输入，每个输入来自寄存器文件的一个条目，并且它将有一个输出，实际上产生这个输出。

<details>
<summary>Original English</summary>

**Reiner Pope**: We want to analyze the cost of the data movement from the register file to the ALU and back. Ultimately, there's going to be some circuit that says, "Well, I don't always have to select this guy. I might select any of the registers at any point in time." The first question is: how can I build a circuit? The circuit I'm going to look for is a mux. In this case, it's going to have eight inputs, one from each entry of the register file, and it's going to have one output, which is actually producing this output.

</details>

**Dwarkesh**: 这个东西的成本是多少？

<details>
<summary>Original English</summary>

**Dwarkesh**: What is the cost of this thing?

</details>

**Reiner Pope**: 我们必须用 AND 和 OR 来构建它。我们如何构建它？我们做最笨的事情。我们形成一个**掩码**。当我们要读取第三个条目时，我们将每个条目与 1 或 0 进行 AND 运算，取决于我们是否要读取它，然后我们将所有条目进行 OR 运算。

<details>
<summary>Original English</summary>

**Reiner Pope**: All we have to build it out of is AND and OR. How do we build it? We do the dumbest thing possible. We form a mask. When we want to read the third entry, we're going to AND every single entry with either 1 or 0 based on whether that's what we want to read, and then we're going to OR all of them together.

</details>

**Dwarkesh**: 只是为了确保我理解基本原理。多路复用器只是选择一个输入吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Just to make sure I understand the basics. What the mux is doing is just selecting an input?

</details>

**Reiner Pope**: 只是选择，对软件不可见。你说“我想要输入三”，这意味着这里有一个多路复用器。

<details>
<summary>Original English</summary>

**Reiner Pope**: Just selecting, invisible to software. You say "I want input number three," and that means there's a mux here.

</details>

**Reiner Pope**: 那么这个多路复用器的成本是多少？一个 N 输入的多路复用器，作用于 P 位。我有 N 行。这只是八行，每行 P 位宽。我必须对每个位进行 AND 运算，所以我有 N 乘以 P 个 AND 门。对于每个输入，我必须决定是否将其屏蔽掉。然后我将它们全部进行 OR 运算。将有 (N-1) 乘以 P 个 OR 门。我有很多不同的东西，几乎所有都是 0，但我需要将它们从八个选项合并为一个选项。每一步，我都需要将一行 OR 到现有的一行中。

<details>
<summary>Original English</summary>

**Reiner Pope**: So what is the cost of this mux? An n-input mux operating on p bits. I have n rows. That's just eight rows, and each row is p bits wide. I have to AND every single bit, so I get n x p many AND gates. For every single input I have to decide whether I'm going to mask it out or not. Then I'm going to OR them all together. There's going to be n – 1 times p many OR gates. I've got all of these different things, almost all of them are 0s, but I need to collapse them from my eight options down into one option. Every step, I need to OR one row into an existing row.

</details>

**Dwarkesh**: 有趣的是，你不会从硬件层面去思考。你只是想，“哦，我选择元素三，”而像这样简单的事情本身就是一个相当复杂的电路。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's actually funny that you don't think at the level of hardware. You just think, "Oh, I'll just select element three," and something as simple as that is in and of itself quite a complicated circuit.

</details>

**Reiner Pope**: 这是所有隐藏的**数据移动成本**的第一步。我们只是进行比较。我必须支付这个成本。我这里有一个多路复用器，实际上我还有另外两个副本，用于我的乘加操作的三个输入中的每一个。我这里有 3 乘以 N 乘以 P 个 AND 门的成本，而实际执行我关心的操作的电路中只有 P 乘以 Q 个门。如果我们代入实际数字，N 为 8，那么仅在数据移动中我就有 24 乘以 P 个门，而如果 Q 为 4，则乘法加法器中只有 4 乘以 P 个门。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is the first step of all of the hidden data movement costs that show up. We're just going to compare. I have to pay this cost. I've got one mux here, and in fact I have two more copies of that for each of the three inputs to my multiply-accumulate operation. I have this cost, which is 3 x n x p AND gates over here, compared to p x q gates in the actual circuit that is doing the thing I care about. If we plug in actual numbers, with n being eight, I get 24 x p gates just in the data movement, compared to—if q is four—4 x p gates just in the multiply-adder.

</details>

**Dwarkesh**: 那个 3 是从哪里来的？

<details>
<summary>Original English</summary>

**Dwarkesh**: Where is the three coming from?

</details>

**Reiner Pope**: 这里的三个不同的输入。我暗示的是，所有这些工作，它随着寄存器文件的大小而扩展——这是一个非常小的寄存器文件——所有这些从寄存器文件到逻辑单元的数据移动工作，其成本远高于逻辑单元。

<details>
<summary>Original English</summary>

**Reiner Pope**: Three different inputs here. What I'm hinting at is that all of this work, which scales as the size of the register file—and this is a very small register file—all of this work just moving the data from the register file to the logic unit is many, many times more expensive than the logic unit.

</details>

### 多路复用器的示例与成本分析

**Reiner Pope**: 在最近的 ClusterMAX 报告中，**SemiAnalysis** 对近 100 家不同的 GPU 云进行了排名。**Crusoe** 是仅有的五家获得金牌评级的公司之一。SemiAnalysis 发现，像 Crusoe 这样的金牌级提供商的总拥有成本比银牌级提供商低 5% 到 15%，即使它们的 GPU 定价相同。这很有道理，因为总拥有成本受到许多不同因素的影响，这些因素不一定体现在标价中，但 Crusoe 已经对其进行了优化。例如，你检测故障的能力以及你替换故障节点的速度。

<details>
<summary>Original English</summary>

**Reiner Pope**: In the most recent ClusterMAX report, SemiAnalysis ranked almost 100 different GPU clouds. Crusoe was one of only five that made the gold tier. SemiAnalysis found that gold-tier providers like Crusoe had a total cost of ownership that was 5% to 15% lower than silver-tier ones, even when they had identical GPU pricing. This makes sense because total cost of ownership is downstream of a bunch of different things that don't necessarily show up in the sticker price, but that Crusoe has optimized. Things like how well you detect faults and how quickly you replace failed nodes.

</details>

**Reiner Pope**: 例如，Crusoe 是首批采用 **NVSentinel** 的云服务商之一，NVSentinel 是 **NVIDIA** 自己的 GPU 监控和自修复软件，旨在提高 GPU 的正常运行时间、利用率和可靠性。这使得 Crusoe 能够利用 NVIDIA 从其所有不同队列和部署中了解到的芯片故障原因，从而使 Crusoe 能够更早地发现故障。一旦发现故障，Crusoe 可以在不到 10 分钟内换上一个健康的节点。由于他们没有运行裸机，Crusoe 无需花费时间安装操作系统或配置驱动程序。他们可以在一个已经运行且预先认证的主机上启动一个新的虚拟机。如果你想了解更多关于这方面的信息，或者 Crusoe 获得金牌评级的其他原因，请访问 **crusoe.ai/dwarkesh**。

<details>
<summary>Original English</summary>

**Reiner Pope**: For example, Crusoe was one of the first clouds to adopt NVSentinel, NVIDIA's own GPU monitoring and self-healing software for enhanced GPU uptime, utilization, and reliability. This lets Crusoe make use of everything that NVIDIA has learned about why chips fail across all their different fleets and deployments, so that Crusoe can catch faults earlier in the process. And once they identify a failure, Crusoe can swap in a healthy node in less than 10 minutes. Because they’re not running bare metal, Crusoe doesn't have to spend time installing an operating system or configuring drivers. They can just spin up a new VM on an already running and pre-qualified host. If you want to learn more about this or the other reasons that Crusoe made gold tier, go to crusoe.ai/dwarkesh.

</details>

**Dwarkesh**: 也许看看多路复用器是什么样子，一个两位或四位多路复用器，会有帮助。

<details>
<summary>Original English</summary>

**Dwarkesh**: It may be helpful to just see what a mux looks like, maybe a two-bit or a four-bit mux.

</details>

**Reiner Pope**: 我们将做一个双向多路复用器。我们有两个不同的数字，有两个输入。这些是正在选择的输入，选择器可以是“我想要这个”或“我想要另一个”。这是一种**独热编码**。这就是我们开始的地方。

<details>
<summary>Original English</summary>

**Reiner Pope**: We’ll do a two-way mux. We've got two different numbers, we’ve got these two inputs. These are the inputs that are being selected between, and the selector can either be "I want this one" or "I want the other one." This is a one-hot encoding. This is what we start with.

</details>

**Reiner Pope**: 让我们关注这个案例。这是我们得到的实际输入，我们想要产生这个结果。非常费力地，我们将这个位与所有这些进行 AND 运算。这会产生将这个位与这一行进行 AND 运算的结果。同样，我们将这个位与这一行进行 AND 运算。这会产生全 0。这里有四个 AND 门。最后，我们将这两个进行 OR 运算，结果得到一个 1。我们将这两个进行 OR 运算，结果得到一个 1。我们将这两个进行 OR 运算，结果得到一个 0。我们将这两个进行 OR 运算，结果得到一个 1。这就是四个 OR 门。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's focus on this case. This is the actual input we got, and we want to produce this guy as the result. Very laboriously, we AND this bit with all of these. That produces ANDing this bit with this row. Likewise, we AND this bit with this row. That produces all 0s. There are four ANDs here. Finally, we OR these two together, and this gives a 1. We OR these two together, this gives a 1. We OR these two together, it gives a 0. We OR these two together and it gives a 1. Those are the four ORs.

</details>

**Reiner Pope**: 这实际上有点像加法。我们做了完全相同的 AND 运算。我们将所有这些东西都进行了 AND 运算，但随后没有使用全加器电路来折叠它，而是使用 OR 门进行了非常简单的折叠。但这看起来不像 N 乘以 P。这是 N 等于 2 个输入的情况。在一般情况下，我们将有 N 行，每行有 P 位。这给了我们 N 乘以 P 个 AND 门。在我描述的这个电路中，几乎所有成本，即七分之八的成本，都用于读取和写入寄存器文件，而只有一小部分成本用于逻辑单元本身。

<details>
<summary>Original English</summary>

**Reiner Pope**: This actually ends up looking a little bit like addition. We did exactly the same set of ANDs. We've ANDed all of these things together, but then instead of collapsing it by using full adder circuits, we just get a very simple collapsing with OR gates. But that doesn't look like n times p. This was with n=2 inputs. In the general case, we will have n rows, and we'll have p bits per row. That gives us the n times p many AND gates. In this circuit I've described, almost all of the cost, seven-eighths of the cost, is in reading and writing the register file, and only a tiny fraction of the cost is in the logic unit itself.

</details>

**Reiner Pope**: 这就是需要解决的问题。这本质上是 Nvidia GPU **Volta** 代之前的状态。这种东西就是 CUDA core 内部的结构。正是这个问题的提出促使了 **Tensor Cores** 的引入，它们更一般地被称为**脉动阵列**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is the problem to solve. This essentially was the state of play prior to the Volta generation of Nvidia GPUs. This kind of thing is what was inside the CUDA cores. This problem statement is what motivated the introduction of Tensor Cores, which are more generically called systolic arrays.

</details>

### 脉动阵列与计算通信权衡

**Reiner Pope**: 思考一下我们将如何解决这个问题。我们几乎将所有电路面积都花在了我们并不真正关心且对软件程序员隐藏的东西上，而我们真正关心的东西却不占太多面积。目标是设法在保持这个大小不变的情况下，让这个变得更大。

<details>
<summary>Original English</summary>

**Reiner Pope**: Think about how we're going to solve this problem. We're spending almost all of our circuit area on something that we really don't care about and is hidden to the software programmer, and the thing that we actually care about is not much of the area. Make this one bigger somehow while keeping this at the same size. That's the goal.

</details>

**Reiner Pope**: 演变是，我们在这个阶段已经将这么多功能内置到硬件中。这一行是一个乘加运算，而这一项是内置到硬件中的。脉动阵列的理念是向上推进两个循环级别，并将整个循环内置到硬件中。

<details>
<summary>Original English</summary>

**Reiner Pope**: The evolution was that we had baked this much into hardware at this stage. This single line is a multiply-accumulate, and this single thing was baked into hardware. The idea of a systolic array is to go two levels of loops up and bake this entire loop out here into hardware.

</details>

**Reiner Pope**: 这个想法是，如果我们有一个更大粒度的**固定功能逻辑**块，那么我们在输入和输出上支付的“税费”可能会小得多。

<details>
<summary>Original English</summary>

**Reiner Pope**: The idea is that if we have a much bigger granularity fixed-function piece of logic, maybe the taxes we pay on the input and output are much smaller.

</details>

**Dwarkesh**: 有趣。听起来你是在建议，如果你在矩阵乘法循环中向上移动一步，你可以将平衡更多地倾向于计算而不是通信。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. It sounds like you're suggesting that if you go up one step in the matrix multiply loop, you can tilt the balance more towards compute than communication.

</details>

**Reiner Pope**: 对。我们将利用这里的两个效应。一是我们可以通过寄存器文件的每次传输做更多的事情。二是，在这个循环的某些部分，我们可以利用某些东西保持不变的优势。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. There are two effects we're going to take advantage of here. One is that we can do more stuff per every trip through our register file. The other is that in some of this loop, we can take advantage of certain things staying fixed.

</details>

**Reiner Pope**: 从视觉上看，我们将研究这个**矩阵乘法**。循环的这部分对应于**矩阵向量乘法**。我们将取一个矩阵并将其乘以一个向量。我们如何做到这一点？每一列都乘以向量然后求和。我们将沿着列求和。这个 0 和 3 乘以 3 和 7 然后求和，然后 1 和 2 乘以 3 和 7 然后求和。矩阵中的每个条目都与乘加运算相关联。我们将画出这四个乘加运算。

<details>
<summary>Original English</summary>

**Reiner Pope**: Visually, we're going to look at this matrix multiplication. This portion of the loop corresponds to a matrix-vector multiplication. We'll take a matrix and multiply it by a vector. How do we do this? Every column gets multiplied by the vector and then summed. We're going to sum along columns. This 0 and 3 gets multiplied by the 3 and 7 and gets summed, and then the 1 and 2 gets multiplied by the 3 and 7 and gets summed. There is a multiply-accumulate associated with every single one of these entries in the matrix. We'll draw out these four multiply-accumulates.

</details>

**Dwarkesh**: 只是为了确保我理解为什么有四个乘加运算：输出向量对应的列中的每个条目都是一个**点积**，在这种情况下，它将是两次乘法然后是这两个乘法的加法。你正在累加……

<details>
<summary>Original English</summary>

**Dwarkesh**: Just to make sure I understand why there are four multiply-accumulates: each entry in the column that corresponds to the output vector is a dot product, and in this case it will be two multiplications and then the addition of those two multiplications. You're accumulating...

</details>

**Reiner Pope**: 实际上每个点积只有一个加法，但我们喜欢从零开始。但它包括零的初始化。

<details>
<summary>Original English</summary>

**Reiner Pope**: Really there's only one addition per dot product, but we like to start with zero. But it includes the initialization of zero.

</details>

**Reiner Pope**: 是的。我们希望有平方级的更多计算。我们有 X 乘以 Y 倍于以前的计算量。但我们希望只拥有 X 倍的通信量。目的是让这个优势项以 Y 的形式发挥作用。我们已经安排了乘法。我们想要引入一个大小为 2 的向量，这已经符合我们的列目标。这很好。但是，我们需要管理这个矩阵的通信，这超出了我们的 X 预算。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. We want to have quadratically more compute. We have x times y as much compute as we had before. But we want to aim for having only x times as much communication. The intention is to get this advantage term going as y. We've laid down the multiplications. We want to bring in a vector of size two, and that is already in line with our columns target. That's fine. However, we need to manage the communication of this matrix, which exceeds our budget of x.

</details>

**Reiner Pope**: 这个想法是，在 AI 环境中，这个矩阵会长时间保持不变。我们这里有一些寄存器文件。从这个寄存器文件出来的数据量……这在某种意义上是我们希望达到 X 的项。我们不希望每个周期都从寄存器文件中完整地引入这个矩阵，因为那样从寄存器文件到连线的成本太高。

<details>
<summary>Original English</summary>

**Reiner Pope**: The idea is that in an AI context, this matrix is going to stay fixed for a long period of time. We've got some register files sitting over here. The amount of stuff coming out of this register file… this is the term that we want to go as x, in some sense. We don't want to bring this full matrix in from the register file every cycle, because that would cost too much in terms of wiring from the register file.

</details>

**Reiner Pope**: 我们的关键技巧是，这个矩阵可以局部存储在**脉动阵列**中。我们将这些数字 0、1、2 和 3 存储在一个名为**寄存器**的门中，它物理地存储这些数字，我们将一次又一次地重复使用这些数字，用于大量的不同向量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Our key trick is that this matrix can be stored locally to the systolic array. We'll store these numbers 0, 1, 2, and 3 in a gate called a register that physically stores these numbers, and we're going to reuse these numbers over and over again for a large number of different vectors.

</details>

**Dwarkesh**: 这里的优化是，矩阵乘法的性质是你可以将这个方形的二次方事物直接存储在逻辑发生的地方，它与你不断交换进出的输入相比，多了一个维度。

<details>
<summary>Original English</summary>

**Dwarkesh**: The optimization here is that the nature of matrix multiplication is that you can store this square quadratic thing directly where the logic is happening, which has an extra dimension compared to the inputs that you keep swapping in and out.

</details>

**Reiner Pope**: 对。这就是矩阵乘法的本质。你进行大量的乘法才能得到一个值。一个点积是大量乘法的结果。

<details>
<summary>Original English</summary>

**Reiner Pope**: That’s right. This is the nature of what a matrix multiplication is. You do a lot of multiplication to get one value out. A dot product is the result of a lot of multiplications.

</details>

**Dwarkesh**: 所以这个优化意味着你可以在得到一些值之前，先塞入大量的乘法。

<details>
<summary>Original English</summary>

**Dwarkesh**: So that optimization means you can stuff a lot of multiplication in before you get some value out of it.

</details>

**Reiner Pope**: 对。只是为了具体地完成这个图景：我在这里交换了 3 和 2。就像这个 0 和 3 将要乘以 3 和 7 一样，我们将在列中形成一个点积。我们将在这里输入 3 和 7。这会进入这个乘法，也会进入这个乘法。同样，3 会进入这里，也会进入这里。然后我们将在沿着这里求和。从一列的顶部开始，我们输入 0，然后从底部得到结果。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. Just to complete the picture of concretely how that looks: I swapped the 3 and the 2 here. Just like this 0 and 3 is going to multiply by the 3 and the 7, we're going to form a dot product along columns here. We're going to feed a 3 and a 7 in here. This feeds into this multiplication and also feeds into this multiplication. Likewise, the 3 feeds into here and also into here. Then we're going to sum along here. Starting at the top of a column, we feed in 0s, and then coming out the bottom we get results.

</details>

**Reiner Pope**: 从视觉上看，矩阵中沿着列执行点积，这与脉动阵列中空间上所做的完全一致。这是一个垂直求和的点积，这是第二个垂直求和的点积。

<details>
<summary>Original English</summary>

**Reiner Pope**: Visually, there's a dot product performed along columns in a matrix, and that maps exactly to what is done spatially in the systolic array. This is one dot product summed vertically, and this is a second dot product also summed vertically.

</details>

### 权重矩阵的本地存储与数据传输

**Dwarkesh**: 需要进出寄存器文件的数据是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: What is the data that needs to go into and out of the register file?

</details>

**Reiner Pope**: 我们有 X 量的数据从输出端出来，我们也有 X 量的数据从输入端进来。至少就输入和输出向量而言，我们已经达到了我们的目标，即只有 X 量的数据进出寄存器文件。这留下了一个问题：我说**权重矩阵**局部存储在脉动阵列中，那么它最初是如何进入那里的呢？在某个时候，你需要启动你的芯片并填充这些数据，那么这些数据是从哪里来的？

<details>
<summary>Original English</summary>

**Reiner Pope**: We have x amount of data coming out on the output, and we also have x amount of data coming from the input. With respect to the input and output vectors at least, we've met our goal of having only x as much data going in and out of the register file. This leaves open the question: I said the weight matrix is stored locally in the systolic array, so how did it get there in the first place? At some point, you need to boot your chip and populate this data, so where did that come from?

</details>

**Reiner Pope**: 诀窍在于我们只是非常缓慢地进行。我们非常缓慢地将它涓流式地输入脉动阵列。最简单的策略是我们运行这个**菊花链**：在这里输入一个数字，在下一个**时钟周期**，它将向下移动到脉动阵列的下一个条目。我们可以在每一列中并行执行此操作，这也将从这里来，这又给我们带来了大约 X 单位的带宽。

<details>
<summary>Original English</summary>

**Reiner Pope**: The trick is that we just do it very slowly. We very slowly trickle-feed it into the systolic array. The simplest strategy is that we run this daisy chain: feed a number in here, and on the next clock cycle it will move down to the next entry of the systolic array. We can do that in every column in parallel, this is also going to come from here, and that gives us another factor of approximately x units of bandwidth coming in.

</details>

**Dwarkesh**: 你介意再重复一遍这句话吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Would you mind repeating that sentence one more time?

</details>

**Reiner Pope**: 我们知道我们只会很少地将数字带入矩阵。我们只想提出任何一种构造，使得跨越脉动阵列边界的**布线量**被限制在 X 而不是 XY。一个特别简单的策略是，我们在一个时钟周期内将一个数字带入脉动阵列的顶行。然后，在 Y 个连续的时钟周期内，我们每次都引入顶行，并将所有其他行向下移动一位。这使得来自这个昂贵的寄存器文件的布线只受限于 X 因子，而不是 XY。

<details>
<summary>Original English</summary>

**Reiner Pope**: We know that we're going to be bringing numbers only rarely into the matrix. We just want to come up with any construction at all such that the amount of wiring that crosses the boundary of the systolic array is bounded to x and not go as xy. A particularly simple strategy is that we bring a number into the top row of the systolic array in one clock cycle. Then, for y consecutive clock cycles, we bring in the top row every time and shift all the other rows down by one. This keeps the wiring that needs to come from this expensive register file only down to a factor of x rather than xy.

</details>

**Dwarkesh**: 我明白了。在通信方面有两个问题：通信时间**和**通信带宽**。你是说既然我们只加载一次，那么就尽量减少带宽，因为带宽等于芯片面积。我们通过较小的通道缓慢加载，因为我们将把这个值保留一段时间。

<details>
<summary>Original English</summary>

**Dwarkesh**: I see. There are two questions in terms of communication: communication time and communication bandwidth. You're saying that since we're only going to be loading this in once, let's minimize bandwidth, because bandwidth equals die area. We load it in slowly over smaller lanes because we're just going to keep this value in there for a while.

</details>

**Reiner Pope**: 完全正确。

<details>
<summary>Original English</summary>

**Reiner Pope**: Exactly.

</details>

### 计算与通信的普遍权衡

**Dwarkesh**: 很有趣的是，我们上次谈到跨多个芯片进行推理时，我们试图优化的一个主要高层次目标是增加每个内存带宽的计算量，也就是说，每个通信的计算量。在这里，我们也在尝试增加实际乘法或加法的数量，相对于从寄存器到逻辑的**信息传输**。在这两种情况下，你都试图最大化计算量相对于通信量。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's interesting to me that when we were talking last time about inference across many chips, the big high-level thing we're trying to optimize for is increasing the amount of compute per memory bandwidth, that is to say, per communication. Here also, we're trying to increase the amount of actual multiplies or additions relative to transporting information from registers to the logic. In both cases, you're trying to maximize compute relative to communication.

</details>

**Reiner Pope**: 这在整个技术栈中都体现出来。这已经非常接近底层，接近于**逻辑门**。还有一个版本可能更接近逻辑门，即你选择的数字格式的精度。我们看到了同样的效果。在 ALU 的纯精度以及矩阵的大小方面，都存在平方与线性项。

<details>
<summary>Original English</summary>

**Reiner Pope**: This shows up all the way up and down the stack. This is close to the bottom, to the gates. There's a version that's maybe even closer to the gates in the precision of the number format that you choose to use. We saw that same effect. There's a squared versus linear term going on both purely in the precision of the ALU, but also in the size of the matrix.

</details>

**Reiner Pope**: 这个单元是下一个更大的单元。我们有乘法电路，在此之上我们有一个相当大的脉动阵列。我画的是 2x2，但较旧的 **TPU** 被描述为 128x128 的这种电路。这最终成为实现矩阵乘法最有效已知电路。

<details>
<summary>Original English</summary>

**Reiner Pope**: This unit is the next bigger unit. We had the multiplication circuit, and on top of that we have a pretty large systolic array. I drew it as 2x2, but older TPUs were described as 128x128 of this circuit shown here. This ends up being the most efficient known circuit for implementing a matrix multiply.

</details>

### 芯片设计中的非显而易见的权衡

**Reiner Pope**: 我们讨论了最大化计算量相对于通信量似乎是显而易见的。那么，有哪些非显而易见的权衡会让你夜不能寐，让你无法确定是选择 X 还是 Y 呢？

<details>
<summary>Original English</summary>

**Reiner Pope**: We've talked about how it seems obvious that you should try to maximize compute relative to communication. What are non-obvious trade-offs that keep you up at night, about whether you should do X or Y and it's not obvious what the answer is?

</details>

**Reiner Pope**: 芯片设计中的大多数决策都是尺寸决策。即使在我们目前绘制的范围之内……AI 芯片都包含这个电路。它们有一个脉动阵列，并且附近有一个提供输入和输出的寄存器文件。即使在这个范围内，你所面临的尺寸问题是：我应该将我的脉动阵列做得多大，以及我的寄存器文件应该做得多大？这两个问题是相互关联的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Most of the decisions in chip design are sizing decisions. Already in what we've drawn so far… AI chips all have this circuit in them. They have a systolic array, and somewhere near it a register file providing inputs and outputs. Even within this scope, the sizing questions you have are: how big should I make my systolic array, and how big should I make the register file? These two questions are coupled.

</details>

**Reiner Pope**: 一种思考方式是为芯片面积中用于**数据移动**的百分比设定一个预算。也许我说我希望这个占 10%，脉动阵列占 90%。然后我可以调整我的寄存器文件大小。更大的寄存器文件更灵活。它们允许我获得更高的**应用级性能**，但它们会占用脉动阵列的面积。

<details>
<summary>Original English</summary>

**Reiner Pope**: One way to think of it is to set a budget for what percentage of chip area you want to spend on data movement. Maybe I say that I want this to be 10% and the systolic array to be 90%. Then I can size my register file. Bigger register files are more flexible. They allow me to get more application-level performance out, but they take away from the area spent on the systolic array.

</details>

### Cursor：AI辅助工作平台

**Reiner Pope**: 我最近举办了一场征文比赛，我请人们写下我认为是关于 AI 的一些最大开放问题。提交窗口上周关闭了，所以我使用 **Cursor** 创建了几个不同的界面来帮助我审查参赛作品。一个界面匿名化提交，并隐藏了必要的信息。它让我可以按问题对回复进行分组，添加笔记，并记录我的分数。另一个界面帮助我审查那些也想被考虑担任我正在招聘的研究员角色的参赛者。用户界面将申请人的文章放在他们的简历和个人网站旁边，这样我就可以一次看到所有内容。Cursor 的线束非常擅长帮助这些模型查看和改进他们的用户界面。我看着它在内置浏览器中渲染这些界面，截取屏幕截图，点击不同部分，并不断迭代。

<details>
<summary>Original English</summary>

**Reiner Pope**: I recently ran an essay contest where I asked people to write about what I consider to be some of the biggest open questions about AI. The submission window closed last week, so I used Cursor to create a couple of different interfaces to help me review the entries. One interface anonymizes submissions and hides the necessary information. It lets me group responses by question, add notes, and record my scores. The other interface helps me review entrants who also want to be considered for the researcher role that I'm hiring for. The UI puts the applicant's essay right next to their resume and their personal website so that I can see everything at once. Cursor's harness is really good at helping these models see and improve their UIs. I watched it render these interfaces in the built-in browser, take screenshots, click through sections, and keep iterating.

</details>

**Reiner Pope**: 到目前为止，Cursor 是我大部分工作的地方。无论我是在阅读和可视化一堆研究论文，还是编写一个界面来审查应用程序，或者为我的黑板讲座制作闪卡，Cursor 都让 AI 很容易看到我正在看的东西，并帮助我理解它并与我一起工作。所以无论你正在做什么，都应该在 Cursor 中完成。请访问 **cursor.com/dwarkesh**。

<details>
<summary>Original English</summary>

**Reiner Pope**: At this point, Cursor is where I do most of my work. Whether I'm reading and visualizing a bunch of research papers, or coding up an interface to review applications, or making flashcards for my blackboard lectures, Cursor just makes it very easy for an AI to look at whatever I'm looking at and help me understand it and work with me on it. So whatever you're working on, you should do it in Cursor. Go to cursor.com/dwarkesh.

</details>

### 芯片时钟周期与同步

**Dwarkesh**: 芯片的**时钟周期**是如何产生的？什么决定了它？芯片的时钟周期又是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: Where does the clock cycle of a chip come in? What determines what that is? And what is a clock cycle of a chip?

</details>

**Reiner Pope**: 首先，值得注意的是芯片具有令人难以置信的并行性。一个芯片中有 1000 亿个**晶体管**。每当你有大规模并行性时，你需要做的一件关键事情就是在不同的并行单元之间进行**同步**。在软件中，你通常有非常昂贵的同步方法，比如**互斥锁**。一个线程完成它的工作，获取存储在内存中的锁，然后通知另一个线程它已经完成。在芯片上，我们采取了非常不同的方法。

<details>
<summary>Original English</summary>

**Reiner Pope**: At baseline, it's worth observing that chips are incredibly parallel. You've got 100 billion transistors in a chip. A key thing you need to do whenever you have massive parallelism is synchronize between the different parallel units. In software, typically you have these very expensive synchronization methods like a mutex. One thread will finish what it's doing, grab a lock stored somewhere in memory, and notify the other thread that it's done. On chips, we take a very different approach.

</details>

**Reiner Pope**: 大约每纳秒左右，芯片中的所有电路都会暂停片刻并同步。这就是**时钟周期**。整个芯片通常会同步执行下一个操作。这在电路中表现为时钟由我们绘制在其他地方的**寄存器**介导，这些是存储设备。可以这样理解：我有一些存储设备，存储一个位，可能是 0 或 1。然后我有一个逻辑云，可能就是这个脉动阵列或乘法器。我有一堆输入馈入这个逻辑云，最终会有一个输出寄存器写入。有一个**全局时钟信号**驱动所有这些寄存器。在某个时刻，当时钟到来时，那一瞬间电线上的任何值都会被存储。

<details>
<summary>Original English</summary>

**Reiner Pope**: Every nanosecond or so, all circuitry in the chip will pause for a moment and synchronize. That is the clock cycle. The entire chip typically goes in lockstep to the next operation in one fell swoop. What this looks like in circuitry is that the clock is mediated by registers, which are these storage devices we've drawn elsewhere. The way to think of it is: I have some storage holding a bit, which might be 0 or 1. Then I have some cloud of logic, which maybe is this systolic array or multiplier. I have a bunch of inputs feeding into this cloud of logic, and eventually there's going to be some output register that it writes to. There is a global clock signal driving all these registers. At a certain instance in time, when the clock strikes, whatever value happens to be on that wire at that instant is what gets stored.

</details>

**Reiner Pope**: 挑战在于我希望我的**时钟速度**尽可能快。如果我以两千兆赫运行，我每秒完成的操作是如果我以一千兆赫运行的两倍。但这意味着我对这个逻辑云的延迟非常敏感，因为其中发生的任何计算都需要在下一个时钟周期到来之前完成。任何芯片上的一个主要优化点就是使这个延迟尽可能短。

<details>
<summary>Original English</summary>

**Reiner Pope**: The challenge is that I would like to have my clock speed run as fast as possible. If I run at two gigahertz, I get twice as many operations done per second as if I run at one gigahertz. But what that ends up meaning is that I'm very sensitive to the delay through this cloud of logic, because any computation happening in there needs to finish before the next clock cycle hits. A major point of optimization on any chip is to make this delay as short as possible.

</details>

**Dwarkesh**: 有趣。这里的限制似乎是，如果添加太多逻辑，可能会错过时钟周期。但如果添加不够，就会浪费潜在的计算能力。是否存在一种情况，你冒险进行概率性计算，或者严格来说，它要么在时钟周期内完成，要么不完成？

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. The constraint here seems to be that if you add too much logic, you might risk missing the clock cycle. But if you don't add enough, you're leaving potential compute on the table. Is there ever a situation where you take a probabilistic chance that a computation finishes, or is it strictly that it either finishes by the clock cycle or it doesn't?

</details>

**Reiner Pope**: 在标准芯片设计中，你会预留足够的裕度，使其存在概率，但这已经超出了许多**标准差**。从所有意图和目的来看，它是一个可靠的部分，并且将始终符合时钟。有一些奇怪的例外，比如**时钟域交叉**，当你从一个时钟域转换到另一个时钟域时。那时你确实需要考虑这种概率。但在主路径中，你会预留足够的裕度，使其提前 25% 的时钟周期到达，从而使其错过时钟的概率非常小。

<details>
<summary>Original English</summary>

**Reiner Pope**: In standard chip design, you margin it such that there is a probability, but it's many standard deviations out. For all intents and purposes, it is a reliable part and will always meet the clock. There are some weird exceptions, like clock domain crossings where you go from one clock to another. Then you actually do have to reason about this probability. But in the main path, you margin it such that you'll get there 25% of the clock cycle in advance, making it very unlikely that it misses.

</details>

### 时钟同步与流水线寄存器

**Dwarkesh**: 时钟同步的位置，寄存器所在的位置，这是由芯片设计师决定的吗？或者这是一种人工产物，你想要某个逻辑序列，而你用来将你的 **Verilog** 转换为发送给 **TSMC** 的软件只是决定了为了使其工作，你必须在这里、这里和这里放置一个寄存器，确保没有单个步骤使整个芯片的时钟周期比它必须的更长？

<details>
<summary>Original English</summary>

**Dwarkesh**: Where the clocks synchronize, where the registers are, is this something you determine as a chip designer? Or is it an artifact where you want a certain sequence of logic, and the software you use to convert your Verilog into what you send to TSMC just determines that to make it work, you have to put a register here, here, and here, making sure no single step makes the whole chip's clock cycle longer than it has to be?

</details>

**Reiner Pope**: 插入它们实际上是设计芯片工作的一个重要部分。它是通过手动和自动方法相结合来完成的。为了展示你可以做到的非常简单的版本，你可以将这个逻辑一分为二。我不再只有一个逻辑云，而是可以有两个更小的逻辑云，它们做同样的事情，但通过一个寄存器将它们分开。如果你在中间分割，你可以达到两倍的**时钟频率**。这很棒，你获得了两倍的性能，但代价是一个额外的寄存器，这意味着更多的存储。

<details>
<summary>Original English</summary>

**Reiner Pope**: Inserting them is actually a huge part of the work of designing a chip. It's done by a combination of manual and automatic methods. To show the very dumb version of what you can do here, you can take this logic and split it in half. Instead of just one cloud of logic, I can have two smaller clouds of logic that do the same thing, but split them up by a register. If you split it in the middle, you can hit twice the clock frequency. That's great, you get twice the performance, but at the cost of an extra register, which means more storage.

</details>

**Dwarkesh**: 退一步说，为什么我们需要同步整个芯片？如果你想象玩 **Factorio** 或类似游戏，没有全局时钟周期。事情只是在完成后就完成了。铁板上有了铁，你可以拿走。

<details>
<summary>Original English</summary>

**Dwarkesh**: Stepping back, why do we need to synchronize the whole chip? If you imagine playing Factorio or something, there's no global clock cycle. Things are just done when they're done. There's iron on the plate, and you can take it if you want.

</details>

**Reiner Pope**: 借鉴这个类比，你需要注意的一点是，如果我有两条不同的逻辑路径。假设我在这里需要进行计算 f，在这里进行计算 g，它们将在计算 h 处汇合。将会存在**制造差异**。在某些芯片中，f 会花费更长时间；在某些芯片中，g 会花费更长时间。如果我有一个信号传播，并且 f 和 g 的结果必须在 h 处汇合，那么可能会出错的是 f 提前到达并遇到了 g 的前一个值，或者 g 的下一个值。

<details>
<summary>Original English</summary>

**Reiner Pope**: Taking that analogy, the thing you need to be mindful of is if I have two different paths through some logic. Say I have to do computation f here and computation g here, and they're going to meet for computation h. There's going to be manufacturing variance. In some chips f will take a little longer; in some chips g will take a little longer. If I have a signal propagating through, and the results from f and g have to meet up at h, what can go wrong is that f gets there early and it meets the previous value of g, or the next value of g.

</details>

**Dwarkesh**: 啊。而且 h 需要知道何时开始，何时进行下一次迭代……

<details>
<summary>Original English</summary>

**Dwarkesh**: Ah. And h needs to know when to start, when the next iteration has…

</details>

**Reiner Pope**: 完全正确。

<details>
<summary>Original English</summary>

**Reiner Pope**: Exactly.

</details>

**Reiner Pope**: 这解释了为什么在相同**制程节点**下制造的不同芯片，采用相同的 **TSMC** 技术，可以具有不同的时钟周期。在 3 纳米下制造的两个芯片可能具有不同的时钟周期，这取决于它们是否能够进行优化，以确保没有单个**关键路径**过长，从而减慢整个芯片的时钟周期。

<details>
<summary>Original English</summary>

**Reiner Pope**: This explains why different chips made at the same process node, the same TSMC technology, can have different clock cycles. Two chips made at 3 nm might have different clock cycles based on whether they were able to optimize to ensure no single critical path is so long that it slows down the whole chip's clock cycle.

</details>

**Reiner Pope**: 对。我在这里展示的这种优化称为**流水线寄存器插入**。我们在流水线中间插入了一个寄存器。这是一个纯粹在时钟速度和面积之间的权衡。那是简单的情况。还有更困难的情况。我画出了一个逻辑流水线，但在其他情况下，你可能有一些计算实际上是反馈给自身的。它运行一些函数 f，然后写回自身。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. This optimization I showed here is called pipeline register insertion. We've inserted a register in the middle of the pipeline. This is a pure trade-off between clock speed and area. That is the easy case. There is a harder case too. I drew out a pipeline of logic, but in other cases you may have some calculation which actually feeds back in on itself. It runs some function f and then writes back to itself.

</details>

**Reiner Pope**: 例如，这可能是一个加法，你每时钟周期添加一个数字。这个小电路本质上总结了在不同时钟周期呈现的所有数字。挑战是，如果这个加法花费太长时间，我能做什么？如果我试图在它的中间放置一个**流水线寄存器**，它会改变所进行的计算。

<details>
<summary>Original English</summary>

**Reiner Pope**: For example, this might be an addition where you're adding a number every clock cycle. This little circuit essentially sums all the numbers presented on different clock cycles. The challenge is, if this plus takes too long, what can I do? If I try to put a pipeline register right in the middle of it, it changes the computation that's done.

</details>

**Reiner Pope**: 我将最终得到两个不同的**运行总和**，而不是形成所有输入的运行总和。我将得到偶数的运行总和和奇数的运行总和。这个约束——我的逻辑中有一个循环，所有芯片都在某个地方有——是最难解决的问题，并且它决定了时钟周期。

<details>
<summary>Original English</summary>

**Reiner Pope**: Instead of forming a running sum of everything that comes in, I will actually have two different running sums. I'll end up with a running sum of the even numbers and a running sum of the odd numbers. This constraint—where I have a loop in my logic, which all chips have somewhere—is the hardest thing to address and sets the clock cycle.

</details>

**Dwarkesh**: 我不明白为什么会有问题。我甚至不确定在那里放置一个寄存器意味着什么。它是一种原子操作吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I don't understand why it would be a problem to have that. I'm not even sure what it would mean to have a register there. Is it a sort of atomic operation?

</details>

**Reiner Pope**: 嗯，加法并不是真正的原子操作。正如你刚刚演示的。它做了很多工作才完成求和。你可以进行这项工作的早期部分，在中间放置一个寄存器，然后进行这项工作的后期部分。

<details>
<summary>Original English</summary>

**Reiner Pope**: Well, plus is not really atomic. As you just demonstrated. It took a whole lot of work to do a summation. You can take the early parts of that work, stick a register in the middle, and then take the late parts of that work.

</details>

### TSMC PDK与高速时钟的代价

**Dwarkesh**: 好的。**TSMC** 提供一个 **PDK**，它规定了可以在芯片中使用的逻辑原语。由他们决定没有原语会大于他们希望工艺节点达到的时钟周期。但除此之外，难道不能只是从 TSMC 获取所有原语，并根据需要不断在它们之间添加寄存器，直到达到所需的时钟周期吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. TSMC offers a PDK which specifies the primitives of logic they can grant you in the chip. It's up to them to determine that no primitive is bigger than the clock cycle they're hoping a process node targets. But other than that, can't you just take all the primitives from TSMC and keep adding registers between them as much as needed until you get to your desired clock cycle?

</details>

**Reiner Pope**: 作为一名逻辑设计师，芯片架构师设定了时钟周期。例如，你从 TSMC 获得的**原语**通常是 AND 门或全加器。这很大程度上取决于电压和你选择的**库**，但通常你可以在一个时钟周期内顺序放置 10、20 或 30 个这样的原语。这些原语非常快，可能只有 10 **皮秒**。作为一名逻辑设计师，原则上，如果你只有一个寄存器和一个 AND 门在一个循环中，你可以获得令人难以置信的快时钟速度，超过四、五或六千兆赫。

<details>
<summary>Original English</summary>

**Reiner Pope**: As a logic designer, the chip architect sets the clock cycle. For example, the primitives you get from TSMC are on the order of AND gates or full adders. It depends a lot on voltage and which library you choose, but generally you can have about 10, 20, or 30 of these sequentially in a clock cycle. These primitives are very fast, maybe 10 picoseconds. As a logic designer, in principle, if you just had a register and an AND gate in a loop, you could get an insanely fast clock speed, more than four, five, or six gigahertz.

</details>

**Reiner Pope**: 但如果你看看这个非常简单的电路，以及你在这里花费的面积……这被称为一个**门等效尺寸**，所以面积单位是 1。这个东西的面积可能是 8 个单位。同样，你几乎所有的成本都变成了同步或通信成本，而不是实际的逻辑成本。这将会是你做得太过分的情况。你将时钟速度做得非常快，但代价是将几乎所有面积都花在了**流水线寄存器**上。

<details>
<summary>Original English</summary>

**Reiner Pope**: But if you take this really simple circuit and look at the area you're spending here… This is called one gate equivalent in size, so unit of one in area. This thing is maybe a unit of eight in area. Again, almost all your cost becomes synchronization or communication cost compared to the actual logic. This would be a case where you've gone too far. You've made your clock speed really fast at the cost of spending almost all of your area on pipeline registers.

</details>

**Dwarkesh**: 有趣。所以你暗示了一个动态，你可以拥有一个非常快的时钟速度，但你并没有完成太多工作。你可以有**低延迟**但**低吞吐量**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. So you're hinting at a dynamic where you can have a really fast clock speed but you're not getting that much work done. You can have low latency but low throughput.

</details>

**Reiner Pope**: 事实上，它会损害你的吞吐量，因为芯片的吞吐量是你每个时钟周期完成的工作量（基于**面积效率**）乘以你每秒获得的时钟数。这实际上与我们上次讨论的**批处理大小**非常相似，如果你有一个小的批处理大小，任何一个用户都可以非常快地接收到他们的下一个令牌，但例如在一小时内处理的总令牌数会比本来可以的要低。

<details>
<summary>Original English</summary>

**Reiner Pope**: It hurts your throughput, in fact, because the throughput of your chip is the product of how much you get done per clock cycle—which is based on area efficiency—times how many clocks you get per second. This is actually so similar to the thing we were discussing last time about batch size, where if you have a low batch size, any one user can receive their next token really fast, but the total number of tokens processed in, say, an hour will be lower than it could otherwise be.

</details>

**Dwarkesh**: 完全正确。如果你将时钟速度提高得非常快，你会获得更少的并行性。

<details>
<summary>Original English</summary>

**Dwarkesh**: Exactly. You get less parallelism out if you drive your clock speed up really high.

</details>

### AI与人类预测：Jane Street的视角

**Reiner Pope**: 语言模型正在开始与最优秀的人类预测者竞争。我与 **Jane Street** 的两位高级员工 **Ron Minsky** 和 **Dan Pontecorvo** 坐下来，并问：在某个时候，AI 是否会做 Jane Street 所做的一切？有一个我们应该认真对待的世界，在这个世界里，我们将构建大型语言模型或其他 AI 系统，它们比地球上所有人类都更聪明，在所有认知任务中都更强大。

<details>
<summary>Original English</summary>

**Reiner Pope**: Language models are starting to compete against the best human forecasters. I sat down with two senior Jane Streeters, Ron Minsky and Dan Pontecorvo, and asked: at some point, does AI just do what Jane Street does? There's a world that we should take seriously where, you know, we're going to build large language models or some other AI systems that are like strictly smarter than all humans on the planet and more capable at all cognitive tasks.

</details>

**Reiner Pope**: 特别是**交易**，在我看来有点像 **AGI** 完成，有点像 **NP 完全**，因为归根结底，交易涉及弄清楚事物的价值，这意味着对未来进行预测。Jane Street 并没有与 AI 对赌。他们刚刚签署了一份 60 亿美元的计算协议。但 Ron 的观点是，优势会不断变化。

<details>
<summary>Original English</summary>

**Reiner Pope**: Trading in particular feels to me as like kind of AGI complete, sort of like NP complete, because at the end of the day trading involves figuring out what things are worth, which means making predictions about the future. Jane Street isn't betting against AI. They just signed a six billion dollar compute deal. But Ron's view is that the edge keeps moving.

</details>

**Reiner Pope**: 我现在比以往任何时候都更渴望招聘更多的工程师和交易员。你知道，你总会遇到一些我们还不知道如何自动化的其他困难部分。嗯，这最终将成为竞争优势所在。你可以在 **janestreet.com/dwarkesh** 找到这些职位空缺并观看完整的采访。

<details>
<summary>Original English</summary>

**Reiner Pope**: I have never been more desperate to hire more engineers and more traders than I am today. You know, you have the usual thing of like the other hard parts that we don't yet know how to automate. Well, that ends up being where the competitive edge lies. You can find these open positions and watch the full interview at janestreet.com/dwarkesh.

</details>

### FPGA与ASIC的权衡

**Dwarkesh**: 我记得在 Jane Street 与 **Clark**，一位 **FPGA** 工程师交谈过，他帮助我为我们上次一起做的采访做准备。他解释了他们为什么使用 FPGA。我想对于**高频交易**来说，吞吐量不如延迟重要，所以对时钟周期进行非常具体的确定性控制是最重要的事情。也许讨论一下为什么你不能用 **ASIC** 来实现这一点，或者为什么你可能使用 FPGA 来实现高频交易的确定性时钟周期会很有趣。

<details>
<summary>Original English</summary>

**Dwarkesh**: I remember talking to an FPGA engineer at Jane Street, Clark, who helped me prep for the previous interview we did together. He was explaining why they use FPGAs. I imagine that for high-frequency trading, throughput is less important than latency, so having very specific control over the clock cycle in a deterministic way is the most important thing. Maybe it'd be interesting to talk about why you can't just achieve that with an ASIC, or why you might use an FPGA to have deterministic clock cycles for high-frequency trading.

</details>

**Reiner Pope**: 让我们考虑 FPGA 与 **ASIC** 的商业案例。FPGA 和 ASIC 使用大致相同的概念模型。你有一系列由小的**原语**（AND、OR、XOR）构建的逻辑门，通过导线连接在一起，在一个固定的时钟周期内运行。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's consider the business case for an FPGA versus an ASIC. FPGAs and ASICs use largely the same conceptual model. You have a series of gates built from small primitives—ANDs, ORs, XORs—connected together with wires running in a fixed clock cycle.

</details>

**Reiner Pope**: 任何你可以在 FPGA 中表达的东西，你也可以在 ASIC 中表达。在 ASIC 上会便宜大约一个数量级，并且**能效**更高。权衡在于，第一个 FPGA 会花费你 10,000 美元，而你制造的第一个 ASIC 会花费 3000 万美元，因为它需要进行完整的**流片**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Anything you can express in an FPGA you can express in an ASIC too. It will be about an order of magnitude cheaper and have better energy efficiency on an ASIC than an FPGA. The trade-off is that the first FPGA costs you $10,000, whereas the first ASIC you make costs $30 million because it requires an entire tape-out.

</details>

**Reiner Pope**: FPGA 的商业用例是当你需要**确定性延迟**、快速运行时间和高并行性，但你会频繁更改工作负载，也许每个月都会更改。你不想每次都支付流片成本。

<details>
<summary>Original English</summary>

**Reiner Pope**: The business use case for an FPGA is when you want something that has very deterministic latency, fast runtime, and high parallelism, but you are going to change the workload frequently, maybe every month. You don't want to pay that tape-out cost every time.

</details>

### FPGA的工作原理：寄存器、查找表与多路复用器

**Dwarkesh**: FPGA 实际上如何在固定硬件中模拟 ASIC 编程模型？

<details>
<summary>Original English</summary>

**Dwarkesh**: How does an FPGA actually emulate the ASIC programming model in a fixed piece of hardware?

</details>

**Reiner Pope**: 它的核心有我们刚刚谈到的两个组件。它有作为存储设备的**寄存器**，以及提供所有逻辑门的**查找表**（**LUT**）。然后还有第三个组件。我们有一群这样的寄存器和 LUT，它们通过一大组多路复用器连接在一起。在每个这样的设备前面，我们都有一个多路复用器，它从其他地方选择一个输入。我们有很多不同的选项馈入所有这些设备。

<details>
<summary>Original English</summary>

**Reiner Pope**: At its core, it has the two components we just talked about. It has registers as storage devices, and it has lookup tables (LUTs) which provide all of the gates. Then there's a third component. We have a swarm of these registers and LUTs, and they are connected by a big set of muxes. In front of every single one of these, we have a mux which selects an input from everywhere else. We have a whole bunch of different options feeding into all of these things.

</details>

**Reiner Pope**: 这实质上允许的是，当我编程我的 FPGA 时，我可以获取所有这些组件并叠加一个特定的布线，它通过这个 LUT，然后馈入另一个 LUT，发送到这个寄存器，然后再馈入另一个 LUT，或者类似的东西。我用橙色绘制的是你如何……FPGA 的意思是**现场可编程门阵列**。橙色部分是现场编程的，而白色部分是 FPGA 中必须存在的所有导线，才能首先制造出这个设备。

<details>
<summary>Original English</summary>

**Reiner Pope**: What this allows is essentially that when I program my FPGA, I can take all of these components and superimpose a particular wiring which goes through this LUT, feed it into another LUT, send it to this register, and then feed it into another LUT, or something like that. What I've drawn in orange is how you… FPGA means Field-Programmable Gate Array. The orange is what has been programmed in the field, whereas the white is all the wires that must exist in the FPGA in order to actually make the device in the first place.

</details>

**Dwarkesh**: “现场编程”是什么意思？

<details>
<summary>Original English</summary>

**Dwarkesh**: What does it mean to be programmed in the field?

</details>

**Reiner Pope**: 现场编程意味着该设备正在数据中心部署。它部署在实际世界中，然后你可以对其进行编程。

<details>
<summary>Original English</summary>

**Reiner Pope**: Programmed in the field means the device is being deployed in a data center. It's sitting out in the world, and then you can come and program it.

</details>

**Dwarkesh**: 哦，不是像电场那样的“场”。是像实际世界中的“现场”，好的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Ah, not field as in like electric field. Field as in like out there in the world, ok.

</details>

**Dwarkesh**: 如果我看看现场编程如何从第一个查找表出来并进入第二个查找表，它是如何工作的？连接的导线在哪里？

<details>
<summary>Original English</summary>

**Dwarkesh**: If I look at how the field programming comes out of the first lookup table and goes into a second one, how does that work? Where are the wires that make that happen?

</details>

**Reiner Pope**: 我在绘制所有这些时有点偷懒了。这里的每个设备前面都有一个多路复用器，它可以从所有可用的附近电路中进行选择。FPGA 的实际配置相当于**多路复用器控制**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I got a little bit lazy in drawing all of these. Every single device here has a mux sitting in front of it, which can select from all of the nearby circuits that are available. The actual configuration of the FPGA amounts to the mux control.

</details>

**Reiner Pope**: 在这个多路复用器中，我们有数据输入，我们有选择的控制。在每个多路复用器旁边都有一个小存储设备，上面写着“你将从这里获取输入”。对其进行编程包括配置每个多路复用器。

<details>
<summary>Original English</summary>

**Reiner Pope**: In this mux, we have the data inputs, and we have the control that selects. There's a little storage device sitting next to every single one of these muxes saying, "This is where you're going to source your input from." Programming it consists of configuring every single one of these muxes.

</details>

**Dwarkesh**: 这有道理。查找表内部发生了什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: That makes sense. What is happening inside of the lookup table?

</details>

**Reiner Pope**: 查找表也会有一些控制，告诉它做什么。它的目的是可配置地扮演 AND 门、OR 门、XOR 门或任何其他门的角色。有很多方法可以考虑这样做。传统 FPGA 的做法是……一个查找表有四个输入位和一个输出位。从四个位到一个位有多少种不同的函数？有 16 种不同的函数。你可以将这列成 16 个不同的数字。

<details>
<summary>Original English</summary>

**Reiner Pope**: The lookup table is also going to have a little bit of control telling it what to do. Its purpose is to configurably take the role of an AND gate, OR gate, XOR, or any of those different things. There are many ways you could consider doing that. The way it's done in traditional FPGAs… A lookup table has four bits of input and one bit of output. How many different functions are there from four bits to one bit? There are 16 different functions. You can tabulate this as 16 different numbers.

</details>

**Reiner Pope**: 你有一个 0111001 的表格，有 16 个条目。这个表格存储在这个蓝色的**配置位**中。它将这四个位视为二进制，查找表格中的相关行，然后发出该位。这本质上是查找表的**真值表**视图。

<details>
<summary>Original English</summary>

**Reiner Pope**: You've got a table of 0111001, 16 entries. This table is stored in this blue configuration bit. It views these four bits as binary, looks up the relevant row of the table, and emits that bit. This is essentially a truth-table view of lookup tables.

</details>

**Dwarkesh**: 好的，那么如果你考虑 AND 门、OR 门、NOR 门、XOR 门，这些都接受输入……这些是双输入函数。有时我们有三输入函数，比如三路 XOR，或四路 XOR。在这种情况下，它只取决于它的大小吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so if you think about an AND gate, OR gate, NOR gate, XOR gate, these all take as input… Those are two-input functions. Sometimes we have a three-input function, like a three-way XOR, or a four-way XOR. In this case, does it just depend on how big it is?

</details>

**Reiner Pope**: LUT 的典型大小是四个输入。这可以说是一个**最佳点**。这里还有另一个计算与通信的权衡。如果输入太少，你需要使用更多的 LUT。

<details>
<summary>Original English</summary>

**Reiner Pope**: The typical size for LUTs is four inputs. It's sort of just a sweet spot. There’s another compute vs. communication trade-off here. If it has too few inputs, you need to use more LUTs.

</details>

**Reiner Pope**: 基本上，查找表就是一个真值表。通过真值表，你可以编程任何你想要的逻辑门。所以，你可以把查找表看作是一个可编程的逻辑门。

<details>
<summary>Original English</summary>

**Reiner Pope**: Basically the lookup table is a truth table. With a truth table, you can program in any gate you want. So instead of a lookup table, you can just think of it as a programmable gate.

</details>

**Reiner Pope**: 对。你在这里可以做的一件事是，你可以看到 FPGA 比 ASIC 贵一个数量级的经验法则从何而来。你计算这个查找表内部有多少个逻辑门。我们可以将这个查找表本质上视为这些多路复用器之一。它必须在 16 个不同的值之间进行选择，所以它是一个 N=16 选项和 P=1 位的多路复用器。正如我们之前看到的，这个电路的成本是 N 乘以 P 个逻辑门。所以它的成本是 NP，即 16 个 AND 门，还有 16 个 OR 门。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. One of the things you can do here is you can see where the rule of thumb that an FPGA is an order of magnitude more expensive than an ASIC comes from. You count how many gates would be inside this lookup table. We can view this lookup table essentially as one of these muxes. It has to select between 16 different values, so it's a mux with n=16 options and p=1 bits. As we saw earlier, this circuit costs n times p many gates. So it costs np, which is 16, AND gates, and also 16 ORs.

</details>

**Dwarkesh**: 这个电路是多路复用器吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: This circuit being the mux?

</details>

**Reiner Pope**: 完全正确，是多路复用器。

<details>
<summary>Original English</summary>

**Reiner Pope**: Exactly, the mux.

</details>

**Dwarkesh**: 进入查找表的多路复用器？

<details>
<summary>Original English</summary>

**Dwarkesh**: The mux that goes into the lookup table?

</details>

**Reiner Pope**: 查找表本身你可以认为是一个大的多路复用器，它从所有 16 行中选择一个输出。那就是查找表。

<details>
<summary>Original English</summary>

**Reiner Pope**: The lookup table itself you can think of as being a big mux that selects from all 16 rows down to one output. That's the lookup table.

</details>

**Dwarkesh**: 但是你在这里的绘制方式是，有一个多路复用器，然后是一个查找表。

<details>
<summary>Original English</summary>

**Dwarkesh**: But the way you've drawn it here, there's a mux and then a lookup table.

</details>

**Reiner Pope**: 到处都是多路复用器。这里面还有一个多路复用器。这个多路复用器就是这个多路复用器。

<details>
<summary>Original English</summary>

**Reiner Pope**: It's muxes all the way down. There is a second mux that is inside here. This mux is this mux.

</details>

**Dwarkesh**: 另一个多路复用器只是说……它来自哪里，在这个门的混乱中。

<details>
<summary>Original English</summary>

**Dwarkesh**: And the other mux is just saying… where it came from in this mess of gates.

</details>

**Reiner Pope**: 对，第二个多路复用器是，“好的，现在你有一个值，但那个值仍然是一个四位值。”

<details>
<summary>Original English</summary>

**Reiner Pope**: Right, and the second mux is, "Okay, now you have one value, but that value is still a four-bit value."

</details>

**Reiner Pope**: 是的，我从“汤”中选择了四个位。然后我用这四个位来选择我要使用查找表中的哪个条目。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, I've selected four bits from the soup. Then I use those four bits to select which entry in the lookup table I'm going to use.

</details>

**Dwarkesh**: 假设在第一个多路复用器中，你从八个附近的寄存器中提取输入。总共有 32 位输入。其中四个位输出。这四个位进入第二个多路复用器，它在查找表内部。在这种情况下，这些寄存器是单比特寄存器。

<details>
<summary>Original English</summary>

**Dwarkesh**: Suppose in the first mux you're pulling from eight nearby registers as input. That's a total of 32 bits going in. Out of that, four bits come out. Those four bits go into the second mux, which is inside the lookup table. In this case, these registers are single-bit registers.

</details>

**Dwarkesh**: 如果有八个附近的寄存器和查找表，那么总共有八位输入。我从八个值中选择四个不同的值。实际上有四个不同的多路复用器，每个输入位都有一个小的多路复用器。每个都从八个中选择一个。

<details>
<summary>Original English</summary>

**Dwarkesh**: If there are eight nearby registers and lookup tables, then I have eight bits total coming in nearby. I select from eight down to four different values. There are actually four different muxes, a little mux associated with each of these input bits. Each of them is selecting one out of eight.

</details>

**Reiner Pope**: 这些八个来自哪里？附近的寄存器和其他 LUT。

<details>
<summary>Original English</summary>

**Reiner Pope**: Where are those eight coming from? Nearby registers and other LUTs.

</details>

**Dwarkesh**: 每个寄存器都是一位。

<details>
<summary>Original English</summary>

**Dwarkesh**: Each register is one bit.

</details>

**Reiner Pope**: 是的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes.

</details>

**Dwarkesh**: 我猜 **AMD** 或制造这些 FPGA 的公司仍然需要对哪些寄存器连接到哪些寄存器有自己的看法。你可以编程实际的逻辑门，但它们会在连接中添加一条线……也就是通信拓扑结构，对吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I guess AMD or whoever makes these FPGAs still has to be opinionated about which registers are connected to which registers. You can program in the actual gates, but they add a wire in the connect… the communication topology, right?

</details>

**Reiner Pope**: 你在局部粒度上获得了灵活性。有一个附近的区域你可以选择，但对于更粗粒度、长距离的连接，他们会形成自己的意见。

<details>
<summary>Original English</summary>

**Reiner Pope**: You get flexibility at a local grain. There's a nearby neighborhood you can select from, but for more coarse, long-distance connections, they form an opinion on that.

</details>

**Dwarkesh**: 那么它慢 10 倍的原因是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: And the reason it's 10x slower is why?

</details>

**Reiner Pope**: 如果你看看构建这个查找表的成本，它是 32 个逻辑门。它可以给我提供相当于——什么是一个有趣的例子——一个四路 AND 门。一个四路 AND 意味着 AND、AND，然后是 AND 的 AND。这是一个我可以直接在 ASIC 中使用三个 AND 门实现的电路。使用 LUT，我也可以实现它，但它将花费 32 个逻辑门而不是三个。

<details>
<summary>Original English</summary>

**Reiner Pope**: If you look at the cost of building this lookup table, it's 32 gates. It can give me the equivalent of—what’s an interesting thing I can do here—a four-way AND gate. A four-way AND means AND, AND, and then an AND of an AND. This is a circuit I could implement in an ASIC directly using three AND gates. Using a LUT, I can also implement it, but it's going to take 32 gates instead of three.

</details>

**Dwarkesh**: 所以开销实际上来自于这样一种事实，即描述真值表有一种比列出每个可能的输入组合更简洁的方式，那就是直接写出逻辑门。

<details>
<summary>Original English</summary>

**Dwarkesh**: So the overhead is really coming from the fact that there's a more concise way to describe a truth table than listing out every single possible combination of inputs, which is just to write out the gate.

</details>

**Reiner Pope**: 是的，放置**多晶硅**和导线等等。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes, to place down the polysilicon and the wires and so on.

</details>

### CPU的非确定性延迟与缓存

**Dwarkesh**: 有趣。你对我提出的一个重要观点是，他们偏爱 FPGA 而非 CPU 的原因是它们具有**确定性时钟周期**。他们知道数据包何时进出。为什么 CPU 不能保证这一点？

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. One important point you made to me is that the reason they prefer FPGAs to CPUs is that they get deterministic clock cycles. They know when a packet will come in and go out. Why isn't that a guarantee in CPUs?

</details>

**Reiner Pope**: 你实际上也可以设计一个具有确定性延迟的 CPU。事实上，许多 AI 芯片内部的处理器也具有确定性延迟。**Groq** 已经宣传过这一点。TPU 在核心中也具有这一点。挑战在于同时获得确定性延迟和高速。

<details>
<summary>Original English</summary>

**Reiner Pope**: You can actually design a CPU that has deterministic latency as well. In fact, the processors inside a lot of AI chips also have deterministic latency. Groq has advertised this. TPUs have that in the core as well. The challenge is getting deterministic latency and high speed at the same time.

</details>

**Reiner Pope**: **非确定性延迟**源于 CPU 中的特定设计选择。实际上可以消除这些设计选择并制造具有确定性延迟的 CPU，但这些在市场上不是很具吸引力，所以人们不再制造这些 CPU 了。从某种意义上说，确定性延迟是一个更简单的起点，一些芯片设计师添加了一些东西使其变得非确定性。

<details>
<summary>Original English</summary>

**Reiner Pope**: Non-deterministic latency comes from specific design choices in a CPU. It's actually possible to remove those design choices and make a CPU with deterministic latency, but those are not very attractive in the market, so people don't make those CPUs anymore. In some sense, deterministic latency is a simpler starting point, and some chip designers have added things in to make it non-deterministic.

</details>

**Reiner Pope**: 举一个具体的例子，CPU 上非确定性的最重要来源可能是 CPU **缓存**本身。在 CPU 中，你有 CPU 芯片本身，然后旁边是 **DDR 内存**。你有一个缓存系统，它记住最近访问的 DDR 并存储它们。当我执行 CPU 指令时，每次我有一个访问内存的指令，它首先检查数据是否存储在缓存中。如果没有，它就从 DDR 获取。

<details>
<summary>Original English</summary>

**Reiner Pope**: To take a concrete example, probably the most important source of non-determinism on a CPU is the CPU cache itself. In a CPU, you have the CPU die itself, and then DDR memory off on the side. You have a cache system inside that remembers recent accesses to DDR and stores them. When I'm running through my CPU instructions, every time I have an instruction that accesses memory, it first checks if the data was stored in the cache. If not, it fetches it from DDR.

</details>

**Reiner Pope**: 这是一个巨大的优化。缓存比 DDR 快两个数量级。如果你从不使用缓存，基本上所有程序都会慢一百倍。缓存的存在对于 CPU 以合理的速度运行是绝对必要的。但你是否获得**缓存命中**取决于 CPU 的环境：正在运行的其他程序，最近运行了什么，以及缓存系统内部的**随机数生成器**正在做什么。这是 CPU 运行时非确定性的一个重要来源。这就是 CPU 的内存系统。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is a huge optimization. The cache is two orders of magnitude faster than the DDR. If you never used the cache, basically all programs would run a hundred times slower. The presence of a cache is absolutely necessary for a CPU to run at a reasonable speed. But whether or not you get a cache hit depends on the ambient environment of the CPU: what other programs are running, what has run recently, and what the random number generator inside the cache system is doing. That is a big source of non-determinism in the runtime of a CPU. That is the memory system for a CPU.

</details>

**Reiner Pope**: 你可以做的不同之处在于，不再让硬件决定“我要读取内存”，然后硬件决定它是否来自缓存，你可以将这个决定内置到软件中，这是一种不同的设计理念。你可以在 TPU 中看到这一点，例如。我将绘制相同的图表，但我称之为**暂存器**（**scratchpad**）。

<details>
<summary>Original English</summary>

**Reiner Pope**: The big thing you can do differently is, instead of having the hardware say, "I’m going to read memory" and then the hardware decides whether or not it comes from the cache, you can bake this decision into software, a different design philosophy. You see this in TPUs, for example. I'll draw the same diagram, but I'll call it a scratchpad.

</details>

**Reiner Pope**: 主要区别是……这将是一个 TPU，在这种情况下，你使用的是 **HBM** 而不是 DDR，但它仍然是片外内存。软件不再是“首先访问内存”并让硬件决定，而是有一种指令类型用于暂存器，而另一种完全不同的指令类型用于 HBM。这种风格通常被称为暂存器而不是缓存。关键的区别在于，你有一种指令类型表示“读取或写入暂存器”，而另一种完全不同的指令类型表示“读取或写入 HBM”。

<details>
<summary>Original English</summary>

**Reiner Pope**: The main difference is… This would be a TPU, and you have HBM in this case rather than DDR, but it's still an off-chip memory. Instead of the software saying "first access memory" and letting the hardware decide, you have one kind of instruction that goes to the scratchpad and a totally different kind of instruction that goes to HBM. This style is generically known as scratchpad instead of cache. The key distinction is that you have one kind of instruction that says "read or write scratchpad," and a totally different instruction that says "read or write HBM."

</details>

**Dwarkesh**: 所以暂存器就是缓存？

<details>
<summary>Original English</summary>

**Dwarkesh**: So scratchpad being the cache.

</details>

**Reiner Pope**: 是的，这里的东西就是暂存器。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, this thing here is the scratchpad.

</details>

### 冯·诺依曼架构与现代硬件的并行性

**Dwarkesh**: 回过头来看：人们说计算机是“**冯·诺依曼架构**”，其中存在信息的串行处理。也许只是因为我们一直在谈论并行加速器，但 FPGA 是超并行的。AI 加速器，TPU，是超并行的。即使是 CPU，如果你考虑到它们拥有的所有核心，也是超并行的。在什么意义上，现代硬件实际上是冯·诺依曼架构？这真的是描述现代硬件的公平方式吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Stepping way back: people say computers have the "von Neumann architecture", where there's this serial processing of information. Maybe it's just because we've been talking about parallel accelerators, but the FPGA is super parallel. The AI accelerators, the TPUs, are super parallel. Even CPUs are super parallel if you think about all the cores they have. In what sense is modern hardware actually the von Neumann architecture? Is that actually a fair way to describe modern hardware?

</details>

**Reiner Pope**: 我认为这是描述 CPU 的公平方式。CPU 上的并行性大约是 100 个核心乘以可能 16 路向量单元，所以在 CPU 上大约有 1000 路并行性。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think it's a fair way to describe CPUs. The amount of parallelism you get on a CPU is about 100 cores times maybe 16-way vector units, so about 1,000-way parallelism on a CPU.

</details>

**Dwarkesh**: 一个问题：有一个芯片被用于 CPU，如果线程更少，仅仅是晶体管电压的开关，是不是说实际上只有一个控制流——芯片的一小部分——电压在开关？CPU 的芯片面积到底是如何被占用的……如果核心这么少，你把所有芯片面积都花在了什么上？

<details>
<summary>Original English</summary>

**Dwiner Pope**: One question: there is a die being used for the CPU, and if there are fewer threads, just as a matter of transistor voltages switching on and off, is it that there's literally one control flow—a small part of the die—where voltages are switching on and off? How do you actually occupy the die area of a CPU… If there are so few cores, what are you spending all of the die on?

</details>

**Reiner Pope**: 是的，那里发生了什么？核心只是更大更复杂。我们应该比较一个 CPU 核心（它占用芯片面积的百分之一）与一个 LUT。一个 LUT 只有 16 个逻辑门。很明显，FPGA 中的 LUT 数量比 CPU 中的核心数量多得多。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, what is happening there? The cores are just much bigger and more complicated. We should compare a CPU core, which takes up one one-hundredth of the die, to a LUT. A LUT is only 16 gates. It's clear why there are so many more LUTs in an FPGA than cores in a CPU.

</details>

**Dwarkesh**: 但为什么 **CUDA 核心**比 CPU 核心多？CPU 和 **GPU** 之间有什么区别？

<details>
<summary>Original English</summary>

**Dwarkesh**: But why are there more CUDA cores, for example, than CPU cores? What's the difference between a CPU and a GPU?

</details>

**Reiner Pope**: 在 CPU 内部，一个大的面积用途是缓存。ALU 实际上很少。大部分是这些寄存器文件而不是逻辑单元。这两个在 GPU 中都有等效物，所以这不是一个很大的区别。但 GPU 中没有等效物的是**分支预测器**。CPU 中有一大块区域只是一堆预测器，用于预测下一个分支何时出现以及分支目标在哪里。

<details>
<summary>Original English</summary>

**Reiner Pope**: Inside the CPU, one big use of the area is the cache. Very little is actually the ALUs. Mostly it's these register files rather than the logic units. Both of those have equivalents in a GPU, so that's not a big difference. But the thing that does not have an equivalent in a GPU is the branch predictor. There is a whole big area in the CPU which is just a bunch of predictors saying when the next branch will be and where the branch target is.

</details>

**Reiner Pope**: 剥离掉很多这些以及收紧这些寄存器文件，驱动了 GPU 相对于 CPU 的许多优势。

<details>
<summary>Original English</summary>

**Reiner Pope**: Stripping a lot of that out, as well as making these register files tighter, drives a lot of the GPU gains over the CPU.

</details>

**Dwarkesh**: 分支预测器的目的是什么？同时执行两个分支，还是它做什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: What is the purpose of the branch predictor? To execute both branches at once, or what does it do?

</details>

**Reiner Pope**: 问题是，当我有 series 指令时，如果我有一个分支，处理指令的实际步骤需要很长时间。它可能需要五纳秒。识别我有一个分支，评估布尔值是否为真，将程序计数器更新到新目标，然后从指令内存中读取，可能需要五纳秒才能完成。所以实际上，这可能在下面某个地方完成。我希望以比五纳秒允许的更快的时钟速度运行。五纳秒是 200 兆赫兹的时钟速度。我希望以一或两千兆赫运行。

<details>
<summary>Original English</summary>

**Reiner Pope**: The issue is that when I've got a series of instructions, if I have a branch, the actual step of processing an instruction takes a really long time. It takes maybe five nanoseconds. The time to notice that I've got a branch, evaluate whether the Boolean is true, update the program counter to the new target, and then read from the instruction memory could take five nanoseconds to finish. So in reality, this may finish somewhere down here. I want to run a clock speed that is much faster than what five nanoseconds allows. Five nanoseconds is a 200 MHz clock speed. I would like to run at one or two gigahertz.

</details>

**Reiner Pope**: 所以我需要在评估分支的同时运行其他指令。我只是想继续运行发生在我之后的指令。但这可能是错误的。如果分支最终被采取，那么我需要知道，我实际上需要跳到目标位置并运行这些指令，而不是评估这些指令。分支预测器的目的是提前五个周期预测分支将要发生，甚至在你到达该指令之前。

<details>
<summary>Original English</summary>

**Reiner Pope**: So I need to run other instructions while the branch is being evaluated. I just want to keep running the instructions that happen after me. But that might have been wrong. If the branch ended up being taken, then I need to know that instead of evaluating these instructions, I actually need to jump to wherever the target is and run those instructions instead. The purpose of the branch predictor is to predict, five cycles earlier, that a branch is going to happen, before you even get to that instruction.

</details>

### 芯片与大脑：并行性、时钟与能耗

**Dwarkesh**: 如果我思考大脑的工作方式与你在这里描述的相比，在高层次上，差异可能在于，虽然你可以在这些加速器中进行**结构化稀疏性**并节省一些本来需要专用于逻辑门的面积，但在大脑中存在**非结构化稀疏性**。任何神经元都可以连接到任何其他神经元，而不是以它们列对齐的方式。

<details>
<summary>Original English</summary>

**Dwarkesh**: If I think about how the brain works versus what you're describing here, at a high level the differences might be that while you can do structured sparsity in these accelerators and save yourself some area that you would have otherwise had to dedicate to gates, in the brain there's unstructured sparsity. Any neuron can connect to any other neuron, and not in ways where they have the column aligned.

</details>

**Dwarkesh**: 此外，内存和计算是共存的。尽管我想你也可以说，在某种程度上，内存和计算在这些芯片上也是共存的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Then there's the fact that memory and compute are co-located. Although I guess you could say in a way the memory and compute are co-located on these dies too.

</details>

**Reiner Pope**: 这在某种意义上正是内存和计算的共存。所以也许这并不是一个很大的区别。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is exactly the co-location, in some sense, of the memory and compute. So maybe that isn't a big difference.

</details>

**Dwarkesh**: 另一个很大的区别是，大脑的时钟周期比计算机慢得多。部分原因是为了节约能量，因为时钟周期越快，信号稳定和识别晶体管状态所需的电压就越大。

<details>
<summary>Original English</summary>

**Dwarkesh**: Another big difference is that the clock cycle on the brain is much slower than on computers. Partly that's to preserve energy, because the faster the clock cycle, the bigger the voltage needs to be in order for the signal to settle and to identify what state a transistor is in.

</details>

**Reiner Pope**: 对。

<details>
<summary>Original English</summary>

**Reiner Pope**: That’s right.

</details>

**Dwarkesh**: 你对大脑可能在做什么以及这些芯片如何工作有什么评论吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I don't know if you have any commentary on what the brain might be doing versus how these chips work.

</details>

**Reiner Pope**: 让我们先谈谈时钟速度。芯片上的时钟速度非常高，因为它驱动着更高的吞吐量。当我们比较 GPU 运行某个工作负载时，它运行的**批处理大小**是 1000。而大脑没有运行批处理大小 1000，我只有一个人。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's take the clock speed one first. The clock speed is quite high on a chip because that drives higher throughput. When we compare a GPU running some workload, it's running batch size 1,000. Whereas the brain is not running batch size 1,000, there's only one of me.

</details>

**Reiner Pope**: 你可以想象说：“取一个 GPU，然后不以千兆赫运行，而是以兆赫运行，”那将开始看起来更像是你所说的大脑中的等效事物。但就硅片的工作方式而言，这并不能给你带来 1000 倍的**能效**优势。它最终看起来是你只需运行一次这个电路直到稳定，然后它会长时间处于空闲状态。

<details>
<summary>Original English</summary>

**Reiner Pope**: You could imagine saying, "Take a GPU and instead of running at a gigahertz, run it at a megahertz," and that would start to look a little more like the equivalent things you're talking about in the brain. But in the way silicon works, that does not give you a 1,000x advantage in energy efficiency. What it ends up looking like is you just run this circuit once to stabilization, and then it will sit idle for a long period of time.

</details>

**Reiner Pope**: 当它空闲时，它不会消耗太多能量，因为大部分能量消耗在将比特从零切换到一再切换回来。

<details>
<summary>Original English</summary>

**Reiner Pope**: It doesn't consume a lot of energy while it's sitting idle because most of the energy is consumed in toggling bits from zero to one and back.

</details>

**Dwarkesh**: 让我们谈谈这种电路的能量消耗。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let's talk about the energy consumption of a circuit like this.

</details>

**Reiner Pope**: 存储位的思考方式是，你隐式地将一些电荷沉积在一个电容器中。当位变成 1 时，它就会充电，然后当它下次变成 0 时，它就会放电。这种电容器充电然后将电荷释放到地面的循环就是能量消耗发生的地方。这被称为**动态功耗**或**开关功耗**，它是芯片能量消耗的大部分。

<details>
<summary>Original English</summary>

**Reiner Pope**: The way to think of a bit being stored is that you've deposited some charge in a capacitor sitting somewhere in the chip implicitly. It becomes charged when the bit becomes a one, and then it becomes discharged when it next goes to a zero. That cycle of charging the capacitor and then dumping that charge out to ground is where the energy is consumed. This is called the dynamic or switching power, and it's most of the energy consumption of a chip.

</details>

**Reiner Pope**: 还有一些其他能量消耗只是因为绝缘体不完美，但我们会忽略它。大部分能量消耗来自将比特从零切换到一再切换回来。如果你以慢得多的速度运行芯片，并且每千个时钟周期只计时一次，你将会有 1000 倍的转换次数。它将减少大约 1000 倍的能量消耗。但这不是能效上的实质性优势。

<details>
<summary>Original English</summary>

**Reiner Pope**: There is some other energy consumption just coming from the fact that insulators aren't perfect, but we'll discard that. Most of the energy consumption comes from toggling from zero to one and back to zero. If you run a chip much slower and you only clock it once every thousand clock cycles, you will have 1,000 times fewer transitions. It will be about 1,000 times less energy consumption. But it's not a substantial advantage in energy efficiency.

</details>

### GPU与TPU的架构差异

**Dwarkesh**: 好的，你从高层次上描述了 TPU 的工作原理。那么 GPU 和 TPU 在高层次上的区别是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so you described how a TPU works at a high level. What is the difference at a high level between how a GPU and a TPU work?

</details>

**Reiner Pope**: 存在一个不同的高层次组织原则，然后在核心内部也有不同。从高层次上看，我们将分别查看 GPU 和 TPU，看看它们的顶层**块结构**是什么样子。如果你把这两种情况都看作是整个芯片，那么 GPU 的组织结构主要是许多几乎相同的单元，它们是 **SM**。它们中间有一个 **L2 内存**，然后底部有更多这样的 SM。所以有一个相当规则的核心网格。

<details>
<summary>Original English</summary>

**Reiner Pope**: There is a high-level organization principle that is different, and then inside the cores things are different. Looking at the high level, we'll take a GPU and a TPU and see what the top-level block structure looks like. If you think of this as the whole chip in each case, the organization of the GPU is mostly a bunch of almost-identical units, which are the SMs. They've got an L2 memory in the middle, and then a bunch more of these SMs on the bottom. So there is a fairly regular grid of cores.

</details>

**Reiner Pope**: 如果我们比较 TPU，你会发现它使用了更粗粒度的逻辑单元。你最终只有几个**矩阵单元**，它们是大的脉动阵列。中间你有一个**向量单元**，然后底部是你的矩阵单元。这些带有中间向量单元的矩阵单元构成了整个 TPU 芯片。你可以想象将这个东西缩小成一个非常小的单元，带有更小的矩阵单元和更小的向量单元，这有点像一个 SM。

<details>
<summary>Original English</summary>

**Reiner Pope**: If we look at a TPU in comparison, you end up with much coarser-grained units of logic. You end up with just a few matrix units, which are the big systolic arrays. In the middle you've got some vector unit, and then you've got your matrix units at the bottom. These matrix units with a vector unit in the middle make up the whole TPU chip. You can think of scaling this thing down into a really tiny unit with a smaller matrix unit and a smaller vector unit, and that is sort of what an SM is.

</details>

**Reiner Pope**: 从非常高层次的角度来看，GPU 在整个芯片上平铺了许多微小的 TPU。

<details>
<summary>Original English</summary>

**Reiner Pope**: From a very high-level point of view, the GPU has a lot of tiny TPUs tiled across the whole chip.

</details>

**Dwarkesh**: 哦，有趣。你是在暗示流式多处理器（SM）中的 Tensor Core 类似于 MXU 吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Oh, interesting. You're suggesting the tensor core within a streaming SM is analogous to an MXU?

</details>

**Reiner Pope**: 是的，它们都非常相似。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, it's all very similar.

</details>

**Dwarkesh**: 我明白了。如果你缺乏结构，拥有大量微小的 TPU 很有意义。而如果你只有巨大的矩阵乘法，你可能想避免拥有带有自己寄存器和**warp 调度器**的独立 SM 的成本。为什么不干脆把它做大，将这些成本分摊到整个芯片上呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: I see. If you had more lack of structure, having a bunch of tiny TPUs makes a lot of sense. Whereas if you just have huge matrix multiplications, you might want to avoid the cost of having individual SMs with their own registers and warp schedulers. Why not just make a huge thing and amortize those costs across the whole thing?

</details>

**Reiner Pope**: 这体现在你能将事物发展到多大。我们已经看到了这个主题，特别是对于脉动阵列，更大的脉动阵列更好地分摊了寄存器文件成本。这种设计允许你拥有更大的脉动阵列，而 GPU 设计则限制你拥有所有东西的小单元。然而，存在一个权衡。

<details>
<summary>Original English</summary>

**Reiner Pope**: This shows up in how large you can grow things. We've seen this theme, especially with the systolic array, where a larger systolic array amortizes the register file costs better. This design allows you to have larger systolic arrays, whereas the GPU design constrains you to having small units of everything. There is a trade-off, however.

</details>

**Reiner Pope**: 由于这种粗粒度的分离，你需要通过这里仅有的两条边界线，将大量数据从向量单元移动到矩阵单元。如果你看看 GPU 中的等效事物，你会发现到处都是向量单元，并且你可以通过许多不同的线路移动数据。在 GPU 中，向量单元和矩阵单元之间可以移动的数据量实际上比 TPU 中高得多。

<details>
<summary>Original English</summary>

**Reiner Pope**: Because of this coarse-grained separation of things, you need to move a lot of data from the vector unit to the matrix units, through just two lines of perimeter here. If you look at the equivalent thing in a GPU, you've got vector units everywhere, and you can move data through many different lines. The amount of data you can move between a vector unit and a matrix unit is actually much higher in a GPU than in a TPU.

</details>

**Dwarkesh**: 对。但你可能也需要移动更少的面积。

<details>
<summary>Original English</summary>

**Dwarkesh**: Right. But also you might have to move across less area.

</details>

**Reiner Pope**: 这也是一种**节能**。所以如果你能完全在 SM 内部操作，数据移动会小得多。但当你想要跨 SM 操作时，它会变得更复杂和昂贵。

<details>
<summary>Original English</summary>

**Reiner Pope**: Which is an energy saving as well. So if you can operate entirely within an SM, the data movement is much smaller. But the moment you want to operate across SMs, it becomes more complicated and expensive.

</details>

**Dwarkesh**: 所以你不需要评论，但人们可能会期望 MatX 可能会尝试做的一件事是，获得像 GPU 那样的较小结构的**脉动阵列**，周围是 **SRAM**，但同时让它变成这样，你不需要在 SM 中支持 CUDA 架构所需的东西——这些东西占用大量空间——你可能会丢弃。

<details>
<summary>Original English</summary>

**Dwarkesh**: So you don’t have to comment, but one might expect that a thing MatX might try to do is get the GPU-like smaller structure of systolic arrays surrounded by SRAM, but at the same time make it so that the things you need in an SM to support the CUDA architecture—which take a bunch of space—you might discard.

</details>

**Reiner Pope**: 我们已经公开讨论过一种我们称之为**可分割脉动阵列**的东西，从某种意义上说，你可以把它看作是既可以是大型脉动阵列，也可以是小型脉动阵列。

<details>
<summary>Original English</summary>

**Reiner Pope**: We've talked publicly about something we call a splittable systolic array, which in some sense you can think of as big systolic arrays that can be small systolic arrays too.

</details>

**Dwarkesh**: 酷。好的，我想这是一个很好的结束语。Reiner，非常感谢。

<details>
<summary>Original English</summary>

**Dwarkesh**: Cool. Okay, I think that's a good note to close on. Reiner, thank you so much.

</details>

**Reiner Pope**: 谢谢，Dwarkesh。

<details>
<summary>Original English</summary>

**Reiner Pope**: Thanks, Dwarkesh.

</details>