Static Routing—Cisco Packet Tracer

#Project Overview
This project demonstrates the configuration and verification of Static Routing between two separate LAN networks using Cisco Packet Tracer.
The main objective is to enable communication between two different networks through two routers using manually configured static routes.

#Network Topology

PC0/PC1─── Switch0─── Router0 ══Serial══ Router1 ─── Switch1─── PC2/PC3

#IP Addressing:
Device Interface IP Address Subnet Mask:
PC0      Fa0     192.168.10.2  255.255.255.0
PC1      Fa0     192.168.10.3  255.255.255.0
Router0  G0/0    192.168.10.1  255.255.255.0
Router0  S0/0/0  10.0.0.1      255.255.255.252
Router1  S0/0/0  10.0.0.2      255.255.255.252
Router1  G0/0    192.168.20.1  255.255.255.0
PC2      Fa0     192.168.20.2  255.255.255.0
PC3      Fa0     192.168.20.3  255.255.255.0


#Static Routing Configuration
Router0:
ip route 192.168.20.0 255.255.255.0 10.0.0.2

Router1
ip route 192.168.10.0 255.255.255.0 10.0.0.1

#Verification
Before configuring Static Routing:
PC1 -> PC2 (Failed)

After configuring Static Routing:
PC1 -> PC2 (Successful)

#The routing tables were verified using:
show ip route

End-to-end connectivity was verified using:
ping 192.168.20.2

The packet path was also verified using:
tracert 192.168.20.2

The traffic successfully followed:
PC0—192.168.10.2 --> Router0—192.168.10.1 --> Router1—10.0.0.2 --> PC2—192.168.20.2

#Configuration Backup
The router configurations were saved using:
copy running-config startup-config

#Project Objectives
Understand how routers forward packets between different networks.
Configure IP addresses on router interfaces.
Configure a Serial WAN connection.
Configure Static Routes manually.
Verify routing tables.
Test end-to-end connectivity.
Use Ping and Traceroute for network verification.


#Tools & Technologies
Cisco Packet Tracer
Cisco IOS
IPv4
Static Routing
TCP/IP Networking

#Author:
ENG.Milad Rimon Durra