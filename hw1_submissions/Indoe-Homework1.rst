##########
Homework 1
##########

:Author: Tyler Indoe <twi1@zips.uakron.edu>
:Date: 1/25/2012
:Due Date: **1/31/2012**


Terms
=====



ifconfig
--------


ifconfig 
	configure network interface paramenters

ifconfig -a
	instructs ifconfig to display information about all interfaces in the system

ifconfig -d
	displays interfaces that are down, can only use flag of -a or -l

ifconfig -l
	used to list all of the available interfaces on the system

ifconfig -u
	displays interfaces that are up



ip
--

ip
	show / manipulate routing, devices, policy routing and tunnels

ip -v
	prints the version of the "ip" utility

ip -s, -stats, -statistics

	outputs more information. As a rule, the information is statistics and some time values.

ip -f, -family
	followed by protocol family identifier: inet, inet6 or link ,enforce the protocol family to use. If the option 	is not present, the protocol 	family is guessed from other arguments. If the rest of the command line does not 	give enough information to guess the family, ip falls 	back to the default one, usually inet or any. link is 	a special family identifier meaning that no networking protocol is involved.

ip -4
	shortcut for -family inet

ip -6
	shortcut for -family inet6

ip -0
	shortcut for -family link

ip -o, -oneline
	output each record on a single line, replacing line feeds with the '\' character. This is convenient when you 	want to count records with wc or to grep the output

ip -r, -resolve
	use the system's name resolver to print DNS names instead of host addresses




route
-----

route
	manipulates the kernel's IP routing tables. Its primary use is to set up static routes to specific hosts or 	networks via an interface after it has been configured with

route -a family

	use the specified address family

route -F 

	operate on the kernels FIB routing table

route -C 
	operate on the kernels routing cache

route -n
	show numerical addresses instead of trying to determine symbolic host names. This is useful if you are trying 	to determine why the route to your nameserver has vanished

route -e
	use netstat(8) format for displaying the routing table. -ee will generate a very long line with all parameters 	from the routing table

route del
	Delete a route

route add
	add a new route

route target
	the destination network or host

route -net
	the target is a network

route -host
	the target is a host

route netmask NM
	when adding a network route, the net mask is to be used





netstat
-------

netstat
	prints information about the Linux networking subsystem. The type of information printed is controlled by the first argument

netstat -r
	display the kernel routing tables

netstat -g
	displays multicast group membership

netstat -i
	displays a table of all network interfaces

netstat -m
	displays a list of masqueraded connections

netstat -s
	display summery statistics


iptables
--------

iptables 
	administration tool for IPv4 packet filtering and NAT

iptables -t, --table table
	This option specifies the packet matching table which the command should operate on.
 
iptables filter
	This is the default table (if no -t option is passed)
 
iptables nat
	This table is consulted when a packet that creates a new connection is encountered.

iptables mangle
	This table is used for specialized packet alteration.

iptables -A
	Append one or more rules to the end of the selected chain.

iptables -D
	Delete one or more rules from the selected chain


iptables -I
	Insert one or more rules in the selected chain as the given rule number.

iptables -R
	Replace a rule in the selected chain

iptables -L
	List all rules in the selected chain.

iptables -F
	Flush the selected chain

iptables -Z
	Zero the packet and byte counters in all chains.

iptables -N
	Create a new user-defined chain by the given name.

iptables -X
	Delete the optional user-defined chain specified. 

iptables -p
	Set the policy for the chain to the given target

iptables -E
	Rename the user specified chain to the user supplied name


	








Sources
=======



ifconfig
--------

man ifconfig

http://publib.boulder.ibm.com/infocenter/pseries/v5r3/index.jsp?topic=/com.ibm.aix.cmds/doc/aixcmds3/ifconfig.htm


ip
--

man ip

http://linux.die.net/man/8/ip


route
-----

http://linux.about.com/od/commands/l/blcmdl8_route.htm


netstat
-------

http://linux.about.com/od/commands/l/blcmdl8_netstat.htm


iptables
--------

http://linux.about.com/od/commands/l/blcmdl8_iptable.htm



