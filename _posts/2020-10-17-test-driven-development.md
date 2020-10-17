---
title: "Test Driven Development"
categories:
  - Blog
tags:
  - software design patterns
  - basics
---

Test-driven development (TDD) involves two practices: Test First Development and Refactoring. 

First, you write a test and verify that the new test fails. 

Next, the code that makes the test pass is implemented successfully, after that the written code is refactored. 

The purpose of test-driven development is to achieve clean code that works. 

The idea is that the <b> requirements are translated into tests.</b> This means that, when the tests pass, it will be guaranteed that the software meets the requirements.

<h2> Requirements </h2>

For TDD to work, the system being coded has to be flexible enough to allow it to be tested automatically.

Each test will be small enough to allow it to uniquely determine whether or not the tested code passes the verification. 

This design patter avoids the unwanted "over-design" of applications: clearer interfaces and more cohesive code are achieved.

<h2> TDD Lyfe-cycle </h2>

First, a list of requirements is defined and then the teams iterates over the following cycle:
<ol>
<li>Select a requirement: The requirement is chosen from a list that is believed to give us greater knowledge of the problem and that, at the same time, is easily implementable.</li>

<li>Write a test: You start by writing a test for the requirement. For this, the programmer must clearly understand the specifications and requirements of the functionality to be implemented. This step forces the programmer to take a customer's perspective by considering the code through its interfaces.</li>

<li>Verify that the test fails: If the test does not fail, it is because the requirement was already implemented or because the test is wrong.</li>

<li>Write the implementation: Write the simplest code that makes the test work. The expression "Keep It Simple, Stupid!", Known as the KISS principle, is used.</li>

<li>Run automated tests: Verify if the entire test suite is working properly.</li>

<li>Elimination of duplication: The final step is refactoring, which will be used primarily to eliminate duplicate code. A small change is made at a time and then the tests are run until they work.</li>

<li>Requirements list update: The requirements list is updated by crossing out the implemented requirement. Likewise, requirements that have been seen as necessary during this cycle are added and design requirements are added (eg that one functionality is decoupled from another).</li>
</ol>

Having a single universal test repository makes it easy to supplement TDD with another best practice for agile development processes, <b>Continuous Integration<b>. 

Continuously integrating our work with that of the rest of the development team allows us to run the entire battery of tests and thus discover if our latest version is compatible with the rest of the system. 

It is advisable and less expensive to correct small problems every few hours, than to face huge problems close to the scheduled delivery date.

<h2> What makes TDD desirable?</h2>

<ul>

<li>Programmers using test-driven development in a raw project find that they rarely have the need to use the debugger.</li>

<li>Despite the high initial requirements of applying this methodology, TDD can provide great added value in software development producing higher quality applications in less time. </li>

<li>It offers more than just a validation of compliance with requirements, it can also guide the design of a program. </li>

<li>Focusing first on the test cases one must envision how the customers will use the functionality. Therefore, the programmer only cares about the interface and not the implementation.</li>

<li>The power of TDD lies in the ability to take small steps when needed. It allows a programmer to focus on the current task, and the first goal is often to make the test pass. </li>

<li>Exceptional cases and error handling are not considered initially. These are implemented after the main functionality has been achieved. </li>

<li>Another advantage is that, when used correctly, it ensures that all written code is covered by a test. This can give the programmer a higher level of confidence in the code.</li>

</ul>
