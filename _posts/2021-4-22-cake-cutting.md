---
title: "Fair cake-cutting"
categories:
  - Blog
tags:
  - Game theory
---

Fair cake-cutting is a kind of fair division problem. The problem involves a heterogeneous resource, such as a cake with different toppings, that is assumed to be divisible – it is possible to cut arbitrarily small pieces of it without destroying their value. The resource has to be divided among several partners who have different preferences over different parts of the cake, i.e., some people prefer the chocolate toppings, some prefer the cherries, some just want as large a piece as possible. The division should be unanimously fair - each person should receive a piece that he or she believes to be a fair share.

The "cake" is only a metaphor; procedures for fair cake-cutting can be used to divide various kinds of resources, such as land estates, advertisement space or broadcast time.

The prototypical procedure for fair cake-cutting is divide and choose, which is mentioned already in the book of Genesis. It solves the fair division problem for two people. The modern study of fair cake-cutting was initiated during World War II, when Hugo Steinhaus asked his students Stefan Banach and Bronisław Knaster to find a generalization of divide-and-choose to three or more people. They developed the last diminisher procedure. 

Today, fair cake-cutting is the subject of intense research in mathematics, computer science, economics and political science. 

<h2>Assumptions</h2>

There is a cake C, which is usually assumed to be either a finite 1-dimensional segment, a 2-dimensional polygon or a finite subset of the multidimensional Euclidean plane Rd.

There are n people with subjective value functions over C. Each person i has a value function Vi which maps subsets of C to numbers. All value functions are assumed to be absolutely continuous with respect to the length, area or (in general) Lebesgue measure.[3] This means that there are no "atoms" – there are no singular points to which one or more agents assign a positive value, so all parts of the cake are divisible. In many cases, the value functions are assumed to be sigma additive (the value of a whole is equal to the sum of the values of its parts).

C has to be divided to n disjoint subsets, such that each person receives a disjoint subset.

The n people have equal rights to C. I.e., there is no dispute over the rights of the people – everyone agrees that everyone else is entitled to a fair share. The only problem is how to divide the cake such that each person receives a fair share.


<h2>Procedural requirements</h2>

In addition to the desired properties of the final partitions, there are also desired properties of the division process. One of these properties is truthfulness (aka incentive compatibility), which comes in two levels.

<ul>
<li>Weak truthfulness means that if the partner reveals his true value measure to the algorithm, he is guaranteed to receive his fair share (e.g. 1/n of the value of the entire cake, in case of proportional division), regardless of what other partners do. Even if all other partners make a coalition with the only intent to harm him, he will still receive his guaranteed proportion. Most cake-cutting algorithms are truthful in this sense.</li>
<li>Strong truthfulness means that no partner can gain from lying. I.e., telling the truth is a dominant strategy. Most cake-cutting protocols are not strongly truthful, but some truthful protocols have been developed; see truthful cake-cutting.</li>
</ul>

Another property is symmetry: there should not be a difference between different roles in the procedure. Several variants of this property have been studied:

<ul>
<li>Anonymity requires that, if the agents are permuted and the procedure is re-executed, then each agent receives exactly the same piece as in the original execution. This is a strong condition; currently, an anonymous procedure is known only for 2 agents.</li>
<li>Symmetry requires that, if the agents are permuted and the procedure is re-executed, then each agent receives the same value as in the original execution. This is weaker than anonymity; currently, a symmetric and proportional procedure is known for any number of agents, and it takes O(n3) queries. A symmetric and envy-free procedure is known for any number of agents, but it takes much longer - it requires n! executions of an existing envy-free procedure.</li>
<li>Aristotelianity requires that, if two agents have an identical value-measure, then they receive the same value. This is weaker than symmetry; it is satisfied by any envy-free procedure. Moreover, an aristotelian and proportional procedure is known for any number of agents, and it takes O(n3) queries.</li>
</ul>


A third family of procedural requirements is monotonicity: when a division procedure is re-applied with a smaller/larger cake and a smaller/larger set of agents, the utility of all agents should change in the same direction. See resource monotonicity for more details. 