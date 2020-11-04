---
title: "Fuzz testing"
categories:
  - Blog
tags:
  - software testing
---

Fuzzing or fuzz testing is an automated software testing technique that involves providing invalid, unexpected, or random data as inputs to a computer program.

The program is then monitored for exceptions such as crashes, failing built-in code assertions, or potential memory leaks. 

Typically, fuzzers are used to test programs that take structured inputs. This structure is specified, e.g., in a file format or protocol and distinguishes valid from invalid input.


An effective fuzzer generates semi-valid inputs that are "valid enough" in that they are not directly rejected by the parser, but do create unexpected behaviors deeper in the program and are "invalid enough" to expose corner cases that have not been properly dealt with.

For the purpose of security, input that crosses a trust boundary is often the most interesting.

For example, <b>it is more important to fuzz code that handles the upload of a file by any user</b> than it is to fuzz the code that parses a configuration file that is accessible only to a privileged user. 

<h1>Types of fuzzers</h1>

<ul>
<li>Reuse of existing input seeds <br>
A <b>mutation-based</b> fuzzer leverages an existing corpus of seed inputs during fuzzing. It generates inputs by modifying (or rather mutating) the provided seeds. For example, when fuzzing the image library libpng, the user would provide a set of valid PNG image files as seeds while a mutation-based fuzzer would modify these seeds to produce semi-valid variants of each seed.<br>
A <b>generation-based</b> fuzzer generates inputs from scratch. For instance, a smart generation-based fuzzer takes the input model that was provided by the user to generate new inputs. Unlike mutation-based fuzzers, a generation-based fuzzer does not depend on the existence or quality of a corpus of seed inputs.</li>
<li>Aware of input structure<br>
A smart fuzzer leverages the input model to generate a greater proportion of valid inputs. For instance, if the input can be modelled as an abstract syntax tree, then a smart mutation-based fuzzer would employ random transformations to move complete subtrees from one node to another. If the input can be modelled by a formal grammar, a smart generation-based fuzzer would instantiate the production rules to generate inputs that are valid with respect to the grammar. However, generally the input model must be explicitly provided, which is difficult to do when the model is proprietary, unknown, or very complex.</li>
<li>Aware of program structure<br>

Typically, a fuzzer is considered more effective if it achieves a higher degree of code coverage. The rationale is, if a fuzzer does not exercise certain structural elements in the program, then it is also not able to reveal bugs that are hiding in these elements. Some program elements are considered more critical than others. For instance, a division operator might cause a division by zero error, or a system call may crash the program.<br>

A <b>black-box fuzzer</b> treats the program as a black box and is unaware of internal program structure. For instance, a random testing tool that generates inputs at random is considered a blackbox fuzzer. Hence, a blackbox fuzzer can execute several hundred inputs per second, can be easily parallelized, and can scale to programs of arbitrary size. <br>

A <b>white-box fuzzer</b> leverages program analysis to systematically increase code coverage or to reach certain critical program locations. If the program's specification is available, a whitebox fuzzer might leverage techniques from model-based testing to generate inputs and check the program outputs against the program specification. <br>
</li>

</ul>

<h1>Use cases</h1>

Fuzzing is used mostly as an automated technique to expose vulnerabilities in security-critical programs that might be exploited with malicious intent. More generally, fuzzing is used to demonstrate the presence of bugs rather than their absence. 

<h2>Exposing bugs</h2>

In order to expose bugs, a fuzzer must be able to distinguish expected from unexpected program behavior. However, a machine cannot always distinguish a bug from a feature. In automated software testing, this is also called the test oracle problem.

Typically, a fuzzer distinguishes between crashing and non-crashing inputs in the absence of specifications and to use a simple and objective measure. Crashes can be easily identified and might indicate potential vulnerabilities. However, the absence of a crash does not indicate the absence of a vulnerability. 

To make a fuzzer more sensitive to failures other than crashes, sanitizers can be used to inject assertions that crash the program when a failure is detected.

There are different sanitizers for different kinds of bugs:

<ul>
<li>to detect memory related errors, such as buffer overflows and use-after-free (using memory debuggers such as AddressSanitizer)</li>
<li>to detect race conditions and deadlocks (ThreadSanitizer)</li>
<li>to detect undefined behavior (UndefinedBehaviorSanitizer)</li>
<li>to detect memory leaks (LeakSanitizer)</li>
<li>to check control-flow integrity (CFISanitizer)</li>
</ul>

Fuzzing can also be used to detect "differential" bugs if a reference implementation is available. 

For automated regression testing, the generated inputs are executed on two versions of the same program. For automated differential testing, the generated inputs are executed on two implementations of the same program . If the two variants produce different output for the same input, then one may be buggy and should be examined more closely.
 
<h2>Validating static analysis reports</h2>

Static program analysis analyzes a program without actually executing it. This might lead to false positives where the tool reports problems with the program that do not actually exist. Fuzzing in combination with dynamic program analysis can be used to try to generate an input that actually witnesses the reported problem.

<h2>Browser security</h2>
Modern web browsers undergo extensive fuzzing. The Chromium code of Google Chrome is continuously fuzzed by the Chrome Security Team with 15,000 cores. For Microsoft Edge and Internet Explorer, Microsoft performed fuzzed testing with 670 machine-years during product development, generating more than 400 billion DOM manipulations from 1 billion HTML files.

