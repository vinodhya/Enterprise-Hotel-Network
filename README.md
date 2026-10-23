# Enterprise Hotel Network Design & Implementation

## Project Overview

This project focuses on designing and implementing a multi-floor hotel network using **Cisco Packet Tracer**. The network connects eight departments across three floors while providing department-level network segmentation, dynamic IP addressing, inter-network communication, and secure remote router access.

## Objectives

- Design a network for three floors using three routers and three switches.
- Create separate VLANs for each department.
- Configure inter-VLAN routing using Router-on-a-Stick.
- Implement OSPF dynamic routing between routers.
- Configure DHCP on routers for automatic IP address allocation.
- Provide Wi-Fi connectivity for laptops and smartphones.
- Enable SSH for secure remote router administration.
- Configure switch port security using sticky MAC address learning and shutdown violation mode.
- Verify connectivity between departments.

## Network Structure

| Floor | Department | VLAN ID | Network Address |
|---|---|---:|---|
| 1st Floor | Reception | 80 | `192.168.8.0/24` |
| 1st Floor | Store | 70 | `192.168.7.0/24` |
| 1st Floor | Logistics | 60 | `192.168.6.0/24` |
| 2nd Floor | Finance | 50 | `192.168.5.0/24` |
| 2nd Floor | HR | 40 | `192.168.4.0/24` |
| 2nd Floor | Sales & Marketing | 30 | `192.168.3.0/24` |
| 3rd Floor | Admin | 20 | `192.168.2.0/24` |
| 3rd Floor | IT | 10 | `192.168.1.0/24` |

## Technologies and Protocols

- **Cisco Packet Tracer** – Network design and simulation
- **VLANs** – Department-level network segmentation
- **802.1Q** – VLAN tagging on trunk links
- **Router-on-a-Stick** – Inter-VLAN routing
- **OSPF** – Dynamic routing
- **DHCP** – Automatic IP address allocation
- **SSH** – Secure remote router access
- **Port Security** – Sticky MAC address learning and shutdown violation mode
- **Serial DCE/DTE links** – Router-to-router connectivity

## Router-to-Router Connections

The three routers are interconnected using serial links in a triangle topology.

| Connection | Network Address |
|---|---|
| R1 – R2 | `10.10.10.8/30` |
| R2 – R3 | `10.10.10.0/30` |
| R3 – R1 | `10.10.10.4/30` |

OSPF is configured to advertise the department networks and router-to-router networks.

## Security Configuration

- SSH Version 2 for remote router administration.
- Local username authentication for SSH access.
- Port security on the IT switch's `Fa0/4` interface.
- Sticky MAC address learning to dynamically learn the authorized device's MAC address.
- Maximum of one secure MAC address on the protected port.
- Shutdown violation mode for unauthorized MAC address violations.

The designated **Test-PC** is connected to `SW3 Fa0/4` and is used to test remote SSH access to the routers.

## Testing and Verification

The following tests are used to verify the implementation:

- DHCP address allocation for end devices.
- VLAN membership and trunk configuration.
- OSPF neighbor relationships and learned routes.
- Successful ping tests between devices in different VLANs.
- SSH login from Test-PC to the routers.
- Port security status and sticky MAC address learning.



## Learning Outcomes

Through this project, I gained practical experience in:

- Designing a multi-floor enterprise network.
- Configuring VLANs and inter-VLAN routing.
- Implementing OSPF and DHCP.
- Establishing secure remote router access.
- Applying switch port security.
- Troubleshooting and verifying network connectivity.

---

*This project was developed for networking practice and educational purposes using Cisco Packet Tracer.*
