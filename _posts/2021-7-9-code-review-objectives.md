---
title: "Code Review List of Objectives"
categories:
  - Blog
tags:
  - software testing
  - bug hunting
  - teaching
  - Quality Assurance
---

Here are 8 specific things You should pay close attention to when conducting code reviews for tests.


<h2>Does the test verify what’s needed?</h2>

When verifying something manually, there are a lot of subconscious validations that are being made. So if anything was incorrect, we’d likely notice. Our tests are not as good at this. In fact, they will only fail if the conditions that we explicitly specify are not met. 

So when reviewing test code, make sure the test is including assertions for all that is needed.

<h2>Does the test focus on one thing?</h2>

Each test should focus on a single thing. This may be a bit confusing because I told you above to assert everything. However, all of those assertions work together to verify a single thing .

If, however, the test also verified the company’s logo or some other feature besides the main objective, that would be outside of the scope and should be it's own test.

<h2>Can the test run independently?</h2>

In addition to focusing on a single thing, each test should be independent, meaning it should not rely on other tests at all. This makes it much easier to track down failures and their root causes, and will also enable the team to run the tests in parallel to speed up execution if needed.

While the test's author may agree that tests should be isolated, they still sometimes fall into the trap of using related test runs as setup for other tests. For example, if the test is to remove an item from the cart, it’s tempting to run the “add to cart” test first and depend upon it before running the “remove from cart” test. 

<b>Call this out in reviews! Your recommendation should be that the test create and delete whatever it needs, and if possible to do this outside of the GUI.</b>

<h2>How is test data being managed?</h2>

How tests deal with test data can be the difference between a stable and reliable test suite versus a flaky and untrustworthy one. 

As each test should be developed to run independently and all tests should be able to run in parallel at the exact same time, each test should be responsible for their own test data. Trying to share data that is being manipulated is the perfect ingredient for an unreliable test. 

When the tests are running in parallel and have different expectations of the test data’s state, the tests end up failing when there’s no real issue with the application. 

<b>Recommend to the author that they create whatever data is needed for the test within the test itself.</b>

<h2>Is there a separation of concerns?</h2>

Remember, test code should be treated with the same care as feature code. That means that clean coding practices, such as separation of concerns, should be followed. The test method should only focus on putting the application in a desired state and verifying that state. The implementation of manipulating the application’s state should not be within the test itself.

Likewise, the non-test methods should not make any assertions. Their responsibility is to manipulate the state of the application, and the test’s responsibility is to verify that state. Adding assertions within non-tests decreases the reusability of those methods.

<h2>Is there anything in the test that should be a utility?</h2>

Separating concerns already addresses this in most cases, but double check that the test isn’t implementing something that can be reused by other tests. Sometimes this may be a common series of verification steps that certainly is the test’s responsibility, however, is/will be duplicated across multiple tests.

In these cases, it’s good to recommend that the author move this block of code into a utility method that can be reused by multiple tests.

<h2>Are the selectors reliable?</h2>

For GUI and mobile tests, the test's author will need to use selectors to locate and interact with the web elements. The first thing to ensure is that these locators are not within the tests themselves. 

Make sure the selectors can stand the test of time. For example, using selectors that depend on the structure of the page (e.g. indices) will only work until the structure of the page is changed.

<h2>Is the wait strategy solid?</h2>

Flag any hard-coded waits. Automated tests run faster than customers would actually interact with the product and this could lead to issues with the test, such as trying to interact with or verify something that is not yet in the desired state. To solve for this, the code needs to wait until the application is in the expected state before proceeding.

However, hard-coding a wait is not ideal. It leads to all kinds of problems such as lengthening the duration of execution, or still failing because it didn’t wait long enough.

<b>Instead, recommend that the author use conditional waits that will only pause execution for the least amount of time that is needed.</b>