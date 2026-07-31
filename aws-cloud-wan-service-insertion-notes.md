# AWS Cloud WAN Service Insertion

## Overview

AWS Cloud WAN Service Insertion allows organizations to centrally inspect network traffic by steering it through security appliances before forwarding it to its destination. This enables consistent security enforcement across multiple AWS Regions, VPCs, and hybrid environments.

Instead of deploying security appliances in every VPC, Service Insertion centralizes traffic inspection using AWS Network Firewall or third-party firewall appliances.

---

# Architecture Diagram

```
                    On-Premises
                         │
                AWS Direct Connect
                         │
                         ▼
                 AWS Cloud WAN
                  Core Network
                         │
              Network Function Group
                         │
        ┌────────────────┼────────────────┐
        ▼                                 ▼
AWS Network Firewall             Third-Party Firewall
        │                                 │
        └────────────────┬────────────────┘
                         ▼
                  Destination VPC
```

---

# What is AWS Cloud WAN Service Insertion?

Service Insertion is the process of automatically redirecting network traffic through centralized security services before allowing it to reach its destination.

This provides:

- Centralized security inspection
- Consistent policy enforcement
- Simplified network architecture
- Reduced operational overhead

---

# Why Service Insertion is Needed

Without Service Insertion:

- Each VPC requires its own firewall.
- Security policies become difficult to manage.
- Operational costs increase.

With Service Insertion:

- One centralized security layer protects multiple VPCs.
- Security policies remain consistent.
- Traffic inspection becomes easier to manage.

---

# Core Network Policies

Core Network Policies define:

- Traffic segmentation
- Routing rules
- Service insertion rules
- Network attachments
- Security enforcement

---

# Network Function Groups

Network Function Groups logically group security appliances together.

Examples:

- AWS Network Firewall
- Palo Alto VM-Series
- Fortinet FortiGate
- Check Point CloudGuard

---

# Security Appliance Integration

Supported security solutions include:

- AWS Network Firewall
- Palo Alto Networks VM-Series
- Fortinet FortiGate
- Check Point CloudGuard
- Cisco Secure Firewall

---

# East-West Traffic Inspection

East-West traffic is communication between workloads inside AWS.

Example:

VPC A → Firewall → VPC B

---

# North-South Traffic Inspection

North-South traffic is communication between AWS and external networks.

Example:

Internet → Firewall → Application

or

On-Premises → Firewall → AWS

---

# Integration with AWS Network Firewall

AWS Network Firewall provides:

- Stateful inspection
- Stateless inspection
- Domain filtering
- Threat detection
- Intrusion prevention

---

# Integration with Third-Party Firewalls

Cloud WAN supports third-party virtual firewalls to provide:

- Deep Packet Inspection (DPI)
- Advanced Threat Protection
- URL Filtering
- SSL Inspection
- Malware Detection

---

# Multi-Region Traffic Steering

Cloud WAN can steer traffic across multiple AWS Regions while ensuring traffic passes through centralized security appliances.

Benefits include:

- Centralized security
- Simplified routing
- Consistent compliance

---

# Enterprise Architecture

```
               Branch Office
                     │
                     ▼
              AWS Direct Connect
                     │
                     ▼
                AWS Cloud WAN
                     │
              Core Network Policy
                     │
            Network Function Group
                     │
              AWS Network Firewall
                     │
         ┌───────────┼───────────┐
         ▼           ▼           ▼
      VPC A       VPC B       VPC C
```

---

# Enterprise Use Cases

- Banking
- Healthcare
- Government
- Retail
- Multi-Account AWS Environments
- Hybrid Cloud Networks
- Zero Trust Security

---

# Best Practices

- Centralize security inspection.
- Use least-privilege routing policies.
- Monitor Cloud WAN metrics.
- Enable CloudWatch logging.
- Regularly review Core Network Policies.
- Deploy firewalls across multiple Availability Zones.
- Test failover scenarios.

---

# Common Troubleshooting

## Traffic Not Passing Through Firewall

Verify:

- Core Network Policy
- Service Insertion configuration
- Route propagation
- Attachments

---

## Firewall Not Receiving Traffic

Check:

- Network Function Group
- Routing policy
- Cloud WAN attachment

---

## Connectivity Issues

Verify:

- Route tables
- Security Groups
- AWS Network Firewall rules

---

## High Latency

Review:

- Firewall performance
- Traffic path
- Cross-Region routing

---

# Advantages

- Centralized security
- Simplified management
- Enterprise scalability
- Multi-Region support
- Consistent security policies
- Lower operational costs

---

# Summary

AWS Cloud WAN Service Insertion enables organizations to centrally inspect, secure, and manage network traffic across multiple AWS Regions using AWS Network Firewall and third-party security appliances. It simplifies enterprise cloud networking while improving security, scalability, and operational efficiency.
