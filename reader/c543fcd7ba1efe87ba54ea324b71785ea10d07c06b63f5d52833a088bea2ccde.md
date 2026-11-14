---
author: Adam's Axiom
date: '2026-10-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ScFf69X7gYU
speaker: Adam's Axiom
tags:
  - game-theory
  - nash-equilibrium
  - mechanism-design
  - incentive-compatibility
  - subgame-perfect-equilibrium
title: 博弈论基础与双咖啡馆定价
summary: 本文作为博弈论指南，通过双咖啡馆定价案例阐述纳什均衡与子博弈完美均衡，分析机制设计中的激励相容问题，并探讨模型假设与预测偏差。
insight: ''
draft: true
series: ''
category: philosophy-wisdom
area: society-thinking
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/13 -->

### 博弈论基础与双咖啡馆定价

这是一份经济学博弈论的完整指南。我们将从基础讲起：什么是博弈，以及任何单方改变自身选择都无法获益的均衡。随后我们将进入更复杂的主题。谈判涉及协议以及协议带来的利益分享。拍卖理论则解释了规则如何塑造报价与支付。我们将通过详尽的示例和自测问题，一步步探讨每个概念。你将理解如何得出每个答案，以及为什么它是合理的。

<details><summary>Original English</summary>
This is a complete guide to game theory in economy. We will begin from the basics: what is a game and the equilibrium at which no one benefits change your choice independently. Then we let's move on to more complex topics. Talks relate to agreements and benefit sharing from agreements. Theory auctions explains how rules shape rates and payments. We step by step let's consider each idea with detailed examples and questions for self-checks. You you will understand how to get there to each answer and why does that make sense.
</details>

那么什么是博弈论？博弈论研究的是最优选择取决于他人选择、而他人的最优选择又取决于你的选择时的决策方案。让我们看看这对两家决定明天价格的咖啡馆意味着什么。这就是决策所在。你经营 A 咖啡馆，而 B 咖啡馆在马路对面。每天晚上，店主都会决定明天一杯咖啡的价格，而且只有两个选项：维持当前价格，或者降价。

<details><summary>Original English</summary>
So what is theory? games? Game theory studies solutions where your best choice depends on the choice another's, and theirs—from yours. Let's see what this means for two coffee shops that determine prices for tomorrow. That's what The solution lies. You you run cafe A, and cafe B—through road. Today every evening the owner decides tomorrow's price for a cup of coffee, and there is only two options. Leave current price or lower it.
</details>

在做决定之前，哪位店主都看不到对方的选择；开门营业后，价格在整整一天内都保持固定。你有降价的冲动。成为一家更便宜的咖啡馆，是让 B 咖啡馆的顾客穿过马路的理由。你每杯赚的钱会变少，但如果新来的人足够多，就能弥补损失。

<details><summary>Original English</summary>
No owner sees another's choice before making a decision, and after opening the price remains fixed for the whole day. You have temptation to lower the price. To be cheaper a coffee shop—this is an excuse for coffee shop customers B to cross the road. You you will earn less on each cup, but if it comes new enough people, it can compensate for losses.
</details>

困难在于，B 咖啡馆的店主现在也正坐在自己的店里考虑同样的选择。他们很可能会产生同样的想法。你的竞争对手很不巧也具备思考能力。问题就在这里。你明天的利润取决于你自己的选择，也取决于他们的选择，所以你不能孤立地评估自己的选择。你必须考虑到大家都可以从你这里做出选择。

<details><summary>Original English</summary>
The difficulty is that coffee shop owner B now sitting in his institution and considers the same choice. It is quite possible that in they will have the same idea. Your competitor in an awkward way developed the ability think. And in this That's the problem. Your tomorrow's profit depends on your choice and from their , so you can't evaluate your choice separately. You must take into account that everyone can choose from you.
</details>

为了比较结果，我们将以每日利润来衡量。利润就是销售收入减去销售成本以及咖啡馆运营费用。在这一节中，我仅为我们虚构的咖啡馆提供利润数字，因为最主要的是比较决策。稍后在课程中，我们将根据价格、销量和费用来预期利润。假设如果你们双方都维持当前价格，每家咖啡馆每天将获得 100 美元利润。

<details><summary>Original English</summary>
To compare results, we we will measure them in daily profit. Profit is money, received from sales, minus expenses for these sales and the work of the coffee shop. IN In this lesson I just I will provide profit figures. for our fictional coffee shop, because the main thing is to compare decision. Later in we will be on course expect profit, based on prices, quantities and expenses. Let's assume, what if you both save the current prices, each coffee shop will receive 100 dollars profit per day.
</details>

现在假设你降价，而 B 咖啡馆保持原价。你成了更便宜的咖啡馆。假设这吸引了足够多的新顾客，使你的每日利润增加到 150 美元——即便你每杯赚得更少。到目前为止，打折看起来相当有利可图。

<details><summary>Original English</summary>
Now let's assume that you lower the price, and cafe B leaves yours. You become a cheaper coffee shop. Let's assume this attract enough new customers to increase your daily profit up to 150 dollars. Even despite the fact that you earn less on each cup. So far discount looks like quite profitable.
</details>

现在假设你们双方都降价了。两家咖啡馆不再有哪一家比另一家便宜，因此顾客失去了跑过去的理由。你并没有比另一家店更便宜；你们双方只是都比昨天更便宜了。你们每杯咖啡赚得更少，如果较低的价格不能带来足够的额外销量，利润就会下降。在我们的例子中，假设额外销量不足，每家咖啡馆将获得 60 美元。

<details><summary>Original English</summary>
Now let's assume that you both lowered your prices. No more coffee shops is not cheaper than the other, therefore customers lose their reason move. You are not became cheaper than another institution. You both became cheaper than were yesterday. Each of you earn less on each cup, and if lower prices are not will provide enough extra sales, profit will fall. In our For example, let's say, what additional sales not enough, and each the cafe will receive 60 dollars.
</details>

### 问题一：降价能否保证利润？

这是你的第一个问题：降价是否能保证你赚到比双方都维持原价时所能获得的 100 美元更多？算一算如果 B 咖啡馆维持原价，你的利润会如何变化；然后再算一算如果 B 咖啡馆也降价，利润又会如何变化。如果想尝试解答，请在此处暂停。

<details><summary>Original English</summary>
Here is yours. first question. Or guarantees a reduction prices are what you earn more than 100 dollars, which would get if you Did both keep their prices? Find out how yours will change profit if cafe B will retain its price, and then how is he will change if the cafe B will also lower the price. Stop here if want to try this make.
</details>

如果 B 咖啡馆维持原价，你的利润将从 100 美元增加到 150 美元。150 减去 100 等于 50，所以这是 50 美元的利润增长。如果 B 咖啡馆也降价，你的利润将从 100 美元降至 60 美元。60 减去 100 等于负 40。因此，与两家咖啡馆都维持原价相比，这是 40 美元的损失。所以答案是否定的。同一个选择，根据一个你无法控制的决定，既可以让你多赚 50 美元，也可以让你少赚 40 美元。

<details><summary>Original English</summary>
If cafe B will keep the price, your profit will increase from 100 up to 150 dollars. 150 minus 100 is equal to 50. So this is profit of $50. If cafe B too will lower the price, your profit will fall from 100 up to 60 dollars. 60 minus 100 is equal to minus 40. So, that's a loss of 40 dollars compared to if both cafes kept the prices. So The answer is no. One and the same choice can make you 50 richer dollars or 40 poorer dollars depending on a decision you don't you control.
</details>

请注意我们尚未证明的内容。我们并没有证明维持价格就是最好的方案。如果 B 咖啡馆降价而你维持价格，你可能会得到更差的结果，而我们还没有考虑过这种选项。我们只是表明，没有任何潜在的收益是能得到保证的。你不能仅凭你希望另一位店主带给你的那个结果来评估这一决策。因此，你仍然需要做出决定。

<details><summary>Original English</summary>
Please note that what we have not proven. We have not proven that price retention is the best solution. If Cafe B will lower the price, and you will keep yours, you you can get more worse result, and we have not yet considered such an option. We only showed that there is no possible benefit guaranteed. You are not can you rate this solution, looking only for the result, for which one, how are you hope, will let you out another owner. Therefore, you still need to make a decision.
</details>

### 博弈的三个要素

要正确做出决策，你需要三项信息要素，它们是任何博弈的主要组成部分。第一：由谁做选择。做出决策的人被称为参与者（players）。在我们的案例中，就是两位咖啡馆店主。第二：每位参与者可以选择什么。我们的店主可以选择维持或降低他们的价格。我们有意排除了其他选项，例如改良咖啡或搬迁到竞争较少的街道。这在实际商业中可能很重要，但现在我们单独抽出一项决策来理解它。第三：每位参与者试图达成什么目标。经济学家称之为收益（win/payoff）。收益是反映结果对参与者价值的数字。在这里，收益就是每日利润，我们假设每位店主都只是想将其最大化。

<details><summary>Original English</summary>
That do it right, you need three information elements, which are the main parts of any games. First—who makes a choice. Persons who make decisions, are called players. IN in our case it is two cafe owners. Second—what can choose every player. Our owners can to maintain or reduce their prices. We are conscious excluded others options such as coffee improvement or moving to the street from less competitors. This can to be important in real business, but now we we single out one decision to understand him. Third—what is he trying to do? to reach everyone player. Economists they call it win. The win is number that reflects value of the result for the player. Here the winnings are daily profit, and we we assume that everyone the owner just wants maximize it.
</details>

### 问题二：决策者的选择与不确定性

这是第二个问题。你正在规划明天的销售，有两件事让你担忧：一是明天是否会下雨；二是隔壁的面包店是否会打折。这两者中，哪一件需要你去思考另一个做决策之人的选择？在我回答之前，请暂停一下。

<details><summary>Original English</summary>
Here is the second question. Are you planning? tomorrow's sales, and You are concerned about two things. . One—whether it will rain. Another—will it introduce discounts next door bakery. What about this? requires you to think about the choice another person who makes a decision? Pause before than I will answer.
</details>

是面包店。下雨当然可能损害生意，但在决定是否开始下雨之前，它并不会权衡价格。然而面包店店主却会。两个因素都是必须考虑的不确定性，但面包店店主是有选择和自身利益的参与者。因此，他的决定可能取决于他认为你会怎么做。博弈论为经济学增添的正是这种不确定性。

<details><summary>Original English</summary>
It bakery. Rain, of course, can harm business, but he doesn't weighs the prices before how to decide whether start walking. But here the bakery owner can. Both factors are uncertainty that must be taken into account, but the bakery owner— player with a choice and own benefit. So his decision may to depend on what, in his opinion, You will do it. Exactly like this uncertainty game theory adds to economy.
</details>

### 支付矩阵与结果构建

这样，你知道了由谁做选择、每位店主可以选择什么，以及各自渴望得到什么。但你仍然无法在降价与保价之间做出抉择，因为还缺少一种结果：如果 B 咖啡馆降价而你维持价格，情况会有多糟？为了回答这个问题，我们需要一种能够同时展示所有选择组合的方法。因此，让我们补全我们遗漏的那个结果。

<details><summary>Original English</summary>
So, you you know who chooses what everyone can choose owner and what each yearns. But you still you can't choose between price reduction and its preservation, because one is missing result. If the cafe "B" will lower the price, and you save yours, how bad is this can it end? That answer this, we need a way display all combinations of choices simultaneously. So let's fill in the result, which we missed.
</details>

假设你维持价格，而 B 咖啡馆降价。现在 B 咖啡馆变得更便宜了，穿过马路的理由已经出现在了另一侧。你的部分顾客流向了他们。你每杯赚的金额一如往常，但销量大幅减少，而咖啡馆的开门营业成本几乎没有什么变化。在我们的例子中，假设这为你带来 30 美元利润；而 B 咖啡馆处在你曾期望的处境中，获得了 150 美元。

<details><summary>Original English</summary>
Let's say you keep the price until Cafe B is lowering its prices. Now cafe "B" becomes cheaper, and the reason to cross the road appears already in the other side. Part your customers go to them. You, as before, earn a regular salary the amount from each cup, but you sell a lot less, whereas opening costs almost no institution are changing. In our For example, let's assume, what does this bring you 30 dollars of profit. AND cafe "B", finding itself in a situation that you hoped, gets 150.
</details>

我们终于集齐了全部四种结果。但你仍然可能会做出错误的比较：如果双方都维持价格，你将获得 100；而如果双方都降价，则是 60。维持价格看起来更好，直到你想起你无法替 B 咖啡馆选择价格。我们需要一种方法来比较你真正能够控制的选择。我们将把结果放入一张被称为支付矩阵的表格中。这个名字听起来令人生畏，尽管该事物本身并不配得上这种恐惧。

<details><summary>Original English</summary>
We finally have all four results. But you you can still do it wrong comparison. If both will keep prices, you will get 100, and if both decrease —60. Price retention looks better so far you won't remember that you don't you can choose the price for cafe "B". To us need a way compare elections that you really you control. We we will place the results into the table that is called a matrix payments. This name sounds scary though object to this not deserves.
</details>

行中列出了 A 咖啡馆的选择：维持或降低。列中列出了 B 咖啡馆的选择：维持或降低。找到行与列的交叉点，就能看到这两种决策组合的结果。每个单元格包含两个数字。在这张表中，第一个数字属于行参与者 A 咖啡馆，第二个数字属于列参与者 B 咖啡馆。这一顺序是必须确立的约定，因为数字本身并不会开口说明这一点。

<details><summary>Original English</summary>
In lines elections listed cafe "A": save or lower. IN columns elections listed cafe "B": save or lower. Find intersection of line and column, so that see the result a combination of these two decisions. Each the cell contains two numbers. In this table The first number belongs to to the player in line, cafe "A", and the second - to the player in the column, cafe "B". This order —an agreement that must be determined, because The numbers themselves don't say that. they will say.
</details>

让我们来看看这四个单元格。如果 A 维持价格且 B 维持价格，单元格中显示 100 和 100。如果 A 维持而 B 降价，里面显示 30 和 150：A 得到 30，B 得到 150。如果 A 降价而 B 维持，我们得到一个镜像展示：150 和 30。而如果双方都降价——

<details><summary>Original English</summary>
Let's consider these four cells. If "A" keeps price and "B" keeps it, in The cell says 100. and 100. If "A" keeps, and "B" reduces, it says there 30 and 150. "A" gets 30, and "B" gets 150. If "A" lowers the price, and "B" keeps, we we get a mirror image display: 150 and 30. And if both decrease
</details>

<!-- chunk 2/13 -->

价格，大家都会得到 60。

<details><summary>Original English</summary>
prices, everyone will get 60.
</details>

这就是整个博弈。A 的两种选择乘以 B 的两个选项，得出四种组合。更多选项就意味着更多组合。从这些条件中，得出了一个规则。当你为咖啡馆 A 做选择时，比较咖啡馆 A 的表现。当你为咖啡馆 B 做选择时，比较咖啡馆 B 的指标。不要将 A 的利润与 B 的利润进行比较，不要把其中较大的一个称为更好的策略 A。而且也不能从菜单中选择 B 的银行账户。在我们使用表格之前，先尝试读出单元格中的数值。咖啡馆 A 降低价格，咖啡馆 B 保持其价格。我们在哪个单元格？B 赚多少？这比两家咖啡馆都保持价格时 B 所赚的少多少？

<details><summary>Original English</summary>
This is the whole game. Two choices for A, multiplied by two options for B, give four combinations. More options would mean more combinations. From this conditions, one thing follows rule. When you make a choice for a cafe Ah, compare. Cafe A's performance. When you make a choice for cafe B, compare indicators cafe B. Don't compare profit A from profit B and not name the larger one them better strategy A. And not can choose bank account B from the menu. Try it read the value in cell before we we will use the table. Cafe A lowers the price, and Cafe B keeps its price. In which we cell? How many does B earn? AND how much less is it, than B earns when both cafes keep prices?
</details>

在这里停一下，自己找出对应的行和列。

<details><summary>Original English</summary>
Stop here and find it yourself row and column.
</details>

A 的选择给了我们“降价”这一行，B 的选择给了我们“保持”这一列。在这个单元格中显示的是 150，30。B 是列玩家，因此 B 得到第二个数字，30 美元。当双方都保持价格时，B 获得 100。100 减去 30 等于 70，因此，B 的利润减少了 70 美元。如果你回答的是 150，你找对了单元格，但读取的是另一位玩家的收益。这个小错误会带来很多麻烦。

<details><summary>Original English</summary>
Choice A gives us the string "to reduce", and choice B gives us the column "to save. In this the cell shows 150, 30. B—is a player column, so B gets the second number, 30 dollars. When both keep prices, B receives 100. 100 minus 30 equals 70, therefore, B's profit is 70 dollars less. If you answered 150, you found the right one cell, but read the winnings another player. This minor mistake creates a lot trouble.
</details>

我们还要区分经常被混为一谈的三件事。降低价格是单一玩家可采取的行动。两家咖啡馆都降价是他们共同行动的结果。60 美元是某位玩家在这样一种结果下的收益。单一行动并没有一个固定的收益结果。降价所带来的结果，取决于它与什么相遇。还有一个我们稍后会用到的区别。策略是关于如何进行博弈的完整计划。在这里，每位所有者只做出一项决定，因此“保持”或“降价”的选择本身就已经是完整的计划。在包含多项决策的博弈中，策略可能是这样的：“进入市场，如果需求高就扩张，如果需求弱就保持小规模。”单个行动只是该计划的一部分。

<details><summary>Original English</summary>
Let's also divide three things that often unite. Decrease prices are an action, available to one to the player. Decrease the prices of both cafes are the result of their joint actions. 60 dollars is a win one player per such a result. The action has no consequences. one fixed winnings. That which brings a decrease prices, depends on of what it is with collides. There is one more. the difference that we will need later. Strategy-this is the full plan of how to play Everyone here the owner approves one decision, therefore the choice "save" or ""reduce" is already complete plan. In the game with several solutions strategy can sound like this: "Get out to the market, then expand if demand is high, and to stay small, if he is weak." A separate action is only part of this plan.
</details>

还要记住，“同时”并不意味着两位所有者必须在同一秒内做出决定。一个人可以在 8:00 写下价格，另一个人在 9:00 写下。如果没有人能在做决定前看到对方的选择，这仍然是一个同时选择的博弈。他们在做选择时知道什么，比他们手表上的时间是否一致更重要。

<details><summary>Original English</summary>
And remember that "simultaneous" not means that both the owners decide in one second. One can write down the price of 8:00 and another at 9:00. If no one sees choosing another over how to make it, it's still a game with simultaneous choice. What they know under time of choice, more important for the coincidence of time on their watches.
</details>

表格还取决于其周围的环境情况。两位所有者都知道可供选择的选项和利润数字。每个人只关心自己当天的利润。他们之间没有任何协议，而且这些收益不包含未来的奖励或惩罚。我们稍后会回顾这些假设，但首先我们必须理解我们做了什么假设。

<details><summary>Original English</summary>
Table also depends on the situation around her. Both owners know available options and numbers profit. Everyone cares only about your own daily profit. There is no one between them. agreements, and these winnings do not include future rewards or punishments. We let's review these assumptions later, but first we have understand that we assumed.
</details>

### 新情境练习

让我们在另一种情境中尝试这种方法。这是一个具有各自玩家和收益指标的独立模型。外卖送货服务选择上午或晚上取件，而向他们购买商品的咖啡馆则选择小订单还是大订单。这一次，外卖送货服务是行玩家。因此，第一个数字属于公司，第二个数字属于咖啡馆。上午和晚上，对应 8，12。上午和大订单，对应 14，18。晚上和上午，对应 10，9。晚上和大订单，对应 16，15。这些数字是该特定配送协议下的净利润（美元）。每位玩家都偏好更高的净利润。

<details><summary>Original English</summary>
Let's let's try this method in another situation. It separate model with with their players and own indicators winnings. Service delivery chooses morning or evening collection, and the cafe, which buys from them goods, chooses small Is it a large order? This time the service delivery is a player line. So, first the number belongs to companies, and the second—cafe. Morning and evening they give eight, 12. Morning and the big one is given by 14, 18. Evening and morning give 10, nine. Evening and great give 16, 15. These numbers are pure profit in dollars for this particular agreements on delivery. Everyone the player gives preference for more net profit.
</details>

这里有一个问题。咖啡馆下了大订单，而公司选择在晚上取件。咖啡馆得到什么？接着，如果仅公司改为上午，它的利润会发生什么变化？

<details><summary>Original English</summary>
Here question. Cafe does great order, and the company takes him in the evening. What gets a cafe? Then, if only the company passes into the morning, What happens to her? profit?
</details>

停下来看看，每个数字属于谁。晚上和大订单给出 16，15。咖啡馆是列玩家，所以它得到 15。如果公司改为上午，而订单依然是大订单，我们转向“上午和大订单”，它对应 14，18。公司现在得到 14 而不是 16。16 减去 14 等于 2，因此，其利润下降了 2 美元。咖啡馆的利润从 15 增加到 18，增加了 3，但这不是要求针对该公司进行的比较。

<details><summary>Original English</summary>
Stop and watch, Who owns each? numeric. Evening and great they give 16. 15. The cafe is column player, so it gets 15. If the company is moving in the morning, while order remains large, we move on to morning and the big one, which gives 14. 18. Company now gets 14 instead of 16. 16 minus 14 is equal to two, therefore, its profit falls by 2 dollars. Cafe profit increases from 15 to 18, this an increase of three, but this not the comparison that asked to do company.
</details>

### 严格优势策略与囚徒困境

现在让我们回到一开始吸引你的那个比较。100 对比 60。这两个结果是两家咖啡馆都改变价格的结果。如果咖啡馆 B 降低价格，你的真实比较是：保持价格得到 30，对比降价得到 60，因为保持价格并不能换回 100 美元的结果。表格防止了我们回答错误的问题，但它并没有告诉我该怎么做，因为你仍然不知道咖啡馆 B 会选择哪一列。那么，当你的最佳行动似乎取决于你所做的选择……看不到吗？有时你的最佳行动只是看起来取决于你所看不到的决定。找出的方法是依次考虑咖啡馆 B 的每个选项，将其固定下来，并与自己的各个选项进行比较。

