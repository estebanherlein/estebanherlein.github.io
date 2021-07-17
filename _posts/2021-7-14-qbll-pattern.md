---
title: "Queue-based load leveling"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
  - Cloud Design Patterns
---

Queue-based load leveling (QBLL) is a common cloud design pattern that helps with scale problems as an application grows. Rather than performing complex operations at request time -- which adds latency to user-exposed functionality -- these operations are instead added to a queue that is tuned to execute a more manageable number of requests within a given time period. 

This design pattern is most valuable in systems where there are many operations that do not need to show immediate results, such as sending emails or calculating aggregate values.

For example, take an API endpoint that must make retroactive changes to a large dataset whenever it is executed. While this endpoint was built with a certain threshold of traffic in mind, a large burst in requests or a rapid growth in user adoption could negatively affect the latency of the application.

By offloading this functionality to a queue-based load leveling system, the application infrastructure can more easily withstand the increased throughput by processing a fixed number of operations at a time.