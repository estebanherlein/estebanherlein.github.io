---
title: "On subnetworks "
categories:
  - Blog
tags:
  - Networking theory
---

The Internet is a large network made up of a finite number of devices.
<b>A finite but extremely large number</b>


To order this almost incalculable number of devices and in order to solve some limitations of standardized technologies(such as IPV4 limited addresses), the division of networks into subnets is carried out.

You may want to read the article on <a href="../Internet-protocol/">IPV4</a> before proceeding

<h2> How does a packet know where to go</h2>

Network addresses are hierarchical, they are made up of 2 parts, one called the network portion and another one called the host portion.

This allows network devices to quickly identify if a packet is going to a host within the same network or if the packet is going somewhere else on the internet.

The network address portion and the host portion is defined by the network mask

<h2>Network mask</h2>

Basically it is a notation that quickly shows which of the 32 bits that make up the address are fixed and which are variable.

For example let's take the following address

>192.168.1.xxx

The first 3 octets are the network portion, these are fixed and all network devices will share them.

The last octet will be the host portion, all devices connected to the network must necessarily have a unique host number.

The network mask can be defined as:

> 255.255.255.0

This means that the first 24 bits of the address will be fixed and the last 8 bits will be variable

<h3>CIDR notation</h3>

>192.168.1.0/24

This means the exact same thing but in a compact manner.

In the previous example we left 8 bits for the host portion, which limits us to 2<sup>8</sup> (256) possible addresses.

Due to technicalities, the maximum number of addresses can be calculated using the following rule:

Maximum number of hosts = (2<sup>number of hosts bits</sup>) - 2

This means that no more than 254 devices can exist on the 192.168.1.0/24 subnet.

<h2> How does the internet benefit from this?</h2>

Subneting is a fundamental part of the internet protocol that allows routers to carry out and speed up the distribution of ip packets.

when the routing hardware receives a packet, it takes the ip header and checks if the receiver and sender are on the same subnet

In the case that they are in the same subnet, the packet is directed to the end device

In the event that the destination device exists outside the subnet, the packet is forwarded to the next routing device so that it can check if the destination subnet exists in its tables.

this process is repeated iteratively until the packet reaches its destination
