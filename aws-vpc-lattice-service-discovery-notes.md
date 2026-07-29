# AWS VPC Lattice Service Discovery

## Overview

AWS VPC Lattice provides built-in DNS-based service discovery, allowing applications to communicate using service names instead of IP addresses. This simplifies application connectivity, improves scalability, and supports dynamic infrastructure changes.

Applications can automatically discover services running across multiple VPCs and AWS accounts through the VPC Lattice Service Network.

---

# Architecture Diagram

```
                  Client Application
                         │
                DNS Lookup Request
                         │
                         ▼
               AWS VPC Lattice DNS
                         │
                         ▼
              Service Network
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
    Orders API      Payment API      User API
        │                │                │
        ▼                ▼                ▼
      EC2/ECS          ECS/EKS         Lambda
```

---

# Key Components

## Service Network

A logical container where services are registered.

---

## Service Discovery

Applications discover services using DNS names instead of IP addresses.

Example:

```
orders.internal
payments.internal
users.internal
```

---

## DNS Resolution

VPC Lattice resolves service names to healthy backend targets.

---

## Target Groups

Contain backend resources that receive application traffic.

---

## Health Checks

Only healthy targets are returned during service discovery.

---

## IAM Integration

Access to discovered services is controlled using IAM and resource policies.

---

# Configuration Workflow

1. Create a Service Network.
2. Create one or more VPC Lattice Services.
3. Associate services with the Service Network.
4. Associate VPCs with the Service Network.
5. Configure IAM permissions.
6. Verify DNS resolution.
7. Test application connectivity.

---

# Enterprise Use Cases

- Enterprise microservices
- Internal APIs
- Shared platform services
- Multi-account application networking
- Zero Trust architectures

---

# Best Practices

- Use meaningful service names.
- Organize related services within the same Service Network.
- Configure health checks for every Target Group.
- Monitor DNS resolution using CloudWatch.
- Apply least-privilege IAM policies.
- Document service naming standards.

---

# Common Troubleshooting Scenarios

## DNS Resolution Fails

Verify:

- VPC association
- Service association
- DNS configuration
- IAM permissions

---

## Service Not Reachable

Check:

- Target Group health
- Listener configuration
- Security Groups

---

## Intermittent Connectivity

Review:

- Health checks
- CloudWatch metrics
- Backend application status

---

## Unauthorized Access

Verify:

- IAM policy
- Resource-based policy
- Service Network policy

---

# Advantages

- Automatic service discovery
- DNS-based communication
- Simplified application networking
- High scalability
- Native AWS integration
- Enterprise-ready architecture

---

# Summary

AWS VPC Lattice Service Discovery enables secure, DNS-based communication between applications across VPCs and AWS accounts, simplifying enterprise microservices networking while maintaining centralized security and policy enforcement.
