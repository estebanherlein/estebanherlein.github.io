---
title: "PHP Variable Types"
categories:
  - Blog
tags:
  - php
---
In PHP you can find six types of variables:
<ul>
<li>integer</li>
<li>string</li>
<li>float</li>
<li>boolean</li>
<li>array</li>
<li>objects </li>
</ul>

<h2>Integer</h2>

Integer variables are able to hold a whole number in the range of -2147483648 to 2147483647. Negative values can be assigned by placing the minus (-) sign after the assignment operator and before the number. 

If the value assigned to an integer type variable moves outside the supported range, either via assignment or mathematical calculation, the variable type is automatically converted to a floating point type. 

<h2>Float</h2>

Floating point variables contain numbers that require the use of decimal places. In addition, float variables can store whole numbers up to higher values than the integer variable type (such as 1.067, 0.25, 423454567098, 84664435.9576). 

<h2>Boolean</h2>

PHP boolean type variables hold a value of true or false and are used to test conditions such as whether some part of a script was performed correctly.

We will look at using boolean values in greater detail when we look at PHP Flow Control and Looping, with particular regard to the if statement. It is useful to know that the true and false values are actually represented internally by PHP boolean values 1 and 0 respectively, though it is important to be aware that boolean 1 and 0 are not the same as integer values 1 and 0. 

<h2>String Variable</h2>

The string variable type is used to hold strings of characters such as words and sentences. In addition to providing mechanisms for creating and changing entire string variable values, PHP allows you to extract and change parts of a string value.

A string can be assigned to variable either by surrounding it in single quotes (') or double quotes ("). If your string itself contains either single or double quotes you should use the opposite to wrap the string

You can also escape quotes in your string by preceding them with a backslash (\), especially useful if your string contains both single and double quotes of its own that would otherwise confuse the PHP pre-processor

Double quoted strings also allow the insertion of special control sequences that are interpreted to have special meaning for the PHP pre-processor (such as a tab or new line)>

<ul>
<li><b>\n</b>	New line</li>
<li><b>\r</b>	Carriage Return</li>
<li><b>\t</b>	Tab</li>
<li><b>\\</b>	Backslash Character</li>
<li><b>\"</b>	Double quotation mark</li>
<li><b>\$</b>	Dollar sign (prevents text from being treated as a variable name)</li>
<li><b>\034</b>	Octal ASCII value</li>
<li><b>\x0C</b>	Hexadecimal ASCII Value</li>
</ul>

<h3>Extracting and Writing String Fragments</h3>

Once we have defined a string variable we can extract or make changes to individual characters in the string using what is termed {x} notation, where x represents the index into the string of the character we wish to view or change. Before we look at an example, it is important to keep in mind that the index into the string is zero based. By this we mean that the first character of the string is in position 0, not position 1.