# AWS Network Firewall Rule Variables

## Overview

AWS Network Firewall Rule Variables allow administrators to create reusable IP addresses, CIDR ranges, and port groups that can be referenced inside Suricata-compatible rules. This improves readability, simplifies management, and reduces duplication across enterprise firewall policies.

---

# Architecture Diagram

```text
Application VPC
       │
       ▼
Transit Gateway
       │
       ▼
Inspection VPC
       │
       ▼
AWS Network Firewall
       │
       ▼
Stateful Rule Group
       │
       ▼
Rule Variables
 ┌─────┼──────────────┐
 ▼     ▼              ▼
IP Set Port Set   HOME_NET
 │      │             │
 └──────┼─────────────┘
        ▼
 Suricata Rules
        │
        ▼
PASS / DROP / REJECT / ALERT
        │
        ▼
Destination
```

---

# What are Rule Variables?

Rule Variables are reusable objects that store:

- IP Addresses
- CIDR Blocks
- Port Numbers
- Port Ranges

These variables simplify firewall rule management.

---

# Why Use Rule Variables?

Benefits include:

- Easier policy management
- Reusable configurations
- Reduced configuration errors
- Simplified rule updates
- Enterprise scalability

---

# IP Sets

IP Sets contain one or more:

- IP Addresses
- CIDR Blocks

Example:

```text
WEB_SERVERS

10.10.1.10
10.10.1.11
10.10.2.0/24
```

Suricata Rule:

```text
$WEB_SERVERS
```

---

# Port Sets

Port Sets define reusable ports.

Example:

```text
WEB_PORTS

80
443
8080
```

Reference:

```text
$WEB_PORTS
```

---

# HOME_NET

HOME_NET represents trusted internal networks.

Example:

```text
10.10.0.0/16
10.20.0.0/16
10.30.0.0/16
```

---

# EXTERNAL_NET

EXTERNAL_NET represents all networks outside HOME_NET.

Traffic entering from external networks can be inspected against enterprise security rules.

---

# Custom Variables

Organizations can create variables for:

- Database Servers
- Application Servers
- Domain Controllers
- Web Servers
- Management Networks

---

# Firewall Policy Variables

Firewall Policies can reference:

- HOME_NET
- EXTERNAL_NET

These variables are inherited by Stateful Rule Groups.

---

# Rule Group Variables

Rule Groups may define their own variables when different network scopes are required.

---

# Suricata Variable Example

```text
alert tcp $EXTERNAL_NET any -> $WEB_SERVERS $WEB_PORTS (msg:"Allow Web Traffic"; sid:1000001; rev:1;)
```

---

# Logging

Integrate with:

- Amazon CloudWatch Logs
- Amazon S3
- Amazon Kinesis Data Firehose

---

# Monitoring

Monitor using:

- CloudWatch Metrics
- Firewall Logs
- AWS CloudTrail

---

# Enterprise Use Cases

- Multi-VPC environments
- Shared security services
- Centralized inspection
- Zero Trust Architecture
- Enterprise firewall management

---

# Best Practices

- Use descriptive variable names.
- Group related IP addresses.
- Reuse variables across rules.
- Document variables.
- Review variables regularly.
- Keep variables organized.

---

# Limitations

- Variables must follow Suricata syntax.
- Incorrect variable definitions may cause rule failures.

---

# Common Troubleshooting

## Rule Not Matching

Verify:

- Variable names
- IP addresses
- Port numbers
- Rule order

---

## Incorrect Traffic Matching

Check:

- HOME_NET
- EXTERNAL_NET
- Firewall Policy Variables

---

# Summary

AWS Network Firewall Rule Variables improve enterprise firewall management by providing reusable IP Sets, Port Sets, HOME_NET, and EXTERNAL_NET definitions that simplify Suricata-compatible rule creation.
