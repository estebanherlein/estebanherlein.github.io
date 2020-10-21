---
title: "User Datagram Protocol"
categories:
  - Blog
tags:
  - Networking theory
  - UDP
---

UDP is a transport layer protocol that serves as an alternative to TCP.

This protocol is intended to minimize the amount of traffic that is sent on top of the data stream .

This is achieved by implementing the connections without a triple handshake.

As its header is concise and only has relevant information, there is more space in the package for the data.

As acknowledgments are not implemented, it is possible and probable that some packets are lost without the possibility of claiming them from the sender.

You may want to read the article on <a href="../transport-control-protocol/">TCP</a>

<h2>UDP Features</h2>

<ul>
<li> No connection needs to be established: this lack of connection between sender and receiver makes you save time and bits </li>
<li> Socket dependant: Although there is no use for a triple handshake data streams are sent from socket to socket. There must be one waiting for your data on the other side of the stream.
</li>
<li>Fast and lag-free communication : Thanks to the lack of connection and the fact that lost packets are not re-sent, on TCP when a packet is lost the receiver asks the sender to re-send the lost package. This simple action makes the transmission more time and resource consuming.
</li>
<li>No guarantee of security or integrity of the data: Because of the lack of ACK packets there is no way of being sure that the packets have arrived in order, nor that the packets have arrived without being intercepted and or changed. The application layer has to implement it's own correction and protection measures.
</li>
</ul>

<h2>What kind of app makes use of the User Datagram Protocol?</h2>

There are three types of applications that can benefit from the User Datagram Protocol.

<ol>
<li>Apps that can tolerate some measure of data loss but can not tolerate lag</li>

<li>Apps with simple request and response transactions</li>

<li>One-way communications where reliability is not required or where it can be managed by the application</li>
</ol>

VoIP and Internet Protocol Television (IPTV), use UDP. TCP reliability mechanisms present a certain degree of delay that can be perceived in the quality of sound or video that is received.

Other types of applications suitable for UDP are those that use simple request and response transactions. This is when a host sends a request and there is a possibility that it may or may not receive a response (DHCP, DNS, SNMP, TFTP)