<details><summary>Original English</summary>
Now let's go back to comparison, which tempted you to beginning. 100 against 60. These two results changed the prices of both cafe. If cafe B lowers the price, your real comparison—it's 30 for saving prices vs. 60 for her decrease, because price retention is not returns the result in 100 dollars. Table prevented us answer false question, but she didn't tell me what to do, because you still don't know, which column will you choose? cafe B. So how to choose action when your the best move, It seems to depend. from the choice you make Can't you see? Sometimes your the best move is only seems dependent from the choice you make You don't see. Way to find out—to take each of the options cafe B in turn, record it and compare with him own options.
</details>

因此，我们首先假设 B 保持其价格。你是咖啡馆 A，你可以保持价格赚取 100 美元，或者降低价格赚取 150 美元。150 减去 100 等于 50，所以降价让你多得 50 美元。我们在同一列内的两行之间移动，因此在整个比较过程中，B 的选择保持不变。

<details><summary>Original English</summary>
Therefore, let us first assume, that B retains its price. You are cafe A, you you can keep the price and earn 100 dollars or lower it and earn 150. 150 minus 100 is equal to 50, so the price reduction gives you $50 more. We move between two lines within one column, so choice B remains unchanged throughout of the whole comparison.
</details>

现在假设 B 降低其价格。你可以保持价格赚取 30，或者降低价格赚取 60。60 减去 30 等于 30，因此降价让你多得 30 美元。同样，B 的选择保持不变。你在两种情况下都更倾向于降价，所以你不一定需要知道 B 会选择哪一列。我们说，对 A 而言，降价严格优于保持价格。严格优势策略为该玩家提供高于任何其他备选策略的收益，无论其他玩家采取什么行动。

<details><summary>Original English</summary>
Now suppose that B lowers its price. You you can keep the price and earn 30 or lower it and earn 60. 60 minus 30 equals 30, hence the price reduction gives you $30 more. Again, choice B remains unchangeable. You prefer price reduction in both situations, so you not necessarily know, which column will B choose? We say that for A price reduction strictly dominates her retention. Strictly dominant strategy provides the player with higher gain than any alternative, regardless of actions other players.
</details>

现在轮到你来检验另一位所有者了。如果 A 保持价格，比较 B 的两种可能收益。然后针对 A 降低价格的情况重复该比较。B 是否也拥有严格优势策略？指出具体的数字来证实你的答案，而不是仅依赖于表格的对称性。暂停一下。

<details><summary>Original English</summary>
Now your turn check another owner. If A holds the price, compare the two possible winnings B. Then repeat. comparison for case if A reduces price. Does B also have strictly dominant strategy? Point specific numbers for confirmation of your answers, instead of to rely on only for symmetry tables. Do it. pause.
</details>

如果 A 保持价格，B 若保持自己的价格则得到 100，若降价则得到 150。如果 A 降低价格，B 若保持自己的价格则得到 30，若降价则得到 60。B 在两种情况下都更倾向于降低价格，因此两位所有者拥有相同的严格优势策略。如果每个人都按照动机行动，双方都会降低价格，并各自得到 60。这是一个奇怪的结果，因为两位所有者都更愿意得到 100 美元，而不是 60 美元。

<details><summary>Original English</summary>
If A holds price, B gets 100, if he keeps his, or 150 if it reduces. If A lowers the price, B gets 30 if keeps his, or 60, if it decreases. B gives preference for reduction prices in both cases, therefore both owners have the same strictly dominant strategy. If everyone acts accordingly incentive, both reduce prices and receive 60 each. This strange result, because both owners would prefer to receive 100 dollars, not 60.
</details>

我们得出这一点，并没有假设他们中的某个人行为不智。我们只是让每位所有者掌控自己的价格，不幸的是，这是他们实际能够控制的唯一价格。重要的比较并不是 60 对比他们原本可以共同赚取的 100。当另一家咖啡馆降低价格时，维持你自己的价格并不能换回 100 美元的结果，而只会带来 30。每位所有者只能改变一项决定，而不能同时决定双方。

<details><summary>Original English</summary>
We have reached this point, no assuming that someone of them is acting unwisely. We only provided to each owner control over one's own at a price that, unfortunately, is the only price that they actually control. It is important comparison not 60 vs. 100 that they could earn money together. When another cafe lowers the price, maintaining your own will return the result in 100 dollars. This gives only 30. Each owner can change one thing solution, not to beat both.
</details>

这样的结构被称为囚徒困境。无论后者的选择是什么，每位玩家都有采取损人行动的动机。当双方都这样做时，他们发现自己所处的境地，要比他们选择合作备选项时更糟糕。困境源于动机，而不是因为监狱的存在或某个特别讨厌的人。

<details><summary>Original English</summary>
Such a structure called a dilemma prisoner. Every player has an incentive to act on harm to another, regardless of choice the last one. When both do that, they find themselves in worse situation, than if they had chosen cooperative alternative. Dilemma arises from incentives, not through the presence of a prison or particularly unpleasant person.
</details>

让我们把它转化为监狱术语，以便我们进行逻辑推理，而不仅仅是选择最大的数字。这是一个独立的虚构模型。两名嫌疑人被分别审讯。每个人都可以保持沉默或招供。如果两人都沉默，每人获得 1 年。如果一人招供而另一人沉默，招供的人获得 0 年，而沉默的人获得 3 年。如果两人都招供，每人获得 2 年。假设每个人只关心刑期。面对另一人的沉默，第一名嫌疑人应该怎么做？面对招供又该怎么做？招供是否优于沉默？暂停一下，记住这些数字反映的是成本（惩罚）。在另一人沉默的情况下，招供带来 0 年而不是 1 年。在另一人招供的情况下，招供带来

<details><summary>Original English</summary>
Let's let's translate this into prison language terms so that we reasoned logically, and not just chosen the largest number. It separate fictional model. Two suspects are interrogated separately. Everyone can remain silent. or confess. If both are silent, each gets 1 year. If one confesses, and the other is silent, the one, whoever confesses, receives zero years old, and the one who was silent—three. If both confess, everyone gets two years. Let's assume that everyone is only concerned prison term. What should do the first suspected of response to the silence of another? And what? to do in response to confession? Or confession dominates over silence? Do it. pause, remembering that these numbers reflect costs (punishment). In case of the silence of another, confession gives zero years instead of one. In case of confession another, confession gives
</details>

<!-- chunk 3/13 -->

服刑两年而不是三年。在两种情况下坦白都更好，因为年数越少越好。如果两人都坦白，每人将被判两年；尽管如果两人都保持沉默，每人本只会得到一年。激励机制的结构与咖啡馆博弈相同，只不过收益方向相反。

<details><summary>Original English</summary>
two years instead three. Confess better in both cases, because it is smaller the number of years is better. If both admit, everyone will receive two years, although if both were silent, each I would get one each. year. Incentives have the same structure as in the game with the cafe, but with in another direction advantages.
</details>

让我们回到最初的咖啡馆收益表，并故意修改一个数字。在这个版本中，A 拥有极其忠诚的常客。如果 A 维持原价，而 B 降价，A 赚取 90，而不是 30。其他一切保持不变。如果 B 维持原价，A 仍然倾向于降价，因为 150 优于 100。但如果 B 降价，A 现在倾向于维持原价，因为 90 优于 60。A 不再有占优策略。

<details><summary>Original English</summary>
Let's go back. to the initial cafe tables and intentionally change one number. In this option A has extremely loyal regular customers. If A leaves the price, and B reduces, A earns 90, not 30. Everything else remains unchangeable. If B leaves the price, And all prefers the same reduction, because 150 is better for 100. But if B lowers the price, and now prefers that to leave, because 90 better than 60. A has more no dominant strategies.
</details>

这里是第二个版本，同样基于最初的表格开始，而不是从 90 开始。假设如果 A 维持原价而 B 降价，收益为 60，这与降价对降价的结果相同。如果 B 维持原价，降价仍然带来 150 而非 100。因此，降价绝不会更差，并且在至少一种情况下它更好。我们称之为弱占优。在某些情况下允许平局，但在任何情况下都不能更差。但请注意平局意味着什么：如果 A 确信 B 会降价，A 在任何情况下都会得到 60。因此，基于这一信念，维持原价同样是一个好策略。弱劣势策略不能像严格劣势策略那样被作为完全不可能而彻底排除。

<details><summary>Original English</summary>
Here is the second one option, again starting from the initial table, and not from 90. Let's assume that if A leaves the price, and B decreases, this gives 60, so same as decrease against decline. If In leaves the price, reduction still gives 150 instead of 100. So, there is never a decrease worse, and at least in in one case it better. We call this is weak domination. Draw in in certain cases allowed. Be worse in certain In some cases, no. But pay attention to the fact that which means a draw. If A is sure that B will lower the price, A will receive 60 in any in any case. Therefore, leaving the price is just as good in response to this belief. Weak the dominated action is not can be discarded as completely impossible, on unlike strictly dominated.
</details>

从现在起，每当我提起咖啡馆博弈，我指的都是最初的表格：100、150、30 和 60。占优为我们提供了一条强有力的捷径，但在包含忠诚度的版本中，A 的最佳行动取决于 B，而许多博弈对所有人来说正是如此。每个人的最佳选择取决于其他人，而其他人的选择又由他们自己决定。那么，当没有人拥有占优策略时，我们该如何找到共同说得通的选择呢？

<details><summary>Original English</summary>
From now on, when I I remember the game from the cafe, I I mean again initial table. 100, 150, 30 and 60. Domination gives us a powerful short way, but in variant with loyalty is the best A's action depended on B, and many games are just like this for everyone. The best choice every person depends on others, and the choice of others is up to them. So how do we find choices that make sense together, when no one has dominant strategy ?
</details>

### 最佳应对与协调博弈

让我们用一个新的例子来回答这个问题，脱离价格表。我们的两家咖啡馆想要在街头联合举办一场活动。每位店主必须在不知道对方选择的情况下选择周六或周日。如果他们选择不同的日子，每场活动吸引的人数都不足以抵消付出的努力。如果他们选择同一天，双方都会获益。

<details><summary>Original English</summary>
Let's answer. a new example of this , separately from the price tables. Our two they want to hold a cafe common street West. Every owner must choose Saturday or Sunday, no knowing the other's choice. If they choose different days, each the west will attract not enough people to to be worth the effort. If they choose the same day, both win.
</details>

假设如果两人都选择周六，A 得到 80，B 得到 60。如果两人都选择周日，A 得到 60，B 得到 80。如果他们选择不同的日子，两人都得到零。这是该活动的预期净收益，纯粹作为示例给出，并非计算得出。两位店主都倾向于活动办成功，胜过毫无行动，但 A 更喜欢周六，而 B 更喜欢周日。占优捷径无法为 A 选出日子。如果 B 选择周六，A 偏好周六，因为 80 优于零。如果 B 选择周日，A 偏好周日，因为 60 优于零。A 的最佳选择随 B 的选择而变化。

<details><summary>Original English</summary>
Let's assume that if both will choose Saturday, A will get 80, and B will get 60. If both will choose Sunday, A will receive 60, and B will get 80. If they will choose different days, both will receive zero. It expected clean proceeds from the event, provided for example, and not calculated. Both owners prefer a successful event than lack of action, but A more I like Saturday, and Sunday. Predominant short way is not will choose the day for A. If B chooses Saturday, A gives preference for Saturday, because 80 better than zero. If B chooses Sunday, A prefers Sundays, because 60 is better than zero. The best choice A varies depending on from choice B.
</details>

在别人的特定选择下，或基于对他们行动的特定信念下，为玩家带来最高收益的选择被称为最佳应对。这个概念是条件性的。它回答的是“相对于什么而言是最佳”，而不是“所有之中最好的”。如果两个选择并列，两者都将被视为最佳应对。我们绝不能凭空捏造数据中不存在的偏好。

<details><summary>Original English</summary>
The choice that brings the player highest profit for a certain choice of others or at a certain beliefs about their actions, is called best answer . This concept is conditional. . It responds to the question "best" about what", not " "the best of all." If there were two elections equal, both would be considered the best answers. We are not must invent preferences, which not in numbers.
</details>

这里是第一个练习。共有四对可能的日期组合。找出所有每位店主都已经对另一方的行动做出了最佳应对的组合。然后分两步检验每对组合：首先只改变 A 的选择；然后只改变 B 的选择。停在这里试着做一下。

<details><summary>Original English</summary>
Here first exercise. THERE ARE four possible pairs days. Find all couples in which each the owner already chooses best answer on the actions of another. Then check each pair in two steps. First change only choice A. Then change only choice B. Stop here and try this make.
</details>

双方都选周六通过了检验。如果仅 A 改到周日，A 的收益从 80 降到零。如果仅 B 改到周日，B 的收益从 60 降到零。双方都选周日也通过了检验。独自单方面改换，A 的收益将从 60 降到零，B 的收益将从 80 降到零。

<details><summary>Original English</summary>
Saturday for both pass verification. If only A moves to Sunday, A's profit falls from 80 to zero. If only B moves to Sunday, B's profit falls from 60 to zero. Sunday for both also pass verification. A lost would be from 60 to zero, having crossed alone , and B—from 80 to zero.
</details>

任何错配的组合都无法通过检验。假设 A 选择周六，B 选择周日，此时每人都得到零。A 单独改到周日就可以将结果提升到 60。B 单独改到周六就可以将结果提升到 60。另一个错配组合也以同样的方式检验：如果 A 选择周日，B 选择周六，A 可以改到周六并获得 80，或者 B 可以改到周日并获得 80。只要存在一个玩家能通过单方面改变获得益处，就足以否决该组合。我们并不要求两个玩家同时采取行动。有两个组合保留了下来，因此该博弈有两个纯策略纳什均衡。

<details><summary>Original English</summary>
None inappropriate the steam does not pass verification. Suppose A chooses Saturday, and B—Sunday, so everyone gets zero. And could improve the result to 60, having passed alone on Sunday. B could improve result up to 60, having crossed alone on Saturday. Other mismatched pair not is being checked in the same way. If A chooses Sunday, and B—Saturday, A could move to Saturday and get 80, or B could would move to Sunday and get 80. We one is enough player with one a beneficial change to reject the pair. We are not we demand that both the players acted simultaneously. Two couples survive, so this the game has two equilibria Nash in the pure strategies.
</details>

### 纳什均衡的定义与检验

纳什均衡是一组策略，在其中任何玩家在其他人策略保持不变的前提下，仅凭单方面改变自己的策略都无法提高自身收益。换句话说，每个玩家同时都在对其他所有人的行动采取最佳应对。在这样的一次性选择博弈中，纯策略意味着以确定性选择某一个行动。随后我们将考虑随机选择。

<details><summary>Original English</summary>
Nash equilibrium is a set of strategies, in which no player cannot improve own profit, changing your strategy alone, provided that strategies of others remain unchangeable. Others in words, everyone player at the same time plays the best response to everyone's actions others. In such games with one choice is pure strategy means choosing one action from confidence. Subsequently we will consider random elections.
</details>

让我们看看这种检验对最初的价格博弈说明了什么。双方都降价——这就是纳什均衡。如果竞争对手降价，任何单方面转向维持原价的店主，其利润都会从 60 降到 30。双方都维持原价不是均衡，因为每位店主都可以单方面改变决定，并将利润从 100 提高到 150。但如果双方都维持原价，每位店主获得的都比双方都降价时要多。因此，均衡对每位玩家来说可能比另一个可行的结果更差。均衡并不意味着结果是公平、高效、友好或特别令人满意的。它仅意味着：在其他人的策略保持不变的条件下，单方面的改变无法提高该玩家的收益。而且对于完全不在这个表格中的顾客来说，他们可能更喜欢较低的价格。

<details><summary>Original English</summary>
Let's see what this is. the check says about the initial game with prices. Both are lowering prices—this Nash equilibrium. If competitor lowers price, any the owner who will switch to it on its own price retention, will see the fall profit from 60 to 30. Both keep prices are not equilibrium because everyone the owner can change decision alone and to raise profits from 100 to 150. But if both keep prices, each owner receives more than if both are decreasing. So, equilibrium can to be worse for each player than another one available result. Balance does not mean that the result is fair, efficient, friendly or especially impressive. This means that are one-sided changes do not improve player's winnings for conditions that others strategies remain unchangeable. AND to customers who not at all in this one tables, can to like the lower ones prices.
</details>

### 匹配硬币博弈与纯策略的缺失

是否有某种博弈里的每一对选择都无法通过检验？这里有第二个新博弈，脱离了咖啡馆情境。两名玩家各自秘密选择正面或反面。如果他们的选择一致，A 从 B 那里赢取 1 美元。如果选择不同，B 从 A 那里赢取 1 美元。因此，A 想要一致，而 B 想要差异。

<details><summary>Original English</summary>
Can each a certain pair of elections is not pass the test? Here second new game, separate from the cafe. Two players secretly choose an eagle or tails. If their the elections coincide, A wins $1 from B. If they are different, B wins $1 from A. So, A wants a match, and B wants differences.
</details>

如果两人都选正面，A 赢了，但 B 想把选择改到反面。如果 A 选正面而 B 选反面，B 赢了，但 A 想把选择改到反面以达成一致。剩下的两个组合会发生什么？停下来检验它们。如果两人都选反面，A 达成了一致，所以 B 想把选择改到正面，以使结果不同。如果 A 选反面而 B 选正面，A 想把选择改到正面以求一致。四对组合中的每一对都让某人有动机进行有利的改变。这里不存在纯策略纳什均衡。这是一个十分合理的回答。我们绝不能为了图省事随便圈出一个最不别扭的单元格，指望没人会注意到。

<details><summary>Original English</summary>
If both choose Heads up, A won, but B wants to change the choice to tails. If A chooses heads, and B chooses tails , B won, but A wants change the selection to tails for matching. What happens with the other two pairs? Stop and check them out. If both choose tails, A reached a match, so B wants to change choice for an eagle, so results were different. If A chooses tails, and B The eagle chooses, but wants change selection to eagle for coincidence. Each of four pairs gives someone has a chance beneficial change. Not there is a Nash equilibrium in pure strategies. This is quite reasonable. respond. We are not must circle least inconvenient cell, hoping that no one will notice.
</details>

回到街头活动，检验给我们提供了两个可行的方案。但店主们仍必须选定一个，而寻找均衡并没有告诉 A 或 B 会选择哪一天。A 偏好周六，B 偏好周日，而选择不同的日子会让双方一无所获。传统、最晚预订期限或沟通消息或许能帮助他们协调行动。那么，究竟是什么能让任何一位店主确信对方会在同一天来呢？何时这种信心才算足够？又在何时激励机制本身必须做出改变？

<details><summary>Original English</summary>
Returning to street event, test gives us two workers plans. But the owners still have to choose one, and search did not suggest equilibrium And, what day will B. A choose? prefers Saturday. B provides Sunday preference. AND choice of different days leaves both of them with nothing. Tradition, extreme booking deadline or messages can help them to coordinate actions. So, what will force anyone owner to be sure that the other will come the same day day? And when confidence enough? And when the incentives themselves have change?
</details>

让我们首先考虑信心，因为在某些博弈中，信心是主要问题。咖啡馆店主们一致认为，一个联合点餐应用程序能对双方都有所帮助。但这里存在一个细微差别：只有当双方都花周末时间接入各自的菜单时，该应用才能发挥作用。每家店主本可以改为将周末花在完善自己的店铺上，并获得较小但稳妥的收益。在指责任何一位店主不愿沟通之前，我们先看看他们冒着什么风险。这是另一个新模型，这一次获胜得到的是效用点数，而不是美元。该分值衡量的是店主……

<details><summary>Original English</summary>
Let's consider first confidence because in some games confidence is the main problem. Cafe owners agree that common application for orders can help them both. There is a nuance here. Addition works only when when both will spend the weekend on connecting your menu. Everyone could instead spend weekend on improving oneself institution and receive smaller but reliable benefit. Before to name anyone from owners non-contact, Let's look at what they are. take risks. This is another one. new model, and this Once you win, you get points. benefits, not dollars. The score measures, as far as the owner
</details>

<!-- chunk 4/13 -->

### 猎鹿博弈与纯纳什均衡

重视结果，而且数值越大越好。每位店主在看不到对方选择的情况下，各自选择合作项目或稳妥项目。如果两人都选择合作，每人得到八分。如果 A 选择合作，而 B 选择稳妥，A 得到零分，因为把周末时间花在对接并没有上线、不知为何未能连接的应用上。B 则从改善后的设施中获得四分。将选择对调，收益也会相应对调。如果两人都选择稳妥选项，每个人都将得到四分。因此，无论另一位店主采取何种行动，稳妥选项都能带来四分。

<details><summary>Original English</summary>
appreciates the result, and higher numbers are better. Each owner chooses joint project or safe project, not seeing the choice of another. If both choose common, each gets eight points. If A chooses common, and B chooses safe, A gets zero, because I spent weekend on connection to application that is not up to why not connects. B gets four points from improved institution. Change elections for the opposite, and the winnings will change in accordance. If both will choose safe option, everyone will receive four. Therefore, safe option gives four, regardless from the actions of another owner.
</details>

提一个问题。如果 A 确信 B 会选择合作选项，A 应该选合作还是稳妥？如果 A 确信 B 会选择稳妥，那么 A 又应该选什么？请用数字解释这两个答案，然后告诉我为什么单一通用的答案是错误的。

<details><summary>Original English</summary>
Here question. If A I am sure that B will choose common option, or should choose A common or safe? If A I am sure that B will choose safe, what then should you choose A? Explain both. answers in numbers, and then tell me why one universal the answer would be incorrect.
</details>

在这里暂停一下。面对合作，A 从合作中得到八分，从稳妥中得到四分，因此合作更好。面对稳妥，A 从合作中得到零分，从稳妥中得到四分，因此稳妥更好。一味合作的指令忽略了落单的风险；一味自保的指令则忽略了当他人加入时自身的收益。B 面临相同的数字，因此“两人都选合作”和“两人都选稳妥”是纯纳什均衡。

