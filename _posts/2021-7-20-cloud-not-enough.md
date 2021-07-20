---
title: "Why is Cloud Native infrastructure not enough?"
categories:
  - Blog
tags:
  - Cloud Design Patterns
  - Cloud Native
---

Cloud Native applications need both a scalable and available infrastructure layer (e.g. Kubernetes new tab and its ecosystem of tools new tab) and a scalable and available application layer. The infrastructure layer excels in managing, orchestrating, scaling, and ensuring the availability of “empty boxes” of software: the containers.

<b>Managing containers only gets you halfway there. Of equal importance is what you put inside the boxes, and how you stitch them together into a single coherent system.</b>

Kelsey Hightower elegantly described the problem new tab “There’s a ton of effort attempting to "modernize" applications at the infrastructure layer, but without equal investment at the application layer, think frameworks and application servers, we’re only solving half the problem. Even with the best orchestration, logging, security, and debugging infrastructure, code has to be written to make the best use of it.”

Both the infrastructure and application layers are equally important and need to work in concert to deliver a holistic and consistent user experience. They manage resilience and scalability at distinct granularity levels in the application stack. 

The application layer allows for fine-grained entity-level management of resilience and scalability, working closely with the application code, while the infrastructure layer is more coarse-grained. 

In a way, the infrastructure layer acts as a “Cloud OS”, where the containers are similar to processes, each with a certain level of isolation, resource management, and resiliency. 

The “Cloud OS” provides basic features such as persistence, I/O, communication, monitoring, and deployment. The application logic lives within these containers utilizing the services provided by the “Cloud OS” but still must be properly designed and put together to deliver a complete end-user application.

<h3>Cloud Native applications are more efficient. </h3>
If cloud infrastructure is about making more efficient use of infrastructure resources like machines, networks, and operating systems, then Cloud Native applications are about making more efficient use of application resources like data, threads, and CPUs.

<h3>Cloud Native applications are more robust. </h3>
If cloud infrastructure provides mechanisms to restart failing nodes, re-route failing requests, and provision new infrastructure capacity, Cloud Native applications provide modern and improved mechanisms to handle application lifecycle changes, intelligently recover from failed requests, and accommodate service and topology changes.

<h3>Cloud Native applications are more manageable, adaptable, and agile. </h3>
If cloud infrastructure provides mechanisms for managing ever-changing physical infrastructure, Cloud Native applications provide clear management, tooling, insights, and operational support for changes to routing, sharding, threading, topology, and more.

