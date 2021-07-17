---
title: "Writing and running tests with pytest"
categories:
  - Blog
tags:
  - pytest
  - Software Testing
  - python
---
<hr>
To gain experience using Pytest I am going to write code that works like a calculator.

I will test it using pytest.

Then I'll automate and streamline the test and delivery process.

You can find more articles of this series with the  <a href="https://estebanherlein.github.io/tags/#pytest">Pytest tag</a>  
<hr>

<h2>The code we will be testing</h2>

Since we need code to run some tests against it we will be testing a couple of simple and straightforward calculator functions. They will serve the porpouse of testing well since they receive and input and return a result value which will be useful when running assertions to decide if the test was successful or not.

You can clone the code from  <a href="https://github.com/estebanherlein/introtopytest">this repository</a>

<pre>
<code>
def add(x, y):
   return x + y

def subtract(x, y):
   return x - y

def multiply(x, y):
   return x * y

def divide(x, y):
   return x / y

</code>
</pre>

There are 4 python functions , they all receive 2 parameters and operate with them to return an integer as a result.

There are multiple tests that can be run against this fairly simple set of functions.

<ul>
<li>use good input, test that the application returns the correct value</li>
<li>use a list of good input, test that the application returns the correct value consistently</li>
<li>use bad input, test if the application santizes it</li>
<li>use bad input, test that the application returns the correct value</li>
<li>and many many more</li>
</ul>

We will start slow, writing a single test case for every function where we test them with the same input , 8 and 2.

<h2>The tests</h2>

<pre>
<code>

import calculator

def test_add():
    result = calculator.add(8, 2)
    expected = 10
    assert result == expected

def test_substract():
    result = calculator.subtract(8, 2)
    expected = 6
    assert result == expected

def test_multiply():
    result = calculator.multiply(8, 2)
    expected = 16
    assert result == expected

def test_divide():
    result = calculator.divide(8, 2)
    expected = 4
    assert result == expected

</code>
</pre>

We will start by importing the code to be tested. We'll be interacting with it on every test.

There is a test for every function writen on the code package.

There is a simple structure we follow for every test.


<pre>
<code>
def test_add():

// We called the function with the preset 
// parameters and save its output to a 
// variable called result.

    result = calculator.add(8, 2)
	
// we set the expected result, what the 
// function should return given the 
// predefined parameters.

    expected = 10
	
// We compare the expected output against
// the real output to check if the code 
// is working as expected.

    assert result == expected
</code>
</pre>

<h2> Running our tests against the code </h2>


The simplest way to run our test against our code is to launch pytest thourgh the cli while on the root folder of our project

<h3>Default pytest execution </h3>
<pre>
<code>
pytest
</code>
</pre>

If you only want to run the tests located on the V1 folder you can change the current path of your cli to that folder to run the command from there.


This will gather our test file and run all the tests for us. The previous command output should look something like this


<pre>
<code>
=========== test session starts ==============
platform win32 -- Python 3.9.0, pytest-6.2.1, py-1.10.0, pluggy-0.13.1
rootdir: C:\ww\ww\ww\testingwithpytest
collected 4 items

test_calculator.py ....

[100%]

=========== 4 passed in 0.02s =================
</code>
</pre>

It ouputs some debugging information, the number of tests that will be executed  and, afterwards, the results.

If a test failed it would output it's information.


<h3>Verbose pytest execution </h3>

Running the command pytest with the verbose option will output debugging information and the name of each individual test with it's result

<pre>
<code>
pytest - v
</code>
</pre>


<pre>
<code>
========== test session starts ==========
platform win32 -- Python 3.9.0, pytest-6.2.1, py-1.10.0, pluggy-0.13.1 -- 
c:\ww\ww\ww\testingwithpytest\venv\scripts\python.exe
cachedir: .pytest_cache
rootdir: C:\ww\ww\ww\testingwithpytest
collected 4 items

test_calculator.py::test_add PASSED
[ 25%]
test_calculator.py::test_substract PASSED
[ 50%]
test_calculator.py::test_multiply PASSED
[ 75%]
test_calculator.py::test_divide PASSED
[100%]

========== 4 passed in 0.03s ============
</code>
</pre>