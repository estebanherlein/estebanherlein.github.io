---
title: "Input kludge"
categories:
  - Blog
tags:
  - Software Design Anti-Patterns
---

An input kludge is a type of failure in software (an anti-pattern) where simple user input is not handled. 

For example, if a computer program accepts free text input from the user, an ad hoc algorithm will mishandle many combinations of legal and illegal input strings. 

Input kludges are usually difficult for a programmer to detect in a unit test, but very easy for the end user to find. The evidence exists that the end user can easily crash software that fails to correctly handle user input.

Indeed, the buffer overflow security hole is an example of the problems caused.

To remedy input kludges, one may use input validation algorithms to handle user input. A monkey test can be used to detect an input kludge problem. 

A common first test to discover this problem is to roll one's hand across the computer keyboard or to 'mash' the keyboard to produce a large junk input, but such an action often lacks reproducibility. Greater systematicity and reproducibility may be obtained by using fuzz testing software. 