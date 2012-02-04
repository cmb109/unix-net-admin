
##############
**Homework 1**
##############


:Author: Tim Foster trf12@zips.uakron.edu
:Date Due: 1/21/2012


Definitions:
==============

++++++++++
*ifconfig*
++++++++++

The basic use of ifconfig is to display the status of the network interface configurations.  A typical response may be as follows:

[tim@Fedora16 ~]$ ifconfig

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1 Mask:255.0.0.0
 
          inet6 addr: ::1/128 Scope:Host
 
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
 
          RX packets:72 errors:0 dropped:0 overruns:0 frame:0
 
          TX packets:72 errors:0 dropped:0 overruns:0 carrier:0
  
          collisions:0 txqueuelen:0 
          RX bytes:4864 (4.7 KiB)  TX bytes:4864 (4.7 KiB)



p2p1      Link encap:Ethernet HWaddr 08:00:27:19:34:EF 
          inet addr:10.0.2.15 Bcast:10.0.2.255  Mask:255.255.255.0
                   
          inet6 addr: fe80::a00:27ff:fe19:34ef/64 Scope: Link
up 
          BROADCAST RUNNING MULTICAST MTU:1500  Metric:1
                     
          RX packets:9 errors:0 dropped:0 overruns:0 frame:0
          
          TX packets:33 errors:0 dropped:0 overruns:0 carrier:0
          
          collisions:0 txqueuelen:1000 
          
          RX bytes:2015 (1.9 KiB)  TX bytes:5882 (5.7 KiB)



As you can see from the example above we can see the "UP" interfaces, their IPv4 and IPv6 addresses along with their netmask and broadcast addresses. It also gives a snap shot of received and sent packets, and collisions.


With the use of further options such as:

1. **[-a]**  lists all interfaces whether they are up or down

2. **[-s]**  (short listing) gives a one line summary of the interfaces

3. **[-v]**  (verbose) gives extra information if there are errors for troubleshooting


You can also change the ip, broadcast and other interface peramaters as folows:


	1. to change the ip address of an interface

	  *(as root)*  ifconfig *(interface)* (xxx.xxx.xxx.xxx)/ *(mask bits)* or netmask xxx.xxx.xxx.xxx




	2. to add a secondary address to an interface

	  *(as root)*   ifconfig *(interface)* add (xxx.xxx.xxx.xxx)/ *(mask bits)* or netmask xxx.xxx.xxx.xxx





The list below comes directly from Ubuntu ifconfig --help file and shows proper syntax of more ifconfig options:

ifconfig [-a] [-v] [-s] <interface> [[<AF>] <address>]
  	 [add <address>[/<prefixlen>]]
  	 [del <address>[/<prefixlen>]]
  	 [[-]broadcast [<address>]]  [[-]pointopoint [<address>]]
  	 [netmask <address>]  [dstaddr <address>]  [tunnel <address>]
  	 [outfill <NN>] [keepalive <NN>]
  	 [hw <HW> <address>]  [metric <NN>]  [mtu <NN>]
  	 [[-]trailers]  [[-]arp]  [[-]allmulti]
 	 [multicast]  [[-]promisc]
  	 [mem_start <NN>]  [io_addr <NN>]  [irq <NN>]  [media <type>]
  	 [txqueuelen <NN>]
  	 [[-]dynamic]
 	 [up|down] ...

++++
*ip*
++++

The IP command is used to show and/or manipulate routing, devices, policy routing and tunnels within a Linux system.  

**sudo ip link set eth0 up**      

*This command will bring the interface eth0 up (debian)*


**sudo ip link set eth0 down**    

*This command will bring the interface eth0 down (debian)*

Below is the IP --help file from Ubuntu Server

