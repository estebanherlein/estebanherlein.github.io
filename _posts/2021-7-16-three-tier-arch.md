---
title: "Three-Tier Architecture"
categories:
  - Blog
tags:
  - Cloud Design Patterns
---

Three-tier architecture, which separates applications into three logical and physical computing tiers, is the predominant software architecture for traditional client-server applications.

<h2>What is three-tier architecture?</h2>
Three-tier architecture is a well-established software application architecture that organizes applications into three logical and physical computing tiers: the presentation tier, or user interface; the application tier, where data is processed; and the data tier, where the data associated with the application is stored and managed.

The benefit of three-tier architecture is that because each tier runs on its own infrastructure, each tier can be developed simultaneously by a separate development team, and can be updated or scaled as needed without impacting the other tiers.

For decades three-tier architecture was the prevailing architecture for client-server applications. Today, most three-tier applications are targets for modernization, using cloud-native technologies such as containers and microservices, and for migration to the cloud.

<h2>The three tiers in detail</h2>

<h3>Presentation tier</h3>
The presentation tier is the user interface and communication layer of the application, where the end user interacts with the application. Its main purpose is to display information to and collect information from the user. This top-level tier can run on a web browser, as desktop application, or a graphical user interface (GUI), for example. Web presentation tiers are usually developed using HTML, CSS and JavaScript. Desktop applications can be written in a variety of languages depending on the platform.

<h3>Application tier</h3>
The application tier, also known as the logic tier or middle tier, is the heart of the application. In this tier, information collected in the presentation tier is processed - sometimes against other information in the data tier - using business logic, a specific set of business rules. The application tier can also add, delete or modify data in the data tier.

The application tier is typically developed using Python, Java, Perl, PHP or Ruby, and communicates with the data tier using API calls. 

<h3>Data tier</h3>
The data tier, sometimes called database tier, data access tier or back-end, is where the information processed by the application is stored and managed. This can be a relational database management system such as PostgreSQL, MySQL, MariaDB, Oracle, DB2, Informix or Microsoft SQL Server, or in a NoSQL Database server such as Cassandra, CouchDB or MongoDB. 

In a three-tier application, all communication goes through the application tier. The presentation tier and the data tier cannot communicate directly with one another.

<h2>Tier vs. layer</h2>
In discussions of three-tier architecture, layer is often used interchangeably – and mistakenly – for tier, as in 'presentation layer' or 'business logic layer.' 

They aren't the same. A 'layer' refers to a functional division of the software, but a 'tier' refers to a functional division of the software that runs on infrastructure separate from the other divisions. The Contacts app on your phone, for example, is a three-layer application, but a single-tier application, because all three layers run on your phone.

The difference is important, because layers can't offer the same benefits as tiers.

<h2>Benefits of three-tier architecture</h2>
Again, the chief benefit of three-tier architecture its logical and physical separation of functionality. Each tier can run on a separate operating system and server platform - e.g., web server, application server, database server - that best fits its functional requirements. And each tier runs on at least one dedicated server hardware or virtual server, so the services of each tier can be customized and optimized without impact the other tiers. 

Other benefits (compared to single- or two-tier architecture) include:
<ul>
<li>Faster development: Because each tier can be developed simultaneously by different teams, an organization can bring the application to market faster, and programmers can use the latest and best languages and tools for each tier.</li>
<li>Improved scalability: Any tier can be scaled independently of the others as needed.</li>
<li>Improved reliability: An outage in one tier is less likely to impact the availability or performance of the other tiers.</li>
<li>Improved security: Because the presentation tier and data tier can't communicate directly, a well-designed application tier can function as a sort of internal firewall, preventing SQL injections and other malicious exploits.</li>
</ul>