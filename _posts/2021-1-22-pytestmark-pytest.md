---
title: "Marking test functions , pytest"
categories:
  - Blog
tags:
  - pytest
  - software testing
  - python
---
<hr>
To gain experience using Pytest I am going to write code that works like a calculator.

I will test it using pytest.

Then I'll automate and streamline the test and delivery process.

You can find more articles of this series with the  <a href="https://estebanherlein.github.io/tags/#pytest">Pytest tag</a>  
<hr>

<h2>Group test functions</h2>

Pytest.mark let's testers mark test function with custom metadata.

One scenario where this is desirable is when splitting tests into different suites.

Via cli flags you can let pytest know that it should only run an specific subset of tests.

<pre>
<code>
@pytest.mark.nameofsubset
</code>
</pre>

The next command would run the tests defined under the nameofsubset fixture mark.

<pre>
<code>
pytest -v -m nameofsubset
</code>
</pre>

You can algo run everything but an specific subset

<pre>
<code>
pytest -v -m "not webtest"
</code>
</pre>

<h2> Skip tests </h2>

The simplest way to skip a test function is to mark it with the skip decorator which may be passed an optional reason

<pre>
<code>
@pytest.mark.skip(reason="no way of currently testing this")
</code>
</pre>

<h3>Conditional skip</h3>

If you wish to skip something conditionally then you can use skipif instead. Here is an example of marking a test function to be skipped when run on an interpreter earlier than Python3.6:

<pre>
<code>
@pytest.mark.skipif(sys.version_info < (3, 7), reason="requires python3.7 or higher")
</code>
</pre>

<h2>XFail: expected to fail</h2>

You can use the xfail marker to indicate that you expect a test to fail:

This test will run but no traceback will be reported when it fails. Instead, terminal reporting will list it in the “expected to fail” (XFAIL) or “unexpectedly passing” (XPASS) sections.

<pre>
<code>
@pytest.mark.xfail
def test_function():
    ...
</code>
</pre>

Alternatively, you can also mark a test as XFAIL from within the test or its setup function imperatively

<pre>
<code>
def test_function2():
    import slow_module

    if slow_module.slow_function():
        pytest.xfail("slow_module taking too long")
</code>
</pre>

<h3>Condition parameter</h3>

If a test is only expected to fail under a certain condition, you can pass that condition as the first parameter
<pre>
<code>
@pytest.mark.xfail(sys.platform == "win32", reason="bug in a 3rd party library")
</code>
</pre>

<h3>Reason parameter</h3>
You can specify the motive of an expected failure with the reason parameter
<pre>
<code>
@pytest.mark.xfail(reason="known parser issue")
</code>
</pre>

<h3>Raises parameter</h3>
If you want to be more specific as to why the test is failing, you can specify a single exception, or a tuple of exceptions
<pre>
<code>
@pytest.mark.xfail(raises=RuntimeError)
</code>
</pre>

