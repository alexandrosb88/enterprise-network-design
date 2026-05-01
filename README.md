# enterprise-network-design

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)
<br />

## Description

> ### CCNA-level Enterprise Network Design built in Cisco Packet Tracer
<br />

This repository presents a comprehensive enterprise network 
design and implementation for a fictitious company, built 
entirely in Cisco Packet Tracer.

The project incorporates a wide range of CCNA-level concepts 
and real-world networking practices, including:

- Structured IP addressing scheme
- VLAN segmentation for Data, Voice, Wireless, DMZ and Management traffic.
- Static and dynamic (DHCP) addressing
- Etherchannel (LACP) for link aggregation
- HSRP for gateway redundancy
- Inter-VLAN routing
- Wireless LAN Controller (WLC) configuration with Lightweight APs
- OSPF dynamic routing and static routing

<br />
<br />

## Network Topology

<br />
<br />

***------------------------- WAN / DMZ / PERIMETER -------------------------***
<br />
<br />
![network-topology-1](resource_files/network-topology-1.png)
<br />
<br />
***------------------------- INTERNAL NETWORK A -------------------------***
<br />
<br />
![network-topology-2](resource_files/network-topology-2.png)
<br />
<br />
***------------------------- INTERNAL NETWORK B -------------------------***
<br />
<br />
![network-topology-3](resource_files/network-topology-3.png)

<br />
<br />

*View the full network topology [here](resource_files/network-topology.png)* 

<br />

*You can download the packet tracer file [here](resource_files/network-topology.png)* 
<br />
<br />

## Configuration Breakdown


> *Expand each section to view the configuration commands*

<details>

<summary>IP Addressing and Subnetting</summary>

<br />
<br />

Core Switch 1
```
ip routing

int g1/0/1
no switchport
no shut
ip address 10.2.2.1 255.255.255.252

int g1/0/2
no switchport
no shut
ip address 10.2.2.5 255.255.255.252
exit
do write memory
```
Core Switch 2
```
ip routing

int g1/0/1
no switchport
no shut
ip address 10.2.2.13 255.255.255.252

int g1/0/2
no switchport
no shut
ip address 10.2.2.9 255.255.255.252
exit
do write memory
```

</details>
EtherChannel: Implement the Link Aggregation Control Protocol (LACP) for EtherChannel configuration, enhancing link aggregation efficiency.
STP PortFast and BPDUguard: Configure Spanning Tree Protocol (STP) PortFast and BPDUguard to expedite port transitions from blocking to forwarding states.
Subnetting: Utilize subnetting techniques to allocate the appropriate number of IP addresses to each network group.
Basic Settings: Configure fundamental device settings, including hostnames, and console passwords, enable passwords, banner messages, password encryption, and disable IP domain lookup.
Inter-VLAN Routing: Enable devices in all departments to communicate with one another by configuring the respective multilayer switch for inter-VLAN routing.
Core Switch: Assign IP addresses to Multilayer switches to enable both routing and switching functionalities.
DHCP Server: Ensure that all devices in the network obtain IP addresses dynamically from the servers located at the server farm site.
HSRP: Implement high-availability router protocols such as HSRP to achieve redundancy, load balancing, and failover capabilities.
Static Addressing: Allocate static IP addresses to devices located in the server room.
Routing Protocol: Utilize Open Shortest Path First (OSPF) as the routing protocol to advertise routes on the firewall, routers, and multilayer switches.
Standard ACL for SSH: Establish a simple standard Access Control List (ACL) on the VTY line to permit remote administrative tasks via SSH only for the Senior Network Security Engineer PC.
Cisco ASA Firewall: Configure default static routes, basic settings, security levels, zones, and policies on the Cisco ASA Firewall to define access control and resource utilization within the network.
