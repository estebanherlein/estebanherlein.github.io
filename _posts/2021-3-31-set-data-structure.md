---
title: "Set data Structure"
categories:
  - Blog
tags:
  - Data Structures
---

In computer science, a set is an abstract data type that can store unique values, without any particular order. It is a computer implementation of the mathematical concept of a finite set. Unlike most other collection types, rather than retrieving a specific element from a set, one typically tests a value for membership in a set.

Some set data structures are designed for static or frozen sets that do not change after they are constructed. Static sets allow only query operations on their elements — such as checking whether a given value is in the set, or enumerating the values in some arbitrary order. Other variants, called dynamic or mutable sets, allow also the insertion and deletion of elements from the set. 

Set objects also support mathematical operations like union, intersection, difference, and symmetric difference.



<h3>Core set-theoretical operations</h3>

One may define the operations of the algebra of sets:
<ul>
<li>union(S,T):<br> returns the union of sets S and T.</li>
<li>intersection(S,T):<br>  returns the intersection of sets S and T.</li>
<li>difference(S,T):<br>  returns the difference of sets S and T.</li>
<li>subset(S,T):<br>  a predicate that tests whether the set S is a subset of set T.</li>
</ul>
<h3>Static sets</h3>

Typical operations that may be provided by a static set structure S are:

<ul>
<li>is_element_of(x,S):<br>  checks whether the value x is in the set S.</li>
<li>is_empty(S):<br>  checks whether the set S is empty.</li>
<li>size(S) or cardinality(S):<br>  returns the number of elements in S.</li>
<li>iterate(S):<br>  returns a function that returns one more value of S at each call, in some arbitrary order.</li>
<li>enumerate(S):<br>  returns a list containing the elements of S in some arbitrary order.</li>
<li>build(x1,x2,…,xn,):<br>  creates a set structure with values x1,x2,...,xn.</li>
<li>create_from(collection):<br>  creates a new set structure containing all the elements of the given collection or all the elements returned by the given iterator.</li>
</ul>
<h3>Dynamic sets</h3>

Dynamic set structures typically add:
<ul>
<li>create():<br>  creates a new, initially empty set structure.</li>
<li>create_with_capacity(n):<br>  creates a new set structure, initially empty but capable of holding up to n elements.</li>
<li>add(S,x):<br>  adds the element x to S, if it is not present already.</li>
<li>remove(S, x):<br>  removes the element x from S, if it is present.</li>
<li>capacity(S):<br>  returns the maximum number of values that S can hold.</li>
</ul>

<h2>Multiset</h2>

A generalization of the notion of a set is that of a multiset or bag, which is similar to a set but allows repeated ("equal") values (duplicates). This is used in two distinct senses: either equal values are considered identical, and are simply counted, or equal values are considered equivalent, and are stored as distinct items. For example, given a list of people (by name) and ages (in years), one could construct a multiset of ages, which simply counts the number of people of a given age. Alternatively, one can construct a multiset of people, where two people are considered equivalent if their ages are the same (but may be different people and have different names), in which case each pair (name, age) must be stored, and selecting on a given age gives all the people of a given age.

Formally, it is possible for objects in computer science to be considered "equal" under some equivalence relation but still distinct under another relation. Some types of multiset implementations will store distinct equal objects as separate items in the data structure; while others will collapse it down to one version (the first one encountered) and keep a positive integer count of the multiplicity of the element.

As with sets, multisets can naturally be implemented using hash table or trees, which yield different performance characteristics. 