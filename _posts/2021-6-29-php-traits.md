---
title: "Traits"
categories:
  - Blog
tags:
  - php
---

PHP implements a way to reuse code called Traits.

Traits are a mechanism for code reuse in single inheritance languages such as PHP. A Trait is intended to reduce some limitations of single inheritance by enabling a developer to reuse sets of methods freely in several independent classes living in different class hierarchies. The semantics of the combination of Traits and classes is defined in a way which reduces complexity, and avoids the typical problems associated with multiple inheritance and Mixins.

A Trait is similar to a class, but only intended to group functionality in a fine-grained and consistent way. It is not possible to instantiate a Trait on its own. It is an addition to traditional inheritance and enables horizontal composition of behavior; that is, the application of class members without requiring inheritance. 


<h3>Precedence</h3>

An inherited member from a base class is overridden by a member inserted by a Trait. The precedence order is that members from the current class override Trait methods, which in turn override inherited methods. 

<h3>Multiple Traits </h3>

Multiple Traits can be inserted into a class by listing them in the use statement, separated by commas. 

<h3>Conflict Resolution </h3>

If two Traits insert a method with the same name, a fatal error is produced, if the conflict is not explicitly resolved.

To resolve naming conflicts between Traits used in the same class, the insteadof operator needs to be used to choose exactly one of the conflicting methods.

Since this only allows one to exclude methods, the as operator can be used to add an alias to one of the methods. Note the as operator does not rename the method and it does not affect any other method either. 

<h3>Traits Composed from Traits </h3>

Just as classes can make use of traits, so can other traits. By using one or more traits in a trait definition, it can be composed partially or entirely of the members defined in those other traits. 