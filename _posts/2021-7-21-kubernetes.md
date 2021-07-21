---
title: "Kubernetes"
categories:
  - Blog
tags:
  - Kubernetes
---

If the number of applications grows in our system, it becomes difficult to manage. Docker is not enough, since we need a coordination to do the deployment, the supervision of services, the replacement, the automatic scaling and, ultimately, the administration of the different services that make up our distributed architecture.

In 2014, Kubernetes was publicly released as a learning-based Open Source system using large-scale services.

It was designed to be used anywhere, so you can orchestrate deployments on-premises, in public clouds, and in hybrid deployments.

<h2>What can i do with Kubernetes?</h2>

Even though Kubernetes already offers a lot of functionality, there are always new scenarios that benefit from new features. Application workflows can be optimized to speed up development time. 

A proprietary orchestration solution may be sufficient at first, but often requires robust automation when you need to scale. That is why Kubernetes was designed as a platform: to build an ecosystem of components and tools that make it easier to deploy, scale, and manage applications.

Labels, or Labels, allow users to organize their resources as they wish. Annotations, or Annotations, allow you to assign arbitrary information to a resource to facilitate your workflows and make it easier for administrative tools to inspect status.

Additionally, the Kubernetes Control Plane uses the same APIs that developers and end users use. Users can write their own controllers, such as a scheduler or scheduler, using their own APIs from a command line tool.

This design has allows other systems to be built on top of Kubernetes

Kubernetes is not a mere orchestration system. In fact, Kubernetes eliminates the need to orchestrate. Orchestration is defined as the execution of a defined workflow: do A, then B, and then C.

Kubernetes is made up of a set of independent and combinable control processes that bring the current state to the desired state. It shouldn't matter too much how you get from A to C. No centralized control is required and as a result the system is easier to use, more powerful, robust, resilient and extensible.