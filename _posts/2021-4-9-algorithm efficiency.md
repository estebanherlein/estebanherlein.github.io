---
title: "Algorithm efficiency"
categories:
  - Blog
tags:
  - Data Structures
  - Algorithms
---

The efficiency of an algorithm is related to the amount of resources it requires to obtain a solution to the problem (fewer resources, greater efficiency). It is assumed that all the algorithms discussed are going to be effective, that is, they adequately solve the problem for which they have been designed. 


<h2>Efficiency</h2>

The efficiency of an algorithm is determined by the lowest consumption of resources, such as the time and memory that are needed for it to be executed. This efficiency can be quantified with the following complexity measures 

<ul>
<li>Temporal complexity or execution time: "The cost or temporal complexity of an algorithm is defined as the time it takes to execute and provide a result from the input data" </li>


<li>
Spatial complexity: "The cost or spatial complexity of an algorithm is defined as the amount of memory required (total sum of the space occupied by the algorithm variables) before, during and after its execution" </li>

</ul>

From the previous definitions it can be guessed that problems will arise when evaluating the efficiency of an algorithm in an objective way. 

Since dependencies can appear in the measurement of temporal and spatial costs with elements outside the algorithm itself, such as: the programming language used, the machine where it is run, the compiler used, the experience of the programmer, etc. 

In addition, depending on elements such as the input data (number of data, value of the initial variables, ...), the way to make calls to other function libraries, auxiliary variables (of the language itself), etc. 

To avoid these problems, it makes sense to estimate the cost of algorithms regardless of the programs that implement them. 

In the same way that it makes sense to analyze the adequacy of the design of a building or a bridge regardless of its construction and, therefore, in all civil engineering processes studies are carried out on the proposed designs before their actual construction.


For each problem we will determine a measure N, which we will call the size of the input or the number of data to be processed by the program.

It affects runtime, the order in which the input elements are processed. It could be considered that the values of the n cases that are presented as input are those corresponding to a typical case, an average case or a worst case case. 

The worst case is the easiest to define (the one that takes the longest for any input); but, if other types of input are desired, it would be necessary to define what is considered typical or the distribution of the values in the average case.


<h2>Algorithm quality</h2>

The two most important measures of the quality of an algorithm are
<ul>
<li>the total computation time, measured by the number of computational operations performed during the execution of the algorithm, and the amount of memory used.</li>
<li>The notation to capture such information is through complexity functions.</li>
</ul>

To eliminate the effect of a certain computer or a certain programming language, it is considered that the algorithm is executed in a virtual "model" machine type RAM (English: random access machine) that has no memory limit or representation precision limit. of integers or real numbers ...