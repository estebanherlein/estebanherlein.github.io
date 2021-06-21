---
title: "Infrastructure as code"
categories:
  - Blog
tags:
  - Devops
  - AWS
---

Infrastructure as Code (IaC) is the management of infrastructure (networks, virtual machines, load balancers, and connection topology) in a descriptive model, using the same versioning as DevOps team uses for source code.

Like the principle that the same source code generates the same binary, an IaC model generates the same environment every time it is applied. IaC is a key DevOps practice and is used in conjunction with continuous delivery.

<h2>What does IaC mean ? </h2>

Infrastructure managers have often performed such provisioning manually.  

The manual processes have certain disadvantages, including:

Higher cost because they require human capital that could otherwise go toward more important business needs. 
Inconsistency due to human error,  leading to deviations from configuration standards.
Lack of agility by limiting the speed at which your organization can release new versions of services in response to customer needs and market drivers. 
Difficulty in attaining and maintaining compliance to corporate or industry standards due to the absence of repeatable processes. 


Infrastructure as Code addresses these deficiencies by bringing automation to the provisioning process. Rather than relying on manually performed steps, both administrators and developers can instantiate infrastructure using configuration files. Infrastructure as Code treats these configuration files as software code. 

These files can be used to produce a set of artifacts, namely the compute, storage, network, and application services that comprise an operating environment. 

Infrastructure as Code eliminates configuration drift through automation,  thereby increasing the speed and agility of infrastructure deployments.

<h2>IaC solves real problems</h2>

Infrastructure as Code evolved to solve the problem of <b>environment drift</b> in the release pipeline. Without IaC, teams must maintain the settings of individual deployment environments.

Over time, each environment becomes a snowflake, that is, a unique configuration that cannot be reproduced automatically. 

Inconsistency among environments leads to issues during deployments. With snowflakes, administration and maintenance of infrastructure involves manual processes which were hard to track and contributed to errors.

<b>Idempotence</b> is a principle of Infrastructure as Code. Idempotence is the property that a deployment command always sets the target environment into the same configuration, regardless of the environment's starting state. Idempotency is achieved by either automatically configuring an existing target or by discarding the existing target and recreating a fresh environment.

Accordingly, with IaC, teams make changes to the environment description and version the configuration model, which is typically in well-documented code formats such as JSON. The release pipeline executes the model to configure target environments. <b>If the team needs to make changes, they edit the source, not the target</b>.