<details><summary>Original English</summary>
Pause here. Against the common, A gets eight from common and four from safe, therefore joint is better. Against safe, A gets zero from common and four from safe, therefore Safe is better. Universal instruction to cooperate ignores risk to be left alone. Universal instruction to protect ignores the benefit of oneself, when another person joins. B faces the same in numbers, therefore "both are common", and "both are safe" are pure balances Nash.
</details>

在两人都选合作的局面下，任何单独转向稳妥的店主，其收益都会从八分降到四分。在两人都选稳妥的局面下，任何单独转向合作的店主，其收益都会从四分降到零分。这种结构常被称为“猎鹿博弈”。这个名称源于需要协作的高价值狩猎与可以独自完成的小型猎物捕获之间的对比。信任至关重要，因为吸引人的选择取决于另一个人是否也会这样做。

<details><summary>Original English</summary>
From a situation where both chose common, any the owner who alone switches to safe, loses from eight to four. From the situation, where both chose safe, any the owner who alone switches to common, loses from four to zero. This structure often called "deer hunting." The name comes from the contrast between valuable hunting, which requires cooperation, and smaller prey, which can be obtained myself. Trust has importance, because attractive choice depends on whether another person too will do.
</details>

将此与我们最初的降价博弈作对比。在那里，哪怕面对维持原价的咖啡馆，降价依然是更优选择。而在这里，选择稳妥选项比参与合作项目的那个结果要差。在当前博弈中，合作的结果本身就处于均衡之中。我们需要信心与协调来实现它，而不是自动消除背叛的动机。

<details><summary>Original English</summary>
Compare this with our initial price reduction game. There was a decrease better even against the cafe that held its price. Here is a choice safe option worse than that who is participating in joint project. The result of cooperation is already in equilibrium in this game. We need confidence and coordination, so that to achieve this, not automatic elimination incentive to betray.
</details>

### 聚点与协调

这与街头事件也有所不同。那里的两位店主都想选在同一天，但 A 更偏好周六，另一方更偏好周日。即使确信彼此能协调一致，他们依然无法就停留在哪个均衡达成一致。而在引入此类因素的博弈中，则不存在这种分歧。两位店主共同将该选择排在首位。难点在于相信另一位店主真的会去执行。

<details><summary>Original English</summary>
It also different from an incident on the street. Both owners are there wanted to choose that one the same day, but A preferred Saturday, and Sunday. Even being confident that they are coordinated, they they still couldn't to agree on that, at which equilibrium to stop. In the game with with the addition of such there is no disagreement. Both owners put together first place choice. The difficulty lies in in order to believe that another owner will really do it.
</details>

有时为了协调，甚至不需要传递消息。两位顾客约定碰面，却忘了具体说明在市场的哪个入口附近。两人都宁愿在北门或南门附近碰面，也不愿彼此错过。北门上方引人瞩目的钟表可以使那里成为显而易见的碰面地点。这种吸引注意力的默认选项被称为聚点。这块钟表并不一定会让北门变得更好。它有助于每个人推测对方会做出怎样的推测。

<details><summary>Original English</summary>
Sometimes for coordination even not needed message. Two customers agree on meeting, but forget to specify, near which entrance to market. Both prefer meet near northern or south entrance than cross. Noticeable watch above the north entrance can do it obvious place meetings. Such option for default, that attracts attention, is called focal point. The clock is not definitely does north entrance better. He helps. to every person guess what will guess another.
</details>

### 斗鸡博弈与卸货冲突

现在来看前一个问题的第二部分：当店主们的意愿相反时会发生什么？两家咖啡馆共用一个卸货区，都希望获得最便利的送货时段。每个人都可以坚持自己的时段，或者向对方让步。我们将继续使用收益点数。

<details><summary>Original English</summary>
Now the second part of the previous question: what happens when the owners want the opposite? Cafe have a common area unloading, and both want get the most convenient time for delivery. Everyone can to insist on one's own slot or to yield to another. We will continue. use points benefits.
</details>

如果双方都坚持，送货就会彼此受阻，每人得到负 10 分。如果 A 坚持而 B 让步，A 得到六分，B 得到两分。如果 A 让步而 B 坚持，A 得到两分，B 得到六分。如果双方都让步，他们使用不太便利的时段，每个人得到三分。这是斗鸡博弈（生存博弈）。面对让步的一方，坚持是有利的；但面对坚持的一方，让步则是有利的。最差的结果是双方互相坚持。与包含应用的博弈不同，这里的纯均衡规定了不同的选择。每位参与者都希望成为得到心仪时段的那个人。

<details><summary>Original English</summary>
If both insist, deliveries are blocked each other, and each gets minus 10. If A insists, and B inferior, A gets six, and B—two. If A is inferior, and B insists, A receives two, and B—six. If both are inferior, they use less convenient slots, and everyone gets three. It chicken game (game of survival). Profitably to insist against the one who inferior, but it is profitable to give in to the one who insists. Worst result—it's mutual insistence. On unlike the game with application, clean equilibrium here provide for different election. Every player I would like to be the one who will get the desired slot.
</details>

找出纯均衡。检验以下各项选项：双方都让步、双方都坚持，以及两种不均衡的结果。不要假设最和平的一对状态就必定是稳定的。在此停下并检查单方面偏离。“双方都坚持”的选项行不通，因为每位参与者只要让步，就能将结果从负 10 分提升至两分。“双方都让步”的选项同样行不通，因为每个人都可以通过坚持，将三分提升至六分。“A 坚持且 B 让步”的版本行得通：A 让步会从六分降至三分，而 B 坚持则会从两分降至负 10 分。反向的结果基于同样的原因也成立。因此存在两个均衡，每位店主都更偏好自己坚持的那一个。

<details><summary>Original English</summary>
Find clean ones equilibrium. Check options: both inferior, both insist and two uneven results. Don't assume that the most peaceful couple there must be stable. Stop here and check one-sided deviation. Option «both insist" does not pass, because every player can improve the result from minus 10 to two, having given in. The option "both" "are inferior" also not passes, because everyone can improve with three to six, insisting. Version "A insists, and B inferior" passes. AND would drop from six up to three, having given in, and B would drop from two to minus 10, insisting. Reverse result passes from the same reasons. So, there are two equilibrium, and each the owner gives preference to the one where he insists.
</details>

现在我们来尝试另一个版本。假设装卸区出现了足够容纳两方送货的空间。我们只改变一个结果：当双方都坚持时，每位店主现在得到七分而不是负 10 分。所有其他结果保持不变。面对坚持的一方，坚持带来七分，而让步带来两分。面对让步的一方，坚持带来六分，而让步带来三分。坚持现在严格优于让步。消除冲突成本改变了策略问题。

<details><summary>Original English</summary>
Now let's try another one version. Let's assume, appeared in the compartment enough space for both deliveries. We we change only one result. When both insist, every owner now gets seven points instead of minus 10. All other results remain unchangeable. Against the one who insists, persistence gives seven, while concession gives two. Against the one who gives way, persistence gives six, while concession gives three. Insistence now strictly dominates concession. Elimination collision costs changed the strategic problem.
</details>

### 期望收益与随机化

但 A 往往无法确信 B 会怎么做。假设 A 认为 B 加入应用或稳妥行事的概率相同。合作决策值得冒这个险吗？而且在类似“猜正反”的游戏中，可预测性会导致你被利用。为了应对这两种情况，我们把机会转化为概率。计算期望收益并弄清楚，何时随机化本身就是一种合理的策略。

<details><summary>Original English</summary>
But A often will not be sure that will do B. Let's assume, A believes that B is the same probability will join application or play safely. Is it worth it? joint decision risk? And in games on like "heads or tails"» predictability leads to you will take advantage. That to cope with both cases, we let's transform opportunities on probabilities. Calculate the expected winnings and find out, when randomization in itself is a reasonable strategy.
</details>

让我们从应用开始。A 认为 B 选择合作选项或稳妥选项的概率大致相同。我们可以将这种信念记作概率。概率 1/2 意味着 50% 的机会。对于不能同时发生的一组完备机会，概率相加之和应为一或 100%。如果 A 选择合作选项，A 有一半时间得到八分，有一半时间得到零分。八的一半是四；零的一半是零。将它们相加，平均总共得到四分。如果 A 选择稳妥选项，无论 B 采取何种行动，A 都得到四分。在这样的假设下，这两种选择达到了某种平衡。

<details><summary>Original English</summary>
Let's start with the application. AND believes that B is the same will probably choose common option or safe. We can write it down belief as probabilities. Probability 1/2 means 50% chance. For full set opportunities that are not can happen simultaneously, probabilities should in total give one or 100%. If A chooses common option, A gets eight points half time and zero points half the time. Half past eight—four. Half of zero—zero. Add them, and together it gives in average four points. If A chooses safe option, A gets four points, regardless of B's actions. Under such an assumption two choices are certain balanced.
</details>

我们刚才计算出来的东西被称为期望收益。你将每种可能的收益乘以其概率，然后把结果相加。这里有一个小问题。一个提议以 1/3 的概率带来 $60 的利润，以 2/3 的概率带来 $30 的损失。另一项选择则给出作为保证结果的零。哪里有最高的期望现金收益？

<details><summary>Original English</summary>
That, what we just did calculated, is called expected gain. You multiply each possible win on its probability, and then add results. Here quick question. The offer gives profit of $60 with probability 1/3 and a loss of $30 from with probability 2/3. The alternative gives zero as guaranteed result. Where is the highest? expected cash win?
</details>

停下来注意表示亏损的负号。60 的 1/3 是 20。负 30 的 2/3 是负 20。期望收益为零，因此按期望金额来看，两种选项是等价的。该提议依然规定了 60 的利润或 30 的损失。零是平均值，而不是第三种可能的支付。在具有相同概率的多次独立重复中，平均值趋向于零。这并不意味着每个人都无所谓。看重规避风险的人可能会偏好有保证的零。为了对此类人进行建模，我们会使用反映他们风险偏好的收益，而不是默认假定美元就是他们的效用。

<details><summary>Original English</summary>
Stop and note the minus sign for damage. 1/3 of 60—this is 20. 2/3 of negative 30—This is minus 20. Expected winnings is zero, therefore both options equivalent to expected money. The offer is still provides for 60 profit or loss 30. Zero is average. value, not the third possible payment. By many independent repetitions with the same probabilities average value goes to zero. This is not means that everyone was I don't care. The one who values avoidance risk, can give advantage guaranteed zero. To simulate such person, we would used winnings that reflect their preferences for risk, not silently assumed that dollars—this is their usefulness.
</details>

期望收益还解释了我们留下的另一个悬而未决的问题：可预测性。假设你总是出“石头”。对于任何想出“布”的人来说，你把情况变得极其简单。转向固定的“石头、剪刀、布”循环并不能解决问题，一旦别人研究出这个循环。有时，一个好的计划是让你接下来的行动保持有意的不可预测。让我们为“石头、剪刀、布”设定收益：胜者得一，负者得负一，平局得零。两名选手的收益相加总为零。这是一场零和博弈。一名选手的胜出必定是另一名选手的损失。我们那场包含

<details><summary>Original English</summary>
Expected winnings also explain another the problem we left open: predictability. Let's say you always You play "stone". You made life extremely simple for anyone who wants to play "paper". Transition to fixed cycle «rock, paper, scissors» does not solve the problem when they study this cycle. Sometimes a good plan—to make your next action consciously unpredictable. Let's assign "stone, paper, scissors" winnings: one for victory, minus one for defeat and zero for a draw. Winnings of two players always in the sum give zero. This is a game with zero sum. One player's win—this is definitely a loss another. Our game with there
</details>

<!-- chunk 5/13 -->

咖啡馆里的价格战并不是零和博弈。两位店主可能会一起变得更富有，也可能会一起变得更贫穷。如果你的对手以 1/3 的概率使用每一种行动，“石头”的期望收益就是 1/3*0 + 1/3*-1 + 1/3*1，结果是零。“布”和“剪刀”的期望值也是零。没有任何单独的行动，也没有任何行动的组合能超过这个共同的平均值。如果你也同样进行随机化，对你的对手来说情况也是一样的。每位玩家的组合都是对另一方行动的最优应对。这就是混合策略纳什均衡。

<details>
<summary>Original English</summary>
was no price in the cafe a zero-sum game . Both owners could become or richer, or poorer together. If your opponent uses every action with probability 1/3, "stone" has expected gain 1/3*0 + 1/3*-1 + 1/3*1. This is zero. « Paper and scissors also have zero expectation. No action and no combination actions do not exceed this common average. If you too randomize the same, the same also true for your opponent. A combination of each player is the best response to actions another. This is equilibrium. Nash in mixed strategies.
</details>

混合策略为纯策略赋予概率。在这里，每种纯策略就只是一个行动。这并不意味着机械地轮流交替，因为那样只会成为一种新的固定模式。“抛硬币猜正反”能这样运作，仅仅是因为它只有两个行动且概率各为 1/2，但这种概率水平之所以行得通，是因为那些博弈是对称的。

<details>
<summary>Original English</summary>
Mixed strategy assigns pure probability strategies. Here each pure strategy is just one action. This is not means alternating mechanically, what would be just new template. "Eagle or "tail" works like this only with two actions and with probabilities 1/2, but probability levels worked because these games were symmetrical.
</details>

现在来看一个具有两个行动且总和为零的新博弈，在这里“五五开”是错误的。两位玩家各自独立选择“左”或“右”。当双方都选择“左”时，A 得到两分，B 失去两分。当双方都选择“右”时，A 得到一分，B 失去一分。当他们的选择不同时，A 失去一分，B 得到一分。A 希望出现一致，尤其是在左侧。B 则希望出现分歧。如果 A 总是选择左，B 就会选择右。如果 A 总是选择右，B 就会选择左。无论是寻找一致的人，还是寻找分歧的人，都总想改变自己的选择，因此不存在纯策略均衡。

<details>
<summary>Original English</summary>
Here new game with two actions and zero in the amount where "fifty" "for fifty"—this wrong. Two players regardless choose left or right. When both choose left, A gets two points, and B loses two. When both choose on the right, A gets one, and B loses one . When their elections differ, and loses one, and B gets one . And he wants a coincidence, especially on the left. B wants disagreement. If A always chooses on the left, B chooses right. If A always chooses on the right, B chooses left. Or the one who looking for a match, or the one, who is looking for disagreement, always wants to change the choice, so clean there is no balance.
</details>

设 P 为 A 选择“左”的概率，因此 A 以 1-P 的概率选择“右”。这里有一个稍微奇特的做法：我们通过观察 B 的激励机制来求解 A 的概率。如果 B 要同时使用这两种行动，他就必须在这两者之间无差异。否则，B 就会把我全部的概率都投向最好的那个选项。

<details>
<summary>Original English</summary>
Let P be the probability of what A will choose left, therefore, A chooses right from with probability 1-P. Here a somewhat strange move. We we find probability for A, looking at incentives B. If B is going to use both actions, he has to be indifferent between them. Otherwise B would direct all my probability of the best option.
</details>

如果 B 选择“左”，A 的收益是 2*P 减去 1 减 P 的值。第二部分是负 1 加 P，所以合在一起就是 3P 减 1。如果 B 选择“右”，A 的期望收益是负 P 加上 1 减 P 的值，这变成了 1 减 2P。因为 B 的收益总是与 A 的获胜相反，所以恰恰当这两个表达式相等时，B 才会感到无差异。因此，这个方程描述了 B 的选择，尽管其中的未知数是 A 的概率。

<details>
<summary>Original English</summary>
If B chooses left, A's gain is 2*P minus the value of 1 minus P. Second part —this is minus 1 plus P, so, together it goes 3P minus 1. If B chooses right, expected gain A is minus P plus value 1 minus P. This becomes 1 minus 2P. Since B's gain is always the opposite to win A, B indifferent just then, when these two expressions equal. So, this is the equation describes choice B, although the unknown in it is probability A.
</details>

3P 减 1 等于 1 减 2P。两边同时加上 2P，然后再在两边同时加上 1。5P 等于 2，因此 P 等于 2/5。A 应该在 40% 的情况下选择“左”，在 60% 的情况下选择“右”。我们来验证一下：面对 B 选择“左”的情况，A 得到 2*0.4 减 0.6，等于 0.2；面对 B 选择“右”的情况，A 得到负 0.4 加 0.6，同样是 0.2。B 无论偏向哪个选项都毫无所获。

<details>
<summary>Original English</summary>
3P minus 1 equals 1 minus 2P. Add 2P to both sides, and then add 1 to both parties. 5P is equal to 2, therefore P is equal to 2/5. AND should choose left in 40% of cases and on the right at 60%. Let's check this. Against the fact that B chooses left, A gets 2*0.4 minus 0.6, which is equal to 0.2. Against what B chooses on the right, A gets minus 0.4 plus 0.6, also 0.2. B wins nothing, giving preference any option.
</details>

求出 A 的策略并不能直接让我们得到 B 的策略，所以现在轮到你了。设 Q 为 B 选择“左”的概率。现在让我们使 A 在“左”和“右”之间保持无差异。求出 Q 并计算每位玩家的期望收益。停一下，在这里注意看你求的是谁的概率。

<details>
<summary>Original English</summary>
Finding strategy A does not give we have strategy B, so Now it's your turn. Let Q be the probability of what B will choose left. Now let's make A indifferent between left and right. Find Q and calculate the expected everyone's gain player. Stop. here and watch out for that, whose probability are you find.
</details>

如果 A 选择“左”，A 获得 2*Q 减去 1 减 Q 的值，也就是 2Q 减 1 加 Q，即 3Q 减 1。如果 A 选择“右”，A 获得负 Q 加上 1 减 Q 的量，等于 1 减 2Q。让它们相等：3Q 减 1 等于 1 减 2Q。5Q 等于 2，因此 Q 也等于 2/5。把 Q = 0.4 代入任意一个表达式中：3*0.4-1 等于 0.2。因此，A 的期望收益是 0.2，而 B 是负 0.2。

<details>
<summary>Original English</summary>
If A chooses left, A earns 2*Q minus the value of 1 minus Q. This is 2Q minus 1 plus Q, which is 3Q minus 1. If A chooses on the right, A earns minus Q plus magnitude 1 minus Q, which is equal to 1 minus 2Q. Equalize their. 3Q minus 1 is equal to 1 minus 2Q. 5Q is equal to 2, therefore Q is also equal to 2/5. Substitute Q = 0.4 into any expression. 3*0.4-1 is equal to 0.2. Therefore, expected gain A is 0.2, and B— minus 0.2.
</details>

这个博弈对 A 有微弱的优势，因为左侧的一致带来的收益高于右侧的一致，即使双方玩家的行为都很理性也是如此。为什么不是 50/50？如果 A 在一半的情况下选择“左”，那么 B 选择“左”平均会给 A 带来 2*1/2-1/2，即半个点；而 B 选择“右”会给 A 带来 -1/2 + 1/2，即零点。B 就会乐于每次都选择“右”，因为 B 支付的就是 A 所赢得的。40/60 的比例消除了这种脆弱性差异。

<details>
<summary>Original English</summary>
The game has slight advantage for A, since the coincidence on the left brings more than a coincidence on the right, even if both players act reasonably. Why not 50/50? If A chose left in half of the cases, left choice for B would give A in average 2*1/2-1/2, that is, half a point. Choice on the right for B gave would be A -1/2 + 1/2, i.e. zero . B with pleasure I would choose the right. every time, because B pays what A wins. Ratio 40/60 eliminates this vulnerability the difference.
</details>

这是一种极小化极大考量。A 选择一种使自己的最差期望结果尽可能大的策略，而 B 则选择使 A 的最佳期望结果尽可能小的策略。在这里，他们在 0.2 的水平上相遇。这种保护针对的是平均值，而不是单局比赛。但尽管如此，在具体的某一场游戏中仍有可能输掉一分；而且如果 B 可预测地选择“左”，A 就必须放弃混合策略，直接选择“左”，每次都拿到两分。在更复杂的博弈中，仅有简单的均衡行动是不够的。你还必须检查未进入混合的那些行动是否会带来更多收益，以及各项概率是否落在零到一的范围内且总和为一。

<details>
<summary>Original English</summary>
It minimax consideration. And chooses a strategy that makes his worst expected result as much as possible , and B chooses the one that makes the best expected result And minimal. Here they meet at the level of 0.2. This protection concerns average value, rather than a separate round. But still, maybe to lose a point in a specific game, and if B is predictable chooses left, A has to refuse mixtures, choose left and receive two points each time. IN more complex games simple equilibrium Action is not enough. You should also check whether the actions that did not enter the mix, did not bring more, and also or probabilities lie within the limits of zero to one and in The sum is given as one.
</details>

### 伯特兰价格竞争模型

到目前为止，我们博弈中的收益都是直接给出的。现实中的公司必须通过价格、产量和成本来赚取它们。如果两家公司向同一批买家销售同一种同品类的咖啡豆，价格竞争带来的结果会与产量竞争不同吗？

<details>
<summary>Original English</summary>
So far, payments in our games were given to us ready. Real companies have to earn them through prices, volumes and costs. If two companies sell the same coffee grains of the same kind to the buyers themselves, or will give a price competition other result than competition for production volume?
</details>

让我们借助一个新模型来回答这个问题。这里不再是我们之前收益表中的咖啡馆老板，那里的任何数字在这里都不适用。两家公司向完全相同的客户销售相同的咖啡，而且两家公司生产每包装的成本都是一样的。在我们即将构建的示例中，这些公司可以在一场博弈中定价 30 美元，在另一场博弈中定价 50 美元。区别在于每家公司选择什么，以及这些选择如何影响价格。

<details>
<summary>Original English</summary>
Let's answer the this question is for with the help of a new models. This is not cafe owners from our previous tables payments, and none of those there are no numbers here applies. Two companies sell the same coffee to one and the same to the same customers, and production of each the package costs both firms are the same. IN examples that we now let's build these firms can set price 30 dollars in one game and 50—in another. Difference is that each firm chooses and how are these elections affect the price.
</details>

