---
title: "Asynchronous Request and Reply"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
  - Cloud Design Patterns
---

When we talk about Cloud Applications, Micro-services often come to mind. This is an architecture style where multiple micro-services i.e. remote APIs or third-party services are composed to perform dedicated functions to provide a particular functionality to a client application.

In such a setup, synchronously processing the client request before all the back end work is completed may not always be feasible. This is especially true in the case of long-running processes. Furthermore, latency also becomes a consideration when the response to the client needs to be a few milliseconds.

<h2>Solution: Asynchronous Processing (HTTP Polling or Event Notification)</h2>
<ul>
<li>The client makes an API request
<li>The application now offloads the work to another back end service or message queue</li>
<li>The client can poll for the resource/process status using an HTTP GET (HTTP Polling) at regular intervals as appropriate for the client application</li>
<li>The status API returns “In-Progress” indicating the back end process is still running</li>
<li>Once the process completes, the status will return the required output or another reference to the resource</li>
<li>The application can also push event notifications once the process is complete without the need for the client to poll repeatedly</li>
</ul>