# Simple Networking project - Accounts & Delivery Department Network

A basic departmental network designed and simulated using Cisco Packet Tracer. This project demonstrates subnetting, IP addressing, router interface configuration, and connectivity between two departments.

## Project Overview

The objective of this lab is to connect the **ACCOUNTS** and **DELIVERY** departments through a router and switches, allowing devices in both departments to communicate across separate IP subnets.

This project was completed as part of my practical networking learning journey.

## Objectives

* Design a network connecting two departments.
* Configure appropriate network devices and connections.
* Divide the given network address into two subnets.
* Assign IP addresses, subnet masks, and default gateways.
* Configure router interfaces for inter-subnet communication.
* Verify connectivity using the `ping` command.

## Tools & Technologies

* **Cisco Packet Tracer**
* IPv4 Addressing
* Subnetting
* Static IP Configuration
* Router Interface Configuration
* Basic Inter-Subnet Routing
* ICMP / Ping

## Network Topology

The simulated network consists of:

* **1 Router** — Cisco 2911
* **2 Switches** — Cisco 2960-24TT
* **4 PCs** — 2 in each department
* **2 Printers** — 1 in each department

The router connects the two departmental networks and acts as the default gateway for each subnet.

## IP Addressing Scheme

The network `192.168.40.0/24` was divided into two `/25` subnets.

### ACCOUNTS Department

**Network:** `192.168.40.0/25`

| Device                       | IP Address     | Subnet Mask       | Default Gateway |
| ---------------------------- | -------------- | ----------------- | --------------- |
| Router0 — Accounts Interface | `192.168.40.1` | `255.255.255.128` | —               |
| PC0                          | `192.168.40.2` | `255.255.255.128` | `192.168.40.1`  |
| PC1                          | `192.168.40.3` | `255.255.255.128` | `192.168.40.1`  |
| Printer0                     | `192.168.40.4` | `255.255.255.128` | `192.168.40.1`  |

### DELIVERY Department

**Network:** `192.168.40.128/25`

| Device                       | IP Address       | Subnet Mask       | Default Gateway  |
| ---------------------------- | ---------------- | ----------------- | ---------------- |
| Router0 — Delivery Interface | `192.168.40.129` | `255.255.255.128` | —                |
| PC2                          | `192.168.40.130` | `255.255.255.128` | `192.168.40.129` |
| PC3                          | `192.168.40.131` | `255.255.255.128` | `192.168.40.129` |
| Printer1                     | `192.168.40.132` | `255.255.255.128` | `192.168.40.129` |

## Subnetting Details

| Subnet   | Network Address     | Usable Host Range                 | Broadcast Address |
| -------- | ------------------- | --------------------------------- | ----------------- |
| ACCOUNTS | `192.168.40.0/25`   | `192.168.40.1 – 192.168.40.126`   | `192.168.40.127`  |
| DELIVERY | `192.168.40.128/25` | `192.168.40.129 – 192.168.40.254` | `192.168.40.255`  |

**Subnet Mask:** `255.255.255.128`

## Connectivity Verification

Connectivity was tested using the `ping` command to verify communication between devices in the ACCOUNTS and DELIVERY departments.

The router enables communication between the two different IP subnets.

> **Verification:** Add a screenshot of the final successful ping results here.

## Project Files

| File                            | Description                                |
| ------------------------------- | ------------------------------------------ |
| `accounts-delivery-network.pkt` | Cisco Packet Tracer simulation file        |
| `network-topology.png`          | Network topology screenshot                |
| `subnetting-answers.png`        | Subnetting calculations and address ranges |
| `connectivity-test.png`         | Ping verification screenshot               |

## Key Learnings

* Dividing a `/24` network into two `/25` subnets.
* Identifying network, host, and broadcast addresses.
* Assigning IP addresses to end devices and router interfaces.
* Configuring default gateways.
* Understanding how routers enable communication between different subnets.
* Verifying connectivity using ICMP ping.
* Documenting a network simulation for future reference.

## Status

**Completed**
