---
title: "Intro to pytest"
categories:
  - Blog
tags:
  - pytest
  - software testing
  - python
---

Pytest is a testing framework based on python. It is mainly used to write API test cases. 

Pytests may be written either as functions or as methods in classes – unlike unittest, which forces tests to be inside classes. 

Test classes must be named “Test*”, and test functions/methods must be named “test_*”. 

Test classes also need not inherit from unittest.TestCase or any other base class. 

Thus, pytests tend to be more concise and more Pythonic. pytest can also run unittest and nose tests.

<h2>Features</h2>

<ul>
<li>Pytest can run multiple tests in parallel, which reduces the execution time of the test suite.</li>
<li>Pytest has its own way to detect the test file and test functions automatically, if not mentioned explicitly.</li>
<li>Pytest allows us to skip a subset of the tests during execution.</li>
<li>Pytest allows us to run a subset of the entire test suite.</li>
<li>Pytest is free and open source.</li>
<li>Because of its simple syntax, pytest is very easy to start with.</li>
</ul>

<h2> Project Structure</h2>

The modules containing pytests should be named “test_*.py” or “*_test.py”. 

While the pytest discovery mechanism can find tests anywhere, pytests must be placed into separate directories from the product code packages. These directories may either be under the project root or under the Python package. However, the pytest directories must not be Python packages themselves, meaning that they should not have “__init__.py” files. 

Test configuration may be added to configuration files, which may go by the names “pytest.ini”, “tox.ini”, or “setup.cfg”.

<pre>
<code>
[project root directory]
|-- [product code packages]
|-- [test directories]
|   |-- test_*.py
|   `-- *_test.py
`-- [pytest.ini|tox.ini|setup.cfg]
</code>
</pre>

<h2> Test Execution</h2>

pytest has a very powerful command line for launching tests. Simply run the pytest module from within the project root directory, and pytest will automatically discover tests.

<pre>
<code>
# Find and run all pytests from the current directory
python -m pytest
 
# Run pytests in a specific module
python -m pytest tests/test_calc_func.py
 
# Generate JUnit-style XML test reports
python -m pytest --junitxml=[path-to-file]
 
# Get command help
python -m pytest -h
</code>
</pre>

<h2> Fixtures </h2>

Test fixtures initialize test functions. 

They provide a fixed baseline so that tests execute reliably and produce consistent, repeatable, results. 

Initialization may setup services, state, or other operating environments. 

These are accessed by test functions through arguments; for each fixture used by a test function there is typically a parameter (named after the fixture) in the test function’s definition.

pytest fixtures offer dramatic improvements over the classic xUnit style of setup/teardown functions:

<ul>
<li>fixtures have explicit names and are activated by declaring their use from test functions, modules, classes or whole projects.</li>
<li>fixtures are implemented in a modular manner, as each fixture name triggers a fixture function which can itself use other fixtures.</li>
<li>fixture management scales from simple unit to complex functional testing, allowing to parametrize fixtures and tests according to configuration and component options, or to re-use fixtures across function, class, module or whole test session scopes.</li>
</ul>

In addition, pytest continues to support classic xunit-style setup. You can mix both styles, moving incrementally from classic to new style, as you prefer. You can also start out from existing unittest.TestCase style or nose based projects.