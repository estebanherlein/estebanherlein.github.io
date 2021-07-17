---
title: "Linux network configuration"
categories:
  - Blog
tags:
  - Linux
  - Shell Essentials
  - Dev-ops
  - Networking Theory
---
 
Having access to the network is a key feature of most Linux systems. Users want to surf the net, send and receive email and transfer files with other users.

Typically the programs that perform these functions, such as web browsers and email clients, are reasonably easy to use. However, they all rely on an important feature: the ability of your computer to communicate with another computer.

Linux provides you with several tools to both configure your network as well as monitor how it is performing.‌⁠​​⁠​ 


<h2>ifconfig command</h2>

The ifconfig command stands for interface configuration and is used to display network configuration information. 

It is important to note from the output below that the IP address of the primary network device eth0 is 192.168.1.2 and that the device is currently active UP:

<pre>
<code>
root@localhost:~# ifconfig                                     
<b>eth0</b>      Link encap:Ethernet  HWaddr b6:84:ab:e9:8f:0a
          inet addr: <b>192.168.1.2</b>  Bcast:0.0.0.0  Mask:255.255.255.0
          inet6 addr: fe80::b484:abff:fee9:8f0a/64 Scope:Link
          <b>UP</b> BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:95 errors:0 dropped:4 overruns:0 frame:0
          TX packets:9 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:25306 (25.3 KB)  TX bytes:690 (690.0 B)
lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1 
          RX packets:6 errors:0 dropped:0 overruns:0 frame:0  
          TX packets:6 errors:0 dropped:0 overruns:0 carrier:0 
          collisions:0 txqueuelen:0 
          RX bytes:460 (460.0 B)  TX bytes:460 (460.0 B)
</code>
</pre>

The lo device is referred to as the loopback device. It is a special network device used by the system when sending network-based data to itself.

The ifconfig command can also be used to modify network settings temporarily. Typically these changes should be permanent, so using the ifconfig command to make such changes is relatively rare.

<h2>route command</h2>

A router (or gateway) is a machine that allows hosts from one network to communicate with another network. To view a table that describes where network packages are sent, use the route command:

<pre>
<code>
root@localhost:~# route    
Kernel IP routing table 
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface 
<b>192.168.1.0     * </b>              255.255.255.0   U     0      0        0 eth0  
<b>default         192.168.1.1</b>     0.0.0.0        UG     0      0        0 eth0
</code>
</pre>


The first highlighted line in the preceding example indicates that any network package sent to a machine in the 192.168.1 network is not sent to a gateway machine (the * indicates no gateway). 


The second highlighted line indicates that all other network packets are sent to the host with the IP address of 192.168.1.1 (the router).

Some users prefer to display this information with numeric data only, by using the -n option to the route command. For example, look at the following and focus on where the output used to display default:

<pre>
<code>
root@localhost:~# route -n    
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface 
192.168.1.0     0.0.0.0         255.255.255.0   U     0      0        0 eth0
<b>0.0.0.0</b>        192.168.1.1     0.0.0.0         UG    0      0        0 eth0
</code>
</pre>

The 0.0.0.0 refers to all other machines, and is the same as default.

<h2>ping command</h2>

The ping command can be used to determine if another machine is reachable. 

If the ping command can send a network package to another machine and receive a response, then you should be able to connect to that machine.

By default, the ping command continues sending packages endlessly. To limit how many pings to send, use the -c option followed by a number indicating how many iterations you desire. 

If the ping command is successful, it looks like the following example:
<pre>
<code>
root@localhost:~# ping -c 4 192.168.1.2 
PING 192.168.1.2 (192.168.1.2) 56(84) bytes of data.
64 bytes from 192.168.1.2: icmp_req=1 ttl=64 time=0.051 ms
64 bytes from 192.168.1.2: icmp_req=2 ttl=64 time=0.064 ms 
64 bytes from 192.168.1.2: icmp_req=3 ttl=64 time=0.050 ms 
64 bytes from 192.168.1.2: icmp_req=4 ttl=64 time=0.043 ms
   
--- 192.168.1.2 ping statistics ---   
4 packets transmitted, 4 received, 0% packet loss, time 2999ms 
rtt min/avg/max/mdev = 0.043/0.052/0.064/0.007 ms
</code>
</pre>

