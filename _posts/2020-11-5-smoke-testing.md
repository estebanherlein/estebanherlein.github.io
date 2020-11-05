---
title: "Smoke testing"
categories:
  - Blog
tags:
  - software testing
---

A test suite that covers the main functionality of a component or system to determine whether it works properly before planned testing begins, also known as “Build Verification Testing”.

It can also be used to decide whether to announce a production release or to revert.

The term ‘smoke testing’ came to software testing from a similar type of hardware testing in which the device passed the test if it did not catch fire (or smoked) the first time it was turned on.


Smoke test helps in exposing integration and major problems early in the cycle. It can be conducted on both newly created software and enhanced software. 

Smoke test is performed manually or with the help of automation tools/scripts. If builds are prepared frequently, it is best to automate smoke testing.

As and when an application becomes mature, with addition of more functionalities etc, the smoke test needs to be made more expansive. Sometimes, it takes just one incorrect character in the code to render an entire application useless.


<h1>Advantages</h1>

<ul>
<li>Exposes integration issues.</li>
<li>Uncovers problems in early stages of development.</li>
<li>Provides some level of confidence that changes to the software have not adversely affected major areas (areas covered by smoke testing)</li>
</ul>

<h2>How is smoke testing done</h2>

Whenever there is a new build the QA team defines essential functionality and the smoke test is performed on it. After this the team contrasts the expected results with those obtained to identify showstoppers


<h2>Testing Cycle</h2>
<img src="https://i.imgur.com/fnClFOE.png" alt="Smoke Test cycle" >