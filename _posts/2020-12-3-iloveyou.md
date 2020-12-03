---
title: "ILOVEYOU"
categories:
  - Blog
tags:
  - Malware
  - Worms
---

ILoveYou (or VBS / LoveLetter) is a worm written in VBScript. In May 2000, it infected approximately 50 million computers, causing losses of more than 5.5 billion dollars.

<h1>Propagation method</h1>

It reaches the user in an e-mail whose Subject is: 'ILOVEYOU' and includes a file called 'LOVE-LETTER-FOR-YOU.TXT.vbs'. When this worm runs, it creates multiple copies of itself on your hard drive. After this, the worm creates several entries in the Windows configuration registry.

VBS / LovelLetter checks, in the Windows SYSTEM directory, the existence of the WinFAT32.exe file. If it finds it, it generates a random number between 1 and 5, and depending on the result, it creates the registry entry 'HKCU \ Software \ Microsoft \ InternetExplorer \ Main \ Start, to which it assigns a value to download the file WIN- BUGSFIX. EXE.

After performing this operation, the worm generates, in the Windows SYSTEM directory, the file LOVE-LETTER-FOR-YOU.HTM, which will be the one that will subsequently  be send via IRC. The worm then sends itself to all the addresses it finds in the Microsoft Outlook address book.

<h1>Workflow </h1>

When it has already been mailed, VBS / LoveLetter performs its destructive effect. Specifically, it searches the path of the hard drive and all network drives for files with the extension vbs, vbe, js, jse, css, wsh, sct and hta. When it finds them, it overwrites them with its code, modifies their size and changes their extension to VBS, which leads to the loss of all the information contained in the files. If the files it finds have a jpg or jpeg extension, it also overwrites them, changes their size and adds the VBS extension at the end (leaving them as jpg.vbs or jpeg.vbs).

If VBS / LoveLetter finds a file with an mp3 or mp2 extension, it generates a copy of itself with the name of the found file and adds the VBS extension, hiding the original files. The worm also checks to see if any of the following files are found in the directory in which it is being searched: mirc32.exe, mlinnk32.exe, mirc.ini, scrip.ini or mirc.hlp. 

If he finds them, he creates the file 'script.ini', which will be in charge of sending the LOVE-LETTER-FOR-YOU.HTM file via IRC to anyone who connects to the same channel as him.

<h1>Effects and damages caused</h1>

The worm spread rapidly around the world. As of May 13, 2000, 50 million infections had been reported around the globe, a figure that represented 10 percent of all computers with an Internet connection at that time. 

It attacked the Pentagon, the CIA, the British Parliament and big business. In Spain, for example, 80% of companies suffered from worm attacks. 

The amount of damage caused was estimated to be between 5.5 to 8.7 billion dollars, derived mainly from work removing the worms from infected systems.


<h1>Origin</h1>

Investigators traced the virus to an email address registered in Manila, the capital of the Philippines.

The owners's brother was Onel de Guzmán, a computer science student at the city's AMA Computer College.

He was a member of an underground hacking group called Grammersoft and quickly became the main suspect in a police investigation.
Love bug

The accused's lawyer organized a press conference on May 11.

At the appearance, in which De Guzmán gave the impression that he did not speak English well, when asked if he could have accidentally released the virus, he said: "It is possible."

The Philippines did not have a law on hacking at the time, so neither De Guzmán nor anyone else was prosecuted.

Suspicion also fell on De Guzman's fellow student, Michael Buen, who has been cited online as co-author of the worm.

This fact made clear in the Philippines the need to have legislation regulating Internet activity. 

For this reason, on June 14, 2000, Law No. 8,792 was enacted, which currently, in its Section 33, sanctions the introduction of computer viruses and other malware with the aim of damaging data messages and electronic documents. 

However, it could not be applied against Onel de Guzmán, since the criminal act (the release of the worm) had been executed before the enactment of the law.