tim@ubuntu:~$ ip -help
  Usage: ip [ OPTIONS ] OBJECT { COMMAND | help }

       ip [ -force ] -batch filename
                   where  OBJECT := { link | addr | addrlabel | route | rule | neigh | ntable |
                   tunnel | tuntap | maddr | mroute | mrule | monitor | xfrm }
                   
 
         OPTIONS := { -V[ersion] | -s[tatistics] | -d[etails] | -r[esolve] |
                    -f[amily] { inet | inet6 | ipx | dnet | link } | 



                    -rc[vbuf] [size]}

Below there are some examples of the above syntax and what they do.

tim@ubuntu:~$ ip -s link  

*shows statistics of the links which is good for troubleshooting*


1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    RX: bytes  packets  errors  dropped overrun mcast   
    1579       12       0       0       0       0      
    TX: bytes  packets  errors  dropped carrier collsns 
    1579       12       0       0       0       0      
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP qlen 1000
    link/ether 08:00:27:91:11:9b brd ff:ff:ff:ff:ff:ff
    RX: bytes  packets  errors  dropped overrun mcast   
    2300       13       0       0       0       0      
    TX: bytes  packets  errors  dropped carrier collsns 
    20093      130      0       0       0       0      




tim@ubuntu:~$ ip -d link  

*shows the links details without packet stats*


1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP qlen 1000
    link/ether 08:00:27:91:11:9b brd ff:ff:ff:ff:ff:ff

tim@ubuntu:~$ ip -V
ip utility, iproute2-ss110317

*shows the version of the ip utility*

+++++++
*route*
+++++++

The route command is used to show and/or manipulate the ip routing table within Linux.
Below is the sytax and usage from Ubuntu Server help file and explanations.


       route [-v] [-FC] {add|del|flush}      *Modify routing table (add or delete routes)*

       route {-h|--help}                     *route help file*
       route {-V|--version}                  *Display version/author*

        **[-v]**            *be verbose (detailed routing information)*

        **[-n]**            *don't resolve names (don't use DNS)*

        **[-e]**            *display other/more information (extended)*

        **[-F]**            *display Forwarding Information (port forwarding)*

        **[-C]**            *display routing cache*


  
      List of possible address families (which support routing):
         inet (DARPA Internet) inet6 (IPv6) ax25 (AMPR AX.25) 
         netrom (AMPR NET/ROM) ipx (Novell IPX) ddp (Appletalk DDP) 
         x25 (CCITT X.25)  

          *you can see that Linux supports a wide range of protocols*


+++++++++
*netstat*
+++++++++

The nestat command shows the status/connections, routing tables and multicast statistics on a network 

and used for network troubleshooting.

**tim@ubuntu:~$ netstat -e**



*detailed connection status on the network (good troubleshooter)*



*shows Active Internet connections*

*protocols*



*received packets*

*sent packets*



*connected ports and the files in use*



**tim@ubuntu:~$ netstat -s**


  Ip:
    83 total packets received

    2 with invalid addresses

    0 forwarded

    0 incoming packets discarded

    81 incoming packets delivered

    86 requests sent out

  Icmp:
    0 ICMP messages received

    0 input ICMP message failed.

    ICMP input histogram:

    0 ICMP messages sent

    0 ICMP messages failed

    ICMP output histogram:

  Tcp:
    1 active connections openings

    1 passive connection openings

    0 failed connection attempts

    0 connection resets received

    0 connections established

    12 segments received

    12 segments send out

    1 segments retransmited

    0 bad segments received.

    0 resets sent

  Udp:
    62 packets received

    0 packets to unknown port received.

    0 packet receive errors

    69 packets sent

  *Above is an awesome example of the netstat commands power in troubleshooting show tcp* 
  *connectionsip packets sent and received and ICMP attempts.*



++++++++++
References
++++++++++

accessed 1/27/2012:  http://www.techrepublic.com/article/linux-101-use-ifconfig-in-linux-to-configure-your-network/6040932

accessed 1/27/2012:  http://linux.die.net/man/8/ip

accessed 1/29/2012:  http://linux.die.net/man/8/route

accessed 1/30/2012:  http://linux.die.net/man/8/netstat





 









