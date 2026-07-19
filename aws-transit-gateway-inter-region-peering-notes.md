# AWS Transit Gateway Inter-Region Peering

## Overview

AWS Transit Gateway Inter-Region Peering enables Transit Gateways deployed in different AWS Regions to communicate with each other over the AWS Global Network. This provides secure, high-performance connectivity between regional AWS environments without requiring VPN tunnels over the public internet.

---

# Architecture Diagram

```
                 AWS Global Network

          ┌──────────────────────────────┐
          │ Transit Gateway Peering      │
          └──────────────┬───────────────┘
                         │
      ┌──────────────────┴──────────────────┐
      ▼                                     ▼
US-East-1                            US-West-2
Transit Gateway                    Transit Gateway
      │                                     │
   Production VPC                     Disaster Recovery VPC
      │                                     │
      EC2                                 EC2
```

---

# Key Components

- AWS Transit Gateway
- Inter-Region Peering Attachment
- VPC Attachments
- Transit Gateway Route Tables
- VPC Route Tables
- Security Groups
- Network ACLs

---

# Configuration Workflow

1. Create a Transit Gateway in each AWS Region.
2. Create an Inter-Region Peering Attachment.
3. Accept the peering request in the peer Region.
4. Update Transit Gateway Route Tables.
5. Update VPC Route Tables.
6. Verify Security Groups and Network ACLs.
7. Test connectivity between Regions.

---

# Enterprise Use Cases

- Disaster Recovery
- Multi-Region Applications
- Global Enterprise Networks
- Cross-Region Data Replication
- Centralized Shared Services

---

# Best Practices

- Use summarised CIDR ranges when possible.
- Keep route tables simple and documented.
- Monitor Transit Gateway metrics with CloudWatch.
- Enable VPC Flow Logs.
- Validate routing after every network change.

---

# Common Troubleshooting

## Peering Attachment Pending

Verify that the request has been accepted in the peer Region.

## No Connectivity

Check:

- Transit Gateway Route Tables
- VPC Route Tables
- Security Groups
- Network ACLs

## One-Way Traffic

Verify return routes are configured correctly.

## Packet Loss

Review MTU settings, route propagation, and CloudWatch metrics.

---

# Advantages

- Global AWS backbone connectivity
- Lower latency than internet-based VPNs
- Highly available architecture
- Simplified global network management
- Scalable enterprise design

---

# Summary

Transit Gateway Inter-Region Peering provides secure, scalable connectivity between AWS Regions using the AWS Global Network, making it an essential building block for enterprise multi-region architectures.
