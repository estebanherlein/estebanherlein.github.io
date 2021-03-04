---
title: "Debugging strategies"
categories:
  - Blog
tags:
  - debugging
---

Although there is no precise procedure for fixing all bugs, there are a number of useful strategies that can reduce the debugging effort. 

<b>A significant part (if not all) of this process is spent localizing the error, that is, figuring out the cause from its symptoms.</b>

Below are several useful strategies to help with this.

Keep in mind that different techniques are better suited in different cases; there is no clear best method. It is good to have knowledge and experience with all of these approaches.

Sometimes, a combination of one or more of these approaches will lead you to the error. 

<ul>
<li><b>Incremental and bottom-up program development.</b><br> One of the most effective ways to localize errors is to develop the program incrementally, and test it often, after adding each piece of code. It is highly likely that if there is an error, it occurs in the last piece of code that you wrote. With incremental program development, the last portion of code is small; the search for bugs is therefore limited to small code fragments. An added benefit is that small code increments will likely lead to few errors, so the programmer is not overwhelmed with long lists of errors. </li>

<li><b>Bottom-up development maximizes the benefits of incremental development.</b><br> With bottom-up development, once a piece of code has been successfully tested, its behavior won't change when more code is incrementally added later. Existing code doesn't rely on the new parts being added, so if an error occurs, it must be in the newly added code (unless the old parts weren't tested well enough).</li>

<li><b>Instrument program to log information.</b><br> Typically, print statements are inserted. Although the printed information is effective in some cases, it can also become difficult to inspect when the volume of logged information becomes huge. In those cases, automated scripts may be needed to sift through the data and report the relevant parts in a more compact format. Visualization tools can also help understanding the printed data. For instance, to debug a program that manipulates graphs, it may be useful to use a graph visualization tool (such as ATT's graphviz) and print information in the appropriate format (.dot files for graphviz). </li>

<li><b>Instrument program with assertions.</b><br> Assertions check if the program indeed maintains the properties or invariants that your code relies on. Because the program stops as soon as it an assertion fails, it's likely that the point where the program stops is much closer to the cause, and is a good indicator of what the problem is. An example of assertion checking is the repOK() function that verifies if the representation invariant holds at function boundaries. Note that checking invariants or conditions is the basis of defensive programming. The difference is that the number of checks is usually increased during debugging for those parts of the program that are suspected to contain errors. </li>

<li><b>Use debuggers.</b><br> If a debugger is available, it can replace the manual instrumentation using print statements or assertions. Setting breakpoints in the program, stepping into and over functions, watching program expressions, and inspecting the memory contents at selected points during the execution will give all  the needed run-time information without generating large, hard-to-read log files.</li>

<li><b>Backtracking.</b><br> One option is to start from the point where to problem occurred and go back through the code to see how that might have happened.</li> 

<li><b>Binary search.</b><br> The backtracking approach will fail if the error is far from the symptom. A better approach is to explore the code using a divide-and-conquer approach, to quickly pin down the bug. For example, starting from a large piece of code, place a check halfway through the code. If the error doesn't show up at that point, it means the bug occurs in the second half; otherwise, it is in the first half. Thus, the code that needs inspection has been reduced to half. Repeating the process a few times will quickly lead to the actual problem. </li>
 
<li><b>Problem simplification.</b><br> A similar approach is to gradually eliminate portions of the code that are not relevant to the bug. For instance, if a function fun f() = (g();h();k()) yields an error, try eliminating the calls to g, h, and k successively (by commenting them out), to determine which is the erroneous one. Then simplify the code in the body of buggy function, and so on. Continuing this process, the code gets simpler and simpler. The bug will eventually become evident. A similar technique can be applied to simplify data rather than code. If the size of the input data is too large, repeatedly cut parts of it and check if the bug is still present. When the data set is small enough, the cause may be easier to understand.</li>

<li><b>A scientific method: form hypotheses.</b><br> A related approach is as follows: inspect the test case results; form a hypothesis that is consistent with the observed data; and then design and run a simple test to refute the hypothesis. If the hypothesis has been refuted, derive another hypothesis and continue the process. In some sense, this is also a simplification process: it reduces the number of possible hypotheses at each step. But unlike the above simplification techniques, which are mostly mechanical, this process is driven by active thinking about an explanation. A good approach is to try to come with the simplest hypotheses and the simplest corresponding test cases.</li> 
    
<li><b>Bug clustering.</b><br> If a large number of errors are being reported, it is useful to group them into classes of related bugs (or similar bugs), and examine only one bug from each class. The intuition is that bugs from each class have the same cause (or a similar cause). Therefore, fixing a bug with automatically fix all the other bugs from the same class (or will make it obvious how to fix them).</li>

<li><b>Error-detection tools.</b><br> Such tools can help programmers quickly identify violations of certain classes of errors. For instance, tools that check safety properties can verify that file accesses in a program obey the open-read/write-close file sequence; that the code correctly manipulates locks; or that the program always accesses valid memory. Such tools are either dynamic (they instrument the program to find errors at run-time), or use static analysis (look for errors at compile-time). For instance, Purify is a popular dynamic tool that instruments programs to identify memory errors, such as invalid accesses or memory leaks. Examples of static tools include ESC Java and Spec#, which use theorem proving approaches to check more general user specifications (pre and post-conditions, or invariants); or tools from a recent company Coverity that use dataflow analysis to detect violations of safety properties. Such tools can dramatically increase productivity, but checking  is restricted to a particular domain or class of properties. There is also an associated learning curve, although that is usually low. Currently, there are relatively few such tools and this is more an (active) area of research.</li>

</ul>

A number of other strategies can be viewed as a matter of attitude about where to expect the errors:

<ol>

<li>The bug may not be where you expect it. It a large amount of time has unsuccessfully been spent inspecting a particular piece of code, the error may not be there. Keep an open mind and start questioning the other parts of the program.</li>

<li>Ask yourself where the bug is not. Sometimes, looking at the problem upside-down gives a different perspective. Often, trying to prove that the absence of a bug in a certain place actually reveals the bug in that place.</li>

<li>Explain to yourself or to somebody else why you believe there is no bug. Trying to articulate the problem can lead to the discovery of the bug.</li>

<li>Inspect input data, test harness. The test case or the test harness itself may be broken. One has to check these carefully, and make sure that the bug is in the actual program.</li>

 <li>Make sure you have the right source code. One must ensure that the source code being debugged corresponds to the actual program being run, and that the correct libraries are linked. This usually requires a few simple checks; using makefiles and make programs (e.g., the Compilation Manager and .cm files) can reduce this to just typing a single command.</li>

<li>Take a break. If too much time is spent on a bug, the programmer becomes tired and debugging may become counterproductive. Take a break, clear your mind; after some rest, try to think about the problem from a different perspective.</li>

</ol>

All of the above are techniques for localizing errors.

<b>Once they have been identified, errors need to be corrected. </b>

In some cases, this is trivial (e.g., for typos and simple errors)

Some other times, it may be fairly straightforward, but the change must ensure maintaining certain invariants. 
 
The programmer must think well about how the fix is going to affect the rest of the code, and make sure no additional problems are created by fixing the error. Of course, proper documentation of these invariants is needed.

Finally, bugs that represent conceptual errors in an algorithm are the most difficult to fix. The programmer must re-think and fix the logic of the algorithm.