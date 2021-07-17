---
title: "Birthday problem"
categories:
  - Blog
tags:
  - Probability Theory
---

The birthday problem or birthday paradox concerns the probability that, in a set of n randomly chosen people, some pair of them will have the same birthday. 

In a group of 23 people, the probability of a shared birthday is 50%, while a group of 70 has a 99.9% chance of a shared birthday. (By the pigeonhole principle, the probability reaches 100% when the number of people reaches 367, since there are only 366 possible birthdays, including February 29.) 

<b>The birthday problem is a veridical paradox: a proposition that at first appears highly counterintuitive, but is in fact true.</b>

While it may seem surprising that only 23 individuals are required to reach a 50% probability of a shared birthday, this result is made more intuitive by considering that the comparisons of birthdays will be made between every possible pair of individuals.

With 23 individuals, there are 23 × 22 / 2 = 253 pairs to consider, which is well over half the number of days in a year (182.5 or 183). 

<h2>Explanation: Counting Pairs</h2>

With 23 people we have 253 pairs:

<pre><code>(23 × 22) / 2 = 253</code></pre>

The chance of 2 people having different birthdays is:

<pre><code>1 - (1/365) = (364/365) = 0.9972</code></pre>

Makes sense, right? When comparing one person's birthday to another, in 364 out of 365 scenarios they won't match. Fine.

But making 253 comparisons and having them all be different is like getting heads 253 times in a row -- you had to dodge "tails" each time.

Let's get an approximate solution by pretending birthday comparisons are like coin flips. 

We use exponents to find the probability:

<pre><code>(364/365)^253 = 0.4995</code></pre>

Our chance of getting a single miss is pretty high (99.7260%), but when you take that chance hundreds of times, the odds of keeping up that streak drop. Fast.

<h2>Lessons from the birthday paradox</h2>

<ul>
<li>√n is roughly the number you need to have a 50% chance of a match with n items.</li>
<li>√253 is about 20. This comes into play in cryptography for the birthday attack.</li>
<li>Even though there are 2128 (1^38) GUIDs, we only have 264 (1^19) to use up before a 50% chance of collision. And 50% is really, really high.</li>
<li>You only need 13 people picking letters of the alphabet to have 95% chance of a match. Try it above (people = 13, items = 26).</li>
<li>Exponential growth rapidly decreases the chance of picking unique items (aka it increases the chances of a match). Remember: exponents are non-intuitive! </li>
</ul>

<h2> Birthday problem and Hash collisions</h2>

The same logic that drives matching birthdays also drives the probability that one can find collisions with a hash function.

In other words, if you have a uniform hashing function that outputs a value between 1 and 365 for any input, the probability that two hashes would collide in a set of 23 values is also 50%

This applies to finding collisions in hashing algorithms because it’s much harder to find something that collides with a given hash than it is to find any two inputs that hash to the same value.