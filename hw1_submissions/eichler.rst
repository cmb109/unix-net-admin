##############################
Unix/Linux Command Cheat Sheet
##############################

:Author: David Eichler



Introduction
============

This is basically a quick reference guide for the various commands and 
topics covered in the class.


Networking
==========


Network Interfaces
------------------

ifconfig

	With no args, shows a list of all interfaces that are "up".
	command example: ifconfig
	This is used to see what interfaces are up and there ip addresses

ifconfig -a

	Show ALL interfaces known on the system.
	command example: if config -a
	This is used to see all available interfaces. You can check to see which ones are up and which
	ones can be configured

ifup/ifdown

	brings an interface up or shuts it down
	Using the interface after the command only applies it to that interface
	-a
	bring all interface marked auto up or shutdown all interface that are currently up
	This is used to change the state of an interface which is what we have to do with our Fedora 
	virtual machines
	command example: ifup eth01

route

	add or delete static or default route to the routing table using the arguments of add or delete
 	followed by the [ip address] -netmask [netmask] 
	-gw
	This can be used to add the default gateway to the routing table by using the gw argument
	This can also be used for routing to your known networks
	command example: route add 192.168.1.0 -netmask 255.255.255.0
	

netstat

	shows network status
	-i
	shows the state of the interface
	-r
	show routing tables
	This is used to check interface status and routing tables
	command example: netstat -r -i
	
iptables

	administration tool for IPv4 packet filtering and NAT by tables and rules
	-L list rules
	-A appends a rule
	-D delete a rule
	-p protocol to check
	-s source ip address/netmask
	-d destination ip address/netmask
	This is used to filter addresses or work as a firewall and works similar to Cisco routers ACL's
	command example: iptables -A INPUT -p tcp --dport 80 -j ACCEPT
	this example allows incoming web traffic
	This can also be used to block ip addresses and to shut down ports for example ftp


References

	*http://manpages.ubuntu.com
	*http://linux.die.net
	*http://www.softpanorama.org/
	*http://www.computerhope.com/unix
	*Linux Admininstration: A Beginner's Guide

	