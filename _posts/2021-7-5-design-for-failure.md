---
title: "Design for failure"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
---

The concept of “Design for Failure” is often used to describe the approach that assumes that there will be a hardware or system failure somewhere, sometime – and instead of architecting for hardware and server clustering and availability, to design applications so that recovery can be performed quickly.

A consequence of using services as components, is that applications need to be designed so that they can tolerate the failure of services. Any service call could fail due to unavailability of the supplier, the client has to respond to this as gracefully as possible. 

This is a disadvantage compared to a monolithic design as it introduces additional complexity to handle it. The consequence is that microservice teams constantly reflect on how service failures affect the user experience. 

<b>Netflix's Simian Army induces failures of services and even datacenters during the working day to test both the application's resilience and monitoring.</b>

This kind of automated testing in production would be enough to give most operation groups the kind of shivers usually preceding a week off work. This isn't to say that monolithic architectural styles aren't capable of sophisticated monitoring setups - it's just less common.

Since services can fail at any time, it's important to be able to detect the failures quickly and, if possible, automatically restore service. Microservice applications put a lot of emphasis on real-time monitoring of the application, checking both architectural elements (how many requests per second is the database getting) and business relevant metrics (such as how many orders per minute are received). Semantic monitoring can provide an early warning system of something going wrong that triggers development teams to follow up and investigate.

This is particularly important to a microservices architecture because the microservice preference towards choreography and event collaboration leads to emergent behavior. While many pundits praise the value of serendipitous emergence, the truth is that emergent behavior can sometimes be a bad thing. Monitoring is vital to spot bad emergent behavior quickly so it can be fixed.

Monoliths can be built to be as transparent as a microservice - in fact, they should be. The difference is that you absolutely need to know when services running in different processes are disconnected. With libraries within the same process this kind of transparency is less likely to be useful.

Microservice teams would expect to see sophisticated monitoring and logging setups for each individual service such as dashboards showing up/down status and a variety of operational and business relevant metrics. Details on circuit breaker status, current throughput and latency are other examples we often encounter in the wild.

<h2>How can this be traslated to AWS? </h2>

In the approach to modernise applications to take advantage of Cloud – there are considerations to take into account the re-design of the application to support underlying failures in the Cloud subsystems. This means;
<ul>
<li>Each application component must be deployed across redundant cloud components, ideally with minimal or no common points of failure</li>
<li>Each application component should be partition tolerant—in other words, it should be able to survive network latency (or loss of communication) among the nodes that support that component without freezing, crashing or hanging (store/cache and recover)</li>
<li>Distribution of components across availability zones will be required to ensure availability of components</li>
<li>However, where latency is an issue and inter-dependence is required, plan for close location of resources</li>
<li>Instead of building completely new architecture for DR, create a Production system with AZ distribution, leveraging the inherent cloud capability as available.</li>
</ul>
