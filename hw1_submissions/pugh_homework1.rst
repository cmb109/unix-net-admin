==========
Homework 1
==========

:Author: Kacy Pugh <ktp4@zips.uakron.edu>
:Date: 1/25/12
:Due Date: 

Assignment Requirements
=======================
Documentation of the networking commands ifconfig, iproute, route, netstat, and iptables.

ifconfig
--------
Displays the status of the currently active interface. Used at boot time to setup interfaces as necessary. After that, usually only needed for troubleshooting. 

**Common Flags**:

- *-a*
  Displays all available interfaces, even if down.
  
  Used this in class to see if particular interfaces were recognized.

- *-s*
  Displays a short list.
  
  Could be used if details are not needed.

- *interface*
  This is the name of the interface, such as eth0.
 
  Used if details of only a spefic interface need to be shown.

- *up*
  Activates the interface.

  Used when an interface is disabled.

- *down*
  Causes the driver for the interface to be shut down.

- *address*
  The IP address to be assigned to this interface.

  Used when an ip address needs to be set manually.

**Resources**:

- man ifconfig
- `TechRepulic <http://www.techrepublic.com/article/linux-101-use-ifconfig-in-linux-to-configure-your-network/6040932>`_.

ip
---
Similar to ifconfig, but much more powerful. Used to show and/or manipulate routing, devices, policy routing and tunnels.

**Common Flags**:

- *link*
  lists network devices and it's corresponding commands display and change the state of devices.

  One might use this to change the state of the device to up or down.

- *address*
  Displays the ip address on a device.

  One might use this to setup synergy on their machines.

- *route*
  Shows the routing table entry.

  One might use this to help troubleshoot conection issues.

**Resources**

- man ip

route
-----
Shows and/or manipulates the routing table. It's primary use is to set up static routes to specific hosts or networks via an interface after it has been conifigured with the ifconfig command.

**Common Flags**

- del
  Deletes a route.

- add
  adds a new route

  One may use this if dhcp was not in use and a default gateway was needed to be manually setup.

- -v
  select verbose operation

  One would use this flag to make it a little more understandable.

- -n 
  shows numerical addresses instead of trying to determine host names.

  One could use this option if the hostname is unknown.

**Resources**

- man route
- `Lainoox.com <http://www.lainoox.com/linux-route-commands/>`_

netstat
-------
Prints information about the Linux networking subsystem such as: network connections, routing tables, interface statistics, masquerade connections, and multicast memberships

One would use this command if he or she wanted to see what ports were currrently in use on machine. You could also use this to see the routing table without superuser credentials.

**Common Flags**

- -r
  Displays the kernel routing table similar to route

- -n
  Prints addresses as dotted quad IP numbers rather than hostnames.

  Useful in situations where one wants to avoid address lookups, such as DNS.

- i
  Displays statistics for the currently connected network interfaces.

- -ta
  Displays a list of currently running servers.

**Resources**

- `tldp.org <http://tldp.org/LDP/nag2/x-087-2-iface.netstat.html>`_
- man netstat

iptables
--------
Administration tool for IPv4 packet filtering and NAT. Used to set up, and inspect tables of IPv4 packet filter rules in the Linux kernel. Several tables may be defined. Each table contains a number of built-in chains and may also contain user-defined chains.

Each chain is a set of rules which can match a set of packets. Each rule specifies what to do with a packet that matches. This is called a "target", which may be a jump to a user-defined chain in the same table.

**Common Flags**

- -F
  This cleans-up all the existing rules

  One would use this before adding any new rules to ensure all are set to defaults.

- -A INPUT -s "$BLOCK_THIS_IP" -j DROP
   Blocks the specified ip.

  One would use this if they wanted to block an ip that is generating random activity, or an ip you want to stop yourself from visiting.

- -t
  Specifies which talbe the command should operate on.

- -A
  Append oen or more rules to the end of the selected chain.

- -L
  List all rules in the chain

- -R
  Replace a rule in the chain

- -D
  Delete one or more rows in the selected chain

**Resources**

- `The Geek Stuff <http://www.thegeekstuff.com/2011/06/iptables-rules-examples/>`_
- man iptables




