---
title: "Linked List data Structure"
categories:
  - Blog
tags:
  - Data structures
---
In computer science, a linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element points to the next. It is a data structure consisting of a collection of nodes which together represent a sequence. 

In its most basic form, each node contains: data, and a reference (in other words, a link) to the next node in the sequence. This structure allows for efficient insertion or removal of elements from any position in the sequence during iteration. 

More complex variants add additional links, allowing more efficient insertion or removal of nodes at arbitrary positions. A drawback of linked lists is that access time is linear (and difficult to pipeline). Faster access, such as random access, is not feasible. Arrays have better cache locality compared to linked lists. 

The principal benefit of a linked list over a conventional array is that the list elements can be easily inserted or removed without reallocation or reorganization of the entire structure because the data items need not be stored contiguously in memory or on disk, while restructuring an array at run-time is a much more expensive operation. 

Linked lists allow insertion and removal of nodes at any point in the list, and allow doing so with a constant number of operations by keeping the link previous to the link being added or removed in memory during list traversal. 


<h2>When to use a  Linked List?</h2>

Arrays can be used to store linear data of similar types, but arrays have the following limitations.

1) The size of the arrays is fixed: So we must know the upper limit on the number of elements in advance. Also, generally, the allocated memory is equal to the upper limit irrespective of the usage.
2) Inserting a new element in an array of elements is expensive because the room has to be created for the new elements and to create room existing elements have to be shifted.

<h3>Advantages over arrays</h3>
<ol>
<li>Dynamic size</li>
<li>Ease of insertion/deletion</li>
</ol>

<h3>Drawbacks:</h3>
<ol>
<li>Random access is not allowed. We have to access elements sequentially starting from the first node. So we cannot do binary search with linked lists efficiently with its default implementation. Read about it here.</li>
<li>Extra memory space for a pointer is required with each element of the list.</li>
<li>Not cache friendly. Since array elements are contiguous locations, there is locality of reference which is not there in case of linked lists.</li>
</ol>

<h3>Representation:</h3>

A linked list is represented by a pointer to the first node of the linked list. The first node is called the head. If the linked list is empty, then the value of the head is NULL.

Each node in a list consists of at least two parts:
<ol>
<li>data</li>
<li>Pointer (Or Reference) to the next node</li>
</ol>

