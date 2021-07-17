---
title: "Dictionary data Structure"
categories:
  - Blog
tags:
  - Data Structures
---

A dictionary represents an unordered collection of keys and values. The Dictionary data type is optimized for fast lookup of values.

Each addition to the dictionary consists of a value, and its associated key. Every key in a Dictionary must be unique. A key cannot be null, but a value can be, only when the value type is a reference type.

For example, a dictionary could store the key value pairs of a dog’s name (key) and their titles (values):

<pre><code>
results = {'Detra' : 17,
           'Nova' : 84,
           'Charlie' : 22,
           'Henry' : 75,
           'Roxanne' : 92,
           'Elsa' : 29}
</code></pre>

Instead of using the numerical index of the data, we can use the dictionary names to return values: 

<pre><code>
>>> results['Nova']
84
>>> results['Elsa']
29
</code></pre>

A dictionary is also called a hash, a map, a hashmap in different programming languages (and an Object in JavaScript). They're all the same thing: a key-value store.

The concept of a key-value store is widely used in various computing systems, such as caches and high-performance databases.

Typically, the keys in a dictionary must be simple types (such as integers or strings) while the values can be of any type. Different languages enforce different type restrictions on keys and values in a dictionary. Dictionaries are often implemented as hash tables.

Keys in a dictionary must be unique; an attempt to create a duplicate key will typically overwrite the existing value for that key.

Note that there is a difference (which may be important) between a key not existing in a dictionary, and the key existing but with its corresponding value being null. 

<h2>Differences with similar data structures</h2>
<ul>
<li>Arrays<br>arrays and dictionaries both store collections of data, but differ by how they are accessed. Items in an array are accessed by position (often a number) and hence have an order. Items in a dictionary are accessed by key and are unordered.</li>

<li>Sets<br>Sets are groups of items, unordered with duplicates removed. The keys of a dictionary form a set, but each key has an associated value; these values could be duplicated within a dictionary.</li>
</ul>

<h2>Operations with dictionaries</h2>

Dictionaries typically support several operations:
<ul>
<li>retrieve a value (depending on language, attempting to retrieve a missing key may give a default value or throw an exception)</li>
<li>insert or update a value (typically, if the key does not exist in the dictionary, the key-value pair is inserted; if the key already exists, its corresponding value is overwritten with the new one)</li>
<li>remove a key-value pair</li>
<li>test for existence of a key</li>
</ul>

Most programming languages with dictionaries will also support iteration over the keys or values in a dictionary. Note that items in a dictionary are unordered, so loops over dictionaries will return items in an arbitrary order. 