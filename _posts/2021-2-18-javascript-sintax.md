---
title: "JavaScript Sintax"
categories:
  - Blog
tags:
  - JavaScript
---

JavaScript's syntax is the set of rules that define how JavaScript programs are constructed

<pre><code>
 var x, y, z;       // Declare Variables
x = 5; y = 6;      // Assign Values
z = x + y;         // Compute Values 
</code></pre>

<h3>JavaScript is Case Sensitive</h3>

All JavaScript identifiers are case sensitive. 

The variables lastName and lastname, are two different variables:

<pre><code>
var lastname, lastName;
lastName = "carlos";
lastname = "Saul";
</code></pre>


<h2>Values</h2>

The JavaScript syntax defines two types of values:
<ul>
<li>Fixed values</li>
<li>Variable values</li>
</ul>

Fixed values are called Literals.

Variable values are called Variables.

<h3>Literals</h3>

The two most important syntax rules for fixed values are:

Numbers are written with or without decimals:

<pre><code>
10.50

1001
</code></pre>

Strings are text, written within double or single quotes:

<pre><code>
"John Doe"

'John Doe'
</code></pre>

<h3>Variables</h3>

In a programming language, variables are used to store data values.

JavaScript uses the var keyword to declare variables.

An equal sign is used to assign values to variables.

In this example, x is defined as a variable. Then, x is assigned (given) the value 6:

<pre><code>
var x;

x = 6; 
</code></pre>

<h2>Operators</h2>

JavaScript uses arithmetic operators ( + - * / ) to compute values: 

<pre><code>
(5 + 6) * 10
</code></pre>

JavaScript uses an assignment operator ( = ) to assign values to variables: 

<pre><code>
var x, y;
x = 5;
y = 6; 
</code></pre>

<h2>Comments</h2>

Not all JavaScript statements are "executed".

Code after double slashes // or between /* and */ is treated as a comment.

Comments are ignored, and will not be executed:


<pre><code>
 var x = 5;   // I will be executed

// var x = 6;   I will NOT be executed 
</code></pre>


<h2>Identifiers</h2>

Identifiers are names.

In JavaScript, identifiers are used to name variables (and keywords, and functions, and labels).

The rules for legal names are much the same in most programming languages.

In JavaScript, the first character must be a letter, or an underscore (_), or a dollar sign ($).

Subsequent characters may be letters, digits, underscores, or dollar signs.

Numbers are not allowed as the first character.
This way JavaScript can easily distinguish identifiers from numbers. 