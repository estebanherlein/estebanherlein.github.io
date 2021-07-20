---
title: "Testing Stages"
categories:
  - Blog
tags:
  - Dev-ops
  - Cloud Native
---

The three CI/CD teams should incorporate testing into the software development lifecycle at the different stages of the CI/CD pipeline. 

Overall, testing should start as early as possible.

Unit tests are both the fastest to run and the least expensive. Therefore, unit tests should make up the bulk of your testing strategy. A good rule of thumb is about 70 percent. Unit tests should have near-complete code coverage because bugs caught in this phase can be fixed quickly and cheaply. 

Service, component, and integration tests require detailed environments and, therefore, are more costly in infrastructure requirements and slower to run. 

Performance and compliance tests are the next level. They require production-quality environments and are more expensive yet. 

UI and user acceptance tests are require production-quality environments as well. All of these tests are part of a complete strategy to assure high-quality software. However,for speed of development,emphasis is on the number of tests and the coverage in the bottom half of the pyramid. 

<h2>Testing Stages</h2>

<h3>Setting up the Source</h3>

At the beginning of the project it’s essential to set up a source where you can store your raw code, configuration and schema changes. In the source stage, choose a source code repository such as one hosted inGitHub or AWS CodeCommit.

<h3>Setting Upand Executing Builds</h3>

Build automation is essential to the CI process. When setting up build automation, the first task is to choose the right build tool. There are many build tools, such as Ant, Maven,and Gradle for Java; Make for C/C++; Grunt for JavaScript;and Rake for Ruby. The build tool that will work best for you will depend on the programming language of your project and the skill set of your team. 

After you choose the build tool, all the dependencies need to be clearly defined in the build scripts, along with the build steps. It’s also a best practice to version the final build artifacts, which makes it easier to deploy and to keep track of issues.

In the build stage, the buildtools will take as input any change to the source code repository, build the software,and run the following types of tests: 

<b>Unit Testing</b>– Tests a specific section of code to ensure the code does what it is expected to do. The unit testing is performed by software developers during the development phase. At this stage,a static code analysis, data flow analysis, code coverage,and other software verification processes can be applied.

<b>Static Code Analysis</b> –This test is performed without actually executing the application after the build and unit testing. This analysis can help find coding errors and security holes, it also can ensure conformance to coding guidelines.

<h3>Staging</h3>

In the staging phase, full environments are created that mirror the eventual production environment. The following tests are performed: 

<b>Integration Testing</b>– Verifies the interfaces between components against software design. Integration testing is an iterative process and facilitates building robust interfaces and system integrity.

<b>Component Testing</b>– Tests message passing between various components and their outcomes. A key goal of this testing could be idempotency in component testing. Tests can include extremely large data volumes, or edge situations and abnormal inputs.

<b>System Testing</b>– Tests the system end-to-end and verifies if the software satisfies the business requirement. This might include testing the UI, API, backend logic, and endstate.

<b>Performance Testing</b>– Determines the responsiveness and stability of a systemas it performs under a particular workload. Performance testing also is used to investigate, measure, validate, or verify other quality attributes of the system, such as scalability, reliability, and resource usage. Types of performance tests might include load tests, stress tests, and spike tests. Performance tests are used for benchmarking against predefined criteria.

<b>Compliance Testing</b>–Checks whether the code change complies with the requirements of a non-functional specification and/or regulations. It determines if you are implementing and meeting the defined standards. 

<b>User Acceptance Testing</b>– Validates the end-to-end business flow. This testing is executed by an end-user in a staging environment and confirms whether the system meets the requirements of the requirement specification. Typically, customers employ alpha and beta testing methodologies at this stage.

<h3>Production</h3>

Finally, after passing the previous tests, the staging phase is repeated in a production environment. In this phase,a final Canary test can be completed by deploying the new code only on a small subset of servers or even one server, or one Region before deploying code to the entire production environment. Specifics on how to safely deploy to production are covered in the Deployment Methods section.