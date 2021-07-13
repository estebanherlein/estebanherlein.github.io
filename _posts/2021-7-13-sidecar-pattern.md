---
title: "Sidecar"
categories:
  - Blog
tags:
  - Devops
  - AWS
  - Cloud Design Patterns
---

Peripheral tasks such as Monitoring, Logging etc are critical to most applications and often integrated within them. However, these tasks run alongside the same process as the application which is potentially inefficient and points to improper separation of concerns. Plus, outages caused in these monitoring and logging components could severely impact the entire application functions.

<h2>Solution: Co-locate as Sidecar</h2>
<ol>
<li>Co-locate the set of tasks along with the application but place them in their process or container as a Sidecar</li>
<li>Sidecars are typically small/pluggable components and can be written in different languages</li>
<li>Both application and sidecar are deployed as a single unit, therefore latency is low</li>
<li>The sidecar can be used for modifying how the application container works without having to make any changes to the code</li>
<li>The sidecar is bolted to the application and its lifecycle is dependent on the application</li>
<li>If the sidecar container logic gets complex or tightly coupled with the main application, it may better be integrated with the main application’s code instead</li>
</ol>