---
title: "Object Orgy"
categories:
  - Blog
tags:
  - Software design anti-pattern
  - Object-oriented programming
---

In computer programming, an object orgy is a situation in which objects are insufficiently encapsulated via information hiding, allowing unrestricted access to their internals. 

This is a common failure (or anti-pattern) in object-oriented design or object-oriented programming, and it can lead to increased maintenance needs and problems, and even unmaintainable complexity. 

<h2>Consequences</h2>
The results of an object orgy are mainly a loss of the benefits of encapsulation, including: 
<ul>
<li>Unrestricted access makes it hard for a reader to reason about the behaviour of an object. This is because direct access to its internal state means any other part of the system can manipulate it, increasing the amount of code to examine, and creating means for future abuse.</li>
<li>As a consequence of the difficulty of reasoning, design by contract is effectively impossible.</li>
<li>If much code takes advantage of the lack of encapsulation, the result is a scarcely maintainable maze of interactions, commonly known as a rat's nest or spaghetti code.</li>
<li>The original design is obscured by the excessively broad interfaces to objects.</li>
<li>The broad interfaces make it harder to re-implement a class without disturbing the rest of the system. This is especially hard when clients of a class are developed by a different team or organisation.</li>	
</ul>

<h2>Causes</h2>

<ul>
<li>Members may be declared public to avoid the effort or syntactic overhead of providing proper accessors for them. This may increase readability of the class, but at the cost of the consequences described above.</li>	

<li>For some languages, a member intended to be readable by other objects can be made modifiable because the language has no convenient construct for read-only access.</li>	

<li>An object orgy may be a symptom of coding to an immature an anemic design, when a designer has insufficiently analysed the interactions between objects. It can also arise from laziness or haste in implementing a design, especially if a programmer does not communicate enough with a designer, or from reluctance to revise a design when problems arise, which also encourages many other anti-patterns.</li>	

<li>Many programmers view objects as anemic data repositories and manipulate them violating Information Hiding, Encapsulation and Design by Contracts principles. </li>	
</ul>

<h2>Solutions</h2>
In general, encapsulation is broken because the design of other classes requires it, and a redesign is needed. 

If that is not the case, it may be sufficient to re-code the system according to best practices. 

Once the interfaces are published irrevocably, it may be too late to fix them. 