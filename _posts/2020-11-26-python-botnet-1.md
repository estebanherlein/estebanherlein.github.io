---
title: "Python Botnet part 1"
categories:
  - Blog
tags:
  - Remote administration
  - Malware
  - Python
---


Throughout this series of articles I will design and write the necessary code to set up a botnet in python.

I am aware that distributing malicious code written in python is complicated because not all potential clients have python installed. (particularly computers running windows os)

This makes the file to distribute larger since it will contain both client code and the binaries to interpret and execute python code.

However, since python code is easy to both write and read, it will be useful for educational purposes.


This apps will be developed Through test driven design.

Test-driven design is a software engineering practice that involves two other practices: Test First Development and Refactoring. 

First, a test is written and it is verified that the new test fails. 

Next, the code that makes the test pass is implemented successfully, and then the written code is refactored.

The purpose of test-driven development is to achieve clean code that works. 

<b>The idea is that the requirements are translated into tests, in this way, when the tests pass, it will be guaranteed that the software meets the requirements that have been established.</b>



<h1>Botnet workflow</h1>


<ol>
<li>Initialize the multi-threaded server.</li>
<li>Initialize the client and establish a direct connection to the server.</li>
<li>Generate a stable tunnel for client-server interaction.</li>
<li>Collect information on the client side.</li>
<li>Send it to the server and store it.</li>
<li>Define the next communication date, dismantle the tunnel and maintain radio silence.</li>

</ol>



<h1>Backlog</h1>



<h2>Tests </h2>

[ ] client side can generate a socket

[ ] server side can create at least two sockets and serve two clients at the same time

[ ] client side must be able to receive orders and react to them

[ ] client side must be able to collect local information

[ ] client side must be able to sleep and awake on demand

[ ] client side must be able to publish himself to the server

[ ] client side must be able to persist on it's system

<h2>Botnet Utils class</h2>

[ ] Generate socket

[ ] send data through socket

[ ] receive data through socket

<h2>Client class</h2>

[ ] Receive orders and react to them

[ ] collect local information 

[ ] publish itself to the server

Potential Orders: 
<ul>
<li>sleep for x seconds</li>
<li>collect information</li>
<li>search for peers on local network</li>
<li>persist</li>
</ul>

<h2>Server class</h2>
<ul>
<li> Manage multiple sockets in parallel</li>
<li>Give orders</li>
<li>receive incoming connections on default socket and  establish a new one on a different port.</li>
<li> Manage client database</li>
</ul>


You can find this project's respository on https://github.com/estebanherlein/python-botnet