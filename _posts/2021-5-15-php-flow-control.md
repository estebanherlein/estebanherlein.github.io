---
title: "PHP Flow Control"
categories:
  - Blog
tags:
  - php
---

One of the main reasons for using scripting languages such as PHP is to build logic and intelligence into the creation and deployment of web based data. In order to be able to build logic into PHP based scripts, it is necessary for the script to be able to make decisions and repeat tasks based on specified criteria.

For example, it may be necessary to repeat a section of a script a specified number of times, or perform a task only if one or more conditions are found to be true (i.e. only let the user log in if a valid password has been provided).

In programming terms this is known as flow control and looping. In the simplest terms this involves some standard scripting structures provided by languages such as PHP to control the logic and overall behavior of a script. Each of these structures provides a simple and intuitive way to build intelligence into scripts. These PHP structures can be broken down into a number of categories as follows:

<h3>Conditional Statements</h3>
<ul>
<li>if statements</li>
<li>if ... else ... statements</li>
</ul>
<h3>Looping Statements</h3>
<ul>
<li>for loops</li>
<li>while loops</li>
<li>do ... while loops</li>
</ul>
<h3>Switch Statements </h3>

<h2>PHP Conditional Statements</h2>

Just about everything in life revolves around decisions. We wouldn't get very far through the day if we weren't able to decide what to wear, what to eat and which roads to traverse on the way to work. 

Similarly computers would be of little use without some innate ability to evaluate choices and make decisions. If all we were able to do was provide a computer with a set of instructions that simply followed one after the other with no ability to make choices based on specific criteria, none of the software we have today would exist.

Conditional statements provide the core of building decision making into scripting languages such as PHP. Conditional statements essentially control whether a part of a script is executed depending the result of a particular expression (i.e. whether an expression returns a boolean true or false value). 

The two types of conditional structures provided by PHP (and most other programming languages) are if and if ... else. 

<h3>The PHP if Statement</h3>

The basic building block of conditional coding is the if statement. The first line of an if statement consists of the if statement followed by the expression to be evaluated in parentheses.

The second step in constructing an if statement involves specifying the action to be taken when the expression is evaluated to be true. This is achieved by placing the lines of script to be executed in open and closing braces after the if statemen

<h3>The PHP if ... else Statements</h3>

The if statement above allows you to specify what should happen if a particular expression evaluates to true. It does not, however, provide the option to specify something else that should happen in the event that the expression evaluates to be false. This is where the if ... else construct comes into play.

The syntax for if ... else is the same as for the if statement with the exception that the else statement can be used to specify alternate action.

<h2>PHP Looping Statements</h2>

It is generally accepted that computers are great at performing repetitive tasks an infinite number of times, and doing so very quickly. It is also common knowledge that computers really don't do anything unless someone programs them to tell them what to do.

Loop statements are the primary mechanism for telling a computer to perform the same task over and over again until a set of criteria are met. This is where for, while and do ... while loops are of use.

<h3>PHP for loops</h3>

Suppose you wanted to add a number to itself ten times. One way to do this might be to write a hundred line script , adding the number to itself on each new line.

Whilst this is somewhat ungainly and time consuming to type, it does work. What would happen, however, if there was a requirement to perform this task 100 times or even 10,000 times. Writing a script to perform this as above would be prohibitively time consuming. This is exactly the situation the for loop is intended to handle. 

The syntax of a PHP for loop is as follows:

for ( initializer; conditional expression; loop expression )
{
// PHP statements to be executed go here
}

The initializer typically initializes a counter variable. Traditionally the variable $i is used for this purpose. For example:

$i = 0

This sets the counter to be the value $i and sets it to zero.

The conditional expression specifies the test to perform to verify whether the loop has been performed the required number of times. For example, if we want to loop 1000 times:

$i < 1000

Finally, the loop expression specifies the action to perform on the counter variable. For example to increment by 1:

$i++

Bringing this all together we can create a for loop to perform the task outlined in the earlier in this section:

<?php
$j = 10;

for ($i=0; $i<10; $i++)
{
$j += $j;
}
?>

<h3>PHP while loops</h3>

The PHP for loop described previously works well when you know in advance how many times a particular task needs to be repeated in a script. Clearly, there will frequently be instances where code needs to be repeated until a certain condition is met, with no way of knowing in advance how many repetitions are going to be needed to meet that criteria. To address this PHP, provides the while loop.

Essentially, the while loop repeats a set of tasks until a specified condition is met. The while loop syntax is defined follows:

<?php
while (condition)
{
      // PHP statements go here
}
?>

<h3>PHP do ... while loops</h3>

You can think of the do ... while loop as an inverted while loop. 

The while loop evaluates an expression before executing the code contained in the body of the loop. If the expression evaluates to false on the first check then the code is not executed. 

The do .. while loop, on the other hand, is provided for situations where you know that the code contained in the body of the loop will always need to be executed at least once. 

For example, you may want to keep stepping through the items in an array until a specific item is found. You know that you have to at least check the first item in the array to have any hope of finding the entry you need. 

<?php
do
{
       PHP statements
} while (conditional expression)
?>

<h2>PHP switch Statements</h2>

when a need arises to evaluate a large number of conditions. A much easier way to handle such situations is to use the PHP switch statement, the syntax for which is defined as follows:

switch (''value'')
{
case "match1" :
PHP statements
break;

case "match2" :
PHP statements
break;

case "match3" :
PHP statements
break;

case "match4" :
PHP statements
break;

case "match5" :
PHP statements
break;

default :
PHP statements
break;
}

There can be any number of case statements - basically as many as you need to fully compare the value in the switch statement against the possible options (represented by match1 through to match5 in the above example) specified by the case statements. 

When a match is found the PHP statements corresponding to the matching case are executed. Note the break; statement in each case - this is important. Without the break; all the cases after the matching case will also be executed when a match is found. 