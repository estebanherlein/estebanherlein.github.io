---
title: "Intrusion Detection and Prevention Systems"
categories:
  - Blog
tags:
  - Cibersecurity
---

Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) are both parts of the network infrastructure. IDS/IPS compare network packets to a cyberthreat database containing known signatures of cyberattacks — and flag any matching packets.

The main difference between them is that IDS is a monitoring system, while IPS is a control system.

IDS doesn’t alter the network packets in any way, whereas IPS prevents the packet from delivery based on the contents of the packet, much like how a firewall prevents traffic by IP address.
<ul>
<li><strong>Intrusion Detection Systems (IDS):</strong> analyze and monitor network traffic for signs that indicate attackers are using a known cyberthreat to infiltrate or steal data from your network. IDS systems compare the current network activity to a known threat database to detect several kinds of behaviors like security policy violations, malware, and port scanners.</li>
<li><strong>Intrusion Prevention Systems (IPS):</strong> live in the same area of the network as a firewall, between the outside world and the internal network. IPS proactively deny network traffic based on a security profile if that packet represents a known security threat.</li>
</ul>

Many IDS/IPS vendors have integrated newer IPS systems with firewalls to create a Unified Threat Management (UTM) technology that combines the functionality of those two similar systems into a single unit. Some systems provide both IDS and IPS functionality in one unit.

<h3>Differences between them</h3>

Both IDS/IPS read network packets and compare the contents to a database of known threats. The primary difference between them is what happens next. IDS are detection and monitoring tools that don’t take action on their own. IPS is a control system that accepts or rejects a packet based on the ruleset.

IDS requires a human or another system to look at the results and determine what actions to take next, which could be a full time job depending on the amount of network traffic generated each day. IDS makes a better post-mortem forensics tool for the CSIRT to use as part of their security incident investigations.

The purpose of the IPS, on the other hand, is to catch dangerous packets and drop them before they reach their target. It’s more passive than an IDS, simply requiring that the database gets regularly updated with new threat data.

<i>Point of emphasis: IDS/IPS are only as effective as their cyberattack databases. Keep them updated and be prepared to make manual adjustments when a new attack breaks out in the wild and/or the attack signature isn’t in the database.</i>

<h3> What makes them a critical part of every Security Operation </h3>

Security teams face an ever-growing threat of data breaches and compliance fines while continuing to struggle with budget limitations and corporate politics. IDS/IPS technology covers specific and important jobs of a cybersecurity strategy:
<ul>
<li><strong>Automation:</strong> IDS/IPS systems are largely hands-off, which makes them ideal candidates for use in the current security stack. IPS provides the peace of mind that the network is protected from known threats with limited resource requirements.</li>
<li><strong>Compliance:</strong> Part of compliance often requires proving that you have invested in technologies and systems to protect data. Implementing an IDS/IPS solution checks off a box on the compliance sheet and addresses a number of the CIS Security controls. More importantly, the auditing data is a valuable part of compliance investigations.</li>
<li><strong>Policy enforcement:</strong> IDS/IPS are configurable to help enforce internal security policies at the network level. For example, if you only support one VPN, you can use the IPS to block other VPN traffic.</li>
</ul>