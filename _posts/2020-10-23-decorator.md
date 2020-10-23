---
title: "Decorator structural pattern"
categories:
  - Blog
tags:
  - software design patterns
  - structural patterns
---

Extending a class is the first thing that comes to mind when you need to alter an object’s behavior. 

However, inheritance has several serious caveats that you need to be aware of.
<ul>
<li>Inheritance is static. You can’t alter the behavior of an existing object at runtime. You can only replace the whole object with another one that’s created from a different subclass.</li>
<li>Subclasses can have just one parent class. In most languages, inheritance doesn’t let a class inherit behaviors of multiple classes at the same time.</li>
</ul>

One of the ways to overcome these caveats is by using Aggregation or Composition instead of Inheritance. 

Both of the alternatives work almost the same way: one object has a reference to another and delegates it some work.


<h2>When should you use it ? </h2>

<ul>
<li> Use the Decorator pattern when you need to be able to assign extra behaviors to objects at runtime without breaking the code that uses these objects.</li>

<li> Use the pattern when it’s awkward or not possible to extend an object’s behavior using inheritance.</li>
</ul>

<h2> How do you implement it ? </h2>

<ol>

<li>Make sure your business domain can be represented as a primary component with multiple optional layers over it.</li>

<li>Figure out what methods are common to both the primary component and the optional layers. Create a component interface and declare those methods there.</li>

<li>Create a concrete component class and define the base behavior in it.</li>

<li>Create a base decorator class. It should have a field for storing a reference to a wrapped object. The field should be declared with the component interface type to allow linking to concrete components as well as decorators. The base decorator must delegate all work to the wrapped object.</li>

<li>Make sure all classes implement the component interface.</li>

<li>Create concrete decorators by extending them from the base decorator. A concrete decorator must execute its behavior before or after the call to the parent method (which always delegates to the wrapped object).</li>

<li>The client code must be responsible for creating decorators and composing them in the way the client needs.</li>


</ol>


