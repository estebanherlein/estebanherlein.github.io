---
title: "Whitebox testing"
categories:
  - Blog
tags:
  - testing software
---

In white-box testing an internal perspective of the system, as well as programming skills, are used to design test cases.

Although traditional testers tended to think of white-box testing as being done at the unit level, it is used for integration and system testing more frequently today. 

It can test paths within a unit, paths between units during integration, and between subsystems during a system–level test

Though this method of test design can uncover many errors or problems, it has the potential to miss unimplemented parts of the specification or missing requirements


<h1>Basic Procedure</h1>

It requires the tester to have an in-depth knowledge of the source code being tested. The programmer must have a deep understanding of the application to know what kinds of test cases to create so that every visible path is exercised for testing. 

Once the source code is understood then it can be analyzed for test cases to be created. 

The following are the three basic steps that white-box testing takes in order to create test cases:

<ol>
<li><b>Input</b> involves different types of requirements, functional specifications, detailed designing of documents, proper source code and security specifications.This is the preparation stage of white-box testing to lay out all of the basic information.</li>
<li><b>Processing</b> involves performing risk analysis to guide the whole testing process, proper test plan, execute test cases and communicate results. This is the phase of building test cases to make sure they thoroughly test the application the given results are recorded accordingly.</li>
<li><b>Output</b> involves preparing a final report that encompasses both the Testing plan and the results.</li>
	
</ol>

<h1>Levels</h1>
<ol>
<li><b>Unit testing.</b> White-box testing is done during unit testing to ensure that the code is working as intended, before integration happens with previously tested code. White-box testing during unit testing potentially catches many defects early on and aids in addressing defects that happen later on after the code is integrated with the rest of the application and therefore reduces the impacts of errors later in development.</li>
<li><b>Integration testing.</b> White-box testing at this level is written to test the interactions of interfaces with each other. The unit level testing made sure that each code was tested and working accordingly in an isolated environment and integration examines the correctness of the behaviour in an open environment through the use of white-box testing for any interactions of interfaces that are known to the programmer.</li>
<li><b>Regression testing.</b> White-box testing during regression testing is the use of recycled white-box test cases at the unit and integration testing levels.</li>
</ol>

<h1>Advantages</h1>

<ul>
<li>Side effects of having the knowledge of the source code is beneficial to thorough testing.</li>
<li>Optimization of code becomes easy as inconspicuous bottlenecks are exposed</li>
<li>Gives the programmer introspection because developers carefully describe any new implementation</li>
<li>Provides traceability of tests from the source, thereby allowing future changes to the source to be easily captured in the newly added or modified tests</li>
<li>Easy to automate</li>
<li>Provides clear, engineering-based rules for when to stop testing</li>
</ul>

<h1>Disadvantages</h1>

<ul>
<li>White-box testing brings complexity to testing because the tester must have knowledge of the program, or the test team needs to have at least one very good programmer who can understand the program at the code level. </li>
<li>On some occasions, it is not realistic to be able to test every single existing condition of the application and some conditions will be untested.</li>
<li>The tests focus on the software as it exists, and missing functionality may not be discovered.</li>
<li>The resulting test can be fragile because they are tightly coupled to the specific implementation of the thing being tested. The code under test could be rewritten to implement the same functionality in a different way that invalidates the assumptions baked into the test. This could result in tests that fail unnecessarily or, in the worst case, tests that give false positives and mask errors in the code.</li>

</ul>


