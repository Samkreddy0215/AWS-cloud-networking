# AWS Transit Gateway Connect

## Overview

AWS Transit Gateway Connect is an advanced networking feature that enables high-performance integration between AWS Transit Gateway and third-party SD-WAN or virtual network appliances using GRE (Generic Routing Encapsulation) tunnels and BGP (Border Gateway Protocol).

Transit Gateway Connect provides dynamic routing, faster convergence, and simplified hybrid cloud networking.

---

# Architecture Diagram

```text
                 Branch Office
                      │
                      ▼
              SD-WAN Edge Router
                      │
                 GRE Tunnel
                      │
                BGP Session
                      │
                      ▼
          Transit Gateway Connect Peer
                      │
                      ▼
         AWS Transit Gateway Connect
                      │
          Transit Gateway Route Table
          ┌───────────┼───────────┐
          ▼           ▼           ▼
     Production     Shared     Development
        VPC           VPC           VPC
```

---

# What is AWS Transit Gateway Connect?

AWS Transit Gateway Connect allows virtual routers and SD-WAN appliances to connect to AWS Transit Gateway using GRE tunnels while exchanging routes dynamically through BGP.

Unlike Site-to-Site VPN, Transit Gateway Connect is optimized for high-throughput enterprise networking.

---

# Why Use Transit Gateway Connect?

Benefits include:

- Dynamic route exchange
- Faster routing convergence
- High scalability
- Reduced operational overhead
- Native SD-WAN integration

---

# Core Components

- AWS Transit Gateway
- Transport Attachment
- Transit Gateway Connect Attachment
- Connect Peer
- GRE Tunnel
- BGP Session

---

# Transit Gateway Connect Attachment

A Connect Attachment is created on top of an existing transport attachment.

Supported transport attachments include:

- VPC Attachment
- AWS Direct Connect Attachment

The transport attachment carries GRE traffic.

---

# Transit Gateway Connect Peer

A Connect Peer establishes:

- GRE tunnel
- BGP peering session

Each Connect Peer exchanges routing information dynamically with AWS Transit Gateway.

---

# GRE Tunnel

GRE encapsulates routing traffic between:

- SD-WAN appliance
- AWS Transit Gateway

Benefits include:

- Lightweight encapsulation
- Flexible routing
- High performance

---

# BGP Peering

BGP provides:

- Dynamic route learning
- Automatic route updates
- Failover
- Route convergence

---

# Route Propagation

Routes learned through BGP are propagated into Transit Gateway Route Tables.

Traffic is automatically forwarded to connected VPCs.

---

# High Availability

Enterprise deployments should use:

- Multiple Connect Peers
- Multiple Availability Zones
- Redundant SD-WAN appliances
- Redundant BGP sessions

---

# Enterprise Use Cases

- Cisco SD-WAN
- VMware SD-WAN
- Fortinet SD-WAN
- Branch office connectivity
- Hybrid cloud
- Multi-region enterprise networking

---

# Best Practices

- Deploy redundant Connect Peers.
- Use multiple Availability Zones.
- Monitor BGP sessions continuously.
- Test failover regularly.
- Document routing policies.
- Use route summarization when appropriate.

---

# Common Troubleshooting

## GRE Tunnel Down

Verify:

- Connect Attachment
- GRE endpoint IP addresses
- Appliance configuration

---

## BGP Neighbor Down

Check:

- ASN configuration
- Inside CIDR
- GRE tunnel status
- Firewall rules

---

## Routes Not Propagating

Verify:

- Route propagation
- Transit Gateway Route Tables
- BGP advertisements

---

# Advantages

- High-performance routing
- Dynamic BGP
- SD-WAN integration
- Enterprise scalability
- Simplified hybrid networking

---

# Limitations

- Requires GRE support.
- Requires BGP configuration.
- Requires supported SD-WAN appliances.

---

# Summary

AWS Transit Gateway Connect enables enterprise SD-WAN integration with AWS using GRE tunnels and BGP, providing scalable, dynamic, and highly available hybrid cloud connectivity.
