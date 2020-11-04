---
title: "Regression testing"
categories:
  - Blog
tags:
  - software testing
---

Any type of software testing done after code is changed in order to discover errors , lack of functionality, or functional differences with respect to the expected behavior of the software.

The purpose of these tests is to ensure that test cases that have already been tested successfuly remain that way.

Regression tests can be defined as the set of planned tests that are selected to be executed, generally automatically and periodically, in each new release of the software product, with the purpose of verifying that it has not suffered regressions.

In most situations it is considered a good practice that when a bug is found and corrected, a test exposing the bug is written and retested regularly after subsequent changes to the program.


<h2>Types of regression tests</h2>

<h3>By scope</h3>
<ul>
<li><b>Local</b> - changes introduce new bugs.</li>
<li><b>Unmasked</b> - changes reveal previous errors.</li>
<li><b>Remote</b> - Changes link some parts of the program (modules) and introduce errors .</li>

</ul>

<h3>By temporality</h3>

<ul>
<li><b>New feature</b> - changes made with respect to new functionalities in the version introduce bugs in other new features in the same version of the software.</li>
<li><b>Pre-existing feature</b> - changes made with respect to new functionality introduce bugs in existing functionality from previous versions.</li>

</ul>


<h2>How to mitigate risks</h2>
 
<ul>
<li>Repeat the complete battery of tests, manually or by automation, periodically.</li>
<li>Partial repetition based on traceability and risk analysis.</li>
<li>Customer or user testing:<br>
<b>Beta</b> - distribution to potential users and subscribers of beta versions.<br>
<b>Pilot</b> - distribution to a well-defined and localized subset of potential users.<br>
<b>Parallel</b> - Using both types simultaneously </li>
<li>Emergency patches - these patches are released immediately, and will be included in future releases.</li>

</ul>

<h2>Quote on regression testing</h2>


> "As a consequence of the introduction of new bugs, program maintenance requires far more system testing per statement written than any other programming. Theoretically, after each fix one must run the entire batch of test cases previously run against the system, to ensure that it has not been damaged in an obscure way. In practice, such regression testing must indeed approximate this theoretical idea, and it is very costly." 
<br>

>  Fred Brooks, Mythical Man Month 