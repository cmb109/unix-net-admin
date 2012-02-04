##########
Homework 1
##########

:Sandor Gyarmati
:1/31/2012

Linux / Unix Command: ifconfig
==============================

*Description:* It is used to configure the kernel-resident network interfaces. It is used at boot time to set up interfaces as necessary. After that, it is usually only needed when debugging or when system tuning is needed

*Examples:* 
    ifconfig [interface] up - This flag causes the interface to be activated. It is implicitly specified if an address is assigned to the interface
    ifconfig [interface] down - This flag causes the driver for this interface to be shut down

Linux / Unix Command: ip
========================

*Description:* This utility allows you to configure your network interfaces in various ways.

*Examples:*
    ip link show [ DEVICE ] 
    ip addrlabel { list | flush } 

Linux / Unix Command: route
===========================

*Description:*  It manipulates the kernel's IP routing tables. Its primary use is to set up static routes to specific hosts or networks via an interface after it has been configured with the ifconfig.

*Examples:*
    route del - delete a route
    route add - add a route

Linux / Unix Command: netstat
=============================

*Description:* It prints information about the Linux networking subsystem. The type of information printed is controlled by the first argument.

*Examples:*
    natstat route - Display the kernel routing tables
    natstat groups - Display multicast group membership information for IPv4 and IPv6

Linux / Unix Command: iptables
==============================

*Description:* It is used to set up, maintain, and inspect the tables of IP packet filter rules in the Linux kernel. Several different tables may be defined. Each table contains a number of built-in chains and may also contain user-defined chains.

*Examples:*
    iptables [-t table] -[ADC] chain rule-specification [options]
    iptables [-t table] -I chain [rulenum] rule-specification [options]