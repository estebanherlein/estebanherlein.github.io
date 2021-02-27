---
title: "Dart sintax"
categories:
  - Blog
tags:
  - flutter
---

Every app has a main() function. To display text on the console, you can use the top-level print() function:

<pre><code>
void main() {
  print('Hello, World!');
}
</code></pre>

<b>void</b> is a special type that indicates a value that’s never used. 

Functions like main() that don’t explicitly return a value have the void return type.

<h2>Variables</h2>

<pre><code>
var name = 'Voyager I';
var year = 1977;
var antennaDiameter = 3.7;
var flybyObjects = ['Jupiter', 'Saturn', 'Uranus', 'Neptune'];
var image = {
  'tags': ['saturn'],
  'url': '//path/to/saturn.jpg'
};
</code></pre>

Variables store references. The variable called name contains a reference to a String object with a value of “Voyager I”.

The type of the name variable is inferred to be String, but you can change that type by specifying it.

If an object isn’t restricted to a single type, specify the Object or dynamic type

Uninitialized variables have an initial value of null. Even variables with numeric types are initially null, because numbers, like everything else in Dart, are objects.

<h3>Final and const</h3>

If you never intend to change a variable, use final or const, either instead of var or in addition to a type. 

A final variable can be set only once; a const variable is a compile-time constant. Const variables are implicitly final. A final top-level or class variable is initialized the first time it’s used.

<h3>Built-in types</h3>

The Dart language has special support for the following types:
<ul>
<li>numbers</li>
<li>strings</li>
<li>booleans</li>
<li>lists (also known as arrays)</li>
<li>sets</li>
<li>maps</li>
<li>runes (for expressing Unicode characters in a string)</li>
<li>symbols</li>
</ul>

You can initialize an object of any of these special types using a literal. For example, 'this is a string' is a string literal, and true is a boolean literal.

Because every variable in Dart refers to an object—an instance of a class—you can usually use constructors to initialize variables. Some of the built-in types have their own constructors.

 For example, you can use the Map() constructor to create a map.
 
<h4>Lists</h4>

Perhaps the most common collection in nearly every programming language is the array, or ordered group of objects. In Dart, arrays are List objects, so most people just call them lists.

Lists use zero-based indexing, where 0 is the index of the first value and list.length - 1 is the index of the last value. You can get a list’s length and refer to list values just as you would in JavaScript

<pre><code>var list = [1, 2, 3];</code></pre>

<h4>Sets</h4>

A set in Dart is an unordered collection of unique items. Dart support for sets is provided by set literals and the Set type.

<pre><code>var halogens = {'fluorine', 'chlorine', 'bromine', 'iodine', 'astatine'};</code></pre>

<h4>Maps</h4>

In general, a map is an object that associates keys and values. Both keys and values can be any type of object. Each key occurs only once, but you can use the same value multiple times. Dart support for maps is provided by map literals and the Map type.

<pre><code>
var gifts = {
  // Key:    Value
  'first': 'partridge',
  'second': 'turtledoves',
  'fifth': 'golden rings'
};
</code></pre>

<h4>Functions</h4>

Dart is a true object-oriented language, so even functions are objects and have a type, Function. This means that functions can be assigned to variables or passed as arguments to other functions. You can also call an instance of a Dart class as if it were a function. For details, see Callable classes.

<pre><code>
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
</code></pre>

<h2>Control flow statements</h2>

Dart supports the usual control flow statement.

<pre><code>

if (year >= 2001) {
  print('21st century');
} else if (year >= 1901) {
  print('20th century');
}

for (var object in flybyObjects) {
  print(object);
}

for (int month = 1; month <= 12; month++) {
  print(month);
}

while (year < 2016) {
  year += 1;
}

</code></pre>

<h2>Comments</h2>

Dart comments usually start with //.

<pre><code>
// This is a normal, one-line comment.

/// This is a documentation comment, used to document libraries,
/// classes, and their members. Tools like IDEs and dartdoc treat
/// doc comments specially.

/* Comments like these are also supported. */
</code></pre>

<h2>Imports</h2>

To access APIs defined in other libraries, use import.
<pre><code>
// Importing core libraries
import 'dart:math';

// Importing libraries from external packages
import 'package:test/test.dart';

// Importing files
import 'path/to/my_other_file.dart';
</code></pre>

<h2>Exceptions</h2>

To raise an exception, use throw:
<pre><code>
if (astronauts == 0) {
  throw StateError('No astronauts.');
}
</code></pre>

To catch an exception, use a try statement with on or catch (or both):
<pre><code>
try {
  for (var object in flybyObjects) {
    var description = await File('$object.txt').readAsString();
    print(description);
  }
} on IOException catch (e) {
  print('Could not describe object: $e');
} finally {
  flybyObjects.clear();
}
</code></pre>