我们从公司选择价格的模型开始。客户知道这两种价格，并会从较便宜的公司购买。如果价格相同，需求就会被平分。每家公司都能为整个市场提供服务。在每家公司中，边际成本都是每单位 30 美元，没有固定成本。它们同时定价，且随后不能更改。

<details>
<summary>Original English</summary>
Let's start with a model where firms choose prices. Customers know both prices and buy from a cheaper company. If the prices are the same, demand is shared equally. Every company can serve the whole market. In each fixed costs are 30 dollars per unit, fixed there are no costs. They set prices at the same time and not can change them subsequently.
</details>

假设两家都定下了 50 的价格。任何一家公司都可以定一个略低于 50 的价格，以此占领整个市场，并赚取比只在半个市场销售时更多的利润。因此，50/50 并不是均衡。只要双方确立的共同价格高于 30 且仍能吸引买家，这种降价的压力就会一直存在。如果一家公司定价比另一家低，但仍高于成本，那么定价较高的公司就有动力去降低这个有利可图的价格。如果价格高到没有人买，公司也可以降低价格来吸引买家，同时保持正的利润率。

<details>
<summary>Original English</summary>
Suppose, both established price 50. Any firm could appoint price just under 50, to capture the entire market and earn more than when selling on half the market. Therefore, 50/50 is not balance. Such the pressure of the decrease price is valid when both establish a common price above 30, which is all still attracts buyers. If one the company establishes a price lower than another, but still higher than cost, a more expensive company has incentive to reduce this profitable price. If prices are so high that no one buys, the company can lower your price, to attract buyers, keeping while positive margin.
</details>

在每单位 30 美元的价格下，没有哪家公司拥有利润率，因此每家公司获得的利润都为零。如果一家公司提高价格，它就会把自己的客户丢失给竞争对手。如果它把价格降到 30 以下，虽然能吸引客户，但在每单位上都会亏钱。根据我们的假设，两家公司都将价格定在边际成本水平就是伯特兰均衡。边际成本是额外再生产一单位产品的成本。

<details>
<summary>Original English</summary>
At a price of 30 dollars per unit no company has margins, so each gets zero profit. If the company increases the price, it loses his/hers customers for the benefit competitor. If she lowers the price below 30, that attracts customers, but loses money on each unit. According to our assumptions, installation of both firms at the same price level marginal costs are Bertrand equilibrium. Marginal costs are additional costs for production still one unit products.
</details>

这是一个令人印象深刻的结果，其中包含的假设起到了决定性作用。完全相同的商品、知情的客户、充足的产能以及轻松改变价格——这些不仅仅是装点门面的注脚。如果客户喜欢某家店的位置或产品口味，微小的价格差异可能不会迫使所有人都去另一家店。

<details>
<summary>Original English</summary>
It impressive result, and embedded in it assumption play back decisive role. Identical goods, informed customers, sufficient power and ease of price change— it's not easy decorative notes . If customers like location or product taste one store, a small difference in the price may not be forced all go to another.
</details>

你的第一个问题涉及关于产能的假设。两家公司都把价格定在 50，但每家公司在此价格下只能满足一半的市场需求。我们还能断言小幅降价允许一家公司占领整个市场吗？停下来，找出哪一步变成了谬误，不要试图去求解一个全新的模型。不，不能。降价的公司仍然只能满足半个市场，因此期望通过吸引所有客户来获得的收益是无法实现的。这并没有给我们一个新的均衡价格，它只是表明我们之前的证明不再有效。找出错误的假设是有用的，但这并不允许我们随意捏造替代的答案。现在让我们来改变这个决定，舍弃这种限制……

<details>
<summary>Original English</summary>
Your first the question concerns assumption about production capacity . Both companies set the price at 50, but everyone can to provide only half of the market price demand at this price . Can we still to claim that slight decrease prices allow one the company to seize the entire market? Stop and determine which step turns out to be false, without trying to solve absolutely new model. No, not. maybe. A company that reduces price, still can to provide only half of the market, so expected gain from involving everyone customers are unreachable. This does not give us a new equilibrium price. It indicates that our previous proof no longer valid. Find false assumption useful, but it doesn't give permission to invent response to replacement. Now let's change it. decision. Let's discard limitation
</details>

<!-- chunk 6/13 -->

### 古诺模型与产量决定

两家公司的产能再次变得足以按意愿生产任意数量。然而这一次，每家公司都必须在市场价格确定之前先行决定产量。不妨设想提前对咖啡豆进行包装，此时若出现过剩产量，不付出成本就无法消除。在该模型中，每家公司在选择产量时，都将竞争对手的产量视为既定，但总供给决定了买方支付的价格。

<details><summary>Original English</summary>
capacities to both companies again could produce as much as they will want. However, this once each must to decide on quantity before will be installed market price. Imagine bean packaging in advance, when excessive production impossible to eliminate without costs. In the model Every company is a fool chooses the volume production, perceiving volume competitor as given, but cumulative the proposal defines the price paid buyers.
</details>

我们来使用简单的数字。每单位价格为 90 减去总产出量，且不能跌破零。生产每单位的成本仍为 30。在此数学范例中，产量可以是分数。A 公司和 B 公司同时从零及以上选择产量，没有固定成本，产品也没有差异。

<details><summary>Original English</summary>
We we will use simple numbers. Price per unit is 90 minus total output volume, and it cannot fall below zero. Production each unit still costs 30. For this mathematical example volumes can be fractional numbers. Firms A and B simultaneously choose volumes production from scratch and above, without permanent costs and differences in products.
</details>

我们来试一下：A 产出 20 单位，B 产出 20 单位。总发行量为 40，因此价格为 90 减去 40，即 50 美元。每单位带来 50 减去 30 即 20 的利润空间。A 公司获得 1,000 美元收入，在生产上花费 600 美元，因此其利润为 400 美元。B 公司也是如此。我们达到了高于成本价的价格，但我们仍需检验是否有公司想要改变生产量。

<details><summary>Original English</summary>
Let's try. 20 units from A and 20 from B. General the issue is 40, therefore the price is 90 minus 40, that is, 50 dollars. Each unit brings a margin of 50 minus 30, which is 20 . Company A receives $1,000 in income and spends 600 on production, so its profit is 400 dollars. Company B does the same. We reached prices above cost price, but everything we still have to check, Does any of the companies want change the volume production.
</details>

### 最优反应推导与均衡计算

因此，我们把 A 公司的产量记为 QA，B 公司的产量记为 QB。只要价格为正，价格减去每单位产品的成本价就等于 90 减去 QA 减去 QB 减去 30。这可以简化为 60 减去 QA 减去 QB。将该边际乘以 QA，你就会得到 A 的利润。

<details><summary>Original English</summary>
Therefore, let's call it volume company A QA, and the volume Company B QB. Until price is positive, price minus cost price units of production equals 90 minus QA minus QB minus 30. This is simplifies to 60 minus QA minus QB. Multiply this margin by QA and you will get profit A.
</details>

我们固定 B 的产量，并将 60 减去 QB 记为字母 D。为了求出 A 的利润，从 D 中减去 QA，然后将结果乘以 QA。我们可以将其改写为 D 的平方除以 4，减去 QA 与二分之一 D 之间差值的平方。如果将第二种形式的括号展开，我们就会得到第一种形式。在固定 B 的产量时，D 的平方除以 4 这一项无法改变。平方项绝不可能为负，并且我们是在减去它。所以，当这个平方项等于零时利润最高，这种情况发生在 QA 等于 D 除以 2 时。

<details><summary>Original English</summary>
Let us fix the volume B and let's call it 60 minus QB letter D. To find profit A, subtract QA from D, and then multiply the result on QA. We can rewrite this as D in square, divided by 4, minus square differences between QA and half D. If open the brackets in the second version, we will get the first one. At fixed volume B part D in a square, divided by 4, cannot to change. Square part never can be negative, and we subtract it. So, the profit is highest when this the square is equal to zero, what happens, when QA equals D divide by 2.
</details>

不需要数学分析。这种改写仅描述了定价公式为正的部分。如果总生产量达到 90 或更多，价格就会变为零，每单位都会带来 30 美元的亏损。零生产带来零利润，因此这类产量绝不可能是最优的。而如果 D 为零或为负，任何正数都会导致亏损，因此 A 的最佳选择为零。我们把 D 的值代回去。为了找到 A 的最佳反应，从 60 中减去 B 的产量，然后将结果除以 2。如果结果为负，A 就选择零。换一下名称，B 的最佳反应也具有相同的形式。

<details><summary>Original English</summary>
Mathematical analysis not needed. It rewriting describes only the part where the pricing formula is positive. If total volume production reaches 90 or more, price becomes zero, and each unit brings a loss of 30 dollars. Production zero brings zero, therefore such volumes can never be the best. And if D is zero or is negative, any positive number causes losses, therefore the best choice A—zero. Let's substitute value D back. That find the best one answer A, subtract the volume of B from 60, then divide result by 2. If the result is negative, And chooses zero. Best answer B has the same shape with changed names.
</details>

这些图表展示了面对竞争对手的任意产量时，每家公司想要生产多少。在对称均衡中，两个产量都等于同一个数值 Q。因此，Q 等于 60 减去 Q 的一半。两边乘以 2：2Q = 60 - Q。两边加上 Q：3Q = 60。除以 3，Q 就是 20。我们得到了与之前相同的结果，现在则是针对每种可能的产量都进行了验证。

<details><summary>Original English</summary>
These graphs show, how much each company wants to produce for any volume competitor. IN symmetrical both in equilibrium the volumes are equal one and the same number, Q. Therefore, Q equal to half from 60 minus Q. Multiply both sides in two. 2Q = 60-Q. Add Q to both parties. 3Q = 60. Divide by three, and Q is 20. We got the same one result, as well as before, now tested for every possible volume.
</details>

这里是你们的第二个问题：保持相同的需求，但将两家公司产品的单位成本从 30 增加到 45。在反应公式中，数字 60 变成了 90 减去 45。在对称均衡中每家公司生产多少，价格又会是多少？暂停一下并按这些步骤算一下。90 减去 45 等于 45。均衡方程：Q 等于 45 减去 Q 的一半。乘以 2，加上 Q，你得到 3Q 等于 45。所以，每家公司生产 15。总生产量为 30，价格是 90 减去 30，即 60。每家公司的利润空间是 60 减去 45，等于 15。所以，利润是 15 乘以 15，即 225。

<details><summary>Original English</summary>
Here is yours. second question. Leave the same demand, but increase unit cost products for both firms from 30 to 45. In answer formula the number 60 becomes 90 minus 45 . How much does it produce? every company in symmetrical equilibrium and what will be price? Pause and go through these steps. 90 minus 45 is equal to 45. Equation equilibrium: Q is equal to half of 45 minus Q. Multiply by two, add Q, and you get 3Q is equal to 45. So, each firm produces 15. Total volume production is 30, and the price is 90 minus 30, i.e. 60. The margin of each firms—that's 60 minus 45, which is equal to 15. So, profit is 15 multiply by 15, or 225.
</details>

### 伯川德与古诺比较及序贯博弈

现在让我们回到 30 美元的初始成本，我们最初的谜题就解开了。在我们严格假设下的价格竞争（伯川德竞争）给出了 30 的价格。同时对商品数量做出承诺则给出了 50 的价格。公司既没有变聪明，也没有变不聪明。在第一个小模型中，降价可以占领整个市场。在第二个模型中，增加产量也会降低公司自身获得的价格。我们改变了选择，因此也改变了其结果。

<details><summary>Original English</summary>
Now let's return initial cost in 30 dollars, and ours introductory puzzle solved. Price competition for our hard assumptions Bertrand gave a price of 30. Commitment to quantity of goods at the same time they gave a price of 50 . Firms have neither become smarter, nor less smart. In the first small model price reduction could capture the entire market. In the second—an increase production also lowered the price, which received it herself firm. We changed choice, so we changed it consequences.
</details>

客户对它的看法与公司不同。在模型中，愿意支付 30 到 50 之间的买家数量并没有购买，尽管他们对咖啡豆的估价高于其成本。在这些简化假设下，此类错失的交易是以限量发行的效率为代价的。公司的利润与贸易总利润是不同的指标。

<details><summary>Original English</summary>
Clients see it differently than companies. In the model number of buyers, willing to pay from 30 up to 50, do not buy, although they value grains higher than theirs cost. During these simplified assumptions such lost deals are at the cost of efficiency limited edition. The company's profit and total profit from trade—this different indicators.
</details>

到目前为止，两家公司都是在看不到对方决定的情况下做出选择。但一家公司可以先建立产能，并留给竞争对手做出回应的可能。当一个选择比另一个选择更早被察觉时，行动顺序可能会改变结果。为了分析这一点，我们将把表格展开为决策树。

<details><summary>Original English</summary>
Until that both companies made a choice, not seeing solutions alone one. But the company can first build up power and leave to a competitor possibility answer. When alone the choice becomes noticeable earlier than the other, the sequence of actions can change the result. To analyze this, we will unfold table into a tree decisions.
</details>

### 进入博弈与逆向归纳法

那么，让我们画一棵类似这样的树，带入新的情境和全新的数字。没有从咖啡豆市场或之前的咖啡馆表格中继承任何东西。一家新咖啡馆正在审视在现有咖啡馆旁边开店的可能性，而现有咖啡馆的老板宣称，无论怎样，新来者都会面临价格战。新手可能会从字面上接受这一警告并不予介入。或者他可以提出一个更好的问题：当我开店之后，战斗对这家店的老板来说依然会是最佳选择吗？

<details><summary>Original English</summary>
So, let's let's draw something like this tree with new situation and fresh in numbers. Nothing. transferred from the market grain or previous cafe tables. New cafe reviews possibility of discovery next to the existing one , and the owner the latter announces, that on any A newbie is waiting for a price war. A beginner could accept it warning literally and to stay away. Or he could to put better question. When am I already I will open it, will it be still fighting the best choice for the owner of the establishment?
</details>

首先，我们将称之为“参与者”的新手做出选择：进入市场还是置身事外。如果他置身事外，他得到零，而现有公司（即老机构）得到 100。如果他进入，现有公司看到这一点并做出选择：对抗还是瓜分市场。瓜分市场让每家企业得到 40。对抗让参与者得到 -20，让现有公司得到 -10。这些是同一时期的净利润（以美元计），我总是先报出参与者的收益。两家公司都知道这些数字，并且偏好更多的金钱。声誉和隐性成本尚未包含在该决策树中。

<details><summary>Original English</summary>
First a newbie, which we will call " participant", chooses: to enter the market or to stay away. If he stays aside, he gets zero, and the operating company, that is, an old institution, gets 100. If he included, operating company sees this and chooses: to fight or to divide market. Market division gives each firm 40. The struggle gives the participant minus 20, and operating company—minus 10 . These are net profits in dollars for the same period, and I always I will call first participant's winnings. Both companies know these numbers give preference for larger money. Reputation and hidden costs yet not included in this tree.
</details>

在决策树中，有人做决定的每一个点都称为节点。参与者节点首先出现，进入分支通向现有公司的节点。自然的诱惑是从最开始着手，去问进入看起来是否令人望而生畏。相反，逆向归纳法从最后一个决定开始。如果发生市场进入，在位参与者会将对抗的 -10 与合作的 40 进行比较。合作更好。在这个节点上，来自竞争对手缺席的 100 单位已经不可得了，无论激进的参与者如何没有提及它们。

<details><summary>Original English</summary>
In the tree every point where someone makes a decision, is called a node. The participant node is leaving first, and the entrance branch leads to the node of the current companies. Natural temptation—to start with from the very beginning and to ask if it looks The entrance is intimidating. Instead, the reverse induction begins from the last decision. If market entry took place, active the player compares minus 10 from the fight out of 40 from cooperation. Collaboration is better. IN this node 100 units from absence competitor already unavailable, as it were hot player I didn't mention them.
</details>

现在让我们回到那个进入的人：他预期会得到合作，因此进入会给他带来 40，而克制进入则带来零。他选择进入。预测的路径是：进入，然后合作。我们首先解决了后面的决定，并用它来评估前面的决定。在位参与者不愿看到没有竞争对手的心态，在进入发生之后，使得对抗变得有利可图。

<details><summary>Original English</summary>
Now let's go back to that, who is entering? He expects cooperation, so the input gives him 40, while abstinence from input gives zero. He enters. Predicted path: login, and then cooperation. We first solved later decision and used it for evaluation of the previous one. Reluctance of the actor player to see no competitor made a fight profitable after that, how the entry occurred.
</details>

我们来尝试一种变体。假设现有参与者拥有如此巨大的成本优势，以至于进入之后的对抗能给他带来 50 而不是 -10。进入者在对抗中仍然得到 -20，合作仍各得 40，而克制进入仍然保持不变。现在逆向归纳法意味着什么？停下来，在解决第一个决定之前先解决最终的决定。

<details><summary>Original English</summary>
Let's try an option. Suppose the current the player has so big cost advantage, that the fight after entrance gives him 50 instead of minus 10. The one, who enters, still gets minus 20 from struggle, cooperation gives 40 each, and refrain from entering remains unchangeable. What now? implies the reverse induction? Stop. and solve the final decision before the first.
</details>

在现有参与者的节点上，对抗带来 50，而合作带来 40，因此他选择对抗。预料到这一点，进入者会将进入的 -20 与克制带来的零进行比较。他选择克制进入。预测发生了改变，因为落实威胁的动力发生了改变，而不是因为威胁是用更大的字体写出的。在这场改变了的博弈中，进入者的策略是克制。在位参与者的策略是在有进入的情况下进行对抗，即使在预测路径上这绝不会起作用。我们把这个计入答案，因为进入者的决定取决于之后会发生什么。

<details><summary>Original English</summary>
In the node of the current player fight gives 50 , and cooperation—40, therefore he chooses to fight. Waiting for this, he, who enters, compares minus 20 from the entrance with zero from retention. He refrains from entrance. Forecast changed, because changed incentive to perform threat, not because the threat was written in larger font. IN this changed game the strategy of the one who enters—to refrain. Incumbent's strategy player—to fight in in case of entry, even if on predicted path it never works. We turn this on answer, because the solution the one who enters, depends on what would happen after
</details>

<!-- chunk 7/13 -->

### 不完全信息博弈与信息集

另一种选择。这里是一棵稍大一点的博弈树。

<details><summary>Original English</summary>
another choice. Here a little bigger tree.
</details>

供应商首先向咖啡馆提议较低或较高的配送费。咖啡馆看到费用后，决定接受或拒绝。因此，策略层面，咖啡馆应该确定在每种付费提议后自己会做什么。接受低费用并拒绝高费用——这是一种策略。两者都接受——是另一种策略。如果费用会影响选择，仅仅说“接受”并不是一个完整的行动计划。

<details><summary>Original English</summary>
Provider first proposes cafe low or high fee for delivery. Cafe sees fee, and then accepts or rejects its. So, the strategy The cafe should determine, what will it do after each payment. Accept low and to reject a high—it one strategy. Accept both—another. Just to say "to accept" is not full plan if the fee affects choice.
</details>

现在假设供应商隐瞒了费用，而咖啡馆必须在看不到费用的情况下去接受或拒绝。咖啡馆不能再选择“如果低就接受”以及“如果高就拒绝”，因为他不知道自己处于哪种情况。在博弈树上，我们将博弈方无法区分的决策节点连接起来，形成一个信息集。博弈方必须为其中的每一个节点选择相同的行动。

<details><summary>Original English</summary>
Now let's say, the supplier records the fee is hidden, and the cafe should accept or reject it, no seeing her. Cafe can't anymore choose to "accept, if low" and "reject if "high", because he doesn't know, in what situation is located. On a tree we connect the nodes making decisions that the player cannot to distinguish, in information set. The player must choose the same effect for everyone them.
</details>

隐藏的费用对结果仍然很重要，咖啡馆只是无法在行动中依赖于它。仅在纸上的各个分支上画图，并不能给咖啡馆安装监控摄像头。

<details><summary>Original English</summary>
Hidden fee still important for results. Cafe just can't to depend on her in in their actions. Painting individual branches on The cafe doesn't give paper surveillance cameras.
</details>

这里是你们的第二个问题。两家公司在装有价格的密封信封上签字。A 先签，B 后签，但 B 看不到 A 的信封。B 能针对 A 的实际价格做出另外的价格选择吗？

<details><summary>Original English</summary>
Here is your second one. question. Two companies sign sealed envelopes with prices. A signs first, and B later, but B cannot read envelope A. Can B choose another price in response to actual price of A?
</details>

暂停一下，解释一下为什么不能。不能。B 没有看到 A 的价格，因此无法对其做出反应。在时间上稍后定价，在策略上与同时定价是相同的。B 可以根据自己对 A 价格的假设来行动，但如果信号没有揭示 A 的选择，后行动并不能带来任何优势。

<details><summary>Original English</summary>
Stop and explain what is not enough. No. B not saw price A, so no maybe on her react. Setting the price later in time, strategically, the same, which is simultaneous. B can act on your assumptions about price A, but later the move does not give any advantages, if the signal is not reveals choice A.
</details>

### 子博弈完美均衡与不可信威胁

因此，逆向归纳法在信息完全的有限博弈中显然有效，在这种博弈中，每位博弈方在做决策之前都能看到先前的行动。对于隐蔽行动，我们必须考虑信息集，并且通常需要加入信念。

<details><summary>Original English</summary>
So, the reverse induction clearly works in finite games with full information, where everyone the player sees previous actions before making a decision. WITH by covert actions we must take into account information sets and add often belief.
</details>

我们还需要检查结果相等的情况。如果企业从对抗和合作中都获得 40，那么这两种选择都将是最优反应，而进入与否将取决于该选择。请指明相等情况的存在，不要默默选择一个方便的答案。

<details><summary>Original English</summary>
To us also needed check cases equality of results. If the firm receives 40 both from the struggle and from cooperation, both options will be best answer, and the input will depend from choice. Please specify the existence of equality, and don't choose silently convenient answer.
</details>

