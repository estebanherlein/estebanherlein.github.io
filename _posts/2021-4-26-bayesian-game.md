---
title: "Bayesian game"
categories:
  - Blog
tags:
  - Game theory
---

In game theory, a Bayesian game is a game in which players have incomplete information about the other players. 

For example, a player may not know the exact payoff functions of the other players, but instead have beliefs about these payoff functions. These beliefs are represented by a probability distribution over the possible payoff functions.

Ex, each player in the game is associated with a set of types, with each type in the set corresponding to a possible payoff function for that player. In addition to the actual players in the game, there is a special player called Nature. Nature randomly chooses a type for each player according to a probability distribution across the players' type spaces. This probability distribution is known by all players (the "common prior assumption"). This modeling approach transforms games of incomplete information into games of imperfect information (in which the history of play within the game is not known to all players).

Incompleteness of information means that at least one player is unsure of the type (and therefore the payoff function) of another player. Such games are called Bayesian because players are typically assumed to update their beliefs according to Bayes' rule. In particular, the belief a player holds about another player's type might change according to his own type. 

<h2>Sheriff's Dilemma</h2>

A sheriff faces an armed suspect. Both must simultaneously decide whether to shoot the other or not.

The suspect can either be of type "criminal" or type "civilian". The sheriff has only one type. The suspect knows its type and the Sheriff's type, but the Sheriff does not know the suspect's type. Thus, there is incomplete information (because the suspect has private information), making it a Bayesian game. There is a probability p that the suspect is a criminal, and a probability 1-p that the suspect is a civilian; both players are aware of this probability (common prior assumption, which can be converted into a complete-information game with imperfect information).

The sheriff would rather defend himself and shoot if the suspect shoots, or not shoot if the suspect does not (even if the suspect is a criminal). The suspect would rather shoot if he is a criminal, even if the sheriff does not shoot, but would rather not shoot if he is a civilian, even if the sheriff shoots. Thus, the payoff matrix of this Normal-form game for both players depends on the type of the suspect. It is assumed that payoffs are given as follows: 

 <img src="https://i.imgur.com/lJY6CLr.png" alt="sherrifs dilemma payoff"> 

If both players are rational and both know that both players are rational and everything that is known by any player is known to be known by every player (i.e. player 1 knows player 2 knows that player 1 is rational and player 2 knows this, etc. ad infinitum – common knowledge), play in the game will be as follows according to perfect Bayesian equilibrium:

When the type is "civilian", the dominant strategy for the suspect is not to shoot, and when the type is "criminal", the dominant strategy for the suspect is to shoot; alternative strictly dominated strategy can thus be removed. Given this, if the sheriff shoots, he will have a payoff of 0 with probability p and a payoff of -1 with probability 1-p, i.e. an expected payoff of p-1; if the sheriff does not shoot, he will have a payoff of -2 with probability p and a payoff of 0 with probability 1-p, i.e. an expected payoff of -2p. 

Thus, the Sheriff will always shoot if p-1 > -2p, i.e. when p > 1/3. 
