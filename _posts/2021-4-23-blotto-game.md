---
title: "Blotto game"
categories:
  - Blog
tags:
  - Game Theory
---

A Colonel Blotto game is a type of two-person constant-sum game in which the players (officers) are tasked to simultaneously distribute limited resources over several objects (battlefields).

In the classic version of the game, the player devoting the most resources to a battlefield wins that battlefield, and the gain (or payoff) is equal to the total number of battlefields won.

Consider two players (Colonel Blotto and Enemy), two battlefields both of equal value, both players know each other's total level of resources prior to allocation, and they then must make a simultaneous allocation decision. It is often assumed Colonel Blotto is the more-resourced officer (his level of resource can be defined to be 1), and Enemy has a fraction of resources less than 1. The Nash equilibrium allocation strategies and payoffs depend on that resource level relationship. 

The Colonel Blotto game was first proposed by Émile Borel in 1921. The game was studied after the Second World War by scholars in Operation Research, and became a classic in game theory. Gross and Wagner's 1950 paper, from which the fictitious Colonel Blotto and Enemy get their name, provides some example Nash equilibrium. Macdonell and Mastronardi 2015 provide the first complete characterization of all Nash equilibria to the canonical simplest version of the Colonel Blotto game. This solution, which includes a graphical algorithm for characterizing all the Nash equilibrium strategies, includes previously unidentified Nash equilibrium strategies as well as helps identify what behaviors should never be expected by rational players. 

Nash equilibrium strategies in this version of the game are a set of bivariate probability distributions: distributions over a set of possible resource allocations for each player, often referred to as Mixed Nash Equilibria (such as can be found in Paper-Rock-Scissors or Matching Pennies as much simpler examples).

Macdonell and Mastronardi 2015 solution, proof, and graphical algorithm for identifying Nash equilibria strategies also pertains to generalized versions of the game such as when Colonel Blotto have differing valuations of the battlefields, when their resources have differing effectiveness on the two battlefields (e.g. one battlefield includes a water landing and Colonel Blotto's resources are Marines instead of Soldiers), and provides insights into versions of the game with three or more battlefields.

In addition to military strategy applications, the Colonel Blotto game has applications to political strategy (resource allocations across political battlefields), network defense, R&D patent races, and strategic hiring decisions. Consider two sports teams with must spend budget caps (or two Economics departments with use-or-lose grants) are pursuing the same set of candidates, and must decide between many modest offers or aggressive pursuit of a subset of candidates. 

<h2>Example</h2>

As an example Blotto game, consider the game in which two players each write down three positive integers in non-decreasing order and such that they add up to a pre-specified number S. Subsequently, the two players show each other their writings, and compare corresponding numbers. The player who has two numbers higher than the corresponding ones of the opponent wins the game.

For S = 6 only three choices of numbers are possible: (2, 2, 2), (1, 2, 3) and (1, 1, 4). It is easy to see that:

    Any triplet against itself is a draw
    (1, 1, 4) against (1, 2, 3) is a draw
    (1, 2, 3) against (2, 2, 2) is a draw
    (2, 2, 2) beats (1, 1, 4)

It follows that the optimum strategy is (2, 2, 2) as it does not do worse than breaking even against any other strategy while beating one other strategy. There are however several Nash equilibria. If both players choose the strategy (2, 2, 2) or (1, 2, 3), then none of them can beat the other one by changing strategies, so every such strategy pair is a Nash equilibrium.

For larger S the game becomes progressively more difficult to analyze. For S = 12, it can be shown that (2, 4, 6) represents the optimal strategy, while for S > 12, deterministic strategies fail to be optimal. For S = 13, choosing (3, 5, 5), (3, 3, 7) and (1, 5, 7) with probability 1/3 each can be shown to be the optimal probabilistic strategy.

Borel's game is similar to the above example for very large S, but the players are not limited to round integers. They thus have an infinite number of available pure strategies, indeed a continuum.

This concept is also implemented in a story of Sun Bin when watching a chariot race with three different races running concurrently. In the races each party had the option to have one chariot team in each race, and each chose to use a strategy of 1, 2, 3 (with 3 being the fastest chariot and 1 being the slowest) to deploy their chariots between the three races creating close wins in each race and few sure outcomes on the winners. When asked how to win Sun Bin advised the chariot owner to change his deployment to that of 2, 3, 1. Though he would be sure to lose the race against the fastest chariots (the 3 chariots); he would win each of the other races, with his 3 chariot easily beating 2 chariots and his 2 chariot beating the 1 chariots. 