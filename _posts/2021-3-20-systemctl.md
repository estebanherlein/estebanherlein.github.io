---
title: "Systemctl"
categories:
  - Blog
tags:
  - Linux
---
The systemctl command is a utility which is responsible for examining and controlling the systemd system and service manager. 

It is a collection of system management libraries, utilities and daemons which function as a successor to the System V init daemon. 

The new systemctl commands have proven quite useful in managing a servers services. It provides detailed information about specific systemd services, and others that have server-wide utilization.

Keep in mind that most of the systemctl commands will not provide any output if they have been successful. 

However, if the systemctl command has failed to complete the task, you will get an error message stating that it failed.

<h2>Managing Services</h2>
<h3>What is a Service? </h3>

In the systemd utility, a service is referred to as a unit.

<b>A unit is any resource that the system knows how to act on and administrate. </b>

A unit is the principal object that the systemd tools know how to address. These assets are defined in a configuration file called a unit file.

<h2>Check Service Status</h2>

Using systemctl, we can check the status of any systemd service on the managed dedicated server. The status command provides information about a service. It also lists the running state, or detail on why it is not running, or if a service has been stopped unintentionally. If we are connected to the server as a non-root user, we will have to run the systemctl commands using.

<pre><code>systemctl status servicename.service</code></pre>

This unit can be called without the .service extension. Since systemctl will look for those files with .service suffix, the command can also be used like this.


<pre><code>systemctl start servicename</code></pre>

<h2>Starting or Stopping a Service</h2>

The systemctl utility can also be used to start or stop systemd services using a service unit file, with or without that .service suffix.


<pre><code>systemctl start servicename.service</code></pre>

The same rules apply when we want to stop a specific service.

<pre><code>systemctl stop servicename.service</code></pre>

Keep in mind that the start order can only be used on systemd services that are not currently running, and the stop command used only with running services.

<h2>Restarting or Reloading a Service</h2>

A running service can be restarted using the restart command to avoid stopping and starting it manually using the following command.

<pre><code>systemctl restart servicename.service</code></pre>

Occasionally, we do not need to restart a service to apply configuration changes, if any were you made. Instead, we can use the reload command to restart the service which implements any changes to the running service.

<pre><code>systemctl reload servicename.serivce</code></pre>

If we are not sure about which of the two commands we should use, there is an additional option using the reload-or-restart command which will automatically determine it for us.

<pre><code>systemctl reload-or-restart servicename.service</code></pre>

<h2>Enable or Disable a Service</h2>

When it comes to cloud server services, we require most of them to be online and active all the time. 

Starting them manually is not a convenient method to employ, due to the number of services required to run on a server. 

This is where the enable and disable commands come into play. Using the enable command, we can modify how the systemd service responds once the server has been started or rebooted. 

It will update the service settings, which then tells systemd that the specific service needs to start up automatically, once the server is up. The command to accomplish this is as follows.

<pre><code>systemctl enable servicename.service</code></pre>

While most of the services like HTTPD, MySQL, MariaDB, etc. will have already automatically started, we may need to enable the automatic startup for some of them manually.

Similar to how we can set a service to automatically start when the server boots up, we can also disable a service using the following command.

<pre><code>systemctl reload-or-restart servicename.service</code></pre>
