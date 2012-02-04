##############################
Unix/Linux Command Cheat Sheet
##############################

:Author:  Curtis Ellis

Introduction
============
Homework 1



Networking
==========
------------------------------------------
ifconfig
	lists interfaces and interface status of the interfaces that are currently up
ifconfig -a
	list all the interfaces and their status up or down.

http://linuxmanpages.com/man8/ifconfig.8.php
-------------------------------------------
ip address add 192.168.1.1/24 broadcast dev eth0
	sets the ip address and subnet on a particular interface.

ip -6 address
	sets an ipv6 address

page 302
-------------------------------------------
route add -net default via gw 192.168.1.1 dev eth 0
	adds a default route

route add -host 192.168.1.1 netmask 255.255.255.255 dev ppp0
	adds a static route

page 310
-------------------------------------------
netstat
	Displays network connections to the host

netstat -r 
	shows the routing table

page 312
-------------------------------------------

iptables -h
	shows configuration options
iptables -t table -A chain rule-spec [options]
	Appends a rule-spec to chain
	
page 333
-------------------------------------------