最初的威胁失败了，因为进入后的对抗是无利可图的。或者，在对方进入之前，在位公司是否能改变博弈，使威胁变得可信？先动一定能自动带来优势吗？我们将对两种选择都进行检验，严格把承诺作为解决方案的一部分。

<details><summary>Original English</summary>
Initial threat failed because fight after entry was unprofitable. Or can the company change game before entering, so the threat became reliable? And does it give first move automatic advantage? We will check. both options, having done exactly obligation part of the solution.
</details>

对公司来说，如果竞争对手相信价格战，那将是有利的。但在我们的博弈树上，进入后的对抗给公司带来负 10，而合作带来 40。只有当一项威胁在行动时刻的执行本身就是最优反应时，它才是可信的。仅仅对局势感到不满是不够的。

<details><summary>Original English</summary>
It would be profitable for the company, so that the competitor believes in price war. But on our tree fight after entry gives the company minus 10, while cooperation—40. There is a threat reliable when it execution is best answer at the moment of action. Be dissatisfied situation not enough.
</details>

普通的纳什均衡可能会漏掉这种空洞威胁。我们来看这一对策略：竞争对手选择不进入，而公司选择在对方进入时展开对抗。假定公司的计划是对抗，放弃进入给竞争对手带来 0，而不是负 20。所以，不进入是最优反应。因为竞争对手不进入，公司永远不需要真正采取行动。如果将计划改为合作，公司的收益仍将是 100，不会发生改变。没有任何一方能从策略改变中获益，因此这对策略通过了纳什检验。但是，如果进入确实发生了，该计划会迫使公司获得负 10 而不是 40。

<details><summary>Original English</summary>
Ordinary equilibrium Nesha can miss such an empty threat. Let's take this pair. strategies: do not enter for a competitor and to fight in case of entry for the company. Provided plan to fight, Denial of entry gives competitor zero instead of minus 20. So, refrain from entering—this is the best respond. Because the competitor does not enter, the company never have to act. Change of plan to cooperation has not changed her income would be 100. None the player does not benefit from changes in strategy, therefore the couple passes the test Nash. But if the entrance took place, the plan forced would like to get the company minus 10 instead of 40.
</details>

这一计划之所以存在，仅仅是因为没有人去检验它。在这个完全信息博弈树中，每一个决策点连同其后续的所有事态发展，都构成一个独立的博弈。这个较小的博弈被称为子博弈，而整个博弈本身也被视为其中之一。子博弈完美均衡——是一组策略，它在每一个子博弈中都给出最优反应，即使在那些路径未引向的子博弈中也是如此。在这里，逆向归纳法给出了这个结果：进入，并在发生进入时选择合作。

<details><summary>Original English</summary>
The plan exists only because that no one knows him checks. In this tree full information each acceptance point solutions together with everything further development events form a separate game. This smaller game called a sub-game, and the whole game too is considered one of them. Perfect for subgames equilibrium—is a set of strategies, which gives the best answers in each underheat, even in those to which the path does not lead. Here is the reverse induction gives this result. Enter and cooperate if there will be an entrance.
</details>

### 承诺与沉没成本

改变它的一种方法是——真正的承诺。假设在市场参与者做出决定之前，现有博弈方可以购买设备以降低其未来的运营成本，并且市场参与者看到了这项购买。有了这套设备，在市场进入发生后的对抗给现有博弈方带来 50 个单位的营业利润（在考虑设备成本之前）。瓜分市场仍然带来 40，而对抗仍然给市场参与者带来负 20。因此，在市场进入后，对抗现在成为了现有博弈方的最优反应。

<details><summary>Original English</summary>
One way change it—real obligation. Let's assume that to how the participant the market will decide, the current player can purchase equipment, which will lower it future operations expenses, and the participant the market sees this purchase. With this equipment fight after entering the market brings to the current player 50 units operational profit to cost consideration equipment. Distribution the market still gives 40, and still fighting brings to the participant minus 20. So, after market entry the fight is now best answer current player.
</details>

市场参与者将进入市场的负 20 与克制不进入的 0 进行比较，他选择止步。但是设备并不是免费的。假设它花费 30，需预先支付。现在我们需要区分三个指标：来自市场的营业利润、已经支付的沉没成本，以及作为前两者之差的总利润。

<details><summary>Original English</summary>
The participant compares minus 20 from the entrance to market with zero from detention, and he stays away. But the equipment is not free of charge. Let's assume it is costs 30, paid in advance. Now we need to distinguish three indicators: operating profit from the market, sunk costs that have already been paid, and total profit, which is the difference between first and second.
</details>

没有设备时，进入市场发生，瓜分市场，现有博弈方的总利润是 40。有了设备，进入市场被遏制，活跃博弈方保留了 100 个单位的营业利润。其总利润是 100 减去 30，即 70。70 优于 40，所以在这种情况下承诺是合理的。

<details><summary>Original English</summary>
Without equipment is being logged in market, firm share, and total profit current player is 40. With equipment entrance to the market is holding back, and active player stores 100 units operational profit. Its total profit is 100 minus 30, that is 70. 70 is better than 40, so in this case the obligation is justified.
</details>

这里是你们的第一个问题。将设备费用增加到 70，保持其对营业利润的影响不变。活跃博弈方无论如何都会购买它吗？请分别回答两个单独的问题：购买后威胁是否具有说服力？预先购买是否划算？

<details><summary>Original English</summary>
Here is yours. first question. Increase the value equipment up to 70, keeping it impact on the operating profit unchanged. Will it be active? player anyway buy it? Give answer to two individual questions. Or there is a threat convincing after purchases, and is there bargain purchase in advance?
</details>

停下来思考一下。购买后，威胁仍然具有说服力。70 无论活跃博弈方是对抗还是瓜分市场都已经支付了，因此这不会改变 50 对 40 的比较。然而，在购买之前，比较看起来就不同了。购买阻碍了市场进入，留下 100 减去 70，等于 30。放弃购买会导致市场进入和利润瓜分，带来 40。30 小于 40，所以现有博弈方不应该购买设备。承诺可能代价过高，而不值得选择。当对抗的代价高过单纯共同利用市场时，在对抗中获胜就不那么引人注目了。

<details><summary>Original English</summary>
Stop and Think about it. After shopping threat everything still remains convincing. 70 already paid independently from fighting active player or shares the market, so it doesn't change comparison 50 out of 40. However, before buying the comparison looks like otherwise. Purchase hinders market entry and leaves 100 minus 70, which is equal to 30. Cancellation of purchase leads to the entrance to market and division profit, which gives 40. 30 less than 40, so the current player is not must buy equipment. The obligation may to be too expensive, to choose it. Victory in less confrontational impressive when she costs more than just common market use.
</details>

承诺还必须是对它要影响的博弈方可见或可靠易懂的。隐蔽的设备可能会改变活跃博弈方实际会做的事，但它无法阻止没有理由相信局势已变的参与者。

<details><summary>Original English</summary>
Commitment also must be visible or reliably understandable for the player on whom it should have an impact. Secret equipment can change what active player would actually do, but it won't stop participant who has there is no reason to believe that something has changed.
</details>

### 斯塔克尔伯格产量竞争

当企业选择生产产量时，承诺也很重要。让我们回到我们关于竞争企业的课程中的大豆市场，带着它最初的数字。价格是 90 减去总产量，且不能跌破零。每单位生产成本为 30 美元。当企业 A 和 B 同时选择时，各自生产 20 个单位，并赚得 400 美元。

<details><summary>Original English</summary>
Commitment also important when firms choose volumes production. Let's go back to the market beans from our lesson about competing firms with its initials in numbers. Price is 90 minus total volume release and it is not may fall below zero. Each unit costs 30 dollars in production. When firms A and B chose simultaneously, each produced 20 units and earned 400 dollars.
</details>

现在 A 首先承诺其产量。B 观察到这一点，然后才做出选择。并且 A 随后无法改变其产量。我们已经知道企业 B 的最优反应。如果 A 的产量小于 60，从 60 中减去它，并将结果除以二，以此求出 B 的产量。如果 A 的产量为 60 或更多，B 就不生产任何东西。

<details><summary>Original English</summary>
Now A takes over obligations regarding volume first. B is watching this and only then does he choose. AND cannot change his/her production volume subsequently. We already know best answer firm B. If the volume production A smaller for 60, subtract it from 60 and divide the result by two, so find the volume production B. If production volume A is 60 or more, B nothing produces.
</details>

让我们将 A 的产量称为 Q。B 对应生产 30 减去 Q 的一半，因此总产量等于 30 加上半个 Q。价格是 90 减去该总和，等于 60 减去半个 Q。我们减去 30 美元的成本价，A 在每单位上获得 30 减去半个 Q 的利润空间。A 的利润——即 Q 乘以该利润空间，即 30Q 减去二分之一 Q 的平方。

<details><summary>Original English</summary>
Let's call it volume A through Q. B corresponds to 30 minus half of Q, so general issue equals 30 plus half Q. Price is 90 minus this the sum equals 60 minus half of Q. Let's subtract cost price of 30 dollars, and A gets margin of 30 minus half Q for each unit. Profit A—this is Q multiplied by this margin, i.e. 30Q minus half of Q squared.
</details>

我们可以将其重写为 450 减去 1/2 乘以 Q 与 30 之差的平方。平方不能为负，因此当该差值为零时利润最高，即在 Q 等于 30 时。此时 B 生产 15。总产量为 45，价格为 45，从而留出每单位 15 美元的利润空间。A 赚得 30 乘以 15，即 450。B 赚得 15 乘以 15，即 225。

<details><summary>Original English</summary>
We can rewrite it's like 450 minus 1/2 multiply by the square the difference between Q and 30. A square cannot be negative, therefore the highest profit, when this difference is zero, at Q, which is equal to 30. Then B produces 15. General the output is 45, and price—45, which leaves margin of $15 per unit. And earns 30* 15, or 450. B earns 15* 15, or 225.
</details>

该公式仅涵盖小于 60 的产量，因此我们应当检查其余情况。在 60 或更多时，B 不生产任何东西，但 A 自己的产量将价格压低至 30 或更低。其利润空间随后变为零或负数。30——这是总体上最好的承诺。这是斯塔克尔伯格产量博弈。A 比同时选择时赚得更多，因为他

<details><summary>Original English</summary>
This formula covered only volumes less than 60, therefore we should check the rest. At 60 or nothing more B produces, but own Issue A lowers the price to 30 or less. Its the margin then becomes zero or negative. 30—this best obligations in general. It's a game of volume. Stackelberg. AND earns more than while simultaneously choice, because he
</details>

<!-- chunk 8/13 -->

做出选择，预判 B 的反应。做出承诺关乎你自己的业务。你的第二个问题：假设 A 承诺生产 20，B 会生产多少？价格是多少？以及 A 能赚多少？

<details><summary>Original English</summary>chooses, 

anticipating





reaction 

B.





Commitment 

makes





your 

own 

business. 

Your





second 

question.





Suppose, 

A





 undertakes





produce 

20. 

What





produces 

B? 

What 

is 

the 

price? 

AND





How 

much 

does 

A 

earn?</details>

利用 B 的反应函数，不要认为 B 会保持在 15 的水平。我们在这里停一下。对 B 而言，60 减 20 等于 40。40 除以 2，我们得到产量为 20。总发行量（总产量）是 40，价格是 50，A 的利润率是 20 美元。所以，A 赚了 20*20，也就是 400，与两家公司同时做决定时的金额相同。

<details><summary>Original English</summary>Use





reaction 

B, 

not





consider 

that 

B





remains 

at 

the 

level





15. 

Let's 

stop 

here. 

For





B 

60-20 

equals 

40.





Dividing 

40 

by 

2,





we 

get 

the 

volume





production 

20.





General 

release





is 

40, 

the 

price 

is 

50,





and 

A's 

margin 

is 

$20.





So, 

A 

earns 

20*20,





that 

is, 

400, 

the 

same 

amount,





How 

many 

companies?





were 

elected 

simultaneously.</details>

承诺生产 30 会将 A 的利润推高至 450，即使价格在下降。以较小的利润率售出更大数量的单位，终归可能是更好的选择。先行动总是有帮助吗？

<details><summary>Original English</summary>Obligation





produce 

30 

boosts





profit 

A 

up 

to 

450,





even 

though





the 

price 

is 

falling. 

Bigger





number 

of 

units 

from





with 

a 

smaller 

margin 

everything





one 

might 

be 

better





option. 

Is 

it 

always?





helps 

to 

walk





first?</details>

让我们回到“猜正反”游戏，其中 A 希望匹配，而 B 希望不一致。如果 A 的选择是公开的，并且 B 看到这个选择，B 只需选择另一面，A 每次都会输。当玩家同时且随机地选择时，A 的期望收益等于零。在这里，公开自己的行动恶化了 A 的处境。所以，先发优势是对比得出的结论，而不是早到的奖励。

<details><summary>Original English</summary>Let's 

go 

back.





to 

the 

game 

"heads 

or 

tails"





", 

where 

A 

wants 

a 

match, 

and 

B





wants 

disagreement.





If 

A 

chooses





is 

open, 

and 

B 

sees





this 

choice, 

B 

simply





chooses 

the 

other 

side, 

and 

A





loses 

every 

time. 

When





players 

chose





simultaneously 

and





accidentally,





expected 

gain 

A





was 

equal 

to 

zero. 

Here





revealing 

one's 

move





worsened 

the 

situation





A. 

So, 

the 

advantage





the 

first 

move 

is





conclusion 

from 

these





comparisons, 

not 

prizes





for 

coming





earlier.</details>

### 重复博弈与合作

我们之前每次只考虑了一次互动。让我们回到那些决定是否降价的咖啡馆老板。抑或失去未来的利润足以让维持今天的价格变得合理？为了回答这个问题，我们必须为明天提供确定的收益。让我们在我们首次遇到这个问题的博弈中定义明天的收益。

<details><summary>Original English</summary>We 

considered





only 

one 

interaction





at 

a 

time. 

Let's 

go 

back.





to 

the 

cafe 

owners,





who 

decide 

whether





lower 

prices. 

Or





maybe 

loss





future 

profits





save





today's 

price





justified? 

That





to 

answer 

this, 

we





we 

have 

to 

provide





tomorrow





a 

certain 

gain.





Let's 

define





win 

for





tomorrow 

at





the 

game 

where 

we 

first





encountered 

this





problem.</details>

在咖啡馆老板决定一天的价格的原始博弈中，无论对方的行动如何，降价对每个老板而言都是最优反应。因此，双方都降低了价格，并且双方都陷入了更糟的境地。但假设他们期望明天和后天再次相遇，没有已知最后一天。今天的选择现在可以改变另一个老板随后会采取的行动。

<details><summary>Original English</summary>IN





original 

game 

with





cafe 

owners





chose 

prices 

for 

one





day. 

Price 

reduction





was 

the 

best





answer 

for





each 

owner,





regardless 

of 

actions





another. 

So, 

both





lowered 

prices 

and 

both





found 

themselves 

in 

the 

worst





situation. 

But





let's 

assume 

that 

they





are 

expecting 

to 

meet





again 

tomorrow 

and





the 

day 

after 

tomorrow, 

without





last 

known





day. 

Today's 

choice





now 

can 

change 

that





that 

another 

owner





will 

do 

it 

later.</details>

明天并不会奇迹般地创造合作，它创造了另一个需要计算的后果。我们将使用最初的每日利润。如果双方老板都维持价格，每人赚 100 美元。单方面降价的那个人得到 150，而维持价格的老板得到 30。如果双方都降价，每人将赚 60。

<details><summary>Original English</summary>Tomorrow 

is 

not





creates 

collaboration





magically. 

He





creates 

another 

one





consequence 

that 

follows





calculate. 

We





 we will use





initial 

daily





profits. 

If 

both





owners 

keep





their 

prices, 

each





earns 

$100.





The 

one 

who 

lowered 

the 

price





alone, 

gets 

150,





and 

the 

owner, 

who





saved 

it—30. 

If





both 

will 

lower 

prices,





everyone 

will 

earn 

60.</details>

现在设想一个提议的策略：只要没有老板降过价，你就维持你的价格；在出现任何降价之后，你在随后的每一轮中都降低价格。这被称为“冷酷触发”（strict trigger）策略，因为它的惩罚永不结束。让我们假设每位老板都能清楚看到对方的价格，并且双方都理解该策略。企业之间的合作可能会伤害顾客。这同样的计算也可以描述我们所祝贺的合作，例如关爱公共资源。

<details><summary>Original English</summary>Now 

imagine





 proposed





strategy. 

You





keep 

your 

price,





while 

none 

of





owners 

never





lowered 

his. 

After





any 

decrease





you 

reduce 

the 

price 

in





to 

each 

subsequent 

one





round. 

It





 is called





the 

strategy 

of 

"strict





trigger", 

because 

its





punishment 

never





ends.





Let's 

assume 

that 

everyone





the 

owner 

sees 

clearly





the 

price 

of 

the 

other, 

and 

both





understand 

the 

strategy.





Collaboration 

between





firms 

can





harm 

customers.





This 

same 

calculation





can 

also 

describe





the 

cooperation 

we





Congratulations, 

for 

example,





caring 

for 

the 

common





resource.</details>

接下来我们需要一种方法来确定未来有多重要。设 delta 表示下一轮相比于这一轮有多重要。这可以表示耐心、关系持续的概率，或两者兼具。Delta 至少为零且小于一。如果 delta 等于 0.8，那么下一轮的 100 美元在老板今天评估时价值 80 美元。两轮之后，同样的 100 乘以 0.8 两次，得出 64。Delta 必须保持在 1 以下，因为每天永远 100 美元且不减少将没有最终总额。

<details><summary>Original English</summary>Next 

to 

us





need 

a 

way





to 

determine 

how 

much





important 

future.





Let 

the 

delta





indicates 

how 

much





next 

round





more 

important 

comparatively





with 

this. 

This 

can





to 

display 

patience





, 

probability





continuation 

of 

the 

relationship





or 

both 

together.





Delta 

is





at 

least 

zero 

and





less 

than 

one.





If 

delta 

is 

equal 

to





0.8, 

then 

100 

dollars 

in





next 

round





cost 

80 

dollars,





when 

the 

owner 

evaluates





them 

today. 

Through





two 

rounds 

the 

same 

100





multiply 

by 

0.8 

twice,





which 

gives 

64. 

Delta 

has





stay 

below





units, 

since 

100





dollars 

every 

day 

forever





without 

reduction 

did 

not 

have





b 

of 

the 

final 

amount.</details>

这是你的第一个问题。简单的事情能让合作盈利吗？将 delta 设为 1/2。永远维持价格现在带来 100，然后折合今天相当于 50，然后是 25，以此类推。假设一位老板降价，而另一位维持价格。降价的老板现在得到 150。此后，双方老板永远降价，因此惩罚带来的支付价值 30，然后是 15，然后是 7.50 美元，以此类推。比较这两个总额。

<details><summary>Original English</summary>Here





your 

first 

question.





Does 

it 

do 

simple 

things?





 availability





 future





Is 

cooperation 

profitable?





Set 

the 

delta 

to





1/2. 

Price 

retention





forever 

gives 

100 

now,





then 

50 

in





 today's





equivalent, 

then 

25





and 

so 

on.





Let's 

say 

one





the 

owner 

lowers 

the 

price,





and 

the 

other 

keeps 

it.





The 

one 

who 

lowered





gets 

150 

now.





After 

that, 

both





owners 

are 

reducing





prices 

forever, 

so





payments 

from





punishments 

cost 

30,





then 

15, 

then 

7.50





dollars 

and 

so 

on.





Compare 

the 

two 

amounts.</details>

这里有一个提示：每轮减少一半的现金流，等于首笔支付加上其自身总额的一半。暂停并尝试一下。让我们把合作的总额称为 V。在第一个 100 之后的所有部分——又是同样的流，只是缩减了一半。因此，V 等于 100 加上半个 V。两边都减去半个 V，你将得到半个 V 是 100。因此，V 等于 200。惩罚流的运作方式相同。它的总和是 30 加上自身的一半。因此，总额的一半是 30，整个总额是 60。加上 150 的即时利润，降价的价值是 210。未来是存在的，但降价仍然以 10 美元胜出。明天的回报是真实的，只是它还不够昂贵（价值还不够高）。

<details><summary>Original English</summary>Here's 

a 

hint. 

Flow,





decreasing





twice 

each





round, 

equal 

to





first 

payment 

plus





half 

of 

it





own 

amount.





Stop 

and





try 

it. 

Let's 

call 

it





amount 

of 

cooperation 

V. 

All





after 

the 

first 

100—this





the 

same 

stream 

again





, 

only 

reduced





twice. 

So, 

V





equals 

100 

plus





half 

V. 

Subtract





half 

V 

from 

both





parties, 

and 

you





you 

will 

get 

that





half 

of 

V 

is 

100





. 

So, 

V 

is 

equal 

to 

200.





Punishment 

Flow





works 

the 

same 

way. 

Its





the 

sum 

is 

30 

plus





half 

of 

it





himself. 

Therefore,





half 

of 

the 

amount 

is 

30, 

and





whole—60. 

Add 

150





immediate 

profit, 

and





the 

reduction 

costs 

210.





The 

future 

exists, 

but





decrease 

anyway





wins 

by 

$10.





Tomorrow's 

payback 

is





real. 

She 

just





not 

enough 

yet





road.</details>

那么明天应该变得多重要呢？让我们回到通用的 delta 并使用同样的方法。如果老板永远维持价格，现值为 100 加上 delta 乘以同样的流。所以，V 等于 100 加上 delta 乘以 V。两边都减去 delta 乘以 V，剩下 V 乘以差值 1 减 delta，等于 100。所以，合作价值 100 除以差值 1 减 delta。

<details><summary>Original English</summary>So 

how 

much





should 

become 

more 

important





tomorrow? 

Let's 

go 

back.





to 

the 

total 

delta 

and





let's 

use 

that 

one





the 

same 

method. 

If





the 

owner 

keeps 

the 

price





forever, 

cost





is 

100 

now





