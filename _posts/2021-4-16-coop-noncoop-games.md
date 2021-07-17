---
title: "Cooperative and non-cooperative games"
categories:
  - Blog
tags:
  - Game Theory
---

Although there are many types (e.g., symmetric/asymmetric, simultaneous/sequential, et al.) of game theories, cooperative and non-cooperative game theories are the most common. 

Cooperative game theory deals with how coalitions, or cooperative groups, interact when only the payoffs are known. It is a game between coalitions of players rather than between individuals, and it questions how groups form and how they allocate the payoff among players.

Non-cooperative game theory deals with how rational economic agents deal with each other to achieve their own goals. The most common non-cooperative game is the strategic game, in which only the available strategies and the outcomes that result from a combination of choices are listed. A simplistic example of a real-world non-cooperative game is Rock-Paper-Scissors.  

<h2>Rock-Paper-Scissors.</h2>

The game Rock-Paper-Scissors (RPS) is represented in  what is called a game box. There are two players, 1 and 2. Each player has three strategies in the game:
 
<img src="https://i.imgur.com/2jELMt1.png" alt="rock paper scissors payoff matrix"> 

R (rock), P (paper), and S (scissors). Player 1 is represented by the rows while player 2 is represented by the columns.

If player 1 chooses R and player 2 chooses P then this is represented as the pair, called a strategy profile, (R,P) and the result is that player 1 gets a payoff of -1 and player 2 gets a payoff of +1, represented as a payoff profile (-1, 1). For interpretation, think of payoffs as encoding preferences over winning, losing, or tying, with the understanding that S beats P (because scissors cut paper), P beats R (because paper can wrap a rock… ), and R beats S (because a rock can smash scissors). If both choose the same, then they tie. 

This game is called zero-sum because, for any strategy profile, the sum of payoffs is zero. In any zero-sum game, there is a number V , called the value of the game, 2 with the property that player 1 can guarantee that she gets at least V no matter what player 2 does and conversely player 2 can get -V no matter what player 1 does.

In this particular game, V = 0 and both players can guarantee that they get 0 by randomizing evenly over the three strategies. Note that randomization is necessary to guarantee a payoff of at least 0.


<h2>Eating Out with Friends</h2>

Eight friends have decided to go out together for lunch at a burger restaurant. They will split the bill equally. There are two items on the menu: (i) a regular burger that costs $4 and (ii) a deluxe burger that costs $8.

Each friend feels that eating a regular burger is worth $5 while eating a deluxe burger is worth $6. Note that a regular burger is worth more than it costs ($5 > $4) while a deluxe burger is worth less than it costs ($6 < $8). 

Deluxe burgers are obviously a bad deal—you have to pay $8 for something that is only worth $6 to you—but game theory predicts that, when eating together, all eight friends will splurge on deluxe burgers. Why?

To understand this unexpected outcome, it is helpful to think about the game from a mathematical point of view. Let D be the number of friends who order deluxe and let R be the number who order regular. (D and R are integers from 0 to 8, with R + D = 8, because there are eight friends in total.) Since deluxe burgers cost $8 and regular ones cost $4, the total bill is 8D + 4R. Since R = 8 − D, we can rewrite this as 8D + 4 (8 − D). Multiplying this out, we get 8D + 32 − 4D which can be simplified to

<b>Total bill = 32 + 4d</b>

Each friend’s individual bill is 1/8th of the total bill. Since the total bill is 32 + 4D, each friend pays 32/8 + 4D/8 which can be simplified to

<b>Individual bill = 4 + d/2</b>

When someone upgrades their order from “regular” to “deluxe,” they get an extra dollar of value from the burger (it’s now worth $6 to them instead of $5). However, they only pay an extra 50 cents, since the additional $4 cost for the deluxe burger is split eight ways. 

Each individual, therefore, has a motivation to order a deluxe burger even though, when everyone does this, they all wind up paying $8 for something that is only worth $6 to them. 

What would happen if one person in the group decided to order a regular burger? The total bill would fall from $64 to $60, causing everyone’s individual bill to fall from $8 to $7.50. So, the person who ordered the regular burger would have to pay $7.50 for something that is only worth $5 to them, even worse than paying $8 for something that is only worth $6.

This seems strange but, in fact, this turns out to be an example of the most famous and most well-studied strategic situation in game theory—the game known as the “Prisoners’ Dilemma (PD).”