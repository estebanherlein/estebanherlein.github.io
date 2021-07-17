---
title: "Global Server Load Balancing (GSLB)"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
  - Cloud Design Patterns
---

GSLB is the means by which you ensure that if one data center (cloud or traditional) isn’t responding, you can find another. GSLB can be applied at the domain or host level. So you can use it to switch example.com between locations as well as api.example.com.

<h2>Usage</h2>

At its most basic, GSLB uses rudimentary, DNS-based load balancing. That means it’s got a list of IP addresses associated with a domain or host, and if the first one isn’t available, requests are directed to the second in the list – or third, or fourth, and so on.

There are two steps to this process:
<ol>
<li>Ask the global load balancer for the appropriate IP address. This is the negative always associated with GSLB – if you’ve asked in the last 15 minutes or  whatever the current TTL is for the IP address of cheese.com, you get the last response you received. So if that site went down in that time, you’re not going to get connected.</li>
<li>Make the request to the IP address of the site returned by the GSLB inquiry. This often ends up being a local load balancer which uses its own algorithms and decision-making process to get the request to the appropriate resource.</li>
</ol>

There’s generally no intelligence to the decision made in step 1; it is strictly based on whether or not a given site is responding. Still, this is how you can use multiple locations – cloud, hosting provider, on-premises – to ensure availability. By strategically choosing locations in diverse geographical areas, you can avoid the impact of natural disasters or Internet outages.

But that’s more of a DR (disaster recovery) or BC (business continuity) scenario. 

There are others that take advantage of smarter GSLB application services such as geolocation and application performance. So if the app at Site A is performing poorly, maybe you want to send visitors to Site B until the issue is resolved. Or perhaps you want to direct users to the geographically closest location to help improve performance (because the speed of light is still a rule and distance matters to app performance).