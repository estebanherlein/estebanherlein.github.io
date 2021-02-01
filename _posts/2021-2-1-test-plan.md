---
title: "Test Plan"
categories:
  - Blog
tags:
  - Quality Assurance
  - software testing
---

A test plan is a document detailing the objectives, resources, and processes for a specific test for a software or hardware product. The plan typically contains a detailed understanding of the eventual workflow. 

<h2>Characteristics </h2>

A test plan documents the strategy that will be used to verify and ensure that a product or system meets its design specifications and other requirements. A test plan is usually prepared by or with significant input from test engineers.

Depending on the product and the responsibility of the organization to which the test plan applies, a test plan may include a strategy for one or more of the following:

<ul>

<li>Design Verification or Compliance test – to be performed during the development or approval stages of the product, typically on a small sample of units.</li>
<li>Manufacturing or Production test – to be performed during preparation or assembly of the product in an ongoing manner for purposes of performance verification and quality control.</li>
<li>Acceptance or Commissioning test – to be performed at the time of delivery or installation of the product.</li>
<li>Service and Repair test – to be performed as required over the service life of the product.</li>
<li>Regression test – to be performed on an existing operational product, to verify that existing functionality was not negatively affected when other aspects of the environment were changed (e.g., upgrading the platform on which an existing application runs).</li>

</ul>

A complex system may have a high level test plan to address the overall requirements and supporting test plans to address the design details of subsystems and components.

Test plan document formats can be as varied as the products and organizations to which they apply. There are three major elements that should be described in the test plan: Test Coverage, Test Methods, and Test Responsibilities. These are also used in a formal test strategy.

<h3>Test coverage</h3>

Test coverage in the test plan states what requirements will be verified during what stages of the product life. 

Test coverage is derived from design specifications and other requirements, such as safety standards or regulatory codes, where each requirement or specification of the design ideally will have one or more corresponding means of verification. 

Test coverage for different product life stages may overlap, but will not necessarily be exactly the same for all stages. 

For example, some requirements may be verified during Design Verification test, but not repeated during Acceptance test. 

Test coverage also feeds back into the design process, since the product may have to be designed to allow test access.

<h3>Test methods</h3>

Test methods in the test plan state how test coverage will be implemented. 

Test methods may be determined by standards, regulatory agencies, or contractual agreement, or may have to be created new. 

Test methods also specify test equipment to be used in the performance of the tests and establish pass/fail criteria.

Test methods used to verify hardware design requirements can range from very simple steps, such as visual inspection, to elaborate test procedures that are documented separately.

<h3>Test responsibilities </h3>

Test responsibilities include what organizations will perform the test methods and at each stage of the product life.

This allows test organizations to plan, acquire or develop test equipment and other resources necessary to implement the test methods for which they are responsible. Test responsibilities also include what data will be collected and how that data will be stored and reported (often referred to as "deliverables"). 
 
One outcome of a successful test plan should be a record or report of the verification of all design specifications and requirements as agreed upon by all parties. 


<h2>Template</h2>


The format and content of a software test plan vary depending on the processes, standards, and test management tools being implemented. Nevertheless, the following format, which is based on IEEE standard for software test documentation, provides a summary of what a test plan can / should contain.

<h3>Test Plan Identifier:</h3>

    Provide a unique identifier for the document. (Adhere to the Configuration Management System if you have one.)

<h3>Introduction:</h3>

    Provide an overview of the test plan.
    Specify the goals / objectives.
    Specify any constraints.

<h3>References:</h3>

    List the related documents, with links to them if available, including the following:
        Project Plan
        Configuration Management Plan

<h3>Test Items:</h3>

    List the test items (software / products) and their versions.

<h3>Features to be Tested:</h3>

    List the features of the software / product to be tested.
    Provide references to the Requirements and/or Design specifications of the features to be tested.

<h3>Features Not to Be Tested:</h3>

    List the features of the software / product which will not be tested.
    Specify the reasons these features won’t be tested.

<h3>Approach:</h3>

    Mention the overall approach to testing.
    Specify the following:
        Testing levels [if it’s a Master Test Plan],
        Testing types
        Testing methods

<h3>Item Pass / Fail Criteria:</h3>

    Specify the criteria that will be used to determine whether each test item has passed or failed testing.

<h3>Suspension Criteria and Resumption Requirements:</h3>

    Specify criteria to be used to suspend the testing activity.
    Specify what is required before testing can resume.

<h3>Test Deliverables:</h3>

    List test deliverables, and links to them if available, including the following:
        Test Plan (this document itself)
        Test Cases
        Test Scripts
        Test Data
        Defect Reports
        Test Reports

<h3>Test Environment:</h3>

    Specify the properties of test environment: hardware, software, network, etc.
    List any testing or related tools.

<h3>Estimate:</h3>

    Provide a summary of test estimates (cost or effort) and/or provide a link to the detailed estimation.

<h3>Schedule:</h3>

    Provide a summary of the schedule, specifying key test milestones, and/or provide a link to the detailed schedule.

<h3>Staffing and Training Needs:</h3>

    Specify staffing needs by role and required skills.
    Identify training that is necessary to provide those skills, if not already acquired.

<h3>Responsibilities:</h3>

    List the responsibilities of each team / role / individual.

<h3>Risks:</h3>

    List the risks that have been identified.
    Specify the mitigation plan and the contingency plan for each risk.

<h3>Assumptions and Dependencies:</h3>

    List the assumptions that have been made during the preparation of this plan.
    List the dependencies.

<h3>Approvals:</h3>

    Specify the names and roles of all persons who must approve the plan.
    Provide space for signatures and dates. (If the document is to be printed.)
