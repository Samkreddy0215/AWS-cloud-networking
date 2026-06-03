# AWS Site-to-Site VPN

## What is Site-to-Site VPN?

AWS Site-to-Site VPN creates a secure encrypted connection between an on-premises network and an AWS VPC.

---

## Customer Gateway (CGW)

Customer Gateway represents the on-premises router or firewall.

Examples:

* Cisco
* Juniper
* Fortinet
* Palo Alto

---

## Virtual Private Gateway (VGW)

Virtual Private Gateway is the AWS side of the VPN connection.

It attaches to a VPC.

---

## VPN Tunnel Architecture

On-Premises Network
↓
Customer Gateway
↓
Internet
↓
Virtual Private Gateway
↓
AWS VPC

---

## VPN Redundancy

AWS creates:

* Tunnel 1
* Tunnel 2

This provides high availability.

---

## Routing Methods

### Static Routing

Routes are manually configured.

### Dynamic Routing (BGP)

Routes are automatically exchanged.

---

## Enterprise Use Cases

* Hybrid Cloud
* Branch Office Connectivity
* Data Center Extension
* Secure AWS Access

---

## Key Points

* Secure encrypted connection
* Connects On-Premises to AWS
* Uses CGW and VGW
* Supports BGP
* Uses redundant VPN tunnels
