# AWS VPC Lattice Cross-Account Service Sharing

## Overview

AWS VPC Lattice allows services hosted in one AWS account to be securely shared with applications running in other AWS accounts. This enables centralized platform teams to publish common services while allowing application teams to consume them without creating complex VPC peering or Transit Gateway configurations.

Cross-account sharing is commonly implemented with AWS Resource Access Manager (AWS RAM), IAM policies, and VPC Lattice Service Networks.

---

# Architecture Diagram

```
                 AWS Organization

      Shared Services Account
               │
     VPC Lattice Service Network
               │
     Shared API / Authentication
               │
        AWS RAM Share
     ┌─────────┼─────────┐
     ▼         ▼         ▼
Account A  Account B  Account C
 Orders     Finance      HR
    │           │          │
  VPC         VPC        VPC
```

---

# Key Components

## VPC Lattice Service

Publishes applications that other AWS accounts can consume.

---

## Service Network

Provides centralized connectivity between shared services and consumer VPCs.

---

## AWS Resource Access Manager (AWS RAM)

Shares Service Networks across AWS accounts.

---

## IAM Policies

Control which accounts, users, and roles can access shared services.

---

## VPC Associations

Associate consumer VPCs with the shared Service Network.

---

# Configuration Workflow

1. Create a VPC Lattice Service.
2. Create or select a Service Network.
3. Share the Service Network using AWS RAM.
4. Accept the resource share in the consumer account.
5. Associate the consumer VPC with the Service Network.
6. Configure IAM authorization.
7. Test cross-account connectivity.

---

# Enterprise Use Cases

- Shared authentication services
- Central logging platforms
- Internal API platforms
- Enterprise microservices
- Shared DevOps tools
- Multi-account landing zones

---

# Best Practices

- Follow least-privilege IAM access.
- Share only required Service Networks.
- Separate Production and Non-Production environments.
- Enable CloudWatch monitoring.
- Enable access logging.
- Review AWS RAM shares regularly.
- Document account ownership.

---

# Common Troubleshooting Scenarios

## Consumer Account Cannot Access Service

Verify:

- AWS RAM share accepted
- Service Network association
- IAM permissions
- Resource policies

---

## Access Denied

Check:

- IAM role
- Resource-based policy
- Organization permissions

---

## Service Not Reachable

Verify:

- VPC association
- Listener configuration
- Target Group health

---

## Cross-Account DNS Issues

Review:

- Route 53 configuration
- Service discovery
- DNS resolution

---

# Advantages

- Simplified multi-account networking
- Centralized service management
- Reduced network complexity
- Secure service sharing
- Native AWS integration
- Enterprise scalability

---

# Summary

AWS VPC Lattice Cross-Account Service Sharing enables organizations to securely publish and consume application services across AWS accounts using Service Networks, AWS RAM, and IAM, supporting scalable enterprise multi-account architectures.
