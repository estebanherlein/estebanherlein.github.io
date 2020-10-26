---
title: "Abstract Factory creational pattern"
categories:
  - Blog
tags:
  - software design patterns
  - creational patterns
---

Abstract Factory is a creational design pattern that lets you produce families of related objects without specifying their concrete classes.

The main difference between a “factory method” and an “abstract factory” is that the factory method is a single method, and an abstract factory is an object. 

The factory method is just a method, it can be overridden in a subclass, whereas the abstract factory is an object that has multiple factory methods on it.


<h2>When should you use it ? </h2>

<ul>
<li>Use the Abstract Factory when your code needs to work with various families of related products, but you don’t want it to depend on the concrete classes of those products—they might be unknown beforehand or you simply want to allow for future extensibility.</li>

<li>In a well-designed program each class is responsible only for one thing. When a class deals with multiple product types, it may be worth extracting its factory methods into a stand-alone factory class or a full-blown Abstract Factory implementation.</li>
</ul>

<h2> How do you implement it ? </h2>

<ol>
<li>Map out a matrix of distinct product types versus variants of these products.</li>

<li>Declare abstract product interfaces for all product types. Then make all concrete product classes implement these interfaces.</li>

<li>Declare the abstract factory interface with a set of creation methods for all abstract products.</li>

<li>Implement a set of concrete factory classes, one for each product variant.</li>

<li>Create factory initialization code somewhere in the app. It should instantiate one of the concrete factory classes, depending on the application configuration or the current environment. Pass this factory object to all classes that construct products.</li>

<li>Scan through the code and find all direct calls to product constructors. Replace them with calls to the appropriate creation method on the factory object.</li>

</ol>