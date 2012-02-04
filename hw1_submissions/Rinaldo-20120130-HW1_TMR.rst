##########
Homework 1
##########

:Author: Tom Rinaldo <tmr2@uakron.edu>
:Date: 1/30/2012

Introduction
============

Provided below is a summery of the following GNU commands for Linux


Definitions 
============

ifconfig
------------------
:Summery: The command *ifconfig* is used to configure, see the status of, and control the stat of a network interface device.
:Example #1: *ifconfig -a* -- prints a list of all the network devices on the machine.
:Example #2: *ifconfig eth0 10.0.0.3 netmask 255.255.255.0 up* -- sets the ip for the network device /dev/eth0 to 10.0.0.3 with the subnet mask of 255.255.255.0, and it brings the device up (if it wasn't already)

ip
------------------
:Summery: The *ip* command is a 'meta' command that controls many network functions on a Linux system.
:Example #1: *ip route list* -- prints the route, the devices accociated, the ip address of the gateway, and the IP address assigned to that network device.
:Example #2: *ip route add 10.0.0.0/24 dev eth1* -- Send all packets that belong on the local *10.0.0.x* network to the */dev/eth1* network device.

route
------------------
:Summery: The *route* command controls the network routing tables on a Linux. 
:Example #1: *route add default gw 10.0.0.1 eth0* -- Adds the default gateway to be 10.0.0.1 on /dev/eth0.
:Example #2: *route* -- prints out the routing table for the system

netstat
------------------
:Summery: The command *netstat* shows information from the variable network tables in Linux. It's usually used to print routing table information, and open sockets on the machine.
:Example #1: *netstat -r* -- like *route* prints out the routing table for the system, but with *MSS* *Window* and *irtt* given instead of *Metric*, *Ref*, and *Use*.
:Example #2: *netstat -n* -- prints the open sockets on the machine, while only printing out numeric IP addresses instead of resolving the machine's hostname.

iptables
------------------
:Summery: *iptables* is the command that control the firewall/packet filter in the Linux Kernel.
:Example #1: *iptables -L* -- Lists all the fireall rules currently set on the system.
:Example #2: *iptables -F* -- Deletes all rules in the firewall tables.

    
References
===========
- man ifconfig
- man route
- man netstat
- man iptables
- man ip
- http://www.cyberciti.biz/faq/howto-linux-configuring-default-route-with-ipcommand/