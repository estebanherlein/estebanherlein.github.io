---
title: "Singleton"
categories:
  - Blog
tags:
  - software design patterns
---

The singleton pattern is used to limit creation of a class to only one object. 


<h2>When should i use it ? </h2>

This is beneficial when one (and only one) object is needed to coordinate actions across the system. There are several examples of where only a single instance of a class should exist, including caches, thread pools, and registries.

<h2> How do you implement it ? </h2>

The answer is to make the constructor ‘private’ to the class we intend to define as a singleton. That way, only the members of the class can access the private constructor and no one else.