---
title: "Congestion games"
categories:
  - Blog
tags:
  - Game theory
---

Congestion games are a class of games in game theory first proposed by American economist Robert W. Rosenthal in 1973. 

<b>In a congestion game the payoff of each player depends on the resources it chooses and the number of players choosing the same resource. </b>

Congestion games are a special case of potential games. Rosenthal proved that any congestion game is a potential game and Monderer and Shapley (1996) proved the converse: for any potential game, there is a congestion game with the same potential function. 

<h2>Motivation</h2>

Consider a traffic net where two players originate at point O and need to get to point T . Suppose that node O is connected to node T via connection points A and B, where A is a little closer than B (i.e. A is more likely to be chosen by each player). 

However, both connection points get easily congested, meaning the more players pass through a point the greater the delay of each player becomes, so having both players go through the same connection point causes extra delay.

Good outcome in this game will be for the two players to "coordinate" and pass through different connection points. Can such outcome be achieved? And if so, what will the cost be for each player? 

We  model  this  situation  via  a  game  with  the  two  streams  as  players.  Eachplayer  has  two  available  strategies  –  routing  throughAor  routing  throughB– leading to four total possibilities