plus 

delta,





multiplied 

by 

that





the 

same 

flow 

again.





So, 

V 

is 

equal 

to 

100





plus 

delta





multiply 

by 

V.





Subtract 

delta





multiply 

by 

V 

of 

both





parties. 

This 

leaves 

V,





multiplied 

by 

the 

difference





1 

minus 

delta, 

which





is 

equal 

to 

100. 

So,





cooperation 

is 

worth 

100,





divided 

by 

the 

difference 

1





minus 

delta.</details>

如果老板降价一次，他现在得到 150，之后从明天及以后每轮得到 60。这个未来的流价值 delta 乘以 60 除以差值 1 减 delta。请注意我们在比较什么。这些是包含对方老板反应的完整路径，而不仅仅是今天的 100 与 150。当 100 对 1 减 delta 的份额（商）至少为 150 加上 60 delta 除以 1 减 delta 时，合作至少同样有利可图。

<details><summary>Original English</summary>If





the 

owner 

lowers 

the 

price





once, 

he 

gets





150 

now, 

then 

60 

later





each 

round 

from





tomorrow 

and 

beyond. 

This





future 

flow





is 

it 

worth 

a 

delta





multiply 

by 

60,





divided 

by 

the 

difference 

1





minus 

delta.





Please 

note 

that 

we





compare. 

These 

are 

complete





ways 

that 

include





another's 

answer





owner, 

not 

just





100 

today 

versus 

150.





Collaboration 

is





at 

least 

the 

same





profitable 

when 

the 

share





100 

to 

1 

minus 

delta





is 

at 

least 

150





plus 

60 

delta 

by 

1





minus 

delta.</details>

两边都乘以差值 1 减 delta。因为它是正数，比较的方向不变。左边变成 100。右边变成 150 减去 150 delta 加上 60 delta。含 delta 的两项合并，因此右边是 150 减去 90 delta。我们需要让 100 至少等于这个量。两边加上 90 delta 并减去 100，你将看到 90 delta 必须至少为 50。除以 90，delta 必须至少为 5/9，约合 0.56。恰好在 5/9 时，老板无所谓维持还是降低价格。高于这一水平，未来的损失将压倒今天的诱惑。

<details><summary>Original English</summary>Multiply 

both





sides 

by 

difference 

1





minus 

delta.





Because 

she





positive, 

direction





comparison 

is 

not





is 

changing. 

Left





side 

becomes 

100. 

Right





side 

becomes 

150 

minus





150 

delta 

plus 

60





delta. 

Two 

members 

from





deltas 

unite,





therefore 

the 

right 

side





is 

150 

minus 

90





delta. 

We 

need,





so 

that 

100 

is 

at 

least





this 

amount. 

Add 

90





delta 

to 

both 

sides





and 

subtract 

100 

and 

you





you 

will 

see 

that 

90 

delta





must 

be 

at 

least 

50.





Divide 

by 

90. 

Delta





must 

be 

at 

least 

5/9,





what 

constitutes





approximately 

0.56. 

Exactly





at 

5/9 

owner





never 

mind, 

keep





or 

reduce 

the 

price.





Above 

this 

level





future 

losses





 prevail





today's 

temptation.</details>

现在让我们检验 delta 为 0.8 的情况。合作是 100 除以 0.2，等于 500。对于降价，我们将从 60 乘以 0.8 开始，即 48。除以 0.2，得出 240。加上 150 的即时利润，降价的价值是 390。合作胜出 110。我们还必须检验惩罚，这正是我们检验威胁的原因。当双方老板不得不降价时，他们中是否有人会愿意放弃追究并维持自己的价格？在对方降价的情况下，维持带来 30，而降价带来 60。降价仍然是最优反应，因此惩罚是完全可信的。

<details><summary>Original English</summary>Now 

let's 

check





delta 

at 

0.8.





Collaboration 

is 

100,





divided 

by 

0.2, 

which





is 

equal 

to 

500. 

For





we 

will 

start 

the 

decrease 

from 

60





multiply 

by 

0.8, 

which





is 

48. 

Divided





by 

0.2, 

this 

gives 

240.





Add 

150 

immediately





profit, 

and 

decrease





costs 

390. 

Collaboration





wins 

by 

110. 

We 

also





must 

check





punishment 

from 

that





the 

very 

reason 

why





we 

checked





threats. 

When 

both





the 

owners 

have





reduce 

the 

price, 

or





Will 

any 

of 

them 

want





forgive 

the 

loan 

and





maintain 

its 

price. 

IN





in 

case 

of 

reduction 

by 

others,





retention 

gives 

30, 

and





the 

decrease 

gives 

60.





There 

is 

still 

a 

decrease





the 

best 

answer,





therefore 

the 

punishment 

is





quite 

real.</details>

然而，对合作的支持并不意味着它必然发生。双方老板永远降价仍然是一个均衡。我们的计算表明合作可以得到维持，这并没有证明老板们一定会共同行动。如果每个人都知道博弈刚好只有三轮呢？在最后一轮，降价不会导致未来的损失，因此双方都会降价。在第二轮，第三轮的结果已经确定，因此双方再次降价。同样的逻辑也适用于第一轮。这种“逆向解构”取决于具体的假设：单轮博弈具有唯一均衡，最终日期是已知的，收益不包含额外的社会动机，双方老板都知道这一切，他们知道对方知道这一点，以此类推。改变这些假设，结论可能会改变。

<details><summary>Original English</summary>Support 

for 

cooperation,





however, 

does 

not 

mean 

that





it 

must 

happen





necessarily. 

That 

which





both 

owners





lowering 

prices 

forever,





is 

still 

an 

equilibrium.





Our 

calculation





shows 

that 

cooperation





can 

be 

supported.





This 

does 

not 

prove 

that





the 

owners 

will 

be





to 

act 

together. 

What 

about





as 

everyone 

knows 

what 

will 

happen





exactly 

three 

rounds? 

IN





last 

round





price 

reduction 

is 

not





will 

lead 

to





future 

losses, 

therefore





both 

are 

decreasing. 

IN





second 

round





result 

of 

the 

third





already 

defined, 

therefore





both 

again





are 

reduced. 

Same





The 

logic 

also 

applies 

to





first 

round. 

This 

is 

"





disentanglement"





depends 

on





specific 

assumptions





. 

Single-round 

game





has 

a 

unique 

equilibrium,





and 

the 

final 

date





known. 

Winnings 

are 

not





contain 

additional





social 

motives.





Both 

owners





they 

know 

all 

this, 

they 

know,





that 

the 

other 

knows 

this, 

and





and 

so 

on. 

Change 

these





assumptions, 

and





conclusion 

can





to 

change.</details>

这是你的第二个问题。假设老板们预期有很多轮，但他们的监督有时会记录一次并未发生过的降价。“残酷报复”会产生什么弱点？你不需要方程式。追踪虚假报告会导致什么。停在这里。一次虚假报告便注定了两位老板陷入永久惩罚。在我们的理想模型中，这个策略足够严厉，能够抑制蓄意降价。它也足够严厉，以至于会摧毁合作

<details><summary>Original English</summary>Here 

is 

yours.





second 

question.





Suppose 

the 

owners





many 

are 

expecting





rounds, 

but 

their





monitoring 

sometimes





records 

a 

price 

decrease,





which 

was 

not 

there. 

Which





weakness 

creates 

"





"cruel 

retribution"?





You 

don't 

need





equation. 

Follow,





what 

does 

it 

lead 

to





false 

report.





Stop 

here. 

One





false 

report





dooms 

both





owners 

on





permanent 

punishment.





This 

strategy





strict 

enough 

to





to 

restrain 

intentionally





price 

reduction 

in 

our





ideal 

model.





She 

is 

also 

quite





strict, 

so 

that





to 

destroy 

cooperation</details>

<!-- chunk 9/13 -->

……在误解之后。如果可能发生错误，那么在分析中就必须考虑错误的概率和代价。一种惩罚规则不会仅仅因为它更具戏剧性就变得更好。

<details><summary>Original English</summary>
after a misunderstanding. If errors are possible, their probability and price must be taken into account in the analysis. Rule punishment does not become better only than that it is more dramatic.
</details>

“以牙还牙”是一种著名的替代方案。你先选择合作，然后复制另一位玩家上一步的行动。它会惩罚背叛行为，并允许重归合作。但是当两位使用该策略的玩家犯错之后，就会作为回应而互相攻击。在每一个重复博弈中，这也并不总是均衡或最佳选择。

<details><summary>Original English</summary>
"An eye for an eye" is a well-known alternative. You you start with cooperation, and then copy the previous one another player's action. It punishes for decline prices and allows return to cooperation. But after two players made mistakes, which use her, can to exchange blows in response. This is also not always there equilibrium or the best choice in each repeating game.
</details>

声誉又增加了另一个层面。其他人可能会将你的行动视为关于你属于哪种玩家的信息。今天信守承诺可能会影响未来的合作伙伴是否愿意与你打交道。为了模拟这一点，我们必须确定谁看到了什么、信念如何变化，以及这会影响哪些未来的机会。声誉不能是一种神秘的额外收益，只在我们最初的答案不合心意时才添加进去。

<details><summary>Original English</summary>
Reputation adds another level. Others people can perceive the action as information about What kind of player are you? Keeping the promise today maybe influence whether will be future partners to have with you matter. That simulate this, we must determine, who sees what, how are changing beliefs and what future opportunities it affects. Reputation cannot be mysterious additional winnings, which we only add when the initial The answer is inconvenient.
</details>

### 不完全信息与贝叶斯博弈

一直以来，我们都假设每个人都知道其他人的收益。但这往往并非事实。现有企业可能成本很低，也可能成本很高，而新进入的玩家可能看到相同的价格，却不知道自己的对手究竟是谁。接下来，我们将让这些未知事实成为博弈的一部分。

<details><summary>Original English</summary>
All this time we assumed that everyone the owner knows the winnings others. This is often not the case. . An existing business can to have low or high costs, and a new player can see the same price, not knowing with whom he has an opponent matter. Next we let's do these unknowns facts are part of the game.
</details>

设想有一位新玩家在决定是否要在一家已有咖啡馆的对面也开一家咖啡馆。他看到了橱窗和价格，但看不到竞争对手的开销。在营企业可能拥有高效的厨房和廉价的食材，或者其开销可能非常高，以至于激烈的竞争会对其造成伤害。在同一外观之下，可能隐藏着截然不同的动机。这里给出了该新模型的数据：放弃进入，新玩家获得 0；如果他进入市场，面对高成本的竞争对手，对方会瓜分市场，参与者获得 40 美元；如果他进入市场，面对低成本的竞争对手，对方会发起竞争，参与者损失 20。这些数字已经考虑了竞争对手的反应，我们很快就会验证它们。

<details><summary>Original English</summary>
Imagine that the new the player decides whether to open a cafe opposite already existing. He sees showcase and prices, but not sees expenses competitor. Acting business can have efficient kitchen and cheap products, or his expenses may to be so high, that aggressive competition to him will hurt. By the same facade can hide very well different incentives. Here the figures provided for this new model. Refusal from participation brings the new player gets zero. If he goes out on market vs. competitor with high costs, that divides the market, and participant earns $40. If he comes out against a competitor with low costs, he enters struggle, and a participant loses 20. These numbers already taken into account the reaction of competitors, and we will check them in the near future.
</details>

竞争对手清楚自己的开销，而新参与者则不清楚。设 P 为成本偏高的概率，那么成本偏低的概率就等于 1 减 P。

<details><summary>Original English</summary>
The competitor knows his own expenses, and new member—no. Let P be the probability that the costs high. Then the probability that costs are low, is equal to 1 minus P.
</details>

请注意这里缺少了什么。当玩家无法观察到另一位玩家的行动时，如未公开价格的情形，这属于不完全信息（imperfect information）。当玩家对博弈本身的信息有所不知时，例如对手的开销，这属于不完全信息（incomplete information）。

<details><summary>Original English</summary>
Pay attention to what there is not enough here. When the player cannot to watch by the actions of another player, as in the case of closed price, this incomplete information. When the player doesn't know something about the game itself, for example, about opponent's expenses, this incomplete information.
</details>

我们的参与者面对的是另一种类型。我们把私下知悉的特征描述为类型。竞争对手有高开销类型，也有低成本类型。正因为他清楚自己属于哪一种，他的策略就可以决定每种类型该怎么做。

<details><summary>Original English</summary>
Our participant encounters another type. We describe privately known description as type. There is a competitor type with high expenses or type of low costs. AND because he knows, which one, his strategy can to determine that will do every type.
</details>

进入市场的期望收益是 40 乘以 P，再加上或者减去 20 乘以整个数值 (1 - P)。将这第二部分展开：-20 乘以 1 等于 -20，而 -20 乘以 -P 等于 +20P。因此，我们得到 40P - 20 + 20P，即 60P - 20。当这个值大于零时，进入比放弃更好。两边各加 20，使得 60P 大于 20；然后除以 60。当 P 大于 1/3 时，进入更好。刚好在 1/3 时，参与者在期望收益上是无差异的。

<details><summary>Original English</summary>
Expected winnings from the input is 40*P plus or minus 20*for the whole value 1-P. Multiply this second part. -20*1 is equal to -20. A -20*-P is equal to + 20P. So, we we have 40P-20 + 20P, which is 60P-20. Exit better than rejection, when this value is higher zero. Add 20 to both sides to 60P exceeded 20. Then divide by 60. Login better when P is greater 1/3. Exactly at 1/3 participant indifferent regarding the expected profit.
</details>

提出一个问题：参与者认为高开销的概率为 40%，低开销的概率为 60%。那么进入的期望收益是多少？这与放弃进入相比如何？以及在你的建议背后，对风险做出了怎样的假设？

<details><summary>Original English</summary>
Your question. Member believes that there is 40% probability of high expenses and 60% probability of low expenses. Which expected income from entrance? How is this? compared to denied entry? AND what is the assumption about The risk lies in based on your recommendations?
</details>

暂停一下。40 的 40% 是 16；-20 的 60% 等于 -12；16 减 12 等于 4。因此，进入的期望收益是 4 美元，而放弃则是 0。只关心金钱均值的参与者会选择进入市场。而那些尤其害怕损失 20 美元的人，可能会有其他效用值，那样我们就需要去比较期望效用。

<details><summary>Original English</summary>
Take a break. 40%of 40 is 16. 60% of -20 is equal to -12. 16-12 is equal to four. So, the input has expected profit 4 $ vs. zero for refusal. Member, who only cares about average money, enters the market. That, Who is especially afraid? lose $20, maybe to have other meanings utility, and then we compare the expected utility.
</details>

### 贝叶斯更新与信号传递

在下一个例子中，我们来改变初始信念。参与者在看到任何证据之前的先前信念，现在设为 30% 为高开销。设想有 100 家可比的竞争对手，其中 30 家成本高，70 家成本低。某项供应商合同特征出现在 80% 的高成本公司中，以及 20% 的低成本公司中。假设这个群体描述了我们的竞争对手，而参与者刚好观察到了这一特征。

<details><summary>Original English</summary>
For next example we will change the initial belief. Previous participant's beliefs , before he saw any evidence, now is 30%high expenses. Imagine 100 comparable competitors. 30 have high costs, and 70— low. Certain feature contract supplier appears in 80% of companies with high costs and 20% with low. Let's assume that this the group describes our competitor, and participant just watching by this feature.
</details>

30 家的 80%——即 24 家高成本公司具备这一特征；70 家的 20%——即 14 家低成本公司具备这一特征。这总共有 38 家公司具备该特征，其中 24 家属于高成本。因此，如果我们的在营对手具备这一特征，更新后高成本的概率就是 38 分之 24。这可以简化为 19 分之 12，约为 63%。这就是频数形式的贝叶斯法则。

<details><summary>Original English</summary>
80% of 30—that's 24 companies with high costs, who have this feature. 20%from 70— these are 14 firms with low expenses that have its. This makes 38. firms with this characteristic, and 24 of them have high costs. So, if our active member has this feature, updated probability high costs is 24 out of 38. This simplifies to 12 to 19, or about 63%. It Bayes' rule in frequency form.
</details>

请注意问题的方向性。80% 是指在给定高成本的条件下看到该特征的概率；而我们需要的是在给定存在特征的条件下属于高开销的概率。把这两者混淆是一个常见的错误，会导致无法得出正确答案。

<details><summary>Original English</summary>
Pay attention to directionality question. 80%—it was probability of seeing sign provided high costs. To us was needed probability of high expenses provided presence of a sign. To confuse these things— a common mistake that does not give the correct answers.
</details>

这一信号是否改变了决策？观察之前：60 乘以 0.3 是 18，而 18 减 20 等于 -2。因此，新参与者会选择观望。观察之后：60 乘以 12/19 等于 720/19；20 等于 380/19；相减得到 340/19，约为 17.89 美元。这一信号将决策从不进入转变成了进入市场。

<details><summary>Original English</summary>
Does it change? Is this a signal of a solution? Before observation: 60*0.3 is 18, and 18-20 is equal to -2. Therefore, new member stays away . After it: 60*12/19 is equal to 720/19. 20 is equal to 380/19. Subtraction gives 340/19, about $17.89. Signal transforms retention from entrance to entrance to market.
</details>

现在尝试反向观察，同样从 30% 这一先验概率开始。当前的在营企业没有该特征。有多少高成本和低成本公司不具备该特征？更新后的概率是多少？参与者是否会进入市场？请计算公司的数量，而不是凭直觉调整百分比。暂停一下。

<details><summary>Original English</summary>
Now try the opposite observation, starting from that one the most a priori probability of 30%. The current member does not have of this sign. How many firms with high and low costs Don't they have it? What updated probability and would you enter market participant? Count the companies, not the change percentages intuitively. Do it. pause.
</details>

30 减 24 剩下 6 家高开销公司；70 减 14 剩下 56 家低成本公司。总共有 62 家公司没有该特征，因此高成本的概率为 62 分之 6，大约为 10%。现在将这 62 家公司中的每一家都视为等可能的对手：其中 6 家每家给参与者带来 40，总计 240；其中 56 家每家带来负 20，总计负 1120；合在一起是负 880。除以 62，我们得到大约负 14.19 美元。参与者选择留在局外。

<details><summary>Original English</summary>
30-24 leaves six firms with high expenses. 70 minus 14 leaves 56 firms with low costs. These are 62 companies without a sign, therefore the probability high costs is 6 out of 62, approximately 10%. Now consider each of these 62 firms as equally likely opponent. Six of 40 of them are given to the participant, which in total is 240 . 56 of them give a minus 20, which in total is minus 1120. Together this is minus 880. Dividing by 62, we get approximately minus $14.19. The participant remains aside.
</details>

特征的不存在同样也是证据。我们同样需要检验在营参与者的决策，而不是将其视作某种既定天气。进入发生后，高成本的在营参与者若瓜分市场可获利 40，若对抗则为 -10，因此他会选择瓜分市场；低成本的在营参与者若瓜分市场可获利 40，若对抗则为 50，因此他会选择对抗。这些选择带给新参与者的收益分别为 40 和 -20。

<details><summary>Original English</summary>
Absence of sign was also testimony. Us too need to check active participant, instead of to perceive it as weather. After login active participant with high costs earns 40 by dividing market, and -10, fighting, so he divides the market . Active participant with low costs earns 40 by dividing market, and 50, fighting, that's why he fights. These elections bring participant 40 and -20.
</details>

现在让我们回到最初 40% 的先验概率。根据这一信念，新参与者进入市场。高成本类型瓜分市场，低成本类型展开对抗。鉴于其信念，进入是新参与者的最佳期望应对；而每种类型也都做出了各自的最佳选择。这就是贝叶斯纳什均衡。每位玩家以及玩家的每种类型，都在结合自身信息和对其他人的信念的情况下，最大化期望收益。在更长的博弈中，信念会在先前的步骤之后发生改变，所以我们还需要检验每一种可能历史之后的行为。

<details><summary>Original English</summary>
Now let's go back to initial a priori probability of 40%. According to this conviction, the participant enters market. High type divides the expenses market, and the type of low—fights. Exit is the best expected reaction participant in view of his beliefs. AND each type does their own thing own best choice. This is Bayesian Nash equilibrium. Everyone player and each type the player maximizes expected gain, considering your information and beliefs about others. In longer games belief change after previous steps, so we also need to check behavior after every possible history.
</details>

我们的特征此前是被动的。现在假设卖家声称自己的产品非常好，而不道德的卖家也可以说出一模一样的话。怎样才能让这种声明具有信息量？接下来我们将把空洞承诺与担保进行比较。然后再检验两类卖家提供担保的原因是否确实有所不同。

<details><summary>Original English</summary>
Our sign was passive. Now let's assume that the seller says that his product is great. Unscrupulous the seller can to say exactly the same thing . What could be done? this statement informative? Further we will compare an empty promise from guarantee. Then let's check if it's true in two types There are different sellers reasons for providing it.
</details>

咖啡店需要一台新咖啡机。两位卖家都把他们的机器描述为性能可靠。这很有用，直到我们记起不诚实的卖家同样可以说出这个词。如果两类卖家都能从买家的信任中获益，并且都能免费发表同样的言论，那么该言论本身给买家提供的信息就微乎其微。这样的讯息被称为廉价磋商（cheap talk），因为发送它不会因开销或责任而对任何人的收益产生改变。廉价磋商并不总是无用的。当两个人只是想找一个碰头的地点时，免费的讯息就能完美发挥作用。这里的问题出在另一处。卖家……

<details><summary>Original English</summary>
Coffee shop needed new coffee machine. Two sellers are described their cars as reliable. This is useful, until we remember, that is dishonest the seller can also learn this word. If both types sellers will win from the trust of buyers and can do the same statement free of charge, by myself the statement gives the buyer little information. Such message called cheap chatter, because it sending to no one does not change the benefit because of expenses or obligation. Cheap chatter is not always useless. When two people just want find one place meetings, free the message works perfectly. The problem here is in another. Seller
</details>

<!-- chunk 10/13 -->

### 信号发送与质保机制

劣质产品的卖家也想听起来和优质卖家一样好。

