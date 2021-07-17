---
title: "Future proofing test automation"
categories:
  - Blog
tags:
  - Software Testing
  - Bug Hunting
---

Without a clear strategy in mind, many teams make the mistake of automating their tests for their current situation.

Perhaps you're just starting out and you have a dozen or so tests that run locally. However, once you're up to, let's say a hundred tests ,all of a sudden, it's very clear how faulty your design decisions were.

Now you have to find time to refactor your test automation project.

I'll share with you some design considerations that you can keep in mind early in your automation journey. Knowing these things upfront will help you future-proof your test automation project and save you lots of time and headaches.

<h1>Test in parallel</h1>

When you only have a handful of automated tests, running them sequentially doesn't seem like a big deal however as the number of automated tests grows the longer it will take for your entire test suite to complete.

A solution to this is to run the tests in parallel. However this is not as simple as flipping a switch, your tests have to be designed to run this way.

<h2>Decouple your tests</h2>

For starters you should not have any of your test dependent on one another.

If you rely on test one to execute before another test, then these two tests cannot be run in parallel. Be sure to design all of your tests to be independent; any setup or cleanup should be isolated within the test itself.

You also want to avoid modifying test data that other tests may rely on, if test one changes the value of a record and changes it back to its original value once completed then there's still a risk of the test executing at the moment where the value has been changed. Therefore test two fails to mitigate this.

Any test that needs to change test data should be the only test using that data.

Finally objects and variables that are used by multiple tests should be declared in a thread-safe manner meaning they should not be global or static as their values could change.

While your automation project consists of test code, that doesn't mean that you can throw caution to the wind and ignore clean coding practices. 

<h1>Remember test automation is software development.</h1>

It has to be extended and maintained so it's best to develop it in a manner that will support both. 

Avoid excessive code duplication, long classes and methods, inefficient waiting within tests and other bad practices 

Instead embrace approaches that enable Code reusability and maintainability. Become familiar with design patterns that are especially beneficial for test automation projects, design patterns such as the page object model, screenplay, fluent builder, singleton, factory facade.

You don't have to use all of these in fact some are alternatives to each other but being knowledgeable about them helps you know which ones are best for your test automation project.