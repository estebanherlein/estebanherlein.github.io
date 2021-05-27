---
title: "PHP comments"
categories:
  - Blog
tags:
  - php
---

When programming in any language the process of adding comments involves writing notes alongside the code to describe what the code does and how it works. The comments are ignored by the PHP pre-processor when executing a script and are purely for human consumption.

Commenting of code is often neglected by software developers. Sometimes this is because the code is being developed to meet a looming deadline and there is no time to adequately comment it. Often there is a tendency on the part of the developers to believe that they will remember how the code works six months or a year from now. Another common excuse for not commenting is that the code is so well written as to be completely self-explanatory.

Excuses aside, there is much to be gained from included helpful and concise comments with the PHP code that powers your web site. Firstly, you will be amazed at how puzzling a section of code can be even a few months after you have written it. It is not unusual for a developer to revisit some old code they once wrote and express amazement that they actually wrote it. It is important to remember that there is a good chance you will have to continue to maintain your PHP scripts long after they are written.

Another important reason for commenting your code is to ensure that others who may follow in your footsteps to maintain or add functionality to your creation will also benefit from reading your comments. There are few things worse in the software development business than having to traverse the steep learning curve caused by the complexity of somebody else's uncommented code.

Now that we have established that commenting code is worthwhile, we can take a look at the mechanisms provided by PHP to achieve this goal. PHP provides two commenting mechanisms - one for single line comments, and another for multi-line comments. PHP borrows its commenting conventions from other languages such as C, C++ and Java, so if you are familiar with these languages there will be no surprises. 

<h2>PHP Single Line Comments</h2>

Comments that reside on a single line are prefixed with the two forward slash characters in PHP (i.e. //).

The following example contains a single line comment:


>   // This is a single line comment


The single line comment can be on a line of its own, or it can be appended to the end of a line of code:

>    echo "This is a test line"; // Output a line of text


In the above example the PHP pre-processor will execute the echo statement and then ignore everything after the // single line comment marker.

Single line comment markers are also useful for temporarily removing lines of code from the execution flow (particularly useful during debugging sessions). For example, the following change to our previous example will cause the PHP pre-processor to ignore the entire echo command during execution:

>  // echo "This is a test line";

<h2>PHP Multi-line Comments</h2>

Multi-line comments are wrapped in /* and */ delimiters. The /* marks the start of the comment block and the */ marks the end. The following example demonstrates the use of multi-line commenting in PHP:


/*

   This a multi-line block 
   of comments
   
*/


Multi-line comments are useful when you have notes you want to make in the code that will take up more than one line. The ability to mark blocks of lines as comments avoids the necessity of placing the single line comment marker at the start of each comment line.

Another useful application of multi-line comments is to comment out blocks of PHP code temporarily. It is quite common to have written some PHP script and then wonder if you can re-write it so that it is perhaps more efficient or reliable. In this situation you can comment out the old script fragment so that it is no longer executed and write some new code. If it turns out your new code is worse than the original (which happens from time to time) you can simply remove the new code and uncomment the old to bring it back into the execution flow