If the ping command fails, a message stating, Destination Host Unreachable displays:
<pre>
<code>
root@localhost:~# ping -c 4 192.168.1.1 
PING 192.168.1.1 (192.168.1.1) 56(84) bytes of data.
From 192.168.1.2 icmp_seq=1 Destination Host Unreachable
From 192.168.1.2 icmp_seq=2 Destination Host Unreachable
From 192.168.1.2 icmp_seq=3 Destination Host Unreachable
From 192.168.1.2 icmp_seq=4 Destination Host Unreachable
 
--- 192.168.1.1 ping statistics --- 
4 packets transmitted, 0 received, +4 errors, 100% packet loss, time 2999ms
pipe 4
</code>
</pre>

It is important to note that just because the ping command fails does not mean that the remote system is unreachable. 

Some administrators configure their machines (and even entire networks!) to not respond to ping requests because a server can be attacked by something called a denial of service attack. 

In this sort of attack, a server is overwhelmed by a massive number of network packets. By ignoring ping requests, the server is less vulnerable.

As a result, the ping command may be useful for checking the availability of local machines, but not always for machines outside of your own network.

<h2>netstat command</h2>

The netstat command is a powerful tool that provides a large amount of network information. It can be used to display information about network connections as well as display the routing table similar to the route command.

For example, to display statistics regarding network traffic, use the -i option to the netstat command:

<pre>
<code>
root@localhost:~# netstat -i 
Kernel Interface table 
Iface   MTU Met   RX-OK RX-ERR RX-DRP RX-OVR    TX-OK TX-ERR TX-DRP TX-OVR Flg
eth0       1500 0       137      0      4 0        12      0      0      0 BMRU
lo        65536 0        18      0      0 0        18      0      0      0 LRU
</code>
</pre>

The most important statistics from the output above are the TX-OK and TX-ERR. A high percentage of TX-ERR may indicate a problem on the network, such as too much network traffic.

To use the netstat command to display routing information, use the -r option:
<pre>
<code>
root@localhost:~# netstat -r
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
192.168.1.0     *               255.255.255.0   U         0 0          0 eth0 
default         192.168.1.1     0.0.0.0        UG         0 0          0 eth0 
</code>
</pre>

The netstat command is also commonly used to display open ports. 

A port is a unique number that is associated with a service provided by a host. If the port is open, then the service is available for other hosts.

The SSH service is assigned port #22. So, if port #22 is open, then the service is available to other hosts.

It is important to note that the host also needs to have the services running itself; this means that the service (in this case the ssh daemon) that allows remote users to log in needs to be started .

To see a list of all currently open ports, use the following command:
<pre>
<code>
root@localhost:~# netstat -tln 
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State 
tcp        0      0 192.168.1.2:53          0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN 
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN 
tcp        0      0 127.0.0.1:953           0.0.0.0:*               LISTEN 
tcp6       0      0 :::53                   :::*                    LISTEN
tcp6       0      0 :::22                  :::*                    LISTEN 
tcp6       0      0 ::1:953                 :::*                    LISTEN 
</code>
</pre>

As you can see from the output above, port #22 is listening, which means it is open.

In the previous example, -t stands for TCP , -l stands for listening (which ports are listening) and -n stands for show numbers, not names.

<h2>host command</h2>

In its simplest form, the host command works with DNS to associate a hostname with an IP address. As used in a previous example, example.com is associated with the IP address of 192.168.1.2:

<pre>
<code>
root@localhost:~# host example.com
example.com has address 192.168.1.2
</code>
</pre>

The host command can also be used in reverse if an IP address is known, but the domain name is not.

<pre>
<code>
root@localhost:~# host 192.168.1.2
2.1.168.192.in-addr.arpa domain name pointer example.com.
2.1.168.192.in-addr.arpa domain name pointer cserver.example.com.
</code>
</pre>

Other options exist to query the various aspects of a DNS such as a CNAME canonical name -alias:

<pre>
<code>
root@localhost:~# host -t CNAME example.com
example.com has no CNAME record
</code>
</pre>

Since many DNS servers store a copy of example.com, SOA Start of Authority records indicate the primary server for the domain:

<pre>
<code>
root@localhost:~# host -t SOA example.com
example.com has SOA record example.com. cserver.example.com. 2 604800 86400 2419200 604800
</code>
</pre>