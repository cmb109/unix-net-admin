Linux Homework 1
Dan Revesz




I.	[Ifconfig]
	Is used to configure network interfaces. The command is really only used when setting up everything at the begining. After that its rarely used but when it is it would be used for system 		tuning or debugging.
	The common flags for this command are:
	[Interface]-The name of the interface being created or addressed. Such as eth0.
	[Address]-this flag allows you to create a IP address for the interface that your creating.


II.	[IP]
	This command allows you to configure network interfaces.It is a TCP/IP type utility.
	The common flags for this command are:
	

III.	[Route]
	Used primarily to configure static route to certain hosts or networks. This is done after the ifconfig command has been used.
	The common flags for this command are:
	[Add]-which is used to add a new static route.
	[Del]-which is used to delete an existing static route. 

IV.	[Netstat]
	This command is used with multiple arguments that allow you to veiw or print information about the linux networking configurations on your system.
	The common flags for this command are:
	[-r]-this argument shows the kernels routing tables
	[-i]-this command can be used to view all network interfaces currently in use or can be used in combination with a interface name for a specific interface you want to print.

V.	[Iptables]
	This command can be used to modify, create and veiw the tables of the IP packet filter rules. The packet filter is veiw with targets and chains.
	










			References
I.	http://linux.about.com/od/commands/l/blcmdl8_ifconfi.htm
II.	http://linux.about.com/od/commands/l/blcmdl8_route.htm
III.	http://linux.about.com/od/commands/l/blcmdl8_netstat.htm

