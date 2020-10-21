---
title: "Factory Method creational pattern"
categories:
  - Blog
tags:
  - software design patterns
  - creational patterns
---

A normal factory produces goods; a software factory produces objects. 

It does so without specifying the exact class of the object to be created. 


<h2>When should you use it ? </h2>

Creating an object directly within the class that requires or uses the object is inflexible because it commits the class to a particular object and makes it impossible to change the instantiation independently of the class. 

A change to the instantiator would require a change to the class code which we would rather not touch. This is referred to as code coupling and the Factory method pattern assists in decoupling the code. 


<h2> How do you implement it ? </h2>

The Factory Method design pattern is used by first defining a separate operation, a factory method, for creating an object, and then using this factory method by calling it to create the object. 

This enables writing of subclasses that decide how a parent object is created and what type of objects the parent contains.