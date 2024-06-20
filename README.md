# ISP Implementation Project

[![Languages](https://img.shields.io/badge/%E4%B8%AD%E6%96%87-zh-C8161E.svg)](README-zh.md)
[![GPLv3 license](https://img.shields.io/badge/license-GPLv3-lightgrey.svg)](LICENCE.txt)

### Project Overview

This project involves the design, configuration, and implementation of an Internet Service Provider (ISP) network, using TCP/IP networks and Unix-based systems. It provides hands-on experience in managing and delivering various network services, adhering to both intra-domain and inter-domain routing protocols.

### Objectives

- **Network Design:** Develop a comprehensive network design that includes IP address allocation, network topology, and service implementation.
- **Routing Protocols:** Implement and manage both intra-domain (OSPF) and inter-domain (BGP) routing protocols to ensure efficient and redundant network paths.
- **Service Provision:** Configure essential ISP services such as DNS, DHCP, and Web services.
- **Testing and Troubleshooting:** Perform extensive testing and troubleshooting to validate the network design and service implementations.

### Network Design

The network design for ASN 125 is based on the following components:

- **Network Topology:** A detailed network diagram illustrating the connection between various network devices and their interfaces.
- **IP Address Allocation:** A systematic allocation of IP addresses and domain names to all device interfaces.

#### Network Diagram

![AS125 network topology design diagram](./125.png "AS125 network topology design diagram")

#### IP Address Allocation

| Device | Interface | IP Address | Domain Name       |
| ------ | --------- | ---------- | ----------------- |
| r1     | eth0      | 1.0.0.5/31 | r1eth0.isp125.lab |
| ...    | ...       | ...        | ...               |

### Routing Implementation

#### Intra-domain Routing

- **Protocol:** OSPF (Open Shortest Path First)
- **Rationale:** OSPF is chosen for its faster convergence compared to RIP, and its ability to avoid equal-cost paths through cost differentiation.
- **Design:** Each router is connected with at least two interfaces to ensure redundancy. Specific cost values are assigned to different paths to avoid equal-cost paths.

#### Inter-domain Routing

- **Protocol:** BGP (Border Gateway Protocol)
- **Configuration:** BGP is implemented on AS125R1 and AS125R2, with AS125R1-AS1 as the primary link and AS125R2-AS21 as the backup link.
- **Policy:** Traffic is primarily routed through AS125R1-AS1, with AS125R2-AS21 serving as a backup. Route maps and BGP attributes are used to manage route selection and traffic flow effectively.

### Services Implementation

#### DNS

- **Domain:** ns.isp125.lab
- **Function:** Provides forward lookup services.

#### Web

- **Domain:** www.isp125.lab
- **Content:** Hosts a simple text-based web page.

#### DHCP

- **Domain:** dhcpd.isp125.lab
- **Function:** Dynamically assigns IP addresses to client devices.

### Testing and Validation

Extensive testing was conducted to ensure the reliability and performance of the network and its services. This included:

- **Connectivity Tests:** Using `ping` and `traceroute` to verify network connectivity.
- **Service Verification:** Ensuring DNS resolution, web accessibility, and dynamic IP assignment.

### Conclusion

This project successfully demonstrates the capability to design, implement, and manage a fully functional ISP network. It highlights the technical skills required for network design, routing protocol configuration, and service provision, as well as the ability to troubleshoot and resolve network issues.

For the Chinese version of this README, please refer to [README-zh.md](README-zh.md).