---
title: "Troubleshoot and Fix Your Code"
categories:
  - Blog
tags:
  - debugging
---
 
The process of troubleshooting and fixing the bugs in your code isn’t intuitive to anyone who hasn’t spent a long time learning to code.

Here are some common tips for beginners who feel stuck when their code is giving errors or isn’t doing what they want it to do.

While these tips are generally geared towards beginners, many of them are tips everyone follows when debugging issues.

 Even as someone who has been coding full time for years, you may still use these steps constantly (especially #9).
 
<h2>Print things a lot</h2>

On every single line of code, you should have a sense of what all of the variables values’ are. If you’re not sure, print them out!

Then when you run your program, you can look at the console and see how the values might be changing or getting set to null values in ways you’re not expecting.

Sometimes it’s helpful to print a fixed string right before you print a variable, so that your print statements don’t all run together and you can tell what is being printed from where

<pre><code>
print "about to check some_var"
print some_var
</code></pre>

<h2>Start with code that already works</h2>

When in doubt, start with someone else’s existing code that already works. If you’re a beginner, you’re still more of a Hacker than an Engineer, and so it’s better to start with an existing structure and tweak it to meet your needs.

Make sure you run the code you find before you make any changes to verify that it works properly and does what it claims to do. Then make small changes to the existing code and test it often to see if your changes have introduced bugs.

<h2>Run your code every time you make a small change</h2>

Do not start with a blank file, sit down and code for an hour and then run your code for the first time. You’ll be endlessly confused with all of the little errors you may have created that are now stacked on top of each other. It’ll take you forever to peel back all the layers and figure out what is going on.

Instead, you should be running any script changes or web page updates every few minutes – it’s really not possible to test and run your code too often.

The more code that you change or write between times that you run your code, the more places you have to go back and search if you hit an error.

<h2>Read the error message</h2>

It’s really easy to throw your hands up and say “my code has an error” and feel lost when you see a stacktrace. But in my experience, about 2/3rds of error messages you’ll see are fairly accurate and descriptive.

The language runtime tried to execute your program, but ran into a problem. Maybe something was missing, or there was a typo, or perhaps you skipped a step and now it’s not sure what you want it to do.

The error message does its best to tell you what went wrong. At the very least, it will tell you what line number it got to in your program before crashing, which gives you a great clue for places to start hunting for bugs.

<h2>Google the error message</h2>

If you can’t seem to figure out what your error message is trying to tell you, your best bet is to copy and paste the last line of the stacktrace into Google. Chances are, you’ll get a few stackoverflow.com results, where people have asked similar questions and gotten explanations and answers.

<h2>Guess and Check</h2>

If you’re not 100% sure how to fix something, be open to trying 2 or 3 things to see what happens. You should be running your code often (see #3), so you’ll get feedback quickly. Does this fix my error? No? Okay, let’s go back and try something else.

There’s a solid possibility that the fix you try may introduce some new error, and it can be hard to tell if you’re getting closer or farther away. Try not to go so far down a rabbit hole that you don’t know how to get back to where you started.

<h2>Comment-out code</h2>

Every programming language has a concept of a comment, which is a way for developers to leave notes in the code, without the language runtime trying to execute the notes as programming instructions.

You can take advantage of this language feature by temporarily “commenting out” code that you don’t want to lose track of, but that you just don’t want running right now. This works by basically just putting the “comment character” for your language at the start (and sometimes at the end) of the lines that you’re commenting out.

<h2>If you’re not sure where the problem is, do a binary search</h2>

The more code you have that’s running, the more places you have to check for an error. Especially as your project grows past a few dozen lines, it can get more and more difficult to find out where errors are happening. Your stack trace and error message should give you a clue as to where things are going wrong, but sometimes they’re not too helpful.

In that case, it’s helpful to do a binary search to hone in on the section of code that’s misbehaving.

At a high level, a binary search involves splitting something in half and searching each of the halves for what you’re looking for. Once you decide which half it’s in, you repeat the process again on that half. This is one of the quickest ways to hone in on where something is, in an otherwise large list of instructions.

<h2>Take a break and walk away from the keyboard</h2>

It’s really easy to get caught up in the details of your current implementation. You get bogged down in little details and start to lose sight of the forest through the trees.

In cases where you feel like you’ve been spinning on your wheels for the last 20 or 30 minutes, You should try to step away from the code and do some other activity for a little while. You can get a glass of water, meander around a bit or have a snack. It’s a great way to reset your mind, pull back and start to think of another approach.

<h2>How to ask for help</h2>

Okay okay, so you’ve really tried everything and it seems like nothing is working. Now you feel like you’re really ready to ask someone else for help.

Before asking anyone about a bug in your code, it’s important that you make sure you have all of the following components of an excellent question

<ol>
<li>Explain what you’re trying to do</li>
<li>Show the code that’s giving the error</li>
<li>Show the entire stack trace including the error message</li>
<li>Explain 2-3 things that you’ve tried already and why they didn’t work</li>
</ol>

Sometimes, in the simple process of going through these items in your mind and writing them down, a new solution becomes obvious. 
