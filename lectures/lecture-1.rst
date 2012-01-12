***************************
Unix/Linux Networking Admin
***************************

Lecture 1 - Ch. 11 & 12
#######################

:Author: Doug Stanley <doug@douglasstanley.com>
:Date: 01/12/2012
:Version: 1.0

.. footer:: Lecture 1 - 1/12/12

.. contents::
   :class: handout

TCP/IP
======

* Everything's Layered

* Headers (see pg 257 fig 11-1)

* Wrapped going out, unwrapped coming back in

* Packets vs. Frames

.. class:: handout

Layers and Headers
------------------

In networking, it's all about the layers. "Layers" are used for encapsulation.
This allows the different parts of the networking stack to not have to worry
about things in other parts of the networking stack. It's a typical design
often referred to as separation of concerns. It's very popular, especially
among object oriented programmers.

What basically happens, is that at each "layer", that layer has it's own
specification for how it's data should look. It also has something called a
header, which basically describes the format for the data this layer is
concerned about.

We typically think of layers going from the top down. The top being what the
end user is interacting with (like a web browser application), and the bottom
being the physical wires or radio waves, in wireless networking, that connects
the devices devices. As information flows down the stack from the top to the
bottom, each layer wraps up the previous layer's data into a self contained
package, and passes it to the next layer down. Then at the other end of the
communication, the opposite happens. It comes in at the bottom, and at each
subsequent layer, it's unwrapped and passed up the stack.

.. class:: handout

Packets vs. Frames
------------------

Most often, these terms are used interchangeably, however, there is a subtle
difference between them. Typically, the word frame refers to what gets sent out
over ethernet (or possibly other link layer mediums). A packet, is used more to
refer to pieces of information at the protocol levels. So, you typically have
a packet, inside a frame.


OSI Model
=========

* Model is abstract, mostly used as a reference

  * i.e. Is that a layer 2 or 3 switch?

* Came after the TCP/IP model

  * TCP/IP loosely maps to OSI (pg. 260, fig. 11-3)


The Layers
==========

* Layer 1 - Physical (wire)

* Layer 2 - Link (ethernet)

* Layer 3 - Network (IP)

* Layer 4 - Transport (TCP or UDP)

* Layer 5-7 - Session, Presentation, Application

  * Sometimes TCP is considered layer 4 & 5


TCP vs UDP
==========

* Mostly the same....except

* TCP Based on idea of sessions

* TCP guarantees delivery of packets in correct order.

* UDP is stateless (i.e. each packet independant).

* No guarantee on the order UDP packets will arrive


TCP Header Anatomy
==================

* Source and Destination port number

* Sequence  & Acknowledgement Number

* Flags

* TCP Checksum

* Window size

.. class:: handout

TCP Header Anatomy Explained
----------------------------

Communication is based on ports. This was setup to allow a single IP address
to have many simultaneous connections (about 65535).

The checksum is a crc (cyclic redundancy check) based checksum. Essentially,
the data in the payload of the packet is fed into an algorithm which gives a
number back (the checksum). The checksum is added as part of the packet when it
is sent out. Then the receiver can do the same calculation on the data it
received, and if the checksum it calculated is the same as the one put in the
packet by the sender, then it can be reasonably assumed the data is intact.
This is mainly done to detect problems where packets may have been corrupted
in transit. Malicious people in the middle may still alter the data in the
packet, and then just replace the crc with a new one. So it doesn't prevent
anyone from modifying the data in the packet. It just lets the recipient know
if the packet needs to be re-requested or not.

The sequence and acknowledgement numbers are used to guarantee that packets
arrive in the correct order. Essentially, each side knows what packets it has
sent, and which ones it's waiting for. If one side receives a packet that it's not expecting, it assumes the one it was expecting got lost somewhere along the
way, and re-requests it.

The flags are used for various things, but most importantly, they're used for
determining the state of the TCP connection, or to alter the state (start over,
shut down, etc).

Window size is used to dynamically adjust how much data is being sent or
received. If the receiving end misses a packet, it assumes something is wrong
with the connection, and signals to the other end to try sending less data
at a time, by adjusting the window size. It scales it down until either
packets get accepted as expected. 


TCP Connection Life Cycle
=========================

1. Connection initiated by sending packet with SYN flag

2. Response is sent back with SYN and ACK set

3. Client sends packet back with ACK set

4. Packets get sent to the server, packets with ACK get sent back

5. When finished, send a final packet with the FIN flag set


ARP and Ethernet
================

* Special packet types

* Used to learn Ethernet address associated with IP address

* Hosts (and "smart" devices) cache

* Requests are broadcast to entire LAN

* Responses come directly from the host (usually)

* Can be used with other protocols

  * i.e. not just for IP and Ethernet


IP Networks
===========

* Networks broken into smaller "subnets"

  * There are limits to how many devices can be in a network

* Netmask used to determine if an IP is on the same net as me

  * On the same net as me? Ethernet/link layer

  * On a different net? Needs to be routed

* Routers know how to get to other nets

  * Static vs Dynamic routing

.. class:: handout

More on Networks and Routing
----------------------------

Hosts on the same ethernet segment simply can communicate more or less
directly.

Static routing is basically done with a simple table. It's basically a list
of destination networks, and the "hext hop" to send them to.

Dynamic routing isn't much different than static routing, except that these
tables are dynamically generated and typically more or less updated in real
time. Routers basically broadcast to one another what networks they know how to
get to. Then each router knows which routers to talk to for certain networks.


IPv6
====

* Currently the internet mostly uses IPv4

* Only 2^32 (about 4 billion giver or take) possible

* They're now all gone

* IPv6, has 2^128 possible (more IPs than atoms in the sun?)

* Slow to adopt because of technical hurdles.

  * Not as simple as flipping a switch to change


TCP Dump
========

* Captures traffic on the network

* Can be used to analyze traffic, find problems

* Alternatives like wireshark provide a GUI

.. class:: handout

Overview of tcpdump
-------------------

Here are some important pieces of info about using tcpdump...

(Need to write more here.)

Some more
~~~~~~~~~

+------+--------+
| Test | Test 2 |
+======+========+
| 1    | 2      |
+------+--------+



Network Configuration Overview
==============================

* Varies from distro to distro

  * Debian vs Redhat (and some others)

  * Mainly the location of config files

  * Different flavors of Unix have other subtle differences too

    * i.e. bsd's net device naming scheme

* Generally, most commands are the same accross the board though


The Commands
============

* ifconfig

* route

* ip

* ifup/ifdown

* netstat
