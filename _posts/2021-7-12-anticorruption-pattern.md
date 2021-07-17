---
title: "Anti-Corruption Layer pattern"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
  - Cloud Design Patterns
---

Implement a façade or adapter layer between different subsystems that don’t share the same semantics. This layer translates requests that one subsystem makes to the other subsystem. Use this pattern to ensure that an application’s design is not limited by dependencies on outside subsystems. This pattern was first described by Eric Evans in Domain-Driven Design.