<details><summary>Original English</summary>
low-quality the product wants to sound as well as seller of quality.
</details>

那么，我们来看看质保。卖家承诺如果车坏了就出钱维修。优质车辆发生故障的频率更低，因此完全相同的承诺对于两类卖家的成本是不同的。

<details><summary>Original English</summary>
So, let's consider warranty. Seller promises to pay repair if the car will break. Quality cars break down less often, so one and the same the promise itself is worth it two types of sellers differently.
</details>

这里给出一组数字。如果买家相信这是优质卖家，他们就会付更多的钱，卖家的利润空间每辆车增加30美元。卖家得到了这30美元。此外卖家还要支付质保维修费用。平均而言，优质机器的这项维修成本是10美元，劣质机器则是50美元。

<details><summary>Original English</summary>
Here given numbers. If buyers believe that quality seller, they pay more, and seller's margin increases by 30 dollars for the car. Seller gets these 30. Also the seller pays warranty repair. IN average this the repair costs 10 dollars for quality machines and 50 for low-quality.
</details>

买家看到质保，知晓这些数字，并将其视为高质量的标志。提供质保为优质卖家带来了30单位的收益，预期维修成本为10。30减去10等于20的利润。因此该卖家提供质保。

<details><summary>Original English</summary>
The buyer sees guarantee, knows these numbers and perceives it as a sign of high quality. Granting guarantees brings to a quality seller 30 units of benefit at 10 expected repair costs. 30 minus 10 is equal to profit of 20. So this the seller provides warranty.
</details>

如果不诚实的卖家模仿这一点，他同样能获得这30，但要支付50。30减去50等于20的亏损。因此该卖家保持沉默。在这些假设下，只有优质卖家提供质保，因此买家的假设被证实是正确的。这就是分离信号。

<details><summary>Original English</summary>
If dishonest the seller imitates this, he gets the same 30, but pays 50. 30 minus 50 equals a loss of 20. So this seller is silent. During these assumptions only quality seller provides a guarantee, therefore buyers' assumptions are found correct. It separation signal.
</details>

不同类型选择不同且可观察的行动，得益于此，接收方将了解到新信息。我们从两个方向进行了检验：优质类型必须偏好发信号而非保持沉默；劣质类型必须偏好保持沉默而非模仿。仅仅表明优质卖家能负担得起质保是不够的。

<details><summary>Original English</summary>
Different types choose various observables actions, thanks to which the recipient will know something new. We checked both directions. Qualitative type must give signal advantage, and not silence. Low-quality type must give preference for silence, and not imitations. Show only that which is of good quality the seller can to afford guarantee, not enough.
</details>

请回答这个问题：将劣质卖家的预期维修成本从50美元改为20美元，其余所有条件保持不变。质保还能继续区分这两种类型吗？计算劣质类型通过模仿获得的收益。

<details><summary>Original English</summary>
Your question. Change expected cost repair low-quality seller from 50 to 20 dollars, leaving everything else unchanged. Will it continue? guarantee to share these two types? Calculate the benefit low-quality type from imitation.
</details>

在这里停一下。现在这家伙能得到30并花费20，从而产生10美元的利润。在30美元的溢价保持不变的情况下，10美元好过一无所获，因此低质类型会想要模仿。两种类型都会想要提供质保，这就破坏了原本设定的分离状态。

<details><summary>Original English</summary>
Stop here. Now this guy gets 30 and spends 20, which gives 10 dollars of profit. By constant allowance in $30, $10 is better than nothing, because the low type will want copy. Both types will want offer warranty that violates proposed separation.
</details>

所有人都会得到同样具有价值的保修服务，但是明白新成本的买家，就不能继续把每份质保都当作品质的确认。如果他真这么做了，那他就会为往往并不可靠的车辆多付30美元。信念、价格溢价与卖家的选择必须保持一致，而这里并不吻合。

<details><summary>Original English</summary>
Cafe everything will get the same warranty service that has value, but the buyer who understands new costs, can't continue to count each guarantee confirmation quality. If he did that did, then would overpay 30 dollars for cars, which are often unreliable. Conviction, price allowance and choice the seller has to agree, and here this is not there.
</details>

### 信息甄别机制

在那个例子中，是有信息优势的卖家做出了行动。信息较少的一方能否通过提供选择来制造差异呢？这种方法被称为信息甄别。

<details><summary>Original English</summary>
In that example informed the seller chose an action. Could it be less? informed party to create the difference, offering a choice ? This approach is called screening.
</details>

设想一家外送服务公司，它并不知道客户会下多少单。如果要求客户自我描述，会诱使对方给出乐观的回答。

<details><summary>Original English</summary>
Imagine delivery service, which doesn't know how much orders will be made client. Request to describe customers will encourage himself to optimistic answers.
</details>

取而代之的是，该服务提供了包含两种资费的菜单。在相同周期内，轻度用户预期有两次送递，而重度活跃用户预期有10次。基础资费没有订阅费，送递费用为8美元。“会员”资费则需要先支付20美元预付款，之后每次送递为4美元。服务内容完全相同。每位客户清楚自己的使用量，并会选择总额更便宜的方案。客户之间的唯一区别在于所需的送递次数。

<details><summary>Original English</summary>
Instead, the service offers a menu of two tariffs. For the same period light user is waiting two deliveries, and active—10. Base tariff does not have subscription fees, and the cost delivery is 8 dollars. Tariff « "membership" implies down payment 20 dollars, and then 4 dollars for each delivery. Service identical. Everyone the client knows their own usage volumes and chooses the cheaper one total amount. Clients only differ the number of necessary deliveries.
</details>

对于轻度用户，基础资费的费用是2乘以8，即16美元。会员资费是20加上2乘以4，即20加8等于28。轻度用户选择基础资费。对于活跃用户，基础资费是10乘以8等于80。会员资费是20加上10乘以4，即20加40等于60。活跃用户选择会员资费。他们的选择揭示了订单量，而无需去相信问卷调查。

<details><summary>Original English</summary>
For the light basic user the fare costs two multiply by eight, that is 16 dollars. Membership costs 20 plus two multiplied by four, that is 20 plus eight or 28. Easy the user chooses basic rate. For active basic user The fare is 10 multiply by eight or 80. Membership costs 20 plus 10 multiply by four, that is, 20 plus 40 or 60. Active user elects membership. Their choice reveals the volumes orders without need to trust survey.
</details>

请回答这个问题：将20美元的会员费降低4美元。现在每位客户会选择哪种资费？选择会员资费是否仍能识别活跃用户？请计算会员资费下的两组总金额。算算看。

<details><summary>Original English</summary>
Your question. Reduce membership fee from $20 for four . What is the tariff now? will each customer choose? Does the choice allow membership still identify active user? Count both total amounts for membership. Do it.
</details>

在这里停一下。轻度用户的基准资费仍为16，活跃用户仍为80。轻度用户的会员费用变为4加上8即12，低于16。活跃用户的会员费用变为4加上40即44，低于80。两者都会选择会员资费。更便宜的费用可以吸引客户，但该菜单已不再能区分他们。所以，单纯的会员身份本身并不能说明使用情况。

<details><summary>Original English</summary>
Pause here. Base the tariff remains 16 for the lung user and 80 for active. Membership for the lung the user becomes four plus eight or 12, which is below 16. Membership for active the user becomes four plus 40 or 44, which is below 80. Both elect membership. Cheaper board can attract customers, but the menu doesn't have them anymore divides. So, exactly membership in itself says nothing about use.
</details>

### 逆向选择与道德风险

销售前隐藏的质量也会危害整个市场。经济学家称之为逆向选择。假设二手车买家无法分辨车辆可靠还是不可靠，因此根据平均质量出价。可靠车辆的拥有者清楚自己的车价值更高，于是部分人拒绝出售。他们的退出降低了仍在销售的车辆的平均质量。明白这一点的买家会再次压低价格，而这又可能排挤下一批最可靠的卖家。这是一种可能的机制，并不是说每个二手市场中的商品都会彻底消失。检验、质保和声誉可以改变买家所掌握的信息，以及优秀卖家获得回报的方式。现实市场在建模时需要考虑这些特征。

<details><summary>Original English</summary>
Hidden quality before sale also can harm the entire market. Economists call this is unfavorable selection. Suppose, used car buyers technicians cannot distinguish reliable cars from unreliable, therefore offer a price, based on average quality. Owners of reliable machines know that their the goods cost more, so some refuse sell. Their output lowers the average quality of the machines that remain in sales. Buyers who they understand this, again are lowering the price, and this can replace the following the most reliable sellers. It possible mechanism, and not a statement that every second-hand market goods disappear. Inspections, guarantees and reputation can to change what they know buyers, and how are rewarded good sellers. Real market needs to be taken into account these features in models.
</details>

要区分隐藏质量与隐藏努力。如果车在售出前就已经是坏的，这就是隐藏类型。现在让我们假设设备已经付款，而他决定对车进行多么仔细的维护。这属于隐藏行动，通常被称为道德风险，我们稍后会为此设计激励合同。

<details><summary>Original English</summary>
Distinguish hidden quality and hidden efforts. If the car is already bad for sales, this hidden type. Now let's assume that equipment already paid, and he decides how much carefully to service the car . This is a hidden action, which is often called moral hazard, and we will develop incentive contract for this later.
</details>

### 合作剩余与外部选项

假设咖啡馆最终找到了可以信任的供应商。但仍有一个问题：机器对于咖啡馆的价值，可能远高于卖家转让它的成本。这笔交易可以使双方都变得更好，但并未决定他们将如何分享这笔盈余。那么，究竟是谁拿到了呢？我们用数字来明确这一点。

<details><summary>Original English</summary>
Let's assume that the cafe is all finds supplier to whom can trust. One the problem remains . The machine can be much more valuable for a cafe, how much does it cost give it to the seller. The deal can make both sides better, not determining how they will share this winnings. So, who is it? receives? Let's Let's define this in numbers.
</details>

假设一家咖啡馆与这家供应商通过合作能够创造100美元的总收益。知晓交易创造了价值，并未告诉我们这份价值将如何分配。为此，我们需要了解一旦谈判破裂，各方能做什么。

<details><summary>Original English</summary>
Let's say a cafe and this supplier can create 100 dollars total benefits by cooperating. Knowing that the deal creates value, not tells us how this the value will be distributed. For we need this to know that each the party can do, if negotiations will fail.
</details>

假设咖啡馆能从其次优替代方案中获得20美元，而供应商能获得30美元。这就是在出现分歧时他们的报酬，通常称为外部选项。所有数值均以同一种货币单位表示，且是在考虑了相关成本后的净值。100是通过达成协议可获得的总金额，并非在外部选项之上的额外100。

<details><summary>Original English</summary>
Let's say a cafe can get 20 dollars from your next the best alternatives, and supplier—30. It their payments at differences that usually called external options. All values are specified in one currency units and are pure after taking into account relevant costs. 100 is the total amount, available from their agreements, not additional 100 over external options.
</details>

我们将咖啡馆在协议中所占的份额记为 X。那么供应商获得 100 减去 X。咖啡馆不会同意少于20，因为它可以从其他地方得到20。供应商不会同意少于30，这意味着咖啡馆不可能拿到超过70。因此，咖啡馆可接受的范围是20到70，剩下的归供应商。

<details><summary>Original English</summary>
Let's call the cafe's share in agreement X. Then the supplier receives 100 minus X. The cafe is not will agree to less than 20, because it can get 20 in another place. Provider will not agree to less than 30, which means that the cafe is not can get more 70. Therefore, acceptable range for cafes is from 20 to 70, and the rest goes to the supplier.
</details>

达成协议额外创造了多少价值？不达成交易，外部选项合计提供50。达成交易，总金额为100。100减去20再减去30剩下50。因此，交易带来的增益是50。

<details><summary>Original English</summary>
How much extra creates value agreement? No deal external options in total give 50. With a deal total amount is 100. 100 minus 20 minus 30 leaves 50. So, the gain from The transaction is 50.
</details>

如果各方分得这笔额外收益的一半，咖啡馆将在其获益下得到20加25即45，供应商得到30加25即55。这种对收益的均分是一种可能的解，但它建立在关于各方如何讨价还价的额外假设之上。了解外部选项为我们提供了可接受协议的区间。但它依然没有给我们提供一个过程，来解释为什么会选择45和55，而不是该区间内的任何其他点。

<details><summary>Original English</summary>
The distribution under which each side gets half this additional I would give the cafe 20 if I won. plus 25, that is 45, and supplier 30 plus 25, that is, 55. Such equal division of winnings is one of the possible decisions, but he based on additional assumptions about as parties are bargaining. Knowledge external options gives us range acceptable agreements. It still doesn't give us the process, who chooses 45 and 55, not any other point in this range.
</details>

请回答这个问题：将咖啡馆的外部选项提高到40，同时供应商的仍维持在30水平，且交易依然创造100的总金额。现在咖啡馆可接受的区间是多少？从协议中获得的收益有多大？平均分配这些收益又会得到什么？请把总金额与额外利润分开核算。

<details><summary>Original English</summary>
Your question: increase external option cafes up to 40, while in supplier he remains at the level 30, and the deal is still on creates a general the sum of 100. What is it now? acceptable range for a cafe? As far as great benefits from agreement? And what will it give? equal distribution of these benefits? Hold total amount separately from additional profits.
</details>

在这里停一下。咖啡馆现在至少需要40，而供应商仍需要30。因此，咖啡馆的区间是从40到70。外部选项之和为70，100减去70剩下30作为交易带来的收益。平均分配时每方各得15。咖啡馆获得40加15即55，供应商获得30加15即45。更强有力的替代选项不仅改变了可接受的区间，也改变了这一具体的分配结果。让我们……

<details><summary>Original English</summary>
Stop here. Cafe now you need at least 40, and the supplier still need 30. So, cafe range—from 40 up to 70. The sum of external options is 70, and 100 minus 70 leaves 30 benefits from the deal. At equal distribution is 15 each. Cafe gets 40 plus 15, that is, 55, and supplier 30 plus 15 , that is 45. More strong alternative changed as acceptable range, and this particular one too distribution. Let's let's make
</details>

<!-- chunk 11/13 -->

### 议价博弈中的时间折损与逆向归纳

在新模型中规则很明确。为了将时间因素隔离开来，本博弈将未达成协议时的双方收益均设定为零。因此，先前的 20 和 30 不再有效。

<details><summary>Original English</summary>
rules clear in the new models. To isolate time, this game installs both payments in case of disagreement to zero. Therefore, previous 20 and 30 are no longer valid.
</details>

第一发起人提出 100 美元的分配方案，另一方选择接受或拒绝。若拒绝，则只剩下 80 美元，且角色互换。原受要约方提出最终提议。如果拒绝，双方都得零。提议以整美元为单位，当博弈者无差异时即表示同意。

<details><summary>Original English</summary>
First initiator offers a distribution of 100 dollars, and the other the party accepts or rejects. After deviation only 80 left dollars and roles are changing places. Primary defendant makes the final proposal. If it reject, both get zero. Proposals are being made in whole dollars, and the players agree, when they don't care.
</details>

从终点开始倒推。在第二轮中，受要约方将提议与拒绝所得的零收益进行比较。零提议等于拒绝收益，而我们的平局规则规定接受。因此，第二发起人给自己留下 80 并出价为零。

<details><summary>Original English</summary>
Start at the end. IN second round the defendant compares offer with zero from deviation. Zero proposal is equal to the deviation, and our rule is a draw says accept. Therefore, second initiator leaves himself 80 and offers zero.
</details>

现在我们回到第一轮。原受要约方知道拒绝会导致随后保底获得 80。这 80 就是等待的价值。因此，第一发起人必须出价至少 80。

<details><summary>Original English</summary>
Now let's go back to first round. Primary defendant knows that refusal leads to save 80 later. These 80 are what what is it worth expectation. Therefore, the first initiator has offer at least 80.
</details>

出价 80 会给发起人留下 20，而任何更低的提议都会被拒绝，导致发起人在第二轮中得到零。20 大于零，因此该交易给第一发起人 20，给受要约方 80。当另一个人可以最后行动时，先走的一方优势就不那么明显了。这一结果取决于最终提议规则、金额递减以及平局规则。

<details><summary>Original English</summary>
Proposition 80 leaves 20 to the initiator, while any smaller offer deviates and leaves the initiator with zero in the second round. 20 is better than zero, so the deal gives 20 to the first initiator and 80 to the defendant. First walk less impressively, when another person can to walk last. This the result depends from the rule final offer , reducing the amount and the rules are a draw.
</details>

这里是你的第二个问题。仍保持无差异即同意的设定，但假设延迟使第二轮只剩下 60 美元而不是 80 美元。第一发起人必须出价多少，又能给自己留下多少？再次按倒推顺序分析。

<details><summary>Original English</summary>
Here your second question. Leave your consent at indifference, but suppose that delay leaves only 60 dollars in second round instead of 80. What has to offer first initiator and how many he can leave itself? Work again in reverse order.
</details>

停在这里。在最后一轮中，新发起人给自己留下 60 并出价零，该提议被接受。因此，第一受要约方可以通过等待确保得到 60，而当下的 60 提议是可以接受的。100 减去 60 给第一发起人留下 40。更长的延迟削弱了回应方，因为等待的价值仅限于博弈者能从较小的第二项资金中获取的份额。

<details><summary>Original English</summary>
Stop here. IN final round new initiator leaves himself 60 and offers zero, which accepted. Therefore, first defendant can provide 60, waiting, and immediate proposition 60 is acceptable. 100 minus 60 leaves 40 for the first initiator. More long delay weakens the one who answers, because worth the wait only that the player can get from smaller second fund.
</details>

最后，区分转移与损失。从咖啡馆向供应商转移 10 美元改变了分配，但一百的总额保持不变。通过延迟将一百降至八十则破坏了无人获得的 20 美元。因此，对分配的争夺可能会造成双方都更愿意避免的损失。

<details><summary>Original English</summary>
Eventually, distinguish transfers and losses. Transfer $10 from the cafe supplier changes distribution, but total amount one hundred remains. Reducing hundreds to eighty through delay destroys 20 dollars that no one receives. So the struggle for distribution can create losses that both sides would prefer to avoid.
</details>

### 一级价格与二级价格密封拍卖

现在我们可以说明是什么促成了协议、各方可以带走什么以及时间如何影响分配。但假设有多个买家想要同一辆车。仅仅改变支付规则，能否让同一个出价在一种拍卖中合适而在另一种拍卖中不利？

<details><summary>Original English</summary>
Now we can to say what creates agreement, with which each the party can leave and how time affects divide. But let's assume that several buyers they want the same car . Can change only payment rules place a bet equal value appropriate on one auction and disadvantageous on another?
</details>

在咖啡馆老板出价之前，她应该知道获胜需要支付多少。情况是这样的：咖啡馆想要一辆二手车，卖方正在对其进行拍卖。在不同的拍卖形式中都是最高出价获胜，但支付规则不同，且该规则会改变出价策略。

<details><summary>Original English</summary>
Before the cafe owner will make a bet, she should know how much will have to pay for the victory. Here it is. situation. The cafe wants a used car, and the seller is exhibiting her up for auction. IN different formats auctions wins the highest rate, but payment rule is different, and this the rule changes betting strategy.
</details>

我们先从私有价值开始。这辆车对这家咖啡馆来说价值 80 美元，因为它可以带来相应的效益。而且当另一个参与者对汽车的估值不同时，这个价值并不会改变。

<details><summary>Original English</summary>
Let's start with the private values. Machine worth 80 dollars for this cafe because the benefit it provides can bring. And this one value is not changes when another participant evaluates car differently.
</details>

我们假设：单一商品、密封出价、无佣金、无预算约束或转售计划。如果咖啡馆获胜，其剩余等于汽车的价值减去其所支付的金额。在一级价格拍卖中，出价最高的人获胜，并按自己的出价支付。如果咖啡馆出价 80 并获胜，其剩余等于 80 减 80，即为零。出价 60 在获胜时将带来 20 美元的剩余，但较低的出价更容易输给他人。因此，老板在获胜几率与获胜收益之间进行权衡。单凭 80 美元的自身价值无法确定一级价格拍卖中的最佳出价，我们还需要关于对手可能如何出价的假设。低于价值的出价（通常称为“压价”）可以保护剩余。然而，例如总是出价低 10% 的规则，根据目前的信息并没有普遍的合理性。

<details><summary>Original English</summary>
Let's assume: one goods, closed bets , no commissions , budget constraints or plans resale. If the cafe wins, its surplus—this cost of the car minus what it is pays. At auction first price The winner is the one who proposed the most, and pays your bet. If the cafe puts 80 and wins, its surplus is equal to 80 minus 80, that is, zero. Rate 60 I would give 20 dollars. surplus in case victory, but inferior bet more often loses to others. Therefore, the owner balances between the chance of victory and size profit in case winnings. Only myself cost 80 dollars does not allow determine the best bid at auction first price. To us also needed assumptions about as, probably, will put rivals. Rate below the value that often called " understatement", defends excess. However rule, for example, always bet 10% less, does not have general justification for based on this information.
</details>

在密封出价的二级价格拍卖中，赢家支付对手最高出价的金额。你的出价决定你是否获胜，而对手的出价决定你在获胜时支付多少。根据我们关于私有价值的假设，按你的真实价值 80 出价是一个弱优势策略。这意味着它绝不会比任何其他出价更差，并且有时更好。

<details><summary>Original English</summary>
On second price auction with closed betting winner pays the amount highest bid opponent. Your the bet decides whether you you win, and the bet decides the opponent, How much do you pay in in case of victory. By our assumptions about private value, bet on your the real value of 80 is weakly dominant strategy. It means that she never worse than any other bet, and sometimes better.
</details>

让我们通过固定对手的最高出价并比较各种选项来验证这一点。

<details><summary>Original English</summary>
Let's check this, recording the highest opponent's bet and comparing options.
</details>

假设对手的最高出价是 60，低于咖啡馆的价值。出价 80 获胜并花费 60，留下 20 的剩余。出价 100 同样获胜且花费 60，因此没有任何额外收益。出价 50 告负并损失了这 20。当压价阻止你以低于自身价值的价格获胜时，就会造成损害。

