###########################################
Homework 1 - Unix/Linux Command Cheat Sheet
###########################################


:Author: Kaedra Herink
:Date: 1/25/2012



ifconfig
========

The ifconfig command is used to configure parameters of an interface.  If simply "ifconfig" is typed in, it will display the current status of interfaces that are active.

	ifconfig -a
		
		Displays information for all active and inactive interfaces.


	ifconfig *interface*

		Displays information for the interface specified.

			Ex: ifconfig *eth1*

	ifconfig arp
		
		Turns on ARP (Address Resolution Protocol), which maps network addresses with link-level addresses.

	ifconfig -arp

		Disables ARP.

	ifconfig description *value*

		Allows you to enter a description for an interface.

			Ex: ifconfig description *Backup interface*

	ifconfig *interface* broadcast *broadcast-address*

		Used to change the broadcast address.

			Ex: ifconfig *eth0* broadcast *192.168.3.255*
	





ip
========

The ip command will display, and allow a user to change things relating to routing, network devices, and tunnels.  

	ip route show

		Displays the routing table.

	ip addr show

		Lists IP addresses for interfaces.

	ip link show

		Lists network interfaces.

	ip link set dev *interface-name* name *new-interface-name*

		Renames an interface.

			Ex: ip link set dev *eth2* name *wan1*

	ip link set dev *interface* up
		
		Brings the specified interface up.

			Ex: ip link set dev *eth0* up




route
=====

The route command allows a user to view the routing table, as well as manipulate and maintain it.  This includes, but is not limited to, adding routes, deleting routes, changing routes,

	route -n

		With the -n option, this command shows the routing table for all IP addresses that are bound to the server.

	route add *ip-address* netmask *subnet-address* dev *interface*

		This command shows the basic syntax of adding a route to the routing table.
		Included are the destination IP, subnet address, and the interface to get to the address.
		If "dev" is the last option used on this command, then "dev" can be omitted, and the 
		interface can simply follow the netmask numerical entry.

			Ex: route add *192.168.50.111* netmask *255.255.255.0* dev *eth1*

	route del *ip-address* netmask *subnet-address*

		Deletes the specified route.
                    
                        Ex: route del *192.168.50.111* netmask *255.255.255.0*





netstat
=======

Netstat is a command that allows a user to see information about the network, 
the routing table, and host you are connected to.

	netstat -a

		Netstat with the -a option will display information about all connections and all routing table entries.

	
	netstat -i

		Displays information about the state (up/down) of interfaces.
		
	netstat -i *interface*

		Displays more detailed information about a specified interface.

			Ex: netstat -i *lo0*

	netstat -tup

		Lists all active connections going to and from the system.

	netstat -at

		Lists all TCP ports.

	netstat -ut

		Lists all UDP ports.

	netstat -ap | grep *program/process*

		Used to find out which port a program is using.

			Ex: netstat -ap | grep *ssh*



iptables
========

The iptables command allows a user to view and change attributes dealing with packet filtering and NAT (Network Address Translation).  Packet filtering deals with rules applied to incoming and outgoing IPv4 packets.  "Chains" are used to define these rules and manipulate the routing of packets.  The iptables command aids in viewing, maintaining, and altering chains.

	iptables -F

		This command deletes all of the existing and default rules.  
		You might want to use this before starting to create a new set of rules.


	iptables -N *name-of-chain*

		This command creates a new chain.

			Ex: iptables -N *newchain1*

	iptables -A 

		The -A in this command is used to *append* information to a chain.

			Ex: iptables -A INPUT -i eth0 -s "$BLOCK_THIS_IP" -j DROP

	

	

			





###########
References
###########

+ http://linux.die.net/man/8/ifconfig

+ http://www.openbsd.org/cgi-bin/man.cgi?query=ifconfig

+ http://linux.die.net/man/8/ip

+ http://linux.about.com/od/commands/l/blcmdl8_iptable.htm

+ http://www.thegeekstuff.com/2011/06/iptables-rules-examples/

+ http://www.computerhope.com/unix/unetstat.htm

+ http://www.computerhope.com/unix/route.htm

+ http://www.thegeekstuff.com/2010/03/netstat-command-examples/

+ http://www.thegeekstuff.com/2011/06/iptables-rules-examples/

+ http://www.pixelbeat.org/cmdline.html

+ http://www.thegeekstuff.com/2009/03/ifconfig-7-examples-to-configure-network-interface/

+ http://www.thegeekstuff.com/2010/03/netstat-command-examples/#more-3596




