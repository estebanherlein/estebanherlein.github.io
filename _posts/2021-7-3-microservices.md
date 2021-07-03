---
title: "Microservices"
categories:
  - Blog
tags:
  - Devops
  - AWS
---

Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are

<ul>
<li>Highly maintainable and testable</li>
<li>Loosely coupled</li>
<li>Independently deployable</li>
<li>Organized around business capabilities</li>
<li>Owned by a small team</li>
</ul>

The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications. It also enables an organization to evolve its technology stack. 

It is not a silver bullet. It has several drawbacks. Moreover, when using this architecture there are numerous issues that you must address.

In short, the microservice architectural style  is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies. 

<h2>Microservices vs Monolithic</h2>

To start explaining the microservice style it's useful to compare it to the monolithic style: a monolithic application built as a single unit. 

Enterprise Applications are often built in three main parts: a client-side user interface (consisting of HTML pages and javascript running in a browser on the user's machine) a database (consisting of many tables inserted into a common, and usually relational, database management system), and a server-side application. The server-side application will handle HTTP requests, execute domain logic, retrieve and update data from the database, and select and populate HTML views to be sent to the browser. This server-side application is a monolith - a single logical executable. Any changes to the system involve building and deploying a new version of the server-side application. 

A monolithic server is a natural way to approach building such a system. All your logic for handling a request runs in a single process, allowing you to use the basic features of your language to divide up the application into classes, functions, and namespaces. 

With some care, you can run and test the application on a developer's laptop, and use a deployment pipeline to ensure that changes are properly tested and deployed into production. You can horizontally scale the monolith by running many instances behind a load-balancer.

Monolithic applications can be successful, but increasingly people are feeling frustrations with them - especially as more applications are being deployed to the cloud . Change cycles are tied together - a change made to a small part of the application, requires the entire monolith to be rebuilt and deployed. Over time it's often hard to keep a good modular structure, making it harder to keep changes that ought to only affect one module within that module. Scaling requires scaling of the entire application rather than parts of it that require greater resource. 

These frustrations have led to the microservice architectural style: building applications as suites of services. As well as the fact that services are independently deployable and scalable, each service also provides a firm module boundary, even allowing for different services to be written in different programming languages. They can also be managed by different teams .

<h2>Characteristics</h2>

We cannot say there is a formal definition of the microservices architectural style, but we can attempt to describe what we see as common characteristics for architectures that fit the label. As with any definition that outlines common characteristics, not all microservice architectures have all the characteristics, but we do expect that most microservice architectures exhibit most characteristics. 

<ul>
<li>Decentralized Data Management</li>
<li>Organized around Business Capabilities</li>
<li>Componentization via Services</li>
<li>Smart endpoints and dumb pipes</li>
<li>Infrastructure Automation</li>
<li>Designed for failure</li>
</ul>