<details><summary>Original English</summary>
Let's assume the highest opponent's bet—60, which is below the cost for cafe. Bet 80 wins and costs 60, leaving 20 surplus. Bet 100 everyone wins too one costs 60, so adds nothing. Bet 50 loses and loses these 20. Underpricing It hurts when it interferes. win on price below your cost.
</details>

现在假设竞争对手的最高出价是 90，高于咖啡馆的价值。出价 80 告负，这是个好消息。咖啡馆不需要支付任何费用，其剩余为零。出价 100 会获胜，但咖啡馆将为价值 80 的东西支付 90，因此剩余将是 80 减 90，即负 10。当抬价迫使你以高于自身价值的价格购买时，就会造成损害。

<details><summary>Original English</summary>
Now let's assume that highest bid competitor—90, higher costs for the cafe. Bet 80 loses, what is good news. Cafe doesn't pay anything, but its excess is equal to zero. Rate 100 would win, but the cafe would pay 90 for that which is worth 80, so the surplus would be 80 minus 90, that is, minus 10 . Overpricing It hurts when it forces buy at price above your value.
</details>

如果竞争对手的出价正好是 80，获胜意味着为价值 80 的东西支付 80，而失败则什么都没有。在任何一种情况下，剩余都等于零。低于、高于或等于，这些情形涵盖了所有的可能性，而在任何一种情况下，其他出价都不会优于出价 80。这是关于激励的结果。这并不保证咖啡馆一定会获胜或一定会获得任何剩余。

<details><summary>Original English</summary>
And if the rate competitor exactly 80, winning means payment of 80 for that is worth 80, while Lose—nothing. IN in any case the surplus is equal to zero. Below, above or equals. These cases cover all opportunities, and in none of them are different the bet doesn't win rate 80. This result regarding incentives. This is not promise that the cafe wins or not at all will receive any excess.
</details>

轮到你了。咖啡馆对汽车的估价为 80，并在二级价格拍卖中出价 80。竞争对手的最高出价可能是 50、75 或 90。在每种情况下咖啡馆是否会获胜？它支付多少？又获得什么剩余？然后解释在第一价格拍卖中同样的 80 出价表现如何。

<details><summary>Original English</summary>
Your turn. The cafe rates the car at 80 and bets 80 on second-price auction. Highest rate competitor may be 50, 75 or 90. Will it win? cafe in each of cases? How many Does it pay? And what surplus receives? Then explain how behaves the same bid 80 at auction first price.
</details>

停在这里。面对 50，咖啡馆将获胜，支付 50 并获得 80 减 50，即 30。面对 75，它获胜，支付 75 并获得五。面对 90，它失败，什么都不付，获得零。在一级价格拍卖中，出价 80 获胜意味着支付 80，因此无论竞争对手的出价有多低，剩余都等于零。出价本身没有改变，是支付规则改变了出价的后果。

<details><summary>Original English</summary>
Stop here. Against 50 cafes will win, pays 50 and receives 80 minus 50, that is 30. Against 75 it wins, pays 75 and receives five. Against 90 it is loses, nothing pays and receives zero. At auction first price winning rate 80 means payment 80, therefore the surplus is equal to zero, no matter how low there was no bet competitor. Itself the rate has not changed. Payment rule changed the consequences rates.
</details>

### 共同价值与赢家诅咒

这一结果还取决于咖啡馆清楚自己的价值。因此，我们来改变出售的对象。想象一下，竞拍者想买一批咖啡以按市场价格转售。每个人的转售价值大致相同，但目前没有人知道具体是多少，每个人都只有大致的估计。这被称为共同价值环境。

<details><summary>Original English</summary>
This result also depended on what the cafe knew own value. Therefore , let's change that for sale. Imagine, that the bidders want to buy a party coffee to resell its at market price. Resale value approximately the same for everyone, but no one doesn't know yet, and everyone has only an approximate assessment. It is called environment total cost.
</details>

假设一批货物结果价值为 100，三个参与者的估价分别为 80、100 和 120。如果更高的估价导致更高的出价，那么最可能的赢家是拥有 120 的人——最乐观的评估。赢家并没有获得高人一等知识的证明，他们可能只是房间里最乐观的人。

<details><summary>Original English</summary>
Suppose a party turned out to be worth 100 , and three participants had grades 80, 100 and 120. If higher grades lead to higher rates, most likely the winner has 120— most optimistic assessment. The winner is not received a certificate about higher knowledge. Maybe they just were the most optimistic person in the room.
</details>

当竞拍者没有考虑到这种筛选时，胜利往往会带来失望，这种模式被称为“赢家的诅咒”。所以，问题不仅在于“在我看来它价值几何”，更在于“如果我的出价是最高的，它的价值应该是多少”，因为获胜表明其他人的估值更低。这并不意味着赢家总是亏钱，或者存在标准扣除金额。正确的调整取决于评估是如何形成的、有多少人参与拍卖以及他们如何出价。

<details><summary>Original English</summary>
When bidders do not take this into account selection, victory often brings disappointment, and such the model is called " the winner's curse ". So, it's better questions not only in because, in my opinion opinion, it costs a lot, and in because it should be its value if my rate is the highest, because victory indicates that others rated it lower. This does not mean that winners always lose money or that there is a standard amount for deduction. Correct adjustment depends from how assessments are formed, how many people are taking participation in the auction and how they place bets.
</details>

这里有一个关于这种差异的问题。你对一幅画估价 80 美元，因为你喜欢把它放在家里，并且你绝不会卖掉它。另一个竞标者估价为 100 美元。他们更高的估价是否意味着你的 80 美元是错误的？现在将此与那批咖啡豆进行对比。停下来判断什么是私有的，什么是共同的。他们的乐趣不会改变你的乐趣，所以你的私有评估可以保持在 80 的水平。而在咖啡豆的例子中，另一位参与者的评估是关于你试图确定的那个未知转售价值的信息。因此，他们的

<details><summary>Original English</summary>
Here is a question about this difference. You You rate the picture at 80. dollars because you it's nice to hold her at home and you never her You will not sell. Another bidder values it at $100 . Does their higher mean estimate that your 80 dollars were wrong? Now compare this to the lot beans. Stop and decide what is private, what about common. Theirs pleasure not changes yours, so your private assessment can stay on levels 80. With beans evaluation of another the participant is information about that the most unknown resale value that you are trying to to determine. Therefore, their
</details>

<!-- chunk 12/13 -->

出价可以成为你潜在收益的证据。这就是为什么在这里第二价格证明不起作用的原因。他预测，只要我们改变竞争对手的出价，对咖啡馆的估值就保持在80不变。在共同价值下，你的估值不是已知价值，胜利本身会改变你所应当预期的东西。这一切的目标在于超额收益，而不是为了胜利本身去争夺胜利。

<details><summary>Original English</summary>
the rate can be evidence of your possible profit. That is why the proof for there is no second price here works. He predicted that the assessment The cafe remained at 80 unchanged as long as we changed the rate competitor. At shared value your rating is not known value, and Victory itself changes what you have expect. The goal in all this— excess, not victory for the sake of of victory itself.
</details>

买家可以通过过度多付来赢下每一场拍卖。这是同时得到物品和遗憾的有效方式。因此，经济学问题在于，预期收益是否超过了所付出的款项。

<details><summary>Original English</summary>
The buyer can win everyone auction, excessive overpaying. It effective way get both objects and pity. Economical the question is therefore, whether it exceeds expected benefit payment made.
</details>

注意是谁选择了付款方式——卖家。这一选择改变了诚实出价的价值。是否有意识地制定规则，让有益的行为对做出决策的人有利？在人们共同分摊让所有人受益的事物的成本时，这个问题尤为重要。

<details><summary>Original English</summary>
Pay attention to who selected payment method -seller. This one the choice changed the value of honest pond. Is it possible? consciously develop rules so that useful behavior became profitable for the one who accepts decision? This is a question most importantly, when people share the costs on what everyone wins.
</details>

### 公共物品与搭便车问题

我们那两家就在拐角处的咖啡馆恰好将面临这种共同开支。两家都希望有一个更好的公共配送系统。每个店主都可以为改进出资，而每一项改进都会为两家机构带来好处。店主们一致认为改进是有用的，但大家都更希望由其他人来付钱。

<details><summary>Original English</summary>
Our two cafes are just around the corner will face exactly with this kind of common expenses. Both of them want a better common delivery system. Every owner can pay for improvements, and every improvement brings benefits to both institutions. Owners agree that improvements are useful, but everyone would prefer, to have someone else pay.
</details>

现在我们可以诊断问题，而不是给他们上一通关于团队合作的励志演讲。假设每份出资对付款方而言耗费6美元，并为每家咖啡馆创造4美元的收益。这些是假定的数字，选出来是为了便于我们比较选择。当双方都出资时，收益会累加。

<details><summary>Original English</summary>
Now we can diagnose problem instead to read to them motivational speech about teamwork. Suppose each the contribution is worth payer 6 dollars and creates 4 dollars benefits for everyone cafe. These are conditional numbers, chosen in order to we could compare election. Benefits are added when both do contribution.
</details>

如果双方都付钱，每家咖啡馆从自己的出资中获得四，从对方的出资中获得四，总计为八。每家咖啡馆也各支付六，因此每家剩下的净利润为二。如果只有A付钱，那么A得到4减去6，也就是负2，而B不付任何钱得到4。如果只有B付钱，数字对调：A得到4，B得到负2。如果没人付钱，双方都得到零。

<details><summary>Original English</summary>
If they pay both, every cafe gets four from own contribution and four from another, eight in total. Each the cafe also pays six, so each remains with the clean profit of two. If only A pays, then A gets 4 minus 6, that is, minus 2, and B gets 4, nothing paying. If only B pays, the numbers change in places. A gets 4, and B gets minus 2. If nobody pays, both receive zero.
</details>

让我们从A的角度来看这个情况。如果B出资，那么A出资带来2，不出资则带来4。如果B不出资，那么A出资带来负2，不出资则给A带来零。无论如何不出资都更好，所以这是严格优势策略，而B也面临同样的选择。两位店主都拒绝，每人得到零，尽管出资能给双方各带来二。我们重新发现了其他条件下的囚徒困境结构。

<details><summary>Original English</summary>
Let's take a look at the situation from A. If B contributes, then the contribution is given by A 2, then as absence contribution is given by A 4. If B does not contribute, then the contribution is A minus 2, while the absence contribution gives A zero. IN better anyway not to contribute, so it is purely dominant strategy, and B is faced with such by choice. Both owners refuse and receive zero each, although contribution I would bring both. two each. We rediscovered the structure of the dilemma prisoner in other conditions.
</details>

搭便车乘客的问题在于，一个人可以不承担提供成本而获得好处。极端情况是纯公共物品，它具有非竞争性和非排他性。非竞争性意味着一人使用该物品不会降低其他人获得该物品的可能性。非排他性意味着不可能或很难阻止那些不付钱的人享有该物品。

<details><summary>Original English</summary>
Problem ticketless passenger consists of because a person can to benefit, without incurring the costs of its provision. Extreme the case is pure public good, which is non-competitive and inalienable. Non-competitiveness means that use of the good not by one person reduces accessibility for others. Inalienability means that it is impossible or hard not to to allow for good those who don't pay.
</details>

我们的共享系统改进对这两家店来说正是如此。普通的配送不应该是这样的，因为货车空间有限，一家咖啡馆的箱子可能会挤占其他箱子。

<details><summary>Original English</summary>
Our shared system improvement works that's right for these two shops. Ordinary delivery should not to be like this because The van has limited space, and boxes one cafe can to displace others.
</details>

你的问题。一份6美元的出资给两家咖啡馆带来的总收益是多少，出资人自己的净利润又是多少？然后解释为什么出资对双方作为一个整体可能是有益的，但对付款的店主却毫无吸引力。

<details><summary>Original English</summary>
Your question. What total benefit from a contribution of 6 dollars for both cafes and which one net profit the donor himself? Then explain why the contribution may be useful for a couple, but unattractive for owner who pays.
</details>

停下来比较这两种视角。一份出资为A创造4美元，为B创造4美元，因此总收益为8美元。减去6美元的成本，共同净利润将为二。但出资人个人仅获得四的收益，却要支付全部的六，结果剩下负二。部分收益流向了其他人，因此个人层面的比较不同于群体层面的比较。

<details><summary>Original English</summary>
Stop and compare these two points of view. One contribution creates 4 dollars for A and 4 for B, therefore, the total benefit is 8 dollars. Subtract the cost of 6 dollars, and a joint net profit will be two. But the donor personally receives only four of benefits, while paying all six, which leaves minus two. Part of the benefit gets someone to another, therefore individual comparison differs from group.
</details>

### 机制设计与激励

那么什么规则可以改变这种个人比较呢？选择之一是强制性的联合协议。仅在双方都接受该一揽子方案的情况下，双方各支付六，然后改进得以实施。现在没有任何店主会陷入自己独自付钱的境地，也没有人能不付款就获得收益。选择变成了：要么是每人获得二的一揽子方案，要么是每人获得零的未达成协议状态。所以，基于我们的假设，双方都能同意。

<details><summary>Original English</summary>
So what? the rule could change it individual comparison? One of options—this mandatory joint agreement. Both pay six in that alone if both accept the package, and then improvement is being implemented. Now none of owners cannot to stay in situations when he pays himself, and no one cannot get benefit without payment. The choice becomes: either package that brings two each, or the absence of an agreement that brings zero to everyone. So, for our assumptions, both can agree.
</details>

这是机制设计的视角。你从想要的结果出发，询问什么样的规则能促使人们在顾及其信息和激励的情况下，以支持该结果的方式行事。拍卖、出资规则和合同都可以是这样的机制。机制仍需考虑到人们实际能做什么、他们是否会参与，以及设计者实际知道些什么。

<details><summary>Original English</summary>
It design perspective mechanisms. You start with what you want result and you ask which ones the rules will force people to act in such a way that to support him, considering their information and incentives. Auctions, contribution rules and contracts can to be like that mechanisms. The mechanism still has take into account that people can really to do, will they take they participate and what actually knows designer.
</details>

联合方案改变了店主们是否愿意付钱。现在咖啡馆需要一条能改变员工细致工作意愿的规则。它雇佣技术人员来维修设备。细致的工作将维修成功的概率从40%提高到80%，但这需要技术人员付出12美元的努力成本。成功给咖啡馆带来100美元的利润，而失败带来零。咖啡馆可以观察到成功，但无法直接检查付出的努力。

<details><summary>Original English</summary>
Joint the package changed whether the owners wanted pay. Now a cafe a rule is needed that will change the desire employee to do the work carefully. It hires equipment for service equipment. Thorough work increases probability successful repair with 40 %up to 80%, but it costs equipment 12 dollars efforts. Success brings cafe 100 dollars of profit, and failure—zero. Cafe can watch success, but can't directly check the effort.
</details>

起初咖啡馆提供20的固定报酬，无论维修是否成功都会支付。如果细致工作，技术人员得到20减去12，也就是八。不付努力的技术人员得到20。如果技术人员只看重这一项收入，固定报酬无法激励付出努力。咖啡馆希望获得高质量工作的愿望本身，并不是对该项工作完成的报酬。

<details><summary>Original English</summary>
First a cafe offers a fixed payment 20, that paid regardless of whether whether the repair was successful. With careful work technician gets 20 minus 12, that is eight. Effortless technician gets 20. If the technician only appreciates this one income, fixed the payment is not motivating effort. Cafe Wish to get quality work in itself is not a reward for its implementation.
</details>

假设咖啡馆支付20的基础报酬，外加维修成功时的40美元奖金。在付出努力的情况下，预期奖金为40的80%，即32。加上20的基础报酬并减去12的努力成本，技术人员的预期收入为40。若不付出努力，预期奖金为40的40%，即16。加上基础报酬，收入为36。细致工作现在多盈利四。在该模型中合同激励了努力，也就是说，期望的行动为技术人员带来的预期收入至少与备选方案相同。

<details><summary>Original English</summary>
Let's say a cafe pays base 20 plus $40 bonus in in case of successful repair. With effort expected bonus is 80% of 40, or 32. Add base 20 and subtract the cost effort 12, then expected income the technique is 40. Effortlessly expected bonus is 40% of 40, or 16. Add the base, and The income is 36. Careful work now more profitable four. Contract stimulates efforts in this model, that is the desired action brings at least the technique same expected income, as well as alternative.
</details>

轮到你了。保持相同的基本报酬不变，找出能让付出努力至少与不付出努力同样具有吸引力的最小成功奖金。努力使成功概率增加0.4，并且成本为12。停下来比较额外预期奖励与这些开销。

<details><summary>Original English</summary>
Your turn. Keeping that the basic pay itself, find the smallest bonus for success, which will make an effort at least the same attractive as their absence. Effort increase probability of success by 0.4 and cost 12. Stop and compare additional expected reward with these expenses.
</details>

我们把奖金称为B。努力将获得奖金的几率提高了0.4，因此额外的预期奖励是0.4*B。我们要求0.4 B至少为12。用12除以0.4，B不能少于30。刚好在30时，技术人员在两种行动选择之间无差异。任何高于30的奖金都会创造付出努力的明确激励，而我们40美元的奖金超过了这一门槛。这向我们表明技术人员在被雇佣后会选择什么行动。但他们究竟会不会签署合同——这是一个单独的核验。

<details><summary>Original English</summary>
Let's call the bonus B. Efforts increase chance to get it on 0.4, therefore additional expected reward is 0.4*B. To us it is necessary that 0.4 B be at least 12. Divide by 12 by 0.4, and B should not be less than 30. Exactly at 30 technician indifferent between two options for action. Any bonus over 30 creates a clear incentive to effort, and our $40 bonus overcomes this threshold. It shows us what action will choose a technician after hiring. Will they sign? they contract in general—this is a separate audit.
</details>

假设技术人员在别处能挣35。在40美元奖金下，付出努力带来40，这好于35。当奖金为最低的30时，努力带来20加24减去12，也就是32。因此技术人员会去别的地方。在固定报酬为20的情况下，甚至更好的不付努力的选项也仅带来20。如果我们忽视外部选择，我们就会制定出一份没人会签的合同。

<details><summary>Original English</summary>
Suppose a technician can earn 35 in somewhere else. At $40 bonus effort gives 40, which better than 35. When minimum bonus 30 efforts yield 20 plus 24 minus 12, that is 32. So, the technician goes to another place. At fixed payment 20 even better effortless option gives only 20. If we ignored external options, we would develop a contract that no one will not sign.
</details>

同样也要核验咖啡馆。假设在带有40美元奖金的合同下付出努力，咖啡馆的预期价值为80。其预期支出为20加32，即52。因此预期净利润为28。我们假设在拒绝维修的情况下收益为零。根据上述假定，该合同给咖啡馆带来了优势。这并不证明该合同是所有可能合同中最好的。我们没有检查所有的基本工资和奖金选择，同时也忽略了风险和未计算在内的质量因素。

<details><summary>Original English</summary>
Check also a cafe. Provided making efforts for contract with $40 bonus expected cost The cafe is 80. His expected the payout is 20 plus 32, or 52. So, expected net the profit is 28. Let's assume that in the case refusal of repairs the benefit is zero. According to the specified cafe assumptions provides advantage of this contract. This is not proves that such the contract is the best of the possible. We are not checked everything basic options pay and bonuses, and also ignored risks and unaccounted for quality.
</details>

我们找到了一个可接受的方案，它能激励付出努力并对双方都有利。在这两个故事中，我们都改变了选择标准，然后核验是否会有人拒绝协议。然而，这些核验中的每一个都是基于我们自己设定的数字。那么，当模型本身对人的描述不正确时，会发生什么呢？让我们在关于定价的最初博弈中检验这个问题。如果两位店主……

<details><summary>Original English</summary>
We found acceptable option, which stimulates to effort and profitable to both sides. In both stories we changed the criteria choice, and then checked if anyone will refuse agreements. However, each of these checks was based on numbers, which we ourselves have determined . So what's happening? when the model itself incorrectly describes people? Let's check this out. question on the initial game with pricing. If both owners
</details>

<!-- chunk 13/13 -->

维持低价，每个人每天获得 100 美元利润。如果一方降价，而另一方——不降，那么降价的一方获得 150。而维持原价的店主获得 30。如果双方都降价，每个人获得 60。

<details><summary>Original English</summary>
keep prices down, everyone receives 100 dollars daily profit. If one lowers the price, and the other—no, the one who lowered, gets 150. A the owner who kept price, gets 30. If both decrease, everyone gets 60.
</details>

无论竞争对手采取什么行动，降价都更有利可图，因此我们预测双方都会降价。明天双方都维持低价。还是博弈论遭受了挫败？也许是我们的想法有误，或者是原始数据有误。

<details><summary>Original English</summary>
The decrease was more profitable regardless from the actions of a competitor, so we predicted, that both will reduce prices. Tomorrow both keep prices down. Or game theory has undergone defeat? Perhaps, our thoughts were erroneous, or source data.
</details>

错误的预测是展开研究的理由，而不是为了现实去捍卫表格的理由。但研究并不意味着捏造任何故事来挽救回应。这意味着检查我们是否写下了店主们想要什么、他们能够选择什么以及他们知道什么。

<details><summary>Original English</summary>
False forecast is a reason for research, not reason to defend table from reality. But research is not means fabrication any story, to save respond. This means checking that we wrote down what they want owners that they could choose and what they knew.
</details>

让我们从他们想要什么开始。在我们的表格中，假设每位店主只对当天的利润感兴趣。相反，我们假设每位店主都承诺维持价格，而违反这一承诺会被视为损失 60 个单位。现在效用是每次每日利润减去 60，

<details><summary>Original English</summary>
Let's start with of what they want. In our tables it was assumed that each owner only interested profit for the current day. Let's assume instead, that everyone the owner promised to maintain the price, and violation of this promises perceived as loss of 60 units. Now the utility is daily profit minus 60 every time,
</details>