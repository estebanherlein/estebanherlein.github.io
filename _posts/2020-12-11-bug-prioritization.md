---
title: "Bug prioritization"
categories:
  - Blog
tags:
  - software testing
---


Time management is key in most software development projects. Especially when a lot of bugs start to come in, features requests pop up and new feature releases are just around the corner, you might wonder how to manage the time of your developers most effectively.


<h1> The basic defect management process </h1>

The topic of bug tracking is – and should always be – a deeply integrated step inside the software development workflow.

On a basic level, the defect management process includes the following steps:

<ol>
<li>Finding bugs</li>
<li>Documenting bugs</li>
<li>Reproducing bugs</li>
<li>Fixing bugs</li>
</ol>


Bug prioritization occurs on the documentation step of this 4 step process


<h1>Bugs vs feature requests</h1>

Looking at the question of how to prioritize bugs, we need to deal with the follow up question of how to prioritize bugs vs feature requests.

<h2>What is technical debt?</h2>

Basically, technical debt is a “concept in programming which reflects the extra development work that arises when code which is easy to implement in the short run is used instead of applying the best overall solution”.

Technical debt arises naturally over time. Bugs arise by taking shortcuts in software development. Instead of implementing the best solution during software development (which naturally takes a lot of time), we tend to take a shortcut (as it’s more time-effective in the short-run).


<h1>Bug Prioritization algorithm </h1>


So, how do we prioritize bugs? And how do we find a good balance for implementing new feature requests.



<h2>Step 1: Collect information (bugs & feature requests)</h2>

The more information we have, the less risky our decisions are.

So, while having limited development resources, we need to be information-driven when it comes to the decision of how important certain bugs and feature requests are.

Start collecting all your bugs and feature requests in one place. An issue management tool or a simple spreadsheet might be a great fit for that. Talk with customers, users, website visitors, your colleagues, and clients and ask them about their feelings when it comes to certain features or bugs.

Step 1 might sound like an easy one. However, it is the most time-consuming step in this process. You need to find answers to a whole bunch of questions. When collecting bugs you need to make sure to look at the following things:

<ul>
<li>Does a bug affect one of the major flows in your product? (For example A user can’t create a new project in your project management software)</li>
<li>What is the estimated number of users who will encounter this bug? How important are these users for you?</li>
<li>How big will the effort to fix the bug be?</li>
</ul>

<h2>Step 2: Assign values to each bug & feature request</h2>

One way to evaluate the importance of a bug fix or feature request is by looking at the value your implementation is causing. A bug causing a dead footer link might not be as valuable as a bug affecting the user’s payment.

Many teams already proceed with that step by asking “how important a bug fix or new features is”. Though I recommend going even further by making use of the framework of outcome driven innovation.

<h2>Step 3: Outcome driven innovation</h2>

A wat to prioritize feature requests and bug fixes can be done by calculating the opportunity for each ticket. You can use the opportunity algorithm developed by Anthony W. Ulwick.

This framework lets you focus on what’s really important.

An algorithm? Sounds complicated. Here’s the good news: It isn’t.

The algorithm includes the following three parameters:

<ul>
<li>Importance (of a feature request or bug fix)</li>
<li>Satisfaction (of the user with a feature request or bug fix)</li>
<li>Opportunity (which is gained through the implementation of a feature request or bug fix)</li>
</ul>


By making use of this technique, you not only consider the importance of a bug fix, you also take other parameters (such as satisfaction and opportunity) into account as well.