---
title: "Debugging for beginners"
categories:
  - Blog
tags:
  - Debugging
---

Without fail, the code we write as software developers doesn’t always do what we expected it to do. Sometimes it does something completely different! When this happens, the next task is to figure out why, and although we might be tempted to just keep staring at our code for hours, it’s much easier and efficient to use a debugging tool, or debugger.

A debugger, unfortunately, isn’t something that can magically reveal all the problems or “bugs” in our code. Debugging means to run your code step by step in a debugging tool like Visual Studio, to find the exact point where you made a programming mistake. 

You then understand what corrections you need to make in your code, and debugging tools often allow you to make temporary changes so you can continue running the program.

Using a debugger effectively is also a skill that takes time and practice to learn but is ultimately a fundamental task for every software developer.  i

<h2>Clarify the problem by asking yourself the right questions</h2>

It helps to clarify the problem that you ran into before you try to fix it. We expect that you already ran into a problem in your code, otherwise you wouldn't be here trying to figure out how to debug it! 

So, before you start debugging, make sure you've identified the problem you're trying to solve:

<ul>
<li>What did you expect your code to do?</li>

<li>What happened instead?</li>

<li>If you ran into an error (exception) while running your app, that can be a good thing! An exception is an unexpected event encountered when running code, typically an error of some kind. A debugging tool can take you to the exact place in your code where the exception occurred and can help you investigate possible fixes.</li>

<li>If something else happened, what is the symptom of the problem? Do you already suspect where this problem occurred in your code? For example, if your code displays some text, but the text is incorrect, you know that either your data is bad or the code that set the display text has some kind of bug. By stepping through the code in a debugger, you can examine each and every change to your variables to discover exactly when and how incorrect values are assigned.</li>

</ul>

<h2>Examine your assumptions</h2>

Before you investigate a bug or an error, think of the assumptions that made you expect a certain result. 

Hidden or unknown assumptions can get in the way of identifying a problem even when you are looking right at the cause of the problem in a debugger. 

You may have a long list of possible assumptions! 

Here are a few questions to ask yourself to challenge your assumptions.

<ul>
<li><b>Are you using the right API (that is, the right object, function, method, or property)?</b> An API that you're using might not do what you think it does. (After you examine the API call in the debugger, fixing it may require a trip to the documentation to help identify the correct API.)</li>

<li><b>Are you using an API correctly?</b> Maybe you used the right API but didn't use it in the right way.</li>

<li><b>Does your code contain any typos?</b> Some typos, like a simple misspelling of a variable name, can be difficult to see, especially when working with languages that don’t require variables to be declared before they’re used.</li>

<li><b>Did you make a change to your code and assume it is unrelated to the problem that you're seeing?</b></li>

<li><b>Did you expect an object or variable to contain a certain value (or a certain type of value) that's different from what really happened?</b></li>

<li><b>Do you know the intent of the code?</b> It is often more difficult to debug someone else's code. If it's not your code, it's possible you might need to spend time learning exactly what the code does before you can debug it effectively.</li>

</ul>

By questioning your assumptions, you may reduce the time it takes to find a problem in your code. You may also reduce the time it takes to fix a problem.

<h2>Always remember</h2>

When writing code, start small, and start with code that works! (Good sample code is helpful here.) 

Sometimes, it is easier to fix a large or complicated set of code by starting with a small piece of code that demonstrates the core task you are trying to achieve.

Then, you can modify or add code incrementally, testing at each point for errors.