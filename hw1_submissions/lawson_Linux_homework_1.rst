################################
Unix/Linux Homework Assignment 1
################################

Mark Lawson
01/31/2012


ifconfig
==========

The command ifconfig in Linux is used to view the network interfaces on the machine. It can display only active interfaces, or all available 
interfaces on the systems regardless of status dependent upon the command entered.

ifconfig
-----------

* Displays all active (up interfaces) on the system.

  - sudo ifconfig eth0 192.168.13.8 netmask 255.255.255.192 up

    + Changes the ip address to 192.168.13.8 with a mask of 255.255.255.192, placing the interface in an active state.

    + Can be used to quickly set the interface address the the Admins choice.

  - sudo ifconfig eth0 mtu 1600

    + Changes the mtu size on eth0 from the default of 1500 to 1600.

    + Can be used to allow for large transmission sizes, such as jumbo frames.

ifconfig -a
-------------

* Displays all network interfaces available on the system regardless of state (up or down).

  - ifconfig -a lo

    + Displays all loopback interfaces available on the system.

    + Can be used to quickly see what logical interfaces are available. If peforming a standard ping to 127.0.0.1 and a timeout occurs, the lo interface would want to be checked to ensure the address had not been changed.
 
  - ifconfig -a eth

    + Displays all the ethernet interfaces available on the system.

    + Can be used to see what Ethernet interfaces are available, and also their state. This would be helpful in checking the status of the Ethernet interfaces, as well as their network information, mtu size, etc in the event that communication was not correctly working/taking place.

ifup/ifdown
=============

* Essentially the same program called by different names. Ifup brings an interface to an active state (up), ifdown places the interface in an inactive state (down).

  - ifup -a

    + Brings all the interfaces up at once

    + Can be used if the Admin wishes to activate all interfaces at the same time, for instance if there were three Ethernet interfaces, and all were connected to swich ports.

  - ifdown -a

    + Brings all the interfaces down at once. 
 
    + Can be used if the Admin wished to de-activate all interfaces at the same time. 

route
=======

* Displays the current routing table on the system.

  - sudo route add default gw 192.168.13.1 eth0

    + Sets the default gateway for Ethernet 0 to 192.168.13.1

    + Can be used to set the interfaces gateway to the interface of the router to which it is attaches in order to gain access outside of the LAN.

  - sudo ip route add 192.168.1.2/24 dev eth0

    + Adds an entry in the routing table for eth0. 

    + Can be used to configure a route for the interface to send IP traffic through to communicate with other devices on the network.

netstat
=========

* Netstat shows the status of the network.

  - netstat -s

    + This command will show statistics for all ports. 

    + Can be used if there is a break in communication, will display if packets are being sent as well as received, and which protocol (UDP, TCP, etc) is being used.

  - netstat -c

    + Displays active Internet connections.
    
    + Can be used to see which computers are currently accessing the Internet, and also which sockets are open.

iptables
============

* iptables shows the status of the ip tables and rules for access in place.

  - iptables --list

    + Shows what rulesets are currently in place. 

    + Can be used to view what rulesets are established for a specific IP address. 

    + The Admin can check this if there is an issue with a specific device establishing communication with your machine.

  - sudo iptables -F

    + Clears the current iptables. 
 
    + Can be used when the Admin wants to create new rules, and wants to delete all existing rules.



References
===============

* http://manpages.ubuntu.com/manpages/hardy/man8/ifup.8.html

* http://www.cyberciti.biz/faq/linux-change-ip-address/

* http://linux.about.com/od/commands/l/blcmdl8_ifconfi.htm

* http://www.cyberciti.biz/faq/linux-setup-default-gateway-with-route-command/

* http://www.cyberciti.biz/faq/linux-route-add/

* http://www.computerhope.com/unix/unetstat.htm

* http://www.thegeekstuff.com/2010/03/netstat-command-examples/

* http://www.howtoforge.com/linux_iptables_sarge

* http://www.thegeekstuff.com/2011/06/iptables-rules-examples/

* http://linux.about.com/od/commands/l/blcmdl8_iptable.htm

