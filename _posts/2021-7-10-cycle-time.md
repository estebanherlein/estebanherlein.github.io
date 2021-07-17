---
title: "Cycle time"
categories:
  - Blog
tags:
  - Dev-ops
  - AWS
---


Imagine the simplest change to your production system that you can think of. You want it to be so simple that you can ignore the variable cost of development.

Now imagine that change going through all of the normal processes to get it prioritized, scheduled, defined, implemented, tested, verified, documented, and deployed into production—every step that a change to production would normally take. The time that it takes to complete all of those steps, plus the time that the change spends waiting between steps, is your cycle time. 

<b>This is a great proxy term for measuring the time from "idea" to "valuable software in the hands of users."</b>

If you take an empirical, iterative approach to reducing cycle time, then pretty much all of the benefits of agile development, lean thinking, DevOps, and continuous delivery practice will fall out as a natural consequence.


Think about the consequences of being able to do that:

<ul>
<li>If you have a cycle time of less than an hour, you can't afford the communications overhead of large teams. You need compact, cross-functional, efficient teams.</li>
<li>You can't afford the hand-offs that are implicit in siloed teams. If you divide your development effort up into technical specialisms, you will be too slow. You need cross-functional collaborative teams to ensure a continual flow of changes.</li>
<li>You can't rely on manual regression testing. You need a great story on automated testing. Human beings are too slow, too inefficient, too error prone, and too expensive.</li>
<li>You can't rely on manual configuration and management of your test and production environments. You need to automate the configuration management, automate deployment, and develop a good story on "infrastructure as code."</li>
<li>You can't have a cycle time of less than an hour and have hand-offs between Dev and Ops.</li>
<li>You can't have a cycle time of less than an hour if your business can't maintain a constant smooth flow of ideas.</li>
<li>You have to be very good at a lot of aspects of software development to achieve this kind of cycle time.</li>
</ul>

If you can confidently evaluate your changes to the point where you are happy to release changes into production in under an hour, without any further work, you are doing very well!

<h2>Optimizing for short cycle time drives good behaviors</h2>

Simply striving to improve your cycle time will help you (and, in some sense, force you) to improve your development process, culture, and technology. It will force you to address impediments and inefficiencies that get in your way. And the best part is that I've never seen this metric encourage bad behaviors.

Many people are nervous that reducing cycle time will reduce quality. In my experience, and in countless experiences I've heard about throughout the industry, I've found that the reverse is true.

What happens is that by reducing cycle time you reduce batch-size. By reducing batch-size, you reduce the risk of each change (ever heard of colleagues warning against "big bang" releases?). Each change becomes simpler and lower-risk. 66% of organizations that claim to practice continuous delivery say that quality goes up, not down (according to the 2015 CA Technologies DevOps Survey).

<h2>Smaller releases are low-risk and lessen the cognitive load</h2>

If you have a short cycle time, you can, and will, release changes in small batches. Think about each change. Each change will be small, simple, and easy to understand.

If you release only once every few months, then you will be storing up lots of changes. If you imagine that each change has a small amount of risk associated with it, then the total risk for any release is going to be the sum of all of those risks.

Except it's worse than that. In addition, there is going to be a compounding effect. What if my change interacts with your change? There is an additional risk associated with the interaction between changes. These risks will grow exponentially as more changes are combined. The more changes that are released together, the higher the risk that two or more changes will interact in unexpected ways.

So the total risk is going to be something like the sum of all the risks associated with each change plus the risk that two or more changes will interact badly. If you release one change at a time, though, as I've previously suggested, you eliminate this secondary compounding of risk.