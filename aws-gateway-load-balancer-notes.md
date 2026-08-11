# AWS Gateway Load Balancer (GWLB)

## Overview

AWS Gateway Load Balancer (GWLB) enables enterprises to deploy, scale, and manage third-party virtual network appliances such as firewalls, intrusion detection systems (IDS), intrusion prevention systems (IPS), and deep packet inspection (DPI) appliances.

GWLB combines transparent network gateway functionality with load balancing, allowing traffic to be automatically distributed across multiple security appliances.

---

# Architecture Diagram

```text
                Internet
                    │
                    ▼
             Internet Gateway
                    │
                    ▼
     Gateway Load Balancer Endpoint
                    │
                    ▼
       Gateway Load Balancer (GWLB)
                    │
             GENEVE (UDP 6081)
                    │
         ┌──────────┴──────────┐
         ▼                     ▼
   Firewall VM-1         Firewall VM-2
         │                     │
         └──────────┬──────────┘
                    ▼
           Inspected Network Traffic
                    │
                    ▼
             Application VPC
```

---

# What is AWS Gateway Load Balancer?

AWS Gateway Load Balancer provides transparent insertion of security appliances into network traffic flows.

It automatically distributes traffic across multiple virtual appliances while preserving the original packet information.

---

# Why Use Gateway Load Balancer?

Benefits include:

- Centralized security inspection
- Automatic load balancing
- High availability
- Transparent traffic forwarding
- Enterprise scalability

---

# GWLB Components

- Gateway Load Balancer
- Gateway Load Balancer Endpoint (GWLBe)
- Endpoint Service
- Target Group
- Security Appliances
- Route Tables

---

# Gateway Load Balancer Endpoint (GWLBe)

A Gateway Load Balancer Endpoint allows traffic from a consumer VPC to reach centralized security appliances located in another VPC.

It is deployed in each Availability Zone.

---

# Endpoint Service

The Endpoint Service exposes the Gateway Load Balancer to consumer VPCs using AWS PrivateLink.

---

# GENEVE Protocol

GWLB encapsulates traffic using:

- Protocol: GENEVE
- UDP Port: 6081

GENEVE preserves packet metadata while forwarding traffic to security appliances.

---

# Target Groups

Target Groups contain registered virtual appliances.

Examples:

- Palo Alto VM-Series
- Fortinet FortiGate
- Check Point CloudGuard
- Cisco Secure Firewall

---

# Health Checks

GWLB continuously monitors appliance health.

If an appliance becomes unavailable, traffic is redirected to healthy appliances.

---

# Traffic Flow

1. Client sends traffic.
2. Route Table forwards traffic to GWLBe.
3. GWLBe forwards traffic to GWLB.
4. GWLB encapsulates traffic using GENEVE.
5. Security appliance inspects traffic.
6. Traffic is forwarded to the destination.

---

# Route Tables

Route Tables determine which traffic is redirected to the Gateway Load Balancer Endpoint.

Proper routing is required for transparent inspection.

---

# High Availability

Best practices include:

- Deploy GWLB in multiple Availability Zones.
- Register multiple appliances.
- Monitor appliance health.
- Test failover regularly.

---

# Firewall Integration

GWLB integrates with:

- Palo Alto VM-Series
- Fortinet FortiGate
- Check Point CloudGuard
- Cisco Secure Firewall
- Other supported virtual appliances

---

# Monitoring

Monitor using:

- Amazon CloudWatch Metrics
- Amazon VPC Flow Logs
- Appliance logs
- AWS CloudTrail

---

# Enterprise Use Cases

- Centralized firewall inspection
- IDS/IPS deployment
- Deep Packet Inspection
- East-West traffic inspection
- North-South traffic inspection
- Hybrid Cloud Security
- Zero Trust Architecture

---

# Best Practices

- Deploy endpoints in every Availability Zone.
- Use multiple security appliances.
- Monitor appliance health continuously.
- Keep route tables synchronized.
- Review logs regularly.
- Test failover scenarios.

---

# Limitations

- Requires compatible virtual appliances.
- GENEVE encapsulation support is required.
- Access logging is not generated directly by GWLB.
- Appliance performance affects overall throughput.

---

# Common Troubleshooting

## Traffic Not Reaching Firewall

Check:

- Route Tables
- Gateway Load Balancer Endpoint
- Target Group Health

---

## Appliance Unhealthy

Verify:

- Health Checks
- Appliance configuration
- Security Groups
- Network ACLs

---

## Traffic Bypassing Inspection

Review:

- Route Tables
- Endpoint associations
- GWLB Endpoint configuration

---

# Summary

AWS Gateway Load Balancer enables centralized deployment of scalable security appliances using GENEVE encapsulation and transparent traffic forwarding. It improves enterprise security, scalability, and operational efficiency by distributing traffic across multiple healthy appliances.
