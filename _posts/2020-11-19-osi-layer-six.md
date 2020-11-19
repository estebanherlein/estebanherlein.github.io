---
title: "OSI model, Presentation Layer "
categories:
  - Blog
tags:
  - Networking theory
  - OSI model
---

The presentation layer ensures the information that the application layer of one system sends out is readable by the application layer of another system. For example, a PC program communicates with another computer, one using extended binary coded decimal interchange code (EBCDIC) and the other using ASCII to represent the same characters. If necessary, the presentation layer might be able to translate between multiple data formats by using a common format.


Serialization of complex data structures into flat byte-strings (using mechanisms such as TLV or XML) can be thought of as the key functionality of the presentation layer.

Encryption is typically done at this level too, although it can be done on the application, session, transport, or network layers, each having its own advantages and disadvantages. 

Decryption is also handled at the presentation layer. For example, when logging on to bank account sites the presentation layer will decrypt the data as it is received.

In many widely used applications and protocols, no distinction is made between the presentation and application layers. For example, HyperText Transfer Protocol (HTTP), generally regarded as an application-layer protocol, has presentation-layer aspects such as the ability to identify character encoding for proper conversion, which is then done in the application layer.

Within the service layering semantics of the OSI network architecture, the presentation layer responds to service requests from the application layer and issues service requests to the session layer.

<h1>Services</h1>

<ul>
<li>Data conversion</li>
<li>Character code translation</li>
<li>Compression</li>
<li>Encryption and Decryption
</li>
</ul>

<h1>Protocols</h1>

The Presentation OSI Layer is usually composed of 2 sublayers

<h2>CASE</h2>
<ul>

<li>ACSE	Association Control Service Element</li>
<li>ROSE	Remote Operation Service Element</li>
<li>CCR	Commitment Concurrency and Recovery</li>
<li>RTSE	Reliable Transfer Service Element</li>
</ul>
<h2>SASE</h2>

<ul>

<li>FTAM	File Transfer, Access and Manager</li>
<li>VT	Virtual Terminal</li>
<li>MOTIS	Message Oriented Text Interchange Standard</li>
<li>CMIP	Common Management Information Protocol</li>
<li>JTM	Job Transfer and Manipulation</li>
<li>MMS	Manufacturing Messaging Service</li>
<li>RDA	Remote Database Access</li>
<li>DTP	Distributed Transaction Processing</li>
</ul>