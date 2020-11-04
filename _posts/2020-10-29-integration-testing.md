---
title: "Integration testing"
categories:
  - Blog
tags:
  - software testing
---

A type of testing where software modules are integrated logically and tested as a group. 

A typical software project consists of multiple software modules, coded by different programmers. 

The purpose of this level of testing is to expose defects in the interaction between modules. 

<h1>The reason behind integration tests</h1>

Although each software module is unit tested, defects still exist for various reasons:

<ul>
<li>A Module, in general, is designed by a software developer whose understanding and programming logic may differ from other programmers. Integration Testing becomes necessary to verify the software modules work in unity</li>
    
<li>Through development requirements may change. These new requirements may not be addressed on unit tests and hence system integration Testing becomes necessary.</li>
     
<li>External Hardware interfaces, if any, could be erroneous</li>
    
<li>Inadequate exception handling could cause issues.</li>

</ul>

<h1>Big Bang Testing</h1>

Big Bang Testing is an Integration testing approach in which all the components or modules are integrated together at once and then tested as a unit.

 This combined set of components is considered as an entity while testing. If all of the components in the unit are not completed, the integration process will not execute. 

<b>Advantages:</b>

<ul><li>Convenient for small systems.</li></ul>

<b>Disadvantages:</b>

<ul>
<li>Fault Localization is difficult.</li>
<li>Given the number of interfaces that need to be tested in this approach, some links may be missed.</li>
<li>Since tIntegration testing can only  start after all the modules are designed, the testing team will have less time for execution in the testing phase.</li>
<li>Since all modules are tested at once, high-risk critical modules are not isolated and tested on priority. Peripheral modules which deal with user interfaces are also not isolated and tested on priority.</li>

</ul>


<h1>Incremental Testing</h1>

In this approach, testing is done by integrating two or more modules that are logically related to each other and then tested for proper functioning of the application. 

Afterwards, the other related modules are integrated incrementally and the process continues until all the logically related modules are integrated and tested successfully.

Incremental Approach is carried out by two different Methods: Bottom up and Top down

<h2>Bottom-up Integration Testing</h2>

Bottom-up Integration Testing is a strategy in which the lower level modules are tested first.

These tested modules are then further used to facilitate the testing of higher level modules. 

The process continues until all modules at top level are tested. Once the lower level modules are tested and integrated, then the next level of modules are formed. 

<b>Advantages:</b>

<ul>
<li>Easier Fault localization.</li>

<li>No time is wasted waiting for all modules to be developed</li>

</ul>

<b>Disadvantages:</b>

<ul>
<li>An early prototype is not possible</li>

<li>Critical modules (at the top level of software architecture) which control the flow of application are tested last and may be prone to defects</li>

</ul>

<h2>Top-down Integration Testing</h2>

Top Down Integration Testing is a method that takes place from top to bottom following the control flow of the software system.

The higher level modules are tested first and then lower level modules are tested and integrated in order to check the software functionality.

Stubs are used for testing if some modules are not ready. 

<b>Advantages:</b>

<ul>
<li>Easier Fault localization.</li>

<li>An early prototype is a feasible possibility</li>

<li>Critical Modules are tested on priority; which means than major design flaws could be found and fixed early.</li>

</ul>

<b>Disadvantages:</b>

<ul>
<li>Needs many Stubs.</li>

<li>Modules at a lower level may be tested inadequately.</li>

</ul>

<h1>How to do Integration Testing?</h1>

<ol>
    
<li>Prepare the Integration Test Plan</li>
<li>Design Test Scenarios, Cases, and Scripts.</li>
<li>Execute test Cases and report defects.</li>
<li>Track & re-test defects.</li>
<li> Re iterate over steps 3 and 4 until Integration is successful.</li>

</ol>
