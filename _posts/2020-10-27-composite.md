---
title: "Composite structural pattern"
categories:
  - Blog
tags:
  - software design patterns
  - structural patterns
---

Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they were individual objects.


The greatest benefit of this approach is that you don’t need to care about the concrete classes of objects that compose the tree.

You don’t need to know whether an object is a simple product or a sophisticated box. 
 
You can treat them all the same via the common interface. When you call a method, the objects themselves pass the request down the tree.

<h2>When should you use it ? </h2>

<ul>
<li> Use the Composite pattern when you have to implement a tree-like object structure.</li>

<li> Use the pattern when you want the client code to treat both simple and complex elements uniformly.</li>
</ul>

<h2> How do you implement it ? </h2>

<ol>

<li>Make sure that the core model of your app can be represented as a tree structure. Try to break it down into simple elements and containers. Remember that containers must be able to contain both simple elements and other containers.</li>

<li>Declare the component interface with a list of methods that make sense for both simple and complex components.</li>

<li>Create a leaf class to represent simple elements. A program may have multiple different leaf classes.</li>

<li>Create a container class to represent complex elements. In this class, provide an array field for storing references to sub-elements. The array must be able to store both leaves and containers, so make sure it’s declared with the component interface type.</li>

<li>While implementing the methods of the component interface, remember that a container is supposed to be delegating most of the work to sub-elements.</li>

<li>Finally, define the methods for adding and removal of child elements in the container.</li>

Keep in mind that these operations can be declared in the component interface. This would violate the Interface Segregation Principle because the methods will be empty in the leaf class. However, the client will be able to treat all the elements equally, even when composing the tree.




</ol>


