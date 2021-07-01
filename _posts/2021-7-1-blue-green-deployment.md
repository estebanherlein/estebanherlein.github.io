---
title: "Blue/Green deployment"
categories:
  - Blog
tags:
  - Devops
  - AWS
---

Blue/green deployment is a technique for releasing applications  by shifting  traffic between two identical  environments running  different versions of the application. Blue/green deployments can mitigate common risks associated with deploying software,such as downtime and rollback capability. This paper provides an overview of the blue/green deployment methodology  and describes techniques customers can implement using Amazon Web Services (AWS) services and tools. 

<h2>Excerpt</h2>

In a traditional approach to application  deployment, you typically fix a failed deployment by re-deploying an older,stable version of the application. Redeployment in traditional  data centers is typically done on the same set of resources due to the cost and effort of provisioning additional resources. Although this approach works, it has many shortcomings. Rollback isn’t easy because it’s implemented by redeployment of an older version from scratch. This process takes time, making the application potentially unavailable for long periods. Even in situations where the application  is only impaired, a rollback is required, which overwrites thefaulty version.

As a result,you have no opportunity to debug the faulty application in place. Applying the principles of agility, scalability, utility consumption, and automation capabilities of the AWS platform can shift the paradigm of application deployment. This enables a better deployment technique called blue/green deployment.

<h2>Blue/Green Deployment Methodology</h2>

Blue/green deployments provide near zero-downtime release and rollback capabilities. The fundamental idea behind blue/green deployment is to shift traffic between two identical  environments that are running  different versions of your application. The blue environment represents the current application version serving production traffic. In parallel, the green environment is staged running a different version of your application. After the green environment is ready and tested, production traffic is redirected from blue to green.

If any problems are identified,  you can roll back by reverting traffic back to the blue environment.

<h2>Benefits</h2>

Traditionally, with in-place upgrades, it was difficult  to validate your new application version in a production deployment while also continuing to run your old version of the application. Blue/green deployments provide a level of isolation between your blue and green application environments. It ensures spinning up a parallel green environment does not affect resources underpinning your blue environment. This isolation reduces your deployment risk.

After you deploy the green environment,you have the opportunity to validate it. You might do that with test traffic before sending production traffic to the green environment, or by using a very small fraction of production traffic, to better reflect real user traffic. This is called canary analysis or canary testing. 

If you discover the green environment is not operating as expected, there is no impact on the blue environment. You can route traffic back to it, minimizing impaired operation or downtime, and limiting the blast radius of impact.

This ability to simply roll traffic back to the still-operating blue environment is a key benefit of blue/green deployments. You can roll back to the blue environment at any time during the deployment process. Impaired operation or downtime is minimized because impact is limited to the window of time between green environment issue detection and shift of traffic back to the blue environment. 

Furthermore, impact is limited to the portion of traffic going to the green environment, not all traffic. If the blast radius of deployment errors is reduced, so is the overall deployment risk.

Blue/green deployments also fit well with continuous integration and continuous deployment (CI/CD) workflows, in many cases limiting their complexity. Your deployment automation  would have to consider fewer dependencies on an existing environment, state, or configuration. Your new green environment gets launched  onto an entirely new set of resources.