---
title: "Bug Severity vs Priority in Testing"
categories:
  - Blog
tags:
  - Software Testing
---


Bug severity and bug priority are two commonly used terms in software testing. However, they are often used interchangeably, which is incorrect. 

<h1>What is Bug Severity?</h1>

Bug severity is the measure of impact a defect (or bug) can have on the development or functioning of an application feature when it is being used. It depends on the effect of the bug on the system. Depending on how much of a threat the bug can pose to the software, bug severity can be divided into multiple levels:

<ul>
<li>Low: Bug won’t result in any noticeable breakdown of the system</li>
<li>Minor: Results in some unexpected or undesired behavior, but not enough to disrupt system function</li>
<li>Major: Bug capable of collapsing large parts of the system</li>
<li>Critical: Bug capable of triggering complete system shutdown</li>
</ul>

Usually, QA engineers are the ones to determine the level of bug severity.

<h2> How to determine Bug Severity?</h2>

Identify how frequently the bug can occur. Even if the bug itself is minor, it can be problematic if it occurs frequently in the code. In this case, the minor defect can majorly disrupt the end-user experience.

Once the defect has been isolated and identified, it can be examined to evaluate severity.

<h1> What is Bug Priority? </h1>

Bug priority refers to how urgently a bug needs to be fixed and eliminated from the website or app in question. Basically, it’s a measure of how the bug should be prioritized in the debugging hierarchy. Correctly assigning bug priority is integral to successfully planning a software development life cycle.

<h2>Levels of bug priority:</h2>

<ul>
<li>Low: Bug can be fixed at a later date. Other, more serious bugs take priority</li>
<li> Medium: Bug can be fixed in the normal course of development and testing.</li>
<li>High: Bug must be resolved at the earliest as it affects the system adversely and renders it unusable until it is resolved.</li>
</ul>

Testers can determine bug priority with the same two steps described earlier to determine bug severity.

<h1> Bug Severity vs Priority </h1>


<b> Bug Severity</b>

<ul>

<li> Refers to a measure of the impact that a bug can have on software work flow </li>
<li> Driven by performance of software </li>
<li> Subjective value that is likely to change over the course of development or with regard to resolution of other bugs </li>	
<li> High severity and low priority status means that the bug can cause significant damage, but can be fixed at a later date </li>

</ul>

<b>Bug Priority</b>

<ul>

<li> Refers to the order in which devs have to fix bugs </li>
<li> Driven by business value and time to release </li>
<li> Objective value that is not very likely to change significantly in a software development process </li>
<li> High priority and low severity status means that the bug must be fixed immediately but it does not affect the software too adversely </li>

</ul>


<h2> Example of high severity and low priority </h2>

A website renders with multiple flaws in some legacy browsers. The logo does not load, text scrambles, images are too pixellated. 

<b> Since this is a disruption to product functionality as well as user experience, bug severity is high. However, since the problem only occurs with legacy browsers, it won’t be affecting a large number of users. Hence, bug priority is low. </b>


<h2> Example of high severity and high priority </h2>

A website is being tested on Chrome and works perfectly. But when switched to Firefox, the pricing page shows major flaws. Buy buttons for purchasing plans have disappeared, and so has the text that outlines the prices and corresponding features included in each plan. In this case, anyone using Firefox cannot buy the product, or even know details of the product being offered.

<b> Since key functions are clearly being adversely affected, bug severity is high. Since the broken functions are blocking a key phase of the user journey (actually buying the product), bug priority is high.</b>


<h2> Example of low severity and high priority </h2>

While testing the functionality of a website, it is seen that buttons are slightly out of place when the site is run on Chrome. They can still be clicked easily, and do what they meant to. 

<b> This means that functionality is not affected hence bug severity is low. However, since out-of-place buttons don’t exactly make for a pleasurable visual representation and badly designed websites actively turn off users, bug priority is high. The issue needs to be fixed as fast as possible.</b>

<h2>  Example of low severity and low priority </h2>

While testing the website, some of the text is found to have typos, and the font and color do not match the color and font of the website’s primary design. 


<b> Now, this is a bug for sure but it is certainly not a real problem in functionality. Hence, bug severity is low. Similarly, it does not need to be fixed immediately, and hence bug priority is low.</b>
