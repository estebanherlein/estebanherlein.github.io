---
title: "A good test case"
categories:
  - Blog
tags:
  - Quality Assurance
  - software testing
---


We define a test case as being a written document that provides comprehensive information on what, and how to test. A test case contains details such as the objective, description, exact steps, and most important of all, the expected output of the planned test.

<h2>Write better test cases</h2>

 Sometimes test cases are written as though they were just a regular routine task with little to no care, which leads to poor quality test cases. Writing strong and complete test cases offer numerous benefits to the individual running the test case, as well as to the overall project in the following ways:
 <ul>

<li><b>Reduces review and execution effort </b>– A well-written test case is easy to understand, and thus takes less time to review and execute. In a team, it is quite likely that the test case execution will be performed by a team member other than the creator of the test case, hence having good test cases always saves time and reduces back and forth communication among testers.</li>
<li><b>Identifies gaps early in the project lifecycle </b>– Test Case design requires the capturing of all positive as well as negative scenarios. Documenting those details requires an organized thought process and a complete understanding of the application under test (AUT) which in turn helps in identifying gaps for design and functionality upfront.</li>
<li><b>Helps achieve maximum test coverage  </b>– Test Cases are the primary indicator of the planned test coverage. In process-oriented projects, each test case is reviewed by the business owners to determine scope and coverage before it can be approved for execution. A complete test case with full path coverage always leave a good impression on the reviewer and so will receive less feedback.</li>
 </ul>
 
<h2>Anatomy of a good test case</h2>
 
Irrespective of the method followed for designing and maintaining the test cases, the standard template must include:


<b>Test Case Name/Title –</b> Each test case must be given a unique name.<br>
<b>Objective/Purpose of the test case –</b>  Specify the purpose of the test case.<br>
<b>Preconditions –</b> Add all preconditions, such as dependency or steps already completed.<br>
<b>Test Data required for executing that particular test, if any –</b>  This may not be needed all the time, but some test cases require specialized roles and privileges; hence it is good to add the test data details used for that test case.<br>
<b>Test Steps –</b> Add detailed steps without missing even a single step.<br>
<b>Expected Results –</b>  Add expected output.<br>
<b>Pass/Fail Status –</b> This field is updated only after the test case execution.<br>
<b>Comments –</b> if any.<br>


<h2>Characteristics of a good test case</h2>
<ul>
<li><b>it has one objective –</b><br>  Test Cases are written to cover both main and alternative work-flows. Every test case must aim to achieve only one purpose.<br>
Multiple goals in one test case may lead to incorrect results, incorrect tracking and could impact testing metrics. A prime example would be the testing of choice with the option of a Yes/No. In this case, creating a separate test case can ease the tracking of pass/failure depending on the provided input.</li>
<li><b>It is complete –</b><br>  This means that even if the steps are mentioned in any other test case of a related module, they still need to be included in all the test cases despite it being repetitive. The idea is that each test case must be independent and must be able to be executed with ease by anyone.</li>
<li><b>It makes no assumption –</b><br>  A written test case based on assumption leads to problems during execution. Test Case coverage requires the inclusion of different input conditions, but keeping close to real events is what’s needed by the business owners. It’s bad practice and economics to cause owners to spend on a situation which has almost zero probability.</li>
<li><b>It was conceived with domain expertise</b><br> Complete and to the point full coverage test cases are the product of experience. If the team is comprised of experienced members, it is recommended you utilize them for creating test cases.</li>
<ul>
