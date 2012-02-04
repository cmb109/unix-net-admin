##########
Homework 1
##########

Chris Bittner
=============

Command Summary
---------------

	Command
		ifconfig
	Summary
		Short for interface configureation. Used to configure kernel-resident network interfaces. Used at boot time to set up interfaces. Often used to display and analyze network inteface parameters.
	Common Uses
		*ifconfig
			-to display the current status of active interfaces.
		*ifconfig -a
			-displays the status of all interfaces.
			
	Command
		ip
	Summary
		Manipulate and display routing information, devices, policy routing and tunnels.
	Common Uses
		*ip -s link
			-displays information about a link.
		*ip -V
			-prints the version of the ip utility
		*ip neighbour
			-ARP or NDISC cache entry
	
	Command
		route
	Summary
		Used to manipulate the TCP/IP routing table. Allows configuration of static routes.
	Common Uses
		*route del -net 192.168.1.2 netmask 255.255.255.0 dev eth0
			-deletes ip information for device eth0
		*route add default mango
			-adds a default route in the routing table called mango which will have to be set up before hand.
	
	Command
		netstat
	Summary
		Displays routing tables, network interface statistics, and network connections. Useful for finding problems in the network and looking at the amount of traffic for performance purposes.
	Common Uses
		*netstat -sp tcp
			-display statistics for TCP routing
		*netstat -aop | grep "pid"
			-display's all ports open by a process with id *pid*
	
	Command
		iptables
	Summary
		For the set up of IPv4 packets, it is used to maintain and inspect the tables for these packets as well as set them up. The user can define several different tables.
	Common Uses
		*iptables -t *table* -A *chain rule-specification*
			-adds a chain rule to the table specified
		*iptables -t *table* -N *chain*
			-creates a new chain in the table specified with the specified name.
	
Referances
**********

	*en.wikipedia.org/wiki/Ifconfig

	*linux.die.net/man/8/ifconfig

	*linux-ip.net/gl/ip-cref/node3.html

	*linux.die.net/man/8/ip

	*en.wikipedia.org/wiki/Route_(command)

	*linux.die.net/man/8/route

	*en.wikipedia.org/wiki/Netstat

	*linux.die.net/man/8/netstat

	*linux.die.net/man/8/iptables
	
	*en.wikipedia.org/wiki/Iptables