---
title: "Serverless architecture"
categories:
  - Blog
tags:
  - Dev-ops
  - Cloud Native
---

Serverless architectures are application designs that incorporate third-party “Backend as a Service” (BaaS) services, and/or that include custom code run in managed, ephemeral containers on a “Functions as a Service” (FaaS) platform.

By using these ideas, and related ones like single-page applications, such architectures remove much of the need for a traditional always-on server component. Serverless architectures may benefit from significantly reduced operational cost, complexity, and engineering lead time, at a cost of increased reliance on vendor dependencies and comparatively immature supporting services. 

BaaS and FaaS are related in their operational attributes (e.g., no resource management) and are frequently used together. The large cloud vendors all have “Serverless portfolios” that include both BaaS and FaaS products

<h2>What is Serverless?</h2>

Let’s think about a traditional three-tier client-oriented system with server-side logic. A good example is a typical ecommerce app—dare I say an online pet store?

Traditionally, the architecture will be a client side app that runs on a browser, a server side app and a database.

With this architecture the client can be relatively unintelligent, with much of the logic in the system—authentication, page navigation, searching, transactions—implemented by the server application.

With a Serverless architecture the server side of the architecture is replaced by third party services. Stepping back a little, this example demonstrates a very important point about Serverless architectures.

In the original version, all flow, control, and security was managed by the central server application. In the Serverless version there is no central arbiter of these concerns. Instead we see a preference for choreography over orchestration, with each component playing a more architecturally aware role—an idea also common in a microservices approach.

There are many benefits to such an approach. Systems built this way are often “more flexible and amenable to change,” both as a whole and through independent updates to components; there is better division of concerns; and there are also some fascinating cost benefits.

Of course, such a design is a trade-off: it requires better distributed monitoring, and we rely more significantly on the security capabilities of the underlying platform. More fundamentally, there are a greater number of moving pieces to get our heads around than there are with the monolithic application we had originally. Whether the benefits of flexibility and cost are worth the added complexity of multiple backend components is very context dependent.

