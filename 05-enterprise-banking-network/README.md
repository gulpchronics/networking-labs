# Enterprise Banking Network

A Cisco Packet Tracer project based on an enterprise banking and insurance company network. The company has a four-floor building with different departments, separate VLANs, wireless networks, servers and inter-floor routing.

I built this project to practice designing and configuring a larger enterprise network using VLANs, subnetting, OSPF, DHCP, wireless networking and basic network security.

I also created a network design model using Microsoft Visio before implementing the topology in Cisco Packet Tracer.

---

## Project Overview

The network is designed for a company with four floors.

Each floor contains different departments, and every department has its own VLAN and subnet. The network includes wired and wireless users, printers, servers and routers connecting the floors.

The project includes:

- Four-floor enterprise network
- Department-based VLANs
- IPv4 subnetting
- OSPF routing
- Inter-VLAN routing
- DHCP server
- HTTP server
- Email server
- Wireless access points
- SSH configuration
- Switch port security
- Network verification and connectivity testing

---

## Network Design

The network design was first planned using Microsoft Visio and then implemented in Cisco Packet Tracer.

### Visio Network Model

The Visio model was used to visualize the network structure, departments, routers, switches and connections before creating the Packet Tracer topology.

<!-- Add your Visio model image here if you upload it -->
<!-- ![Visio Network Model](images/visio-model.png) -->

### Cisco Packet Tracer Topology

![Network Topology](images/topology.png)

The topology contains four floors:

- First Floor
- Second Floor
- Third Floor
- Fourth Floor

Each floor has its own router and switches. The routers are connected using point-to-point /30 networks.

---

## Departments and Devices

### First Floor

| Department | PCs | Printers |
|---|---:|---:|
| Management | 20 | 4 |
| Research | 20 | 4 |
| Human Resource | 20 | 4 |

### Second Floor

| Department | PCs | Printers |
|---|---:|---:|
| Marketing | 20 | 4 |
| Accounting | 20 | 4 |
| Finance | 20 | 4 |

### Third Floor

| Department | PCs | Printers |
|---|---:|---:|
| Logistics and Store | 20 | 4 |
| Customer Care | 20 | 4 |
| Guest Area | 40 | 2 |

### Fourth Floor

| Department | PCs | Printers |
|---|---:|---:|
| Administration | 20 | 2 |
| ICT | 20 | 2 |
| Server Room | 2 Admin PCs | Servers |

The server room contains:

- DHCP Server
- HTTP Server
- Email Server

---

## VLAN Configuration

Each department is assigned a separate VLAN and IP subnet.

| Department | VLAN | Network |
|---|---:|---|
| Management | 10 | 192.168.10.0/26 |
| Research | 20 | 192.168.10.64/26 |
| Human Resource | 30 | 192.168.10.128/26 |
| Marketing | 40 | 192.168.10.192/26 |
| Accounting | 50 | 192.168.11.0/26 |
| Finance | 60 | 192.168.11.64/26 |
| Logistics | 70 | 192.168.11.128/26 |
| Customer Care | 80 | 192.168.11.192/26 |
| Guest | 90 | 192.168.12.0/26 |
| Administration | 100 | 192.168.12.64/26 |
| ICT | 110 | 192.168.12.128/26 |
| Server Room | 120 | 192.168.12.192/26 |

Each VLAN uses a separate subnet to divide the departments and manage network communication.

---

## IP Addressing and Subnetting

The base network used for the departments is:

```text
192.168.10.0
