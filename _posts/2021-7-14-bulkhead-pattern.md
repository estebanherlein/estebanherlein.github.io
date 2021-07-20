---
title: "Bulkhead"
categories:
  - Blog
tags:
  - Dev-ops
  - Cloud Native
  - Cloud Design Patterns
---

Named after the divided partitions of a ship that help isolate flooding, the bulkhead pattern prevents a single failure within an application from cascading into a total failure. While the implementation of this pattern in the wild isn't always obvious, it is typically found in applications that can operate under some sort of degraded performance.

An application that implements the bulkhead pattern is built with resiliency in mind. While not all operations are possible when email or caching layers go down, with enough foresight and communication to the end user, the application can still be semi-functional.

With isolated application sections that can operate independently of one another, subsystem failures can safely reduce the application's overall functionality without shutting everything down. A good example of the bulkhead pattern in action is any application that can operate in "offline mode."

While most cloud-based applications require an external API to reach their full potential, fault-tolerant clients can operate without the cloud by relying on cached resources and other workarounds to ensure the client is marginally usable.