Ifconfig- 

 This is the Unix/Linux command for configuring and debugging your interfaces connected to your server.
 
 
ifconfig -a   =This displays all interfaces that are currently available on your server wether or not this interface is up or down.


Ifconfig has certain flags  Up means the interfaces is ready to use.   
                            Down means the interface is down and not ready                              to use.


ip-  

This Unix/Linux command has several diferent features in the system. It can be used by itself or amended to different commands to add an IP effect.

ip -v  =This particular option for the IP command will display what version of IP your server is currently running.

ip -address      =You can configure an ip address to a certain interface



route-

This Unix/Linux command is used to manipulate the ip routing table. 


route -add  =This option will give you the ability to add a certain route to the ip table

route -del   =This option can be used to delete a certain route in the Ip table




netstat-

This Unix/Linux command is used to view (print) certain network properties of the system.


netstat -c    =This particular option will cause netstat to print the selected information once every second until you cancel the command.

netstat -a   =Show all sockets wether they are listening or not.




iptables-

This Unix/Linux command is used to create filters for the Server. You can set up different targets to match certain rules and then execute certain values, ex. Accept, Drop, etc.

iptables -D  =This command will delete on or more rules in the selected chain.





References-

ifconfig

man ifconfig


IP

man ip

http://linux.die.net/man/8/ip


Route

man route

http://linux.about.com/od/commands/l/blcmdl8_route.htm


Netstat

man netstat

http://www.computerhope.com/unix/unetstat.htm


Iptables

man iptables

http://linux.about.com/od/commands/l/blcmdl8_iptable.htm