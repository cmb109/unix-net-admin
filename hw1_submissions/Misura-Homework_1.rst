##############################
Unix/Linux Command Cheat Sheet
##############################

:Author: Doug Stanley <doug@douglasstanley.com>
:Last Modified: 1/19/2012
:Version: 0.1


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

ifconfig -a

    Show ALL interfaces known on the system.

ifup
    Brings a network interface up
	would use this command when statically configuring a route for a network in Linux.
	also when connecting multiple routes to one pc you can chose which ones to have up

ifdown
    Takes down a network interface
	use this one when you are going to configure the static routes first.
	

route
    Allows you to see and manipulate the IP routing table
	use this command to help trouble shoot a connection problem.
	after the command is entered you can pick an interface to reconfigure
	use to view what IP routes are on each interface
netstat
    Shows you the status of the network
	need to use this command to see which interfaces are up or down
	also shows which interfaces are named what 

iptables
    sets up, maintains, and inspects the tables of IPv4 packet filter rules in the Linux Kernel
	can set up rules to allow different connections in or out.
	can HTTP connections to be made so that you can get online






References

http://linux.die.net/man/8/iptables
http://www.computerhope.com/unix/unetstat.htm
http://linux.about.com/od/commands/l/blcmdl8_route.htm
http://www.computerhope.com/unix/ifup.htm