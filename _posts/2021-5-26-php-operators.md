---
title: "PHP operators"
categories:
  - Blog
tags:
  - php
---

Operators in PHP enable us to perform tasks on variables and values such as assign, multiply, add, subtract and concatenate them.

Operators take the form of symbols (such as + and -) and combinations of symbols (such as ++ and +=).

Operators in PHP work with operands which specify the variables and values that are to be used in the particular operation. The number and location of these operands in relation to the operators (i.e. before and/or after the operator) depends on the type of operator in question. 

Let's take, for example, the following simple expression:

> 1 + 3;

In this expression we have one operator (the '+') and two operands (the numbers 1 and 3). The '+' operator adds the values of two operands (resulting in a value of 4).

Operators can be combined to create complete expressions:

> $myVar = 1 + 3;

In the above example, the assignment operator (=) assigns the result of the addition to the operand represented by the variable $myVar. 

After evaluating this expression the value of 4 will have been assigned to the variable $myVar. 

<h2>PHP Assignment Operators</h2>
The assignment operator is used to assign a value to a variable and is represented by the equals (=) sign. The assignment operator can also be combined with arithmetic operators to combine an assignment with a mathematical operation (for example to multiply one value by another and assigning the result to the variable) and also to perform string concatenations. 

<ul>
<li>=	Assignment	Sets the value of the left hand operand to the value of the right</li>
<li>+=	Addition-Assignment	Adds the value of left hand operand to the value of the right hand operand and assigns result to left hand operand	</li>
<li>-=	Subtraction-Assignment	Subtracts the value of right hand operand from the value of the left hand operand and assigns result to left hand operand	</li>
<li>*=	Multiplication-Assignment	Multiplies the left hand operand by value of the right hand operand assigning result to left hand operand	</li>
<li>/=	Division-Assignment	Divides the left hand operand by value of the right hand operand assigning result to left hand operand	</li>
<li>%=	Modulo-Assignment	Sets the value of the left hand operand to the remainder of the value after being divided by the right hand operand	</li>
<li>.=	Concatenation-Operand	Sets the value of the left hand operand to a string containing a concatenation of its value appended with the string in the right hand operand	</li>
</ul>

<h2>PHP Arithmetic Operators</h2>
As the name suggests PHP arithmetic operators provide a mechanism for performing mathematical operations: 
<ul>
<li>+	Addition	Calculates the sum of two operands	</li>
<li>-	Subtraction	Calculates the difference between two operands	</li>
<li>*	Multiplication	Multiplies two operands	</li>
<li>/	Division	Divides two operands</li>
<li>%	Modulus	Returns the remainder from dividing the first operand by the second</li>
</ul>

<h2>PHP Logical Operators</h2>
Logical Operators are also known as Boolean Operators because they evaluate parts of an expression and return a true or false value, allowing decisions to be made about how a script should proceed.
<ul>
<li>&&	AND	Performs a logical "AND" operation.	</li>
<li>||	OR	Performs a logical "OR" operation.	</li>
<li>xor	XOR	Performs a logical "XOR" (exclusive OR) operation.	</li>
</ul>

<h2>PHP Comparison Operators</h2>

The comparison operators provide the ability to compare one value against another and return either a true or false result depending on the status of the match. For example, you might use a comparison operator to check if a variable value matches a particular number, or whether one string is identical to another. PHP provides a wide selection of comparison operators for just about every comparison need. 

<ul>
<li>==	Equal to	Returns true if first operand equals second	</li>
<li>!=	Not equal to	Returns true if first operand is not equal to second</li>
<li><>	Not equal to	Returns true if first operand is not equal to second</li>
<li>===	Identical to	Returns true if first operand equals second in both value and type</li>
<li>!==	Not identical to	Returns true if first operand is not identical to second in both value and type	</li>
<li><	Less than	Returns true if the value of the first operand is less than the second	</li>
<li>>	Greater than	Returns true if the value of the first operand is greater than the second	</li>
<li><=	Less than or equal to	Returns true if the value of the first operand is less than, or equal to, the second</li>	
<li>>=	Greater than or equal to	Returns true if the value of the first operand is greater than, or equal to, the second</li>
</ul>