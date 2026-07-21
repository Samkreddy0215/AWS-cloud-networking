# AWS Cloud WAN Segment Routing

## Overview

AWS Cloud WAN Segment Routing allows enterprises to logically separate networks into different segments while centrally controlling communication between them. Segments help isolate environments such as Production, Development, Testing, and Shared Services without deploying separate networking infrastructures.

---

# Architecture Diagram

```
                    AWS Cloud WAN
                 Core Network Policy
                        │
        ┌───────────────┼───────────────┐
        │               │               │
        ▼               ▼               ▼
 Production        Development     Shared Services
   Segment            Segment          Segment
        │               │               │
     VPCs            VPCs          DNS / AD / Logging
        │               │               │
        └───────────────┼───────────────┘
                        │
              Segment Routing Policies
```

---

# Key Components

## Core Network
Central global network managed by AWS Cloud WAN.

## Segments
Logical groups of network resources.

Examples:
- Production
- Development
- Testing
- Shared Services

## Segment Actions
Define whether traffic is:
- Allowed
- Blocked
- Shared

## Attachments
Resources connected to segments:
- VPC Attachments
- VPN Attachments
- Direct Connect Attachments

## Routing Policies
Control communication between segments.

---

# Configuration Workflow

1. Create a Cloud WAN Core Network.
2. Create network segments.
3. Attach VPCs to the correct segments.
4. Configure segment routing rules.
5. Deploy the Core Network Policy.
6. Validate route propagation.
7. Test inter-segment connectivity.

---

# Enterprise Use Cases

- Production and Development isolation
- Shared Services architecture
- Global enterprise WAN
- Hybrid cloud networking
- Business unit separation
- Compliance-driven network segmentation

---

# Best Practices

- Use dedicated segments for each environment.
- Follow least-privilege communication.
- Document routing policies.
- Test policy changes before production.
- Monitor routing with CloudWatch.
- Review segment membership regularly.

---

# Common Troubleshooting Scenarios

## Segments Cannot Communicate

Verify:
- Segment sharing rules
- Core Network Policy
- Route propagation
- Attachment status

## Missing Routes

Check:
- Core Network Policy deployment
- Route advertisements
- Attachment associations

## Unexpected Connectivity

Review:
- Segment actions
- Policy rules
- Shared route configuration

## Attachment Issues

Verify:
- Attachment health
- Region compatibility
- Policy deployment status

---

# Advantages

- Centralized routing
- Strong network isolation
- Scalable enterprise architecture
- Simplified policy management
- Native AWS integration

---

# Summary

AWS Cloud WAN Segment Routing enables centralized control of traffic flow between enterprise network segments, improving security, scalability, and operational efficiency across global AWS environments.
