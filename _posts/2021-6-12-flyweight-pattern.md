---
title: "Flyweight pattern"
categories:
  - Blog
tags:
  - software design patterns
  - structural patterns
---

In computer programming, the flyweight software design pattern refers to an object that minimizes memory usage by sharing some of its data with other similar objects. 

The flyweight pattern is one of twenty-three well-known GoF design patterns. These patterns promote flexible object-oriented software design, which is easier to implement, change, test, and reuse.

In other contexts, the idea of sharing data structures is called hash consing.

The term was first coined, and the idea extensively explored, by Paul Calder and Mark Linton in 1990 to efficiently handle glyph information in a WYSIWYG document editor. 

<h2>When is this pattern useful?</h2>

The flyweight pattern is useful when dealing large numbers of objects with simple repeated elements that would use a large amount of memory if individually stored. It is common to hold shared data in external data structures and pass it to the objects temporarily when they are used.

A classic example are the data structures used representing characters in a word processor. Naively, each character in a document might have a glyph object containing its font outline, font metrics, and other formatting data. 

However, this would use hundreds or thousands of bytes of memory for each character. Instead, each character can have a reference to a glyph object shared by every instance of the same character in the document. 

This way, only the position of each character needs to be stored internally.

As a result, flyweight objects can:

<ul>

<li>store intrinsic state that is invariant, context-independent and shareable (for example, the code of character 'A' in a given character set)</li>
<li>provide an interface for passing in extrinsic state that is variant, context-dependent and can't be shared (for example, the position of character 'A' in a text document</li>
</ul>

<b>Clients can reuse Flyweight objects and pass in extrinsic state as necessary, reducing the number of physically created objects. </b>