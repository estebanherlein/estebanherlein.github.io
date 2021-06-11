---
title: "Singleton Anti Pattern"
categories:
  - Blog
tags:
  - Software design anti-pattern
  - Object-oriented programming anti-pattern
---

In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to one "single" instance. This is useful when exactly one object is needed to coordinate actions across the system. The term comes from the mathematical concept of a singleton.

Critics consider the singleton to be an anti-pattern in that it is frequently used in scenarios where it is not beneficial, introduces unnecessary restrictions in situations where a sole instance of a class is not actually required, and introduces global state into an application.

The singleton design pattern solves problems like:
<ul>
<li>How can it be ensured that a class has only one instance?</li>
<li>How can the sole instance of a class be accessed easily?</li>
<li>How can a class control its instantiation?</li>
<li>How can the number of instances of a class be restricted?</li>
<li>How can a global variable be accessed?</li>
</ul>
The singleton design pattern describes how to solve such problems:
<ul>
    <li>Hide the constructor of the class.</li>
    <li>Define a public static operation (getInstance()) that returns the sole instance of the class.</li>
</ul>

The key idea in this pattern is to make the class itself responsible for controlling its instantiation (that it is instantiated only once).

<h2>Common uses</h2>
<ul>
<li>The abstract factory, factory method, builder, and prototype patterns can use singletons in their implementation.</li>
<li>Facade objects are often singletons because only one facade object is required.</li>
<li>State objects are often singletons.</li>
<li>Singletons are often preferred to global variables because:

<br />They do not pollute the global namespace (or, in languages with nested namespaces, their containing namespace) with unnecessary variables.

<br />They permit lazy allocation and initialization, whereas global variables in many languages will always consume resources.

</li>
</ul>

<h2>Anti-pattern considerations</h2>

The Singleton Pattern is generally considered an anti-pattern for the following reasons:

<b>Singleton classes break object-oriented design principles</b>

<ul>
<li>It cannot be inherited from. To add new functionality, a new class cannot be descended to contain that functionality, breaking Separation of Concern.</li>
<li>No control over creation. It is impossible to tell if a reference is of an existing instance or a new instance.</li>
<li>Prevents dependency injection. As there is only a single instance of the class, a dependency cannot be injected into it. If done via a property, the dependency is changed for all references to that instance.</li>
</ul>

<b>Singleton classes do not allow for test-driven development (TDD)</b>

<ul>
<li>As there is no control over creation, a "clean" instance of the object cannot be used for each test.</li>
<li>Without dependency injection mock, objects cannot be used in tests.</li>
</ul>