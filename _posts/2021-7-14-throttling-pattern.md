---
title: "Throttling"
categories:
  - Blog
tags:
  - Devops
  - AWS
  - Cloud Design Patterns
---

An alternative design pattern to QBLL is the throttling pattern, which centers on the concept of the "noisy neighbor" problem. 

While the QBLL pattern offloads excess workloads to a queue for more manageable processing, the throttling pattern sets and forces limits on how frequently a single client can use a service or endpoint to keep one "noisy neighbor" from negatively impacting the system for everyone. 

The throttling pattern can also supplement to the QBLL pattern, which allows for the managed processing of excess workloads and ensures the queue depth doesn't become too full.

Let's say that the API endpoint could originally handle about 100 requests per minute before the heavy work was offloaded to a queue, while an API can support a maximum throughput of about 10,000 requests per minute. Ten thousand is a huge jump from 100, but the queue will still only be able to support about 100 requests per minute without any noticeable impact on the end user. 

<b>This means that 1,000 API requests would take about 10 minutes to fully process, and 10,000 API requests would take almost two hours.</b>

In a system with evenly distributed requests, every user would experience slower processing equally, but if a single user sends all 10,000 requests, then all other users will experience a two-hour delay before their workloads even get started. A throttling schema that limits all users to 1,000 requests per second would ensure that no single user could monopolize application resources at the expense of any other user.