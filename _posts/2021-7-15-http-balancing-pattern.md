---
title: "Layer 7 (HTTP) Load Balancing"
categories:
  - Blog
tags:
  - Dev-ops
  - Cloud Native
  - Cloud Design Patterns
---

Layer 7 (HTTP) load balancing offers versatility. You can load balance requests based on anything HTTP – including the payload.

Most folks (smartly, in my opinion) restrict their load balancing rules to what can be found in the HTTP header. That includes the host, the HTTP method, content-type, cookies, custom headers, and user-agent, among others.

HTTP load balancing is first about routing and then about load balancing. A typical HTTP load balancing pattern takes the form of route –> distribute. That means that first a decision is made as to which virtual server a request should be directed and then an algorithm selects a resource from the pool supporting that virtual server.

HTTP load balancing enables patterns like API versioning, where the API version is embedded in the URI (or in a custom HTTP header). The load balancer is able to separate out versions and ensure clients are sent to the correct back-end service for execution. This always graceful migration of clients in situations where you can’t force-upgrade.

This type of scalability pattern also supports other scalability patterns like functional decomposition and data partitioning. It’s the most robust, agile scalability pattern in the mix and allows for a vast array of options when scaling out apps and increasingly, microservices.

