---
title: "Template method behavioral pattern"
categories:
  - Blog
tags:
  - software design patterns
  - behavioral patterns
---
The Template Method pattern suggests that you break down an algorithm into a series of steps, turn these steps into methods, and put a series of calls to these methods inside a single template method. 

The steps may either be abstract, or have some default implementation. 

To use the algorithm, the client is supposed to provide its own subclass, implement all abstract steps, and override some of the optional ones if needed

<h2>When should you use it ? </h2>

<ul>
<li>Use the Template Method pattern when you want to let clients extend only particular steps of an algorithm, but not the whole algorithm or its structure.</li>

<li>Use the pattern when you have several classes that contain almost identical algorithms with some minor differences. As a result, you might need to modify all classes when the algorithm changes.</li>
</ul>

<h2> How do you implement it ? </h2>

<ol>

<li>Analyze the target algorithm to see whether you can break it into steps. Consider which steps are common to all subclasses and which ones will always be unique.</li>

<li>Create the abstract base class and declare the template method and a set of abstract methods representing the algorithm’s steps. Outline the algorithm’s structure in the template method by executing corresponding steps. Consider making the template method final to prevent subclasses from overriding it.</li>

<li>It’s okay if all the steps end up being abstract. However, some steps might benefit from having a default implementation. Subclasses don’t have to implement those methods.</li>

<li>Think of adding hooks between the crucial steps of the algorithm.</li>

<li>For each variation of the algorithm, create a new concrete subclass. It must implement all of the abstract steps, but may also override some of the optional ones.</li>

</ol>


