# Trading Floor Support Network

This project is a multi-floor enterprise network designed for a Trading Floor Support Centre in Cisco Packet Tracer.

The main idea was to build a network where different departments are separated using VLANs, while still allowing the required communication between them. I also added redundancy at the core, dynamic routing, network services and basic security features.

## Network Overview

The network consists of three floors.

### First Floor

| Department | VLAN | Network |
|---|---:|---|
| Sales & Marketing | 10 | 172.16.1.0/25 |
| HR & Logistics | 20 | 172.16.1.128/25 |

### Second Floor

| Department | VLAN | Network |
|---|---:|---|
| Finance & Accounts | 30 | 172.16.2.0/25 |
| Administration & Public Relations | 40 | 172.16.2.128/25 |

### Third Floor

| Department | VLAN | Network |
|---|---:|---|
| ICT | 50 | 172.16.3.0/25 |
| Server Room | 60 | 172.16.3.128/28 |

The Server Room contains the network services used in the project:

- DHCP Server
- DNS Server
- Email Server
- Admin PC

## Core Network

The network uses two core routers and two multilayer switches.

The core devices are connected using point-to-point /30 networks:

```text
R1 ↔ MLSW1    172.16.3.144/30
R1 ↔ MLSW2    172.16.3.148/30
R2 ↔ MLSW1    172.16.3.152/30
R2 ↔ MLSW2    172.16.3.156/30
