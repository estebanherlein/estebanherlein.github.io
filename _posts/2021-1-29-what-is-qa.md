---
title: "What is Quality Assurance?"
categories:
  - Blog
tags:
  - Quality Assurance
---

Quality assurance is used to refer to the process of verifying, both internally to our team and externally to clients, that the product we’ve created meets the pre-defined requirements. 

Some companies don’t have dedicated QA and shift this process to developers. Others wait to test until development is completed. How a company allocates its testing resources depends on their products, the type and size of the markets for those products, the ease of updating the product once released, their budget, etc.

For example, if we design and build web and mobile applications exclusively focused on advancing the legal industry. 

Our products may include legal commitments, we have a greater responsibility to deliver a bug-free experience than if we were building a free game which collects no personal information or money. 

In other words, the greater the chance of someone being adversely affected (financially/legally) by a bug , the more important pre-release testing is to prevent that situation.

Testing plays an important role in ensuring that our web app not only does what it’s required, but does it as smoothly as possible to deliver the maximum value to users.

<h2> Requirement Analysis </h2>

During discovery, our goal is to gain a full understanding of the problem our clients are trying to solve so that we can map out solutions and build an information architecture to serve as the framework for development. 

This process also allows us to determine the scope, priorities, and environment for testing the product.

<h2> Test Plan Documentation </h2>


A test plan is a higher-level document that outlines a project’s general testing procedure and documents the information we’ve gathered about testing during the requirement analysis. 

The specifics of what we cover in a test plan will change depending on the project, but at a minimum, we identify:

<ul>
<li>What we plan to test (e.g., the product/platform/version)</li>
<li>How we’ll test (e.g., any required software needed to accomplish the testing, who will do the testing, how bugs will be reported, what accessibility conformance level to test to)</li>
<li>How we’ll define the outcomes (e.g., what deliverables will come out of the testing, how pass/fail will be defined for each tested issue)</li>
</ul>

A test plan can and should change throughout the project as new information comes in, so that it continues to meet its primary goal of defining the overall test process for everyone involved.

<h2>Test Execution</h2>

In Agile development , we develop and release features in sprints rather than in one fell swoop (or giant disaster) at the end of the engagement. So our active test phase is an iterative process: as features are developed, we test, we send them back as necessary to developers, we test again, we move them forward in the process, new features are developed, repeat.


<h3>QA Tests</h3>

This is what most people typically think of as quality assurance work, although the process of quality assurance really runs through the entire development cycle of a product. 

Prior to development, each feature and its acceptance criteria are defined in a user story, or a brief description of a particular type of user and an action the user wants in order to achieve a goal (example: “As an administrator for a legal referral site, I want to be able to view a list of all the partners who have recently requested access so that I can approve them to use the site”).

Depending on the complexity of the user story, we might write a test case for it which details how to test the feature, any test data necessary, and what constitutes a pass or fail for the feature being tested.

Features that fail, along with any other issues that might come up during the testing, are documented and returned to the developers for another round of coding before they go back to QA.

QA testers need to check that:
<ul>
<li>Feature requirements are met, both functionally and visually.</li>
<li>Cross-browser/device compatibility exists.</li>
<li>Bugs or unexpected outputs are captured and sent back to developers.</li>
</ul>