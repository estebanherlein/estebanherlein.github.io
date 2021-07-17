---
title: "Games of chance"
categories:
  - Blog
tags:
  - Probability Theory
---

Games of chance hold an honored place in probability theory, because of their conceptual clarity and because of their fundamental influence on the early development of the subject. 


Gambling is intimately interwoven with the development of probability as a mathematical theory. Most of the early development of probability, in particular, was stimulated by special gambling problems, such as

<ul>

<li>DeMere's problem</li>
<li>Pepy's problem</li>
<li>the problem of points</li>
<li>the Petersburg problem</li>

</ul>

Some of the very first books on probability theory were written to analyze games of chance, for example Liber de Ludo Aleae (The Book on Games of Chance), by Girolamo Cardano, and Essay d' Analyse sur les Jeux de Hazard (Analytical Essay on Games of Chance), by Pierre-Remond Montmort. 

Gambling problems continue to be a source of interesting and deep problems in probability to this day.

Of course, it is important to keep in mind that breakthroughs in probability, even when they are originally motivated by gambling problems, are often profoundly important in the natural sciences, the social sciences, law, and medicine. 

Also, games of chance provide some of the conceptually clearest and cleanest examples of random experiments, and thus their analysis can be very helpful to students of probability.


<h2> The Monty Hall problem </h2>

The Monty Hall problem is based on a TV game show, and has become famous because of the controversy that it generated. .

The Monty Hall problem involves a classical game show situation and is named after Monty Hall, the long-time host of the TV game show Let's Make a Deal.

There are three doors labeled 1, 2, and 3. A car is behind one of the doors, while goats are behind the other two.


The rules are as follows:

<ul>
<li>The player selects a door.</li>
<li>The host selects a different door and opens it.</li>
<li>The host gives the player the option of switching from her original choice to the remaining closed door.</li>
<li>The door finally selected by the player is opened and she either wins or loses.</li>
</ul>

<h2> Modeling Assumptions</h2>

Let us try to formulate the problem mathematically. In general, the actions of the host and player can vary from game to game, but if we are to have a random experiment in the classical sense, we must assume that the same probability distributions govern the host and player on each game and that the games are independent.

There are four basic random variables for a game:
<ol>
<li>U: the number of the door containing the car.</li>
<li>X: the number of the first door selected by the player.</li>
<li>V: the number of the door opened by the host.</li>
<li>Y: the number of the second door selected by the player.</li>
</ol>

Each of these random variables has the possible values 1, 2, and 3. However, because of the rules of the game, the door opened by the host cannot be either of the doors selected by the player, so V≠X and V≠Y. In general, we will allow the possibility V=U, that the host opens the door with the car behind it. Whether this is a reasonable action of the host is a big part of the controversy about this problem.

<h2>The Standard Strategy</h2>

In most real game shows, the host would always open a door with a goat behind it.

If the player's first choice is incorrect, then the host has no choice; he cannot open the door with the car or the player's choice and must therefore open the only remaining door.

On the other hand, if the player's first choice is correct, then the host can open either of the remaining doors, since goats are behind both. Thus, he might naturally pick one of these doors at random.

<h2>Player Strategies</h2>

The player, on the other hand, determines the probability density function of her first choice, namely P(X=j) for j∈{1,2,3}. 

The obvious first choice for the player is to randomly choose a door, since the player has no knowledge at this point. This leads to the uniform distribution, so P(X=j)=1/3 for j∈{1,2,3}

The player also determines the conditional density function of her second choice, given knowledge of her first choice and the door opened by the host, namely P(Y=l∣X=j,V=k) for i,j,k∈{1,2,3} with j≠k. 

Recall that since the player cannot choose the door opened by the host, this probability must be 0 for l=k. The distribution of X and the conditional distribution of Y given X and V constitute the player strategy.

<h2>The Probability of Winning</h2>

The mathematical formulation we have used is fairly complete. However, there is a much simpler analysis (which you may have discovered yourself).

Suppose that the host follows the standard strategy, and thus always opens a door with a goat.

If the player's first door is incorrect (contains a goat), then the host has no choice and must open the other door with a goat. Then, if the player switches, she wins. 

On the other hand, if the player's first door is correct and she switches, then of course she loses. 

Thus, we see that if the player always switches, then she wins if and only if her first choice is incorrect, an event that obviously has probability 2/3. If the player never switches, then she wins if and only if her first choice is correct, an event with probability 1/3