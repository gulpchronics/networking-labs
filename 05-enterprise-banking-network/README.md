
# Enterprise Banking Network

A Cisco Packet Tracer project based on a banking and insurance company network. The company has a four-floor office building, with different departments on each floor.

I designed and configured the network to practice VLANs, subnetting, OSPF routing, DHCP, wireless networking, server connectivity and basic network security.

I also created a network design model using Microsoft Visio before implementing the topology in Cisco Packet Tracer.

---

## Project Overview

The network is divided into four floors, with each floor having its own departments and network devices.

Each floor contains:

- Department-specific VLANs
- Switches for connecting end devices
- Wireless access points
- PCs and printers
- A Layer 3 switch
- A router for communication with other floors

The fourth floor also contains the server room, which includes DHCP, HTTP and Email servers.

---

## Network Design Model

Before implementing the network in Cisco Packet Tracer, I created a network design model using Microsoft Visio.

The Visio model was used to visualize the network structure, connections between floors and the overall layout of the enterprise network.

> Add your Visio design image to the `images` folder and update the image name below.

![Visio Network Design](images/visio-network-design.png)

---

## Network Topology

The complete network was implemented in Cisco Packet Tracer.

The topology contains four routers, Layer 3 switches, access switches, wireless access points, end devices and servers.

![Network Topology](images/topology.png)

### Floor Distribution

| Floor | Departments |
|---|---|
| First Floor | Management, Research, Human Resource |
| Second Floor | Marketing, Accounting, Finance |
| Third Floor | Logistics and Store, Customer Care, Guest Area |
| Fourth Floor | Administration, ICT, Server Room |

---

## Department Details

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
| Server Room | 2 Admin PCs | — |

The server room contains:

- DHCP Server
- HTTP Server
- Email Server

---

## VLAN and IP Addressing

Each department is assigned a separate VLAN and subnet.

The network uses the `192.168.10.0` address space as the base network. Subnetting was performed according to the number of devices required in each department.

The VLANs used in the project include:

| Department | VLAN |
|---|---:|
| Management | 10 |
| Research | 20 |
| Human Resource | 30 |
| Marketing | 40 |
| Accounting | 50 |
| Finance | 60 |
| Logistics and Store | 70 |
| Customer Care | 80 |
| Guest Area | 90 |
| Administration | 100 |
| ICT | 110 |
| Server Room | 120 |

The subnets were configured using `/26` networks for the departmental networks.

![IP Addressing](images/ip-addressing.png)

---

## Routing - OSPF

OSPF was configured on the routers and Layer 3 switches to advertise routes between the different networks.

The routers on each floor are connected through point-to-point networks using `/30` subnets.

OSPF allows the different floors and VLAN networks to communicate with each other without manually configuring static routes for every network.

![OSPF Verification](images/ospf-verification.png)

### Routing Verification Commands

```text
show ip route
show ip ospf neighbor
show ip protocols
show ip interface brief
```

---

## DHCP Configuration

A dedicated DHCP server was configured in the server room.

The DHCP server provides IP addresses dynamically to devices across the different departments. DHCP relay configuration was used on the Layer 3 switches so that devices in different VLANs could reach the DHCP server.

![DHCP Pool](images/dhcp-pool.png)

### DHCP Verification

I checked the DHCP configuration and verified that end devices were receiving IP addresses from the configured pools.

The following checks were used during configuration:

```text
show ip dhcp binding
show ip interface brief
```

---

## Wireless Network

Each department has a wireless access point for users.

The wireless networks were configured to provide connectivity for wireless devices along with the wired PCs and printers.

The wireless setup was included as part of the department-level network design.

---

## Inter-VLAN Routing

Each department is placed in a separate VLAN and subnet.

Inter-VLAN routing was configured on the Layer 3 switches to allow communication between the different departmental networks.

The `ip helper-address` command was also used to forward DHCP requests from the VLANs to the dedicated DHCP server.

---

## Port Security

Port security was configured on the access switches to control which devices could connect to selected switch ports.

Sticky MAC address learning was used to learn and secure the MAC addresses of connected devices.

The violation mode was configured as `shutdown`.

![Port Security Verification](images/port-security-verification.png)

### Port Security Features

- Sticky MAC address learning
- MAC address security
- Maximum secure MAC address limit
- Shutdown violation mode

---

## SSH Configuration

SSH was configured on the routers for remote management.

This allows the network devices to be accessed remotely instead of relying only on console access.

![SSH Verification](images/ssh-verification.png)

### SSH Configuration Features

- Hostname configuration
- Domain name configuration
- Local username and password
- VTY line configuration
- SSH-only remote access

---

## Connectivity Testing

After configuring the VLANs, IP addressing, routing and DHCP, I tested communication between different parts of the network.

The testing included:

- Communication between devices in the same VLAN
- Communication between different VLANs
- Communication between different floors
- Connectivity to the DHCP server
- Connectivity to the HTTP server
- Connectivity to the Email server
- Testing of routed networks

![Connectivity Test](images/connectivity-test.png)

---

## Verification Images

### VLAN Verification

![VLAN Verification](images/vlan-verification.png)

### IP Addressing

![IP Addressing Verification](images/ip-addressing.png)

### OSPF Verification

![OSPF Verification](images/ospf-verification.png)

### DHCP Pool

![DHCP Pool Verification](images/dhcp-pool.png)

### Port Security

![Port Security Verification](images/port-security-verification.png)

### SSH Verification

![SSH Verification](images/ssh-verification.png)

---

## Configuration Steps

The main configuration steps I followed were:

1. Basic configuration on the routers and switches.
2. VLAN creation and department assignment.
3. Configuration of access and trunk ports.
4. Subnetting and IP address assignment.
5. OSPF configuration on the routers and Layer 3 switches.
6. Static IP configuration for the server room devices.
7. DHCP server configuration.
8. Inter-VLAN routing and DHCP relay configuration.
9. Wireless network configuration.
10. Port security configuration.
11. SSH configuration on the routers.
12. Connectivity testing and troubleshooting.

---

## Commands Used for Verification

Some of the Cisco IOS commands used during the project were:

```text
show vlan brief
show ip route
show ip ospf neighbor
show ip protocols
show ip interface brief
show ip dhcp binding
show ip dhcp pool
show port-security
show port-security interface
```

These commands helped me check the VLANs, routing tables, interfaces, DHCP configuration and port security settings.

---

## What I Learned

Through this project, I practiced:

- Enterprise network design
- Creating a network model using Microsoft Visio
- VLAN configuration
- IP subnetting
- Layer 3 switching
- Inter-VLAN routing
- OSPF routing
- DHCP server configuration
- DHCP relay using `ip helper-address`
- Wireless network configuration
- Port security
- SSH remote access
- Server connectivity
- Network troubleshooting

This project helped me understand how multiple departments, floors and services can be connected together in a larger enterprise network.

---

## Project Structure

```text
05-enterprise-banking-network/
│
├── images/
│   ├── topology.png
│   ├── ip-addressing.png
│   ├── vlan-verification.png
│   ├── ospf-verification.png
│   ├── dhcp-pool.png
│   ├── port-security-verification.png
│   ├── ssh-verification.png
│   ├── connectivity-test.png
│   └── visio-network-design.png
│
├── enterprise-banking-network.pkt
└── README.md
```

---

## Tools Used

- Cisco Packet Tracer
- Microsoft Visio
- Cisco IOS CLI

---

## Project Status

**Completed**

Designed and implemented a four-floor enterprise banking network in Cisco Packet Tracer. The project includes VLANs, subnetting, OSPF, DHCP, wireless networking, server connectivity, port security and SSH configuration.

