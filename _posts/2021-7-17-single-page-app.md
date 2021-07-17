---
title: "Single Page Application"
categories:
  - Blog
tags:
  - Cloud Design Patterns
---

SPA stands for single page application. Strictly speaking, it’s a single page website which dynamically updates in a client’s browser. A more general understanding of an SPA (sometimes referred to as SPI, or single page interface) is a comprehensive approach to web development. 

<h2> What does this approach involve?</h2>

These are sites are generated on the server side. Despite how convenient this is for developers (each request creates a new page from a clean slate), these sites can sometimes be a real headache for clients. Inconveniences clients may encounter include:
<ul>
<li>Even though some frameworks let you return a form with data previously entered by the client, pages may have to be reloaded to be validated.</li>
<li>Generating pages on the server side generates major workloads.</li>
</ul>

The usual solution to that problems still involves generating the site on the server side, but also executing JavaScripts on the client’s side.

Scripts can be used to perform actions like validating a form before it is sent to the server. At first glance, this may seem like a feasible solution, but it has its drawbacks:
<ul>
<li>If frontend and backend functions used to be clearly divided (the backend taking care of view generation and logic, and the frontend the display), then the logic will be cloned on the frontend, which is hardly a practical architecture.</li>
<li>The code responsible for view generation must be constantly cloned, which causes problems: copypasta, divergences in markup, broken selectors, difficulties maintaining code, etc.</li>
</ul>

These are problems we can live with of course, but the SPA approach is much more effective in most cases.

With this approach, a site is understood not as a set of different pages, but a set of conditions for one HTML page. When the conditions change, new content is downloaded asynchronously without reloading the page.

<b>An SPA isn’t a site in the traditional sense, but an application running on the client-side browser.</b>

This is why from the user’s point of view there are hardly any problems with speed, even when the Internet connection is slow or unstable (like when viewing a page from a mobile device). Since the server doesn’t send the client markup text, but data (mainly in JSON format) and only a small amount of it, sites can load faster.

