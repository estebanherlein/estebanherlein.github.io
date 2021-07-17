---
title: "Code review: What are you reviewing for?"
categories:
  - Blog
tags:
  - Software Testing
  - Bug Hunting
  - Teaching
  - Quality Assurance
---

When reviewing code you need to know what is expected. Are you reviewing for security, functionality, maintainability, and/or style? Does your organization have tools and documents on code style or are you using your own coding style?  

<h2>Security</h2>

A Security code review is a specialized task involving manual and/or automated review of an application's source code in an attempt to identify security-related weaknesses (flaws) in the code. A Security code review does not attempt to identify every issue in the code, but instead looks to provide insight into what types of problems exist and to help the developers of the application understand what classes of issues are present. The goal is to arm the developers with information to help them make the application's source code more sound and secure.

<h2>Functionality</h2>

Functiontionality means the ability to perform a task or function. This relates to the business logic behind what you are developing. Functional reviews are mostly done between team members before proceding to the Code Review phase of the developing workflow

<h2>Maintainability</h2>

The purpose of maintainability is to ensure that, over time, a program can be easily maintained.

A programmer may decide to return to a program they wrote some time before in order to add an extra feature. Additionally, another programmer may wish to modify the program in order to improve it or debug an error.

In both situations, the understanding of the program, how it works and the purpose of the code will be made easier if the program is written in a maintainable style. This includes using:

<ul>
<li><b>Comments</b></li>
Comments are lines in programs that provide information about what the different parts of the program do. They serve no other purpose, and are not executed when the program is run - the program simply ignores them and moves on to the next line of code.
<br>

<li><b>Sensible variable names</b></li>
Many programmers choose meaningless variable names such as x or y. While a program will run with such names, it makes understanding the purpose of the variable much more difficult. Programmers should choose a variable name that reflects the purpose of the variable and the data it is intended to hold
<br>

<li><b>Indentation</b></li>
Code within selections or iterations should be indented. This allows the programmer to easily see which code falls within the selection or iteration, and where it ends.
<br>
</ul>


<h2>Style</h2>

On every team there are quite a few programmers, each one with his own hobbies or habits. Because of this, reaching a consensus can be a pitched battle in the beginning but, like it or not, we have to reach an agreement.

The important thing about a good Code Style is that it is not imposed by anyone and that definition is reached among all the people on the team. In addition, it will always be subject to changes and updates. It is very important that all proposals are heard and brought to a forum to evaluate them and study if they are possible. In this way, everyone feelspart of it and will abide by it without problems.