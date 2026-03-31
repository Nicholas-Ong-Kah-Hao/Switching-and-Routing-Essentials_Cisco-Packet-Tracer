# Alstom Multi-Site Enterprise Network Design

This repository contains the Cisco Packet Tracer project and documentation for a multi-site enterprise network designed for **Alstom** as part of the **CT133-3-2-SRE Switching and Routing Essentials** assignment.

The project simulates a secure, segmented, and scalable network across four locations:

- Kuala Lumpur (Headquarters)
- Australia
- Singapore
- India (Remote Branch + Server Farm)

## Project Overview

The purpose of this project is to redesign and modernize Alstom’s enterprise network infrastructure to improve:

- network efficiency
- segmentation
- scalability
- redundancy
- wireless access
- Layer 2 security

The network was implemented in **Cisco Packet Tracer** using a hierarchical approach with routing, switching, WLAN, server services, and security best practices. :contentReference[oaicite:1]{index=1}

## Objectives

- Design a segmented multi-site enterprise network
- Implement VLAN-based departmental separation
- Provide wired and wireless connectivity where required
- Enable dynamic routing between all sites
- Support centralized public services in the India server farm
- Improve gateway availability and uplink redundancy
- Apply Layer 2 security controls against common switching attacks

## Network Sites

### Kuala Lumpur (Headquarters)
Departments:
- Management
- Human Resources
- Design

Key features:
- Wired network
- VLAN segmentation
- Router-on-a-stick
- HSRP
- EtherChannel
- Layer 2 security controls

### Australia
Departments:
- Finance
- R&D
- Delivery

Key features:
- Wired + wireless network
- WLC-managed WLAN
- Lightweight AP
- WPA2-PSK security

### Singapore
Departments:
- Staff
- Guest

Key features:
- Hybrid wired and wireless setup
- WLC-managed WLAN
- Separate guest/staff segmentation

### India
Departments:
- Management
- Development

Key features:
- Wired branch network
- Centralized server farm
- Public-facing DNS, FTP, and Web services

## Technologies and Concepts Used

- Cisco Packet Tracer
- VLAN segmentation
- 802.1Q trunking
- Router-on-a-stick
- DHCP
- OSPF
- HSRP
- EtherChannel using LACP
- WLC and lightweight AP deployment
- WPA2-PSK wireless security
- DNS / FTP / Web server configuration
- Layer 2 security hardening

## Addressing Design

The project uses:

- **Private IPv4 addressing** for internal LANs
- **Documentation public IP ranges** for WAN links
- **Public addressing simulation** for the server farm

Examples from the design include:
- KL VLANs: `10.10.x.0/24`
- Australia VLANs: `10.20.x.0/24`
- Singapore VLANs: `10.30.x.0/24`
- India VLANs: `10.40.x.0/24`
- WAN links: `203.0.113.0/30` ranges
- Server farm: `198.51.100.0/28` :contentReference[oaicite:2]{index=2}

## Key Implementations

### 1. VLAN Segmentation
Each site is divided into departmental VLANs to reduce broadcast domains and improve performance and security.

### 2. Trunk Ports
802.1Q trunking is used to carry multiple VLANs between switches and upstream devices.

### 3. Router-on-a-Stick
Routers use subinterfaces to provide inter-VLAN routing for departmental networks.

### 4. DHCP
Each site provides DHCP services for local clients to simplify address assignment.

### 5. OSPF
All routers participate in OSPF for automatic route distribution across the WAN.

### 6. Wireless LAN
Australia and Singapore use WLC-managed wireless architecture with:
- management VLANs
- lightweight APs
- WLAN-to-VLAN mapping
- WPA2-PSK with AES

### 7. EtherChannel
KL access switches implement EtherChannel using **LACP** to increase bandwidth and provide link redundancy.

### 8. HSRP
KL uses HSRP to provide default gateway redundancy for client VLANs.

### 9. Server Farm
India hosts public-facing services for the enterprise, including:
- DNS
- FTP
- Web server

### 10. Inter-Site Verification
Connectivity was verified using:
- ping
- tracert
- OSPF route checks

## Security Features

This project also includes Layer 2 threat mitigation techniques, including:

- Port Security for MAC flooding protection
- DHCP Snooping to prevent rogue DHCP attacks
- Dynamic ARP Inspection (DAI) to mitigate ARP spoofing
- BPDU Guard to prevent unauthorized topology manipulation
- Password protection on routers

Additional recommended improvements discussed in the report:
- Honeypot deployment
- Bastion host implementation
- Network Access Control (NAC) :contentReference[oaicite:3]{index=3}

## Repository Contents

This repository may include:

- Cisco Packet Tracer file (`.pkt`)
- Project report/documentation
- Topology screenshots
- Configuration evidence
- Verification screenshots
- README

## Learning Outcomes

This project helped strengthen my understanding of:

- enterprise network design
- VLAN planning
- routing and switching
- wireless LAN deployment
- redundancy protocols
- server integration
- network verification
- security hardening

## Module Information

- **Module:** CT133-3-2-SRE
- **Assignment:** Switching and Routing Essentials Group and Individual Assignment
- **Group:** Group 01-08

## Author

Nicholas Ong Kah Hao and His Team Members

## Note

This project was developed for academic purposes as part of a university networking assignment.
