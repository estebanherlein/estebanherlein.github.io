---
title: "Threat Modeling"
categories:
  - Blog
tags:
  - SDLC
  - Security
---

Threat modeling works to identify, communicate, and understand threats and mitigations within the context of protecting something of value.

A threat model is a structured representation of all the information that affects the security of an application. In essence, it is a view of the application and its environment through the lens of security.

Threat modeling can be applied to a wide range of things, including software, applications, systems, networks, distributed systems, Internet of Things (IoT) devices, and business processes.

<h2>Origin</h2>

IT-based threat modeling gained traction in the 1990s with the development of threat and attacker profiles. 

Microsoft introduced its <b>STRIDE</b> (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege) threat modeling methodology in 1999. 

There are many other approaches now. <b>They all involve deconstructing the elements of an application or system to identify the assets to be protected and the possible threats to be mitigated.</b>

<h2>Other Methodologies</h2>

 A threat modeling methodology is a way to break down a complex process into smaller tasks making it easy to spot weaknesses.
<ul>
<li><b>Damage, Reproducibility, Exploitability, Affected users, Discoverability (DREAD)</b> is a quantitative risk analysis that rates, compares and prioritizes a cyberthreat's severity.</li>
<li><b>Operationally Critical Threat, Asset, and Vulnerability Evaluation (OCTAVE)</b> provides an asset- and risk-based strategic assessment that is customizable for specific security objectives and risk management It was developed by Carnegie Mellon University for the Department of Defense.</li>
<li><b>Trike</b> is an open source, risk-centric methodology that ensures each asset's assigned risk level is OK with all interested parties</li>
<li><b>National Institute of Standards and Technology's Guide to Data-Centric System Threat Modeling</b> focuses on protecting particular data types within systems. It models aspects of attack and defense for selected data.</li>
</ul>

<h2>Contents of a Threat Model</h2>

<ul>
<li>Description of the subject to be modeled</li>
<li>Assumptions that can be checked or challenged in the future as the threat landscape changes</li>
<li>Potential threats to the system</li>
<li>Actions that can be taken to mitigate each threat</li>
<li>A way of validating the model and threats, and verification of success of actions taken</li>
</ul>

<h2>Best practices</h2>

There are several steps to take to ensure an effective approach to threat modeling. Some of them include:
<ul>
<li><b>Start early.</b> Threat modeling can be done at any time during a project, but earlier is better as the findings can help ensure the design is secure. It is also quicker and cheaper to add security controls early in the build process.</li>
<li><b>Get a lot of input.</b> Soliciting input from a variety of stakeholders helps identify the widest range of potential adversaries, motives, threats, and where the most vulnerable components reside.</li>
<li><b>Use a variety of tools.</b> There are many tools available, including some unusual approaches. For instance, the University of Washington's Security Cards are a brainstorming tool that helps discover less common or novel attacks and how best to respond to them.</li>
<li><b>Understand risk tolerance.</b> Business owners in particular must fully understand and communicate their risk-tolerance levels so the correct approaches to threat mitigation can be chosen to ensure business goals are met.</li>
<li><b>Educate everyone.</b> Train everyone involved in the different aspects of threat modeling, so their inputs can be maximized. As always with security, threat modeling is an iterative development</li>
</ul>