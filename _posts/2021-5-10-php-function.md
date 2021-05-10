---
title: "PHP Functions"
categories:
  - Blog
tags:
  - php
---

In the world of programming and scripting there are two ways to write code. One way is to write long, sprawling and monolithic sections of script. Another is to break the scripts up into tidy, self contained modules that can be re-used without having to re-invent the same code over and over again. Obviously the latter is highly preferable to the former, and the fundamental building block of this approach to writing PHP scripts is the function. 

Functions are basically named scripts that can be called upon from any other script to perform a specific task. Values (known as arguments) can be passed into a function so that they can be used in the function script, and functions can, in turn, return results to the location from which they were called.

PHP functions exist it two forms, functions that are provided with PHP to make your life as a web developer easier, and those that you as a web developer create yourself. 

<h2>How to Write a PHP Function</h2>

The first step in creating a PHP function is to provide a name by which you will reference the function. Naming conventions for PHP functions are the same as those for variables in that they must begin with a letter or an underscore and must be devoid of any kind of white space or punctuation. You must also take care to ensure that your function name does not conflict with any of the PHP built in functions.

PHP functions are created using the function keyword followed by the name and, finally, a set of parentheses. The body of the function (the script that performs the work of the function) is then enclosed in opening and closing braces. 

<h3>Returning a Value from a PHP Function</h3>

A single value may be returned from a PHP function to the script from which it was called. The returned value can be any variable type of your choice.

The return keyword is used to return the value.

<h3>Passing Parameters to a PHP Function</h3>

Parameters (or arguments as they are more frequently known) can be passed into a function. There are no significant restrictions of the number of arguments which can be passed through to the function.

A function can be designed to accept parameters by placing the parameter names inside the parentheses of the function definition. There are no specific rules on the names that can be given to these arguments other than those applying to variable names in general. 

<h3>Functions and Variable Scope</h3>

Now that we have covered PHP functions it is time to address an issue relating to variable scope. When a variable is declared outside of a function it is said to have global scope. That is, it is accessible to any part of the PHP script in which it is declared. Conversely, when a variable is declared inside a function it is said to have local scope, in that it is only accessible to the script contained in the body of the function.

This means that you can have a global variable and a local variable with the same name containing different values.

Clearly this will be a problem if you ever need to access a global variable in a function with a conflicting local variable name. Fortunately PHP provides the GLOBALS array which provides access to all global variables from within functions