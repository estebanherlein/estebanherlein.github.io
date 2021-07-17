---
title: "Same test multiple Parameters, pytest"
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

We will be using the files located in the V2 folder.

<h2>Running the same test with different subsets of data</h2>

The last article left us with a couple of functions that received 2 inputs and asserted it's calculation.

But we need to test it against more than one pair of integers.

On this article we will test different type of inputs, paying attention to the so called limit values. Upper and lower limits of the accepted inputs. 

But firs let's write some code in order for the test to run against multiple inputs.

<h2>Pytest Fixtures</h2>

Test fixtures initialize test functions. 

They provide a fixed baseline so that tests execute reliably and produce consistent, repeatable, results. 

Initialization may setup services, state, or other operating environments. 

These are accessed by test functions through arguments; for each fixture used by a test function there is typically a parameter (named after the fixture) in the test function’s definition.

In order to use the fixture features built in in pytest we will need to import it into our test_ file. You'll have to add an import statement at the begging of the file

<pre>
<code>
import pytest
</code>
</pre>

Once pytest is visible from our file we will proceed to add it's functionality into our tests.

In the next code snippet you will find the structure we will we working with while passing multiple parameters to a single test.

<pre>
<code>

#the first line declares the fixture and its 
#functionality, after that it sets the variable
#names and the values they will hold.

@pytest.mark.parametrize("x,y,z", [(3,2,5), (5,4,9)])

#after the declaration we pass the variables to the
#function and we write te logic to work around them.

def test_add(x,y,z):
    result = calculator.add(x,y)
    assert result == z
</code>
</pre>

Without the need to implement explicit iterations or loops pytest will make sure that all the variations are tested against the single test.


In order to test our code we will set the cli on the V2 folder and we will run the command pytest, output should look like this.

<pre>
<code>
================== test session starts =======
platform win32 -- Python 3.9.0,
 pytest-6.2.1, py-1.10.0, pluggy-0.13.1 -
- c:\ww\ww\pycharmprojects\testingwithpytest\venv\scripts\python.exe
cachedir: .pytest_cache
rootdir: C:\ww\ww\PycharmProjects\testingwithpytest\v2
collected 2 items

test_calculator_v2.py::test_add[3-2-5] PASSED
[  50%]
test_calculator_v2.py::test_add[5-4-9] PASSED
[ 100%]
================== 2 passed in 0.12s ==========

</code>
</pre>


<h2>Testing the limits </h2>

Because of available time and budget, it is usually impossible to carry out exhaustive software tests for every conceivable test case. Especially when there is a large variation of input combinations to think of, the implementation is practically impossible to do.

We need a simple way to intelligently select test cases from the pool of test cases to cover all test scenarios.

Testing limit values ​​is testing extreme limits of the input values.

Extreme ends such as Start-End, Lower-Upper, Maximum-Minimum, Just Inside-Just Outside values ​​are called limit values. 

To summarize, the idea of taking limit values is one way, by limiting the number of tests to run, to get a quick idea of the ability of the code to react to different inputs in ranges that can be problematic.



<ul>
<li>Minimum</li>
<li>Just above the minimum</li>
<li>A nominal value</li>
<li>Just below the maximum</li>
<li>maximum</li>
</ul>

I will start by adding a function that takes the input and compares it to a series of rules in order to creat minimum and maximun limits.

Both x and y will have to be a number between 0 and 999.

<pre>
<code>

def inputsanitization(x, y):
    if 0 <= x <= 999 and 0 <= y <= 999:
        return True
    else:
        print("Input must be a number between 0 and 999")

</code>
</pre>


This will let us test each function against min, max and out of bounds values.

our code looks like this right now

<pre>
<code>
@pytest.mark.parametrize("first_input,second_input,expected",
					[(0, 1, 1), (1, 1, 2), (11, 3, 14), (998, 3, 1001),  (999, 0, 999), pytest.param(-7, 2, 42, marks=pytest.mark.xfail)])
def test_add(first_input, second_input, expected):
    result = calculator.add(first_input, second_input)
    assert result == expected
</code>
</pre>


The parameters will test each limit , both upper and lower. We have even included an expected to fail case with incorrect input.