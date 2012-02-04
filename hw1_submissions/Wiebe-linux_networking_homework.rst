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
	
	 

ifup/ifdown

	This will bring an interface up with the ifup command or bring hte interface down with the ifdown command.
	You would use this command if you wanted to configure an interface for networking or if you wanted to take the
	interface down so that it isnt used for networking anymore. 
	
route

	it displays the current contents of the routing tables unless the add or del options are used in which case it 
	modifies the routing tables.

netstat

	netstat shows basic network statistics on the host that it is entered into. this can be used with many different
	arguments to figure out different things about the network such as showing the state of all sockets and routing 
	table entries. 
	

iptables

	used to look at the routing tables associated with ipv4 and to set up and maintain them. It is used to look at the 
	different packets that are sent over the network.  	

References
=======

http://linux.about.com/od/commands/l/blcmdl8_route.htm

http://www.computerhope.com/unix/unetstat.htm

http://linux.die.net/man/8/iptables

