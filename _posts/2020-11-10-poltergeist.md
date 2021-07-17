---
title: "Poltergeist"
categories:
  - Blog
tags:
  - Software Design Anti-Patterns
  - Object-oriented Programming Anti-Patterns
---

A poltergeist  is a short-lived, typically stateless object, used to perform initialization or to invoke methods in another more permanent class. 

The original definition is by Michael Akroyd 1996 - Object World West Conference:

>"As a poltergeist appears and disappears mysteriously, so does this short lived object. As a consequence the code is more difficult to maintain and there is unnecessary resource waste. The typical cause for this antipattern is poor object design."

A poltergeist can often be identified by its name; they are often called "manager_", "controller_", "supervisor", "start_process", etc.

Sometimes, poltergeist classes are created because the programmer anticipated the need for a more complex architecture. For example, a poltergeist arises if the same method acts as both the client and invoker in a command pattern, and the programmer anticipates separating the two phases. However, this more complex architecture may actually never materialize.

Poltergeists should not be confused with long-lived, state-bearing objects of a pattern such as model-view-controller, or tier-separating patterns such as business-delegate.

To remove a poltergeist, delete the class and insert its functionality in the invoked class, possibly by inheritance or as a mixin.  