# 6. IP Addressing and Subnetting

## Overview
IP addressing is the backbone of network communication, providing unique identifiers for devices on a network, much like postal addresses for physical mail. This module delves into the structure of IP addresses, focusing on both IPv4 and IPv6, and explores subnetting as a method to divide large networks into smaller, more manageable subnetworks. Subnetting enhances efficiency, security, and performance by reducing broadcast domains and optimizing traffic flow. Learners will learn to calculate subnets, understand address allocation, and differentiate between public and private addresses, equipping them to plan scalable network architectures.

## IPv4 and IPv6 Structure
IP addresses come in two primary versions: IPv4 and IPv6, each with distinct formats and capacities to meet evolving internet demands.

- **IPv4 Structure**: IPv4 addresses are 32-bit numbers, typically represented in dotted decimal notation (e.g., 192.168.1.1). This format divides the address into four octets (8 bits each), separated by periods, allowing for approximately 4.3 billion unique addresses. Each octet ranges from 0 to 255. The address is divided into a network portion (identifying the overall network) and a host portion (identifying devices within that network). However, due to address exhaustion, IPv4 is being phased out in favor of IPv6.

- **IPv6 Structure**: Designed to address IPv4's limitations, IPv6 uses 128-bit addresses, represented in hexadecimal notation with eight groups of four hexadecimal digits separated by colons (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334). This vastly expands the address space to about 3.4 × 10^38 unique addresses. IPv6 simplifies headers for faster routing, supports auto-configuration, and eliminates the need for NAT in many cases. Leading zeros in groups can be omitted, and consecutive zeros can be abbreviated with "::" (e.g., 2001:db8::1).

The transition from IPv4 to IPv6 involves dual-stack configurations, tunneling, and translation mechanisms to ensure compatibility.

## Subnet Masks and CIDR Notation
Subnet masks define the boundary between the network and host portions of an IP address, enabling devices to determine if traffic is local or requires routing.

- **Subnet Masks**: A 32-bit number (for IPv4) that uses binary 1s for the network portion and 0s for the host portion, often written in dotted decimal (e.g., 255.255.255.0). In binary, it might look like 11111111.11111111.11111111.00000000. By applying a bitwise AND operation with the IP address, the network ID is extracted.

- **CIDR Notation**: Classless Inter-Domain Routing (CIDR) replaces classful addressing with a slash notation indicating the number of network bits (e.g., 192.168.1.0/24 means a 24-bit network prefix, equivalent to a subnet mask of 255.255.255.0). CIDR allows flexible allocation, reducing waste from rigid class systems (A, B, C). For IPv6, CIDR works similarly (e.g., 2001:db8::/32).

| CIDR Prefix | Subnet Mask (Decimal) | Usable Hosts | Example Network |
|-------------|-----------------------|--------------|-----------------|
| /24        | 255.255.255.0        | 254         | 192.168.1.0/24 |
| /25        | 255.255.255.128      | 126         | 192.168.1.0/25 |
| /30        | 255.255.255.252      | 2           | 192.168.1.0/30 |

This notation is crucial for route summarization and efficient IP allocation by ISPs.

## Subnetting Techniques and Calculations
Subnetting involves borrowing bits from the host portion to create additional network bits, dividing one network into multiple subnets. This is done by extending the subnet mask beyond the default class boundary.

- **Basic Technique**: Start with a base network (e.g., 192.168.0.0/16). To create /24 subnets, borrow 8 bits, yielding 256 subnets (2^8), each with 254 hosts (2^8 - 2). The formula for subnets is 2^(borrowed bits), and for hosts per subnet is 2^(remaining host bits) - 2 (subtracting network and broadcast addresses).

- **Calculations Example**: For 10.0.0.0/8, subnet into /20 blocks:
  - Borrowed bits: 12 (from /8 to /20).
  - Number of subnets: 2^12 = 4,096.
  - Hosts per subnet: 2^12 - 2 = 4,094.
  - First subnet: 10.0.0.0/20; next: 10.0.16.0/20 (increment by 16 in the third octet).

Variable Length Subnet Masking (VLSM) allows different subnet sizes within the same network for optimization (e.g., /30 for point-to-point links, /24 for departments). Tools like subnet calculators can verify, but manual binary math ensures understanding.

Common pitfalls include forgetting to reserve network/broadcast addresses and overlapping ranges.

## Private vs. Public IP Ranges
IP addresses are classified as public (routable on the internet) or private (for internal use only), with private addresses requiring NAT for external access.

- **Public IP Ranges**: Assigned by IANA and regional registries, these are globally unique and used for direct internet communication. Examples include any address not in private ranges (e.g., 8.8.8.8 for Google's DNS).

- **Private IP Ranges** (per RFC 1918 for IPv4):
  - 10.0.0.0/8 (1,677,7216 hosts)
  - 172.16.0.0/12 (1,048,576 hosts)
  - 192.168.0.0/16 (65,536 hosts)
  
  These are reserved for local networks (e.g., home routers use 192.168.x.x). IPv6 has unique local addresses (fc00::/7) and global unicast (2000::/3).

Public addresses are scarce and costly, while private ones enable large internal networks without consuming global space. Best practices include using private ranges for LANs and reserving public IPs for servers or edge devices.

## Purpose
This module empowers learners to design and manage efficient IP addressing schemes, from calculating subnets for enterprise networks to understanding the IPv4-to-IPv6 migration. By mastering these concepts, participants can optimize resource allocation, troubleshoot addressing conflicts, and implement scalable infrastructures that support growing connectivity demands.
