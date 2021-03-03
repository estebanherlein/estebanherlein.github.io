---
title: "Bug Prevention and Defensive Programming"
categories:
  - Blog
tags:
  - debugging
---

Surprisingly, the debugging process may take significantly more time than writing the code in the first place. A large amount (if not most) of the development of a piece of software goes into debugging and maintaining the code, rather than writing it.

Therefore, the best thing to do is to avoid the bug when you write the program in the first place! 

It is important to sit and think before you code: decide exactly what needs to be achieved, how you plan to accomplish that, design the high-level algorithm cleanly, convince yourself it is correct, decide what are the concrete data structures you plan to use, and what are the invariants you plan to maintain.

 All the effort spent in designing and thinking about the code before you write it will pay off later.

The benefits are twofold. 

First, having a clean design will reduce the probability of defects in your program. 

Second, even if a bug shows up during testing, a clean design with clear invariants will make it much easier to track down and fix the bug.

It may be very tempting to write the program as fast as possible, leaving little or no time to think about it before. The programmer will be happy to see the program done in a short amount. 

But it's likely he will get frustrated shortly afterwards: without good thinking, the program will be complex and unclear, so maintenance and bug fixing will become an endless process.

Once the programmer starts coding, he should use defensive programming. 

This is similar to defensive driving, which means driving under worst-case scenarios (e.g, other drivers violating traffic laws, unexpected events or obstacles, etc). 

Similarly, defensive programming means developing code such that it works correctly under the worst-case scenarios from its environment. 

For instance, when writing a function, one should assume worst-case inputs to that function, i.e., inputs that are too large, too small, or inputs that violate some property, condition, or invariant; the code should deal with these cases, even if the programmer doesn't expect them to happen under normal circumstances.

Remember, the goal is not to become an expert at fixing bugs, but rather to get better at writing robust, (mostly) error-free programs in the first place. 

As a matter of attitude, programmers should not feel proud when they fix bugs, but rather embarrassed that their code had bugs. 

<b>If there is a bug in the program, it is only because the programmer made mistakes.</b>

<h2>Classes of Defects</h2>

Even after careful thought and defensive programming, a program may still have defects. 

Generally speaking, there are several kinds of errors one may run into:

<ul>
   
<li><b>Syntax or type errors.</b><br> These are always caught by the compiler, and reported via error messages. Typically, an error message clearly indicates the cause of error; for instance, the line number, the incorrect piece of code, and an explanation. Such messages usually give enough information about where the problem is and what needs to be done. In addition, editors with syntax highlighting can give good indication about such errors even before compiling the program.</li> 

<li><b>Typos and other simple errors that have pass undetected by the type-checker or the other checks in the compiler.</b><br> Once these are identified, they can easily be fixed. Here are a few examples: <br>missing parentheses, for instance writing x + y * z instead of (x + y) * z; <br>typos, for instance case t of ... | x::tl => contains(x,t);<br> passing parameters in incorrect order; <br> or using the wrong element order in tuples.</li>

<li><b>Implementation errors.</b> <br>It may be the case that logic in the high-level algorithm of a program is correct, but some low-level, concrete data structures are being manipulated incorrectly, breaking some internal representation invariants.

For instance, a program that maintains a sorted list as the underlying data structure may break the sorting invariant.

Building separate ADTs to model each data abstraction can help in such cases: it can separate the logic in the algorithm from the manipulation of concrete structures; in this way, the problem is being isolated in the ADT.  </li>

<li><b>Logical errors.</b> <br>If the algorithm is logically flawed, the programmer must re-think the algorithm. Fixing such problems is more difficult, especially if the program fails on just a few corner cases.

One has to closely examine the algorithm, and try to come up with an argument why the algorithm works. Trying to construct such an argument of correctness will probably reveal the problem. A clean design can help a lot figuring out and fixing such errors. 

In fact, in cases where the algorithm is too difficult to understand, it may be a good idea to redo the algorithm from scratch and aim for a cleaner formulation.</li>
</ul>

<h2>Difficulties</h2>

The debugging process usually consists of the following:
<ol>
<li>Examine the error symptoms</li>
<li>Identify the cause</li>
<li>Finally fix the error.</li>
</ol>

This process may be quite difficult and require a large amount of work, because of the following reasons: 

<ul>
<li><b>The symptoms may not give clear indications about the cause.</b><br> In particular, the cause and the symptom may be remote, either in space (i.e., in the program code), or in time (i.e., during the execution of the program), or both. <b>Defensive programming can help reduce the distance between the cause and the effect of an error.</b></li>

<li><b>Symptoms may be difficult to reproduce.</b><br> Replay is needed to better understand the problem. Being able to reproduce the same program execution is a standard obstacle in debugging concurrent programs. An error may show up only in one particular interleaving of statements from the parallel threads, and it may be almost impossible to reproduce that same, exact interleaving. </li>

<li><b>Errors may be correlated. Therefore, symptoms may change during debugging, after fixing some of the errors.</b> <br>The new symptoms need to be re-examined. The good part is that the same error may have multiple symptoms; in that case, fixing the error will eliminate all of them. </li>

<li><b>Fixing an error may introduce new errors.</b><br> Statistics indicate that in many case fixing a bug introduces a new one! This is the result of trying to do quick hacks to fix the error, without understanding the overall design and the invariants that the program is supposed to maintain. Once again, a clean design and careful thinking can avoid many of these cases.</li>

</ul>
