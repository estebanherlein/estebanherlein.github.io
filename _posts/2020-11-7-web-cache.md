---
title: "Web cache"
categories:
  - Blog
tags:
  - Networking theory
---

A device for the temporary storage (caching) of Web documents (such as Web pages, images, and other types of Web multimedia) to reduce server lag.

A Web cache system stores copies of documents passing through it; subsequent requests may be satisfied from the cache if certain conditions are met. 
 
A Web cache system can refer either to a physical device or to a program.



<h1>Cache types</h1>

There are two main types of web caches (as viewed from the direction of delivery): 

<ol>
<li><b>Forward position client-side)</b>
<br>
A forward cache is a cache outside the Web server's network (on the client computer, in an ISP or within a corporate network).
<br>
A network-aware forward cache is just like a forward cache but only caches heavily accessed items.
<br>
A client, such as a Web browser, can also store Web content. For example, if the back button is pressed, the locally cached version of a page may be displayed instead of a new request being sent to the Web server. A Web proxy sitting between the client and the server can evaluate HTTP headers and choose whether to store Web content. </li>

<li><b>Reverse position (content provider or web-server side)</b>
<br>

A reverse cache sits in front of one or more Web servers and Web applications, accelerating requests from the Internet, reducing peak Web server load. 
<br>
A content delivery network (CDN) can retain copies of Web content at various points throughout a network. 
<br>
A search engine may also cache a website; it provides a way of retrieving information from websites that have recently gone down or a way of retrieving data more quickly than by clicking the direct link. Google, for instance, does so. Links to cached contents may be found in Google search results.  </li>

</ol>

<h1> Cache control </h1>

HTTP defines three basic mechanisms for controlling caches: freshness, validation, and invalidation.

<ul>
<li><b>Freshness</b>
<br>
    allows a response to be used without re-checking it on the origin server, and can be controlled by both the server and the client. For example, the Expires response header gives a date when the document becomes stale, and the Cache-Control: max-age directive tells the cache how many seconds the response is fresh for.</li>
<li><b>Validation</b>
<br>
    can be used to check whether a cached response is still good after it becomes stale. For example, if the response has a Last-Modified header, a cache can make a conditional request using the If-Modified-Since header to see if it has changed. The ETag (entity tag) mechanism also allows for both strong and weak validation.</li>
<li><b>Invalidation</b>
<br>
    is usually a side effect of another request that passes through the cache. For example, if a URL associated with a cached response subsequently gets a POST, PUT or DELETE request, the cached response will be invalidated.</li>

</ul>
Many CDNs and manufacturers of network equipment have replaced this standard HTTP cache control with dynamic caching. 

<h1> Dynamic cache control </h1>

The purpose of dynamic cache control is to increase the cache-hit ratio of a website, which is the rate between requests served by the cache and those served by the normal server.

Due to the dynamic nature of web 2.0 websites, it is difficult to use static web caching. The reason is that dynamic sites, per definition, have personalized content for different users and regions. 

For example, mobile users may see different content from what desktop users may see, and registered users may need to see different content from what anonymous users see. Even among registered users, content may vary widely, often example being social media websites.

Static caching of dynamic user-specific pages introduces a potential risk of serving irrelevant content or 3rd party's content to the wrong users, if the identifier allowing the caching system to differentiate content, the URL/GET-request, isn't correctly varied by appending user-specific tokens/keys to it.

Dynamic cache control has more options to configure caching, such as cookie-based cache control, that allows serving content from cache based on the presence or lack of specific cookies. 

A cookie stores the unique identifier-key of a logged-in user on their device and it's already implemented for authenticating users upon execution of any page that opens a session, in a dynamic caching system, the caches are referred to by URL as well as the cookie keys, allowing to simply enable serving of default caches to anonymous users and personalized caches to logged-in users (without forcing you to modify the code, to make it append additional user identifiers to the URL, like in a static caching system). 