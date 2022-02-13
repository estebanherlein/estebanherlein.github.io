---
title: "Passive Attacks on Networks"
categories:
  - Blog
tags:
  - Cibersecurity
---

Attacks can be categorized in two main types: <strong>"Passive"</strong> when a network intruder intercepts data traveling through the network, and <strong>"Active"</strong> in which an intruder initiates commands to disrupt the network's normal operation.

<h2>Passive attack</h2>

<h3>Traffic analysis</h3>

Traffic analysis attacks are based on what the attacker hears in the network. However, in this type of attack, the attacker does not have to compromise the actual data. The attacker simply listens to the network communication to perform traffic analysis to determine the location of key nodes, the routing structure, and even application behavior patterns.

<strong>What Can Traffic Analysis Reveal About You?</strong>

Encrypting traffic in most cases only secures the content of the traffic. But an attacker can still obtain some information from it. 
<ul>
<li><strong>Metadata</strong><br>
An attacker can’t read the actual messages because the traffic is encrypted. But by analyzing the (encrypted) traffic, they can learn, for example, when and how many messages were sent. Even this simple information can be valuable with the use of some inductive reasoning</li>

<li><strong>Patterns</strong><br>
By searching for patterns in captured traffic, an attacker may be able to figure out when you typically wake up and go to sleep. Add the device name and location to that, and now the attacker knows when you leave your house and when you usually come back.

Even lack of traffic can say something. If it breaks the pattern, it can mean that you went on vacation (which means that it’s a good time to break into your house). Imagine how much an attacker can learn by analyzing traffic from your company office or your data center.</li>

<li><strong>Advanced Analysis</strong><br>

In some scenarios, an attacker can use traffic analysis as a base for other attacks. Take SSH, for example. Every time you press a key on your keyboard, SSH sends a separate IP packet. By analyzing these packets, an attacker can distinguish the timing between key presses. They can then use this information then, to guess users’ password lengths. This can, in effect, help an attacker to narrow down brute force attacks.</li>

<li><strong>Passive Reconnaissance</strong><br>

Traffic analysis can also help attackers understand the network structure and pick their next target. For example, if there is much more traffic coming to and from one specific node, it’s probably a good target for trying more active attacks.

On the other hand, a server that doesn’t get many connections may be an easy target. There is a chance that it’s a less important server or even a test server, and therefore, it may be less secure. Now imagine we apply this approach to military traffic. By analyzing that traffic, a hacker may try to find the location of a command center.</li>
</ul>


<h3>Eavesdropping</h3>

An eavesdropping attack occurs when an attacker intercepts, deletes, or modifies data that is transmitted between two devices. Eavesdropping, also known as sniffing or snooping, relies on unsecured network communications to access data in transit between devices.

To further explain the definition, it typically occurs when a user connects to a network in which traffic is not secured or encrypted and sends sensitive business data to a colleague. The data is transmitted across an open network, which gives an attacker the opportunity to exploit a vulnerability and intercept it via various methods. 

Eavesdropping attacks can often be difficult to spot. Unlike other forms of cyber attacks, the presence of listening device may not adversely affect the performance of devices and networks.


<strong>Eavesdropping Methods</strong>

With eavesdropping, attackers can use various methods to launch attacks that typically involve the use of various eavesdropping devices to listen in on conversations and review network activity.

Despite all the number of technological advances making digital eavesdropping increasingly easy in this day and age, many attacks still rely on intercepting telephones. That is because telephones have electric power, built-in microphones, speakers, space for hiding bugs, and are easy to quickly install a bug on. 

<ul>
<li><strong>Pickup Device</strong><br>

Attackers can use devices that pick up sound or images, such as microphones and video cameras, and convert them into an electrical format to eavesdrop on targets. Ideally, it will be an electrical device that uses power sources in the target room, which eliminates the need for the attacker to access the room to recharge the device or replace its batteries. 

Some listening devices are capable of storing digital information and transmitting it to a listening post. </li>

<li><strong>Transmission Link</strong><br>

A transmission link between a pickup device and the attacker’s receiver can be tapped for eavesdropping purposes. This can be done in the form of a radiofrequency transmission or a wire, which includes active or unused telephone lines, electrical wires, or ungrounded electrical conduits. Some transmitters can operate continuously, but a more sophisticated approach involves remote activation.</li>

<li><strong>Listening Post</strong><br>

A listening post is used to transmit conversations intercepted by bugs on telephones. When a telephone is picked up to make or take a call, it triggers a recorder that is automatically turned off when the call is ended. 

Listening posts are secure areas in which signals can be monitored, recorded, or retransmitted by the attacker for processing purposes. It can be located anywhere from the next room to the telephone up to a few blocks away. The listening post will have voice-activated equipment available to eavesdrop on and record any activity.</li>

<li><strong>Weak Passwords</strong><br>

Weak passwords make it easier for attackers to gain unauthorized access to user accounts, which gives them a route into corporate systems and networks. This includes hackers being able to compromise confidential communication channels, intercept activity and conversations between colleagues, and steal sensitive or valuable business data.</li>

<li><strong>Open Networks</strong><br>

Users who connect to open networks that do not require passwords and do not use encryption to transmit data provide an ideal situation for attackers to eavesdrop. Hackers can monitor user activity and snoop on communications that take place on the network.</li>
</ul>