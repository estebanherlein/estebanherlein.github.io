---
title: "OSI model, Data link layer "
categories:
  - Blog
tags:
  - Networking theory
  - OSI model
---

The data link layer or layer 2 is the second layer of the OSI seven-layer model of computer networks. 

This layer transfers data between adjacent network nodes on a wide area network (WAN) or between nodes on the same local area network (LAN). 

The data link layer provides the functional and procedural means to transfer data between network entities and could provide the means to detect and possibly correct errors that may occur at the physical layer.

The data link layer deals with the local delivery of frames between devices on the same LAN. <b>Data link frames, as these protocol data units are called, do not cross the boundaries of a local network.</b> 

Internetwork routing and global addressing are upper layer functions, allowing data link protocols to focus on local delivery, routing, and media arbitration. 

In this way, the data link layer is analogous to a neighborhood traffic police; endeavors to arbitrate between competing parties for access to a medium, regardless of its final destination. 

When devices try to use a medium simultaneously, image collisions occur. Data link protocols specify how devices detect and recover from such collisions, and can provide mechanisms to reduce or prevent them.


<h1>Services</h1>
<ul>
<li>Encapsulation</li>
<li>Frame synchronization</li>
<li>Logical link control (Error & Flow control)</li>
<li>Media access control (MAC, LAN switching, Physical addressing, QaS, VLAN, ...)</li>
</ul>


<h1>Protocols</h1>
<ul>
<li>ARP		Address Resolution Protocol</li>
<li>CDP		Cisco Discovery Protocol</li>
<li>CAN		Controller Area Network</li>
<li>Ethernet	</li>
<li>EAPS	Ethernet Automatic Protection Switching</li>
<li>FDDI	Fiber Distributed Data Interface</li>
<li>Frame Relay	</li>
<li>HDLC	High-Level Data Link Control</li>
<li>IEEE 802.2		provides LLC functions to IEEE 802 MAC layers</li>
<li>IEEE 802.11		wireless LAN</li>
<li>LAPD	Link Access Procedures, D channel</li>
<li>LLDP	Link Layer Discovery Protocol</li>
<li>MPLS	Multiprotocol Label Switching</li>
<li>NDP	Nortel Discovery Protocol</li>
<li>SDN	OpenFlow</li>
<li>PPP	Point-to-Point Protocol</li>
<li>SLIP	Serial Line Internet Protocol (obsolete)</li>
<li>SMLT	Split multi-link trunking</li>
<li>IEEE 802.1aq	Shortest Path Bridging</li>
<li>UDLD	Unidirectional Link Detection</li>
</ul>