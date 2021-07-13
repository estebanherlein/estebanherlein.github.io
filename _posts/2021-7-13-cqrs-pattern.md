---
title: "Command and Query Responsibility Segregation (CQRS)"
categories:
  - Blog
tags:
  - Devops
  - AWS
  - Cloud Design Patterns
---

Traditionally, people interact with Information Systems through a CRUD data store. Read and Write Data models are often the same. As the complexity of the application increases, multiple representations of the information are created, all referring to one common data (conceptual) model. This can lead to data/resource contentions, performance slowdown and in some cases, security issues.

<h2>Solution: Separate the Read and Write models</h2>
<ul>
<li>This can be done by creating separate schemas or different databases for the Read and Write operations. All reads from a single data store and all Writes/Updates to a separate data store</li>
<li>Creating separate databases provides additional isolation that helps with scalability and performance</li>
<li>The Write databases can be relational while Read databases can be No SQL document-based</li>
<li>This approach not only provides separation of concerns but also allows each data store to independently scale based on its workload</li>
<li>The important consideration in this model is to maintain sync between the Read and Write stores. This is typically achieved through publishing events from the Write store and consumed by the Read store</li>
</ul>