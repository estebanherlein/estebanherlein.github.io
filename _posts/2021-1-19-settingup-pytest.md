---
title: "Setting up pytest"
categories:
  - Blog
tags:
  - pytest
  - software testing
  - python
---
<hr>
In order to test the functionality of pytest I am going to write code that works as a calculator.

I will test its functionality using pytest.

Then I'm going to automate and optimize the test and delivery process.
<hr>

<h2>Pre-requisites</h2>

Pytest is delivered as a python package and can be installed via pip. You will need to have a python interpreter installed.

Pytest looks for test in files that follow a specific naming convention.

<ul>
<li>If no arguments are specified then collection starts from testpaths (if configured) or the current directory. Alternatively, command line arguments can be used in any combination of directories, file names or node ids.</li>
<li>Recurse into directories, unless they match norecursedirs.</li>
<li>In those directories, search for test_*.py or *_test.py files, imported by their test package name.</li>
<li>From those files, collect test items:<br>

        test prefixed test functions or methods outside of class<br>

        test prefixed test functions or methods inside Test prefixed test classes (without an __init__ method)</li>

</ul>

<h2>Installation</h2>

To get started, let’s install pytest through pip via the cli

<pre>
<code>
pip install pytest
</code>
</pre>


<h2>Clone the code</h2>

You can clone the next repository in order to have code and tests ready to be fired with the push of a button.

<pre>
<code>
git clone https://github.com/estebanherlein/introtopytest
</code>
</pre>



<h2>Project Structure</h2>

Right now our project will consist of a file called calculator.py which holds the code to be tested,  a file called test_calculator.py where we will write our tests and a readme.md file to hold important project information.
<pre>
<code>
/
--calculator.py
--test_calculator.py
--readme.md
</code>
</pre>

<h2>Running our tests</h2>

To run our tests for the first time write this command on the cli while on the root folder of the cloned project

<pre>
<code>
pytest
</code>
</pre>


