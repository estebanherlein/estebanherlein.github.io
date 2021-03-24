---
title: "Stack data structure "
categories:
  - Blog
tags:
  - Data structures
---

We can define the stack data structure as a linear restrictive structure of type LIFO (last in first out), this indicates that the last element that entered the stack must be the first to exit. 

We can visualize a stack if we think, for example, of a stack of dishes. 

Suppose we have several dishes in a kitchen. We take one (we'll call it A) and place it on a table. Then, we take another (we will call it B) and place it on top of A. Then, we take another plate (we will call it C) and place it on top of B.

Thus we form a stack of plates and, at the top of the stack, the plate will always be located. 

If we want to remove an item from the stack of dishes, we will always take the one on top. 

Thus, the first plate that we will take out will be C (the last that we stack). The next plate we will take will be B (the second to last that we stack) and, lastly, we will take plate A (the first).

<h2>Characteristics of a stack</h2>

<ul>
<li>Elements can always be inserted first (above the rest of the elements, leaving the element at the top or top of the stack)</li>
<li>Extractions of elements can always be carried out in the first place (the element that is at the top or top of the stack).</li>

</ul>

<h2>Dynamic or static implementation</h2>

A stack-like data structure can be implemented at the software level in a static or dynamic way.

For a static implementation, define a size when the structure is created, we will use a vector and for a dynamic implementation we will use a linked list.

A static implementation with a vector generates a waste of memory space, since when it is created , memory space is reserved for the entire structure, even if it is not occupied. On the other hand, its implementation is very simple and its elements are accessed in a constant time. 

A dynamic implementation of a stack with a linked list does not waste memory, since the elements will be added dynamically and, on the other hand, as a stack It only accesses the top element, as the first element in the list is the same, access and insertion will be efficient.

<h2>Stack implementation example</h2>

One of the most used cases is wanting to verify if a certain statement or instruction is balanced in terms of number of parentheses, brackets or opening and closing brackets. 

When writing programming code if there is no balance between opening signs (for example, an opening parenthesis) and closing (for example, a closing parenthesis), the statement should not even be processed 
