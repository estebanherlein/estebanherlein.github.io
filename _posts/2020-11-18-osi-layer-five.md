---
title: "OSI model, Session Layer "
categories:
  - Blog
tags:
  - Networking Theory
  - OSI model
---

The session layer provides the mechanism for opening, closing and managing a session between end-user application processes, i.e., a semi-permanent dialogue. 

Communication sessions consist of requests and responses that occur between applications. Session-layer services are commonly used in application environments that make use of remote procedure calls (RPCs).

An example of a session-layer protocol is the OSI protocol suite session-layer protocol, also known as X.225 or ISO 8327.

In case of a connection loss this protocol may try to recover the connection. If a connection is not used for a long period, the session-layer protocol may close it and re-open it. 

It provides for either full duplex or half-duplex operation and provides synchronization points in the stream of exchanged messages.

Within the service layering semantics of the OSI network architecture, the session layer responds to service requests from the presentation layer and issues service requests to the transport layer.


<h1>Services</h1>
<ul>
<li>Authentication</li>
<li>Authorization</li>
<li>Session restoration</li>

</ul>


<h1>Protocols</h1>
<ul>

<li>ADSP	AppleTalk Data Stream Protocol</li>
<li>ASP	AppleTalk Session Protocol</li>
<li>H.245	Call Control Protocol for Multimedia Communication</li>
<li>ISO-SP	OSI session-layer protocol (X.225, ISO 8327)</li>
<li>iSNS	Internet Storage Name Service</li>
<li>L2F	Layer 2 Forwarding Protocol</li>
<li>L2TP	Layer 2 Tunneling Protocol</li>
<li>NetBIOS	Network Basic Input Output System</li>
<li>PAP	Password Authentication Protocol</li>
<li>PPTP	Point-to-Point Tunneling Protocol</li>
<li>RPC	Remote Procedure Call Protocol</li>
<li>RTCP	Real-time Transport Control Protocol</li>
<li>SMPP	Short Message Peer-to-Peer</li>
<li>SCP	Session Control Protocol</li>
<li>SOCKS	the SOCKS internet protocol, see Internet socket</li>
<li>ZIP	Zone Information Protocol</li>
<li>SDP	Sockets Direct Protocol</li>

</ul>