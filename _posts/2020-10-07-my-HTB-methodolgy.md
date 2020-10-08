---
title: "My HTB methodology"
categories:
  - Blog
tags:
  - Hack the box
  - CTF
---

When I started hacking HTB boxes I felt lost. 

This was more than a year ago, the labs for new users had not yet been created

While trying to find a methodology or a process that could be tested and reused I turned to pieces of knowledge that I already understood.

I decided to use the scientific method

<h2>A Scientific Method spin-off</h2>

Since we have to start somewhere let's start with its definition

> A method of procedure consisting in systematic observation, measurement, and experiment; and the formulation, testing, and modification of hypotheses

>Wikipedia


Everybody knows you can rely on Wikipedia for an answer on any topic, but I like the next one better.

>A method of research in which a problem is identified, relevant data is gathered, a hypothesis is formulated from this data, then the hypothesys is empirically tested, as you experiment you may change your hypotesis to fit your results

>Ducksters.com

Although both are correct the latter seems to be easier to grasp.

<h2>My HTB methodology</h2>

Let's identify our objective.

In HackTheBox we have several active machines ready to be owned. This is accomplished through the ex-filtration of 2 files or flags. 

user.txt and root.txt.

In order to own them all we will collect copious amounts of information that may or may not be relevant. 

To order this chaos we'll define a methodology, it's life-cycle and the data we seek.

<h3>LIFE CYCLE OF A PENETRATION TEST</h3>

UNTIL ROOT FLAG IS OWNED:

	1- BOX ENUMERATION
		PORT SCANNING
		SERVICE ENUMERATION
		HTTP ENUMERATION
	2- DATA ANALYSIS
	3- VULNERABILITY EXPLOITATION
	4- CONTROL

>Collect as much information as possible, organize your collected data and then the path should reveal itself

>pry0cc

There are four stages to my pentest cycle:

**Enumeration**
Gather as much relevant information as possible to identify potential security flaws

**Analysis**
Organize the information in data sets, identify attack surfaces and formulate our penetration plan

**Exploitation**
(the "I'm in" step) Get remote code execution through a security flaw

**Control** 
After a successful or failed exploitation we take time to check our results against our hypotheses. 

**If everything went smoothly we get to cat the user or the root flag, if the plan fails you fall back to enumeration and/or Analysis and reiterate.**


<h3>Don't fall into the rabbit holes</h3>

During this process you are likely to find yourself at points where everything is confusing.

Boxes where you cannot find exploitable services, open ports or where despite reading all the relevant documentation you cannot identify the entry point.

Time and energy are scarce resources, do not make hasty decisions.

Do not fall in the so-called rabbit holes (a metaphor for something that transports someone into a wonderfully,or not so wonderfully, surreal state)

It is common among creators to put services or applications that seem to be the entry point but are nothing more than traps to waste your time.

You should never work aimlessly, if you are not sure that the direction you are taking is the right one you should take a rest or talk to other pentesters about the problem.

Maybe search the HTB forums for some guidance.
