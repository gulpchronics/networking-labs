# Trading Floor Support Network

A multi-floor enterprise network designed and configured in Cisco Packet Tracer for a Trading Floor Support Centre.

The network is divided into different departments using VLANs and subnetting. It uses multilayer switches for inter-VLAN routing, OSPF for dynamic routing, redundant core devices, DHCP and other network services. Security and connectivity features such as SSH, port security, ACL and NAT/PAT are also configured.

## Network Topology

The network consists of three floors with separate departments and a dedicated Server Room.

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

The Server Room contains:

- DHCP Server
- DNS Server
- Email Server
- Admin PC

## Core Network

The core of the network uses two routers and two multilayer switches.

Point-to-point connections between the core devices are configured using /30 networks:

| Connection | Network |
|---|---|
| R1 - MLSW1 | 172.16.3.144/30 |
| R1 - MLSW2 | 172.16.3.148/30 |
| R2 - MLSW1 | 172.16.3.152/30 |
| R2 - MLSW2 | 172.16.3.156/30 |

The network also includes connections towards the ISP using:

- 195.136.17.0/30
- 195.136.17.4/30
- 195.136.17.8/30
- 195.136.17.12/30

The redundant core design provides multiple paths between the network devices and helps avoid depending on a single core link.

## Technologies and Features

### VLANs

Separate VLANs are created for each department to logically divide the network.

### Subnetting

Different subnet sizes are used according to the requirements of each network segment.

### Inter-VLAN Routing

The multilayer switches provide routing between the departmental VLANs.

### OSPF

OSPF is configured as the dynamic routing protocol for communication between the core devices.

### DHCP

A dedicated DHCP server is used to provide IP addresses to client devices.

### DNS and Email

The Server Room includes DNS and Email services for the network.

### SSH

SSH is configured for remote management of network devices.

### Port Security

Port security is configured on access ports to restrict unauthorized devices from connecting to the network.

### NAT/PAT

NAT/PAT is configured to allow internal private networks to communicate with external networks.

### ACL

Access Control Lists are used to control traffic according to the configured network requirements.

### Wireless

Wireless connectivity is included for supported users and devices.

### Redundancy

Two core routers and two multilayer switches provide redundant paths through the core network.

## Verification

The configuration was tested using Cisco IOS commands and end-device connectivity tests.

### IP Addressing

```text
show ip interface brief
