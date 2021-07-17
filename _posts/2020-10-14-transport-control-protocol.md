---
title: "Transport Control Protocol"
categories:
  - Blog
tags:
  - Networking Theory
---

If a tree falls in a forest and no one is around to hear it, does it make a sound?


The transport control protocol (TCP) is what programmers around the world use to carry out point-to-point transmissions

We use it to establish a connection with another device ensuring that it exists, is willing and available to exchange data.

To make a connection, the essential thing is to have 2 end devices, usually called client and server.

The two ends use a combination of IP and port called a socket to establish the connection.

To make sure that the other end exists, is available and ready, a small dance is performed, this dance is called <b>triple handshake</b>( aka SYN-SYN/ACK-ACK) .

<h2>SYN -SYN/ACK -ACK </h2>

The specific sequence that makes up this dance is detailed below:

<ol>
<li>the client that wishes to establish the connection sends to the server a SYN type packet with a random sequence number that will serve to sort the packets at both ends</li>
<li>When the server receives this packet, it takes the sequence number, adds one to it and (if it is willing to establish the connection) it sends a SYN-ACK packet to the client attaching to it it's own sequence number</li>
<li>To end this dance the client sends an ACK packet to the server with the server's sequence number plus one. Establishing the connection and beginning to transmit the data flow</li>
</ol>

<h2>Controlled interruption</h2>

In addition to providing the framework to initiate connections, it also provides a framework to terminate them after the data stream was successfully transmitted.

<ol>
<li>the client that wishes to end the connection sends a FIN type packet with a random sequence number that will serve to sort the packets at both ends</li>
<li>When the server receives this packet, it takes the sequence number, adds one to it and it sends a ACK packet back, if the server has already finished sending his own data to the client  it sends a FIN packet attaching to it it's own sequence number</li>
<li>To end this dance the client sends an ACK packet to the server with the server's sequence number plus one. Closing the connection and ending the data flow</li>
</ol>

<h2>Useful characteristics of the TCP protocol</h2>

<ul>
<li>Establish neat ways to start and end communications</li>
<li>Allows data to be formed into packets of varying length to be sent and received through Layer 3</li>
<li>Allows devices to order the packets that are sent and received through layer 3</li>
<li>allows data multiplexing (to send and receive multiple data streams at the same time) </li>
</ul>
