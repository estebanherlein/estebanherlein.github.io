---
title: "systemd"
categories:
  - Blog
tags:
  - Linux
  -
---

systemd is a Linux initialization system and service manager that includes features like on-demand starting of daemons, mount and automount point maintenance, snapshot support, and processes tracking using Linux control groups. 

systemd provides a logging daemon and other tools and utilities to help with common system administration tasks.

Notably, systemd provides aggressive parallelization capabilities and dependency-based service control logic, allowing for services to start in parallel and leading to a quicker boot time. These two aspects were present in Upstart, but improved upon by systemd.

systemd not only manages system initialization, but also provides alternatives for other well known utilities, like cron and syslog. 


<h2>The Linux Boot Process and systemd</h2>

To better understand what is meant by an initialization system, this section provides a high-level overview of the Linux boot process.

Linux requires an initialization system during its boot and startup process. At the end of the boot process, the Linux kernel loads systemd and passes control over to it and the startup process begins. 

During this step, the kernel initializes the first user space process, the systemd init process with process ID 1, and then goes idle unless called again. systemd prepares the user space and brings the Linux host into an operational state by starting all other processes on the system.

Below is a simplified overview of the entire Linux boot and startup process:

<ol>
<li>The system powers up. The BIOS does minimal hardware initialization and hands over control to the boot loader.</li>
<li>The boot loader calls the kernel.</li>
<li>The kernel loads an initial RAM disk that loads the system drives and then looks for the root file system.</li>
<li>Once the kernel is set up, it begins the systemd initialization system.</li>
<li>systemd takes over and continues to mount the host’s file systems and start services.</li>
	
</ol>


<h2>Units</h2>

Systemd provides a system of dependencies between various entities called units. Units encapsulate different objects relevant to system startup and maintenance.

Most of these units are configured in their own configuration files. However, some are created automatically from another configuration, or dynamically responding to a system state, or programming it during the execution of another unit.

A drive configuration file encodes information about any of the various drives available. General syntax and options are in systemd.unit
Additional or specific options are indicated in the specific references of each unit. 

Units can acquire different states:
<ul>
<li><b>Active</b> Which can mean started, destined, or connected, depending on the type of unit</li>
<li><b>Inactive</b> which can mean stopped, no destination or disconnected, depending on the type of unit</li>
<li><b>Activating and deactivating</b>. A unit can acquire an intermediate state between two processes waiting to be activated or deactivated</li>
<li>A special state called <b>failed</b> is available similar to inactive and occurs when the service has failed in some way (the service sent an error code, crashed, or timed out)</li>

</ul>

There are twelve different types of units:

<ul>
<li><b>Service</b>: A unit .service Controls daemons and the processes related to them.</li>
<li><b>Socket</b>: Encodes information regarding an IPC network socket (inter-process communication socket), or a FIFO file system socket, controlled and monitored by systemd, for socket-based activation. Each .socket unit has its corresponding .service unit, and establishes a communication channel at the customer's request.
<li><b>Target</b>: The .target units encode information regarding the target units of the system, which are used to group units and achieve a good synchronization between them at startup, they serve exclusively to group units via dependencies, establish and synchronize names that allow them to be related between yes.</li>
<li><b>Device</b>: The .device units encode information regarding a device included in sysfs / udev.</li>
<li><b>Mount</b>: .mount units encode information regarding a mount point controlled and monitored by systemd. Allows you to mount or unmount a file system</li>
<li><b>Automount</b>: the .automount units encapsulate the automount functionalities of a file system. Each automount unit is contained in a .mount unit when an access request occurs this unit mounts the file system and gives access.</li>
<li><b>Snapshot</b>: The .Snapshot units refer to a dynamic snapshot of the systemd execution state. They are useful to roll back to a defined state after starting / temporarily stopping services or the like.</li>
<li><b>Timer</b>: .timer units encode information about a timer, controlled and monitored by systemd, for timer-based triggering.</li>
<li><b>Swap</b>: The .swap units encode the information about a mobile device or the memory paging file controlled and monitored by systemd.</li>
<li><b>Path</b>: .path units encode information about the path monitored by systemd, for path-based activation.</li>
<li><b>Slice</b>: The units, silica manage the processes (Scope and unit), which can be assigned to a specific sector. With the possibility of setting certain limits to the resources that are applied to all the processes of all the units that appear in that sector.</li>
<li><b>Scope</b>: The .scope units manage a set of system processes. Unlike service units, scope units manage externally created processes, and do not fork those processes.</li>
	
