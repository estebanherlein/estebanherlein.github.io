---
title: "Sonarqube"
categories:
  - Blog
tags:
  - Dev-ops
---
SonarQube is available for free under the GNU Lesser General Public License. An enterprise version for paid licensing also exists, as well as a data center edition that supports high availability

It is a platform used to evaluate the quality of source code, performing a static analysis in order to warn us about different points to improve and obtain metrics that help us improve our development operations as a whole.

Static analysis corresponds to the process of evaluating a software without executing it, I must mention that if we intend to evaluate the coverage of the tests, they must be executed.

SonarQube helps us improve the following aspects: 

<h3>Duplicate code</h3>

It gives us metrics related to duplicate code in our codebase. We understand by duplicate code a sequence of source code that occurs more than once.

Code duplication is generally considered a sign of poor or lazy programming style, since good development is more associated with code reuse. Its main disadvantage is that maintenance becomes a much more expensive task 

<h3>Dead code</h3>

It is the code that is in our codebase but it is never used. It usually appears after refactoring our code. 

<h3>Coding standards</h3>

Refers to conventions for writing source code, which are often dependent on the programming language.

The most common conventions refer to: variable names, indentations, spacing, etc. 

<h3>Cyclomatic complexity</h3>

It is a software quality metric based on the calculation of the number of independent paths that our code has.

The more complex the logic of a code, the more difficult it will be to understand, maintain and test. 

<h3>Comments</h3>

Comments are usually added for the purpose of making the source code easier to understand for maintenance or reuse.

Poor or scant documentation can make code maintenance very costly.

As with tests, a large percentage of comments does not ensure quality. Comments should be good and clarifying explaining public interfaces, but not logic or design.

<h3>Code coverage</h3>

Code coverage is a measure that indicates the percentage of code validated by the tests. Generally, with a greater coverage we ensure that no errors are introduced in a greater part of the code, but this will depend on the actual functionality that the tests cover.  

<h2>How SonarQube works</h2>

Using SonarQube is very simple. It has 4 fundamental components: parameters, scanners, rules and web server. 

<h3>Parameters</h3>

These are the values that you can set to tell SonarQube, elements such as: the name of the project, its ID, which languages or files you want to analyze or exclude, etc ... 

<h3>Scanners</h3>

SonarQube has several types of scanners to be able to analyze the code depending on the technology we are using.

SonarScanner can be run very easily from a command terminal. It is a script available for both Windows, Mac and Linux.

You can also analyze the code in your repository, if for example you use Jenkins or Azure Devops to download the code and automate the inspection.

The scanners make use of the SonarQube rules to indicate where the errors are. 

<h3>Rules</h3>

The rules in SonarQube are organized in different categories according to the languages or frameworks.

There are, for example, rules to analyze code in PHP, and in addition, there is a set of specific rules to analyze Drupal code

The rules are based on programming standards and good practices.

SonarQube rules basically show 3 types of evidence (issues): Bugs (errors in the code) Vulnerabilities (errors that affect security) Code Smells (bad practices that make it difficult for the code to be maintained)

In addition, within each type of evidence, it has different degrees of severity: blocking, critical, major, minor or info. 

<h3>Web server</h3>

SonarQube, after analyzing the code and comparing it with the live rules, displays the results through a web application.

The simplest thing, if it is a local instance, is to access it through port 9000 of your localhost. 