---
title: "Blackbox testing"
categories:
  - Blog
tags:
  - testing software
---
A method of software testing that examines the functionality of an application without peering into its internal structures or workings. 

This method of test can be applied virtually to every level of software testing: unit, integration, system and acceptance. It is sometimes referred to as specification-based testing

<h1>Basic Procedure</h1>

The tester is aware of what the software is supposed to do but is not aware of how it does it. 

For instance, the tester is aware that a particular input returns a certain invariable output but is not aware of how the software produces the output in the first place.

Test cases are built around specifications and requirements, i.e., what the application is supposed to do. 

Test cases are generally derived from external descriptions of the software, including specifications, requirements and design parameters.

Although the tests used are primarily functional in nature, non-functional tests may also be used.

The test designer selects both valid and invalid inputs and determines the correct output, often with the help of a test oracle or a previous result that is known to be good, without any knowledge of the test object's internal structure. 

<h1>Testing techniques</h1>
<ol>
<li><b>Boundary Value Analysis</b>: <br> The most commonly used black box testing technique, Boundary Value Analysis or BVA is used to find the error in the boundaries of input values rather than the center.</li>
<li><b>Equivalence Class Partitioning</b>:<br>  This technique is used to reduce the number of possible inputs to small yet effective inputs. Used to test an application exhaustively and avoid redundancy of inputs, it is done by dividing inputs into classes and getting value from each class.</li>
<li><b>Decision Table Based Testing</b>: <br>  This approach is the most rigorous one and is ideally implemented when the number of combinations of actions is taken under varying conditions.</li>
<li><b>Cause-Effect Graphing Technique</b>: <br> This technique considers a system’s desired external behavior only. It helps in selecting test cases which relate Causes to Effects to create test cases. In the aforementioned statement, Cause implies a distinct input condition which results in internal change in a system while Effect implies an output condition brought by a combination of causes.</li>
<li><b>Error Guessing</b>: <br> The success of this technique is solely dependent on the experience of the tester. There are no tools and techniques as such, but one can write test cases either while reading the document or while encountering an undocumented error during the testing.</li>
</ol>

<h1>Advantages</h1>

<ul>
<li>Unbiased tests because the designer and tester work independently</li>
<li>Tester is free from any pressure of knowledge of specific programming languages to test the reliability and functionality of an application / software</li>
<li>Facilitates identification of contradictions and vagueness in functional specifications</li>
<li>Test is performed from a user’s point-of-view and not of the designer’s</li>
<li>Test cases can be designed immediately after the completion of specifications</li>
</ul>

<h1>Disadvantages</h1>

<ul>
<li>Tests can be redundant if already run by the software designer</li>
<li>Test cases are extremely difficult to be designed without clear and concise specifications</li>
<li>Testing every possible input stream is not possible because it is time-consuming and this would eventually leave many program paths untested</li>
<li>Cannot be used for testing complex segments of code</li>

</ul>

