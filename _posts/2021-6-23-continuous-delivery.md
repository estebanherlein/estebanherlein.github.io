---
title: "Continuous Delivery"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
---
One misconception about continuous delivery is that it means every change committed is applied to production immediately after passing automated tests. However, the point of continuous deliveryis not to apply every change to production immediately, but to ensure that every change is ready to go to production.

Before deploying a change to production, you can implement adecision process to ensure that the production deployment is authorized and audited. This decision can be made by a person and then executedby the tooling. Using continuous delivery the decision to go live becomes a business decision, not a technical one.

The technical validation happens on every commit. Rolling out a change to production is not a disruptive event. Deployment doesn’t require the technical team to stop working on the next set of changes, and it doesn’t need a project plan, handover documentation, or a maintenance window. Deployment becomes a repeatable process that has been carried out and proven multiple times in testing environments.

<h2>Benefits of Continuous Delivery </h2>

CD provides numerous benefits for your software development team including automating the process, improving developer productivity, improving code quality, and delivering updates to your customers faster.


<h3>Automate the Software Release Process</h3>

CD provides a method for your team to check in code that is automatically built, tested, and prepared for release to production so that your software delivery isefficient, resilient, rapid,and secure.

<h3>Improve Developer Productivity</h3>

CD practices help your team’s productivity by freeing developers from manual tasks, untangling complex dependencies, and returningfocus to delivering new features in software.Instead of integrating their code with other parts of the business and spending cycles on how to deploy this code to a platform, developers canfocus on coding logic that delivers the features you need.

<h3>Improve Code Quality</h3>

CD can help you discover and address bugs early in the delivery processbefore they grow into larger problems later. Your team can easily perform additional types of code tests because the entire process has been automated. With the discipline of more testing more frequently, teams can iterate faster with immediate feedback on the impact of changes. This enables teams to drive quality code with a high assurance of stability and security. Developers will know through immediate feedback whether the new code works and whether any breaking changes or bugs were introduced. Mistakes caught early on in the development process are the easiest to fix.

<h3>Deliver Updates Faster</h3>

CD helps your team deliver updates to customers quickly and frequently.When CI/CD is implemented, the velocity of the entire team, including the release of features and bug fixes,is increased.Enterprises canrespond faster to market changes, security challenges, customer needs, and cost pressures.For example, if a new security feature is required, your team can implementCI/CD with automated testing to introduce the fix quickly and reliably to production systems with high confidence.What used to take weeks and months can now be done in days or even hours