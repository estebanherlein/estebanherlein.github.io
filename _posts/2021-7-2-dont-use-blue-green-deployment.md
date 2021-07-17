---
title: "When should you not use Blue/Green deployment?"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
---

As blue/green deployments become more popular, developers and companies are constantly applying the methodology to new and innovative use cases. 

However, there are some common use case patterns where applying this methodology, even if possible, isn’trecommended. These are cases where implementing blue/green deployment introduces too much risk, whether due to workarounds or additional “moving parts” in the deployment process. 

These complexities can introduce additional points of failure, or opportunities for the process to break down, that may negate any risk mitigation benefits blue/green deployments bring in the first place.

<h3>Are your schema changes too complex to decouple from the code changes? Is sharing of data stores not feasible?</h3>

In some scenarios, sharing a data store isn’t desired or feasible. Schema changes are too complex to decouple. Data locality introduces too much performance degradation to the application, as when the blue and green environments are in geographically disparate regions. 

All these situations require a solution where the data store is inside the deployment environment boundary and tightly coupled to the blue and green applications,respectively.

This requires data changes to be synchronized—propagated from the blue environment to the green one, and viceversa. The systems and processes to accomplish this are generally complex and limited by the data consistency requirements of your application.

This means that during the deployment itself,you have to also manage the reliability, scalability and performance of that synchronization workload, adding risk to the deployment.

<h3>Does your application need to be “deployment aware”?</h3>

You have to use feature flags to control the behavior of the application during the blue/green deployment. This is often a consideration in conjunction with the inability to effectively decouple schema and code changes. 

Your application code would execute additional or alternate subroutines during the deployment, to keep data in sync, or perform other deployment-related duties. These routines are enabled and turned off, as the case may be,during the deployment by using configuration flags.

This practice also introduces additional risk and complexity and typically isn’t recommended with blue/green deployments. The goal of blue/green deployments is to achieve immutable infrastructure, where you don’t make changes to your application after it’s deployed, but redeploy altogether. That way,you ensure the same code is operating in a production  setting andin the deployment setting, reducing overall risk factors.

<h3>Does your commercial off-the-shelf (COTS) application come with a predefined update/upgrade process that isn’tblue/green deployment friendly?</h3>

Many commercial software vendors provide their own update and upgrade process for their applications that they have tested and validated for distribution. 

While  vendors are increasingly  adopting the principles of immutable infrastructure and automated deployment, not all software products have those capabilities to date. Working around the vendor’s recommended update and deployment practices to try to implement or simulate a blue/green deployment process may also introduce unnecessary risk that can potentially negate the benefits of this methodology.