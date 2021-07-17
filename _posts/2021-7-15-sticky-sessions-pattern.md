---
title: "Sticky Sessions & SSL"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
  - Cloud Design Patterns
---

One of the realities of three-tier applications is that they are, as a general rule, stateful.

That means they store information between requests and responses that is critical to the operation of the application. Your shopping cart, credentials, status, last page you visited, and which step in a process you’re on are all tidbits that are often stored as part of the “session”. 

The thing is that many apps developed using three-tier frameworks wound up storing that session on the application or web server, and not in a database. That meant that once you were hooked up to a server, you had to keep going back to that server to make sure all your information was available.

Load balancers implemented persistence in a variety of ways, the most popular being cookie-based. Session ids were stored in a cookie that were then used by the load balancer to make sure requests got to the right server, effectively bypassing an algorithmic selection process.

When the use of SSL/TLS became a critical requirement for shoppers to feel secure, the same issues cropped up. SSL/TLS enables a secure session between a client and a specific app server. 

To ensure both sides of the conversation could decrypt and use data exchanged over that connection, the load balancer had to be able to send client requests to the same server it started on. Using the same techniques as enables session-based persistence, load balancers were able to support SSL/TLS-based persistence.

Regardless of the specific type of persistence used, the pattern is the same. If there exists an indicator that a session has already been established, the load balancer honors the existing connection and ensures it remains for the duration of the user session. If there is not, the load balancer selects a resource based on its configuration and algorithms and makes the connection.

This has consequences on capacity planning when selecting a load balancing algorithm. Least connections is a good choice for this scenario as it ensures that no single resource will become overloaded with ongoing sessions while others sit idle. With other algorithms there is a likelihood that a single resource will wind up maintaining many user sessions at the same time, which has a negative impact on performance for all users directed to that server.