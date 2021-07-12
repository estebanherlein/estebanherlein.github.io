---
title: "Circuit Breaker"
categories:
  - Blog
tags:
  - Devops
  - AWS
  - Cloud Design Patterns
---

There are situations where failures can be caused by unexpected situations and take relatively longer to fix. Retry or waiting for the request to timeout may not be the best option as it may cause further cascading issues such as resource contention and/or blocked threads.

<h2>Solution — Fail fast</h2>

Prevent the application from retrying an operation likely to fail:

<ol>
<li>A circuit breaker acts as a proxy that monitors recent failures of an operation</li>
<li>The proxy maintains a count of failures and if it crosses the set threshold, it’s placed in an Open state</li>
<li>In the Open state, the request fails immediately and is handled appropriately by the application</li>
<li>However, limited requests are still allowed to pass through to check if the operation is still failing or has been successful (fixed)</li>
<li>If the operation continues to return failures, the Open state continues</li>
<li>If the operation was successful, it is assumed the issue has been fixed and the circuit breaker switches to Closed state</li>
</ol>
<b>Error and failure handling in this pattern requires careful consideration to create an acceptable end-user experience</b>