---
title: "State behavioral pattern"
categories:
  - Blog
tags:
  - software design patterns
  - behavioral patterns
---

State is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.

The State pattern is closely related to the concept of a Finite-State Machine.

The main idea is that, at any given moment, there’s a finite number of states which a program can be in. Within any unique state, the program behaves differently, and the program can be switched from one state to another instantaneously. However, depending on a current state, the program may or may not switch to certain other states. These switching rules, called transitions, are also finite and predetermined.

You can also apply this approach to objects. Imagine that we have a Document class. A document can be in one of three states: Draft, Moderation and Published. The publish method of the document works a little bit differently in each state:
<ul>
<li>In Draft, it moves the document to moderation.</li>
<li>In Moderation, it makes the document public, but only if the current user is an administrator.</li>
<li>In Published, it doesn’t do anything at all.</li>
</ul>

<h2>Solution</h2>

The State pattern suggests that you create new classes for all possible states of an object and extract all state-specific behaviors into these classes.

Instead of implementing all behaviors on its own, the original object, called context, stores a reference to one of the state objects that represents its current state, and delegates all the state-related work to that object.

To transition the context into another state, replace the active state object with another object that represents that new state. This is possible only if all state classes follow the same interface and the context itself works with these objects through that interface.

This structure may look similar to the Strategy pattern, but there’s one key difference. In the State pattern, the particular states may be aware of each other and initiate transitions from one state to another, whereas strategies almost never know about each other.

<h2>Real-World Analogy</h2>

The buttons and switches in your smartphone behave differently depending on the current state of the device:
<ul>
<li>When the phone is unlocked, pressing buttons leads to executing various functions.</li>
<li>When the phone is locked, pressing any button leads to the unlock screen.</li>
<li>When the phone’s charge is low, pressing any button shows the charging screen.</li>
</ul>

<h2>Applicability</h2>

Use the State pattern when you have an object that behaves differently depending on its current state, the number of states is enormous, and the state-specific code changes frequently.

Use the pattern when you have a class polluted with massive conditionals that alter how the class behaves according to the current values of the class’s fields.

Use State when you have a lot of duplicate code across similar states and transitions of a condition-based state machine.
