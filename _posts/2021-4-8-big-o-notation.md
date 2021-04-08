---
title: "Big O notation"
categories:
  - Blog
tags:
  - Data structures
---


Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. 

Big O is a member of a family of notations invented by Paul Bachmann, Edmund Landau, and others, collectively called Bachmann–Landau notation or asymptotic notation.

In computer science, big O notation is used to classify algorithms according to how their run time or space requirements grow as the input size grows.

In analytic number theory, big O notation is often used to express a bound on the difference between an arithmetical function and a better understood approximation; a famous example of such a difference is the remainder term in the prime number theorem. 

Big O notation is also used in many other fields to provide similar estimates. 

<h2>Algorithm analysis</h2>

Algorithm analysis refers to the analysis of the complexity of different algorithms and finding the most efficient algorithm to solve the problem at hand. Big-O Notation is a statistical measure, used to describe the complexity of the algorithm.

Basically, Big-O notation signifies the relationship between the input to the algorithm and the steps required to execute the algorithm. It is denoted by a big "O" followed by opening and closing parenthesis. Inside the parenthesis, the relationship between the input and the steps taken by the algorithm is presented using "n".

For instance, if there is a linear relationship between the input and the step taken by the algorithm to complete its execution, the Big-O notation used will be O(n). Similarly, the Big-O notation for quadratic functions is O(n^2)

<h3>Constant Complexity (O(C))</h3>

The complexity of an algorithm is said to be constant if the steps required to complete the execution of an algorithm remain constant, irrespective of the number of inputs. The constant complexity is denoted by O(c) where c can be any constant number.

<h3>Linear Complexity (O(n))</h3>

The complexity of an algorithm is said to be linear if the steps required to complete the execution of an algorithm increase or decrease linearly with the number of inputs. Linear complexity is denoted by O(n).

<h3>Quadratic Complexity (O(n^2))</h3>

The complexity of an algorithm is said to be quadratic when the steps required to execute an algorithm are a quadratic function of the number of items in the input. Quadratic complexity is denoted as O(n^2).

<h2>Space Complexity</h2>

In addition to the time complexity, where you count the number of steps required to complete the execution of an algorithm, you can also find space complexity which refers to the number of spaces you need to allocate in the memory space during the execution of a program.

