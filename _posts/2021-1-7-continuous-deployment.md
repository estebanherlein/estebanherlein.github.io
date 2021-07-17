---
title: "Continuous Deployment"
categories:
  - Blog
tags:
  - Software Testing
  - Dev-ops
---


Continuous Deployment (CD) is a software release process that uses automated testing to validate if changes to a codebase are correct and stable for immediate autonomous deployment to a production environment.

The software release cycle has evolved over time. The legacy process of moving code from one machine to another and checking if it works as expected used to be  an error prone and resource-heavy process. Now, tools can automate this entire deployment process, which allow engineering organizations to focus on core business needs instead of infrastructure overhead.

Continuous deployment can be a powerful tool for modern engineering organizations. Deployment is the final step of the overall ‘continuous pipeline’ that consists of integration, delivery, and deployment. The true experience of continuous deployment is automation to the level at which code is deployed to production, tested for correctness, and automatically reverted when wrong, or accepted if correct.


<h2>Advantages and disadvantages of continuous deployment</h2>

Continuous deployment offers incredible productivity benefits for modern software businesses. It allows businesses to respond to changing market demands and teams to rapidly deploy and validate new ideas and features. 

With a continuous deployment pipeline in place, teams can react to customer feedback in real time. If customers submit bug reports or requests for features, teams can immediately respond and deploy responses. If the team has an idea for a new product or feature, it can be in the hands of customers as soon as the code has been pushed.

<b>The benefits of continuous deployment, however, come at a price. While the return on investment is high, a continuous deployment pipeline can be an expensive initial engineering cost. </b> 

In addition to the initial cost, on going engineering maintenance may be required to ensure the pipeline continues to run fast and smooth.


<h2>Continuous Deployment Tools</h2>

Establishing continuous deployment requires substantial engineering investment. The following is a list of tools that are needed to build a continuous deployment pipeline.

<h3>Automated testing</h3>

The most critical dependency for continuous deployment is automated testing. In fact, the entire chain of continuous integration, delivery and deployment depends on it. Automated tests are used to prevent any regressions when new code is introduced and can replace manual reviews of new code changes. 

<h3>Rolling deployments</h3>

The distinguishing feature between continuous deployment and delivery is the automated step of activating new code within a live environment. A continuous deployment pipeline must be able to undo a deployment in the event that  bugs or breaking changes are deployed. Automated rolling deployment tools like green-blue deploys are a requirement for proper continuous deployment.

<h3>Monitoring and alerts</h3>

A robust continuous deployment pipeline will have real time monitoring and alerts. These tools provide visibility into the health of the overall system and into the before and after state of new code deployments. Additionally alerts can be used to trigger a rolling deployment ‘undo’ to revert a failed deploy.

<h2>Continuous Deployment Best Practices</h2>

Once a continuous deployment pipeline is established, ongoing maintenance and participation is required from the engineering team to ensure its success. The following best practices and behaviors will ensure an engineering team is getting the most value out of a continuous deployment pipeline.

<h3>Test-driven development</h3>

Test-driven development is the practice of defining a behavior spec for new software features before development begins. Once the spec is defined developers will then write automated tests that match the spec. Finally, the actual deliverable code is written to satisfy the test cases and match the spec. This process ensures that all new code is covered with automated testing up front. The alternative to this is delivering the code first and then producing test coverage after. This leaves opportunity for gaps between the expected spec behavior and the produced code.

<h3>Single method of deployment</h3>

Once a continuous deployment pipeline is in place, it’s critical that it is the only method of deployment. Developers should not be manually copying code to production or live editing things. Manual changes external to the CD pipeline will desync the deployment history, breaking the CD flow.

<h3>Containerization</h3>

Containerizing a software application ensures that it behaves the same across any machine it is deployed on. This eliminates a whole class of issues where software works on one machine but behaves differently on another. Containers can be integrated as part of the CD pipeline so that the code behaves the same on a developer’s machine as it does during automated testing, and production deployment.

